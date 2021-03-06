---
description: SQLColAttributes(Access 드라이버)
title: SQLColAttributes (Access 드라이버) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLColAttribute function [ODBC], Access Driver
- Access driver [ODBC], SQLColAttributes
ms.assetid: adb6f81d-e8c7-4748-9b1d-f7a053788bbc
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d9758bb5c473971d3ed9acea52559da0a4aac67d
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88412279"
---
# <a name="sqlcolattributes-access-driver"></a>SQLColAttributes(Access 드라이버)
> [!NOTE]  
>  이 항목에서는 드라이버 관련 정보에 대 한 액세스를 제공 합니다. 이 함수에 대 한 일반 정보는 [ODBC API 참조](../../odbc/reference/syntax/odbc-api-reference.md)에서 적절 한 항목을 참조 하세요.  
  
|attribute|주석|  
|---------------|--------------|  
|SQL_COLUMN_DISPLAY_SIZE|가 중 데이터의 경우에는 열의 최대 길이가 열 시간 2의 최대 길이가 아니라 열의 최대 길이를 SQL_COLUMN_DISPLAY_SIZE 합니다.|  
|SQL_OWNER_NAME|소유자 이름이 지원 되지 않으므로이 열에 빈 문자열 ("")이 반환 됩니다.|  
|SQL_QUALIFIER_NAME|데이터베이스 파일에 대 한 경로가 반환 됩니다.|  
|SQL_COLUMN_SEARCHABLE|을 사용할 SQL_UNSEARCHABLE 수 없습니다.<br /><br /> 고정 길이 및 가변 길이 이진 및 문자 데이터 형식은 WVARBINARY 및 WVARCHAR가이 아닌 경우에도 검색할 수 있습니다.|  
  
> [!NOTE]  
>  위의는 **Sqlcolattributes**에서 반환 된 특성의 전체 목록이 아닙니다.
