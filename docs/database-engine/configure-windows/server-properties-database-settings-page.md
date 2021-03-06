---
title: 서버 속성(데이터베이스 설정 페이지) | Microsoft Docs
description: SQL Server의 데이터베이스 설정을 파악합니다. 백업 동작, 채우기 비율, 파일 위치 및 기타 속성을 제어하는 옵션에 대해 알아봅니다.
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql13.swb.serverproperties.databasesettings.f1
ms.assetid: 1cebdbd3-cbfd-4a02-bba6-a5addf4e3ada
author: markingmyname
ms.author: maghan
ms.custom: ''
ms.date: 05/23/2019
ms.openlocfilehash: a4f5a0dacaeeeadf0446df9e4d3cdf54fcad7be2
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85784126"
---
# <a name="server-properties---database-settings-page"></a>서버 속성 - 데이터베이스 설정 페이지

 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  이 페이지를 사용하여 데이터베이스 설정을 보거나 수정할 수 있습니다.  
  
## <a name="options"></a>옵션

### <a name="default-index-fill-factor"></a>기본 인덱스 채우기 비율

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에서 기존 데이터를 사용하여 새 인덱스를 만들 때 각 페이지를 채우는 비율을 지정합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에서 페이지를 채울 때 페이지를 분할하는 데 시간이 걸리므로 채우기 비율은 성능에 영향을 줍니다.
  
기본값은 0이고 유효한 값은 0에서 100 사이입니다. 채우기 비율을 0이나 100으로 지정하면 완전히 채워진 데이터 페이지로 이루어진 클러스터형 인덱스와 완전히 채워진 리프 페이지로 이루어진 비클러스터형 인덱스가 만들어지지만 인덱스 트리 위쪽에 약간의 공간이 남습니다. 채우기 비율 값 0과 100은 모든 면에서 동일합니다.
  
채우기 비율 값을 작게 설정하면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 는 인덱스의 페이지를 가득 채우지 않습니다. 이 경우 각 인덱스가 더 많은 스토리지 공간을 차지하지만 이후에 데이터를 삽입할 때 페이지를 분할할 필요가 없도록 여유 공간이 생깁니다.
  
### <a name="wait-indefinitely"></a>무기한 대기

[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 가 새 백업 테이프를 기다리는 동안 시간 제한을 두지 않도록 지정합니다.  

### <a name="try-once"></a>한 번 시도

필요할 때 백업 테이프를 사용할 수 없으면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에서 시간 초과가 발생하도록 지정합니다.

### <a name="try-for-minutes"></a>시도 시간(분)

지정한 기간 내에 백업 테이프를 사용할 수 없으면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에서 시간 초과가 발생하도록 지정합니다.  

### <a name="default-backup-media-retention-in-days"></a>백업 미디어 기본 보존 기간(일)

데이터베이스 또는 트랜잭션 로그 백업에 각 백업 미디어를 사용한 후 각 백업 미디어를 보존하는 기간에 대한 시스템 차원 기본값을 제공합니다. 이 옵션은 지정된 기간이 경과하기 전에는 백업을 덮어쓰지 않게 합니다.  

#### <a name="compress-backup"></a>백업 압축

[!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] (이상 버전)에서 **백업 압축 기본값** 옵션의 현재 설정의 의미합니다. 이 옵션에 따라 다음과 같이 백업 압축의 서버 수준 기본값이 결정됩니다.

- **백업 압축** 상자가 비어 있으면 새 백업은 기본적으로 압축되지 않습니다.

- **백업 압축** 상자가 선택되어 있으면 새 백업은 기본적으로 압축됩니다.
  
    > [!IMPORTANT]
    >  기본적으로 압축하면 CPU 사용량이 크게 늘어나고 압축 프로세스로 사용되는 추가 CPU는 동시 작업에 악영향을 줄 수 있습니다. 따라서 CPU 사용량이 [리소스 관리자](../../relational-databases/resource-governor/resource-governor.md)에 의해 제한되는 세션에서 우선 순위가 낮은 압축 백업을 만들 수 있습니다. 자세한 내용은 이 항목 뒷부분의 [Resource GovernoR을 사용하여 백업 압축을 통해 CPU 사용량 제한&#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)에 의해 제한되는 세션에서 우선 순위가 낮은 압축 백업을 만들 수 있습니다.
  
**sysadmin** 또는 **serveradmin** 고정 서버 역할의 멤버인 경우 **백업 압축** 상자를 클릭하여 설정을 변경할 수도 있습니다.  
  
자세한 내용은 [백업 압축 기본값 서버 구성 옵션 보기 또는 구성](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md) 및 [백업 압축&#40;SQL Server&#41;](../../relational-databases/backup-restore/backup-compression-sql-server.md)을 참조하세요.  

#### <a name="backup-checksum"></a>백업 체크섬

이 옵션을 사용하면 *백업 체크섬 기본값*에 대한 sp_configure 설정을 전환할 수 있습니다. 이 기능을 사용하면 백업 체크섬 기본값을 보다 쉽게 사용할 수 있습니다.

### <a name="recovery-interval-minutes"></a>복구 간격(분)

데이터베이스당 최대 복구 시간을 분 단위로 설정합니다. 기본값 0을 사용하면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 자동으로 구성합니다. 실제로 이 옵션은 1분 미만의 복구 시간이 소요되고 활성 데이터베이스에 대해 약 1분 간격으로 검사점이 실행됩니다. 자세한 내용은 [Configure the recovery interval Server Configuration Option](../../database-engine/configure-windows/configure-the-recovery-interval-server-configuration-option.md)을(를) 참조하세요.  
  
### <a name="data"></a>데이터

데이터 파일의 기본 위치를 지정합니다. 새 기본 위치로 이동하려면 찾아보기 단추를 클릭합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]를 다시 시작해야 적용됩니다.  
  
### <a name="log"></a>로그
  
로그 파일의 기본 위치를 지정합니다. 새 기본 위치로 이동하려면 찾아보기 단추를 클릭합니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]를 다시 시작해야 적용됩니다.  
  
### <a name="configured-values"></a>구성 값

이 창의 옵션에 대해 구성된 값을 표시합니다. 이러한 값을 변경한 후에는 **실행 값** 을 클릭하여 변경 사항이 적용되었는지 여부를 확인합니다. 변경 내용이 적용되지 않은 경우 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]의 인스턴스를 다시 시작해야 합니다.  
  
### <a name="running-values"></a>실행 값

이 창의 옵션에 대한 현재 실행 값을 볼 수 있습니다. 이 값은 읽기 전용입니다.  
  
## <a name="see-also"></a>참고 항목

- [서버 구성 옵션&#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)

- [인덱스의 채우기 비율 지정](../../relational-databases/indexes/specify-fill-factor-for-an-index.md)
