---
title: ゴール シーク シナリオ (Excel 用テーブル分析ツール) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
caps.latest.revision: 22
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 2f17c85c7296daaead3b24b4d4002ad9c1be7221
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37187299"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a>ゴール シーク シナリオ (Excel 用のテーブル分析ツール)
  ![テーブル分析ツールのゴール シーク ボタン](media/tat-goalseek.gif "テーブル分析ツールのゴール シーク ボタン")  
  
 **ゴール シーク**シナリオ ツールを補完するものです、 [What-if](what-if-scenario-table-analysis-tools-for-excel.md)シナリオ ツール。 **What-if**ツールに指示する、変更の影響は、**ゴール シーク**ツールは、目的の結果を実現するために変更する必要がありますのある基になる要因を示します。  
  
 たとえば、顧客満足度を向上させることが目標であるとしましょう。 使用することができます**ゴール シーク**分析に最も可能性の高い顧客満足度を向上し、それらの変更はコスト効率の高いかどうかを決定する要因を判断します。  
  
 分析が完了すると、ソース データ テーブルに 2 つの新しい列が作成されます。 これらの列を表示する、*尤度*目的の結果を達成できると存在する場合は、推奨される変更します。  
  
 このツールでは、データのセットを分析し、そのセット全体を対象に予測を作成できます。また、分析を作成してから、シナリオを 1 つずつテストすることもできます。  
  
## <a name="using-the-goal-seek-scenario-tool"></a>ゴール シーク シナリオ ツールの使用  
  
1.  Excel テーブルを開きます。  
  
2.  クリックして**シナリオ**、選択と**ゴール シーク**します。  
  
3.  **シナリオ分析: ゴール シーク** ダイアログ ボックスで、一覧からターゲットを含む列の値を選択します。  
  
4.  達成しようとする値を指定します。  
  
     列の目標が連続する数値である場合は、目標とする値の増減を指定することもできます。 たとえば、選択した可能性があります**Sales**列としてし、ターゲットの 120% の増加を指定します。  
  
     または、上限と下限を入力して、値の範囲で目標を指定することもできます。  
  
5.  変更する値を含む列を指定します。 つまり、目的の結果を得るために操作する列を選択します。  
  
6.  必要に応じて、をクリックして**分析に使用する列の選択**、有用な情報が含まれている列を選択します。 分析に貢献しない列の選択は解除します。  
  
    > [!NOTE]  
    >  目標または変更に使用する列の選択は解除しないでください。 これらの列は必須です。  
  
7.  テーブル全体を対象に予測するか、選択した行のみを対象に予測するかを指定します。  
  
8.  選択した場合、**テーブル全体**オプション、ツール、予測を 2 つの新しい列のソース テーブルに追加します。  
  
9. オプションを選択した場合**この行で**分析の結果は確認のダイアログ ボックスを出力します。 さまざまな値や目標を引き続きテストすることができるように、このダイアログ ボックスは開いたままになります。  
  
### <a name="requirements"></a>要件  
 このツールでは、数値または不連続値を処理できる Microsoft ロジスティック回帰アルゴリズムが使用されます。  
  
 予測を複数回実行し、そのたびに異なる列を選択することもできますが、目標と変更の複数の組み合わせを同時に計算することはできません。  
  
 関連性の高い列を選択して分析を実行すると、より正確な結果が得られます。 ただし、対象となる列が少なすぎると、結果を得ることが難しくなる場合があります。  
  
 予測を 1 つずつ作成する場合は、目的の結果がまだ格納されていない行を選択してください。そうしないと、エラーが発生することがあります。 つまり、ゴール シークの目的が、自転車の購入動機となる要因を特定することである場合は、自転車を購入していない顧客だけを含める必要があります。  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a>ゴール シーク分析の結果について  
 ゴール シーク シナリオを作成すると、このツールによって次の 3 つ処理が行われます。  
  
-   テーブル内のデータに関する主要な要因を格納するデータ マイニング構造を作成する。  
  
-   データに基づいて、ロジスティック回帰マイニング モデルを作成する。  
  
-   指定された個々の値について予測を作成する。  
  
 ゴール シーク シナリオを 1 つずつテストする場合、結果を対話的に表示できます。 これは、作成する場合と同じ、*単一予測クエリ*します。  
  
 ツールのレポート、**結果**ウィンドウ、ダイアログ ボックスのボックスに希望の目標を達成するシナリオの検索に成功したかどうか。 適切な解決策が見つかった場合は、必要な変更を示す提案も生成されます。 たとえば、**ゴール シーク**ツールわかる場合があります、通勤距離が 5 マイル未満をする必要があります。  
  
 例の結果を次に示します。  
  
 **Interest in Buying のゴール シークで解が見つかりました。**  
  
 **最も近い一致を得ました ' 2-5 miles' に 'Commute distance' を変更します。**  
  
 この結果は、データ テーブルの既存の行に基づいて作成されています。つまり、特定の顧客について、他のすべての条件はそのままで、通勤距離だけを 2 ～ 5 マイルに減らした場合、その顧客は自転車を購入する可能性が高くなることを示しています。  
  
 指定することで、Excel テーブル内のすべての行のゴール シークの予測を作成する場合**テーブル全体**ツールは、元のデータ テーブルに 2 つの新しい列を作成します。 テーブルに追加される 1 つ目の列には、目標を満たすことが可能であれば、緑色の円にチェック マークが表示されます。また、どう変更しても目標を達成できない場合は、赤色の円に X 印が表示されます。  
  
 2 つ目の列には、推奨される変更が表示されます。  
  
> [!NOTE]  
>  推奨値の信頼度と予測の可否はアルゴリズムによってあらかじめ定義され、変更することはできません。  
  
## <a name="related-tools"></a>関連ツール  
 より高度なデータ マイニング機能を備えた別のアドインとして、Excel 用のデータ マイニング クライアントがあります。Excel 用のデータ マイニング クライアントには、行動を予測するデータ マイニング モデルを作成するためのウィザードが備わっています。 詳細については、次を参照してください。[データ マイニング モデルを作成する](creating-a-data-mining-model.md)します。  
  
 使用されるアルゴリズムの詳細については、**ゴール シーク**シナリオ ツールで、トピックの「Microsoft ロジスティック回帰アルゴリズム」を参照してください[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]オンライン ブックの「します。  
  
## <a name="see-also"></a>参照  
 [Excel 用テーブル分析ツール](table-analysis-tools-for-excel.md)  
  
  
