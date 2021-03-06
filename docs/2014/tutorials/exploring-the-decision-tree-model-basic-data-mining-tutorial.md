---
title: デシジョン ツリー モデル (基本的なデータ マイニング チュートリアル) の検証 |Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 2e1472c2-3f3e-4dae-acb3-62fca374d397
caps.latest.revision: 37
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: acc02a144a507ee90fb311cb44445816097b1c16
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37204454"
---
# <a name="exploring-the-decision-tree-model-basic-data-mining-tutorial"></a>デシジョン ツリー モデルの検証 (基本的なデータ マイニング チュートリアル)
  [!INCLUDE[msCoName](../includes/msconame-md.md)] デシジョン ツリー アルゴリズムは、自転車の購入に影響する列をトレーニング セットのその他の列に基づいて予測します。  
  

  
##  <a name="Decision_Tree_Tab"></a> デシジョン ツリー タブ  
 **デシジョン ツリー**  タブで、データセット内のすべての予測可能な属性のデシジョン ツリーを表示できます。  
  
 ここでは、モデルは、1 つだけ表示されるツリーがあるために、自転車購入者のみに 1 つの列を予測します。 使用することが多くのツリーがある場合は、**ツリー**ボックスを別のツリーを選択します。  
  
 表示すると、`TM_Decision_Tree`モデル、デシジョン ツリー ビューアーで、グラフの左側にある最も重要な属性を確認できます。 "最も重要" とは、これらの属性が結果に最も大きな影響を及ぼすことを意味します。 ツリーの下寄り (グラフの右側) にある属性は、あまり大きな効果を及ぼしません。  
  
 この例では、自転車購入の予測にとって最も重要な要素は年齢です。 このモデルは顧客を年齢でグループ化し、年齢グループごとに、次に重要な属性を示します。 たとえば、34 歳から 40 歳の顧客グループでは、年齢の次に強い予測子は所有している自動車の台数です。  
  
#### <a name="to-explore-the-model-in-the-decision-tree-tab"></a>[デシジョン ツリー] タブでモデルを調査するには  
  
1.  選択、**マイニング モデル ビューアー** ] タブの [**データ マイニング デザイナー**します。  
  
     既定では、デザイナーはこの場合、--構造に追加された最初のモデルが開きます。`TM_Decision_Tree`します。  
  
2.  虫眼鏡ボタンを使用してツリーの表示サイズを調整します。  
  
     既定では、ツリーの上位 3 レベルのみが [!INCLUDE[msCoName](../includes/msconame-md.md)] ツリー ビューアーに表示されます。 ツリーの階層が 3 レベル未満の場合は、既存のすべてのレベルがビューアーに表示されます。 多くのレベルを表示するにを使用して、**レベルの表示**スライダーまたは**既定の展開**一覧。  
  
3.  スライド**レベルの表示**4 つ目のバーにします。  
  
4.  変更、**バック グラウンド**値を`1`します。  
  
     変更することで、**バック グラウンド**設定すると、すぐにわかりますのターゲット値を持つ各ノード内のケースの数`1`[Bike Buyer] にします。 このシナリオでは、各ケースが顧客を表すことに注意してください。 値`1`、顧客が、自転車を購入したことを示します値**0**顧客が自転車を購入していないことを示します。 ノードの色が濃いほど、対象の値を持つケースの割合が高いことを示します。  
  
5.  カーソルを置くというラベルの付いたノード**すべて**します。 ツールヒントに次の情報が表示されます。  
  
    -   ケースの総数  
  
    -   自転車を購入していないケースの数  
  
    -   自転車を購入したケースの数  
  
    -   [Bike Buyer] の値がないケースの数  
  
     そのほか、ツリーの任意のノードの上にカーソルを置いて、直前のノードからそのノードに到達するために必要な条件を表示することもできます。 この同じ情報を表示することも、**マイニング凡例**します。  
  
6.  ノードをクリックして**Age > = 34 and < 41**します。 ノード上の細い横棒としてヒストグラムが表示されます。ヒストグラムは、その年齢層の顧客の、以前に自転車を購入した顧客 (ピンク) と購入していない顧客 (青) の分布を表します。 ビューアーからは、車の所有台数が 0 ～ 1 台の 34 ～ 40 歳の顧客が自転車を購入する可能性が高いことがわかります。 さらに詳しく見ると、顧客の年齢が 38 ～ 40 歳の場合にはその可能性がさらに高くなることもわかります。  
  
 ここでは、構造とモデルを作成したときにドリルスルーを有効にしてあるため、モデル ケースやマイニング構造から詳細情報を取得することができます。これには、マイニング モデルには含まれていなかった列 (emailAddress や FirstName など) も含まれます。  
  
 詳細については、「[ドリルスルー クエリ &#40;データ マイニング&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)」を参照してください。  
  
#### <a name="to-drill-through-to-case-data"></a>ケース データにドリルスルーするには  
  
1.  ノードを右クリックして**ドリル スルー**し**モデル列のみ**します。  
  
     各トレーニング ケースの詳細がスプレッドシート形式で表示されます。 これらの詳細は、マイニング構造を作成するときにケース テーブルとして選択した vTargetMail ビューから取得されています。  
  
2.  ノードを右クリックして**ドリル スルー**し**モデルおよび構造列**します。  
  
     同じスプレッドシートの末尾に構造列が追加されて表示されます。  
  
  
###  <a name="Dependency_Network_Tab"></a> 依存関係ネットワーク タブ  
 **依存関係ネットワーク** タブには、マイニング モデルの予測的な機能に影響を与える属性間のリレーションシップが表示されます。 依存関係ネットワーク ビューアーを使用すると、自転車の購入の予測において Age と Region が重要な要素になるという先ほどの調査結果が補強されます。  
  
##### <a name="to-explore-the-model-in-the-dependency-network-tab"></a>[依存関係ネットワーク] タブでモデルを調査するには  
  
1.  をクリックして、`Bike Buyer`その依存関係を識別するためにノード。  
  
     依存関係ネットワークの中心ノード`Bike Buyer`、マイニング モデルの予測可能な属性を表します。 このグラフでは、予測可能な属性に影響を及ぼす、接続しているすべてのノードが強調表示されます。  
  
2.  調整、**すべてリンク**最も影響力のある属性を識別するスライダー。  
  
     スライダーをドラッグすると、[Bike Buyer] 列に弱い影響のみを持つ属性ですが、グラフから削除されます。 スライダーを調整すると、顧客が自転車を購入するかどうかの予測は、年齢と地域に最も大きく左右されることがわかります。  
  
## <a name="related-tasks"></a>Related Tasks  
 他の種類のモデルを使用してデータを探索するには、次のトピックを参照してください。  
  
-   [クラスター モデルの検証&#40;基本的なデータ マイニング チュートリアル&#41;](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [Naive Bayes モデルの検証&#40;基本的なデータ マイニング チュートリアル&#41;](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a>このレッスンの次の作業  
 [クラスター モデルの検証&#40;基本的なデータ マイニング チュートリアル&#41;](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>参照  
 [マイニング モデル ビューアーのタスクと操作方法](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md)   
 [デシジョン ツリー タブ&#40;マイニング モデル ビューアー&#41;](../../2014/analysis-services/decision-tree-tab-mining-model-viewer.md)   
 [依存関係ネットワーク タブ&#40;マイニング モデル ビューアー&#41;](../../2014/analysis-services/dependency-network-tab-mining-model-viewer.md)   
 [Microsoft ツリー ビューアーを使用したモデルの参照](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-tree-viewer.md)  
  
  
