---
title: SQL 데이터 개발자 | Microsoft Docs
description: Microsoft의 SQL 데이터 플랫폼을 사용하여 웹 서버, 엔터프라이즈 서버 및 클라우드의 모바일 디바이스 및 데스크톱에서 데이터 중심 솔루션을 만들 수 있습니다.
ms.custom: ''
ms.date: 08/05/2020
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 249e3794-e3fa-41cb-ad9c-f46e19e6805c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 85b7c9f681a79a3678b932c63f755fc01d543100
ms.sourcegitcommit: c7f40918dc3ecdb0ed2ef5c237a3996cb4cd268d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2020
ms.locfileid: "91726595"
---
# <a name="sql-data-developer"></a>SQL 데이터 개발자
Microsoft의 SQL 데이터 플랫폼을 사용하여 웹 서버, 엔터프라이즈 서버 및 클라우드의 모바일 디바이스 및 데스크톱에서 데이터 중심 솔루션을 만들 수 있습니다.  

## <a name="sql-data-storage"></a>SQL 데이터 스토리지
* [SQL Server 데이터베이스 엔진](../database-engine/install-windows/install-sql-server-database-engine.md) SQL Server 데이터베이스 엔진을 사용하여 OLTP(온라인 트랜잭션 처리) 또는 OLAP(온라인 분석 처리) 데이터에 사용할 관계형 데이터베이스를 만들 수 있습니다. 
* [Azure SQL](/azure/azure-sql/azure-sql-iaas-vs-paas-what-is-overview): Azure SQL을 사용하여 데이터베이스를 클라우드로 이동 
* [SQL Compact](https://www.microsoft.com/download/details.aspx?id=30709): SQL Server Compact를 사용하여 모바일 디바이스, 데스크톱 및 웹 클라이언트를 위한 독립 실행형 애플리케이션과 간헐적으로 연결되는 애플리케이션을 빌드합니다.
* [LocalDB](../database-engine/configure-windows/sql-server-express-localdb.md): SQL Server의 전체 서버 인스턴스를 관리할 필요 없이 개발 중에 LocalDB를 사용하여 Transact-SQL 코드를 작성하고 테스트할 수 있습니다.

## <a name="sql-data-tools"></a>SQL 데이터 도구
* [Azure Data Studio](../azure-data-studio/download-azure-data-studio.md): Windows, macOS 및 Linux에서 Azure Data Studio를 사용하여 SQL Server, Azure SQL Database, PostgreSQL, Jupyter Notebook 등을 실행할 수 있습니다.
* [SQL Server Data Tools](../ssdt/download-sql-server-data-tools-ssdt.md): Visual Studio 내부에서 SSDT를 사용하여 관계형 데이터베이스, Azure SQL 데이터베이스, Integration Services 패키지, Analysis Services 데이터 모델 및 Reporting Services 보고서를 작성할 수 있습니다.
* [SQL Server 관리 도구](../ssms/download-sql-server-management-studio-ssms.md)  Windows에서 SSMS를 사용하여 SQL Server 인스턴스를 구성, 모니터링 및 관리할 수 있습니다.

## <a name="sql-data-access"></a>SQL 데이터 액세스
* [SQL 클라이언트 드라이버](sql-connection-libraries.md):  SQL 드라이버를 사용하여 SQL 데이터베이스에서 데이터를 연결, 쿼리, 업데이트, 삽입 또는 삭제할 수 있습니다.
* [Entity Framework](/ef/): Entity Framework를 사용하여 SQL Server에 대한 직접 액세스와 EDM(엔터티 데이터 모델)과 원시 관계형 구조 간 매핑을 제어하는 옵션과 함께 LINQ를 사용하여 데이터베이스에 쉽게 액세스할 수 있습니다. 
* [WCF(Windows Communication Foundation)](/dotnet/framework/wcf/): 거의 턴키에 가까운 솔루션을 위한 Data Services를 사용하여 웹과 인트라넷 모두에서 OData 서비스를 쉽게 만들고 사용할 수 있습니다.
* [Sync Framework](/previous-versions/sql/synchronization/mt490616(v=msdn.10)) Sync Framework를 사용하여 모든 데이터 형식, 데이터 저장소, 전송 프로토콜 및 네트워크 토폴로지에 대한 오프라인 액세스를 설정할 수 있습니다.
* [사후 확장](https://github.com/dotnet/reactive) Rx(사후 확장)를 사용하여 이벤트 스트림 프로그래밍을 수행하고 관찰 가능한 시퀀스 및 LINQ 스타일 쿼리 연산자를 사용하여 비동기 프로그래밍을 단순화할 수 있습니다.  RxJS(JavaScript용 사후 확장)를 통해 관찰 가능한 시퀀스를 사용하여 웹에서 비동기 콜백 기반 프로그래밍 및 이벤트 구동 프로그래밍을 단순화할 수 있습니다.
* [CLR 통합](../relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  CLR 통합을 통해 Microsoft Visual Basic .NET 및 Microsoft Visual C#을 포함한 모든 .NET Framework 언어를 사용하여 저장 프로시저, 트리거, 사용자 정의 형식, 사용자 정의 함수, 사용자 정의 집계 및 스트리밍 테이블 반환 함수를 작성할 수 있습니다. 
* [SQLXML 4.0](../relational-databases/sqlxml/sqlxml-4-0-programming-concepts.md): SQLXML 4.0을 사용하여 관계형 데이터를 XML로 내보낼 수 있습니다.

## <a name="data-collection-processing-and-visualization"></a>데이터 수집, 처리 및 시각화
* [Analysis Services](/analysis-services/analysis-services-developer-documentation)
* [Integration Services](../integration-services/integration-services-developer-documentation.md)  
* [MDS(Master Data Services)](../master-data-services/develop/master-data-services-developer-documentation.md)
* [Replication Services](../relational-databases/replication/concepts/replication-developer-documentation.md)
* [Reporting Services](../reporting-services/reporting-services-developer-documentation.md)
* [Service Broker](../database-engine/configure-windows/sql-server-service-broker.md)
