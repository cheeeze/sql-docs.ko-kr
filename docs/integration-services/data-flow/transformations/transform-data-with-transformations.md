---
description: 변환을 사용하여 데이터 변환
title: 변환을 사용하여 데이터 변환 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data flow [Integration Services], transformations
- transformations [Integration Services], about transformations
- transforming data [Integration Services]
ms.assetid: e1340b6f-ef75-4b14-af6f-823586eff0ed
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5189cda62a168db3cedff0d57666df7e15a0d65c
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92193176"
---
# <a name="transform-data-with-transformations"></a>변환을 사용하여 데이터 변환

[!INCLUDE[sqlserver-ssis](../../../includes/applies-to-version/sqlserver-ssis.md)]


  [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] 에는 원본, 변환 및 대상 등 3가지 유형의 데이터 흐름 구성 요소가 있습니다.  
  
 다음 다이어그램에서는 원본 하나, 변환 두 가지, 대상 하나를 포함하는 간단한 데이터 흐름을 보여 줍니다.  
  
 ![데이터 흐름](../../../integration-services/data-flow/media/mw-dts-08.gif "데이터 흐름")  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] 변환은 다음과 같은 기능을 제공합니다.  
  
-   행 집합을 분할, 복사 및 병합하고 조회 작업을 수행합니다.  
  
-   소문자를 대문자로 변경하는 것과 같은 변환을 적용하여 열 값을 업데이트하고 새 열을 만듭니다.  
  
-   데이터 정리, 텍스트 마이닝 및 데이터 마이닝 예측 쿼리 실행과 같은 비즈니스 인텔리전스 작업을 수행합니다.  
  
-   집계 또는 정렬된 값, 예제 데이터 또는 피벗되거나 피벗되지 않은 데이터로 구성되는 새 행 집합을 만듭니다.  
  
-   데이터 내보내기 및 가져오기, 감사 정보 제공, 느린 변경 차원 작업과 같은 태스크를 수행합니다.  
  
 자세한 내용은 [Integration Services Transformations](../../../integration-services/data-flow/transformations/integration-services-transformations.md)을 참조하세요.  
  
 사용자 지정 변환을 작성할 수도 있습니다. 자세한 내용은 [사용자 지정 데이터 흐름 구성 요소 개발](../../../integration-services/extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) 및 [특정 유형의 데이터 흐름 구성 요소 개발](../../../integration-services/extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)을 참조하세요.  
  
 데이터 흐름 디자이너에 변환을 추가한 다음 변환을 구성하기 전에 다른 변환 또는 데이터 흐름의 원본을 이 변환의 입력에 연결하여 데이터 흐름에 변환을 연결합니다. 두 데이터 흐름 구성 요소 간 연결선을 경로라고 합니다. 구성 요소 연결 및 경로 사용 방법은 [경로에 구성 요소 연결](../connect-components-in-a-data-flow.md)을 참조하세요.  
  
### <a name="to-add-a-transformation-to-a-data-flow"></a>데이터 흐름에 변환을 추가하려면  
  
-   [데이터 흐름에서 구성 요소 추가 또는 삭제](../../../integration-services/data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
### <a name="to-connect-a-transformation-to-a-data-flow"></a>데이터 흐름에서 변환을 연결하려면  
  
-   [데이터 흐름의 구성 요소 연결](../../../integration-services/data-flow/connect-components-in-a-data-flow.md)  
  
### <a name="to-set-the-properties-of-a-transformation"></a>변환의 속성을 설정하려면  
  
-   [데이터 흐름 구성 요소의 속성 설정](../../../integration-services/data-flow/set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a>관련 항목  
 [데이터 흐름 태스크](../../../integration-services/control-flow/data-flow-task.md)   
 [데이터 흐름](../../../integration-services/data-flow/data-flow.md)   
 [경로에 구성 요소 연결](../connect-components-in-a-data-flow.md)   
 [데이터 오류 처리](../../../integration-services/data-flow/error-handling-in-data.md)   
 [데이터 흐름](../../../integration-services/data-flow/data-flow.md)  
  
