---
description: 차원, 계층 구조, 수준 함수 사용
title: 차원, 계층 및 수준 함수 사용 | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: afb7d324a2a4450a4df09ec3493954f0566a2cfc
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88341109"
---
# <a name="using-dimension-hierarchy-and-level-functions"></a>차원, 계층 구조, 수준 함수 사용


  차원, 계층 및 수준 함수는 Analysis Services에서 사용되는 다차원 구조를 탐색하는 데 유용합니다. 일반적으로 이 함수들은 차원, 계층 또는 수준의 멤버에 관한 정보를 가져오는 작업에 다른 함수와 함께 사용됩니다.  
  
 다음 예제에서는를 사용 하는 방법을 보여 줍니다 **. 차원**, **. 계층 구조**및 **입니다. 수준** 함수:  
  
 `WITH`  
  
 `MEMBER MEASURES.DIMENSIONNAME AS [Date].[Calendar].CURRENTMEMBER.DIMENSION.NAME`  
  
 `MEMBER MEASURES.HIERARCHYNAME AS [Date].[Calendar].CURRENTMEMBER.HIERARCHY.NAME`  
  
 `MEMBER MEASURES.LEVELNAME AS [Date].[Calendar].LEVEL.NAME`  
  
 `SELECT`  
  
 `{MEASURES.DIMENSIONNAME, MEASURES.HIERARCHYNAME, MEASURES.LEVELNAME}`  
  
 `ON Columns,`  
  
 `[Date].[Calendar].MEMBERS`  
  
 `ON Rows`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>참고 항목  
 [차원 &#40;MDX&#41;](../mdx/dimension-mdx.md)   
 [함수 &#40;MDX 구문&#41;](../mdx/functions-mdx-syntax.md)   
 [계층 &#40;MDX&#41;](../mdx/hierarchy-mdx.md)   
 [MDX&#41;수준 &#40;](../mdx/level-mdx.md)  
  
  
