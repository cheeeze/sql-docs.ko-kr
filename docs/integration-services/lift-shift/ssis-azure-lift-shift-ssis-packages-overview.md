---
title: Azure에서 SSIS 패키지 배포 및 실행 | Microsoft Docs
description: SSIS(SQL Server Integration Services) 프로젝트 및 워크로드를 Microsoft Azure 클라우드로 이동할 수 있는 방법을 알아봅니다.
ms.date: 09/23/2018
ms.topic: conceptual
ms.prod: sql
ms.prod_service: integration-services
ms.custom: ''
ms.technology: integration-services
author: swinarko
ms.author: sawinark
ms.reviewer: maghan
ms.openlocfilehash: 7a962b29d6af2caf48f32eec5bc7e77bef3b126f
ms.sourcegitcommit: cfa04a73b26312bf18d8f6296891679166e2754d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92194058"
---
# <a name="lift-and-shift-sql-server-integration-services-workloads-to-the-cloud"></a>SQL Server Integration Services 워크로드를 클라우드로 리프트 앤 시프트

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


이제 SSIS(SQL Server Integration Services) 프로젝트 및 워크로드를 Azure 클라우드로 이동할 수 있습니다. SSMS(SQL Server Management Studio)와 같은 친숙한 도구를 사용하여 SQL Managed Instance 또는 Azure SQL Database의 SSIS 카탈로그(SSISDB)에서 SSIS 프로젝트와 패키지를 배포, 실행 및 관리합니다.

## <a name="benefits"></a>이점
온-프레미스 SSIS 워크로드를 Azure로 이동하면 다음과 같은 잠재적 이점이 있습니다.
-   SSIS를 온-프레미스 또는 Azure 가상 머신에서 실행할 때 **운영 비용을 절감**하고 인프라를 관리하는 부담을 줄입니다.
-   Azure 및 Azure SQL Database의 고가용성 기능뿐만 아니라 클러스터당 여러 노드를 지정할 수 있는 기능도 있으므로 **고가용성을 높입니다**.
-   노드당 다중 코어(강화) 및 클러스터당 다중 노드(규모 확장)를 지정하는 기능으로 **확장성을 높입니다**.

## <a name="architecture-of-ssis-on-azure"></a>Azure의 SSIS 아키텍처
다음 표에서는 온-프레미스 SSIS와 Azure SSIS의 차이점을 보여 줍니다.

