---
title: Java EE のサポートについて |Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: a9448b80-b7a3-49cf-8bb4-322c73676005
caps.latest.revision: 26
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 5d5cc306a407e818a79d67cfc4c4340e1a9c2b22
ms.sourcegitcommit: 6fa72c52c6d2256c5539cc16c407e1ea2eee9c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2018
ms.locfileid: "39278863"
---
# <a name="understanding-java-ee-support"></a>Java EE のサポートについて
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  以下のセクションでは、[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] が Java Platform, Enterprise Edition (Java EE) および JDBC 3.0 のオプションの API 機能をサポートするしくみについて説明します。 このヘルプ システムで提供されるソース コード例は、これらの機能を使用するための優れた参考資料となります。  
  
 まず、使用している Java 環境 (JDK、JRE) に javax.sql パッケージが含まれていることを確認してください。 このパッケージは、オプションの API を使用するすべての JDBC アプリケーションに必須です。 JDK 1.5 以降のバージョンには、このパッケージが既に含まれているので、別途インストールする必要はありません。  
  
## <a name="driver-name"></a>ドライバー名  
 このドライバーのクラス名は、**com.microsoft.sqlserver.jdbc.SQLServerDriver** です。 JDBC Driver 4.1、4.2、6.0 の場合、このドライバーは sqljdbc.jar、sqljdbc4.jar、sqljdbc41.jar、または sqljdbc42.jar ファイルに含まれています。 JDBC Driver 6.2 のドライバーは、mssql の jdbc-6.2.1.jre7.jar または mssql-jdbc-6.2.1.jre8.jar に含まれます。 JDBC Driver 6.4 では、ドライバーは、mssql-jdbc-6.4.0.jre7.jar、mssql jdbc-6.4.0.jre8.jar または mssql-jdbc-6.4.0.jre9.jar に含まれます。
  
 このクラス名は、JDBC DriverManager クラスを使用してドライバーを読み込むたびに使用されます。 また、ドライバー構成でドライバーのクラス名を指定する必要があるときにも使用されます。 たとえば、Java EE アプリケーション サーバー内でデータ ソースを構成するには、ドライバーのクラス名を入力する必要が生じる場合があります。  
  
## <a name="data-sources"></a>ソリューション エクスプローラー  
 この JDBC ドライバーは、Java EE または JDBC 3.0 データ ソースをサポートします。 この JDBC ドライバーの [SQLServerXADataSource](../../connect/jdbc/reference/sqlserverxadatasource-class.md) クラスは、**com.microsoft.sqlserver.jdbc.SQLServerXADataSource** によって実装されています。  
  
### <a name="datasource-names"></a>データ ソース名  
 データ ソースを使用して、データベース接続を確立できます。 次の表は、JDBC ドライバーで使用できるデータ ソースを示しています。  
  
|データ ソースの種類|クラスの名前と説明|  
|---------------|--------------------------|  
|DataSource|com.microsoft.sqlserver.jdbc.SQLServerDataSource <br/> <br/> 非プーリング データ ソース。|  
|ConnectionPoolDataSource|com.microsoft.sqlserver.jdbc.SQLServerConnectionPoolDataSource <br/> <br/> JAVA EE アプリケーション サーバー接続プールを構成するデータ ソース。 通常は、アプリケーションが JAVA EE アプリケーション サーバー内で実行される場合に使用されます。|  
|XADataSource|com.microsoft.sqlserver.jdbc.SQLServerXADataSource <br/> <br/> JAVA EE XA データ ソースを構成するデータ ソース。 通常は、アプリケーションが JAVA EE アプリケーション サーバーおよび XA トランザクション マネージャー内で実行される場合に使用されます。|  
  
### <a name="data-source-properties"></a>データ ソースのプロパティ  
 すべてのデータ ソースは、基になるドライバーのプロパティ セットに関連付けられているプロパティを設定または取得する機能をサポートします。  
  
 例 :  
  
 `setServerName("localhost");`  
  
 `setDatabaseName("AdventureWorks");`  
  
 以下は、アプリケーションがデータ ソースを使用して接続するしくみを示しています。  
  
```java
initialize JNDI ..  
Context ctx = new InitialContext(System.getProperties());  
...  
DataSource ds = (DataSource) ctx.lookup("MyDataSource");  
Connection c = ds.getConnection("user", "pwd");  
```  
  
 データ ソースのプロパティの詳細については、次を参照してください。[データ ソースのプロパティを設定](../../connect/jdbc/setting-the-data-source-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [JDBC ドライバーの概要](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
  
  
