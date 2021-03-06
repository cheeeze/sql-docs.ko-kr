---
title: 관계형 쿼리 디자이너에서 쿼리 작성(보고서 작성기 및 SSRS
description: 보고서 데이터 세트용 외부 데이터 원본에서 검색할 데이터를 지정할 수 있도록 관계형 쿼리 디자이너에서 쿼리를 작성하는 방법을 알아봅니다.
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-data
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.custom: ''
ms.date: 04/25/2019
ms.openlocfilehash: 4238085cf388ff4a04c69bb1608a3a36873d46eb
ms.sourcegitcommit: 783b35f6478006d654491cb52f6edf108acf2482
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91891763"
---
# <a name="build-a-query-in-the-relational-query-designer-report-builder-and-ssrs"></a>관계형 쿼리 디자이너에서 쿼리 작성(보고서 작성기 및 SSRS)

쿼리 디자이너를 사용하면 보고서 데이터 세트에 사용하기 위해 외부 데이터 원본에서 검색할 데이터를 지정할 수 있습니다. 마법사에서 쿼리를 작성하거나 데이터 세트 쿼리를 만들 때 쿼리 디자이너를 사용할 수 있습니다.  
  
> [!NOTE]  
> [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 데이터 세트는 데이터 원본을 기반으로 합니다. 데이터 원본의 유형 및 제작 환경에 따라 데이터 세트 쿼리를 정의할 때 열리는 쿼리 디자이너가 결정됩니다. 쿼리 디자이너 기능은 기본 데이터 원본에 따라 다릅니다. 데이터 계층에 대한 자세한 내용은 [데이터 연결 문자열 만들기 - 보고서 작성기 및 SSRS](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)를 참조하세요.

 다음과 같은 태스크에 쿼리 디자이너를 사용할 수 있습니다.  
  
-   외부 데이터 원본에서 여러 스키마에 대한 메타데이터를 탐색합니다.  
  
-   데이터 세트에 대해 검색할 필드를 지정합니다.  
  
-   테이블 등과 같은 두 개체 간의 관계를 지정합니다.  
  
-   보고서 데이터로 검색되기 전에 필터를 지정하여 데이터를 제한합니다.  
  
-   매개 변수를 만들지 여부를 나타냅니다.  
  
-   외부 데이터 원본에서 계산을 수행하기 위해 집계를 지정합니다.  
  
 쿼리 디자이너를 연 후에 포함된 데이터 세트 또는 공유 데이터 세트에 대해 동일한 방법으로 쿼리를 작성합니다. 다음 절차에서는 포함된 데이터 세트 쿼리를 사용합니다.  
  
 자세한 내용은 [관계형 쿼리 디자이너 사용자 인터페이스&#40;보고서 작성기&#41;](../../reporting-services/report-data/relational-query-designer-user-interface-report-builder.md)를 참조하세요.  
  
### <a name="to-build-a-query-for-an-embedded-dataset-in-report-design-view"></a>보고서 디자인 뷰에서 포함된 데이터 세트에 대한 쿼리를 작성하려면  
  
1.  쿼리 디자이너를 엽니다. 보고서 데이터 창에서 데이터 세트를 마우스 오른쪽 단추로 클릭한 다음, **쿼리**를 클릭합니다.  
  
     데이터 원본과 연결된 쿼리 디자이너가 열립니다.  
  
2.  데이터베이스 뷰 창에서 테이블, 뷰, 저장 프로시저 등과 같은 데이터베이스 스키마 개체의 계층 구조를 표시하는 폴더를 확장합니다. 선택 상자를 클릭하여 개체의 모든 필드를 선택하거나 노드를 확장하여 개별 필드를 선택합니다.  
  
     데이터베이스 뷰 창에서 필드를 선택하면 **필드 선택** 창에 선택 항목이 표시됩니다.  
  
     둘 이상의 관련 데이터베이스 테이블에서 필드를 선택한 경우 관계 창을 사용하여 데이터베이스 스키마에서 검색된 테이블 관계를 확인합니다.  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     데이터 세트 필드 목록이 보고서 데이터 창에 나타납니다.  
  
### <a name="to-specify-limits-for-a-query"></a>쿼리에 대한 제한을 지정하려면  
  
1.  관계형 쿼리 디자이너에서 필드가 선택되었으며 **선택한 필드** 창에 해당 필드가 표시되는지 확인합니다.  
  
2.  적용된 필터 창 도구 모음에서 **필터 추가**를 클릭합니다. 새 필터 행이 나타납니다.  
  
3.  **필드 이름**에서 클릭하여 필드의 드롭다운 목록을 표시한 다음 필터링 기준으로 사용할 필드 이름을 클릭합니다. 예를 들어 수량으로 필터링하려면 항목 수를 포함하는 필드를 클릭합니다.  
  
4.  **연산자**에서 클릭하여 연산자의 드롭다운 목록을 표시한 다음 필터에서 사용할 비교 연산자를 선택합니다.  
  
5.  **값**에서 필터링 기준으로 사용할 값을 입력합니다. 예를 들어 100보다 큰 수량을 필터링하려면 100을 입력합니다.  
  
6.  이 행에서 매개 변수 옵션을 선택하여 사용자가 필터 값을 지정할 수 있게 하는 데이터 세트 매개 변수를 만듭니다. 데이터 세트 매개 변수와 일치하는 보고서 매개 변수가 자동으로 만들어집니다.  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 데이터 세트 필드 목록이 보고서 데이터 창에 나타납니다.  
  
### <a name="to-view-a-query-result-set"></a>쿼리 결과 집합을 보려면  
  
1.  쿼리 디자이너 도구 모음에서 **쿼리 실행(!)** 을 클릭합니다.  
  
    > [!NOTE]  
    >  쿼리 디자이너는 디자인 타임 자격 증명을 사용하여 쿼리를 실행하고 결과 집합을 검색합니다. 자세한 내용은 [보고서 데이터 원본에 대한 자격 증명 및 연결 정보 지정](specify-credential-and-connection-information-for-report-data-sources.md)을 참조하세요.  
  
 쿼리는 데이터 원본에서 실행되고 쿼리 결과 창에 예제 데이터를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [보고서 데이터 세트&#40;SSRS&#41;](../../reporting-services/report-data/report-datasets-ssrs.md)   
 [외부 데이터 원본의 데이터 추가&#40;SSRS&#41;](../../reporting-services/report-data/add-data-from-external-data-sources-ssrs.md)   
 [쿼리 디자인 도구&#40;SSRS&#41;](query-design-tools-ssrs.md)   
 [공유 데이터 세트 또는 포함된 데이터 세트 만들기&#40;보고서 작성기 및 SSRS&#41;](../../reporting-services/report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)   
 [보고서 디자인 뷰&#40;보고서 작성기&#41;](../../reporting-services/report-builder/report-design-view-report-builder.md)   
 [공유 데이터 세트 디자인 뷰&#40;보고서 작성기&#41;](../../reporting-services/report-builder/shared-dataset-design-view-report-builder.md)   
 [Reporting Services 쿼리 디자이너](/previous-versions/sql/)  
  
