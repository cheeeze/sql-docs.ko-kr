---
title: FCI 수동 장애 조치 - SQL Server on Linux
description: SQL Server on Linux 특히 Red Hat Linux Enterprise, Ubuntu 및 Suse Linux Enterprise Server에서 FCI(장애 조치(failover) 클러스터 인스턴스)를 수동으로 장애 조치하는 방법을 알아봅니다.
ms.custom: seo-lt-2019
author: VanMSFT
ms.author: vanto
ms.reviewer: vanto
ms.date: 12/06/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: linux
ms.assetid: ''
ms.openlocfilehash: c37157d47e2eddaaf47f787de364603cbaaa250a
ms.sourcegitcommit: 610e3ebe21ac6575850a29641a32f275e71557e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91785095"
---
# <a name="operate-failover-cluster-instance---sql-server-on-linux"></a>장애 조치(failover) 클러스터 인스턴스 작동 - SQL Server on Linux

[!INCLUDE [SQL Server - Linux](../includes/applies-to-version/sql-linux.md)]

이 문서에서는 Linux에서 SQL Server FCI(장애 조치(failover) 클러스터 인스턴스)를 작동하는 방법을 설명합니다. Linux에서 SQL Server FCI를 만들지 않은 경우 [장애 조치(failover) 클러스터 인스턴스 구성 - SQL Server on Linux](sql-server-linux-shared-disk-cluster-configure.md)를 참조하세요. 

## <a name="failover"></a>장애 조치

FCI에 대한 장애 조치(failover)는 WSFC(Windows Server 장애 조치(failover) 클러스터)와 비슷합니다. FCI를 호스트하는 클러스터 노드에서 오류가 발생하면 FCI는 자동으로 다른 노드로 장애 조치(failover)됩니다. WSFC와 달리 기본 설정된 소유자를 설정하는 방법은 없으므로 Pacemaker는 FCI의 새 호스트로 사용할 노드를 선택합니다.

FCI를 수동으로 다른 노드로 장애 조치(failover)할 수 있는 경우가 있습니다. 이 프로세스는 WSFC의 FCI와 다릅니다. WSFC에서는 역할 수준에서 리소스를 장애 조치(failover)합니다. Pacemaker에서 이동할 리소스를 선택하며 모든 제약 조건이 올바르면 다른 모든 항목도 이동됩니다. 

장애 조치(failover) 방법은 Linux 배포에 따라 다릅니다. Linux 배포에 대한 지침을 따릅니다.

- [RHEL 또는 Ubuntu](#manual-failover-rhel-or-ubuntu)
- [SLES](#manual-failover-sles)

## <a name="manual-failover-rhel-or-ubuntu"></a>수동 장애 조치(failover)(RHEL 또는 Ubuntu)

RHEL(Red Hat Enterprise Linux) 또는 Ubuntu 서버에서 수동 장애 조치를 수행하려면 다음 단계를 실행합니다.
1.  다음 명령을 실행합니다. 

   ```bash
   sudo pcs resource move <FCIResourceName> <NewHostNode> 
   ```

   \<FCIResourceName>은 SQL Server FCI의 Pacemaker 리소스 이름입니다.

   \<NewHostNode>는 FCI를 호스트하려는 클러스터 노드의 이름입니다. 

   승인은 받지 않습니다.

2.  수동 장애 조치(failover) 중 Pacemaker는 수동으로 이동하도록 선택한 리소스에 대한 위치 제약 조건을 만듭니다. 이 제약 조건을 확인하려면 `sudo pcs constraint`를 실행합니다.

3.  장애 조치(failover)가 완료되면 `sudo pcs resource clear <FCIResourceName>`을 실행하여 제약 조건을 제거합니다. 

\<FCIResourceName>은 FCI의 Pacemaker 리소스 이름입니다. 

## <a name="manual-failover-sles"></a>수동 장애 조치(failover)(SLES)


SLES(Suse Linux Enterprise Server)에서 `migrate` 명령을 사용하여 SQL Server FCI를 수동으로 장애 조치(failover)합니다. 예를 들면 다음과 같습니다.

```bash
crm resource migrate <FCIResourceName> <NewHostNode>
```

\<FCIResourceName>은 장애 조치 클러스터 인스턴스의 리소스 이름입니다. 

\<NewHostNode>는 새 대상 호스트의 이름입니다. 


<!---

|Distribution |Topic 
|----- |-----
|**Red Hat Enterprise Linux with HA add-on** |[Configure](sql-server-linux-shared-disk-cluster-red-hat-7-configure.md)<br/>[Operate](sql-server-linux-shared-disk-cluster-red-hat-7-operate.md)
|**SUSE Linux Enterprise Server with HA add-on** |[Configure](sql-server-linux-shared-disk-cluster-sles-configure.md)

--->

## <a name="next-steps"></a>다음 단계

- [장애 조치(failover) 클러스터 인스턴스 구성 - SQL Server on Linux](sql-server-linux-shared-disk-cluster-configure.md)

<!--Image references-->
