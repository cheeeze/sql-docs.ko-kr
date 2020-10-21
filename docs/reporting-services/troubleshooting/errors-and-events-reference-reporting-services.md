---
title: 오류 및 이벤트 참조(Reporting Services)
description: 다양한 보고서 서버 이벤트의 ID, 유형, 범주, 원본 및 설명을 확인합니다. 해당 이벤트에는 오류, 경고 및 정보 유형이 포함됩니다.
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: troubleshooting
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.custom: ''
ms.date: 06/12/2019
ms.openlocfilehash: 2631af98c007914e59994d05b83b59186f320ecd
ms.sourcegitcommit: fe59f8dc27fd633f5dfce54519d6f5dcea577f56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91935167"
---
# <a name="errors-and-events-reference-reporting-services"></a>오류 및 이벤트 참조(Reporting Services)

이 문서에서는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]의 오류 및 이벤트 관련 정보를 제공합니다. [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 로그 파일에도 오류 정보가 포함됩니다. 사용할 수 있는 로그 파일의 형식 및 로그를 보는 방법에 대한 자세한 내용은 [Reporting Services 로그 파일 및 소스](../../reporting-services/report-server/reporting-services-log-files-and-sources.md)를 참조하세요.  

## <a name="cause-and-resolution-for-reporting-services-error-messages"></a>Reporting Services 오류 메시지의 원인 및 해결 방법  

[!INCLUDE[msCoName](../../includes/msconame-md.md)] 웹 사이트에서 가장 자주 검색되는 오류의 원인과 해결 방법 정보를 확인할 수 있습니다. 자세한 내용은 [Cause and Resolution of Reporting Services Errors](../../reporting-services/troubleshooting/cause-and-resolution-of-reporting-services-errors.md)을 참조하세요.  
  
## <a name="report-server-events"></a>보고서 서버 이벤트

다음과 같은 보고서 서버 이벤트가 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 애플리케이션 로그에 기록됩니다.  
  
|이벤트 ID|Type|Category|원본|Description|  
|--------------|----------|--------------|------------|-----------------|  
|106|Error|일정 계획|보고서 서버|예약된 작업(예: 보고서 구독 및 배달)을 정의하려면 SQL Server 에이전트를 실행하고 있어야 합니다.|  
|[107](../../reporting-services/troubleshooting/report-server-windows-service-mssqlserver-107.md)|Error|시작/종료|보고서 서버<br /><br /> 일정 예약 및 배달 프로세서|*\<Source>* 에서 보고서 서버 데이터베이스에 연결할 수 없습니다. 자세한 내용은 [보고서 서버 Windows 서비스&#40;MSSQLServer&#41; 107](../../reporting-services/troubleshooting/report-server-windows-service-mssqlserver-107.md)을 참조하세요.|  
|108|Error|내선 번호|보고서 서버<br /><br /> 웹 포털|*\<Source>* 에서 전송, 데이터 처리 또는 렌더링 확장 프로그램을 로드할 수 없습니다.<br /><br /> 확장 프로그램이 불완전하게 배포되었거나 제거된 것 같습니다. 자세한 내용은 [Deploying a Data Processing Extension](../../reporting-services/extensions/data-processing/deploying-a-data-processing-extension.md) 및 [Deploying a Delivery Extension](../../reporting-services/extensions/delivery-extension/deploying-a-delivery-extension.md)를 참조하세요.|  
|109|정보|관리|보고서 서버<br /><br /> 웹 포털|구성 파일이 수정되었습니다. 자세한 내용은 [Reporting Services Configuration Files](../../reporting-services/report-server/reporting-services-configuration-files.md)을 참조하세요.|  
|110|Warning|관리|보고서 서버<br /><br /> 웹 포털|구성 파일 중 하나의 설정이 수정되어 더 이상 사용할 수 없습니다. 기본값이 대신 사용됩니다. 자세한 내용은 [Reporting Services Configuration Files](../../reporting-services/report-server/reporting-services-configuration-files.md)을 참조하세요.|  
|111|Error|로깅|보고서 서버<br /><br /> 웹 포털|*\<Source>* 에서 추적 로그를 만들 수 없습니다. 자세한 내용은 [Report Server Service Trace Log](../../reporting-services/report-server/report-server-service-trace-log.md)을 참조하세요.|  
|112|Warning|보안|보고서 서버|보고서 서버에서 서비스 거부 공격이 발생했습니다. 자세한 내용은 [Reporting Services 보안 및 보호](../../reporting-services/security/reporting-services-security-and-protection.md)를 참조하세요.|  
|113|Error|로깅|보고서 서버|보고서 서버에서 성능 카운터를 만들 수 없습니다.|  
|114|Error|시작/종료|웹 포털|웹 포털에 서 보고서 서버 서비스에 연결할 수 없습니다.|  
|115|Warning|일정 계획|일정 예약 및 배달 프로세서|SQL Server 에이전트 큐의 예약된 태스크가 수정되거나 삭제되었습니다.|  
|116|Error|내부|보고서 서버<br /><br /> 웹 포털<br /><br /> 일정 예약 및 배달 프로세서|내부 오류가 발생했습니다.|  
|117|Error|시작/종료|보고서 서버|보고서 서버 데이터베이스 버전이 잘못되었습니다.|  
|118|Warning|로깅|보고서 서버<br /><br /> 웹 포털|추적 로그가 올바른 디렉터리 위치에 없습니다. 새 추적 로그가 기본 디렉터리에 만들어집니다. 자세한 내용은 [Report Server Service Trace Log](../../reporting-services/report-server/report-server-service-trace-log.md)을 참조하세요.|  
|119|Error|활성화|보고서 서버<br /><br /> 일정 예약 및 배달 프로세서|*\<Source>* 에 보고서 서버 데이터베이스 콘텐츠에 대한 액세스 권한이 부여되지 않았습니다.|  
|120|Error|활성화|보고서 서버|대칭 키를 해독할 수 없습니다. 서비스가 실행되는 계정이 변경된 것 같습니다. 자세한 내용은 [암호화 키 구성 및 관리&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-manage-encryption-keys.md)를 참조하세요.|  
|121|Error|시작/종료|보고서 서버|RPC(원격 프로시저 호출) 서비스를 시작하지 못했습니다.|  
|122|Warning|배달|일정 예약 및 배달 프로세서|일정 예약 및 배달 프로세서에서 전자 메일 배달에 사용되는 SMTP 서버에 연결할 수 없습니다. SMTP 서버 연결에 대한 자세한 내용은 [메일 설정 - Reporting Services 기본 모드(구성 관리자)](../install-windows/e-mail-settings-reporting-services-native-mode-configuration-manager.md)를 참조하세요.|  
|123|Warning|로깅|보고서 서버<br /><br /> 웹 포털|보고서 서버에서 추적 로그에 쓰지 못했습니다. 추적 로그에 대한 자세한 내용은 [보고서 서버 서비스 추적 로그](../../reporting-services/report-server/report-server-service-trace-log.md)를 참조하세요.|  
|124|정보|활성화|보고서 서버|보고서 서버 서비스가 활성화되었습니다. 자세한 내용은 [보고서 서버 초기화&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server.md)를 참조하세요.|  
|125|정보|활성화|보고서 서버|데이터 암호화에 사용된 키를 추출했습니다. 키에 대한 자세한 내용은 [암호화 키 구성 및 관리&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-manage-encryption-keys.md)를 참조하세요.|  
|126|정보|활성화|보고서 서버|데이터 암호화에 사용된 키를 적용했습니다. 키에 대한 자세한 내용은 [암호화 키 구성 및 관리&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-manage-encryption-keys.md)를 참조하세요.|  
|127|정보|활성화|보고서 서버|암호화된 내용을 보고서 서버 데이터베이스에서 제거했습니다. 복구할 수 없는 암호화된 데이터를 삭제하는 방법에 대한 자세한 내용은 [암호화 키 구성 및 관리&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/ssrs-encryption-keys-manage-encryption-keys.md)를 참조하세요.|  
|128|Error|활성화|보고서 서버|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 구성 요소는 함께 사용할 수 없습니다.|  
|129|Error|관리|보고서 서버<br /><br /> 일정 예약 및 배달 프로세서|암호화된 구성 파일 설정을 해독할 수 없습니다.|  
|130|Error|관리|보고서 서버<br /><br /> 일정 예약 및 배달 프로세서|*\<Source>* 에서 구성 파일을 찾을 수 없습니다. 보고서 서버에 구성 파일이 필요합니다.|  
|131|Error|보안|보고서 서버<br /><br /> 일정 예약 및 배달 프로세서|암호화된 사용자 데이터 값을 해독할 수 없습니다.|  
|132|Error|보안|보고서 서버|사용자 데이터를 암호화하는 동안 오류가 발생했습니다. 값을 저장할 수 없습니다.|  
|133|Error|관리|보고서 서버<br /><br /> 웹 포털<br /><br /> 일정 예약 및 배달 프로세서|구성 파일을 로드하지 못했습니다. XML이 잘못된 경우 이러한 오류가 발생할 수 있습니다.|  
|134|Error|관리|보고서 서버|보고서 서버에서 구성 파일의 설정 값을 암호화하지 못했습니다.|  
  
## <a name="see-also"></a>참고 항목

 [Reporting Services 구독 모니터링](../../reporting-services/subscriptions/monitor-reporting-services-subscriptions.md)  
 [Reporting Services 로그 파일 및 원본](../../reporting-services/report-server/reporting-services-log-files-and-sources.md)
