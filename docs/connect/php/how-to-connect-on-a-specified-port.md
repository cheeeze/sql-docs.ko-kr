---
title: '방법: 지정된 포트에서 연결'
description: Microsoft SQLSRV 및 PDO_SQLSRV Drivers for PHP for SQL Server를 사용하여 특정 포트에 구성된 데이터베이스에 연결하는 방법을 알아봅니다.
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- connecting to the server, specifying a port
ms.assetid: 65a154d1-375c-439b-a653-7815c9d70ff3
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b55f12bbfe4bbe255af2d62c2ed0c5ab3f968e98
ms.sourcegitcommit: 129f8574eba201eb6ade1f1620c6b80dfe63b331
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "87435236"
---
# <a name="how-to-connect-on-a-specified-port"></a>방법: 지정된 포트에서 연결
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

이 항목은 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]를 사용하여 지정된 포트에서 SQL Server에 연결하는 방법을 설명합니다.  
  
### <a name="to-connect-on-a-specified-port"></a>지정된 포트에서 연결하려면  
  
1.  연결을 허용하도록 서버가 구성된 포트를 확인합니다. 지정된 포트에서 연결을 허용하도록 서버를 구성하는 방법에 대한 자세한 내용은 [방법: 특정 TCP 포트에서 수신 대기할 서버 구성(SQL Server 구성 관리자)](../../database-engine/configure-windows/configure-a-server-to-listen-on-a-specific-tcp-port.md)을 참조하세요.  
  
2.  원하는 포트를 [sqlsrv_connect](../../connect/php/sqlsrv-connect.md) 함수의 *$serverName* 매개 변수에 추가합니다. 서버 이름과 포트를 쉼표로 구분합니다. 예를 들어 다음 코드 줄은 포트 1521에서 *myServer* 라는 서버에 연결하는 방법을 보여 주기 위해 SQLSRV 드라이버를 사용합니다.  
  
    ```  
    $serverName = "myServer, 1521";  
    sqlsrv_connect( $serverName );  
    ```  
  
    다음 코드 줄은 포트 1521에서 *myServer*라는 서버에 연결하는 방법을 보여 주기 위해 PDO_SQLSRV 드라이버를 사용합니다.  
  
    ```  
    $serverName = "(local), 1521";  
    $database = "AdventureWorks";  
    $conn = new PDO( "sqlsrv:server=$serverName;Database=$database", "", "");  
    ```  
  
## <a name="see-also"></a>참고 항목  
[서버에 연결](../../connect/php/connecting-to-the-server.md)

[Microsoft Drivers for PHP for SQL Server 프로그래밍 가이드 | Microsoft Docs](../../connect/php/programming-guide-for-php-sql-driver.md)

[Microsoft Drivers for PHP for SQL Server 시작](../../connect/php/getting-started-with-the-php-sql-driver.md)

[SQLSRV 드라이버 API 참조](../../connect/php/sqlsrv-driver-api-reference.md)

[PDO_SQLSRV 드라이버 참조](../../connect/php/pdo-sqlsrv-driver-reference.md)  
  
