---
description: setFetchSize 메서드(SQLServerStatement)
title: setFetchSize 메서드(SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.setFetchSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 760e555e-9667-4b40-b0ba-778026ff2923
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1f87aced668933da1e4bbde3b0f4d999abf7eac4
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88431845"
---
# <a name="setfetchsize-method-sqlserverstatement"></a>setFetchSize 메서드(SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  추가 행이 필요할 경우 데이터베이스에서 인출되는 행 수에 관한 힌트를 [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]에 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final void setFetchSize(int rows)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *rows*  
  
 인출할 행 수를 나타내는 **int**입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 setFetchSize 메서드는 java.sql.Statement 인터페이스의 setFetchSize 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
