---
description: 오류 메시지 전송 태스크
title: 오류 메시지 전송 태스크 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.transfererrormessagestask.f1
- sql13.dts.designer.transfererrormessagestask.general.f1
- sql13.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages task [Integration Services]
ms.assetid: da702289-035a-4d14-bd74-04461fbfee1b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa0bf307931b25b72a56e069e9f1c45b9e6c8b5d
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92192784"
---
# <a name="transfer-error-messages-task"></a>오류 메시지 전송 태스크

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  오류 메시지 전송 태스크에서는 하나 이상의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 사용자 정의 오류 메시지를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스 간에 전송합니다. 사용자 정의 메시지는 50000보다 크거나 같은 식별자를 가진 메시지입니다. 50000보다 작은 식별자를 가진 메시지는 시스템 오류 메시지이며 오류 메시지 전송 태스크를 사용하여 전송할 수 없습니다.  
  
 모든 오류 메시지를 전송하거나 지정한 오류 메시지만 전송하도록 오류 메시지 전송 태스크를 구성할 수 있습니다. 사용자 정의 오류 메시지는 여러 다른 언어로 제공될 수 있으며 지정된 언어로만 메시지를 전송하도록 태스크를 구성할 수 있습니다. 다른 언어 버전의 메시지를 대상 서버로 전송하려면 해당 서버에 1033 코드 페이지를 사용하는 us_english 버전의 메시지가 있어야 합니다.  
  
 master 데이터베이스의 sysmessages 테이블에는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]에서 사용하는 시스템 및 사용자 정의된 모든 오류 메시지가 포함됩니다.  
  
 전송할 사용자 정의 메시지가 이미 대상에 있을 수 있습니다. 식별자 및 언어가 동일한 경우 오류 메시지는 중복 오류 메시지로 정의됩니다. 다음 방식으로 기존 오류 메시지를 처리하도록 오류 메시지 전송 태스크를 구성할 수 있습니다.  
  
-   기존 오류 메시지를 덮어씁니다.  
  
-   중복 메시지가 있는 경우 태스크가 실패합니다.  
  
-   중복 오류 메시지를 건너뜁니다.  
  
 오류 메시지 전송 태스크는 런타임에 한 개 또는 두 개의 SMO 연결 관리자를 사용하여 원본 및 대상 서버에 연결합니다. SMO 연결 관리자는 오류 메시지 전송 태스크와 별도로 구성된 후 오류 메시지 전송 태스크에서 참조됩니다. SMO 연결 관리자는 액세스할 서버 및 서버 액세스 시 사용할 인증 모드를 지정합니다. 자세한 내용은 [SMO Connection Manager](../../integration-services/connection-manager/smo-connection-manager.md)을 참조하세요.  
  
 오류 메시지 전송 태스크는 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 원본 및 대상을 지원합니다. 원본 또는 대상으로 사용하는 버전에 대한 제한은 없습니다.  
  
## <a name="events"></a>이벤트  
 이 태스크는 전송된 오류 메시지의 수를 보고하는 정보 이벤트를 발생시킵니다.  
  
 오류 메시지 전송 태스크는 오류 메시지를 전송하는 진행 과정은 보고하지 않으며 0% 및 100% 완료만 보고합니다.  
  
