---
description: prepareStatement 메서드(java.lang.String, int, int, int)
title: prepareStatement 메서드(java.lang.String, int, int, int) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.prepareStatement (java.lang.String, int, int, int)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b78d2192-f315-4c45-9051-c77059e2c3f4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 644b5e0f1ff37ba3e955b0f74096d47df10bd01a
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88432925"
---
# <a name="preparestatement-method-javalangstring-int-int-int"></a>prepareStatement 메서드(java.lang.String, int, int, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  지정된 형식, 동시성 및 유지 기능을 사용하여 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체를 생성하는 [SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public java.sql.PreparedStatement prepareStatement(java.lang.String sql,  
                                                   int nType,  
                                                   int nConcur,  
                                                   int nHold)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *sql*  
  
 SQL 문이 포함된 **String**입니다.  
  
 *nType*  
  
 결과 집합 유형을 나타내는 **int**입니다.  
  
 *nConcur*  
  
 결과 집합 동시성 유형을 나타내는 **int**입니다.  
  
 *nHold*  
  
 결과 집합 유지 기능을 나타내는 **int**입니다.  
  
## <a name="return-value"></a>반환 값  
 PreparedStatement 개체입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 prepareStatement 메서드는 java.sql.Connection 인터페이스의 prepareStatement 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [prepareStatement 메서드 &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/preparestatement-method-sqlserverconnection.md)   
 [SQLServerConnection 멤버](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection 클래스](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
