---
description: 예약 키워드 제한 사항
title: 예약어 제한 사항 | Microsoft Docs
ms.custom: ''
ms.date: 05/01/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC desktop database drivers [ODBC]
- desktop database drivers [ODBC]
ms.assetid: ed42f083-c9e8-4ee4-9d64-d879bf955c78
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 15033816b953df764126853ada353452f00650d6
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92196177"
---
# <a name="reserved-keyword-limitations"></a>예약 키워드 제한 사항

SQL 테이블 또는 관련 개체에서 ODBC 예약 키워드를 식별자로 사용 하지 마십시오. 이름으로 예약 된 키워드를 사용 해야 하는 경우를 대비 하 여 식별자를 *backtick* (') 쌍으로 묶어야 합니다. *억음* 의 또 다른 이름은 *back 따옴표*입니다.

예약 키워드 제한은 예약 된 키워드의 모든 줄임 형식에도 적용 됩니다.

ODBC 예약 키워드 목록은 다음 위치에서 제공 됩니다.

- [ODBC 예약 키워드](../reference/appendixes/reserved-keywords.md)입니다.

- *ODBC 프로그래머 참조 가이드*에서 [부록 C: SQL 문법](../reference/appendixes/appendix-c-sql-grammar.md)을 참조 하세요.