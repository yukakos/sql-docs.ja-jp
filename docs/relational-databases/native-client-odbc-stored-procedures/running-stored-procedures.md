---
title: ストアド プロシージャを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 179068eed7b131a237176e94974f39daa8685b33
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37415651"
---
# <a name="running-stored-procedures"></a>ストアド プロシージャの実行
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  ストアド プロシージャは、データベースに保存される実行可能なオブジェクトです。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では次に示すオブジェクトをサポートしています。  
  
-   ストアド プロシージャ:  
  
     1 つの実行可能なプロシージャとしてプリコンパイルされた 1 つ以上の SQL ステートメント。  
  
-   拡張ストアド プロシージャ :   
  
     拡張ストアド プロシージャ用の SQL Server オープン データ サービス API に記述された、C または C++ のダイナミック リンク ライブラリ (DLL)。 オープン データ サービス API によりストアド プロシージャの機能が拡張され、C または C++ のコードを実装できるようになります。  
  
 ステートメントの実行時、データ ソースに対して (クライアント アプリケーション内でステートメントを直接実行または準備せずに) ストアド プロシージャを呼び出すと、次のような利点があります。  
  
-   パフォーマンスの向上  
  
     SQL ステートメントは、プロシージャが作成される時点で、解析およびコンパイルされます。 プロシージャの実行時には、これらの作業は必要ありません。  
  
-   ネットワーク オーバーヘッドの軽減  
  
     複雑なクエリをネットワーク経由で送信するのではなく、プロシージャを実行することで、ネットワーク トラフィックを削減できます。 ODBC アプリケーションが ODBC { CALL } 構文を使用してストアド プロシージャを実行すると、ODBC ドライバーがさらに最適化を行い、パラメーター データの変換が不要になります。  
  
-   一貫性を向上.  
  
     組織の規則がストアド プロシージャなどの 1 つのリソースに集約して実装されると、コーディング、テスト、デバッグを一度で行えます。 各プログラマが独自の実装を開発するのではなく、テスト済みの共通のストアド プロシージャを使用できます。  
  
-   精度の向上  
  
     通常、ストアド プロシージャは経験を積んだプログラマが開発するので、技術レベルの異なるプログラマが繰り返し手を加えたコードに比べて、効率的でエラーが少なくなる傾向があります。  
  
-   機能の追加  
  
     拡張ストアド プロシージャは、[!INCLUDE[tsql](../../includes/tsql-md.md)] ステートメントでは使用できない C や C++ の機能を使用できます。  
  
     ストアド プロシージャを呼び出す方法の例は、次を参照してください。[プロセスのリターン コードと出力パラメーター &#40;ODBC&#41;](../../relational-databases/native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ストアド プロシージャの呼び出し](../../relational-databases/native-client-odbc-stored-procedures/calling-a-stored-procedure.md)  
  
-   [ストアド プロシージャ呼び出しのバッチ化](../../relational-databases/native-client-odbc-stored-procedures/batching-stored-procedure-calls.md)  
  
-   [ストアド プロシージャの結果の処理](../../relational-databases/native-client-odbc-stored-procedures/processing-stored-procedure-results.md)  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client &#40;ODBC&#41;](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)   
 [ストアド プロシージャの操作方法に関するトピックを実行している&#40;ODBC&#41;](http://msdn.microsoft.com/library/c2220182-a23d-4475-b353-77a77ab613d6)  
  
  
