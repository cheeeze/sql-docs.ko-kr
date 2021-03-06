---
title: SQL Server Integration Services Scale Out의 인증서 관리 | Microsoft Docs
description: 이 문서에서는 SSIS Scale Out 마스터 및 Scale Out 작업자 간의 통신을 보호하기 위해 인증서를 관리하는 방법을 설명합니다.
ms.date: 12/19/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.custom: performance
ms.topic: conceptual
author: haoqian
ms.author: haoqian
ms.openlocfilehash: 087b7d14e46c09b37d0de1cef165e250845b9183
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86919026"
---
# <a name="manage-certificates-for-sql-server-integration-services-scale-out"></a>SQL Server Integration Services Scale Out의 인증서 관리

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]



Scale Out 마스터와 Scale Out 작업자 사이의 통신 보안을 위해 SSIS Scale Out은 두 가지 인증서(마스터를 위한 인증서 하나와 작업자를 위한 인증서 하나)를 사용합니다. 

## <a name="scale-out-master-certificate"></a>Scale Out 마스터 인증서

대부분의 경우 Scale Out 마스터 인증서는 Scale Out 마스터 설치 중에 구성됩니다.

SQL Server 설치 마법사의 **Integration Services Scale Out 구성 - 마스터 노드** 페이지에서 자체 서명 TLS/SSL 인증서를 새로 만들거나 기존 TLS/SSL 인증서를 사용하도록 선택할 수 있습니다.

![마스터 구성](media/master-config.PNG)

**새 인증서**. 인증서에 특별한 요구 사항이 없는 경우 자체 서명 TLS/SSL 인증서를 새로 만들도록 선택할 수 있습니다. 인증서의 CN을 더 지정할 수 있습니다. 나중에 Scale Out 작업자에 사용될 마스터 엔드포인트의 호스트 이름이 CN에 포함되어야 합니다. 기본적으로 마스터 노드의 컴퓨터 이름과 IP 주소가 포함됩니다. 

**기존 인증서**. 기존 인증서를 사용하도록 선택하는 경우 로컬 컴퓨터의 **루트** 인증서 저장소에서 **찾아보기**를 클릭하여 TLS/SSL 인증서를 선택합니다.

### <a name="change-the-scale-out-master-certificate"></a>Scale Out 마스터 인증서 변경

인증서 만료나 기타 이유로 인해 Scale Out 마스터 인증서를 변경할 수 있습니다. Scale Out 마스터 인증서를 변경하려면 다음을 수행합니다.

#### <a name="1-create-a-tlsssl-certificate"></a>1. TLS/SSL 인증서를 만듭니다.
다음 명령으로 마스터 노드에 TLS/SSL 인증서를 만들고 설치합니다.

```dos
MakeCert.exe -n CN={master endpoint host} SSISScaleOutMaster.cer -r -ss Root -sr LocalMachine -a sha1
```
예를 들면 다음과 같습니다.

```dos
MakeCert.exe -n CN=MasterMachine SSISScaleOutMaster.cer -r -ss Root -sr LocalMachine -a sha1
```

#### <a name="2-bind-the-certificate-to-the-master-port"></a>2. 인증서를 마스터 포트에 바인딩
다음 명령으로 원래 바인딩을 확인합니다.

```dos
netsh http show sslcert ipport=0.0.0.0:{Master port}
```

예를 들면 다음과 같습니다.

```dos
netsh http show sslcert ipport=0.0.0.0:8391
```

다음 명령을 사용하여 원래 바인딩을 삭제하고 새 바인딩을 설정합니다.

```dos
netsh http delete sslcert ipport=0.0.0.0:{Master port}
netsh http add sslcert ipport=0.0.0.0:{Master port} certhash={TLS/SSL Certificate Thumbprint} certstorename=Root appid={original appid}
```

예를 들면 다음과 같습니다.

```dos
netsh http delete sslcert ipport=0.0.0.0:8391
netsh http add sslcert ipport=0.0.0.0:8391 certhash=01d207b300ca662f479beb884efe6ce328f77d53 certstorename=Root appid={a1f96506-93e0-4c91-9171-05a2f6739e13}
```

#### <a name="3-update-the-scale-out-master-service-configuration-file"></a>3. Scale Out 마스터 서비스 구성 파일 업데이트
마스터 노드에서 Scale Out 마스터 서비스 구성 파일인 `\<drive\>:\Program Files\Microsoft SQL Server\140\DTS\Binn\MasterSettings.config`를 업데이트합니다. **SSLCertThumbprint**를 새 TLS/SSL 인증서의 지문으로 업데이트합니다.

