---
title: JDBC 드라이버에 대한 공간 데이터 형식 샘플
description: 이 JDBC Driver for SQL Server 애플리케이션 예제는 Geometry 및 Geography 공간 데이터를 만들고, 삽입하고, 데이터베이스에서 검색하는 방법을 보여 줍니다.
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a04840e69f5fd8557d3c6f42f9a339710c9ebe3a
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86921019"
---
# <a name="spatial-data-types-sample"></a>공간 데이터 형식 샘플

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

이 [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] 샘플 애플리케이션은 공간 데이터 형식(Geometry 및 Geography)의 생성, 삽입, 검색 방법을 보여줍니다.

이 샘플의 코드 파일 이름은 SpatialDataTypes.java이며 다음과 같은 위치에 있습니다.

```bash
\<installation directory>\sqljdbc_<version>\<language>\samples\datatypes
```

## <a name="requirements"></a>요구 사항

이 샘플 애플리케이션을 실행하려면 mssql-jdbc jar 파일을 포함하도록 클래스 경로를 설정해야 합니다. 클래스 경로를 설정하는 방법에 대한 자세한 내용은 [JDBC 드라이버 사용](using-the-jdbc-driver.md)을 참조하세요.

> [!NOTE]
> [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]는 기본 설정된 JRE(Java Runtime Environment)에 따라 사용할 수 있는 mssql-jdbc 클래스 라이브러리 파일을 제공합니다. 선택할 JAR 파일에 대한 자세한 내용은 [System Requirements for the JDBC Driver](system-requirements-for-the-jdbc-driver.md)(JDBC Driver 시스템 요구 사항)를 참조하세요.

## <a name="example"></a>예제

다음 예제에서는 샘플 코드로 'Geometry' 및 'Geography' 열이 포함된 SpatialDataTypesTable_JDBC_Sample이라는 테이블을 만듭니다.

샘플은 POINT를 나타내는 WKT(Well-Known-Text)에서 먼저 'Geometry'와 'Geography' 개체를 만듭니다. 매개 변수가 있는 쿼리로 SQLServerPreparedStatement를 사용하여 데이터를 각 열에 적절하게 매핑합니다.

마지막으로 샘플은 테이블에 데이터를 삽입한 다음 검색합니다. 데이터는 WKT 형식으로 표시됩니다.

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;
import com.microsoft.sqlserver.jdbc.Geography;
import com.microsoft.sqlserver.jdbc.Geometry;
import com.microsoft.sqlserver.jdbc.SQLServerPreparedStatement;
import com.microsoft.sqlserver.jdbc.SQLServerResultSet;

public class SpatialDataTypes {

    private static String tableName = "SpatialDataTypesTable_JDBC_Sample";

    public static void main(String[] args) {

        // Create a variable for the connection string.
        String connectionUrl = "jdbc:sqlserver://<server>:<port>;databaseName=<database>;user=<user>;password=<password>";
        // Establish the connection.
        try (Connection con = DriverManager.getConnection(connectionUrl); Statement stmt = con.createStatement();) {
            dropAndCreateTable(stmt);

            // TODO: Implement Sample code
            String geoWKT = "POINT(3 40 5 6)";
            Geometry geomWKT = Geometry.STGeomFromText(geoWKT, 0);
            Geography geogWKT = Geography.STGeomFromText(geoWKT, 4326);

            try (SQLServerPreparedStatement pstmt = (SQLServerPreparedStatement) con
                    .prepareStatement("insert into " + tableName + " values (?, ?)");) {
                pstmt.setGeometry(1, geomWKT);
                pstmt.setGeography(2, geogWKT);
                pstmt.execute();

                SQLServerResultSet rs = (SQLServerResultSet) stmt.executeQuery("select * from " + tableName);
                rs.next();

                System.out.println("Geometry data: " + rs.getGeometry(1));
                System.out.println("Geography data: " + rs.getGeography(2));
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    private static void dropAndCreateTable(Statement stmt) throws SQLException {
        stmt.executeUpdate("if object_id('" + tableName + "','U') is not null" + " drop table " + tableName);

        stmt.executeUpdate("Create table " + tableName + " (c1 geometry, c2 geography)");
    }
}
```

## <a name="see-also"></a>참고 항목

[JDBC 데이터 형식 사용](working-with-data-types-jdbc.md)
