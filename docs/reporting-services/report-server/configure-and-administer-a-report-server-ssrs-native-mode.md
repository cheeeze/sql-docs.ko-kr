---
title: 보고서 서버 구성 및 관리(기본 모드) | Microsoft Docs
description: Reporting Services를 구성하는 데 사용할 수 있는 접근 방식과 구성 요소, 기능 또는 서버 기능을 구성하는 방법에 대한 문서를 찾는 방법을 알아봅니다.
ms.date: 05/15/2019
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, components
- deploying [Reporting Services], component options
- report servers [Reporting Services], component options
- configuration options [Reporting Services]
- administering Reporting Services
- components [Reporting Services], configuring
- configuring servers [Reporting Services]
ms.assetid: cfec012b-56f1-4346-9814-247acf22351c
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3f9d31706fd0ba46c565d4c9049a981dd06fb54b
ms.sourcegitcommit: fe59f8dc27fd633f5dfce54519d6f5dcea577f56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91933800"
---
# <a name="configure-and-administer-a-report-server-ssrs-native-mode"></a>보고서 서버 구성 및 관리(SSRS 기본 모드)
  이 문서에서는 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]를 구성하는 데 사용할 수 있는 방식을 요약하여 설명합니다. 또한 여기에는 특정 구성 요소, 기능 또는 서버 기능의 구성 방법을 설명하는 항목의 목록도 포함되어 있습니다. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]를 구성하기 위해 다음 작업을 수행할 수 있습니다.  
  
-   보고서 서버 구성 관리자를 사용합니다. 이 섹션에서 대부분의 항목은 이 도구를 통해 특정 기능을 구성하는 방법에 대한 정보를 포함합니다.  
  
-   [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] 를 사용하여 서버 속성 사용자 지정, 내 보고서 활성화, 추적 로그 활성화 및 사이트 전체 기본값 설정을 수행할 수 있습니다. 사이트 설정에 대한 자세한 내용은 Management Studio의 [Reporting Services 보고서 서버&#40;기본 모드&#41;](../../reporting-services/report-server/reporting-services-report-server-native-mode.md) 를 참조하세요. 서버 속성을 프로그래밍 방식으로 설정하는 스크립트를 만들고 실행할 수 있습니다. 자세한 내용은 [배포 및 관리 태스크 스크립팅](../../reporting-services/tools/script-deployment-and-administrative-tasks.md) 및 [보고서 서버 시스템 속성](../../reporting-services/report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md)을 참조하세요.  
  
-   웹 포털을 사용하여 보고서 서버에 액세스하는 사용 권한을 부여할 수 있습니다. 사용 권한은 각 사용자 또는 그룹 계정에 대해 정의하는 역할 할당을 통해 제공됩니다. 자세한 내용은 [역할 및 사용 권한&#40;Reporting Services&#41;](../../reporting-services/security/roles-and-permissions-reporting-services.md)을 참조하세요.  
  
-   필요에 따라 구성 파일을 수정하여 애플리케이션 설정을 변경할 수 있습니다. 각 파일에 대한 자세한 내용과 해당 파일의 수정 지침은 [Reporting Services Configuration Files](../../reporting-services/report-server/reporting-services-configuration-files.md)을 참조하십시오.  
  
## <a name="in-this-section"></a>섹션 내용  
 [보고서 서버 URL 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 보고서 서버 및 웹 포털에 액세스하는 데 사용하는 URL을 정의하는 방법을 설명합니다.  
  
 [보고서 서버 서비스 계정 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 서비스 계정 및 암호를 수정하는 방법에 대한 권장 사항과 단계를 제공합니다.  
  
 [보고서 서버 데이터베이스 만들기&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-report-server-create-a-report-server-database.md)  
 서버 메타데이터 및 개체를 저장하는 데 필요한 보고서 서버 데이터베이스를 만드는 방법을 설명합니다.  
  
 [보고서 서버 데이터베이스 연결 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 보고서 서버에서 보고서 서버 데이터베이스에 연결하는 데 사용하는 연결 문자열을 수정하는 방법을 설명합니다.  
  
 [Reporting Services의 전자 메일 배달](../install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md)  
 전자 메일 보고서 배포를 지원하도록 보고서 서버를 구성하는 방법을 설명합니다.  
  
 [무인 실행 계정 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 보고서를 무인 모드로 처리하는 데 필요한 사용자 계정을 구성하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Reporting Services 구성 파일](../../reporting-services/report-server/reporting-services-configuration-files.md)   
 [보고서 서버 구성 관리자&#40;기본 모드&#41;](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md)   
 [Reporting Services 보안 및 보호](../../reporting-services/security/reporting-services-security-and-protection.md)   
 [Reporting Services 보고서 서버&#40;기본 모드&#41;](../../reporting-services/report-server/reporting-services-report-server-native-mode.md)  
  
  
