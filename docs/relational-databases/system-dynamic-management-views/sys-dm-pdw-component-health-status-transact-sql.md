---
description: sys.dm_pdw_component_health_status (Transact-sql)
title: sys.dm_pdw_component_health_status (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: 68cc3f7a-693c-4d5d-a76b-455352af8d7f
author: markingmyname
ms.author: maghan
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 25c3a68f023397b08d61ba58acb2a829c218cffa
ms.sourcegitcommit: 22dacedeb6e8721e7cdb6279a946d4002cfb5da3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92035415"
---
# <a name="sysdm_pdw_component_health_status-transact-sql"></a>sys.dm_pdw_component_health_status (Transact-sql)
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  어플라이언스 구성 요소의 현재 상태에 대 한 정보를 저장 합니다.  
  
|열 이름|데이터 형식|Description|범위|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**||NOT NULL|  
|component_id|Int|구성 요소의 ID입니다. [Sys.pdw_health_components &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-components-transact-sql.md)를 참조 하세요.<br /><br /> 이 보기의 키를 pdw_node_id, component_id, property_id 및 component_instance_id 구성 합니다.|NOT NULL|  
|property_id|**int**|속성의 ID입니다. [Sys.pdw_health_component_properties &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-health-component-properties-transact-sql.md)를 참조 하세요.|NOT NULL|  
|component_instance_id|**nvarchar(255)**|구성 요소의 인스턴스를 식별 합니다. 예를 들어 CPU의 인스턴스는 component_instance_id = ' CPU1 '로 식별할 수 있습니다.<br /><br /> 이 보기의 키를 pdw_node_id, component_id, property_id 및 component_instance_id 구성 합니다.|NOT NULL|  
|property_value|**nvarchar(255)**|현재 속성 값입니다.|NULL|  
|update_time|**datetime**|메트릭이 마지막으로 업데이트 된 시간입니다.|NOT NULL|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;Azure Synapse 분석 및 병렬 데이터 웨어하우스 동적 관리 뷰 ](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