#### <a name="4-restart-the-scale-out-master-service"></a>4. Scale Out 마스터 서비스 다시 시작

#### <a name="5-reconnect-scale-out-workers-to-scale-out-master"></a>5. Scale Out 작업자를 Scale Out 마스터에 다시 연결
각 Scale Out 작업자에 대해 작업자를 삭제한 다음 [Scale Out 관리자](integration-services-ssis-scale-out-manager.md)를 사용하여 다시 추가하거나 다음을 수행합니다.

a.  작업자 노드에서 로컬 컴퓨터의 루트 저장소에 클라이언트 TLS/SSL 인증서를 설치합니다.

b.  Scale Out 작업자 서비스 구성 파일을 업데이트합니다.

작업자 노드에서 Scale Out 작업자 서비스 구성 파일인 `\<drive\>:\Program Files\Microsoft SQL Server\140\DTS\Binn\WorkerSettings.config`를 업데이트합니다. **MasterHttpsCertThumbprint**를 새 TLS/SSL 인증서의 지문으로 업데이트합니다.

다.  Scale Out 작업자 서비스를 다시 시작합니다.

## <a name="scale-out-worker-certificate"></a>Scale Out 작업자 인증서

Scale Out 작업자 인증서는 Scale Out 작업자를 설치하는 동안 자동으로 생성됩니다. 

### <a name="change-the-scale-out-worker-certificate"></a>Scale Out 작업자 인증서 변경

Scale Out 작업자 인증서를 변경하려는 경우 다음을 수행합니다.

#### <a name="1-create-a-certificate"></a>1. 인증서 만들기
다음 명령을 사용하여 인증서를 만들고 설치합니다.

```dos
MakeCert.exe -n CN={worker machine name};CN={worker machine ip} SSISScaleOutWorker.cer -r -ss My -sr LocalMachine
```

예를 들면 다음과 같습니다.

```dos
MakeCert.exe -n CN=WorkerMachine;CN=10.0.2.8 SSISScaleOutWorker.cer -r -ss My -sr LocalMachine
```

#### <a name="2-install-the-client-certificate-to-the-root-store-of-the-local-computer-on-the-worker-node"></a>2. 작업자 노드에서 로컬 컴퓨터의 루트 저장소에 클라이언트 인증서 설치

#### <a name="3-grant-service-access-to-the-certificate"></a>3. 인증서에 서비스 액세스 권한 부여
다음 명령을 사용하여 이전 인증서를 삭제하고 새 인증서에 Scale Out 작업자 서비스에 대한 액세스 권한을 부여합니다.

```dos
certmgr.exe /del /c /s /r localmachine My /n {CN of the old certificate}
winhttpcertcfg.exe -g -c LOCAL_MACHINE\My -s {CN of the new certificate} -a {the account running Scale Out Worker service}
```

예를 들면 다음과 같습니다.

```dos
certmgr.exe /del /c /s /r localmachine My /n WorkerMachine
winhttpcertcfg.exe -g -c LOCAL_MACHINE\My -s WorkerMachine -a SSISScaleOutWorker140
```

#### <a name="4-update-the-scale-out-worker-service-configuration-file"></a>4. Scale Out 작업자 서비스 구성 파일 업데이트
작업자 노드에서 Scale Out 작업자 서비스 구성 파일인 `\<drive\>:\Program Files\Microsoft SQL Server\140\DTS\Binn\WorkerSettings.config`를 업데이트합니다. **WorkerHttpsCertThumbprint**를 새 인증서의 지문으로 업데이트합니다.

#### <a name="5-install-the-client-certificate-to-the-root-store-of-the-local-computer-on-the-master-node"></a>5. 마스터 노드에서 로컬 컴퓨터의 루트 저장소에 클라이언트 인증서 설치

#### <a name="6-restart-the-scale-out-worker-service"></a>6. Scale Out 작업자 서비스 다시 시작

## <a name="next-steps"></a>다음 단계
자세한 내용은 다음 문서를 참조하세요.
-   [Integration Services(SSIS) Scale Out 마스터](integration-services-ssis-scale-out-master.md)
-   [Integration Services(SSIS) Scale Out 작업자](integration-services-ssis-scale-out-worker.md)
