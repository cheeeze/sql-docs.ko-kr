---
description: updateDouble 메서드(java.lang.String, double)
title: updateDouble 메서드(java.lang.String, double) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.updateDouble (java.lang.String, double)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f70971d5-34cc-4f70-8a91-5d46356b24ae
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 8a142c0265b013b95faabd6546978dfabdfe6e0e
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2020
ms.locfileid: "88353449"
---
# <a name="updatedouble-method-javalangstring-double"></a>updateDouble 메서드(java.lang.String, double)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  열 이름이 지정된 경우 지정된 열을 **double** 값으로 업데이트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
public void updateDouble(java.lang.String columnName,  
                         double x)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *columnName*  
  
 열 이름이 포함된 **문자열**입니다.  
  
 *x*  
  
 **double** 값입니다.  
  
## <a name="exceptions"></a>예외  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>설명  
 이 updateDouble 메서드는 java.sql.ResultSet 인터페이스의 updateDouble 메서드에 의해 지정됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [updateDouble 메서드&#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updatedouble-method-sqlserverresultset.md)   
 [SQLServerResultSet 멤버](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 클래스](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
