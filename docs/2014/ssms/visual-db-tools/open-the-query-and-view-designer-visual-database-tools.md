---
title: クエリおよびビュー デザイナーを開く (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
caps.latest.revision: 11
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 21c6185322364fe4d8f612b29f9ef081852dae2f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37259928"
---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a>クエリおよびビュー デザイナーを開く (Visual Database Tools)
  ビューの定義を開いたり、クエリまたはビューの結果を表示したり、クエリを作成したり開いたりすると、クエリおよびビュー デザイナーが開きます。 クエリおよびビュー デザイナーは、4 つの個別のペインで構成されています。  
  
-   ダイアグラム ペインには、データ接続で選択したテーブルまたはテーブル値オブジェクトが、グラフィカルに表示されます。 また、テーブル間の結合リレーションシップも示されます。  
  
-   抽出条件ペインでは、表示するデータ列、結果の順序、選択する行などのクエリ オプションを選択してスプレッドシート形式のグリッドに入力することにより、クエリ オプションを指定できます。  
  
-   SQL ペインでは、任意の SQL ステートメントを作成できます。抽出条件ペインおよびダイアグラム ペインでも SQL ステートメントを作成できますが、どちらの場合も SQL ステートメントは SQL ペインに作成されます。 クエリを作成すると、SQL ペインは自動的に更新され、読みやすいように書式が変更されます。  
  
-   結果ペインには、最後に実行された選択クエリの結果が表示されます。 他の種類のクエリ結果は、メッセージ ボックスに表示されます。  
  
-   これらのペインはクエリおよびビューを操作する場合に便利です。  
  
-   ビューまたはクエリを開くと、いくつかのペインまたはすべてのペインがビューまたはクエリと共に開きます。 どのペインが開くかは、 **[オプション]** ダイアログ ボックスの設定、および接続しているデータベース管理システムの種類によって異なります。 既定の設定では、4 つすべてが開きます。  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a>クエリおよびビュー デザイナーでビューを開くには  
  
1.  オブジェクト エクスプローラーで、開くビューを右クリックし、 **[デザイン]** または **[ビューを開く]** をクリックします。  
  
     **[デザイン]** を選択すると、 **[オプション]** ダイアログ ボックスで選択したオプションに従い、クエリおよびビュー デザイナーのペインが開きます。 **[ビューを開く]** を選択すると、既定で結果ペインのみが開きます。  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a>クエリおよびビュー デザイナーで既存のクエリを開くには  
  
1.  ソリューション エクスプローラーで、 **[クエリ]** フォルダーを展開します。  
  
2.  開くクエリをダブルクリックします。  
  
3.  クエリ ステートメントを強調表示し、強調表示された領域を右クリックして、 **[エディターでクエリをデザイン]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [クエリおよびビューの操作方法に関するトピックを設計&#40;Visual Database Tools&#41;](visual-database-tools.md)   
 [クエリおよびビュー デザイナー ツール (Visual Database Tools)](query-and-view-designer-tools-visual-database-tools.md)  
  
  
