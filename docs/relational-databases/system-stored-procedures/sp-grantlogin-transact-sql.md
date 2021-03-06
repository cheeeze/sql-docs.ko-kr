---
description: sp_grantlogin(Transact-SQL)
title: sp_grantlogin (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_grantlogin_TSQL
- sp_grantlogin
dev_langs:
- TSQL
helpviewer_keywords:
- sp_grantlogin
ms.assetid: 0c873d99-c3bf-4eb1-948b-a46cb235ccd4
ms.author: vanto
author: VanMSFT
ms.openlocfilehash: ddca7a999c1095bc1f6da91e62bd675c736dd96b
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88447073"
---
# <a name="sp_grantlogin-transact-sql"></a>sp_grantlogin(Transact-SQL)

[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 로그인을 만듭니다.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] 대신 [CREATE LOGIN](../../t-sql/statements/create-login-transact-sql.md) 을 사용 해야 합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
sp_grantlogin [@loginame=] 'login'  
```  
  
## <a name="arguments"></a>인수  
`[ @loginame = ] 'login'` Windows 사용자 또는 그룹의 이름입니다. Windows 사용자 또는 그룹은 *도메인* \\ *사용자*(예: **: london\joeb)**)의 windows 도메인 이름으로 한정 되어야 합니다. *login* 은 **sysname**이며 기본값은 없습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 0(성공) 또는 1(실패)  
  
## <a name="remarks"></a>설명  
 **sp_grantlogin** 는 추가 옵션을 지 원하는 CREATE LOGIN을 호출 합니다. SQL Server 로그인을 만드는 방법에 대 한 자세한 내용은 [CREATE LOGIN &#40;transact-sql](../../t-sql/statements/create-login-transact-sql.md) 을 참조 하세요&#41;  
  
 사용자 정의 트랜잭션 내에서는 **sp_grantlogin** 을 실행할 수 없습니다.  
  
## <a name="permissions"></a>사용 권한  
 서버에 대한 ALTER ANY LOGIN 권한이 필요합니다.  
  
## <a name="examples"></a>예제  
 다음 예에서는 `CREATE LOGIN` 를 사용 하 여 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Windows 사용자에 대 한 로그인을 만듭니다 `Corporate\BobJ.` .이는 선호 되는 방법입니다.  
  
```sql
CREATE LOGIN [Corporate\BobJ] FROM WINDOWS;  
GO  
```  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;보안 저장 프로시저 ](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [CREATE LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)   
 [시스템 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
