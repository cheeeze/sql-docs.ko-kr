---
description: getUpdateCount 메서드(SQLServerStatement)
title: getUpdateCount 메서드(SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.getUpdateCount
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: e9570228-4500-44b6-b2f1-84ac050b5112
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 19a4cfc7b9957d8ba4392477e6dcd3732f10bd7c
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88433905"
---
# <a name="getupdatecount-method-sqlserverstatement"></a>getUpdateCount 메서드(SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  현재 결과를 검색하여 업데이트 횟수로 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public final int getUpdateCount()  
```  
  
## <a name="return-value"></a>Return Value  
 업데이트 횟수가 들어 있는 **int**입니다. 반환된 결과가 결과 집합 개체이거나 결과가 더 이상 없으면 -1이 반환됩니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 getUpdateCount 메서드는 java.sql.Statement 인터페이스의 getUpdateCount 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerStatement 멤버](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 클래스](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
