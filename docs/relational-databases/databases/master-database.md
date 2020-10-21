---
description: master 데이터베이스
title: master 데이터베이스 | Microsoft 문서
ms.custom: ''
ms.date: 01/28/2019
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- master database [SQL Server], about
- master database [SQL Server]
ms.assetid: 660e909f-61eb-406b-bbce-8864dd629ba0
author: stevestein
ms.author: sstein
ms.openlocfilehash: bdc1669274577d7d75f0d50ab2f5b9ec736799cc
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92194376"
---
# <a name="master-database"></a>master 데이터베이스

[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sql-asdb.md)]
  **master** 데이터베이스는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 시스템에 대한 모든 시스템 수준 정보를 기록합니다. 이 정보에는 로그온 계정, 엔드포인트, 연결된 서버 및 시스템 구성 설정 등 인스턴스 차원의 메타데이터가 포함됩니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서는 시스템 개체가 **master** 데이터베이스에 저장되지 않고 [리소스 데이터베이스](../../relational-databases/databases/resource-database.md)에 저장됩니다. **master** 는 다른 모든 데이터베이스의 존재 여부와 해당 데이터베이스 파일의 위치를 기록하고 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에 대한 초기화 정보를 기록하는 데이터베이스이기도 합니다. 따라서 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] master **데이터베이스를 사용할 수 없는 경우에는** 를 시작할 수 없습니다.  

> [!IMPORTANT]
> Azure SQL Database 단일 데이터베이스와 탄력적 풀의 경우 master 데이터베이스 및 tempdb 데이터베이스만 적용됩니다. 자세한 내용은 [Azure SQL Database 서버란?](/azure/sql-database/sql-database-servers#what-is-an-azure-sql-database-server)을 참조하세요. Azure SQL Database의 컨텍스트에서 tempdb의 설명은 [Azure SQL Database의 tempdb 데이터베이스](tempdb-database.md#tempdb-database-in-sql-database)를 참조하세요. Azure SQL Managed Instance의 경우 모든 시스템 데이터베이스가 적용됩니다. Azure SQL Database Managed Instance에 대한 자세한 내용은 [Managed Instance란?](/azure/sql-database/sql-database-managed-instance)을 참조하세요.
  
## <a name="physical-properties-of-master"></a>master의 물리적 속성

다음 표에서는 SQL Server 및 Azure SQL Managed Instance의 **master** 데이터와 로그 파일의 초기 구성 값을 나열합니다. 이러한 파일의 크기는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]버전에 따라 조금씩 다를 수 있습니다.  
  
|파일|논리적 이름|물리적 이름|파일 증가|  
|----------|------------------|-------------------|-----------------|  
|주 데이터|master|master.mdf|디스크가 꽉 찰 때까지 10%씩 자동 증가|  
|로그|mastlog|mastlog.ldf|최대 2TB까지 10%씩 자동 증가|  
  
**master** 데이터 및 로그 파일의 이동 방법은 [시스템 데이터베이스 이동](../../relational-databases/databases/move-system-databases.md)을 참조하세요.  

> [!IMPORTANT]
> Azure SQL Database 서버의 경우 사용자는 **master** 데이터베이스의 크기를 제어할 수 없습니다.
  
### <a name="database-options"></a>데이터베이스 옵션

다음 표에서는 SQL Server 및 Azure SQL Managed Instance에 대한 **master** 데이터베이스의 각 데이터베이스 옵션에 대한 기본값과 수정 가능 여부를 나열합니다. 이러한 옵션의 현재 설정을 보려면 [sys.databases](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md) 카탈로그 뷰를 사용하세요.  
  
> [!IMPORTANT]
> Azure SQL Database 단일 데이터베이스 및 탄력적 풀의 경우 사용자는 다음 데이터베이스 옵션을 제어할 수 없습니다.

