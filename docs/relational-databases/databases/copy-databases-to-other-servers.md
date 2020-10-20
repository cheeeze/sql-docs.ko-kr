---
title: 데이터베이스를 다른 서버로 복사 | Microsoft 문서
description: 테스트를 위해, 원격 분기 작업에 사용하기 위해, 또는 기타의 이유로 SQL Server 데이터베이스를 한 컴퓨터에서 다른 컴퓨터로 복사하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55560b212f692b19513d211a69f38efb80b75883
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92194398"
---
# <a name="copy-databases-to-other-servers"></a>데이터베이스를 다른 서버로 복사
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  데이터베이스를 한 컴퓨터에서 다른 컴퓨터로 복사하는 기능은 경우에 따라 유용하게 사용됩니다(예: 테스트, 일관성 검사, 소프트웨어 개발, 보고서 실행, 미러 데이터베이스 만들기 또는 원격 분기 작업에서 사용할 수 있도록 데이터베이스 설정 등).  
  
 다음과 같은 여러 방법으로 데이터베이스를 복사할 수 있습니다.  
  
-   데이터베이스 복사 마법사 사용  
  
     데이터베이스 복사 마법사를 사용하여 서버 간에 데이터베이스를 복사 또는 이동하거나 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 데이터베이스를 이후 버전으로 업그레이드할 수 있습니다. 자세한 내용은 [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md)을 참조하세요.  
  
-   데이터베이스 백업 복원  
  
     전체 데이터베이스를 복사하려면 BACKUP 및 RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] 문을 사용합니다. 일반적으로 데이터베이스의 전체 백업 복원은 여러 가지 이유로 데이터베이스를 한 컴퓨터에서 다른 컴퓨터로 복사하는 데 사용됩니다. 백업 및 복원을 사용하여 데이터베이스를 복사하는 방법은 [백업 및 복원으로 데이터베이스 복사](../../relational-databases/databases/copy-databases-with-backup-and-restore.md)를 참조하세요.  
  
    > [!NOTE]  
    >  데이터베이스 미러링에 사용할 미러 데이터베이스를 설정하려면 RESTORE DATABASE *<database_name>* WITH NORECOVERY를 사용하여 데이터베이스를 미러 서버로 복원해야 합니다. 자세한 내용은 [미러 데이터베이스의 미러링 준비&#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)을 사용합니다.  
  
-   스크립트 생성 마법사를 사용하여 데이터베이스 게시  
  
     스크립트 생성 마법사를 사용하여 데이터베이스를 로컬 컴퓨터에서 웹 호스팅 공급자로 전송할 수 있습니다. 자세한 내용은 [스크립트 생성 및 게시 마법사](../../ssms/scripting/generate-and-publish-scripts-wizard.md)를 참조하세요.  
  