## <a name="execution-value"></a>실행 값  
 전송된 오류 메시지의 개수는 태스크의 **ExecutionValue** 속성에 정의된 실행 값으로 반환됩니다. 오류 메시지 전송 태스크의 **ExecValueVariable** 속성에 사용자 정의 변수를 할당하면 패키지 내의 다른 개체에서 오류 메시지 전송에 대한 정보를 사용할 수 있습니다. 자세한 내용은 [Integration Services&#40;SSIS&#41; 변수](../../integration-services/integration-services-ssis-variables.md) 및 [패키지에서 변수 사용](../integration-services-ssis-variables.md)을 참조하세요.  
  
## <a name="log-entries"></a>로그 항목  
 오류 메시지 전송 태스크에는 다음 사용자 지정 로그 항목이 포함됩니다.  
  
-   TransferErrorMessagesTaskStartTransferringObjects    이 로그 항목에서는 전송이 시작되었음을 보고합니다. 로그 항목에 시작 시간이 포함됩니다.  
  
-   TransferErrorMessagesTaskFinishedTransferringObjects   이 로그 항목에서는 전송이 완료되었음을 보고합니다. 로그 항목에 종료 시간이 포함됩니다.  
  
 이외에 **OnInformation** 이벤트의 로그 항목은 전송된 오류 메시지 수를 보고하며 **OnWarning event** 의 로그 항목은 덮어쓴 대상에 대한 각 오류 메시지에 대해 기록됩니다.  
  
## <a name="security-and-permissions"></a>보안 및 사용 권한  
 새 오류 메시지를 만들려면 패키지를 실행하는 사용자가 대상 서버의 sysadmin 또는 serveradmin 서버 역할의 멤버여야 합니다.  
  
## <a name="configuration-of-the-transfer-error-messages-task"></a>오류 메시지 전송 태스크 구성  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너를 사용하거나 프로그래밍 방식으로 속성을 설정할 수 있습니다.  
  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너에서 설정할 수 있는 속성에 대한 자세한 내용을 보려면 다음 항목을 클릭하십시오.  
  
-   [식 페이지](../../integration-services/expressions/expressions-page.md)  
  
 이러한 속성을 프로그래밍 방식으로 설정하는 방법을 보려면 다음 항목을 클릭하십시오.  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferErrorMessagesTask.TransferErrorMessagesTask>  
  
## <a name="related-tasks"></a>관련 작업  
 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 디자이너에서 이러한 속성을 설정하는 방법을 보려면 다음 항목을 클릭하십시오.  
  
-   [태스크 또는 컨테이너의 속성 설정](./add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
## <a name="transfer-error-messages-task-editor-general-page"></a>오류 메시지 전송 태스크 편집기(일반 페이지)
  **오류 메시지 전송 태스크 편집기** 대화 상자의 **일반** 페이지를 사용하여 오류 메시지 전송 태스크의 이름을 지정하고 해당 태스크를 설명할 수 있습니다. 오류 메시지 전송 태스크에서는 하나 이상의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 사용자 정의 오류 메시지를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]인스턴스 간에 전송합니다.   
  
### <a name="options"></a>옵션  
 **이름**  
 오류 메시지 전송 태스크에 사용할 고유 이름을 제공합니다. 이 이름은 태스크 아이콘에서 레이블로 사용됩니다.  
  
> [!NOTE]  
>  태스크 이름은 패키지 내에서 고유해야 합니다.  
  
 **설명**  
 오류 메시지 전송 태스크에 대한 설명을 입력합니다.  
  
## <a name="transfer-error-messages-task-editor-messages-page"></a>오류 메시지 전송 태스크 편집기(메시지 페이지)
  **오류 메시지 전송 태스크 편집기** 대화 상자의 **메시지** 페이지를 사용하여 하나 이상의 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 사용자 정의 오류 메시지를 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 의 한 인스턴스에서 다른 인스턴스로 복사하기 위한 속성을 지정할 수 있습니다. 
  
### <a name="options"></a>옵션  
 **SourceConnection**  
 목록에서 SMO 연결 관리자를 선택하거나, **\<New connection...>** 을 클릭하여 원본 서버에 대한 새 연결을 만듭니다.  
  
 **DestinationConnection**  
 목록에서 SMO 연결 관리자를 선택하거나, **\<New connection...>** 을 클릭하여 대상 서버에 대한 새 연결을 만듭니다.  
  
 **IfObjectExists**  
 이름이 동일한 오류 메시지가 이미 대상 서버에 있는 경우 기존 사용자 정의 오류 메시지를 덮어쓸지, 기존 메시지를 건너뛸지, 아니면 태스크가 실패하도록 할지를 선택합니다.  
  
 **TransferAllErrorMessages**  
 원본 서버에서 대상 서버로 모든 사용자 정의 메시지를 복사할지, 아니면 지정한 사용자 정의 메시지만 복사할지를 선택합니다.  
  
 이 속성의 옵션은 다음 표에 나열되어 있습니다.  
  
|값|Description|  
|-----------|-----------------|  
|**True**|모든 사용자 정의 메시지를 복사합니다.|  
|**False**|지정한 사용자 정의 메시지만 복사합니다.|  
  
 **ErrorMessagesList**  
 복사할 오류 메시지를 선택하려면 찾아보기 단추 **(…)** 를 클릭합니다.  
  
> [!NOTE]  
>  복사할 오류 메시지를 선택하려면 **SourceConnection** 을 지정해야 합니다.  
  
 **ErrorMessageLanguagesList**  
 사용자 정의 오류 메시지를 대상 서버로 복사할 언어를 선택하려면 찾아보기 단추 **(…)** 를 클릭합니다. 다른 언어 버전의 메시지를 대상 서버로 전송하려면 us_english(코드 페이지 1033) 버전의 메시지가 해당 서버에 있어야 합니다.  
  
> [!NOTE]  
>  복사할 오류 메시지를 선택하려면 **SourceConnection** 을 지정해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Integration Services 태스크](../../integration-services/control-flow/integration-services-tasks.md)   
 [제어 흐름](../../integration-services/control-flow/control-flow.md)  
  
