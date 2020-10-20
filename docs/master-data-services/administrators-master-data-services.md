---
title: 관리자
description: 모델 관리자, 엔터티 관리자 및 슈퍼 사용자 MDS(Master Data Services)의 관리자 유형에 대해 알아봅니다.
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], about administrators
- administrators [Master Data Services]
- models [Master Data Services], administrators
ms.assetid: d330aa4e-6ade-4b09-b376-1b15d6c78f7d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7e65024ac3673e6579e614ad64931ab772b599f3
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92193669"
---
# <a name="administrators-master-data-services"></a>관리자(Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  이 문서에서는 모델 관리자, 엔터티 관리자, 슈퍼 사용자 등 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]의 관리자 유형을 설명합니다.  
  
## <a name="model-administrators"></a>모델 관리자  
 에서 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 모델 관리자는 **모델 개체** 탭의 최상위 모델 개체에 대 한 **관리자** 권한이 할당 된 사용자입니다. 사용자에 게 특정 모델에 대 한 관리자 권한이 있는 경우 모델의 자식 개체에 대 한 다른 모든 사용 권한 (모델 개체 및 멤버 권한)은 모델 **관리자** 권한으로 있으면 효과적으로 무시 됩니다.  
  
-   **탐색기** 기능 영역에 대한 액세스 권한을 가진 사용자는 이 영역에서 모든 마스터 데이터를 추가하고, 삭제하고, 업데이트할 수 있습니다.  
  
-   다른 기능 영역에 대한 액세스 권한을 가진 사용자는 해당 영역에서 사용할 수 있는 모든 관리 태스크를 수행할 수 있습니다.  
  
 각 모델은 여러 관리자를 가질 수 있습니다. 각 사용자는 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 배포에서 한 개, 여러 개 또는 모든 모델에 대한 모델 관리자일 수 있습니다.  
  
 사용자는 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] 에서 또는 프로그래밍 방식으로 모델 관리자로 구성될 수 있습니다. 자세한 내용은 [모델 관리자 만들기&#40;Master Data Services&#41;](../master-data-services/create-a-model-administrator-master-data-services.md)를 참조하세요.  
  
## <a name="entity-administrators"></a>엔터티 관리자  
 에서 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 엔터티 관리자는 모델 개체 탭의 엔터티 개체에 대 한 관리자 권한이 할당 된 사용자입니다. 사용자에 게 엔터티에 대 한 관리자 권한이 있는 경우 엔터티의 자식 개체에 대 한 다른 모든 사용 권한 (모델 개체 및 멤버 권한)은 관리자 권한으로 대체 되며 무시 됩니다.  
  
-   **탐색기** 기능 영역에 대한 액세스 권한을 가진 사용자는 이 영역에서 모든 마스터 데이터를 추가하고, 삭제하고, 업데이트할 수 있습니다.  
  
-   엔터티 변경 시 관리자의 승인이 필요한 경우 엔터티 관리자는 변경 집합을 검토한 다음 승인하거나 거부할 수 있습니다.  
  
 각 엔터티에 관리자가 여러 명 있을 수 있습니다. 각 사용자는 엔터티 하나, 여러 개 또는 모든 엔터티의 관리자일 수 있습니다.  
  
 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 에서 또는 프로그래밍 방식으로 사용자를 엔터티 관리자로 구성할 수 있습니다. 자세한 내용은 [엔터티 관리자 만들기&#40;Master Data Services&#41;](../master-data-services/create-an-entity-administrator-master-data-services.md)를 참조하세요.  
  
## <a name="master-data-services-super-user"></a>Master Data Services 슈퍼 사용자  
 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]에서 슈퍼 사용자 기능 영역에 사용자 권한을 할당할 수 있습니다. 슈퍼 사용자 기능 영역에 대한 권한이 있는 사용자는 실제로 모든 모델에 대한 관리자 권한과 다른 모든 기능 영역에 대한 권한을 갖습니다. 기능 영역의 사용 권한에 대한 자세한 내용은 [기능 영역 권한&#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md)을 참조하세요.  
  
 기본 슈퍼 사용자는 [데이터베이스 만들기 마법사&#40;Master Data Services 구성 관리자&#41;](../master-data-services/create-database-wizard-master-data-services-configuration-manager.md)를 사용하여 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]데이터베이스를 만들 때 **관리자 계정**에 대해 지정됩니다.  
  
 슈퍼 사용자는 다음을 수행할 수 있습니다.  
  
-   모든 기능 영역에 액세스합니다.  
  
-   **탐색기** 기능 영역에서 모든 모델의 모든 마스터 데이터를 추가, 삭제 및 업데이트합니다.  
  
 여러 사용자 및/또는 사용자 그룹에 슈퍼 사용자 권한을 할당할 수 있습니다.  
  
## <a name="comparing-administrator-types"></a>관리자 유형 비교  
  
|관리자 유형|Description|  
|------------------------|-----------------|  
|[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 슈퍼 사용자|[!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]에서 할당된 사용 권한은 관리자의 액세스 권한 아무런 영향을 주지 않습니다.<br /><br /> 명시적으로 할당된 기능 영역 권한 또는 그룹에서 상속된 권한에 따라 슈퍼 사용자로 지정될 수 있습니다.<br /><br /> 모든 모델에 대한 모든 권한이 자동으로 부여됩니다.<br /><br /> 모든 기능 영역에 대한 액세스 권한을 자동으로 가집니다.|  
|모델 관리자|명시적으로 할당된 관리 권한 또는 그룹에서 상속된 사용 권한에 따라 모델 관리자로 지정될 수 있습니다.<br /><br /> 액세스 권한이 부여된 기능 영역에 대해서만 액세스 권한을 가집니다.<br /><br /> 특정 모델의 모든 개체 및 멤버에 대한 모든 권한이 자동으로 부여됩니다.|  
|엔터티 관리자|명시적으로 할당된 관리자 권한 또는 그룹에서 상속된 사용 권한에 따라 엔터티 관리자로 지정될 수 있습니다.<br /><br /> 액세스 권한이 부여된 기능 영역에 대해서만 액세스 권한을 가집니다.<br /><br /> 특정 엔터티의 모든 개체 및 멤버에 대한 모든 권한이 자동으로 부여됩니다.<br /><br /> 엔터티 변경 시 승인이 필요한 경우 보류 중인 변경 집합을 승인할 수 있습니다.|  
  
## <a name="external-resources"></a>외부 리소스  
 msdn.com의 블로그 게시물 [향상된 보안 기능](/archive/blogs/e7/improvements-to-autoplay)  
  
## <a name="see-also"></a>참고 항목  
 [모델 관리자 &#40;MDS(Master Data Services)를 만듭니다&#41;](../master-data-services/create-a-model-administrator-master-data-services.md)   
 [MDS(Master Data Services) 데이터베이스 만들기](../master-data-services/install-windows/create-a-master-data-services-database.md)   
 [알림&#40;Master Data Services&#41;](../master-data-services/notifications-master-data-services.md)  
  
