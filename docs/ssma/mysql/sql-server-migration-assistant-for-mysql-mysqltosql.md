---
title: MySQL에 대 한 SQL Server Migration Assistant (MySQLToSQL) | Microsoft Docs
description: MySQL 용 SSMA에 대해 알아보고 MySQL 데이터베이스를 SQL Server 또는 Azure SQL Database로 마이그레이션하기 위한 단계별 지침을 따르세요.
ms.prod: sql
ms.custom: ''
ms.date: 10/10/2019
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 2793bc33-38d3-46ed-8277-b8580cf78ced
author: nahk-ivanov
ms.author: alexiva
manager: alexiva
ms.openlocfilehash: 294c91e0d1fa62c548bc88c834e292ab34ec0015
ms.sourcegitcommit: e8f6c51d4702c0046aec1394109bc0503ca182f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87935182"
---
# <a name="sql-server-migration-assistant-for-mysql-mysqltosql"></a>MySQL에 대 한 SQL Server Migration Assistant (MySQLToSQL)

[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]MySQL 용 SSMA (Migration Assistant)는 MySQL 데이터베이스를 [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2012, [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2014, [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016, [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2017 (windows 및 linux의 경우), [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] windows 및 linux의 경우 2019 또는 Azure [!INCLUDE[msCoName](../../includes/msconame_md.md)] Database로 마이그레이션하기 위한 도구입니다. MySQL 용 SSMA는 MySQL 데이터베이스 개체를 SQL Server database 개체로 변환 하 고,에서 이러한 개체를 만든 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 다음, mysql에서로 데이터를 마이그레이션합니다 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
이 문서에서는 MySQL 용 SSMA를 소개 하 고 MySQL 데이터베이스를로 마이그레이션하는 방법에 대 한 단계별 지침을 제공 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 합니다. 다음 표에서는 자세한 정보를 확인할 수 있는 문서를 보여 줍니다.  
  
## <a name="contents"></a>콘텐츠  
  
|섹션|Description|
|-----------|---------------|
|[MySQL용 SSMA의 새로운 기능](https://msdn.microsoft.com/1451a0b0-6713-4d0c-954f-ea3d8fce1d31)|MySQL 용 SSMA 버전의 새로운 기능|  
|[&#40;MySqlToSql&#41;에 대 한 MySQL 용 SSMA 설치](../../ssma/mysql/installing-ssma-for-mysql-mysqltosql.md)|SQL Server를 실행 하는 컴퓨터에 MySQL 용 SSMA 클라이언트 및 필수 구성 요소를 설치 하기 위한 필수 구성 요소 및 지침을 제공 하는 문서가 포함 되어 있습니다.|  
|[MySQL 용 SSMA를 시작 &#40;MySQLToSQL&#41;](../../ssma/mysql/getting-started-with-ssma-for-mysql-mysqltosql.md)|사용자 인터페이스, 프로젝트 및 구성 옵션을 소개 합니다.|  
|[MySQL 데이터베이스를 SQL Server-Azure SQL Database &#40;MySQLToSql&#41;로 마이그레이션](../../ssma/mysql/migrating-mysql-databases-to-sql-server-azure-sql-db-mysqltosql.md)|변환 프로세스에 대 한 개요와 프로세스의 각 단계에 대 한 자세한 정보를 제공 합니다.|  
|[MySQLToSQL&#41;&#40;사용자 인터페이스 참조](../../ssma/mysql/user-interface-reference-mysqltosql.md)|MySQL 용 SSMA 대화 상자에 대 한 설명서가 포함 되어 있습니다.|  
|[MySQL용 SSMA 콘솔 작업](working-with-ssma-for-mysql-console-mysqltosql.md)|SSMA 콘솔 응용 프로그램에 대 한 설명서가 포함 되어 있습니다.|  
|[MySQL 용 SSMA 지원 가져오기](https://go.microsoft.com/fwlink/?LinkID=708538&clcid=0x409)|추가 지원을 받는 방법에 대 한 정보를 제공 합니다.|  
