---
title: Management Studio에서 보고서 서버에 연결 | Microsoft Docs
description: SQL Server 제품군의 서버에 연결하고 SQL Server Management Studio의 개체 탐색기를 사용하여 그래픽으로 콘텐츠를 검색하는 방법을 알아봅니다.
ms.date: 05/07/2019
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: tools
ms.topic: conceptual
f1_keywords:
- sql13.swb.connecttors.connectionproperties.f1
- sql13.swb.connecttors.login.f1
- sql13.swb.connection.login.reportserver.f1
helpviewer_keywords:
- report servers [Reporting Services], connections
- connections [Reporting Services], report server
- registering report servers
- report servers [Reporting Services], registering
- Connect to Server dialog box, Reporting Services
ms.assetid: c875ff87-ee7d-443a-a702-bdb4b6c27c6e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 027d3bb67c087f119c3848a2d81ac0875b138db3
ms.sourcegitcommit: fe59f8dc27fd633f5dfce54519d6f5dcea577f56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91934855"
---
# <a name="connect-to-a-report-server-in-management-studio"></a>Management Studio에서 보고서 서버에 연결

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 제품군의 모든 서버에 연결하고 관련 콘텐츠를 그래픽 방식으로 찾아볼 수 있는 개체 탐색기를 제공합니다. Reporting Services의 경우 개체 탐색기를 사용하여 다음 태스크를 수행할 수 있습니다.

- 보고서 서버 기능 사용

- 서버 기본값 설정 및 역할 정의 구성

- 실행 중인 작업 관리

- 작업 일정 관리

 기본 모드 보고서 서버 또는 SharePoint 통합 모드에서 실행되는 보고서 서버에 연결할 수 있습니다. 연결 구문 및 수행할 수 있는 작업 유형은 보고서 서버의 서버 모드 및 사용 권한에 따라 달라집니다. 보고서 서버에 연결할 수 없거나 특정 태스크를 수행하는 데 문제가 있는 경우, 충분한 권한이 없거나 보고서 서버의 이름을 잘못 지정한 것입니다. 사용 권한 및 연결 구문에 대한 자세한 내용은 이 문서의 끝에 있는 표를 참조하세요.

 개체 탐색기를 사용하여 보고서 서버 콘텐츠를 보거나 관리할 수 없습니다. 콘텐츠 관리는 보고서 서버가 기본 모드로 실행되는 경우 웹 포털을 통해 수행하고, 보고서 서버가 SharePoint 통합 모드로 실행되는 경우 SharePoint 사이트를 통해 수행합니다.

 서버가 같은 서버 그룹에 등록되어 있는 한 개체 탐색기를 사용하여 같은 작업 영역에 있는 여러 서버 인스턴스에 대한 연결을 열 수 있습니다. [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]의 보고서 서버 인스턴스에 연결하려면 먼저 서버를 등록해야 합니다. 보고서 서버가 이미 등록되어 있는 경우 이 단계를 건너뛸 수 있습니다. 보고서 서버 등록 방법에 대한 지침은 이 문서의 끝에 제공되어 있습니다.

### <a name="to-connect-to-a-native-mode-report-server"></a>기본 모드 보고서 서버에 연결하려면

1. 개체 탐색기가 아직 열려 있지 않으면, **보기** 메뉴에서 선택합니다.

2. **연결**을 선택하여 서버 유형 목록을 보고 **Reporting Services**를 선택합니다.

3. **서버에 연결** 대화 상자에서 보고서 서버 인스턴스의 이름을 입력합니다. 보고서 서버 인스턴스 이름은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스 이름을 기반으로 합니다. 기본적으로 로컬 보고서 서버 인스턴스의 인스턴스 이름은 컴퓨터 이름입니다. 보고서 서버를 명명된 인스턴스로 설치한 경우 다음 구문을 사용하여 서버를 지정합니다. *\<servername>[\\<instancename\>]* .

4. **인증 형식**을 선택합니다. Windows 인증을 사용하는 경우 자격 증명을 사용하여 연결합니다. 기본 인증 또는 폼 인증을 선택하는 경우 계정과 암호를 입력합니다.  
  
5. **연결**을 선택합니다. 개체 탐색기에 보고서 서버가 나타납니다.  

