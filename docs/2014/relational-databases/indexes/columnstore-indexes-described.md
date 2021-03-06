---
title: 列ストア インデックスの説明 |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: table-view-index
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- indexes creation, columnstore
- indexes [SQL Server], columnstore
- columnstore index
- columnstore index, described
- xVelocity, columnstore indexes
ms.assetid: f98af4a5-4523-43b1-be8d-1b03c3217839
caps.latest.revision: 50
author: mikeraymsft
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 9cd8b98b2e62dbc11d62e07b9b0d7e2ac3e05c6b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37211322"
---
# <a name="columnstore-indexes-described"></a>Columnstore Indexes Described
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]*メモリ内列ストア インデックス*格納および列ベースのデータ ストレージと列ベースのクエリ処理を使用してデータを管理します。 列ストア インデックスは、主に一括読み込みと読み取り専用のクエリを実行するデータ ウェアハウスのワークロードで適切に動作します。 従来の行指向ストレージの最大 **10 倍のクエリ パフォーマンス** と、非圧縮データ サイズの最大 **7 倍のデータ圧縮** を達成するために列ストア インデックスを使用します。  
  
> [!NOTE]  
>  大規模なデータ ウェアハウス ファクト テーブルを格納するために、クラスター化列ストア インデックスが標準とされており、ほとんどのデータ ウェアハウス シナリオで使用されることが予想されます。 クラスター化列ストア インデックスは更新可能であるため、ワークロードで多数の挿入、更新、および削除操作を実行できます。  
  
## <a name="contents"></a>目次  
  
