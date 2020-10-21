---
title: 배포 속성 설정(Reporting Services) | Microsoft Docs
description: 보고서를 작성하고, 미리 보고, 배포하기 위해 SSDT(SQL Server Data Tools) 또는 Visual Studio에서 사용하는 배포 속성을 설정하는 방법을 알아봅니다.
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: tools
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], deploying
- publishing reports [Reporting Services]
- properties [Reporting Services], deployment
- deploying reports [Reporting Services]
ms.assetid: 18201ca0-bf4a-484f-b3a2-95d1046a6a9b
author: maggiesMSFT
ms.author: maggies
ms.date: 05/15/2019
ms.openlocfilehash: 97a0f7d9bf63bf6ad74b522a42900fc36cfcd429
ms.sourcegitcommit: 783b35f6478006d654491cb52f6edf108acf2482
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91891653"
---
# <a name="set-deployment-properties-reporting-services"></a>배포 속성 설정(Reporting Services)

  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 또는 Visual Studio에서는 보고서 서버 프로젝트의 항목을 보고서 서버에 게시할 수 있도록 보고서 서버를 지정하고 필요에 따라 보고서 및 공유 데이터 원본의 폴더를 지정해야 합니다. [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 또는 Visual Studio에서 보고서를 빌드, 미리 보기 및 배포하는 데 필요한 속성과 값은 보고서 서버 프로젝트의 프로젝트 구성에 저장됩니다. 속성 집합을 편리하게 전환할 수 있도록 이러한 프로젝트 속성에 대한 명명된 집합을 여러 개 만들 수 있습니다. 각 속성 집합은 하나의 구성입니다. 예를 들어 테스트 서버에 보고서를 게시하는 구성과 프로덕션 서버에 보고서를 게시하는 구성이 각각 존재할 수 있습니다.  
  
 구성 관리자를 사용하여 프로젝트 구성에서 프로젝트 속성 집합을 만들고 관리할 수 있습니다. 구성 관리자는 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]의 기반이 되는 [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] 에서 지원하는 기능입니다.  
  
> [!NOTE]  
> 설치 후 Reporting Services를 구성하는 데 사용되는 보고서 서버 구성 관리자와 이 기능을 혼동하지 마세요. 자세한 내용은 [보고서 서버 구성 및 관리&#40;SSRS 기본 모드&#41;](../../reporting-services/report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)를 참조하세요.  
>
> [!NOTE]  
> [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]에서는 보고서 서버 프로젝트 또는 솔루션에서 보고서를 게시하는 동작을 *보고서 배포*라고 합니다.  
  
## <a name="to-set-deployment-properties"></a>배포 속성을 설정하려면
  
1. 보고서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
2. 프로젝트에 대한 **속성 페이지** 대화 상자의 **구성** 목록에서 편집할 구성을 선택합니다. 일반적인 구성은 **DebugLocal**, **Debug**및 **Release**입니다.  
  
    > [!NOTE]  
    > 여러 구성을 사용하여 서로 다른 보고서 서버 또는 설정 사이에서 빠르게 전환할 수 있습니다.  
  
3. **OutputPath**  입력란에서 보고서의 빌드 확인, 배포 및 미리 보기에 사용되는 보고서 정의를 저장할 로컬 파일 시스템의 경로를 입력하거나 붙여넣습니다. 이 경로는 프로젝트에 사용하는 경로 및 프로젝트 경로 아래의 자식 폴더인 상대 경로와 달라야 합니다.  
  
4. **ErrorLevel**  입력란에 오류로 보고되는 빌드 문제의 심각도를 입력합니다. **ErrorLevel**  값보다 작거나 같은 심각도 수준을 가진 보고서, 데이터 원본 또는 기타 프로젝트 리소스를 빌드할 때 발생한 문제는 오류로 보고되고 그렇지 않은 문제는 경고로 보고됩니다. 오류가 발생하면 빌드 태스크가 실패합니다. 유효한 심각도 수준은 0에서 4까지입니다. 기본값은 2입니다.  
  
     **ErrorLevel** 을 사용하여 빌드의 중요도를 높이거나 낮출 수 있습니다. 예를 들어 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] 보고서 서버에 배포하는 동안 지도가 있는 보고서를 빌드할 경우 기본적으로 오류가 표시되고 보고서 빌드가 실패합니다. **ErrorLevel** 을 낮추면 지도가 보고서에서 제거되고 경고가 표시되며 보고서 빌드가 계속됩니다.  
  
5. **StartItem**  목록에서 보고서를 선택하여 보고서 프로젝트가 실행 중일 때 미리 보기 창이나 브라우저 창에 표시합니다.  
  
6. **OverwriteDataSources** 목록에서 공유 데이터 원본이 게시될 때마다 서버에서 공유 데이터 원본을 덮어쓰게 하려면 **True** 를 선택하고, 서버에서 데이터 원본을 그대로 유지하려면 **False** 를 선택합니다.  
  
