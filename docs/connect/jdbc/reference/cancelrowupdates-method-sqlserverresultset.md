---
description: cancelRowUpdates 메서드(SQLServerResultSet)
title: cancelRowUpdates 메서드(SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.cancelRowUpdates
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 2ecacca4-f7bc-4f5d-886a-da7747fdccae
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 32e5333f571ff9375bdbdc61e9743d29a57cedfd
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88438185"
---
# <a name="cancelrowupdates-method-sqlserverresultset"></a>cancelRowUpdates 메서드(SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  이 [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) 개체의 현재 행에 대한 업데이트 내용을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void cancelRowUpdates()  
```  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 cancelRowUpdates 메서드는 java.sql.ResultSet 인터페이스의 cancelRowUpdates 메서드에 의해 지정됩니다.  
  
 updater 메서드를 호출한 후 [updateRow](../../../connect/jdbc/reference/updaterow-method-sqlserverresultset.md) 메서드를 호출하기 전에 이 메서드를 호출하면 행에 대한 업데이트 내용이 롤백됩니다. 업데이트를 수행하지 않았거나 updateRow가 이미 호출된 경우 이 메서드는 아무 영향도 주지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
