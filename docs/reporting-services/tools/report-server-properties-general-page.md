---
title: 서버 속성(일반 페이지) | Microsoft Docs
description: 보고서 서버 속성 페이지의 옵션에 대해 알아봅니다.
ms.date: 06/08/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: tools
ms.topic: conceptual
f1_keywords:
- sql13.swb.reportserver.serverproperties.general.f1
ms.assetid: 23537d52-4356-450f-a671-5921cef2431f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 1a7b6731d3dd7b8bbb5218119cc3548e302952ac
ms.sourcegitcommit: fe59f8dc27fd633f5dfce54519d6f5dcea577f56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91935290"
---
# <a name="report-server-properties-general-page"></a>보고서 서버 속성(일반 페이지)
  이 페이지를 사용하여 보고서 관리자에 사용된 제목을 보거나 수정하고, 내 보고서를 설정 또는 해제하고, 내 보고서의 보안에 대한 역할 정의를 선택하고 클라이언트 인쇄 컨트롤을 설정 또는 해제할 수 있습니다.  
  
 **이 페이지를 열려면**
 1) 시작 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]
 2) 보고서 서버 인스턴스에 연결합니다.
 3) 보고서 서버 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 선택합니다.  
  
 서버 모드에 따라 설정할 수 있는 서버 속성이 결정됩니다. SharePoint 통합 모드로 구성된 보고서 서버를 관리하는 경우 내 보고서를 활성화하거나 웹 포털에 대한 제목을 설정할 수 없습니다.  
  
## <a name="options"></a>옵션  
 **이름**  
 웹 포털의 맨 위에 표시되는 이름을 입력합니다. 이 값은 기본적으로 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]입니다. 지정한 이름은 보고서 관리자에만 나타납니다.  
  
 **버전**  
 이 속성은 읽기 전용입니다. 사용 중인 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]의 버전을 지정합니다.  
  
 **버전(Edition)**  
 이 속성은 읽기 전용입니다. 현재 보고서 서버 인스턴스를 지정합니다. 일부 [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]버전에서는 보고서 관리자를 사용할 수 없습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 버전에서 지원되는 기능 목록은 [SQL Server 2017의 버전과 지원하는 기능](../../sql-server/editions-and-components-of-sql-server-2017.md)을 참조하세요.  
  
 **인증 모드**  
 이 속성은 읽기 전용입니다. 보고서 서버 인스턴스에서 허용되는 인증 요청의 유형을 식별합니다. 인증 모드를 변경하려면 **RSReportServer.config** 파일을 편집해야 합니다. 자세한 내용은 [Authentication with the Report Server](../../reporting-services/security/authentication-with-the-report-server.md)을(를) 참조하세요.  
  
 **URL**  
 이 속성은 읽기 전용입니다. 보고서 서버 웹 서비스에 대한 URL을 지정합니다. 이 값은 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 구성 도구에 지정됩니다. 자세한 내용은 [URL 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md)을 참조하세요.  
  
 **각 사용자에 대해 내 보고서 폴더 설정**  
 사용자가 **내 보고서** 를 사용할 수 있도록 합니다. 이 옵션은 기본 모드 보고서 서버에서만 사용할 수 있습니다.  
  
 **각 내 보고서 폴더에 적용할 역할을 선택하십시오.**  
 내 보고서의 보안에 사용할 역할 정의를 지정합니다. 역할 정의는 각 내 보고서 폴더에서 지원되는 태스크 집합을 식별합니다.  

  
## <a name="see-also"></a>참고 항목  
 [보고서 서버 속성 설정&#40;Management Studio&#41;](../../reporting-services/tools/set-report-server-properties-management-studio.md)   
 [Management Studio에서 보고서 서버에 연결](../../reporting-services/tools/connect-to-a-report-server-in-management-studio.md)   
 [내 보고서 사용 및 사용 안 함 설정](../../reporting-services/report-server/enable-and-disable-my-reports.md)   
 [Management Studio의 보고서 서버 F1 도움말](../../reporting-services/tools/report-server-in-management-studio-f1-help.md)   
 [내 보고서 보안](../../reporting-services/security/secure-my-reports.md)  
  
  

