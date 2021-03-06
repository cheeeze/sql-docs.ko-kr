---
description: ChangePassword 메서드(ADOX)
title: ChangePassword 메서드 (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _User25::raw_ChangePassword
- _User25::ChangePassword
helpviewer_keywords:
- ChangePassword method [ADOX]
ms.assetid: d187fbc6-5fac-4abb-803d-bf344dcf0302
author: rothja
ms.author: jroth
ms.openlocfilehash: e51037f9838e9aef279351c822e6c35ffb25f0fb
ms.sourcegitcommit: 18a98ea6a30d448aa6195e10ea2413be7e837e94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88985204"
---
# <a name="changepassword-method-adox"></a>ChangePassword 메서드(ADOX)
[사용자](./user-object-adox.md) 계정에 대 한 암호를 변경 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
User.ChangePassword OldPassword, NewPassword  
```  
  
#### <a name="parameters"></a>매개 변수  
 *OldPassword*  
 사용자의 기존 암호를 지정 하는 **문자열** 값입니다. 사용자에 게 현재 암호가 없으면 *oldpassword*에 빈 문자열 ("")을 사용 합니다.  
  
 *NewPassword*  
 새 암호를 지정 하는 **문자열** 값입니다.  
  
## <a name="remarks"></a>설명  
 보안상의 이유로 새 암호 외에도 이전 암호를 지정 해야 합니다.  
  
 공급자가 트러스티 속성의 관리를 지원 하지 않는 경우 오류가 발생 합니다.  
  
## <a name="applies-to"></a>적용 대상  
 [사용자 개체(ADOX)](./user-object-adox.md)  
  
## <a name="see-also"></a>참고 항목  
 [Groups 및 Users Append, ChangePassword 메서드 예제(VB)](./groups-and-users-append-changepassword-methods-example-vb.md)