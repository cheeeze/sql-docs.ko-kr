---
title: 보고서 서버 Windows 서비스(MSSQLServer) 107 | Microsoft Docs
description: 이 오류 참조 페이지에서 이벤트 ID 107에 대해 알아봅니다. Report Server Windows Service (SQL Server)에서 보고서 서버 데이터베이스에 연결할 수 없습니다.
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: troubleshooting
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 4e68ffa14bfe98bc55e5424abe0dbdac944950a1
ms.sourcegitcommit: fe59f8dc27fd633f5dfce54519d6f5dcea577f56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91933698"
---
# <a name="report-server-windows-service-mssqlserver-107"></a>Report Server Windows Service (MSSQLServer) 107
    
## <a name="details"></a>세부 정보  
  
|범주|값|  
|-|-|  
|제품 이름|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|이벤트 ID|107|  
|이벤트 원본|Report Server Windows Service|  
|구성 요소|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|메시지 텍스트|Report Server Windows Service (MSSQLSERVER)에서 보고서 서버 데이터베이스에 연결할 수 없습니다.|  
  
## <a name="explanation"></a>설명  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 보고서 서버 서비스를 보고서 서버 데이터베이스에 연결할 수 없습니다. 이 오류는 보고서 서버 데이터베이스에 연결할 수 없는 경우 서비스를 다시 시작하면 발생합니다. 이 오류가 발생하는 조건은 다음과 같습니다.  
  
-   보고서 서버 서비스가 시작될 때 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] 서비스가 실행되고 있지 않습니다.  
  
-   원격 연결 또는 TCP/IP 프로토콜이 설정되지 않아 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 서비스에 대한 연결이 실패합니다.  
  
-   보고서 서버 데이터베이스가 올바르게 구성되어 있지 않습니다.  
  
-   서비스 계정이 올바르게 구성되어 있지 않거나 계정에 보고서 서버 데이터베이스에 대한 사용 권한이 더 이상 없습니다. 이 조건은 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 구성 도구를 사용하지 않고 계정 또는 보고서 서버 데이터베이스를 설정한 경우에 발생할 수 있습니다.  
  
## <a name="user-action"></a>사용자 동작  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 서비스가 실행되고 있지 않은 경우 해당 서비스를 시작하고 TCP/IP에 대한 원격 연결이 설정되어 있는지 확인합니다.  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 구성 도구를 사용하여 보고서 서버 데이터베이스와 서비스 계정을 구성합니다.  
  
## <a name="internal-only"></a>내부 전용  
  
## <a name="see-also"></a>참고 항목  

 [보고서 서버 서비스 계정 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)   
 [보고서 서버 구성 관리자&#40;기본 모드&#41;](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md)   

 [보고서 서버 서비스 시작 및 중지](../../reporting-services/report-server/start-and-stop-the-report-server-service.md)  
  
  
