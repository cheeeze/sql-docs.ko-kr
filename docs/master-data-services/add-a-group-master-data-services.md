---
description: 그룹 추가(Master Data Services)
title: 그룹 추가
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- groups [Master Data Services], adding
- adding groups [Master Data Services]
ms.assetid: c7a88381-3b2c-4af7-9cf7-3a930c1abdee
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2a5693bfcc62beaad8f5423d6e5d3dbee5cd7fb7
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88491520"
---
# <a name="add-a-group-master-data-services"></a>그룹 추가(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  **의** 그룹 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 목록에 그룹을 추가하여 웹 애플리케이션에 사용 권한을 할당하는 프로세스를 시작합니다. 그룹의 사용자가 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에 액세스할 수 있게 하려면 하나 이상의 기능 영역과 모델 개체에 그룹 권한을 부여해야 합니다.  
  
## <a name="prerequisites"></a>사전 요구 사항  
 이 절차를 수행하려면  
  
-   **사용자 및 그룹 권한** 기능 영역에 액세스할 수 있는 권한이 있어야 합니다.  
  
### <a name="to-add-a-group"></a>그룹을 추가하려면  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에서 **사용자 및 그룹 권한**을 클릭합니다.  
  
2.  **사용자** 페이지의 메뉴 모음에서 **그룹 관리**를 클릭합니다.  
  
3.  **그룹 추가**를 클릭합니다.  
  
4.  *domain\group_name* 또는 *computer\group_name*과 같이 Active Directory 도메인 이름이나 서버 컴퓨터 이름과 그룹 이름을 입력합니다.  
  
5.  또는 **이름 확인**을 클릭합니다.  
  
6.  **확인**을 클릭합니다.  
  
    > [!NOTE]  
    >  사용자가 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에 처음으로 액세스하면 사용자의 이름이 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 사용자 목록에 추가됩니다.  
  
## <a name="next-steps"></a>다음 단계  
  
-   [기능 영역 권한 할당&#40;Master Data Services&#41;](../master-data-services/assign-functional-area-permissions-master-data-services.md)  
  
## <a name="see-also"></a>참고 항목  
 [보안&#40;Master Data Services&#41;](../master-data-services/security-master-data-services.md)  
  
  
