---
description: MSSQLSERVER_18752
title: MSSQLSERVER_18752 | Microsoft 문서
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 18752 (Database Engine error)
ms.assetid: 234c58d8-7a1e-4b07-a64b-32a311527980
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 50327e76c43f67dbed77e45457481e2b032f32ef
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88499512"
---
# <a name="mssqlserver_18752"></a>MSSQLSERVER_18752
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>세부 정보  
  
| attribute | 값 |  
| :-------- | :---- |  
|제품 이름|SQL Server|  
|이벤트 ID|18752|  
|이벤트 원본|MSSQLSERVER|  
|구성 요소|SQLEngine|  
|심볼 이름|REPL_INUSE|  
|메시지 텍스트|한 번에 하나의 로그 판독기 에이전트 또는 로그 관련 프로시저(sp_repldone, sp_replcmds 및 sp_replshowcmds)만 데이터베이스에 연결할 수 있습니다. 로그 관련 프로시저를 실행한 경우 로그 판독기 에이전트를 시작하거나 다른 로그 관련 프로시저를 실행하기 전에 프로시저가 실행된 연결을 삭제하거나 해당 연결에 대해 sp_replflush를 실행하십시오.|  
  
## <a name="explanation"></a>설명  
한 번에 하나의 로그 판독기 에이전트 또는 로그 관련 프로시저만 데이터베이스에 연결할 수 있습니다.  
  
## <a name="user-action"></a>사용자 동작  
동일한 게시 데이터베이스에 대해 다른 로그 판독기가 실행되고 있지 않은지, 그리고 다른 활성 연결에서 연결을 끊거나 sp_replflush를 실행하지 않고 먼저 sp_replcmds/sp_repltrans/sp_repldone을 실행하지 않았는지 확인합니다.  
  
