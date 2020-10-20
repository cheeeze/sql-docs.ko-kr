---
title: CLR 통합 시작 | Microsoft Docs
description: 이 문서에서는 .NET Framework CLR과 Microsoft SQL Server 통합을 사용 하 여 데이터베이스 개체를 컴파일하는 데 필요한 네임 스페이스 및 라이브러리에 대해 설명 합니다.
ms.custom: ''
ms.date: 08/02/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: quickstart
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration]
- namespaces [CLR integration]
- database objects [CLR integration], about CLR integration
- stored procedures [CLR integration]
- common language runtime [SQL Server], about CLR integration
- building database objects [CLR integration], about CLR integration
- common language runtime [SQL Server], stored procedures
- common language runtime [SQL Server], namespaces
- Hello World example [CLR integration]
- library [CLR integration]
ms.assetid: c73e628a-f54a-411a-bfe3-6dae519316cc
author: rothja
ms.author: jroth
ms.openlocfilehash: c307172d7bf8b258cbd56b4ef4abfe6704750358
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92192363"
---
# <a name="getting-started-with-clr-integration"></a>CLR 통합으로 작업 시작

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

이 항목에서는 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET Framework CLR (공용 언어 런타임)과의 통합을 사용 하 여 데이터베이스 개체를 컴파일하는 데 필요한 네임 스페이스 및 라이브러리에 대 한 개요를 제공 합니다. 또한 이 항목에서는 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#으로 작성된 간단한 CLR 저장 프로시저를 작성, 컴파일 및 실행하는 방법도 보여 줍니다.  
  
## <a name="required-namespaces"></a>필수 네임스페이스  

기본 CLR 데이터베이스 개체를 개발 하는 데 필요한 구성 요소는와 함께 설치 됩니다 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . CLR 통합 기능은 .NET Framework의 일부인 system.data.dll이라는 어셈블리에서 제공되며 이 어셈블리는 GAC(전역 어셈블리 캐시)와 .NET Framework 디렉터리에 있습니다. 이 어셈블리에 대한 참조는 일반적으로 명령줄 도구와 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio에 자동으로 추가되므로 직접 추가하지 않아도 됩니다.  
  
system.data.dll 어셈블리에는 CLR 데이터베이스 개체를 컴파일하는 데 필요한 다음과 같은 네임스페이스가 들어 있습니다.  
  
- `System.Data`  
- `System.Data.Sql`  
- `Microsoft.SqlServer.Server`  
- `System.Data.SqlTypes`  

> [!TIP]
> Linux에서 CLR 데이터베이스 개체를 로드 하는 것은 지원 되지만 .NET Framework를 사용 하 여 빌드해야 합니다 (SQL Server CLR 통합은 .NET Core를 지원 하지 않음). 또한 EXTERNAL_ACCESS 또는 UNSAFE 권한 집합이 있는 CLR 어셈블리는 Linux에서 지원 되지 않습니다.

## <a name="writing-a-simple-hello-world-stored-procedure"></a>간단한 "Hello World" 저장 프로시저 작성  

아래의 Visual C# 또는 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic 코드를 복사하여 텍스트 편집기에 붙여넣고 이름이 "helloworld.cs" 또는 "helloworld.vb"인 파일로 저장합니다.  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
  