-   [基本操作](#basics)  
  
-   [データの読み込み](#dataload)  
  
-   [パフォーマンスに関するヒント](#performance)  
  
-   [関連タスクおよびトピック](#related)  
  
##  <a name="basics"></a> 基本操作  
 *columnstore index* は、列ストアと呼ばれる列指向データ形式を使用してデータを格納、取得、および管理するためのテクノロジです。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 両方のクラスター化と非クラスター化列ストア インデックスをサポートしています。 どちらでも同じインメモリ列ストア テクノロジが使用されますが、目的とサポートされる機能に違いがあります。  
  
###  <a name="benefits"></a> 利点  
 列ストア インデックスは、主に大きいデータ セットに対して分析を実行する読み取り専用のクエリで効果的に動作します。 多くの場合、これらはデータ ウェアハウスのワークロードのクエリです。 列ストア インデックスは、フル テーブル スキャンを使用するクエリで高いパフォーマンスを発揮しますが、データをシークして特定の値を検索するクエリには適していません。  
  
 列ストア インデックスの利点:  
  
-   列には類似したデータがよくあり、圧縮比率が高くなります。  
  
-   高い圧縮比率により、メモリ使用量が削減され、クエリのパフォーマンスが向上します。 さらに、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] がより多くのクエリやデータ操作をインメモリで実行できるため、クエリのパフォーマンスが向上する場合があります。  
  
-   SQL Server に追加されたバッチ モード実行と呼ばれる新しいクエリ実行メカニズムにより、CPU 使用率が大きく軽減されます。 バッチ モード実行は、列ストア ストレージ形式と緊密に統合され、このストレージ形式に合わせて最適化されています。 バッチ モード実行は、ベクター ベースの実行またはベクター化された実行と呼ばれることもあります。  
  
-   クエリはテーブルから少数の列のみを選択することが多く、物理メディアからの合計 I/O を低減します。  
  
### <a name="columnstore-versions"></a>列ストアのバージョン  
 SQL Server 2012、SQL Server 2012 並列データ ウェアハウス、および SQL Server 2014 では、いずれも列ストア インデックスを使用して、一般的な列データ ウェアハウスのクエリが高速化されます。 SQL Server 2012 では 2 つの新機能が導入されました。1 つは非クラスター化列ストア インデックスで、もう 1 つは、データを "バッチ" という単位で処理するベクター ベースのクエリ実行機能です。 SQL Server 2014 では、SQL Server 2012 の機能に加えて、更新可能なクラスター化列ストア インデックスを使用できます。  
  
### <a name="key-characteristics"></a>主な特性  
  
||  
|-|  
|**適用対象**: [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] から [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]|  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]、クラスター化列ストア インデックス。  
  
-   Enterprise Edition、Developer Edition、および Evaluatio Edition で使用できます。  
  
-   更新可能です。  
  
-   テーブル全体における主要な格納方法です。  
  
-   キー列はありません。 すべての列は付加列です。  
  
-   テーブルの唯一のインデックスです。 他のどのインデックスとも組み合わせることはできません。  
  
-   列ストアまたは列ストアの保存用圧縮を使用するように構成できます。  
  
-   列を並べ替えられた順に物理的に格納するのではありません。 代わりに、データを格納して圧縮とパフォーマンスを向上させます。  
  
||  
|-|  
|**適用対象**: [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] から [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]|  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]、非クラスター化列ストア インデックス。  
  
-   クラスター化インデックスまたはヒープ内の列のサブセットにインデックスを作成できます。 たとえば、頻繁に使用される列にインデックスを設定できます。  
  
-   インデックス内の列のコピーを格納する追加ストレージが必要です。  
  
-   インデックスの再構築またはパーティションの切り替えによって更新されます。挿入、更新、削除などの DML 操作によっては更新されません。  
  
-   テーブルの他のインデックスと組み合わせることができます。  
  
-   列ストアまたは列ストアの保存用圧縮を使用するように構成できます。  
  
-   列を並べ替えられた順に物理的に格納するのではありません。 代わりに、データを格納して圧縮とパフォーマンスを向上させます。 列ストア インデックスの作成前にデータを並べ替える必要はありませんが、あらかじめ並べ替えておくと、列ストア圧縮が向上する可能性があります。  
  
###  <a name="Concepts"></a> 主要な概念と用語  
 ここでは、列ストア インデックスに関連する主な用語と概念について説明します。  
  
 列ストア インデックス  
 *columnstore index* は、列ストアと呼ばれる列指向データ形式を使用してデータを格納、取得、および管理するためのテクノロジです。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 両方のクラスター化と非クラスター化列ストア インデックスをサポートしています。 どちらでも同じインメモリ列ストア テクノロジが使用されますが、目的とサポートされる機能に違いがあります。  
  
 列ストア  
 *列ストア* は、行と列を含むテーブルとして論理的に編成され、列方向のデータ形式で物理的に格納されているデータです。  
  
 行ストア  
 *行ストア* は、行と列を含むテーブルとして論理的に編成され、行方向のデータ形式で物理的に格納されているデータです。 これは、リレーショナル テーブル データを格納する従来の方法です。  
  
 行グループと列セグメント  
 高パフォーマンスと高い圧縮率を実現するために、列ストア インデックスは、テーブルを行グループと呼ばれる行のグループにスライスし、各行グループを列方向に圧縮します。 行グループ内の行の数には、圧縮率を向上させるために十分な大きさ、小さくすれば、インメモリ操作のメリットがあります。  
  
 行グループ  
 A*行グループ*と同時に列ストア形式に圧縮される行のグループです。  
  
 列セグメント  
 *列セグメント* は、行グループ内のデータ列です。  
  
-   通常、1 つの行グループには、行グループあたりの最大行数である 1,048,576 行が含まれます。  
  
-   それぞれの行グループには、テーブルの 1 つの列につき 1 つの列セグメントが含まれます。  
  
-   それぞれの列セグメントは一緒に圧縮され、物理メディアに格納されます。  
  
 ![Column segment](../../database-engine/media/sql-server-pdw-columnstore-columnsegment.gif "Column segment")  
  
 非クラスター化列ストア インデックス  
 A*非クラスター化列ストア インデックス*は既存のクラスター化インデックスまたはヒープ テーブルに作成された読み取り専用インデックスです。 このインデックスには、テーブル内のすべての列について、列のサブセットのコピーが含まれます。 テーブルに非クラスター化列ストア インデックスが含まれている場合、そのテーブルは読み取り専用になります。  
  
 非クラスター化列ストア インデックスは、分析クエリを実行しながら、同時に元のテーブルに対して読み取り専用操作を実行できる列ストア インデックスを提供します。  
  
 ![非クラスター化列ストア インデックス](../../database-engine/media/sql-server-pdw-columnstore-physicalstorage-nonclustered.gif "非クラスター化列ストア インデックス")  
  
 クラスター化列ストア インデックス  
 A*クラスター化列ストア インデックス*テーブル全体に対する物理ストレージであり、テーブルの唯一のインデックスです。 クラスター化インデックスは更新可能です。 インデックスに対して挿入、削除、および更新操作を実行したり、インデックスへのデータの一括読み込みを行ったりできます。  
  
 ![Clustered Columnstore Index](../../database-engine/media/sql-server-pdw-columnstore-physicalstorage.gif "Clustered Columnstore Index")  
  
 列セグメントの断片化を低減し、パフォーマンスを高めるために、列ストア インデックスでは、一部のデータおよび削除された行に対応する ID の B-Tree を一時的に行ストア テーブルに格納することがあります。 デルタストア操作は内部で処理されます。 列ストア インデックスは、正しいクエリ結果を返すために、列ストアとデルタストアの両方からのクエリ結果を結合します。  
  
 デルタストア  
 クラスター化列ストア インデックスでのみ使用される、*デルタストア*は行の数が、列ストアに移動するのに十分な大きさになるまで行を格納する行ストア テーブルです。 デルタストアは、読み込みやその他の DML 操作のパフォーマンスを高めるために、クラスター化列ストア インデックスで使用されます。  
  
 大規模な一括読み込みでは、行のほとんどがデルタストアを通らずに列ストアに直接移動します。 一括読み込みの最後に位置する行の数は、行グループの最小サイズである 102,400 行を満たすには足りないことがあります。 この場合、それらの行は列ストアではなくデルタストアに移動します。 102,400 行未満の小規模な一括読み込みでは、すべての行がデルタストアに直接移動します。  
  
 デルタストアは、最大行数に達すると閉じられます。 タプル移動プロセスは終了した行グループをチェックします。 閉じている行グループが見つかると、その行グループが圧縮され、列ストアに格納されます。  
  
##  <a name="dataload"></a> データの読み込み  
  
###  <a name="dataload_nci"></a> 非クラスター化列ストア インデックスにデータを読み込む  
 非クラスター化列ストア インデックスにデータを読み込む最初にデータをヒープとして格納されている、またはクラスター化は、従来の行ストア テーブルを読み込み、インデックスし、で非クラスター化列ストア インデックスを作成して[CREATE COLUMNSTORE INDEX &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).  
  
 ![列ストア インデックスにデータを読み込む](../../database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "列ストア インデックスにデータを読み込む")  
  
 非クラスター化列ストア インデックスを持つテーブルは、インデックスが削除または無効化されるまで読み取り専用になります。 テーブルと非クラスター化列ストア インデックスを更新する場合は、パーティションを切り替えることができます。また、インデックスを無効にし、テーブルを更新してから、インデックスを再構築する方法もあります。  
  
 詳細については、次を参照してください[を使用して非クラスター化列ストア インデックス。](indexes.md)  
  
###  <a name="dataload_cci"></a> クラスター化列ストア インデックスにデータを読み込む  
 ![クラスター化列ストア インデックスへの読み込み](../../database-engine/media/sql-server-pdw-columnstore-loadprocess.gif "Loading into a clustered columnstore index")  
  
 図からわかるように、クラスター化列ストア インデックスにデータを読み込む[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:  
  
1.  最大サイズの行グループを列ストアに直接挿入します。 データが読み込まれると、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] は開いている行グループに先着順でデータ行を割り当てます。  
  
2.  それぞれの行グループが最大サイズに到達すると、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] は次の処理を行います。  
  
    1.  行グループを CLOSED としてマークします。  
  
    2.  デルタストアをバイパスします。  
  
    3.  列ストア圧縮を使用する行グループで、それぞれの列セグメントを圧縮します。  
  
    4.  圧縮された列セグメントを列ストアに物理的に格納します。  
  
