---
description: getGeneratedKeys 메서드(SQLServerStatement)
title: getGeneratedKeys 메서드(SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.getGeneratedKeys
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: a3325950-0e81-4ae8-aa0c-e1f6d371adcd
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2d7b3a4b8ca8f95ab4b62aa1ceee8e330a0b9f9d
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88435865"
---
# <a name="getgeneratedkeys-method-sqlserverstatement"></a>getGeneratedKeys 메서드(SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) 개체를 실행한 결과로 만들어진 자동 생성 키를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final java.sql.ResultSet getGeneratedKeys()  
```  
  
## <a name="return-value"></a>Return Value  
 ResultSet 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getGeneratedKeys 메서드는 java.sql.Statement 인터페이스의 getGeneratedKeys 메서드에 의해 지정됩니다.  
  
 이 메서드를 사용하는 방법에 대한 자세한 내용은 [자동 생성 키 사용](../../../connect/jdbc/using-auto-generated-keys.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
