---
description: 데이터베이스를 데이터베이스 스냅샷으로 되돌리기
title: 데이터베이스를 데이터베이스 스냅샷으로 되돌리기 | Microsoft 문서
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], reverting to
- reverting databases
ms.assetid: 8f74dd31-c9ca-4537-8760-0c7648f0787d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 21b00ef447dd9312fc0ad3b4bb41cc414f91ff0f
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92196709"
---
# <a name="revert-a-database-to-a-database-snapshot"></a>데이터베이스를 데이터베이스 스냅샷으로 되돌리기
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  온라인 데이터베이스의 데이터가 손상되면 일부 경우 데이터베이스를 손상 발생 이전의 데이터베이스 스냅샷으로 되돌리는 작업이 백업에서 온라인 데이터베이스를 복원하는 방법에 대한 대체 방법이 될 수 있습니다. 예를 들어 데이터베이스 되돌리기 작업은 테이블 삭제와 같은 최근의 심각한 사용자 오류 발생 전의 상황으로 돌아가는 데 유용할 수 있습니다. 그러나 스냅샷을 만든 후의 모든 변경 내용은 손실됩니다.  
  
-   **시작하기 전 주의 사항:**  
  
     [제한 사항](#Restrictions)  
  
     [필수 구성 요소](#Prerequisites)  
  
     [보안](#Security)  
  
-   **데이터베이스를 데이터베이스 스냅샷으로 되돌리려면:**  [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> 시작하기 전에  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> 제한 사항  
 다음과 같은 경우에는 되돌리기가 지원되지 않습니다.  
  
-   데이터베이스에 대한 여러 스냅샷이 있습니다. 되돌리기의 경우 되돌리려는 데이터베이스에 대한 하나의 스냅샷만 있어야 합니다.  
  
-   데이터베이스에 읽기 전용 또는 압축 파일 그룹이 있습니다.  
  
-   스냅샷이 만들어질 때 온라인 상태였던 파일이 이제 오프라인 상태입니다.  
  
 데이터베이스를 되돌리기 전에 다음 제한 사항을 고려합니다.  
  
-   되돌리기는 미디어 복구용으로 사용할 수 없습니다. 데이터베이스 스냅샷은 데이터베이스 파일의 불완전한 복사본이므로 데이터베이스나 데이터베이스 스냅샷이 손상된 경우 스냅샷에서 되돌릴 수 없는 경우가 많습니다. 가능하다고 해도 손상된 경우에는 되돌리기를 수행해도 문제가 해결되지 않습니다. 따라서 데이터베이스를 보호하려면 정기적으로 백업하고 복원 계획을 테스트해야 합니다. 자세한 내용은 [SQL Server Database 백업 및 복원](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)을 참조하세요.  
  
    > [!NOTE]  
    >  데이터베이스 스냅샷을 만든 시점까지 원본 데이터베이스를 복원해야 하는 경우 전체 복구 모델을 사용하고 이 작업을 수행할 수 있는 백업 정책을 구현합니다.  
  
-   원래의 원본 데이터베이스를 되돌린 데이터베이스로 덮어쓰기 때문에 스냅샷을 만든 후 데이터베이스에 대해 수행된 모든 업데이트는 손실됩니다.  
  
-   또한 되돌리기 작업으로 오래된 로그 파일이 덮어 쓰이고 로그가 다시 생성됩니다. 따라서 되돌린 데이터베이스를 사용자 오류 발생 지점으로 롤포워드할 수 없습니다. 그러므로 데이터베이스를 되돌리기 전에 로그를 백업하는 것이 좋습니다.  
  
    > [!NOTE]  
    >  원본 로그를 복원하여 데이터베이스를 롤포워드할 수 없어도 원본 로그 파일의 내용은 손실된 데이터를 다시 구성할 때 유용할 수 있습니다.  
  
-   되돌리기로 인해 로그 백업 체인이 끊어집니다. 따라서 되돌려진 데이터베이스의 로그를 백업하기 전에 먼저 전체 데이터베이스 또는 파일을 백업해야 합니다. 전체 데이터베이스를 백업하는 것이 좋습니다.  
  
-   되돌리기 작업 동안 스냅샷과 원본 데이터베이스를 사용할 수 없습니다. 원본 데이터베이스와 스냅샷은 모두 "복원 중"으로 표시됩니다. 되돌리기 작업 중 오류가 발생하면 데이터베이스가 다시 시작될 때 되돌리기를 완료하려고 합니다.  
  
-   되돌려진 데이터베이스의 메타데이터는 스냅샷 시점의 메타데이터와 동일합니다.  
  
-   되돌리면 전체 텍스트 카탈로그가 모두 삭제됩니다.  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> 필수 조건  
 원본 데이터베이스 및 데이터베이스 스냅샷은 다음 사전 요구 사항을 충족해야 합니다.  
  
-   데이터베이스가 손상되지 않았어야 합니다.  
  
    > [!NOTE]  
    >  데이터베이스가 손상된 경우 백업에서 해당 데이터베이스를 복원해야 합니다. 자세한 내용은 [전체 데이터베이스 복원&#40;단순 복구 모델&#41;](../../relational-databases/backup-restore/complete-database-restores-simple-recovery-model.md) 또는 [전체 데이터베이스 복원&#40;전체 복구 모델&#41;](../../relational-databases/backup-restore/complete-database-restores-full-recovery-model.md)을 참조하세요.  
  
-   오류가 발생하기 전에 만든 최근 스냅샷을 식별합니다. 자세한 내용은 [View a Database Snapshot &#40;SQL Server&#41;](../../relational-databases/databases/view-a-database-snapshot-sql-server.md).  
  
-   데이터베이스에 현재 있는 다른 모든 스냅샷을 삭제합니다. 자세한 내용은 [Drop a Database Snapshot &#40;Transact-SQL&#41;](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md).  
  
###  <a name="security"></a><a name="Security"></a> 보안  
  
####  <a name="permissions"></a><a name="Permissions"></a> 권한  
 원본 데이터베이스에 대한 RESTORE DATABASE 권한을 가진 사용자는 해당 데이터베이스를 데이터베이스 스냅샷을 만들었을 때의 상태로 되돌릴 수 있습니다.  
  
##  <a name="how-to-revert-a-database-to-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> 데이터베이스를 데이터베이스 스냅샷으로 되돌리는 방법(Transact-SQL 사용)  
 **데이터베이스를 데이터베이스 스냅샷으로 되돌리려면**  
  
> [!NOTE]  
>  이 프로시저의 예는 이 섹션의 뒷부분에 나오는 [예제(Transact-SQL)](#TsqlExample)을 참조하세요.  
  
1.  데이터베이스를 되돌릴 데이터베이스 스냅샷을 식별합니다. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]에서 데이터베이스의 스냅샷을 확인할 수 있습니다([데이터베이스 스냅샷 보기&#40;SQL Server&#41;](../../relational-databases/databases/view-a-database-snapshot-sql-server.md) 참조). 또한 **sys.databases&#40;Transact-SQL&#41;** 카탈로그 뷰의 [sys.databases&amp;#40;Transact-SQL&amp;#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md) 열에서 뷰의 원본 데이터베이스를 식별할 수 있습니다.  
  
2.  다른 모든 데이터베이스 스냅샷을 삭제합니다.  
  
     스냅샷 삭제 방법은 [Drop a Database Snapshot &#40;Transact-SQL&#41;](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md). 되돌리기 전에 데이터베이스에서 전체 복구 모델을 사용하는 경우 로그를 백업해야 합니다. 자세한 내용은 [트랜잭션 로그 백업&#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-a-transaction-log-sql-server.md) 또는 [데이터베이스가 손상된 경우 트랜잭션 로그 백업&#40;SQL Server&#41;](../../relational-databases/backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)을 참조하세요.  
  
3.  되돌리기 작업을 수행합니다.  
  
     되돌리기 작업을 수행하려면 원본 데이터베이스에 대해 RESTORE DATABASE 권한이 필요합니다. 데이터베이스를 되돌리려면 다음과 같은 Transact-SQL 문을 사용합니다.  
  
     RESTORE DATABASE *database_name* FROM DATABASE_SNAPSHOT **=**_database_snapshot_name_  
  
     여기서 *database_name* 은 원본 데이터베이스이고 *database_snapshot_name* 은 데이터베이스를 되돌리려는 스냅샷의 이름입니다. 이 문에서 백업 디바이스가 아닌 스냅샷 이름을 지정해야 합니다.  
  
     자세한 내용은 [RESTORE&#40;Transact-SQL&#41;](../../t-sql/statements/restore-statements-transact-sql.md)를 통해 복원할 수 없습니다.  
  
    > [!NOTE]  
    >  되돌리기 작업 동안 스냅샷과 원본 데이터베이스를 모두 사용할 수 없습니다. 원본 데이터베이스와 스냅샷이 모두 "복원 중"으로 표시됩니다. 되돌리기 작업 중에 오류가 발생하면 데이터베이스가 다시 시작될 때 되돌리기를 완료하려고 시도합니다.  
  
4.  데이터베이스 스냅샷을 만든 후 데이터베이스 소유자가 변경된 경우 되돌린 데이터베이스의 데이터베이스 소유자를 업데이트할 수 있습니다.  
  
    > [!NOTE]  
    >  되돌린 데이터베이스는 데이터베이스 스냅샷의 사용 권한과 구성(데이터베이스 소유자, 복구 모델 등)을 유지합니다.  
  
5.  데이터베이스를 시작합니다.  
  
6.  필요에 따라, 특히 전체 또는 대량 로그 복구 모델을 사용하는 경우 되돌린 데이터베이스를 백업합니다. 데이터베이스를 백업하려면 [전체 데이터베이스 백업 만들기&#40;SQL Server&#41;](../../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md)를 참조하세요.  

###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> 예(Transact-SQL)  
 이 섹션에는 데이터베이스를 데이터베이스 스냅샷으로 되돌리는 다음 예가 포함되어 있습니다.  
  
-   A. [AdventureWorks 데이터베이스에 대한 스냅샷 되돌리기](#Reverting_AW)  
  
-   B. [Sales 데이터베이스에 대한 스냅샷 되돌리기](#Reverting_Sales)  
  
####  <a name="a-reverting-a-snapshot-on-the-adventureworks-database"></a><a name="Reverting_AW"></a> 1. AdventureWorks 데이터베이스에 대한 스냅샷 되돌리기  
 이 예에서는 현재 하나의 스냅샷만 [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 데이터베이스에 있는 것으로 가정합니다. 여기서 데이터베이스가 되돌려지는 스냅샷을 만드는 예는 [Create a Database Snapshot &#40;Transact-SQL&#41;](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md).  
  
```  
USE master;  
-- Reverting AdventureWorks to AdventureWorks_dbss1800  
RESTORE DATABASE AdventureWorks from   
DATABASE_SNAPSHOT = 'AdventureWorks_dbss1800';  
GO  
```  
  
####  <a name="b-reverting-a-snapshot-on-the-sales-database"></a><a name="Reverting_Sales"></a> 2. Sales 데이터베이스에 대한 스냅샷 되돌리기  
 이 예에서는 **Sales** 데이터베이스에 현재 두 개의 스냅샷인 **sales_snapshot0600** 및 **sales_snapshot1200**이 있다고 가정합니다. 스냅샷 중 오래된 항목을 삭제하고 데이터베이스를 가장 최근의 스냅샷으로 되돌립니다.  
  
 이 예에 사용되는 예제 데이터베이스와 스냅샷을 만드는 코드는 다음을 참조하세요.  
  
-   **Sales** 데이터베이스와 **sales_snapshot0600** 스냅샷의 경우 [CREATE DATABASE&#40;SQL Server Transact-SQL&#41;](../../t-sql/statements/create-database-transact-sql.md)의 "파일 그룹이 포함된 데이터베이스 만들기" 및 "데이터베이스 스냅샷 만들기"를 참조하세요.  
  
-   **sales_snapshot1200** 스냅샷의 경우 [Create a Database Snapshot &#40;Transact-SQL&#41;](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md).  
  
```  
--Test to see if sales_snapshot0600 exists and if it   
-- does, delete it.  
IF EXISTS (SELECT dbid FROM sys.databases  
    WHERE NAME='sales_snapshot0600')  
    DROP DATABASE SalesSnapshot0600;  
GO  
-- Reverting Sales to sales_snapshot1200  
USE master;  
RESTORE DATABASE Sales FROM DATABASE_SNAPSHOT = 'sales_snapshot1200';  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> 관련 작업  
  
-   [데이터베이스 스냅샷 만들기&#40;Transact-SQL&#41;](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [데이터베이스 스냅샷 보기&#40;SQL Server&#41;](../../relational-databases/databases/view-a-database-snapshot-sql-server.md)  
  
-   [데이터베이스 스냅샷 삭제&#40;Transact-SQL&#41;](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a>참고 항목  
 [데이터베이스 스냅샷&#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md)   
 [RESTORE&#40;Transact-SQL&#41;](../../t-sql/statements/restore-statements-transact-sql.md)   
 [sys.databases&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)   
 [데이터베이스 미러링 및 데이터베이스 스냅샷&#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-and-database-snapshots-sql-server.md)  
  
