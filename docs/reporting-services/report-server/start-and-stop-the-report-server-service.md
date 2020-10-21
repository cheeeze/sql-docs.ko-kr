---
title: 보고서 서버 서비스 시작 및 중지 | Microsoft Docs
description: 보고서 서버 웹 서비스, 웹 포털 및 백그라운드 처리 애플리케이션을 포함하는 Windows 서비스를 시작 및 중지하는 방법을 알아봅니다.
ms.date: 05/21/2019
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server
ms.topic: conceptual
helpviewer_keywords:
- stopping Report Server service
- Report Server Windows service, starting
- Report Server service, starting
- starting Report Server service
ms.assetid: 6ec69ac3-27b0-472d-91e1-733af9078ed2
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b7f60e735ecd2483f8f105666ee181cb48eaa98b
ms.sourcegitcommit: a41e1f4199785a2b8019a419a1f3dcdc15571044
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "91987509"
---
# <a name="start-and-stop-the-report-server-service"></a>보고서 서버 서비스 시작 및 중지

  보고서 서버는 보고서 서버 웹 서비스, 웹 포털 및 백그라운드 처리 애플리케이션을 포함하는 Windows 서비스로 구현됩니다. 보고서 서버 기능을 사용하려면 서비스를 실행해야 합니다. 서비스를 중지하면 모든 보고서 서버 작업이 중지됩니다.  
  
 서비스가 중지된 동안 서비스 실행 중에 발생했을 수 있는 예약된 보고서 및 구독 처리 요청이 큐에 추가됩니다. 이는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트가 실행한 작업이 이벤트를 만들기 때문입니다. 서비스가 해제된 동안 작업 백로그가 발생하지 않도록 하려면 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트도 중지하는 것이 좋습니다.  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 구성 도구, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 구성 관리자 및 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows의 서비스 도구를 비롯한 다양한 도구를 사용하여 보고서 서버 서비스를 시작 또는 중지할 수 있습니다.  
  
 서비스 계정을 바꾸는 경우처럼 서비스를 시작하거나 중지하는 것 외에 다른 작업을 수행하려면 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 구성 도구를 사용해야 합니다. 다른 도구를 사용하여 서비스 계정을 변경하면 설치된 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 를 사용할 수 없습니다. 자세한 내용은 [보고서 서버 서비스 계정 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)을 참조하세요.  
  
 이 서비스를 일시 중지하고 다시 시작할 수 없습니다. 시작 매개 변수가 없습니다. 명시적 종속 관계는 없지만 보고서 서버에서 구독이나 예약된 보고서 작업을 지원하는 경우에는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 에이전트가 실행 중이어야 합니다.  
  
## <a name="use-the-reporting-services-configuration-tool"></a>Reporting Services 구성 도구 사용  
  
1. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 구성 도구를 시작한 후 보고서 서버에 연결합니다.  
  
2. 보고서 서버 상태 페이지에서 **중지** 또는 **시작**을 선택합니다.  
  
## <a name="use-administrative-tools"></a>관리 도구 사용  

- 관리 도구, 서비스를 차례로 열고 **SQL Server Reporting Services(MSSQLSERVER)** 를 마우스 오른쪽 단추로 클릭한 다음, **중지** 또는 **다시 시작**을 선택합니다.  
  
- 여러 인스턴스를 실행하고 있거나 보고서 서버를 명명된 인스턴스로 실행하는 경우 괄호 안의 인스턴스 이름이 중지 또는 다시 시작하려는 보고서 서버 인스턴스에 해당하는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [보고서 서버 구성 관리자&#40;기본 모드&#41;](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md)   
 [SQL Server 에이전트 서비스 시작, 중지 또는 일시 중지](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
