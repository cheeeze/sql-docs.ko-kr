---
description: catalog.rename_customized_logging_level
title: catalog.rename_customized_logging_level | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: b1a57d5e-3f03-4901-8b2b-bb8b371b595b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5b6b4770034771049d19e3a1eb3e8c43205aad46
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88430085"
---
# <a name="catalogrename_customized_logging_level"></a>catalog.rename_customized_logging_level 

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]

  기존 사용자 지정 로깅 수준의 이름을 바꿀 수 있습니다. 사용자 지정 로깅 수준에 대한 자세한 내용은 [Integration Services &#40;SSIS&#41; 로깅](../../integration-services/performance/integration-services-ssis-logging.md)을 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```sql  
catalog.rename_customized_logging_level [ @old_name = ] old_name  
    , [ @new_name = ] new_name  
```  
  
## <a name="arguments"></a>인수  
 [ @old_name = ] *old_name*  
 이름을 바꿀 기존 사용자 지정 로깅 수준의 이름입니다.  
  
 *old_name*은 **nvarchar(128)** 입니다.  
  
 [ @new_name = ] *new_name*  
 지정된 사용자 지정 로깅 수준의 새 이름입니다.  
  
 *new_name*은 **nvarchar(128)** 입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="return-codes"></a>반환 코드  
 0(성공)  
  
 저장 프로시저가 실패하면 오류를 반환합니다.  
  
## <a name="result-set"></a>결과 집합  
 None  
  
## <a name="permissions"></a>사용 권한  
 이 저장 프로시저를 실행하려면 다음 권한 중 하나가 필요합니다.  
  
-   **ssis_admin** 데이터베이스 역할의 멤버 자격  
  
-   **sysadmin** 서버 역할의 멤버 자격  
  
## <a name="errors-and-warnings"></a>오류 및 경고  
 다음 목록에서는 저장 프로시저 실패 조건을 설명합니다.  
  
-   사용자에게 필요한 권한이 없습니다.  
  
  
