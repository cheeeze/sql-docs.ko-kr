---
title: Azure SQL 데이터베이스에 연결
description: 이 문서에서는 Microsoft JDBC Driver for SQL Server를 사용하여 Azure SQL Database에 연결하는 경우의 문제에 대해 설명합니다.
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 49645b1f-39b1-4757-bda1-c51ebc375c34
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: bda9c33588c8248d0aff62f555ec46451d0e9e78
ms.sourcegitcommit: c7f40918dc3ecdb0ed2ef5c237a3996cb4cd268d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2020
ms.locfileid: "91725494"
---
# <a name="connecting-to-an-azure-sql-database"></a>Azure SQL 데이터베이스에 연결

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

이 문서에서는 [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]를 사용하여 [!INCLUDE[ssAzure](../../includes/ssazure_md.md)]에 연결하는 경우의 문제에 대해 논의합니다. [!INCLUDE[ssAzure](../../includes/ssazure_md.md)]에 연결하는 방법에 대한 자세한 내용은 다음을 참조하세요.  
  
- [Azure SQL Database](/azure/sql-database/sql-database-technical-overview)  
  
- [방법: JDBC를 사용하여 Azure SQL에 연결](/azure/sql-database/sql-database-connect-query-java)  

- [Azure Active Directory 인증을 사용하여 연결](connecting-using-azure-active-directory-authentication.md)  
  
## <a name="details"></a>세부 정보

[!INCLUDE[ssAzure](../../includes/ssazure_md.md)]에 연결할 때 **SQLServerDatabaseMetaData.getCatalogs**를 호출하려면 master 데이터베이스에 연결해야 합니다.  
[!INCLUDE[ssAzure](../../includes/ssazure_md.md)]는 사용자 데이터베이스에서 전체 카탈로그 집합을 반환하는 기능을 지원하지 않습니다. **SQLServerDatabaseMetaData.getCatalogs**는 sys.databases 보기를 사용하여 카탈로그를 가져옵니다. [!INCLUDE[ssAzure](../../includes/ssazure_md.md)]에서 **SQLServerDatabaseMetaData.getCatalogs** 동작을 이해하려면 [sys.databases (Transact-SQL)](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)의 사용 권한에 대한 설명을 참조하세요.  
  
## <a name="connections-dropped"></a>연결이 삭제됨

[!INCLUDE[ssAzure](../../includes/ssazure_md.md)]에 연결할 때 비활성 기간 후 방화벽과 같은 네트워크 구성 요소에서 유휴 연결을 종료할 수 있습니다. 유휴 연결에는  

- 네트워크 디바이스에서 연결을 삭제할 수 있는 TCP 계층에서 유휴 연결(Idle at the TCP layer) 및  

- TCP **keepalive** 메시지가 발생할 수 있으나(TCP 쪽에서 유휴 상태가 아닌 연결하기) 30분간 활성 쿼리가 없는 Azure SQL 게이트웨이에서 유휴 연결(Idle by the Azure SQL Gateway)의 두 가지 종류가 있습니다. 이 시나리오에서 게이트웨이가 TDS 연결이 30분간 유휴 상태이고 연결을 종료됨을 결정합니다.  
  
네트워크 구성 요소에서 유휴 연결을 삭제하지 않도록 하려면 드라이버가 로드된 운영 체제에서 다음 레지스트리 설정(또는 Windows가 아닌 경우 이에 해당하는 설정)을 설정해야 합니다.  
  
|레지스트리 설정|권장되는 값|  
|----------------------|-----------------------|  
|HKEY_LOCAL_MACHINE \ SYSTEM \ CurrentControlSet \ Services \ Tcpip \ Parameters \ KeepAliveTime|30000|  
|HKEY_LOCAL_MACHINE \ SYSTEM \ CurrentControlSet \ Services \ Tcpip \ Parameters \ KeepAliveInterval|1000|  
|HKEY_LOCAL_MACHINE \ SYSTEM \ CurrentControlSet \ Services \ Tcpip \ Parameters \ TcpMaxDataRetransmissions|10|  
  
레지스트리 설정을 적용하려면 컴퓨터를 다시 시작합니다.  

Azure에서 실행 시 이 작업을 수행하려면 시작 작업을 생성하여 레지스트리 키를 추가합니다.  예를 들어 다음과 같은 시작 태스크를 서비스 정의 파일에 추가합니다.  

```xml
<Startup>  
    <Task commandLine="AddKeepAlive.cmd" executionContext="elevated" taskType="simple">  
    </Task>  
</Startup>  
```

그런 다음 프로젝트에 AddKeepAlive.cmd 파일을 추가합니다. "출력 디렉터리로 복사" 설정을 항상 복사로 설정합니다. 다음은 예제 AddKeepAlive.cmd 파일입니다.  

```bat
if exist keepalive.txt goto done  
time /t > keepalive.txt  
REM Workaround for JDBC keep alive on Azure SQL  
REG ADD HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters /v KeepAliveTime /t REG_DWORD /d 30000 >> keepalive.txt  
REG ADD HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters /v KeepAliveInterval /t REG_DWORD /d 1000 >> keepalive.txt  
REG ADD HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters /v TcpMaxDataRetransmissions /t REG_DWORD /d 10 >> keepalive.txt  
shutdown /r /t 1  
:done  
```

## <a name="appending-the-server-name-to-the-userid-in-the-connection-string"></a>연결 문자열에서 서버 이름을 사용자 ID에 추가  

[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]의 4.0 버전 이전에는 [!INCLUDE[ssAzure](../../includes/ssazure_md.md)]에 연결할 때 연결 문자열에서 서버 이름을 사용자 ID에 추가해야 했습니다. user@servername)을 입력합니다. [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] 4.0 버전부터 연결 문자열에서 @servername을 사용자 ID에 추가할 필요가 없게 되었습니다.  

## <a name="using-encryption-requires-setting-hostnameincertificate"></a>암호화 사용에 hostNameInCertificate 설정 필요

[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]의 7.2 버전 이전에서는 [!INCLUDE[ssAzure](../../includes/ssazure_md.md)]에 연결할 때 **encrypt=true**를 지정하면 **hostNameInCertificate**를 지정해야 합니다(연결 문자열의 서버 이름이 *shortName*.*domainName*인 경우 **hostNameInCertificate** 속성을 \*.*domainName*으로 설정). 드라이버 버전 7.2부터 이 속성은 선택 사항입니다.

다음은 그 예입니다.

```java
jdbc:sqlserver://abcd.int.mscds.com;databaseName=myDatabase;user=myName;password=myPassword;encrypt=true;hostNameInCertificate=*.int.mscds.com;
```

## <a name="see-also"></a>참고 항목

[JDBC 드라이버로 SQL Server에 연결](connecting-to-sql-server-with-the-jdbc-driver.md)