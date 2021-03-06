---
title: MSpeer_conflictdetectionconfigresponse (T-sql)
description: 피어 투 피어 복제에서 토폴로지 전체 구성 요청에 각 노드의 응답을 저장 하는 데 사용 되는 MSPeer_conflictdetectionconfigureresponse 저장 프로시저에 대해 설명 합니다.
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpeer_conflictdetectionconfigresponse
- MSpeer_conflictdetectionconfigresponse_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSpeer_conflictdetectionconfigureresponse
ms.assetid: 2685fb66-731d-40f7-af4b-596b9222c5d4
author: markingmyname
ms.author: maghan
ms.openlocfilehash: d402a77534b12fbb3bf880bcaac17be1dedcdde2
ms.sourcegitcommit: dd36d1cbe32cd5a65c6638e8f252b0bd8145e165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89545578"
---
# <a name="mspeer_conflictdetectionconfigresponse-transact-sql"></a>MSpeer_conflictdetectionconfigresponse(Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  피어 투 피어 복제에서 토폴로지 차원 구성 요청에 대한 각 노드의 응답을 저장하기 위해 사용됩니다. 이 테이블은 게시 데이터베이스에 저장됩니다.  
  
|열 이름|데이터 형식|Description|  
|-----------------|---------------|-----------------|  
|request_id|**int**|[MSpeer_conflictdetectionconfigrequest](../../relational-databases/system-tables/mspeer-conflictdetectionconfigrequest-transact-sql.md) 테이블에서 충돌 구성 요청 항목을 식별 합니다.|  
|peer_node|**sysname**|응답을 생성한 서버 인스턴스의 이름입니다.|  
|peer_db|**sysname**|응답을 생성한 피어에 있는 구독 데이터베이스입니다.|  
|peer_version|**sysname**|게시자의 버전 번호를 식별합니다.|  
|peer_db_version|**sysname**|피어 데이터베이스의 버전 번호를 식별합니다.|  
|is_peer|**bit**|노드가 읽기 전용 구독자인지 여부를 나타냅니다. 값 **0** 은 읽기 전용 구독자를 나타냅니다.|  
|conflict_detection_enabled|**bit**|토폴로지에 대해 충돌 검색을 사용할지 여부를 지정합니다.|  
|originator_id|**varbinary(16)**|충돌 감지를 위해 토폴로지의 각 노드를 식별합니다. 자세한 내용은 [Conflict Detection in Peer-to-Peer Replication](../../relational-databases/replication/transactional/peer-to-peer-conflict-detection-in-peer-to-peer-replication.md)을 참조하세요.|  
|peer_conflict_retention|**int**|메타데이터가 충돌 테이블에 저장된 기간(일 수)입니다.|  
|peer_subscriptions|**XML**|요청에 응답한 노드에 대한 정보입니다.|  
|progress_phase|**nvarchar(32)**|다음 값 중 하나를 사용하여 현재 처리 단계를 식별합니다.<br /><br /> 시작됨<br /><br /> Peer version collected<br /><br /> Status collected|  
|modified_date|**datetime**|단계가 완료된 날짜와 시간입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Transact-sql&#41;&#40;복제 테이블 ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [복제 뷰&#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
