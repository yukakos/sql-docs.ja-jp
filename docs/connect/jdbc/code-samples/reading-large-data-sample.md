---
title: 大規模なデータを読み取るサンプル |Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 6c986144-3854-4352-8331-e79eccbefc28
caps.latest.revision: 28
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 51f1925c55fc3ece88aa8354afb181af8aec38ce
ms.sourcegitcommit: 6fa72c52c6d2256c5539cc16c407e1ea2eee9c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2018
ms.locfileid: "39278643"
---
# <a name="reading-large-data-sample"></a>大きなデータを読み取るサンプル
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  この [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] サンプル アプリケーションでは、[getCharacterStream](../../../connect/jdbc/reference/getcharacterstream-method-sqlserverresultset.md) メソッドを使用して [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] データベースから大きな単一列値を取得する方法を示します。  
  
 このサンプルのコード ファイルは ReadLargeData.java という名前で、次の場所にあります。  
  
 \<*インストール ディレクトリ*> \sqljdbc_\<*バージョン*>\\<*言語*> \samples\adaptive  
  
## <a name="requirements"></a>必要条件  
 このサンプル アプリケーションを実行するには、[!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)] サンプル データベースへのアクセス権が必要です。 また mssql jdbc jar ファイルをインクルードするためのクラスパスを設定します。 クラスパスを設定する方法の詳細については、次を参照してください。 [JDBC ドライバーを使用して](../../../connect/jdbc/using-the-jdbc-driver.md)します。  
  
> [!NOTE]  
>  [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] には、必要な Java ランタイム環境 (JRE) 設定に応じて使用される mssql-jdbc クラス ライブラリ ファイルが用意されています。 選択する JAR ファイルの詳細については、次を参照してください。 [JDBC Driver のシステム要件](../../../connect/jdbc/system-requirements-for-the-jdbc-driver.md)します。  
  
## <a name="example"></a>例  
 次の例のサンプル コードでは、[!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)] データベースへの接続を行います。 次に、サンプル データを作成し、パラメーター化クエリを使用して Production.Document テーブルを更新します。  
  
 さらに、このサンプル コードでは、[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) クラスの [getResponseBuffering](../../../connect/jdbc/reference/getresponsebuffering-method-sqlserverstatement.md) メソッドを使用してアダプティブ バッファリング モードを取得する方法も示されています。 JDBC Driver Version 2.0 リリース以降では、responseBuffering 接続プロパティが既定で "adaptive" に設定されていることに注意してください。  
  
 次に、サンプル コードでは、[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md) オブジェクトで SQL ステートメントを使用して、SQL ステートメントを実行し、返されたデータを [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) オブジェクトに配置します。  
  
 最後に、結果セット内のデータ行を繰り返し処理し、[getCharacterStream](../../../connect/jdbc/reference/getcharacterstream-method-sqlserverresultset.md) メソッドを使用してデータの一部にアクセスします。  
  
 [!code[JDBC#UsingAdaptiveBuffering1](../../../connect/jdbc/codesnippet/Java/reading-large-data-sample_1.java)]  
  
## <a name="see-also"></a>参照  
 [大きなデータの処理](../../../connect/jdbc/working-with-large-data.md)  
  
  
