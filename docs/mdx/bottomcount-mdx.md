---
description: BottomCount(MDX)
title: BottomCount (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: e331a84efe36cef11951afac3f304957e4ffcb00
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88494982"
---
# <a name="bottomcount-mdx"></a>BottomCount(MDX)


  집합을 오름차순으로 정렬하고 지정된 집합에서 가장 낮은 값을 갖는 튜플을 지정된 수만큼 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
BottomCount(Set_Expression, Count [,Numeric_Expression])  
```  
  
## <a name="arguments"></a>인수  
 *Set_Expression*  
 집합을 반환하는 유효한 MDX 식입니다.  
  
 *Count*  
 반환할 튜플 수를 지정하는 유효한 숫자 식입니다.  
  
 *Numeric_Expression*  
 숫자를 반환하는 셀 좌표의 유효한 숫자 식으로서, 일반적으로 MDX 식입니다.  
  
## <a name="remarks"></a>설명  
 숫자 식이 지정된 경우 이 함수는 지정된 집합에 대해 지정된 숫자 식을 계산한 값에 따라 해당 집합의 튜플을 오름차순으로 정렬합니다. 그런 다음 **BottomCount** 함수는 가장 낮은 값을 갖는 지정 된 수의 튜플을 반환 합니다.  
  
> [!IMPORTANT]  
>  [TopCount](../mdx/topcount-mdx.md) 함수와 마찬가지로 **BottomCount** 함수는 항상 계층 구조를 중단 합니다.  
  
 숫자 식이 지정 되지 않은 경우이 함수는 멤버 집합을 정렬 하지 않고 일반적인 순서로 반환 합니다 .이 함수는 [Tail (MDX)](../mdx/tail-mdx.md) 함수 처럼 동작 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 하위 다섯 개의 Product SubCategory 판매량에 대한 연도별 Reseller Order Quantity 측정값을 Reseller Sales Amount 측정값을 기준으로 정렬하여 반환합니다.  
  
```  
SELECT BottomCount([Product].[Product Categories].[Subcategory].Members  
   , 10  
   , [Measures].[Reseller Sales Amount]) ON 0,  
   [Date].[Calendar].[Calendar Year].Members ON 1  
  
FROM  
    [Adventure Works]  
WHERE  
    [Measures].[Reseller Order Quantity]  
```  
  
## <a name="see-also"></a>참고 항목  
 [MDX 함수 참조&#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
