---
description: sys.event_notification_event_types(Transact-SQL)
title: sys. event_notification_event_types (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.event_notification_event_types_TSQL
- sys.event_notification_event_types
- event_notification_event_types_TSQL
- event_notification_event_types
dev_langs:
- TSQL
helpviewer_keywords:
- sys.event_notification_event_types catalog view
ms.assetid: 73dae456-7044-4b00-b0bd-990ef810b356
author: markingmyname
ms.author: maghan
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 0cbd26c772434396e7648012cd035c71eda73cdf
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89548802"
---
# <a name="sysevent_notification_event_types-transact-sql"></a>sys.event_notification_event_types(Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  이벤트 알림이 발생할 수 있는 각 이벤트 또는 이벤트 그룹에 대해 한 개의 행을 반환합니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**type**|**int**|이벤트 알림을 실행하는 이벤트 또는 이벤트 그룹의 유형입니다.|  
|**type_name**|**nvarchar(128)**|이벤트 또는 이벤트 그룹의 이름으로 [CREATE EVENT NOTIFICATION](../../t-sql/statements/create-event-notification-transact-sql.md) 문의 FOR 절에 지정할 수 있습니다.|  
|**parent_type**|**int**|이벤트 또는 이벤트 그룹의 부모인 이벤트 그룹의 유형입니다.|  
  
## <a name="permissions"></a>사용 권한  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 자세한 내용은 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [개체 카탈로그 뷰 &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [카탈로그 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
