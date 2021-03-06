---
title: '手順 2: 破損ファイルの作成 | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: tutorial
applies_to:
- SQL Server 2016
ms.assetid: cd0b18dc-66c3-4d88-86ef-8e40cb660fae
caps.latest.revision: 23
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 017b2b117d8ca43cc9772575343f4047786f63bd
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2018
ms.locfileid: "35406554"
---
# <a name="lesson-4-2---creating-a-corrupted-file"></a>レッスン 4-2 - 破損ファイルの作成
変換エラーの構成と処理を体験するために、コンポーネントの処理が失敗するサンプル フラット ファイルを作成します。  
  
この実習では、既存のサンプル フラット ファイルのコピーを作成します。 その後、このファイルをメモ帳などで開き、 **CurrencyID** 列を編集して、参照変換中に照合が失敗するようにします。 新しいファイルの処理時、参照が失敗すると Lookup Currency Key 変換は失敗し、それ以降のパッケージも失敗します。 破損しているサンプル ファイルを作成したら、パッケージを実行して、パッケージのエラーを確認します。  
  
### <a name="to-create-a-corrupted-sample-flat-file"></a>破損しているサンプル フラット ファイルを作成するには  
  
1.  メモ帳などのテキスト エディターで Currency_VEB.txt ファイルを開きます。  
  
    このサンプル データは、SSIS のレッスン パッケージに含まれています。 サンプル データとレッスン パッケージをダウンロードするには、次の手順を実行します。  
  
    1.  「 [Integration Services 製品サンプル](http://go.microsoft.com/fwlink/?LinkID=267527)」に移動します。  
  
    2.  **[ダウンロード]** タブをクリックします。  
  
    3.  SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip ファイルをクリックします。  
  
2.  テキスト エディターの検索置換機能を使用し、 **VEB** と表示されているすべての箇所を **BAD**に置換します。  
  
3.  他のサンプル データ ファイルと同じフォルダーに、修正したファイルを保存します。このファイルには「 **Currency_BAD.txt**」という名前を付けてください。  
  
    > [!IMPORTANT]  
    > **Currency_BAD.txt** は、他のサンプル データ ファイルと同じフォルダーに保存されていることを確認してください。  
  
4.  テキスト エディターを閉じます。  
  
### <a name="to-verify-that-an-error-will-occur-during-run-time"></a>実行時にエラーが発生することを確認するには  
  
1.  **[デバッグ]** メニューの **[デバッグの開始]** をクリックします。  
  
    データ フローの 3 つ目の反復処理で、Lookup Currency Key 変換が Currency_BAD.txt ファイルを処理しようとし、変換が失敗します。 この変換エラーにより、パッケージ全体が失敗します。  
  
2.  **[デバッグ]** メニューの **[デバッグの停止]** をクリックします。  
  
3.  デザイン画面で、 **[実行結果]** タブをクリックします。  
  
4.  ログの内容を参照し、次の処理不能エラーが発生していることを確認します。  
  
    `[Lookup Currency Key[27]] Error: Row yielded no match during lookup.`  
  
    > [!NOTE]  
    > 数値 27 はコンポーネントの ID です。 この値はデータ フローを構築したときに割り当てられるもので、パッケージの値とは異なることがあります。  
  
## <a name="next-steps"></a>Next Steps  
[手順 3 : エラー フロー リダイレクトの追加](../integration-services/lesson-4-3-adding-error-flow-redirection.md)  
  
  
  
