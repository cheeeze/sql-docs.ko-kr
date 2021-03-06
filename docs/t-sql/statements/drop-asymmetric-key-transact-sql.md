---
description: DROP ASYMMETRIC KEY(Transact-SQL)
title: DROP ASYMMETRIC KEY(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- DROP ASYMMETRIC KEY
- DROP_ASYMMETRIC_KEY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- asymmetric keys [SQL Server], removing
- removing asymmetric keys
- encryption [SQL Server], asymmetric keys
- DROP ASYMMETRIC KEY statement
- dropping asymmetric keys
- deleting asymmetric keys
- cryptography [SQL Server], asymmetric keys
ms.assetid: bf94ac07-9b62-4318-b55b-1eed8f3a1ac6
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6ae0f615c3d59228618a7e04d637997b999cb123
ms.sourcegitcommit: 197a6ffb643f93592edf9e90b04810a18be61133
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "91380218"
---
# <a name="drop-asymmetric-key-transact-sql"></a>DROP ASYMMETRIC KEY(Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  데이터베이스에서 비대칭 키를 제거합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```syntaxsql
DROP ASYMMETRIC KEY key_name [ REMOVE PROVIDER KEY ]  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>인수
 *key_name*  
 데이터베이스에서 삭제할 비대칭 키의 이름입니다.  
  
 REMOVE PROVIDER KEY  
 EKM(Extensible Key Management) 디바이스에서 EKM 키를 제거합니다. 외부 키 관리에 대한 자세한 내용은 [확장 가능 키 관리 &#40;EKM&#41;](../../relational-databases/security/encryption/extensible-key-management-ekm.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 데이터베이스의 대칭 키를 암호화하는 데 사용되거나 사용자 또는 로그인이 매핑된 비대칭 키는 삭제할 수 없습니다. 이러한 비대칭 키를 삭제하려면 먼저 이 키에 매핑된 모든 사용자나 로그인을 삭제해야 합니다. 또한 비대칭 키로 암호화된 모든 대칭 키를 삭제하거나 변경해야 합니다. [ALTER SYMMETRIC KEY](../../t-sql/statements/alter-symmetric-key-transact-sql.md)의 DROP ENCRYPTION 옵션을 사용하여 비대칭 키를 사용한 암호화를 제거할 수 있습니다.  
  
 비대칭 키의 메타데이터는 [sys.asymmetric_keys](../../relational-databases/system-catalog-views/sys-asymmetric-keys-transact-sql.md) 카탈로그 뷰를 사용하여 액세스할 수 있습니다. 데이터베이스 내에서 키 자체를 직접 볼 수는 없습니다.  
  
 EKM(Extensible Key Management) 디바이스의 EKM 키에 비대칭 키를 매핑하고 REMOVE PROVIDER KEY 옵션을 지정하지 않으면 데이터베이스에서는 키가 삭제되지만 디바이스에서는 삭제되지 않으며 경고가 발생합니다.  
  
## <a name="permissions"></a>사용 권한  
 비대칭 키에 대한 CONTROL 권한이 필요합니다.  
  
## <a name="examples"></a>예제  
 다음 예에서는 `MirandaXAsymKey6` 데이터베이스에서 `AdventureWorks2012` 비대칭 키를 제거합니다.  
  
```sql  
USE AdventureWorks2012;  
DROP ASYMMETRIC KEY MirandaXAsymKey6;  
```  
  
## <a name="see-also"></a>참고 항목  
 [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-asymmetric-key-transact-sql.md)   
 [ALTER ASYMMETRIC KEY&#40;Transact-SQL&#41;](../../t-sql/statements/alter-asymmetric-key-transact-sql.md)   
 [암호화 계층](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [ALTER SYMMETRIC KEY&#40;Transact-SQL&#41;](../../t-sql/statements/alter-symmetric-key-transact-sql.md)  
  
  