6. 서버 노드를 마우스 오른쪽 단추로 클릭하여 시스템 속성과 서버 기본값을 설정합니다. 자세한 내용은 [보고서 서버 속성 설정&#40;Management Studio&#41;](../../reporting-services/tools/set-report-server-properties-management-studio.md)를 참조하세요.

### <a name="to-connect-to-a-sharepoint-integrated-mode-report-server"></a>SharePoint 통합 모드 보고서 서버에 연결하려면  

1. 개체 탐색기가 아직 열려 있지 않으면, **보기** 메뉴에서 선택합니다.

2. **연결**을 선택하여 서버 유형 목록을 보고 **Reporting Services**를 선택합니다.

3. **서버에 연결** 대화 상자에서 SharePoint 사이트 URL을 입력합니다. 다음 예에서는 구문을 보여줍니다.`https://<web server>/sites/<site>`

4. **인증 형식**을 선택합니다. Windows 인증을 사용하는 경우 자격 증명을 사용하여 연결해야 합니다. 기본 인증 또는 폼 인증을 선택하는 경우 계정과 암호를 입력합니다.

5. **연결**을 선택합니다. 개체 탐색기에 보고서 서버가 나타납니다.

6. 서버 노드를 마우스 오른쪽 단추로 클릭하여 시스템 속성과 서버 기본값을 설정합니다. 자세한 내용은 [보고서 서버 속성 설정&#40;Management Studio&#41;](../../reporting-services/tools/set-report-server-properties-management-studio.md)를 참조하세요.

### <a name="to-register-a-report-server"></a>보고서 서버를 등록하려면

1. 보고서 서버에 연결할 수 없는 경우 액세스 권한이 없거나 서버를 등록하지 않은 것입니다. 서버를 등록하려면 **보기** 메뉴 > **등록된 서버**를 선택합니다.

2. **Reporting Services** 아이콘을 선택합니다.

3. **Reporting Services**를 마우스 오른쪽 단추로 클릭하고 > **새로 만들기** > **서버 등록**을 선택합니다. **새 서버 등록** 대화 상자가 표시됩니다.

4. **서버 이름**에 값을 입력합니다. 서버 모드에 따라 값을 지정합니다.

    - 기본 모드 보고서 서버의 경우 보고서 서버 인스턴스의 이름을 입력합니다. 보고서 서버 인스턴스 이름은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스 이름을 기반으로 합니다. 기본적으로 로컬 보고서 서버 인스턴스의 인스턴스 이름은 컴퓨터 이름입니다. 보고서 서버를 명명된 인스턴스로 설치한 경우 다음 구문을 사용하여 서버를 지정합니다. *\<servername>[\\<instancename\>]* .

    - SharePoint 통합 모드에서 실행되는 보고서 서버의 경우 연결할 서버는 보고서 서버가 연결된 SharePoint 사이트입니다. 사용 권한 수준을 볼 수 있도록 SharePoint 사이트에 연결합니다. 사용 권한은 보고서 서버 콘텐츠 및 작업에 대한 액세스를 제어합니다. 사이트 모음에 임의의 사이트를 지정할 수 있습니다. 다음 예에서는 구문을 보여줍니다.`https://mysharepointsite`

5. **인증**에서 보고서 서버가 이미 사용하고 있는 인증 모드를 선택합니다.

   - 기본 보안을 사용하는 경우 **Windows 인증**을 선택합니다.
   - 사용자 지정 보안 확장 프로그램을 설치 및 배포한 경우에는 **폼 인증**을 선택합니다.
   - 기본 인증을 사용하도록 보고서 서버를 구성한 경우 **기본 인증**을 선택합니다.
   - 보고서 서버가 SharePoint 통합 모드용으로 구성된 경우 **Windows 인증**을 선택합니다.

6. **테스트**를 선택하여 연결을 확인합니다.

7. 메시지가 표시되면 **확인**, **저장**을 차례로 선택합니다.

## <a name="connection-syntax-and-permissions"></a>연결 구문 및 사용 권한

 다음 표에는 특정 태스크를 수행하는 데 필요한 연결 구문, 단계 및 사용 권한이 요약되어 있습니다.

 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 서버에 연결 **대화 상자에서** 를 서버 유형으로 지정하는 경우 보고서 서버 이름이나 웹 서비스에 대한 엔드포인트를 지정할 수 있습니다.

|연결 대상|   작업   |   사용 권한   |
|----------|-----------|-----------------|  
|기본값 또는 명명된 인스턴스로 연결된 기본 모드 보고서 서버<br /><br /> \<server name>\<_instance><br /><br /> 보고서 서버에는 보고서 서버 WMI 공급자를 통해 연결됩니다.|서버 속성 및 기본값을 보고 설정합니다.<br /><br /> 작업을 보고 취소합니다.<br /><br /> 공유 일정을 만들고 관리합니다.<br /><br /> 역할 정의를 생성, 수정 또는 삭제합니다.|시스템 관리자 역할에 할당됨|  
|보고서 서버 웹 서비스에 대한 엔드포인트를 통해 기본값 또는 명명된 인스턴스로 연결된 기본 모드 보고서 서버<br /><br /> `https://<servername>/reportserver`<br /><br /> 보고서 서버 URL을 지정하면 보고서 서버에 다른 방법으로 연결할 수 있습니다.|서버 속성 및 기본값을 보고 설정합니다.<br /><br /> 작업을 보고 취소합니다.<br /><br /> 공유 일정을 만들고 관리합니다.<br /><br /> 역할 정의를 생성, 수정 또는 삭제합니다.|시스템 관리자 역할에 할당됨|  
|SharePoint 사이트를 통해 연결된 SharePoint 통합 모드 보고서 서버<br /><br /> `https://<webserver>/<SharePointSite>`|서버 속성 및 기본값을 보고 설정합니다.<br /><br /> 작업을 보고 취소합니다.<br /><br /> 연결된 사이트에 대해 정의된 공유 일정을 만들고 관리합니다.<br /><br /> 연결된 사이트에 대해 정의된 사용 권한 수준을 봅니다.|연결된 SharePoint 사이트의 사용 권한 수준을 완전히 제어합니다.|
|보고서 서버 인스턴스의 이름을 통해 연결된 SharePoint 통합 모드 보고서 서버<br /><br /> \<server name>\<_instance>|서버 속성 및 기본값을 보고 설정합니다.<br /><br /> 작업을 보고 취소합니다.|보고서 서버와 통합된 SharePoint 사이트에 대한 모든 권한 수준의 사용 권한<br /><br /> SharePoint 사이트가 아닌 보고서 서버에 연결하면 수행할 수 있는 태스크 수가 줄어듭니다. 보고서 서버가 SharePoint 구성 및 콘텐츠 데이터베이스가 아닌 보고서 서버 데이터베이스에서 저장되거나 관리되는 애플리케이션 데이터만 반환할 수 있기 때문입니다.|

## <a name="see-also"></a>참고 항목

 [보고서 서버 데이터베이스 연결 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 [SQL Server Management Studio의 Reporting Services&#40;SSRS&#41;](../../reporting-services/tools/reporting-services-in-sql-server-management-studio-ssrs.md)
