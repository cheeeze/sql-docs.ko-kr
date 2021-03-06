---
description: sp_validate_redirected_publisher(Transact-SQL)
title: sp_validate_redirected_publisher (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_validate_redirected_publisher
- sp_validate_redirected_publisher_TSQL
helpviewer_keywords:
- sp_validate_redirected_publisher
ms.assetid: 2b7fdbad-17e4-4442-b0b2-9b5e8f84b91d
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 42184546069fb5358fbdc8863998b7bda74f89a4
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89534764"
---
# <a name="sp_validate_redirected_publisher-transact-sql"></a>sp_validate_redirected_publisher(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  게시 데이터베이스의 현재 호스트가 복제를 지원할 수 있는지 확인합니다. 배포 데이터베이스에서 실행해야 합니다. 이 프로시저는 **sp_get_redirected_publisher**에 의해 호출 됩니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```  
  
      sp_validate_redirected_publisher   
    [ @original_publisher = ] 'original_publisher',  
    [ @publisher_db = ] 'database_name',   
    [ @redirected_publisher = ] 'new_publisher' output  
```  
  
## <a name="arguments"></a>인수  
`[ @original_publisher = ] 'original_publisher'`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]원래 데이터베이스를 게시 한 인스턴스의 이름입니다. *original_publisher* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @publisher_db = ] 'publisher_db'` 게시 되는 데이터베이스의 이름입니다. *publisher_db* 는 **sysname**이며 기본값은 없습니다.  
  
`[ @redirected_publisher = ] 'redirected_publisher'` 게시자/데이터베이스 쌍에 대해 **sp_redirect_publisher** 가 호출 될 때 지정 된 리디렉션 대상입니다. *redirected_publisher* 는 **sysname**이며 기본값은 없습니다.  
  
## <a name="return-code-values"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-sets"></a>결과 집합  
 없음  
  
## <a name="remarks"></a>설명  
 게시자 및 게시 데이터베이스에 대 한 항목이 없는 경우 **sp_validate_redirected_publisher** 는 출력 매개 변수 * \@ redirected_publisher*에 null을 반환 합니다. 항목이 있으면 성공한 경우와 실패한 경우 모두에 대해 해당 항목이 출력 매개 변수에 반환됩니다.  
  
 유효성 검사가 성공 하면 **sp_validate_redirected_publisher** 는 성공 표시를 반환 합니다.  
  
 유효성 검사에 실패한 경우에는 실패를 설명하는 오류가 발생합니다.  
  
## <a name="permissions"></a>사용 권한  
 호출자는 **sysadmin** 고정 서버 역할의 멤버 이거나 배포 데이터베이스에 대 한 **db_owner** 고정 데이터베이스 역할의 멤버 이거나 게시자 데이터베이스에 연결 된 정의 된 게시에 대 한 게시 액세스 목록의 멤버 여야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [복제 저장 프로시저&#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [Transact-sql&#41;sp_get_redirected_publisher &#40;](../../relational-databases/system-stored-procedures/sp-get-redirected-publisher-transact-sql.md)   
 [Transact-sql&#41;sp_redirect_publisher &#40;](../../relational-databases/system-stored-procedures/sp-redirect-publisher-transact-sql.md)   
 [Transact-sql&#41;sp_validate_replica_hosts_as_publishers &#40;](../../relational-databases/system-stored-procedures/sp-validate-replica-hosts-as-publishers-transact-sql.md)  
  
  