가장 중요한 차이점은 스토리지와 런타임의 분리입니다. Azure Data Factory는 Azure에서 SSIS 패키지의 런타임 엔진을 호스팅합니다. 런타임 엔진은 Azure-SSIS IR(Azure SSIS Integration Runtime)이라고 합니다. 자세한 내용은 [Azure-SSIS Integration Runtime](/azure/data-factory/concepts-integration-runtime#azure-ssis-integration-runtime)을 참조하세요.

| 위치 | 스토리지 | 런타임 | 확장성 |
|---|---|---|---|
| 온-프레미스 | SQL Server | SQL Server에서 호스팅하는 SSIS 런타임 | SSIS Scale Out(SQL Server 2017 이상)<br/><br/>사용자 지정 솔루션(이전 버전의 SQL Server) |
| Azure | SQL Database 또는 SQL Managed Instance | Azure Data Factory의 구성 요소인 Azure SSIS Integration Runtime | Azure-SSIS Integration Runtime의 옵션 크기 조정 |
| | | | |

## <a name="provision-ssis-on-azure"></a>Azure에서 SSIS 프로비전

**프로비전**. Azure에서 SSIS 패키지를 배포하고 실행하려면 먼저 SSISDB(SSIS 카탈로그)와 Azure-SSIS Integration Runtime을 프로비전해야 합니다.

-   Azure Portal의 Azure에서 SSIS를 프로비저닝하려면 이 문서의 프로비저닝 단계를 따르세요. [Azure Data Factory에서 Azure-SSIS Integration Runtime 프로비저닝](/azure/data-factory/tutorial-deploy-ssis-packages-azure) 

-   PowerShell을 통해 Azure에서 SSIS를 프로비저닝하려면 이 문서의 프로비저닝 단계를 따르세요. [Azure Data Factory에서 PowerShell을 통해 Azure-SSIS Integration Runtime 프로비저닝](/azure/data-factory/tutorial-deploy-ssis-packages-azure-powershell)

Azure-SSIS IR은 한 번만 프로비전해야 합니다. 그런 다음 SSDT(SQL Server Data Tools) 및 SSMS(SQL Server Management Studio)와 같은 친숙한 도구를 사용하여 패키지를 배포, 구성, 실행, 모니터링, 예약 및 관리할 수 있습니다.

> [!NOTE]
> Azure-SSIS Integration Runtime은 일부 Azure 지역에서 아직 사용할 수 없습니다. 지원되는 지역에 대한 정보는 [지역별 사용 가능한 제품 - Microsoft Azure](https://azure.microsoft.com/regions/services/)를 참조하세요.

**강화 및 규모 확장**. Azure-SSIS IR을 프로비전할 때 다음 옵션에 대한 값을 지정하여 강화하거나 규모 확장할 수 있습니다.
-   노드 크기(코어 수 포함) 및 클러스터의 노드 수
-   SSISDB(SSIS 카탈로그 데이터베이스)를 호스팅하는 Azure SQL Database의 기존 인스턴스 및 데이터베이스의 서비스 계층
-   노드당 최대 병렬 실행 수

**성능 향상**. 자세한 내용은 [고성능을 위한 Azure-SSIS Integration Runtime 구성](/azure/data-factory/configure-azure-ssis-integration-runtime-performance)을 참조하세요.

**비용 절감**. 비용을 줄이려면 필요한 경우에만 Azure-SSIS IR를 실행합니다. 자세한 내용은 [Azure SSIS 통합 런타임의 시작 및 중지를 예약하는 방법](/azure/data-factory/how-to-schedule-azure-ssis-integration-runtime)을 참조하세요.

## <a name="design-packages"></a>패키지 디자인

SSDT가 설치된 Visual Studio 또는 SSDT에서 온-프레미스 **패키지를 설계하고 빌드**합니다.

### <a name="connect-to-data-sources"></a>데이터 원본에 연결

**Windows 인증**을 사용하여 클라우드에서 온-프레미스 데이터 원본에 연결하려면 [Azure에서 SSIS 패키지의 Windows 인증을 사용하여 데이터 원본 및 파일 공유에 연결](/azure/data-factory/ssis-azure-connect-with-windows-auth)을 참조하세요.

파일 및 파일 공유에 연결하려면 [Azure에 배포된 SSIS 패키지로 온-프레미스 및 Azure에서 파일 열기 및 저장](/azure/data-factory/ssis-azure-files-file-shares)을 참조하세요.

### <a name="available-ssis-components"></a>지원되는 SSIS 구성 요소

SSISDB를 호스트하기 위해 SQL Database의 인스턴스를 프로비전하는 경우 Azure Feature Pack for SSIS 및 Access 재배포 가능 패키지도 설치됩니다. 이러한 구성 요소는 기본 제공 구성 요소에서 지원하는 데이터 원본 외에도 다양한 **Azure** 데이터 원본 및 **Excel 및 Access** 파일에 대한 연결을 제공합니다.

추가 구성 요소를 설치할 수도 있습니다. 예를 들어 기본적으로 설치되지 않은 드라이버를 설치할 수 있습니다. 자세한 내용은 [Azure SSIS Integration Runtime에 대한 사용자 지정 설치](/azure/data-factory/how-to-configure-azure-ssis-ir-custom-setup)를 참조하세요.

Enterprise Edition 라이선스가 있는 경우 추가 구성 요소를 사용할 수 있습니다. 자세한 내용은 [Azure-SSIS Integration Runtime용 Enterprise Edition 프로비전](/azure/data-factory/how-to-configure-azure-ssis-ir-enterprise-edition)을 참조하세요.

ISV인 경우 사용이 허가된 구성 요소의 설치를 업데이트하여 Azure에서 사용할 수 있습니다. 자세한 내용은 [Azure-SSIS Integration Runtime에 대한 유료 또는 사용이 허가된 사용자 지정 구성 요소 설치](/azure/data-factory/how-to-develop-azure-ssis-ir-licensed-components)를 참조하세요.

### <a name="transaction-support"></a>트랜잭션 지원

온-프레미스 및 Azure 가상 머신의 SQL Server에서는 MSDTC(Microsoft Distributed Transaction Coordinator) 트랜잭션을 사용할 수 있습니다. Azure-SSIS IR의 각 노드에서 MSDTC를 구성하려면 사용자 지정 설정 기능을 사용합니다. 자세한 내용은 [Azure SSIS 통합 런타임에 대한 사용자 지정 설치](/azure/data-factory/how-to-configure-azure-ssis-ir-custom-setup)를 참조하세요.

Azure SQL Database에서는 탄력적 트랜잭션을 사용할 수 있습니다. 자세한 내용은 [클라우드 데이터베이스의 분산 트랜잭션](/azure/sql-database/sql-database-elastic-transactions-overview)을 참조하세요.

## <a name="deploy-and-run-packages"></a>패키지 배포 및 실행

시작하려면 [자습서: Azure에서 SSIS(SQL Server Integration Services) 패키지 배포 및 실행](ssis-azure-deploy-run-monitor-tutorial.md)

### <a name="prerequisites"></a>사전 요구 사항

SSIS 패키지를 Azure에 배포하려면 다음 버전의 SSDT(SQL Server Data Tools) 중 하나가 설치되어야 합니다.
-   Visual Studio 2017의 경우 버전 15.3 이상
-   Visual Studio 2015용, 버전 17.2 이상

### <a name="connect-to-ssisdb"></a>SSISDB에 연결

SSISDB를 호스팅하는 **SQL Database의 이름**은 SSDT 및 SSMS에서 패키지를 배포하고 실행할 때 사용할 네 부분으로 된 다음과 같은 형식(`<sql_database_name>.database.windows.net`)인 이름의 첫 부분입니다. Azure에서 SSIS 카탈로그 데이터베이스에 연결하는 방법에 대한 자세한 내용은 [Azure에서 SSISDB(SSIS 카탈로그)에 연결](ssis-azure-connect-to-catalog-database.md)을 참조하세요.

### <a name="deploy-projects-and-packages"></a>프로젝트 및 패키지 배포

Azure에서 SSISDB에 프로젝트를 배포하는 경우 패키지 배포 모델이 아닌 **프로젝트 배포 모델**을 사용해야 합니다.

Azure에서 프로젝트를 배포하려면 다음과 같은 몇 가지 친숙한 도구 및 스크립팅 옵션 중 하나를 사용할 수 있습니다.
-   SSMS(SQL Server Management Studio)
-   Transact-SQL(SSMS, Visual Studio Code 또는 다른 도구에서 제공)
-   명령줄 도구
-   PowerShell 또는 C# 및 SSIS 관리 개체 모델

배포 프로세스는 패키지의 유효성을 검사하여 Azure-SSIS Integration Runtime에서 실행할 수 있는지를 확인합니다. 자세한 내용은 [Azure에 배포된 SSIS(SQL Server Integration Services) 패키지 유효성 검사](ssis-azure-validate-packages.md)를 참조하세요.

SSMS 및 Integration Services Deployment Wizard를 사용하는 배포 예제는 [자습서를 참조하세요. Azure에서 SSIS(SQL Server Integration Services) 패키지 배포 및 실행](ssis-azure-deploy-run-monitor-tutorial.md)

### <a name="version-support"></a>버전 지원

모든 버전의 SSIS를 사용하여 만든 패키지를 Azure에 배포할 수 있습니다. 패키지를 Azure로 배포할 때 유효성 검사 오류가 없는 경우 패키지가 최신 패키지 형식으로 자동 업그레이드됩니다. 즉, 항상 SSIS의 최신 버전으로 업그레이드됩니다.

### <a name="run-packages"></a>패키지 실행

Azure에 배포된 SSIS 패키지를 실행하려면 다양한 방법을 사용할 수 있습니다. 자세한 내용은 [Azure에 배포된 SSIS(SQL Server Integration Services) 실행](ssis-azure-run-packages.md)을 참조하세요.

### <a name="run-packages-in-an-azure-data-factory-pipeline"></a>Azure Data Factory 파이프라인에서 패키지 실행

Azure Data Factory 파이프라인에서 SSIS 패키지를 실행하려면 SSIS 패키지 작업 실행을 사용합니다. 자세한 내용은 [Azure Data Factory에서 SSIS 패키지 실행 작업을 사용하여 SSIS 패키지 실행](/azure/data-factory/how-to-invoke-ssis-package-ssis-activity)을 참조하십시오.

SSIS 패키지 작업 실행을 통해 Data Factory 파이프라인에서 패키지를 실행하면 런타임에 값을 패키지에 전달할 수 있습니다. 하나 이상의 런타임 값을 전달하려면 SSMS(SQL Server Management Studio)를 사용하여 SSISDB에서 SSIS 실행 환경을 만듭니다. 각 환경에서 변수를 만들고 프로젝트 또는 패키지에 대한 매개 변수에 해당하는 값을 할당합니다. 프로젝트 또는 패키지 매개 변수와 해당 환경 변수를 연결하려면 SSMS에서 SSIS 패키지를 구성합니다. 파이프라인에서 패키지를 실행하는 경우 SSIS 패키지 작업 실행 UI의 설정 탭에서 다른 환경 경로를 지정하여 환경 간에 전환합니다. SSIS 환경에 대한 자세한 내용은 [서버 환경 만들기 및 매핑](../packages/deploy-integration-services-ssis-projects-and-packages.md#create-and-map-a-server-environment)을 참조하세요.

## <a name="monitor-packages"></a>패키지 모니터링

실행 중인 패키지를 모니터링하려면 SSMS에서 다음 보고 옵션을 사용합니다.
-   **SSISDB**를 마우스 오른쪽 단추로 클릭한 다음 **활성 작업**을 선택하여 **활성 작업** 대화 상자를 엽니다.
-   [개체 탐색기]에서 패키지를 선택하여 마우스 오른쪽 단추로 클릭하고, **보고서**, **표준 보고서**, **모든 실행**을 차례로 선택합니다.

Azure-SSIS Integration Runtime을 모니터링하려면 [Azure-SSIS Integration Runtime 모니터링](/azure/data-factory/monitor-integration-runtime#azure-ssis-integration-runtime)을 참조하세요.

## <a name="schedule-packages"></a>패키지 예약
Azure에 배포된 패키지의 실행을 예약하기 위해 다양한 도구를 사용할 수 있습니다. 자세한 내용은 [Azure에 배포된 SSIS(SQL Server Integration Services) 실행 예약](ssis-azure-schedule-packages.md)을 참조하세요.

## <a name="next-steps"></a>다음 단계
Azure에서 SSIS 워크로드를 시작하려면 다음 문서를 참조하세요.
-   [자습서: Azure에 SSIS(SQL Server Integration Services) 패키지 배포 및 실행](ssis-azure-deploy-run-monitor-tutorial.md)
-   [Azure Data Factory에서 Azure-SSIS Integration Runtime 프로비전](/azure/data-factory/tutorial-deploy-ssis-packages-azure)