|데이터베이스 옵션|기본값|수정 가능|  
|---------------------|-------------------|---------------------|  
|ALLOW_SNAPSHOT_ISOLATION|켜기|예|  
|ANSI_NULL_DEFAULT|OFF|예|  
|ANSI_NULLS|OFF|예|  
|ANSI_PADDING|OFF|예|  
|ANSI_WARNINGS|OFF|예|  
|ARITHABORT|OFF|예|  
|AUTO_CLOSE|OFF|예|  
|AUTO_CREATE_STATISTICS|켜기|예|  
|AUTO_SHRINK|OFF|예|  
|AUTO_UPDATE_STATISTICS|켜기|예|  
|AUTO_UPDATE_STATISTICS_ASYNC|OFF|예|  
|CHANGE_TRACKING|OFF|예|  
|CONCAT_NULL_YIELDS_NULL|OFF|예|  
|CURSOR_CLOSE_ON_COMMIT|OFF|예|  
|CURSOR_DEFAULT|GLOBAL|예|  
|데이터베이스 가용성 옵션|ONLINE<br /><br /> MULTI_USER<br /><br /> READ_WRITE|예<br /><br /> 예<br /><br /> 예|  
|DATE_CORRELATION_OPTIMIZATION|OFF|예|  
|DB_CHAINING|켜기|예|  
|ENCRYPTION|OFF|예|  
|MIXED_PAGE_ALLOCATION|켜기|예|  
|NUMERIC_ROUNDABORT|OFF|예|  
|PAGE_VERIFY|CHECKSUM|yes|  
|PARAMETERIZATION|SIMPLE|예|  
|QUOTED_IDENTIFIER|OFF|예|  
|READ_COMMITTED_SNAPSHOT|OFF|예|  
|RECOVERY|SIMPLE|yes|  
|RECURSIVE_TRIGGERS|OFF|예|  
|Service Broker 옵션|DISABLE_BROKER|예|  
|TRUSTWORTHY|OFF|yes|  
  
이러한 데이터베이스 옵션에 대한 자세한 내용은 [ALTER DATABASE&#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md)를 참조하세요.  
  
## <a name="restrictions"></a>제한  
**master** 데이터베이스에서는 다음 작업을 수행할 수 없습니다.  
  
- 파일이나 파일 그룹 추가  
- 백업, master 데이터베이스에서는 전체 데이터베이스 백업만 수행할 수 있습니다.
- 데이터 정렬 변경. 기본 데이터 정렬은 서버 데이터 정렬입니다.  
- 데이터베이스 소유자 변경. **master** 는 **sa**가 소유합니다.  
- 전체 텍스트 카탈로그 또는 전체 텍스트 인덱스 만들기  
- 데이터베이스의 시스템 테이블에 트리거 만들기  
- 데이터베이스 삭제  
- 데이터베이스에서 **guest** 사용자 삭제  
- 변경 데이터 캡처 설정  
- 데이터베이스 미러링 참여  
- 주 파일 그룹, 주 데이터 파일 또는 로그 파일 제거  
- 데이터베이스 또는 주 파일 그룹 이름 바꾸기  
- 데이터베이스를 OFFLINE으로 설정  
- 데이터베이스나 주 파일 그룹을 READ_ONLY로 설정  
  
## <a name="recommendations"></a>권장 사항  
다음은 **master** 데이터베이스로 작업을 수행할 때 고려해야 할 사항입니다.  
  
- 언제든지 사용할 수 있도록 **master** 데이터베이스의 최신 백업을 보관합니다.  
- 다음 작업을 수행한 후에는 가능한 빨리 **master** 데이터베이스를 백업합니다.  
  
  - 데이터베이스 만들기, 수정 또는 삭제  
  - 서버 또는 데이터베이스 구성 값 변경  
  - 로그온 계정 수정 또는 추가  
  
- **master**에는 사용자 개체를 만들지 마세요. 사용자 개체를 만든 경우에는 **master** 를 더 자주 백업해야 합니다.  
- **master** 데이터베이스의 TRUSTWORTHY 옵션을 ON으로 설정하지 마세요.  
  
## <a name="what-to-do-if-master-becomes-unusable"></a>master를 사용할 수 없게 된 경우 수행할 작업  
 **master** 를 사용할 수 없게 된 경우 다음 방법 중 하나로 데이터베이스를 사용 가능한 상태로 되돌릴 수 있습니다.  
  
- 현재 데이터베이스 백업에서 **master** 를 복원합니다.  
  
  서버 인스턴스를 시작할 수 있으면 전체 데이터베이스 백업에서 **master** 를 복원할 수 있습니다. 자세한 내용은 [master 데이터베이스 복원&#40;Transact-SQL&#41;](../../relational-databases/backup-restore/restore-the-master-database-transact-sql.md)을 참조하세요.  
  
- **master** 를 완전히 다시 작성합니다.  
  
  **master** 에 발생한 심각한 손상으로 인해 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]를 시작할 수 없는 경우에는 **master**를 다시 작성해야 합니다. 자세한 내용은 [시스템 데이터베이스 다시 작성](../../relational-databases/databases/rebuild-system-databases.md)을 참조하세요.  
  
  > [!IMPORTANT]  
  >  **master** 를 다시 작성하면 모든 시스템 데이터베이스가 다시 작성됩니다.  
  
## <a name="related-content"></a>관련 내용  
- [시스템 데이터베이스 다시 작성](../../relational-databases/databases/rebuild-system-databases.md)  
- [시스템 데이터베이스](../../relational-databases/databases/system-databases.md)  
- [sys.databases&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)  
- [sys.master_files&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-master-files-transact-sql.md)  
- [데이터베이스 파일 이동](../../relational-databases/databases/move-database-files.md)