7. **TargetServerVersion** 목록에서 SQL Server 2016 버전의 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 또는 **버전 검색** 을 선택하여 **TargetServer URL** 속성이 식별하는 서버에 설치된 버전을 자동으로 확인합니다. 기본값은 **SQL Server 2016 이상**입니다.  
  
     **TargetServerVersion** 을 사용하여 **TargetServer URL**에 지정된 보고서 서버의 버전에 맞게 OutputPath에 지정된 경로에 있는 빌드된 보고서를 사용자 지정할 수 있습니다.  
  
8. **TargetDataSourceFolder** 입력란에 게시된 공유 데이터 원본을 저장할 보고서 서버의 폴더를 입력합니다. **TargetDataSourceFolder** 의 기본값은 Data Sources입니다. 이 필드를 비워 두면 데이터 원본이 **TargetReportFolder**에 지정된 위치에 게시됩니다.  
  
9. **TargetReportFolder** 입력란에 게시된 보고서를 저장할 보고서 서버의 폴더를 입력합니다. **TargetReportFolder**  의 기본값은 보고서 프로젝트 이름입니다.  
  
    > [!NOTE]  
    > 기본 모드로 실행 중인 보고서 서버의 경우 대상 폴더에 보고서를 게시하려면 해당 폴더에 대한 **게시** 권한이 있어야 합니다. 게시 권한은 게시 작업을 포함하는 역할에 사용자 계정을 매핑하는 역할 할당을 통해 제공됩니다. 자세한 내용은 [역할 할당 만들기 및 관리](../../reporting-services/security/create-and-manage-role-assignments.md)를 참조하세요. SharePoint 통합 모드로 실행 중인 보고서 서버의 경우 SharePoint 사이트에 대한 **멤버** 또는 **소유자** 권한이 있어야 합니다. 자세한 내용은 [보고서 서버 항목에 대한 SharePoint 사이트 및 목록 사용 권한 참조](../../reporting-services/security/sharepoint-site-and-list-permission-reference-for-report-server-items.md)를 참조하세요.  
  
10. **TargetServerURL** 입력란에 대상 보고서 서버의 URL을 입력합니다. 보고서를 게시하기 전에 이 속성을 유효한 보고서 서버 URL로 설정해야 합니다. 기본 모드로 실행 중인 보고서 서버에 게시하는 경우 보고서 서버의 가상 디렉터리 URL(예: http:*//server/reportserver* 또는 https:*//server/reportserver*)을 사용합니다. 이는 웹 포털이 아닌 보고서 서버의 가상 디렉터리입니다.  
  
     SharePoint 통합 모드로 실행 중인 보고서 서버에 게시하는 경우 SharePoint 최상위 사이트나 하위 사이트에 대한 URL을 사용합니다. 사이트를 지정하지 않으면 기본 최상위 사이트(예: `https://*servername*`, `https://*servername*/*site*`또는 `https://*servername*/*site*/*subsite*`)으로 나열됩니다.  
  
## <a name="to-set-configuration-manager-properties"></a>구성 관리자 속성을 설정하려면  
  
1. 보고서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
2. 해당 프로젝트의 **속성 페이지** 대화 상자에서 **구성 관리자**를 클릭합니다.  
  
3. **구성 관리자** 대화 상자에서 편집할 구성을 선택합니다. 현재 활성 구성이 **활성(***\<configuration>***)** 으로 표시됩니다.  
  
4. **프로젝트 컨텍스트**에서 솔루션의 각 프로젝트에 대해 **빌드** 또는 **배포**를 선택하거나 선택을 취소합니다.  
  
    > [!NOTE]  
    > **빌드** 를 선택하면 보고서 디자이너는 보고서 프로젝트를 빌드한 다음 미리 보거나 보고서 서버에 게시하기 전에 오류를 확인합니다. **배포** 를 선택하면 보고서 디자이너는 배포 속성에서 정의된 보고서 서버에 보고서를 게시합니다. **배포** 를 선택하지 않으면 보고서 디자이너는 **StartItem** 속성에 지정된 보고서를 로컬 미리 보기 창에 표시합니다.  
  
## <a name="see-also"></a>참고 항목  

- [데이터 원본 및 보고서 게시](../../reporting-services/reports/publishing-data-sources-and-reports.md)
- [보고서 미리 보기](../../reporting-services/reports/previewing-reports.md)
- [보고서 디자이너 F1 도움말](../../reporting-services/tools/report-designer-f1-help.md)
- [SharePoint 모드의 보고서 서버에 게시된 보고서 항목에 대한 URL 예&#40;SSRS&#41;](../../reporting-services/tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md)
- [프로젝트 속성 페이지 대화 상자](../../reporting-services/tools/project-property-pages-dialog-box.md)
- [보고서 서버에 보고서 게시](../../reporting-services/reports/publishing-reports-to-a-report-server.md)
