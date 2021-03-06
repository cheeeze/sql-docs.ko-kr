---
description: sp_fulltext_semantic_unregister_language_statistics_db(Transact-SQL)
title: sp_fulltext_semantic_unregister_language_statistics_db (Transact-sql) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_fulltext_semantic_unregister_language_statistics_db_TSQL
- sp_fulltext_semantic_unregister_language_statistics_db
dev_langs:
- TSQL
helpviewer_keywords:
- sp_fulltext_semantic_unregister_language_statistics_db
ms.assetid: 1426ca4a-9a76-489e-98da-8f6d13ff9732
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 6db576de824f098911229409498527e1aaf9d3ad
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89543394"
---
# <a name="sp_fulltext_semantic_unregister_language_statistics_db-transact-sql"></a>sp_fulltext_semantic_unregister_language_statistics_db(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  현재 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에서 기존 의미 체계 언어 통계 데이터베이스의 등록을 취소하고 연결된 모든 메타데이터를 삭제합니다.  
  
 이 문은 데이터베이스를 분리하거나 파일 시스템에서 실제 데이터베이스 파일을 제거하지 않습니다. 데이터베이스의 등록을 취소한 후 실제 데이터베이스 파일을 분리 및 삭제할 수 있습니다.  
  
 ![항목 링크 아이콘](../../database-engine/configure-windows/media/topic-link.gif "항목 링크 아이콘") [Transact-SQL 구문 표기 규칙](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>구문  
  
```sql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
##  <a name="arguments"></a><a name="Arguments"></a> 인수  
 이 프로시저에는 인수가 필요하지 않습니다. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에는 하나의 의미 체계 언어 통계 데이터베이스만 있으므로 데이터베이스를 식별할 필요가 없습니다.  
  
## <a name="return-code-value"></a>반환 코드 값  
 **0** (성공) 또는 **1** (실패)  
  
## <a name="result-set"></a>결과 집합  
 없음  
  
## <a name="general-remarks"></a>일반적인 주의 사항  
 의미 체계 언어 통계 데이터베이스를 등록 취소하면 여기에 연결된 모든 메타데이터도 제거됩니다.  
  
 **sp_fulltext_semantic_unregister_language_statistics_db** 다음 단계를 수행 합니다.  
  
1.  현재 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 인스턴스에 대해 진행 중인 의미 체계 채우기가 없는지 확인합니다.  
  
2.  지정된 의미 체계 언어 통계 데이터베이스에 연결된 모든 메타데이터를 제거합니다.  

 자세한 내용은 [의미 체계 검색 설치 및 구성](../../relational-databases/search/install-and-configure-semantic-search.md)을 참조하세요.  
  
## <a name="metadata"></a>메타데이터  
 인스턴스에 설치 된 의미 체계 언어 통계 데이터베이스에 대 한 자세한 내용은 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [Fulltext_semantic_language_statistics_database &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql.md)카탈로그 뷰를 쿼리 합니다.  
  
## <a name="security"></a>보안  
  
### <a name="permissions"></a>사용 권한  
 CONTROL SERVER 권한이 필요합니다.  
  
## <a name="examples"></a>예제  
 다음 예에서는 **sp_fulltext_semantic_unregister_language_statistics_db**를 호출 하 여 의미 체계 언어 통계 데이터베이스를 등록 취소 하는 방법을 보여 줍니다.  
  
```sql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
## <a name="see-also"></a>참고 항목  
 [의미 체계 검색 설치 및 구성](../../relational-databases/search/install-and-configure-semantic-search.md)  
  
  
