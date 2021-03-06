---
description: 데이터 원본 사용
title: 데이터 원본 사용 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data sources [ODBC], about data sources
ms.assetid: d5550619-22b2-4b16-bd08-fbabb6554c40
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 162f1c2bf8d75757ac2c29d60f675ac07ba8b00d
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88428836"
---
# <a name="using-data-sources"></a>데이터 원본 사용
데이터 원본은 일반적으로 최종 사용자 또는 기술 자가 *ODBC 관리자*라는 프로그램을 사용 하 여 만듭니다. ODBC 관리자는 사용자에 게 드라이버를 사용 하 라는 메시지를 표시 한 다음 해당 드라이버를 호출 합니다. 드라이버는 데이터 원본에 연결 하는 데 필요한 정보를 요청 하는 대화 상자를 표시 합니다. 사용자가 정보를 입력 하면 드라이버는 시스템에 해당 정보를 저장 합니다.  
  
 나중에 응용 프로그램은 드라이버 관리자를 호출 하 고 컴퓨터 데이터 원본의 이름 또는 파일 데이터 원본을 포함 하는 파일의 경로를 전달 합니다. 컴퓨터 데이터 원본 이름이 전달 되 면 드라이버 관리자는 시스템을 검색 하 여 데이터 원본에서 사용 하는 드라이버를 찾습니다. 그런 다음 드라이버를 로드 하 고 데이터 원본 이름을 전달 합니다. 드라이버는 데이터 원본 이름을 사용 하 여 데이터 원본에 연결 하는 데 필요한 정보를 찾습니다. 마지막으로 데이터 원본에 연결 합니다. 일반적으로 사용자에 게 일반적으로 저장 되지 않는 사용자 ID와 암호를 묻는 메시지를 표시 합니다.  
  
 파일 데이터 원본이 전달 되 면 드라이버 관리자가 파일을 열고 지정 된 드라이버를 로드 합니다. 파일에 연결 문자열도 포함 되어 있으면이를 드라이버에 전달 합니다. 연결 문자열의 정보를 사용 하 여 드라이버는 데이터 원본에 연결 합니다. 연결 문자열이 전달 되지 않은 경우 드라이버는 일반적으로 사용자에 게 필요한 정보를 묻는 메시지를 표시 합니다.
