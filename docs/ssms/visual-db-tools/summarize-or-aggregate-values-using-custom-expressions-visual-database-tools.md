---
title: カスタム式を使用して値を要約または集計する | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-visual-db
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- custom expressions to aggregate values [SQL Server]
ms.assetid: 34130ac1-0106-4766-b324-acb0b7bb6f6e
caps.latest.revision: 3
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 07d5e322c715f5aaec7a4fc713d87fac171c2a8c
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38040090"
---
# <a name="summarize-or-aggregate-values-using-custom-expressions-visual-database-tools"></a>カスタム式を使用して値を要約または集計する (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
集計関数を使用してデータを集計するだけでなく、カスタム式を作成して集計値を求めることもできます。 カスタム式は、集計クエリのどこでも集計関数の代わりに使用できます。  
  
たとえば、 `titles` テーブルでは、平均価格を表示するだけでなく、値下げした場合の平均価格を表示するクエリも作成できます。  
  
テーブルの一部の行だけに関連する計算を式で使用することはできません。式の計算時には集計値だけを使用できるため、集計値に基づく式を指定する必要があります。  
  
### <a name="to-specify-a-custom-expression-for-a-summary-value"></a>集計値にカスタム式を指定するには  
  
1.  検索するグループを指定します。 詳しくは、「[クエリ結果内の行のグループ化 (Visual Database Tools)](../../ssms/visual-db-tools/group-rows-in-query-results-visual-database-tools.md)」をご覧ください。  
  
2.  抽出条件ペインの空白行に移動し、**[列]** 列に式を入力します。  
  
    クエリ出力にわかりやすい列ヘッダーを作成できるように、[クエリおよびビュー デザイナー](../../ssms/visual-db-tools/query-and-view-designer-tools-visual-database-tools.md)により、式に列の別名が自動的に割り当てられます。 詳細については、「[列の別名の作成 (Visual Database Tools)](../../ssms/visual-db-tools/create-column-aliases-visual-database-tools.md)」を参照してください。  
  
3.  式の **[グループ化]** 列で、**[式]** をクリックします。  
  
4.  クエリを実行します。  
  
## <a name="see-also"></a>参照  
[クエリ結果の並べ替えおよびグループ化 (Visual Database Tools)](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
[クエリ結果の要約 (Visual Database Tools)](../../ssms/visual-db-tools/summarize-query-results-visual-database-tools.md)  
  
