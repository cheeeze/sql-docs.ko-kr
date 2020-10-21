---
title: 페이지를 매긴 보고서의 데이터 원본 속성 구성 - SSRS | Microsoft Docs
description: Reporting Services에서 페이지를 매긴 보고서용 데이터 원본 속성을 구성하는 방법을 알아봅니다. 또한 속성을 설정하여 데이터 원본 연결 정보를 변경합니다.
ms.date: 05/24/2018
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-data
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
ms.assetid: 27af5195-c845-40e0-9a9c-efe569424022
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3dc1e561835cf3e44f48ed1ef77fe22d289a3ec6
ms.sourcegitcommit: fe59f8dc27fd633f5dfce54519d6f5dcea577f56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91935026"
---
# <a name="configure-data-source-properties-for-a-paginated-report"></a>페이지를 매긴 보고서의 데이터 원본 속성 구성
  페이지를 매긴 보고서를 실행하면 보고서 서버가 속성 정보를 검색하여 데이터 원본에 연결하는 방식을 결정합니다. 데이터 원본 유형, 연결 문자열 및 자격 증명 정보가 게시된 보고서의 데이터 원본 속성 페이지에 지정되어 있습니다. 데이터 원본 연결 정보가 보고서 생성 시 지정된 원래 값과 달라지도록 속성을 설정할 수 있습니다.  
  
 사용할 연결 정보를 지정하는 미리 정의된 공유 데이터 원본이 있는 경우 이 공유 데이터 원본을 대신 지정할 수도 있습니다. 공유 데이터 원본을 사용하려면 보고서의 데이터 원본 속성 페이지에서 **공유 데이터 원본** 을 클릭합니다.  
  
## <a name="to-configure-an-embedded-data-source"></a>포함된 데이터 원본을 구성하려면  
  
1.  웹 포털에서 보고서별 데이터 원본을 구성할 보고서로 이동합니다.  
  
3.  오른쪽 위 모서리 > **관리**에서 줄임표( **...** )를 선택합니다.  
  
4.  **데이터 원본** 탭을 클릭합니다. 보고서의 데이터 원본 속성 페이지가 열립니다.  
  
5.  보고서 내의 데이터 원본 연결 정보를 지정하려면 **사용자 지정 데이터 원본** 을 클릭합니다.  
  
6.  **연결 형식** 목록에서 데이터 원본의 데이터를 처리하는 데 사용할 데이터 처리 확장 프로그램을 지정합니다.  
  
7.  **연결 문자열**에는 보고서 서버가 데이터 원본에 연결하는 데 사용하는 연결 문자열을 지정합니다. 연결 문자열에는 자격 증명을 지정하지 않는 것이 좋습니다.  
  
     다음 예에서는 로컬 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] 데이터베이스에 연결하기 위한 연결 문자열을 보여 줍니다.  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  **연결 방법**에서 보고서를 실행할 때 자격 증명을 가져오는 방법을 지정합니다.  
  
    -   로그온 이름과 암호를 입력하라는 메시지를 표시하려면 **보고서를 실행하는 사용자가 제공한 자격 증명**을 클릭합니다.  
  
    -   자동화된 보고서 기록 생성과 같은 예약된 작업이나 구독을 지원하는 보고서에 데이터 원본을 사용하려면 **보고서 서버에 안전하게 저장된 자격 증명**을 클릭합니다.  
  
    -   보고서 서버가 보고서에 액세스하는 사용자의 자격 증명을 외부 데이터 원본을 호스팅하는 서버에 전달하도록 하려면 **Windows 통합 보안**을 클릭합니다. 이 경우 사용자 이름이나 암호를 입력하라는 메시지가 표시되지 않습니다.  
  
    -   데이터 원본이 파일 시스템에서 액세스되는 XML 파일인 경우와 같이 데이터 원본이 자격 증명을 사용하지 않는 경우 **자격 증명 필요 없음**을 클릭합니다. 이 자격 증명 유형은 데이터 원본에 대해 유효한 경우에만 지정해야 합니다. 인증이 필요한 데이터 원본에 대해 이 옵션을 선택하면 연결이 실패합니다. 이 옵션을 선택할 때는 사용자 자격 증명을 사용할 수 없는 경우 보고서 서버가 다른 컴퓨터에 연결하여 데이터나 파일을 검색할 수 있도록 허용하는 무인 실행 계정을 구성해야 합니다.  
  
 자격 증명 구성 방법에 대한 자세한 내용은 [보고서 데이터 원본에 대한 자격 증명 및 연결 정보 지정](../../reporting-services/report-data/specify-credential-and-connection-information-for-report-data-sources.md)을 참조하세요. 무인 실행 계정에 대한 자세한 내용은 [무인 실행 계정 구성&#40;보고서 서버 구성 관리자&#41;](../../reporting-services/install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
[공유 데이터 원본 만들기, 수정 및 삭제&#40;SSRS&#41;](../../reporting-services/report-data/create-modify-and-delete-shared-data-sources-ssrs.md)   
[보고서 데이터 원본 관리](../../reporting-services/report-data/manage-report-data-sources.md)
  
