---
description: SQL Server 대상 사용자 지정 속성
title: SQL Server 대상 사용자 지정 속성 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b736aa6d-c154-44a0-be08-f25733fca1d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de7b5eb166ab200a0a5217cb4c95eed7216520d5
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92194781"
---
# <a name="sql-server-destination-custom-properties"></a>SQL Server 대상 사용자 지정 속성

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 대상에는 사용자 지정 속성과 모든 데이터 흐름 구성 요소에 공통된 속성이 모두 있습니다.  
  
 다음 표에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 대상의 사용자 지정 속성을 설명합니다. 모든 속성은 읽기/쓰기가 가능합니다.  
  
|속성 이름|데이터 형식|Description|  
|-------------------|---------------|-----------------|  
|AlwaysUseDefaultCodePage|부울|DefaultCodePage 속성 값을 사용하도록 합니다. 이 속성의 기본값은 **False**입니다.|  
|BulkInsertCheckConstraints|부울|대량 삽입 시 제약 조건을 검사하는지 여부를 지정하는 값입니다. 이 속성의 기본값은 **True**입니다.|  
|BulkInsertFireTriggers|부울|대량 삽입 시 테이블에서 트리거를 실행하는지 여부를 지정하는 값입니다. 이 속성의 기본값은 **False**입니다.|  
|BulkInsertFirstRow|정수|삽입할 첫 번째 행을 지정하는 값입니다. 이 속성의 기본값은 값이 할당되지 않음을 나타내는 **-1**입니다.|  
|BulkInsertKeepIdentity|부울|ID 열에 값을 삽입할 수 있는지 여부를 지정하는 값입니다. 이 속성의 기본값은 **False**입니다.|  
|BulkInsertKeepNulls|부울|대량 삽입 시 Null 값을 유지하는지 여부를 지정하는 값입니다. 이 속성의 기본값은 **False**입니다.|  
|BulkInsertLastRow|정수|삽입할 마지막 행을 지정하는 값입니다. 이 속성의 기본값은 값이 할당되지 않음을 나타내는 **-1**입니다.|  
|BulkInsertMaxErrors|정수|대량 삽입이 중지되기 전에 발생할 수 있는 오류 수를 지정하는 값입니다. 이 속성의 기본값은 값이 할당되지 않음을 나타내는 **-1**입니다.|  
|BulkInsertOrder|String|정렬 열의 이름입니다. 각 열을 오름차순이나 내림차순으로 정렬할 수 있습니다. 여러 정렬 열을 사용하는 경우 열 이름을 쉼표로 구분합니다.|  
|BulkInsertTableName|String|데이터를 복사할 데이터베이스의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 테이블 또는 뷰입니다.|  
|BulkInsertTablock|부울|대량 삽입 작업을 수행하는 동안 테이블을 잠글지 여부를 지정하는 값입니다. 이 속성의 기본값은 **True**입니다.|  
|DefaultCodePage|정수|데이터 원본에서 코드 페이지 정보를 사용할 수 없을 경우 사용할 코드 페이지입니다.|  
|MaxInsertCommitSize|정수|일괄 처리 시 삽입할 최대 행 수를 지정하는 값입니다. 값이 0인 경우 모든 행이 단일 일괄 처리로 삽입됩니다.|  
|제한 시간|정수|삽입에 사용할 데이터가 없는 경우 종료 전에 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 대상에서 대기하는 시간(초)을 지정하는 값입니다. 값 0은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 대상에 제한 시간이 없음을 의미합니다. 이 속성의 기본값은 30입니다.|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 대상의 입력 및 입력 열에는 사용자 지정 속성이 없습니다.  
  
 자세한 내용은 [SQL Server Destination](../../integration-services/data-flow/sql-server-destination.md)을 참조하세요.  
  
## <a name="see-also"></a>관련 항목  
 [Common Properties](./set-the-properties-of-a-data-flow-component.md)  
  
