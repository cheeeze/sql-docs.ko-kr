---
description: MDX 데이터 정의 - DROP SET
title: DROP SET 문 (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 5c4ca356847d75150aa098b331bdf0f8c8368bb6
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92195608"
---
# <a name="mdx-data-definition---drop-set"></a>MDX 데이터 정의 - DROP SET


  명명된 집합을 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
DROP [SESSION] SET   
   <Cube_Reference>.Set_Name   
               [,<Cube_Reference>.Set_Name ...n]  
  
<Cube_Reference> ::= {CURRENTCUBE | Cube_Name}  
  
```  
  
## <a name="arguments"></a>인수  
 *Cube_Name*  
 큐브의 이름을 지정하는 유효한 문자열 식입니다.  
  
 *Set_Name*  
 삭제할 명명된 집합의 이름을 지정하는 유효한 문자열 식입니다.  
  
## <a name="remarks"></a>설명  
 명명된 집합에 대한 자세한 내용은 [명명된 집합을 MDX로 작성&#40;MDX&#41;](/analysis-services/multidimensional-models/mdx/mdx-named-sets-building-named-sets)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Mdx 데이터 정의 문은 MDX를 &#40;&#41;](../mdx/mdx-data-definition-statements-mdx.md)  
  
