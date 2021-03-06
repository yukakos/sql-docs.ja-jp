---
title: カテゴリ (Excel 用テーブル分析ツール) の検出 |Microsoft Docs
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
- clustering [data mining]
- mining model, decision tree
- category detection
ms.assetid: 3c7e9ebb-d0c9-498e-a9ba-cc13eaa43520
caps.latest.revision: 19
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 9b64ca60b977037b62240571cb77e3c4ad7d516f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37282368"
---
# <a name="detect-categories-table-analysis-tools-for-excel"></a>カテゴリの検出 (Excel 用のテーブル分析ツール)
  ![リボンの [Categories] ボタンを検出](media/tat-detectcat.gif "でリボン カテゴリの検出 ボタン")  
  
 **カテゴリの検出**ツールは自動的に特性が似ているテーブルの行を見つけます。  
  
 このツールの処理が完了すると、検出されたカテゴリおよびその特徴を示すレポートが作成されます。 既定では、データの行ごとに、検出されたカテゴリを含む新しい列がデータ テーブルに追加されます。 後でそのカテゴリを確認し、名前を変更することができます。  
  
## <a name="using-the-detect-categories-tool"></a>カテゴリの検出ツールの使用  
  
1.  Excel テーブルを開きます。  
  
2.  クリックして**カテゴリの検出**します。  
  
3.  分析に使用する列を指定します。 個人名やレコード ID などの一意な値を含む列は分析に役立たないため、選択を外すことができます。  
  
4.  作成するカテゴリの最大数を指定することもできます。 既定では、検出された数のカテゴリが自動的に作成されます。  
  
5.  **[実行]** をクリックします。  
  
6.  カテゴリとその特性の一覧が記載された "カテゴリのレポート" という名前の新規ワークシートが作成されます。  
  
 ツールのオプションを指定する方法の詳細については、次を参照してください。[検出カテゴリ ダイアログ ボックス (Excel 用テーブル分析ツール)](detect-categories-table-analysis-tools-for-excel.md)します。  
  
## <a name="understanding-the-categories-report"></a>カテゴリのレポートについて  
 **カテゴリのレポート**、2 つのテーブルを含む**カテゴリ一覧**と**カテゴリの特性**、および**カテゴリ プロファイル**グラフ。  
  
### <a name="category-list"></a>カテゴリの一覧  
 最初のテーブルは、検出されたカテゴリを示します。 **行数**列は、データの行の数は、各カテゴリに割り当てられたことを示します。  
  
 モデルは、各カテゴリに対応する一時的な名前を作成しますが、カテゴリを好みの名前に変更することもできます。 たとえば、次の例では、最初のカテゴリ名前が変更された**低収入**クラスターの最も重要な属性であったためです。  
  
 ![レポートのカテゴリの検出ツールによって作成される](media/dm13-tat-detectcat-report1.gif "カテゴリの検出ツールによって作成されたレポート")  
  
 新しいラベルを入力するとすぐに、その他のすべてのグラフのほかに、ソース データのワークシートに追加されたカテゴリの一覧にも反映されます。  
  
### <a name="category-characteristics"></a>カテゴリの特性  
 2 番目のテーブルでは、**カテゴリの特性**、各カテゴリの構成の詳細が表示されます。 をクリックして、**フィルター**の上部にある、**カテゴリ**列を 1 つまたは少数のカテゴリにフォーカスを参照してください。  
  
 ![レポートのカテゴリの検出ツールによって作成される](media/dm13-tat-detectcat-report2.gif "カテゴリの検出ツールによって作成されたレポート")  
  
 列で、網掛け**相対的な重要度**、ことを示します属性と値の組み合わせが特徴的要因としては、重要な方法です。 バーが長いほど、そのカテゴリの代表的な属性である可能性が高くなります。  
  
### <a name="categories-profile-chart"></a>カテゴリ プロファイル グラフ  
 最後のグラフで、**カテゴリのレポート**ワークシート**カテゴリ プロファイル**は対話型**ピボット グラフ**再配置、フィールドを非表示にして、値をフィルター処理に使用できます。、およびグラフの外観をカスタマイズします。  
  
 Excel 2013 が提供するようになりました**グラフのスタイル**と**グラフ要素**をグラフのデザインを向上させるために簡単にするデザイン サーフェイスで権利を制御します。  
  
 ![レポートのカテゴリの検出ツールによって作成される](media/dm13-tat-detectcat-report3.gif "カテゴリの検出ツールによって作成されたレポート")  
  
## <a name="requirements"></a>要件  
 **カテゴリの検出**ツール量やデータの種類の要件がありません。  
  
> [!NOTE]  
>  使用すると、**カテゴリの検出**ツール、元のデータ テーブルにカテゴリで、新しい列を作成、します。 データ テーブルにこの列を残したままデータ マイニング処理を実行すると、この列が結果に影響することがあります。 他の処理に影響を及ぼさないようにするために、他のデータ マイニング ツールを使用する前に "カテゴリ" 列を含まないデータ テーブルのコピーを作成しておく必要があります。  
  
## <a name="related-tools"></a>関連ツール  
 ときに、**カテゴリの検出**ツールは、データを分析しを使用してデータ マイニング構造とデータ マイニング モデルを作成、[!INCLUDE[msCoName](../includes/msconame-md.md)]クラスタ リング アルゴリズムです。  
  
 使用してデータ マイニング モデルを作成した後、**分析の主要な影響元**ツールで、モデルの参照し、関係を詳しく調べたりする Excel 用データ マイニング クライアントを使用することができます。 Excel 用のデータ マイニング クライアントは、より詳細なデータ マイニング機能を備えた独立したアドインです。 詳しくは、次を参照してください。 [Excel におけるモデルの参照&#40;SQL Server データ マイニング アドイン&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md)します。  
  
 詳細については、データ モデリング、Excel 用データ マイニング クライアントでの機能を使用して、次を参照してください。[データ マイニング モデルを作成する](creating-a-data-mining-model.md)します。  
  
 使用されるアルゴリズムの詳細については、**カテゴリの検出**ツールで、トピックの「Microsoft クラスタ リング アルゴリズム」を参照してください[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]オンライン ブックの「します。  
  
## <a name="see-also"></a>参照  
 [Excel 用テーブル分析ツール](table-analysis-tools-for-excel.md)  
  
  
