---
description: '&lt;= (작거나 같음) (DMX)'
title: '&lt;= (작거나 같음) (DMX) | Microsoft Docs'
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 91b043711d9f81d54d98dc455c806eac60e9a33a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88491489"
---
# <a name="lt-less-than-or-equal-to-dmx"></a>&lt;= (작거나 같음) (DMX)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  하나의 DMX(Data Mining Extensions) 식의 값이 다른 DMX 식의 값보다 작거나 같은지 확인하는 비교 연산을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
DMX_Expression <= DMX_Expression  
```  
  
#### <a name="parameters"></a>매개 변수  
 *DMX_Expression*  
 유효한 DMX 식입니다.  
  
## <a name="return-value"></a>반환 값  
 두 매개 변수가 모두 Null이 아니고 첫 번째 매개 변수 값이 두 번째 매개 변수 값보다 작거나 같은 경우 부울 값에 TRUE가 포함됩니다. 두 매개 변수가 모두 Null이 아니고 첫 번째 매개 변수 값이 두 번째 매개 변수 값보다 클 경우 부울 값에 FALSE가 포함됩니다. 매개 변수 중 하나 또는 둘 모두가 Null 값으로 계산되면 부울 값에 Null 값이 포함됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [DMX&#41;&#40;비교 연산자 ](../dmx/operators-comparison.md)   
 [데이터 마이닝 확장 &#40;DMX&#41; 연산자 참조](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [&#40;DMX&#41;](../dmx/operators-dmx.md)  
  
  
