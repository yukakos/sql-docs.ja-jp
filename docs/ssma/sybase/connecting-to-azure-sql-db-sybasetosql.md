---
title: Azure SQL DB (SybaseToSQL) への接続 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 9e77e4b0-40c0-455c-8431-ca5d43849aa7
caps.latest.revision: 7
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: fb395aeb1a408701a9677b879f139d3538ae7fee
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34778498"
---
# <a name="connecting-to-azure-sql-db-sybasetosql"></a>Azure SQL DB (SybaseToSQL) に接続します。
Sybase データベースを Azure SQL DB を移行するには、Azure SQL DB のターゲット インスタンスに接続する必要があります。 接続するときに、SSMA は Azure SQL DB のインスタンス内のすべてのデータベースに関するメタデータを取得し、Azure SQL DB メタデータ エクスプ ローラーでデータベースのメタデータを表示します。 SSMA は、Azure SQL DB に、接続しているが、パスワードを保存しないのインスタンスの情報を格納します。  
  
プロジェクトを閉じるまで、Azure SQL DB への接続がアクティブな保たれます。 プロジェクトを再度開くと、アクティブなサーバーに接続する場合 Azure SQL DB に再接続する必要があります。 Azure SQL DB にデータベース オブジェクトを読み込むし、データを移行するまで、オフライン作業できます。  
  
Azure SQL DB のインスタンスに関するメタデータが自動的に同期されていません。 代わりに、Azure SQL DB メタデータ エクスプ ローラー内のメタデータを更新するには、Azure SQL DB メタデータを手動で更新する必要があります。 詳細については、このトピックの「「同期する Azure SQL DB メタデータ」セクションを参照してください。  
  
## <a name="required-azure-sql-db-permissions"></a>Azure SQL DB のアクセス許可が必要  
Azure SQL DB への接続に使用されるアカウントには、アカウントが実行する操作に応じて異なるアクセス許可が必要です。  
  
1.  Sybase オブジェクトに変換する[!INCLUDE[tsql](../../includes/tsql_md.md)]スクリプトの構文は、Azure SQL DB からメタデータを更新するかに変換された構文を保存する、アカウントは Azure SQL DB のインスタンスにログオンする権限が必要です。  
  
2.  データベース オブジェクトを Azure SQL DB に読み込むには、最小限のアクセス許可の要件は、メンバーシップ、 **db_owner**ターゲット データベースのデータベース ロール。  
  
## <a name="establishing-a-azure-sql-db-connection"></a>Azure SQL DB の接続を確立します。  
Sybase データベース オブジェクトを Azure SQL DB の構文に変換する前に、Sybase データベースやデータベースを移行する Azure SQL DB のインスタンスへの接続を確立する必要があります。  
  
接続のプロパティを定義するときは、オブジェクトとデータを移行するデータベースを指定します。 Azure SQL DB に接続した後は、Sybase、スキーマ レベルでは、このマッピングをカスタマイズできます。 詳細については、次を参照してください[Sybase ASE のスキーマから SQL Server スキーマにマッピング&#40;SybaseToSQL。&#41;](../../ssma/sybase/mapping-sybase-ase-schemas-to-sql-server-schemas-sybasetosql.md)  
  
> [!WARNING]  
> Azure SQL DB に接続しようとすると、前に、Azure SQL DB のインスタンスを実行しているし、接続を受け入れることを確認してください。  
  
**Azure SQL DB に接続するには**  
  
1.  **ファイル**メニューの  **Azure SQL DB への接続**(プロジェクトの作成後にこのオプションは有効です)。  
  
    Azure SQL DB に以前接続した場合、コマンド名になります**Azure SQL DB への再接続**  
  
2.  接続ダイアログ ボックスで入力または Azure SQL DB サーバー名を選択します。  
  
3.  入力を選択または**参照**データベース名。  
  
4.  入力または選択**UserName**です。  
  
5.  入力、**パスワード**です。  
  
6.  SSMA は、Azure SQL DB に、暗号化された接続をお勧めします。  
  
7.  **[接続]** をクリックします。  
  
> [!IMPORTANT]  
> SSMA for Sybase はへの接続をサポートしていません**マスター** Azure SQL データベース内のデータベースです。  
  
## <a name="synchronizing-azure-sql-db-metadata"></a>Azure SQL DB メタデータを同期します。  
Azure SQL DB データベースについてのメタデータは自動的に更新されません。 Azure SQL DB メタデータ エクスプ ローラー内のメタデータは、Azure SQL DB、または前回のメタデータを手動で更新することを最初に接続したときのメタデータのスナップショットです。 すべてのデータベース、または任意の 1 つのデータベースまたはデータベース オブジェクトのメタデータを手動で更新することができます。  
  
**メタデータを同期するには**  
  
1.  Azure SQL DB に接続していることを確認します。  
  
2.  Azure SQL DB メタデータ エクスプ ローラーで、データベースまたは更新するデータベース スキーマの横にあるチェック ボックスを選択します。  
  
    たとえば、すべてのデータベースのメタデータを更新するには、データベースの横にあるボックスを選択します。  
  
3.  データベース、または個々 のデータベースまたはデータベース スキーマを右クリックし **データベースと同期する**です。  
  
## <a name="next-step"></a>次の手順  
次の手順では、プロジェクトのニーズによって異なります。  
  
-   Sybase スキーマ、Azure SQL DB データベース、およびスキーマ間のマッピングをカスタマイズするを参照してください[マッピング Sybase ASE スキーマから SQL Server スキーマ&#40;SybaseToSQL。&#41;](../../ssma/sybase/mapping-sybase-ase-schemas-to-sql-server-schemas-sybasetosql.md)  
  
-   プロジェクトの構成オプションをカスタマイズするを参照してください[プロジェクト オプションの設定&#40;SybaseToSQL。&#41;](../../ssma/sybase/setting-project-options-sybasetosql.md)  
  
-   ソースとターゲットのデータ型のマッピングをカスタマイズするを参照してください[マッピング Sybase ASE、および SQL Server データ型&#40;SybaseToSQL。&#41;](../../ssma/sybase/mapping-sybase-ase-and-sql-server-data-types-sybasetosql.md)  
  
-   場合は、次のタスクを実行する必要はありません、Sybase データベース オブジェクトの定義を Azure SQL DB オブジェクトの定義に変換できます。 詳細については、次を参照してください[Sybase ASE データベース オブジェクトの変換&#40;SybaseToSQL。&#41;](../../ssma/sybase/converting-sybase-ase-database-objects-sybasetosql.md)  
  
## <a name="see-also"></a>参照  
[SQL Server - Azure SQL DB に ASE Sybase データベースを移行する&#40;SybaseToSQL&#41;](../../ssma/sybase/migrating-sybase-ase-databases-to-sql-server-azure-sql-db-sybasetosql.md)  
  
