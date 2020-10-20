---
title: 비즈니스 규칙 동작
description: MDS(Master Data Services) 비즈니스 규칙은 작업을 발생 시킵니다. 기본값 작업, 값 변경 작업, 유효성 검사 동작 및 외부 동작에 대해 알아봅니다.
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cdc4daca-3dff-46d8-b7f0-57f7826dd61a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 18f95be4c33c1d9695a16f7183407e177bc02925
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92193675"
---
# <a name="business-rule-actions-master-data-services"></a>비즈니스 규칙 동작(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]에서 비즈니스 규칙 동작은 비즈니스 규칙 조건 평가의 결과입니다. 조건이 True이면 동작이 시작됩니다.  
  
> [!NOTE]  
>  값 변경 및 기본값 동작의 경우 생성된 값이 특성의 최대 길이를 초과하면 생성된 값은 잘립니다.  
  
## <a name="default-value-actions"></a>기본값 동작  
 **기본값** 동작은 지정한 특성의 기본값을 설정합니다. 사용 권한이 있는 사용자는 이러한 기본값을 변경할 수 있습니다.  
  
|값 이름|Description|  
|----------------|-----------------|  
|**기본값**|선택한 특성이 **기본적으로** 특정 특성 또는 특정 특성 값으로 설정되거나, 비어 있습니다.<br /><br /> 이 동작은 텍스트, 숫자, 날짜 및 링크 값에 유효합니다.|  
|**생성되는 값을 기본값으로 설정**|선택한 특성은 **생성되는 값을 기본값으로 설정** 합니다. 이 값은 입력하는 시작 값과 증분 값에 따라 결정됩니다.<br /><br /> 이 동작은 텍스트 및 숫자 값에 유효합니다.|  
|**연결된 값을 기본값으로 설정**|선택한 특성은 여러 지정 특성에 따라 결정되는 **연결된 값을 기본값으로 설정** 합니다.<br /><br /> 이 동작은 텍스트 및 링크 값에 유효합니다.|  
  
## <a name="change-value-actions"></a>값 변경 동작  
 **값 변경** 동작은 지정된 특성 또는 특성 값을 업데이트합니다. 사용자는 새 값에 따른 동작이 True인 경우에만 이러한 값을 변경할 수 있습니다.  
  
|값 이름|Description|  
|----------------|-----------------|  
|**같음**|선택한 특성이 정의된 특성 값 또는 다른 특성으로 변경되거나, 비어 있습니다.<br /><br /> 이 동작은 텍스트, 숫자, 날짜 및 링크 값에 유효합니다.|  
|**연결된 값과 같음**|선택한 특성이 연결된 값으로 변경됩니다. 이 값은 지정하는 여러 특성에 따라 결정됩니다.<br /><br /> 이 동작은 텍스트 및 링크 값에 유효합니다.|  
  
## <a name="validation-actions"></a>유효성 검사 동작  
 **유효성 검사** 동작은 True로 평가되지 않은 경우 지정된 사용자 또는 그룹에 전자 메일을 보냅니다. 버전을 커밋하려면 모든 유효성 검사 동작이 True로 평가되어야 합니다.  
  
 단, **필수** 및 **잘못됨** 동작은 예외입니다. 이러한 동작은 값 변경 동작과 함께 실행되어야 데이터의 유효성이 성공적으로 검사되고 버전이 커밋될 수 있습니다.  
  