3.  次のように、列ストアまたはデルタストアに残りの行を挿入します。  
  
    1.  行数が行グループの最小限の行数の要件を満たしている場合は、行が列ストアに追加されます。  
  
    2.  行数が行グループの最小限の行数の要件を満たしていない場合は、行がデルタストアに追加されます。  
  
 デルタストアのタスクとプロセスに関する詳細については、次を参照してください[を使用してクラスター化列ストア インデックス。](../../database-engine/using-clustered-columnstore-indexes.md)  
  
##  <a name="performance"></a> パフォーマンスに関するヒント  
  
### <a name="plan-for-enough-memory-to-create-columnstore-indexes-in-parallel"></a>列ストア インデックスを並列で作成するための十分なメモリの計画  
 列ストア インデックスの作成は、メモリに制限がない限り既定で並列操作になります。 インデックスを並列で作成するには、インデックスを順次作成する場合よりも多くのメモリが必要です。 十分なメモリがある場合、列ストア インデックスの作成には、同じ列で B-Tree を構築する場合の約 1.5 倍の時間がかかります。  
  
 列ストア インデックスを作成するために必要なメモリは、列数、文字列型の列数、並列処理の最大限度 (DOP)、およびデータの特性によって異なります。 たとえば、テーブル内の行数が 100 万未満の場合、SQL Server はスレッドを 1 つだけ使用して列ストア インデックスを作成します。  
  
 テーブルに 100 万を超える行があり、SQL Server で MAXDOP を使用してインデックスを作成するための十分なメモリ許可を取得できない場合、SQL Server は必要に応じて自動的に MAXDOP を減らし、使用できるメモリ許可に合うように調整します。  場合によっては、メモリが制限された状況でインデックスを構築できるように、DOP を 1 まで小さくする必要があります。  
  
