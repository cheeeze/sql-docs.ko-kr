---
description: OR(DMX)
title: OR (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 86a9aede9f1b9b12f465fa52b0343cf22c04b295
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88395439"
---
# <a name="or-dmx"></a>OR(DMX)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  두 숫자 식에서 논리 분리를 수행하는 논리 연산자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
Expression1 OR Expression2  
```  
  
#### <a name="parameters"></a>매개 변수  
 *Expression1*  
 숫자 값을 반환하는 유효한 DMX(Data Mining Extensions) 식입니다.  
  
 *Expression2*  
 숫자 값을 반환하는 유효한 DMX 식입니다.  
  
## <a name="return-value"></a>반환 값  
 인수 중 하나 또는 둘 모두가 TRUE로 계산되면 TRUE를 반환하고 그렇지 않으면 FALSE를 반환하는 부울 값입니다.  
  
## <a name="remarks"></a>설명  
 이 두 인수는 연산자가 논리 분리를 수행하기 전에 부울 값(0은 FALSE, 0이 아닌 경우 TRUE)으로 처리됩니다. 인수 중 하나 또는 둘 모두가 TRUE로 계산되는 경우 이 연산자는 TRUE를 반환합니다. *Expression1* 가 true로 평가 되 고 *식 2* 가 FALSE로 계산 되는 경우 연산자는 true를 반환 합니다.  
  
 다음 표에서는 논리 분리가 수행되는 방법을 설명합니다.  
  
|Expression1의 값|Expression2의 값|반환 값|  
|-----------------------|-----------------------|---------------------|  
|TRUE|TRUE|TRUE|  
|TRUE|FALSE|true|  
|FALSE|TRUE|TRUE|  
|FALSE|FALSE|FALSE|  
  
## <a name="see-also"></a>참고 항목  
 [데이터 마이닝 확장 &#40;DMX&#41; 연산자 참조](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [논리 연산자 &#40;DMX&#41;](../dmx/operators-logical.md)   
 [&#40;DMX&#41;](../dmx/operators-dmx.md)  
  
  
