---
title: 큰 CLR 사용자 정의 형식 | Microsoft Docs
description: 여러 버전의 SQL Server에 대한 공용 언어 런타임에서 사용자 정의 형식의 크기 제한 및 관련 동작에 대해 알아봅니다.
ms.custom: ''
ms.date: 06/12/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 9fdc52df9307bbe4ce3e826ca682d787e1c11506
ms.sourcegitcommit: c95f3ef5734dec753de09e07752a5d15884125e2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88861467"
---
# <a name="large-clr-user-defined-types"></a>큰 CLR 사용자 정의 형식
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  SQL Server 2005에서는 CLR(공용 언어 런타임)에서의 UDT(사용자 정의 형식) 크기가 8,000바이트로 제한되었습니다. [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] 이상 버전에서는 이 제한이 더 이상 적용되지 않습니다. 이제 CLR UDT가 LOB(Large Object) 형식과 비슷하게 처리됩니다. 즉, 8,000바이트보다 작거나 같은 UDT는 SQL Server 2005에서와 동일하게 처리되나 이보다 큰 UDT도 지원되며 이 경우 크기가 "제한 없음"으로 보고됩니다.  
  
 자세한 내용은 [큰 CLR 사용자 정의 형식&#40;OLE DB&#41;](../../oledb/ole-db/large-clr-user-defined-types-ole-db.md)을 참조하세요.  
  
## <a name="use-cases"></a>사용 사례   
  
 OLE DB의 경우 ISequentialStream 바인딩을 통해 UDT 값을 서버로 스트리밍하거나 서버에서 스트리밍하는 기능이 큰 UDT에 대한 지원에 포함되었습니다.  
  
 8,000바이트보다 작거나 같은 UDT는 SQL Server 2005에서와 동일하게 처리됩니다. OLE DB의 경우 작은 UDT는 ISequentialStream 바인딩을 사용하여 이전처럼 스트리밍할 수 있습니다.  
  
 네이티브 코드가 CLR UDT의 내용을 이해해야 하지만 관리되는 개체를 인스턴스화할 필요는 없는 경우가 있습니다. 이 경우 사용자 지정 직렬화를 사용하여 서버의 UDT 값을 클라이언트의 잘 알려진 형식으로 변환할 수 있습니다.  
  
 데이터 액세스 코드가 이미 있는 애플리케이션의 경우 네이티브 API를 통해 UDT를 검색한 후 이를 혼합 모드 애플리케이션에서 C++ CLI interop을 사용하여 인스턴스화하는 방법으로 클라이언트에서 CLR UDT 동작을 이용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 기능용 OLE DB 드라이버](../../oledb/features/oledb-driver-for-sql-server-features.md)    
  
  