##  <a name="related"></a> 関連タスクおよびトピック  
  
### <a name="nonclustered-columnstore-indexes"></a>非クラスター化列ストア インデックス  
 一般的なタスクは、次を参照してください。 [Using Nonclustered Columnstore Indexes](../../database-engine/using-nonclustered-columnstore-indexes.md)します。  
  
-   [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql)  
  
-   [ALTER INDEX &#40;TRANSACT-SQL&#41; ](/sql/t-sql/statements/alter-index-transact-sql)で再構築します。  
  
-   [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)  
  
### <a name="clustered-columnstore-indexes"></a>クラスター化列ストア インデックス  
 一般的なタスクは、次を参照してください。 [Using Clustered Columnstore Indexes](../../database-engine/using-clustered-columnstore-indexes.md)します。  
  
-   [クラスター化列ストア インデックスを作成する&#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql)  
  
-   [ALTER INDEX &#40;TRANSACT-SQL&#41; ](/sql/t-sql/statements/alter-index-transact-sql) REBUILD または REORGANIZE です。  
  
-   [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)  
  
-   [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)  
  
-   [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql)  
  
-   [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql)  
  
### <a name="metadata"></a>メタデータ  
 列ストア インデックス内のすべての列は、付加列としてメタデータに格納されます。 列ストア インデックスにキー列はありません。  
  
-   [sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
-   [sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql)  
  
-   [sys.partitions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-partitions-transact-sql)  
  
-   [sys.column_store_segments &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-column-store-segments-transact-sql)  
  
-   [sys.column_store_dictionaries &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-column-store-dictionaries-transact-sql)  
  
-   [sys.column_store_row_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-column-store-row-groups-transact-sql)  
  
  
