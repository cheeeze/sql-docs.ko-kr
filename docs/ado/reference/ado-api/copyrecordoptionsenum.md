---
description: CopyRecordOptionsEnum
title: CopyRecordOptionsEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CopyRecordOptionsEnum
helpviewer_keywords:
- CopyRecordOptionsEnum enumeration [ADO]
ms.assetid: 2fa4eec5-d50b-4fd3-8ae7-40af441ba12b
author: rothja
ms.author: jroth
ms.openlocfilehash: 1570b0baa22b6d08db9b47d99f4d1e01595622d6
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88974544"
---
# <a name="copyrecordoptionsenum"></a>CopyRecordOptionsEnum
[Copyrecord](./copyrecord-method-ado.md) 메서드의 동작을 지정 합니다.  
  
|상수|값|설명|  
|--------------|-----------|-----------------|  
|**adCopyAllowEmulation**|4|*대상이*다른 서버에 있거나 *원본*보다 다른 공급자가 서비스를 제공 하 여이 메서드가 실패 하는 경우 *원본* 공급자가 다운로드 및 업로드 작업을 사용 하 여 복사를 시뮬레이션 하려고 함을 나타냅니다. 다른 공급자 기능으로 인해 성능이 저하 되거나 데이터가 손실 될 수 있습니다.|  
|**adCopyNonRecursive**|2|현재 디렉터리를 복사 하지만 해당 하위 디렉터리는 대상에 복사 하지 않습니다. 복사 작업은 재귀적이 아닙니다.|  
|**adCopyOverWrite**|1|*대상이* 기존 파일이 나 디렉터리를 가리키는 경우 파일이 나 디렉터리를 덮어씁니다.|  
|**adCopyUnspecified**|-1|기본값 기본 복사 작업을 수행 합니다. 대상 파일 또는 디렉터리가 이미 있는 경우 작업이 실패 하 고 작업이 재귀적으로 복사 됩니다.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 동급  
 이러한 상수에는 ADO/WFC 해당 항목이 없습니다.  
  
## <a name="applies-to"></a>적용 대상  
 [CopyRecord 메서드(ADO)](./copyrecord-method-ado.md)