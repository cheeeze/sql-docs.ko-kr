---
description: 데이터 유효성 검사(Excel용 MDS 추가 기능)
title: 데이터 유효성 검사
ms.custom: microsoft-excel-add-in
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 71eda98f-01a4-4fff-8246-be3133782523
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b878dcc17cf5ea23b1c5eccca58cdab39cfb7524
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "92257895"
---
# <a name="validating-data-mds-add-in-for-excel"></a>데이터 유효성 검사(Excel용 MDS 추가 기능)

[!INCLUDE [SQL Server Windows Only - ASDBMI ](../../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]에서는 데이터를 게시할 때 두 가지 종류의 유효성 검사가 수행됩니다.  
  
-   정의되어 있는 모든 비즈니스 규칙이 데이터에 적용됩니다.  
  
-   허용되는 특성 값인지를 기준으로 데이터가 검사됩니다(예: 문자 수 또는 데이터 형식).  
  
 두 가지 경우 모두 유효한 데이터가 MDS 저장소에 게시됩니다. 유효하지 않은 데이터는 강조 표시되고 오류에 대한 자세한 정보가 상태 열에 표시될 수 있습니다.  
  
## <a name="when-validation-occurs"></a>유효성 검사가 수행되는 경우  
 에서 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] 유효성 검사는 새 데이터 나 변경 된 데이터를 게시할 때 또는 비즈니스 규칙을 수동으로 적용할 때 수행 됩니다.  
  
 비즈니스 규칙이 실패할 경우 데이터가 MDS 저장소에 게시됩니다. 입력 유효성 검사가 실패할 경우에는 데이터가 저장소에 게시되지 않습니다.  
  
## <a name="validation-statuses"></a>유효성 검사 상태  
 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]에서 유효성 검사 상태는 다음과 같습니다.  
  
 추가 상태에 대한 자세한 내용은 [유효성 검사 상태&#40;Master Data Services&#41;](../../master-data-services/validation-statuses-master-data-services.md)를 참조하세요.  
  
|상태|설명|  
|------------|-----------------|  
|유효성 검사 실패|행에 있는 하나 이상의 값이 MDS 관리자가 정의한 비즈니스 규칙에 대한 유효성 검사에 실패했습니다.|  
|유효성 검사 성공|행의 모든 값이 비즈니스 규칙에 대한 유효성 검사에 통과했습니다.|  
  
## <a name="input-statuses"></a>입력 상태  
 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]에서 입력 상태는 다음과 같습니다.  
  
|상태|설명|  
|------------|-----------------|  
|오류|행에 있는 하나 이상의 값이 길이 또는 데이터 형식 같은 시스템 요구 사항을 충족하지 않습니다. MDS 저장소에서 값이 업데이트되지 않습니다.|  
|새 행|행의 값이 아직 MDS 저장소에 게시되지 않았습니다.|  
|읽기 전용|로그인한 사용자에게 행에 있는 하나 이상의 값에 대한 읽기 전용 권한이 있으며 값을 업데이트할 수 없습니다.|  
|변경 안 됨|워크시트에서 행의 어떤 값도 변경되지 않았습니다. 저장소에서 값이 변경되지 않았다는 의미는 아닙니다. 시트의 최신 데이터를 가져오려면 **연결 및 로드** 그룹에서 **로드 또는 새로 고침**을 클릭합니다.<br /><br /> 이는 각 행의 기본 설정입니다.|  
  
## <a name="related-tasks"></a>관련 작업  
  
|태스크 설명|항목|  
|----------------------|-----------|  
|정의된 비즈니스 규칙을 통과하지 못한 값을 확인합니다.|[비즈니스 규칙 적용&#40;Excel용 MDS 추가 기능&#41;](../../master-data-services/microsoft-excel-add-in/apply-business-rules-mds-add-in-for-excel.md)|  
|유효성 검사 오류를 수정하고 멤버에 대해 수행된 모든 트랜잭션을 봅니다.|[멤버에 대한 모든 주석 또는 트랜잭션 보기&#40;Excel용 MDS 추가 기능&#41;](../../master-data-services/microsoft-excel-add-in/view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a>관련 내용  
  
-   [개요: Excel에서 데이터 가져오기&#40;Excel용 MDS 추가 기능&#41;](../../master-data-services/microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