public class HelloWorldProc  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld(out string text)  
    {  
        SqlContext.Pipe.Send("Hello world!" + Environment.NewLine);  
        text = "Hello world!";  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.Runtime.InteropServices  
  
Public Class HelloWorldProc  
    \<Microsoft.SqlServer.Server.SqlProcedure> _   
    Public Shared  Sub HelloWorld(\<Out()> ByRef text as String)  
        SqlContext.Pipe.Send("Hello world!" & Environment.NewLine)  
        text = "Hello world!"  
    End Sub  
End Class  
  
```  
  
이 간단한 프로그램에는 공용 클래스에 대한 정적 메서드 하나가 포함되어 있습니다. 이 메서드는 간단한 문자 메시지를 출력 하기 위해 관리 되는 데이터베이스 개체를 만들기 위해 **[Sqlcontext](/dotnet/api/microsoft.sqlserver.server.sqlcontext)** 및 **[SqlPipe](/dotnet/api/microsoft.sqlserver.server.sqlpipe)** 라는 두 개의 새로운 클래스를 사용 합니다. 또한 이 메서드는 "Hello world!"라는 문자열을 out 매개 변수 값으로 할당합니다. 이 메서드는 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]에서 저장 프로시저로 선언한 다음 [!INCLUDE[tsql](../../../includes/tsql-md.md)] 저장 프로시저와 같은 방식으로 실행할 수 있습니다.  
  
이 프로그램을 라이브러리로 컴파일한 후에 로드 하 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 고 저장 프로시저로 실행 합니다.  
  
## <a name="compile-the-hello-world-stored-procedure"></a>"Hello World" 저장 프로시저 컴파일  

[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]에서는 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework 재배포 가능 파일을 기본적으로 설치합니다. 이러한 파일에는 csc.exe와 vbc.exe, 그리고 Visual C# 및 Visual Basic 프로그램용 명령줄 컴파일러가 포함됩니다. 예제를 컴파일하려면 csc.exe 또는 vbc.exe가 포함된 디렉터리를 가리키도록 경로 변수를 수정해야 합니다. .NET Framework의 기본 설치 경로는 다음과 같습니다.  
  
`C:\Windows\Microsoft.NET\Framework\(version)`  
  
version에는 설치된 .NET Framework 재배포 가능 패키지의 버전 번호가 포함됩니다. 예를 들면 다음과 같습니다.  
  
`C:\Windows\Microsoft.NET\Framework\v4.6.1`

경로에 .NET Framework 디렉터리를 추가한 후에는 다음 명령을 사용하여 예제 저장 프로시저를 어셈블리로 컴파일할 수 있습니다. **/Target** 옵션을 사용 하면 어셈블리로 컴파일할 수 있습니다.  
  
Visual C# 원본 파일의 경우 다음 명령을 실행합니다.  
  
`csc /target:library helloworld.cs`  
  
 Visual Basic 원본 파일의 경우 다음 명령을 실행합니다.  
  
`vbc /target:library helloworld.vb`  
  
이러한 명령은 라이브러리 DLL을 빌드하도록 지정하는 /target 옵션을 사용하여 Visual C# 또는 Visual Basic 컴파일러를 시작합니다.  
  
## <a name="loading-and-running-the-hello-world-stored-procedure-in-sql-server"></a>SQL Server에서 "Hello World" 저장 프로시저 로드 및 실행  

예제 프로시저가 성공적으로 컴파일되면 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]에서 테스트해 볼 수 있습니다. 컴파일된 예제 프로시저를 테스트하려면 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]를 열고 새 쿼리를 만들어 적절한 테스트 데이터베이스(예: AdventureWorks 예제 데이터베이스)에 연결합니다.  
  
[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]에서는 CLR(공용 언어 런타임) 코드를 실행하는 기능이 기본적으로 OFF로 설정되어 있습니다. **Sp_configure** 시스템 저장 프로시저를 사용 하 여 CLR 코드를 사용 하도록 설정할 수 있습니다. 자세한 내용은 [Enabling CLR Integration](../../../relational-databases/clr-integration/clr-integration-enabling.md)을 참조하세요.  
  
저장 프로시저에 액세스할 수 있게 어셈블리를 만들어야 합니다. 이 예에서는 C:\ 디렉터리에 helloworld.dll 어셈블리를 만들었다고 가정합니다. 쿼리에 다음의 [!INCLUDE[tsql](../../../includes/tsql-md.md)] 문을 추가합니다.  
  
`CREATE ASSEMBLY helloworld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE`  
  
어셈블리가 만들어지면 CREATE PROCEDURE 문을 사용하여 HelloWorld 메서드에 액세스할 수 있습니다. 여기서 저장 프로시저 이름은 "hello"입니다.  
  
```sql
CREATE PROCEDURE hello  
@i nchar(25) OUTPUT  
AS  
EXTERNAL NAME helloworld.HelloWorldProc.HelloWorld  
-- if the HelloWorldProc class is inside a namespace (called MyNS),  
-- the last line in the create procedure statement would be  
-- EXTERNAL NAME helloworld.[MyNS.HelloWorldProc].HelloWorld  
```  
  
프로시저가 만들어지면 [!INCLUDE[tsql](../../../includes/tsql-md.md)]로 작성된 일반적인 저장 프로시저와 마찬가지로 프로시저를 실행할 수 있습니다. 다음 명령을 실행하십시오.  
  
```sql
DECLARE @J nchar(25)  
EXEC hello @J out  
PRINT @J  
```  
  
그러면 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] 메시지 창에 다음과 같은 메시지가 출력됩니다.  
  
```
Hello world!  
Hello world!  
```  
  
## <a name="removing-the-hello-world-stored-procedure-sample"></a>"Hello World" 저장 프로시저 예제 제거  

예제 저장 프로시저 실행이 완료되면 프로시저와 어셈블리를 테스트 데이터베이스에서 제거할 수 있습니다.  
  
먼저 drop procedure 명령을 사용하여 프로시저를 제거합니다.  
  
```sql
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'hello')  
   drop procedure hello  
```  
  
프로시저가 삭제되면 예제 코드가 포함된 어셈블리를 제거할 수 있습니다.  
  
```sql
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'helloworld')  
   drop assembly helloworld  
```  
  
## <a name="next-steps"></a>다음 단계

SQL Server의 CLR 통합에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [CLR 저장 프로시저](/dotnet/framework/data/adonet/sql/clr-stored-procedures)
- [ADO.NET에 대한 SQL Server In-Process 전용 확장](../../../relational-databases/clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md)
- [CLR 데이터베이스 개체 디버깅](../../../relational-databases/clr-integration/debugging-clr-database-objects.md)
- [CLR 통합 보안](../../../relational-databases/clr-integration/security/clr-integration-security.md)