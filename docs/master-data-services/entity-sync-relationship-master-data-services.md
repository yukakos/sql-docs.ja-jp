---
title: エンティティの同期関係 (マスター データ サービス) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: bd627a2d-dc64-47e9-9a71-2d0ad04b4962
caps.latest.revision: 6
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 27a3a66a9fb4b31e96f7a09082ba6867b36be722
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38046300"
---
# <a name="entity-sync-relationship-master-data-services"></a>エンティティの同期関係 [マスター データ サービス]

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  エンティティ同期は、エンティティのバージョン間での反復可能な一方向の同期です。 異なるモデルの間でエンティティ データを共有できます。 1 つのモデルで唯一の情報源を保持し、このマスター データをその他のモデルで再利用できます。 たとえば、1 つのモデル エンティティに米国の状態データを格納し、その他のモデルでそのデータを再利用できます。  
  
 エンティティの同期では、データのワンタイム コピーを行うこともできます。  
  
 同期の実行中に、自由形式のリーフ メンバーとソース エンティティ内のファイル属性がすべてターゲット エンティティに同期されます。 これにより、エンティティ スキーマとメンバーが作成、削除、変更されます。  
  
 一度同期関係が確立されると、ターゲット エンティティは同期プロセスによってのみ変更できます。 同期関係はいつでも削除して、ターゲット エンティティを編集可能にできます。  
  
## <a name="see-also"></a>参照  
 [エンティティの同期関係の作成と実行 (マスター データ サービス)](../master-data-services/create-and-execute-an-entity-sync-relationship-master-data-services.md)   
 [エンティティの同期関係の編集と削除 (マスター データ サービス)](../master-data-services/edit-and-delete-an-entity-sync-relationship-master-data-services.md)  
  
  
