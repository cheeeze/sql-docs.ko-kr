---
description: sys.dm_xe_database_session_targets(Azure SQL Database)
title: sys.dm_xe_database_session_targets
titleSuffix: Azure SQL Database
ms.date: 06/10/2016
ms.service: sql-database
ms.prod_service: sql-database
ms.reviewer: ''
ms.topic: language-reference
ms.assetid: 7f353e2a-f8fc-4366-97e4-aa1c49eadaf4
author: markingmyname
ms.author: maghan
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.custom: seo-dt-2019
ms.openlocfilehash: 483fa1c826c4b495d609d1c893f5bb022ac6f943
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89546391"
---
# <a name="sysdm_xe_database_session_targets-azure-sql-database"></a>sys.dm_xe_database_session_targets(Azure SQL Database)
[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

  세션 작업에 대한 정보를 반환합니다.  
  
||  
|-|  
|**적용**대상: [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] V12 및 이후 버전|  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|event_session_address|**varbinary(8)**|이벤트 세션의 메모리 주소입니다. 에는 dm_xe_database_sessions와 다 대 일 관계가 있습니다. Null을 허용하지 않습니다.|  
|target_name|**nvarchar(60)**|세션 내에 있는 대상의 이름입니다. Null을 허용하지 않습니다.|  
|target_package_guid|**uniqueidentifier**|대상이 포함된 패키지의 GUID입니다. Null을 허용하지 않습니다.|  
|execution_count|**bigint**|세션에 대해 대상이 실행된 횟수입니다. Null을 허용하지 않습니다.|  
|execution_duration_ms|**bigint**|대상이 실행된 총 시간(밀리초)입니다. Null을 허용하지 않습니다.|  
|target_data|**nvarchar(max)**|이벤트 집계 정보와 같이 대상에서 유지 관리하는 데이터입니다. Null을 허용합니다.|  
  
## <a name="permissions"></a>사용 권한  
 VIEW DATABASE STATE 권한이 필요합니다.  
  
### <a name="relationship-cardinalities"></a>관계 카디널리티  
  
|시작|대상|관계|  
|----------|--------|------------------|  
|dm_xe_database_session_targets. event_session_address|dm_xe_database_sessions. 주소|다 대 일|  
  
  
