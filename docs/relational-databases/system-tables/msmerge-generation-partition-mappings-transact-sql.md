---
title: MSmerge_generation_partition_mappings (T-sql)
description: 병합 게시의 파티션에 대 한 변경 내용을 추적 하는 데 사용 되는 MSmerge_generation_partition_mappings 저장 프로시저에 대해 설명 합니다.
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSmerge_generation_partition_mappings_TSQL
- MSmerge_generation_partition_mappings
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_generation_partition_mappings system table
ms.assetid: 443a4024-ce48-4772-9ee5-95bd6fb6476b
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 4ae8e89600a76da91ccf06d0a561319af9bec3f1
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89544518"
---
# <a name="msmerge_generation_partition_mappings-transact-sql"></a>MSmerge_generation_partition_mappings(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  **MSmerge_generation_partition_mappings** 테이블은 병합 게시의 파티션에 대 한 변경 내용을 추적 하는 데 사용 됩니다. 이 테이블은 게시 데이터베이스와 구독 데이터베이스에 저장됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|**publication_number**|**smallint**|병합 게시를 식별합니다.|  
|**작성**|**bigint**|생성 값입니다.|  
|**partition_id**|**int**|파티션을 식별합니다.|  
|**changecount**|**int**|파티션이 변경된 횟수입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;복제 테이블 ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
