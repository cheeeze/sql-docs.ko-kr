---
description: DROP SEQUENCE(Transact-SQL)
title: DROP SEQUENCE(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- DROP SEQUENCE
- DROP_SEQUENCE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- DROP SEQUENCE statement
- sequence number object, dropping
ms.assetid: c25772d3-61af-4aa7-b58b-a6f67a793e3d
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 6a3f9e498ea8d3f81d05be782d7c15ecdfb87e38
ms.sourcegitcommit: 197a6ffb643f93592edf9e90b04810a18be61133
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "91379738"
---
# <a name="drop-sequence-transact-sql"></a>DROP SEQUENCE(Transact-SQL)
[!INCLUDE [SQL Server Azure SQL Database ](../../includes/applies-to-version/sql-asdb.md)]

  현재 데이터베이스에서 시퀀스 개체를 제거합니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```syntaxsql
DROP SEQUENCE [ IF EXISTS ] { database_name.schema_name.sequence_name | schema_name.sequence_name | sequence_name } [ ,...n ]  
 [ ; ]  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>인수
 *IF EXISTS*  
 **적용 대상**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] ~ [현재 버전](https://go.microsoft.com/fwlink/p/?LinkId=299658)).  
  
 이미 있는 경우에만 시퀀스를 조건부로 삭제합니다.  
  
 *database_name*  
 시퀀스 개체를 만든 데이터베이스의 이름입니다.  
  
 *schema_name*  
 시퀀스 개체가 속한 스키마의 이름입니다.  
  
 *sequence_name*  
 삭제할 시퀀스의 이름입니다. 형식은 **sysname**입니다.  
  
## <a name="remarks"></a>설명  
 시퀀스 개체는 번호를 생성한 후 이 번호와 관계를 유지하지 않으므로 생성된 번호가 사용 중인 경우에도 삭제할 수 있습니다.  
  
 시퀀스 개체는 스키마 바운드가 아니므로 저장 프로시저 또는 트리거에서 참조하는 동안 삭제할 수 있습니다. 시퀀스 개체가 테이블에서 기본값으로 참조되는 경우에는 삭제할 수 없습니다. 오류 메시지에 시퀀스를 참조하는 개체가 표시됩니다.  
  
 데이터베이스의 모든 시퀀스 개체를 표시하려면 다음 문을 실행합니다.  
  
```sql  
SELECT sch.name + '.' + seq.name AS [Sequence schema and name]   
    FROM sys.sequences AS seq  
    JOIN sys.schemas AS sch  
        ON seq.schema_id = sch.schema_id ;  
GO  
```  
  
## <a name="security"></a>보안  
  
### <a name="permissions"></a>사용 권한  
 스키마에 대한 ALTER 또는 CONTROL 권한이 필요합니다.  
  
### <a name="audit"></a>감사  
 **DROP SEQUENCE**를 감사하려면 **SCHEMA_OBJECT_CHANGE_GROUP**을 모니터링합니다.  
  
## <a name="examples"></a>예제  
 다음 예에서는 현재 데이터베이스에서 `CountBy1`이라는 시퀀스 개체를 제거합니다.  
  
```sql  
DROP SEQUENCE CountBy1 ;  
GO  
```  
  
## <a name="see-also"></a>참고 항목  
 [ALTER SEQUENCE&#40;Transact-SQL&#41;](../../t-sql/statements/alter-sequence-transact-sql.md)   
 [CREATE SEQUENCE&#40;Transact-SQL&#41;](../../t-sql/statements/create-sequence-transact-sql.md)   
 [NEXT VALUE FOR &#40;Transact-SQL&#41;](../../t-sql/functions/next-value-for-transact-sql.md)   
 [시퀀스 번호](../../relational-databases/sequence-numbers/sequence-numbers.md)  
  
  
