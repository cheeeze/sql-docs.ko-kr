---
description: 변수 값 파일 만들기(SybaseToSQL)
title: 변수 값 파일 만들기 (SybaseToSQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Sybase Console,Creating Variable Value Files
- Sybase Console,Variable Value File Validation
ms.assetid: 395be464-4b19-44f7-91e5-b8876d6743dc
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 2f2d3a53cb12a0d7762137a44cc12ec6f06a5d81
ms.sourcegitcommit: 22dacedeb6e8721e7cdb6279a946d4002cfb5da3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92036702"
---
# <a name="creating-variable-value-files-sybasetosql"></a>변수 값 파일 만들기(SybaseToSQL)
변수 값 파일은 서버 마이그레이션 간에 자주 변경 되는 원본 또는 대상 서버 이름과 같은 명령의 매개 변수 값을 구성 하는 XML 파일입니다. 데이터베이스 마이그레이션이 많은 경우 각 원본 서버의 값을 저장 하는 여러 변수 파일이 생성 되 고 명령줄에서 **-v** 스위치를 사용 하 여 마스터 스크립트 파일에서 참조 됩니다. 이를 통해 여러 변수 파일의 변수 값을 사용 하 여 몇 가지 스크립트 파일의 정적 값을 유지 관리할 수 있습니다.  
  
> [!NOTE]  
> 1.  변수 이름 앞에는 $ (달러) 기호가 붙습니다. 변수에 변수 값 파일의 값이 할당 되지 않은 경우에는 스크립트 파일을 구문 분석 하는 동안 오류가 발생 하 여 콘솔 실행 프로세스가 상태일 됩니다.  
> 2.  에 대 한 이스케이프 문자는 **$** **$$** 입니다. 매개 변수의 변수 또는 정적 값 **$** 이 (달러) 기호를 포함 하는 경우 **$$** 변수 대신 문자로 처리 하도록를 지정 해야 합니다.  
> 3.  유지 관리를 위해 변수를 요소 내에 선언 하 여 `'variable-group'` 사용자 정의 변수의 논리적 분리를 수행할 수 있습니다.  이 요소는 반드시 사용 해야 하는 것은 아닙니다.  
  
**예:**  
  
**예제 1:**  
  
```xml  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="ProjectSpecs">  
  
    <variable name="$project_folder$" value="<project-folder>"/>  
  
    <variable name="$project_name$" value="<project-name>"/>  
  
    <variable name="$project_overwrite$" value="<true/false>"/>  
  
    <variable name="$project_type$" value="<project-type>"/>  
  
  </variable-group>  
  
</variables>  
```  
**예 2:**  
  
```xml  
<!--Sample of variable value file commands-->  
  
<variables>  
  
  <variable-group name="SQLServerParams">  
  
    <variable-group name="SqlServerConnectionParams">  
  
      <variable name="$TargetUserName$" value="<user-name>"/>  
  
      <variable name="$TargetServerName$" value="<server-name>"/>  
  
      <variable name="$TargetDB$" value="<database-name>"/>  
  
      <variable name="$TargetPassword$" value="<password>"/>  
  
      <variable name="$TrustedConnection$" value="<true/false>"/>  
  
    </variable-group>  
  
    <variable-group name="SqlServerObjectParams">  
  
      <variable name="$ObjectName1$" value="<object-name>"/>  
  
      <variable name="$ObjectName2$" value="<object-name>"/>  
  
    </variable-group>  
  
  </variable-group>  
  
</variables>  
```  
  
## <a name="variable-value-file-validation"></a>변수 값 파일 유효성 검사  
사용자는 ' 스키마 ' 폴더에서 사용할 수 있는 **ConsoleScriptVariablesSchema** 스키마 정의 파일에 대해 해당 변수 값 파일의 유효성을 쉽게 검사할 수 있습니다.  
  
## <a name="next-step"></a>다음 단계  
콘솔을 운영 하는 다음 단계에서는 [서버 연결 파일 &#40;SybaseToSQL을 만듭니다&#41;](../../ssma/sybase/creating-the-server-connection-files-sybasetosql.md)  
  
## <a name="see-also"></a>참고 항목  
[서버 파일 만들기 (Sybase)](./creating-the-server-connection-files-sybasetosql.md)  
