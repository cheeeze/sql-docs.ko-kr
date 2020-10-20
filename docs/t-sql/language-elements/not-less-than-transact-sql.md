---
description: '!&lt; (보다 작지 않음)(Transact-SQL)'
title: '!&lt; (보다 작지 않음)(Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- '!<'
- Not Less
- '!<_TSQL'
- Not Less Than
- Less Than
dev_langs:
- TSQL
helpviewer_keywords:
- '!< (not less than)'
- not less than operator (!<)
ms.assetid: ecbb598e-58a2-4b6c-90b4-3ad5bdfcae39
author: rothja
ms.author: jroth
ms.openlocfilehash: 328c7feba7e11a6ef59e12ac499ef8522cb9a7de
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92196804"
---
# <a name="lt-not-less-than-transact-sql"></a>!&lt; (보다 작지 않음)(Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  두 식을 비교합니다(비교 연산자). Null이 아닌 식을 비교하는 경우 왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 작지 않으면 결과는 TRUE이고 그렇지 않으면 결과는 FALSE입니다. 피연산자 중 하나 또는 둘 다가 NULL이면 [SET ANSI_NULLS&#40;Transact-SQL&#41;](../../t-sql/statements/set-ansi-nulls-transact-sql.md) 항목을 참조하세요.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```syntaxsql
expression !< expression  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>인수
 *expression*  
 유효한 [식](../../t-sql/language-elements/expressions-transact-sql.md)입니다. 두 식은 모두 암시적으로 변환 가능한 데이터 형식이어야 합니다. 변환은 [데이터 형식 우선 순위](../../t-sql/data-types/data-type-precedence-transact-sql.md) 규칙에 따라 달라집니다.  
  
## <a name="result-types"></a>결과 형식  
 **Boolean**  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식&#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [연산자&#40;Transact-SQL&#41;](../../t-sql/language-elements/operators-transact-sql.md)  
  
  
