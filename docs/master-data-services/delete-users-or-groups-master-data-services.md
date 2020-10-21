---
description: 사용자 또는 그룹 삭제(Master Data Services)
title: 사용자 또는 그룹 삭제
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 48ddbf53a44bf0d34abe725595bba255e6fa4fae
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "92258074"
---
# <a name="delete-users-or-groups-master-data-services"></a>사용자 또는 그룹 삭제(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  사용자나 그룹이 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에 액세스할 수 없게 하려면 해당 사용자나 그룹을 삭제합니다.  
  
 사용자와 그룹을 삭제할 때 다음 동작에 유의하십시오.  
  
-   [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에 대한 액세스 권한이 있는 그룹의 멤버인 사용자를 삭제하는 경우 Active Directory 또는 로컬 그룹에서 제거할 때까지는 해당 사용자가 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 에 액세스할 수 있습니다.  
  
-   그룹을 삭제하는 경우 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 에 액세스한 그룹의 모든 사용자를 삭제할 때까지 **사용자** 목록에 해당 사용자가 표시됩니다.  
  
-   보안에 대한 변경 내용은 20분 동안 MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] 에 전파되지 않습니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 절차를 수행하려면  
  
-   **사용자 및 그룹 권한** 기능 영역에 액세스할 수 있는 권한이 있어야 합니다.  
  
### <a name="to-delete-users-or-groups"></a>사용자나 그룹을 삭제하려면  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에서 **사용자 및 그룹 권한**을 클릭합니다.  
  
2.  사용자를 삭제하려면 **사용자** 페이지에 남아 있습니다. 그룹을 삭제하려면 메뉴 모음에서 **그룹 관리**를 클릭합니다.  
  
3.  표에서 삭제하려는 사용자나 그룹의 행을 선택합니다.  
  
4.  **선택한 사용자 삭제** 또는 **선택한 그룹 삭제**를 클릭합니다.  
  
5.  확인 대화 상자에서 **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [보안&#40;Master Data Services&#41;](../master-data-services/security-master-data-services.md)  
  
  
