---
title: シーケンス クラスターのクラスターの特性 タブ (マイニング モデル ビューアー) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.sequenceclustering.characteristics.f1
ms.assetid: 3a9e8a0c-7d03-47cc-8625-e68d73a8c947
caps.latest.revision: 23
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4272975a16da0cf0d9db534df34d00e329dc5430
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37153183"
---
# <a name="sequence-clustering-cluster-characteristics-tab-mining-model-viewer"></a>シーケンス クラスターの [クラスターの特性] タブ (マイニング モデル ビューアー)
  **Microsoft シーケンス クラスター ビューアー**の **[クラスターの特性]** タブには、シーケンス クラスターを定義する属性の詳細な一覧が表示されます。 これらの特性には、単純な属性と値のペアと、状態間の遷移が含まれる可能性があります。  
  
 クラスターの内容をドリル ダウンし、クラスターの代表となるシーケンスを確認するには、シーケンス クラスター モデルのこのビューを使用します。  
  
 **詳細:** [Microsoft シーケンス クラスター アルゴリズム](data-mining/microsoft-sequence-clustering-algorithm.md)、[Microsoft シーケンス クラスター ビューアーを使用したモデルの参照](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)  
  
## <a name="options"></a>および  
 **ビューアーのコンテンツを更新します。**  
 ビューアーにマイニング モデルを再読み込みします。  
  
 **[マイニング モデル]**  
 現在のマイニング構造に含まれているマイニング モデルから、表示するモデルを選択します。 関連付けられているビューアーが開き、マイニング モデルが表示されます。  
  
 **ビューアー**  
 選択したマイニング モデルを調べるために使用するビューアーを選択します。 カスタム ビューアーまたは **Microsoft 汎用コンテンツ ツリー ビューアー**を使用できます。 利用可能な場合プラグイン ビューアーを使用することもできます。  
  
 **Cluster**  
 表示するクラスターを選択します。  
  
 **特性の\<クラスター >**  
 このテーブルは、現在のクラスターに割り当てられたシーケンスを、確率順に一覧表示します。 シーケンスは基本的には 1 組の属性と値のペアであり、後ろに 1 組または複数組の属性と値のペアが追加されます。 各クラスターの特性は、シーケンスと確率の組み合わせによって定義されます。  
  
 たとえば、マーケット バスケット分析に基づくシーケンス クラスター モデルでは、特売品の選択後、他の商品を購入せずに取引を終了する顧客を最上位特性とするクラスターが考えられます。 サーバー障害の解析を目的とするシーケンス クラスター モデルでは、クラスターの第 1 の特性は、発生頻度の高いエラー イベントになる可能性があります。  
  
|値|説明|  
|-----------|-----------------|  
|**変数**|この列は、遷移、または、特性が値かどうかを示します。<br /><br /> 特性が、値の場合、**変数**列には、属性名が含まれています。<br /><br /> 特性が状態遷移を表している場合、**変数**列には「転移」が含まれています。|  
|**値**|この列の値は、特性が、単純な属性値のペアであるかどうか、または一般的なアイテムまたはイベントのシーケンスを表す状態遷移に依存します。<br /><br /> 特性が、値の場合、**値**列には、状態が含まれています。<br /><br /> 特性が状態遷移を表している場合、**値**列には、状態遷移の説明が含まれています。|  
|**確率**|この列には、特性 (単純な属性と値のペアまたは状態の組み合わせ) が現在のクラスターのメンバーである相対的確率を示すバーが表示されます。<br /><br /> バーの上にマウスを移動することで、特性の頻度の値を表示できます。|  
  
## <a name="see-also"></a>参照  
 [データ マイニング アルゴリズム&#40;Analysis Services - データ マイニング&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [マイニング モデル ビューアー&#40;データ マイニング モデル デザイナー&#41;](mining-model-viewers-data-mining-model-designer.md)   
 [データ マイニング モデル ビューアー](data-mining/data-mining-model-viewers.md)  
  
  