|유효성 검사 이름|Description|  
|---------------------|-----------------|  
|**필수**|선택한 특성이 **필수**입니다. 즉, Null이거나 비어 있을 수 없습니다.<br /><br /> 이 동작은 텍스트, 숫자, 날짜 및 링크 값에 유효합니다.|  
|**유효 하지 않음**|선택한 특성이 **잘못되었습니다**.<br /><br /> 이 동작은 텍스트, 숫자, 날짜 및 링크 값에 유효합니다.|  
|**패턴을 포함해야 함**|선택한 특성이 지정된 **패턴을 포함해야** 합니다. 패턴은 .NET Framework 정규식을 사용하여 지정할 수 있습니다.<br /><br /> 정규식에 대한 자세한 내용은 MSDN Library의 [정규식 언어 요소](/dotnet/standard/base-types/regular-expression-language-quick-reference) 를 참조하십시오.<br /><br /> 이 동작은 텍스트 및 링크 값에 유효합니다.|  
|**고유해야 함**|선택한 특성이 정의된 특성에 대해 별도로 또는 특성과 조합하여 **고유해야** 합니다.<br /><br /> **최선의 구현 방법:** 이 동작을 필수 조건과 함께 사용하면 구독 시스템의 인덱스 필드 유효성을 확인할 수 있습니다.<br /><br /> 이 동작은 텍스트, 숫자, 날짜 및 링크 값에 유효합니다.<br /><br /> **참고**: 첫 번째 특성이 날짜/시간 형식이면 숫자 또는 텍스트 형식의 특성과 함께 사용할 수 없습니다. 첫 번째 특성이 숫자 형식이면 날짜/시간 형식의 특성과 함께 사용할 수 없습니다.|  
|**다음 값 중 하나가 있어야 함**|선택한 특성에 목록에 지정된 **값 중 하나가 있어야** 합니다.<br /><br /> 이 동작은 텍스트 값에 유효합니다.|  
|**보다 커야 함**|선택한 특성이 특정 특성 또는 특정 특성 값 **보다 크거나** , 비어 있어야 합니다.<br /><br /> 이 동작은 텍스트, 숫자 및 날짜 값에 유효합니다.|  
|**같아야 함**|선택한 특성이 정의된 특성 값 또는 다른 특성과 **같거나** , 비어 있어야 합니다.<br /><br /> 이 동작은 텍스트, 숫자, 날짜 및 링크 값에 유효합니다.|  
|**크거나 같아야 함**|선택한 특성이 특정 특성 또는 특정 특성 값보다 **크거나 같거나** , 비어 있어야 합니다.<br /><br /> 이 동작은 텍스트, 숫자 및 날짜 값에 유효합니다.|  
|**보다 작아야 함**|선택한 특성이 특정 특성 또는 특정 특성 값보다 **작거나** , 비어 있어야 합니다.<br /><br /> 이 동작은 텍스트, 숫자 및 날짜 값에 유효합니다.|  
|**작거나 같아야 함**|선택한 특성이 특정 특성 또는 특정 특성 값보다 **작거나 같거나** , 비어 있어야 합니다.<br /><br /> 이 동작은 텍스트, 숫자 및 날짜 값에 유효합니다.|  
|**사이 여야 함**|선택한 특성이 특정 특성 또는 특성 값 두 개의 **사이** 에 있어야 합니다.<br /><br /> 이 동작은 텍스트, 숫자 및 날짜 값에 유효합니다.|  
|**최소 길이**|선택한 특성이 지정된 값의 **최소 길이** 여야 합니다.<br /><br /> 이 동작은 텍스트 및 링크 값에 유효합니다.|  
|**최대 길이**|선택한 특성이 지정된 값의 **최대 길이** 여야 합니다.<br /><br /> 이 동작은 텍스트 및 링크 값에 유효합니다.|  
  
## <a name="external-action"></a>외부 동작  
 **외부** 동작은 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]외부 애플리케이션과 상호 작용합니다.  
  
|동작 이름|Description|  
|-----------------|-----------------|  
|**워크플로 시작**|외부 워크플로를 시작합니다. 이 동작을 발생시킨 데이터가 워크플로로 전달됩니다. 자세한 내용은 [Master Data Services와 SharePoint 워크플로 통합](/previous-versions/sql/sql-server-2008-r2/gg690195(v=msdn.10))을 참조하십시오.<br /><br /> 이 동작은 텍스트, 숫자, 날짜 및 링크 값에 유효합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [비즈니스 규칙 조건 &#40;MDS(Master Data Services)&#41;](../master-data-services/business-rule-conditions-master-data-services.md)   
 [비즈니스 규칙 &#40;MDS(Master Data Services)&#41;](../master-data-services/business-rules-master-data-services.md)   
 [비즈니스 규칙 만들기 및 게시&#40;Master Data Services&#41;](../master-data-services/create-and-publish-a-business-rule-master-data-services.md)  
  
