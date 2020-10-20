---
description: 웹 구성 참조(Master Data Services)
title: 웹 구성 참조
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- web configuration file [Master Data Services]
ms.assetid: b8cc9a35-97ab-4fe0-ab4b-c07f13d9793a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7f4baf9f3ef626f5e2dcdc62092afaf1e586df33
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92196097"
---
# <a name="web-configuration-reference-master-data-services"></a>웹 구성 참조(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 에서는 IIS(인터넷 정보 서비스)가 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 웹 애플리케이션 및 웹 서비스를 호스트할 수 있도록 하는 구성 설정이 Web.config 파일에 포함됩니다. 이 Web.config 파일은 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 설치 경로의 WebApplication 폴더에 있습니다. 경로 및 사용 권한에 대한 자세한 내용은 [폴더 및 파일 사용 권한&#40;Master Data Services&#41;](../master-data-services/folder-and-file-permissions-master-data-services.md)을 참조하세요.  
  
## <a name="webconfig-elements"></a>Web.Config 요소  
 Web.config 파일에는 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] **\<masterDataServices>** 표준 IIS, .NET Framework, ASP.NET 및 WINDOWS COMMUNICATION FOUNDATION (WCF) 구성 요소 외에도 사용자 지정 요소인가 포함 되어 있습니다. 다음 표에서는 Web.config 파일에 포함된 요소에 대해 설명합니다.  
  
|구성 요소|Description|  
|---------------------------|-----------------|  
|**masterDataServices**|사용자 지정 요소. [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 웹 서비스를 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 데이터베이스에 연결합니다.|  
|**connectionStrings**|ASP.NET 요소. 자세한 내용은 MSDN Library에서 [connectionStrings 요소(ASP.NET 설정 스키마)](/previous-versions/dotnet/netframework-4.0/bf7sd233(v=vs.100)) 를 참조하세요.|  
|**system.web**|ASP.NET 요소. 자세한 내용은 MSDN Library에서 [system.web 요소(ASP.NET 설정 스키마)](/previous-versions/dotnet/netframework-4.0/dayb112d(v=vs.100)) 를 참조하세요.|  
|**모드로**|.NET Framework 요소. 자세한 내용은 MSDN Library의 [ \<startup> 요소](/dotnet/framework/configure-apps/file-schema/startup/startup-element) 를 참조 하세요.|  
|**런타임**|.NET Framework 요소. 자세한 내용은 MSDN Library의 [ \<runtime> 요소](/dotnet/framework/configure-apps/file-schema/runtime/runtime-element) 를 참조 하세요.|  
|**system.codedom**|.NET Framework 요소. 자세한 내용은 MSDN Library의 [ \<system.codedom> 요소](/dotnet/framework/configure-apps/file-schema/compiler/system-codedom-element) 를 참조 하세요.|  
|**system.web. 확장명**|ASP.NET 요소. 자세한 내용은 MSDN Library에서 [system.web.extensions 요소(ASP.NET 설정 스키마)](/previous-versions/dotnet/netframework-4.0/bb546044(v=vs.100)) 를 참조하세요.|  
|**system.webServer**|IIS 요소를 포함하는 섹션 그룹. 자세한 내용은 MSDN Library에서 [system.webServer 섹션 그룹 \[IIS 7 설정 스키마\]](/previous-versions/iis/settings-schema/ms689429(v=vs.90))을 참조하세요.|  
|**system.serviceModel**|WCF 요소. 자세한 내용은 [\<system.serviceModel>](/dotnet/framework/configure-apps/file-schema/wcf/system-servicemodel) MSDN 라이브러리의을 참조 하십시오.|  
|**system.diagnostics**|.NET Framework 요소. 자세한 내용은 MSDN Library의 [ \<system.diagnostics> 요소](/dotnet/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element) 를 참조 하세요.|  
|**appSettings**|ASP.NET 요소. 자세한 내용은 MSDN Library에서 [appSettings 요소(일반 설정 스키마)](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)) 를 참조하세요.|  
  
## <a name="masterdataservices-element"></a>masterDataServices 요소  
 **\<masterDataServices>** 요소는 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 웹 서비스를 데이터베이스에 연결 하는 데 사용 되는 사용자 지정 요소입니다 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .  
  
### <a name="syntax"></a>구문  
  
```  
<masterDataServices>  
   <instance virtualPath="path" siteName="name" connectionName="name" serviceName="name" />  
</masterDataServices>  
```  
  
### <a name="elements-and-attributes"></a>요소 및 특성  
  
|항목|Description|  
|----------|-----------------|  
|**instance**|자식 요소. 웹 서비스와 데이터베이스 연결 문자열에 대한 정보를 지정하는 특성을 포함합니다.|  
|**virtualPath**|특성. [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 웹 애플리케이션 및 서비스의 가상 경로를 지정합니다. 이는 **path** **\<application>** **\<site>** IIS ApplicationHost.config 파일의 요소 아래에 있는 요소의 path 특성에 해당 합니다.|  
|**siteName**|특성. [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 웹 애플리케이션과 서비스를 호스트하는 사이트의 이름을 지정합니다. 이는 **name** **\<site>** **\<sites>** IIS ApplicationHost.config 파일의 아래에 있는 요소의 name 특성에 해당 합니다.|  
|**connectionName**|특성. 사용할 연결 이름을 지정합니다. 이는 **name** **\<add>** **\<connectionStrings>** Web.config의 요소 아래에 있는 요소의 name 특성에 해당 합니다.|  
|**serviceName**|특성. 웹 서비스의 이름을 지정합니다. 이는 **name** **\<service>** **\<services>** Web.config의 요소 아래에 있는 요소의 name 특성에 해당 합니다.|  
  
### <a name="example"></a>예제  
 다음 예에서는 MDSDB를 통해 지정된 연결 문자열을 사용하는 /MDS 경로와 Contoso 사이트의 MDS1이라는 서비스를 보여 줍니다.  
  
```  
<masterDataServices>  
   <instance virtualPath="/MDS" siteName="Contoso" connectionName="MDSDB" serviceName="MDS1" />  
</masterDataServices>  
```  
  
