---
title: カタログ関数の使用 |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: native-client|ODBC
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
caps.latest.revision: 36
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 6b778df7190da4b9aab69419c8487267a0911ff6
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37423761"
---
# <a name="using-catalog-functions"></a>カタログ関数の使用
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  どのようなデータベースであっても、その構造は、データベースに格納されたデータを保持するような構造になっています。 この構造の定義は、権限などその他の情報と共にカタログに保存されます。カタログは、システム テーブルのセットとして実装され、データ辞書と呼ばれることもあります。  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC ドライバーにより、アプリケーションで ODBC カタログ関数の呼び出しを通じて、データベースの構造を決定します。 カタログ関数は情報を結果セットとして返す関数で、カタログのシステム テーブルをクエリするカタログ ストアド プロシージャを使用して実装されます。 たとえば、アプリケーションが、システム上のすべてのテーブルに関する情報を含む結果セット、または特定のテーブルが持つすべての列に関する情報を含む結果セットを要求するとします。 この場合、標準の ODBC カタログ関数を使用して、アプリケーションが接続している [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] からカタログ情報を取得します。  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] は分散クエリをサポートします。分散クエリは、1 つのクエリで複数の異種 OLE DB データ ソースのデータにアクセスするクエリです。 リモートの OLE DB データ ソースへアクセスするための方法として、目的のデータ ソースをリンク サーバーとして定義する方法があります。 これを使用して行うことができます[sp_addlinkedserver](../../../relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql.md)します。 リンク サーバーを定義すると、このサーバーのオブジェクトを次のような 4 部構成の名前を使用して Transact-SQL ステートメントで参照できるようになります。  
  
 *linked_server_name.catalog.schema.object_name*.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC ドライバーでは、リンク サーバーからのカタログ情報の取得に役立つ、次の 2 つのドライバー固有の関数をサポートします。  
  
-   **SQLLinkedServers**  
  
     ローカル サーバーに定義されたリンク サーバーの一覧を返します。  
  
-   **SQLLinkedCatalogs**  
  
     リンク サーバーに含まれるカタログの一覧を返します。  
  
 リンク サーバー名とカタログ名を取得したら、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC ドライバーの 2 つの部分名を使用して、カタログから情報を取得をサポートしている*linked_server_name ***.*** カタログ*の*CatalogName*で次の ODBC カタログ関数。  
  
-   **SQLColumnPrivileges**  
  
-   **SQLColumns**  
  
-   **SQLPrimaryKeys**  
  
-   **SQLStatistics**  
  
-   **SQLTablePrivileges**  
  
-   **SQLTables**  
  
 2 つの部分*linked_server_name ***.*** カタログ*はサポートされても*FKCatalogName*と*PKCatalogName*で[SQLForeignKeys](../../../relational-databases/native-client-odbc-api/sqlforeignkeys.md)します。  
  
 SQLLinkedServers と SQLLinkedCatalogs を使用する場合は、次のファイルが必要です。  
  
-   sqlncli.h  
  
     リンク サーバーのカタログ関数の関数プロトタイプと定数定義を含むファイルです。 sqlncli.h を ODBC アプリケーションにインクルードし、アプリケーションのコンパイル時にはこのファイルをインクルード パスに配置しておく必要があります。  
  
-   sqlncli11.lib  
  
     リンカーのライブラリ パスに存在し、リンクされるファイルとして指定する必要があります。 sqlncli11.lib は、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC ドライバーに付属しています。  
  
-   sqlncli11.dll  
  
     実行時に存在する必要があります。 sqlncli11.dll は、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC ドライバーに付属しています。  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client &#40;ODBC&#41;](../../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)   
 [SQLColumnPrivileges](../../../relational-databases/native-client-odbc-api/sqlcolumnprivileges.md)   
 [SQLColumns](../../../relational-databases/native-client-odbc-api/sqlcolumns.md)   
 [SQLPrimaryKeys](../../../relational-databases/native-client-odbc-api/sqlprimarykeys.md)   
 [SQLTablePrivileges](../../../relational-databases/native-client-odbc-api/sqltableprivileges.md)   
 [SQLTables](../../../relational-databases/native-client-odbc-api/sqltables.md)   
 [SQLStatistics](../../../relational-databases/native-client-odbc-api/sqlstatistics.md)  
  
  
