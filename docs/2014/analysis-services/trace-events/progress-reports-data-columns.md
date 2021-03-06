---
title: 進行状況レポートのデータ列 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Progress Reports event category
ms.assetid: d34a6322-e26b-4454-b98f-32307d6956b5
caps.latest.revision: 33
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8f2cb983d7582885b2242cb6115bab2f15c4021e
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37332632"
---
# <a name="progress-reports-data-columns"></a>進行状況レポートのデータ列
  進行状況レポート イベント カテゴリには、次のイベント クラスがあります。  
  
|**イベント ID**|**イベント名**|**イベントの説明**|  
|------------------|--------------------|---------------------------|  
|5|Progress Report Begin|進行状況レポートが開始しました。|  
|6|Progress Report End|進行状況レポートが終了しました。|  
|7|Progress Report Current|進行状況レポートを実行中です。|  
|8|Progress Report Error|進行状況レポート エラーです。|  
  
 次の表は、これらのイベント クラスのデータ列の一覧です。  
  
## <a name="progress-report-begindata-columns"></a>Progress Report Begin のデータ列  
  
|**列名**|**列 ID**|**列の型**|**列の説明**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|イベント クラスを使用してイベントを分類します。|  
|EventSubclass|1|1|イベント サブクラスにより、各イベント クラスに関する追加情報が提供されます。<br /><br /> 1: プロセス<br /><br /> 2: マージ<br /><br /> 3: 削除<br /><br /> 4: DeleteOldAggregations<br /><br /> 5: 再構築<br /><br /> 6: コミット<br /><br /> 7: ロールバック<br /><br /> 8: CreateIndexes<br /><br /> 9: CreateTable<br /><br /> 10: InsertInto<br /><br /> 11: トランザクション<br /><br /> 12: 初期化<br /><br /> 13: 分離<br /><br /> 14: クエリ<br /><br /> 15: CreateView<br /><br /> 16: WriteData<br /><br /> 17: ReadData<br /><br /> 18: GroupData<br /><br /> 19: GroupDataRecord<br /><br /> 20: BuildIndex<br /><br /> 21: 集計<br /><br /> 22: BuildDecode<br /><br /> 23: WriteDecode<br /><br /> 24: BuildDMDecode<br /><br /> 25: ExecuteSQL<br /><br /> 26: ExecuteModifiedSQL<br /><br /> 27: 接続<br /><br /> 28: BuildAggsAndIndexes<br /><br /> 29: MergeAggsOnDisk<br /><br /> 30: BuildIndexForRigidAggs<br /><br /> 31: BuildIndexForFlexibleAggs<br /><br /> 32: WriteAggsAndIndexes<br /><br /> 33: WriteSegment<br /><br /> 34: DataMiningProgress<br /><br /> 35: ReadBufferFullReport<br /><br /> 36: ProactiveCacheConversion<br /><br /> 37: バックアップ<br /><br /> 38: 復元<br /><br /> 39: 同期<br /><br /> 40: 処理のスケジュールを作成<br /><br /> 41: デタッチ<br /><br /> 42: アタッチ<br /><br /> 43: Analyze\Encode データ<br /><br /> 44: 圧縮セグメント<br /><br /> 45: テーブル列の記述<br /><br /> 46: リレーションシップのビルドを準備します。<br /><br /> 47: リレーションシップのセグメントを構築<br /><br /> 48: 負荷<br /><br /> 49: メタデータの読み込み<br /><br /> 50: データの読み込み<br /><br /> 51: ポスト ロード<br /><br /> 52: バックアップ中にメタデータの検査<br /><br /> 53: VertiPaq<br /><br /> 54: 階層の処理<br /><br /> 55: 辞書の切り替え|  
|CurrentTime|2|5|Reported イベントの現在の時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|StartTime|3|5|イベントが開始された時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|JobID|7|1|Reported イベントに関連付けられたジョブ ID を表します。|  
|SessionType|8|8|Reported イベントに関連付けられたセッションの種類 (イベントを発生させたエンティティ) を表します。 イベントを処理する場合、値は次のとおりです。<br /><br /> 1 = ユーザー<br /><br /> 2 = プロアクティブ キャッシュ<br /><br /> 3 = レイジー処理|  
|ObjectID|11|8|Reported イベントに関連付けられたオブジェクト ID (文字列) を表します。|  
|ObjectType|12|1|オブジェクトの種類が含まれます。|  
|ObjectName|13|8|Reported イベントに関連付けられたオブジェクトの名前を表します。|  
|ObjectPath|14|8|Reported イベントに関連付けられたオブジェクトのオブジェクト パスを表します。パスは、オブジェクトの親を先頭に、コンマで区切った親のリストとして表されます。|  
|ObjectReference|15|8|Reported イベントのオブジェクトの参照を表します。すべての親を XML としてエンコードし、オブジェクトを記述するタグを使用して表します。|  
|ConnectionID|25|1|Reported イベントに関連付けられた一意の接続 ID を表します。|  
|DatabaseName|28|8|Reported イベントが発生したデータベースの名前を表します。|  
|NTUserName|32|8|Reported イベントに関連付けられた Windows ユーザー アカウントを表します。|  
|NTDomainName|33|8|Reported イベントに関連付けられた Windows ドメイン アカウントを表します。|  
|SessionID|39|8|Reported イベントに関連付けられたセッション ID を表します。|  
|NTCanonicalUserName|40|8|正規の形式のユーザー名。 たとえば、engineering.microsoft.com/software/someone などです。|  
|SPID|41|1|Reported イベントに関連付けられたユーザー セッションを一意に識別するサーバー プロセス ID (SPID) を表します。 SPID は、XML for Analysis (XMLA) で使用するセッション GUID に直接対応します。|  
|TextData|42|9|Reported イベントに関連付けられたテキスト データを表します。|  
|ServerName|43|8|Reported イベントが発生した [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスの名前を表します。|  
  
## <a name="progress-report-enddata-columns"></a>Progress Report End のデータ列  
  
|**列名**|**列 ID**|**列の型**|**列の説明**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|イベント クラスを使用してイベントを分類します。|  
|EventSubclass|1|1|イベント サブクラスにより、各イベント クラスに関する追加情報が提供されます。<br /><br /> 1: プロセス<br /><br /> 2: マージ<br /><br /> 3: 削除<br /><br /> 4: DeleteOldAggregations<br /><br /> 5: 再構築<br /><br /> 6: コミット<br /><br /> 7: ロールバック<br /><br /> 8: CreateIndexes<br /><br /> 9: CreateTable<br /><br /> 10: InsertInto<br /><br /> 11: トランザクション<br /><br /> 12: 初期化<br /><br /> 13: 分離<br /><br /> 14: クエリ<br /><br /> 15: CreateView<br /><br /> 16: WriteData<br /><br /> 17: ReadData<br /><br /> 18: GroupData<br /><br /> 19: GroupDataRecord<br /><br /> 20: BuildIndex<br /><br /> 21: 集計<br /><br /> 22: BuildDecode<br /><br /> 23: WriteDecode<br /><br /> 24: BuildDMDecode<br /><br /> 25: ExecuteSQL<br /><br /> 26: ExecuteModifiedSQL<br /><br /> 27: 接続<br /><br /> 28: BuildAggsAndIndexes<br /><br /> 29: MergeAggsOnDisk<br /><br /> 30: BuildIndexForRigidAggs<br /><br /> 31: BuildIndexForFlexibleAggs<br /><br /> 32: WriteAggsAndIndexes<br /><br /> 33: WriteSegment<br /><br /> 34: DataMiningProgress<br /><br /> 35: ReadBufferFullReport<br /><br /> 36: ProactiveCacheConversion<br /><br /> 37: バックアップ<br /><br /> 38: 復元<br /><br /> 39: 同期<br /><br /> 40: 処理のスケジュールを作成<br /><br /> 41: デタッチ<br /><br /> 42: アタッチ<br /><br /> 43: Analyze\Encode データ<br /><br /> 44: 圧縮セグメント<br /><br /> 45: テーブル列の記述<br /><br /> 46: リレーションシップのビルドを準備します。<br /><br /> 47: リレーションシップのセグメントを構築<br /><br /> 48: 負荷<br /><br /> 49: メタデータの読み込み<br /><br /> 50: データの読み込み<br /><br /> 51: ポスト ロード<br /><br /> 52: バックアップ中にメタデータの検査<br /><br /> 53: VertiPaq<br /><br /> 54: 階層の処理<br /><br /> 55: 辞書の切り替え|  
|CurrentTime|2|5|Reported イベントの現在の時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|StartTime|3|5|イベントが開始された時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|EndTime|4|5|イベントが終了した時刻を表します。 SQL:BatchStarting や SP:Starting などの開始イベント クラスについては、この列に値が格納されません。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|Duration|5|2|イベントにかかった時間 (ミリ秒) を表します。|  
|CPUTime|6|2|イベントで使用された CPU 時間 (ミリ秒) を表します。|  
|JobID|7|1|Reported イベントに関連付けられたジョブ ID を表します。|  
|SessionType|8|8|Reported イベントに関連付けられたセッションの種類 (イベントを発生させたエンティティ) を表します。 イベントを処理する場合、値は次のとおりです。<br /><br /> 1 = ユーザー<br /><br /> 2 = プロアクティブ キャッシュ<br /><br /> 3 = レイジー処理|  
|ProgressTotal|9|1|Reported イベントの進行状況の合計を表します。|  
|IntegerData|10|1|処理イベントに対して処理される行数の現在のカウントなど、Reported イベントに関連付けられた整数データを表します。|  
|ObjectID|11|8|Reported イベントに関連付けられたオブジェクト ID (文字列) を表します。|  
|ObjectType|12|1|オブジェクトの種類が含まれます。|  
|ObjectName|13|8|Reported イベントに関連付けられたオブジェクトの名前を表します。|  
|ObjectPath|14|8|Reported イベントに関連付けられたオブジェクトのオブジェクト パスを表します。パスは、オブジェクトの親を先頭に、コンマで区切った親のリストとして表されます。|  
|ObjectReference|15|8|Reported イベントのオブジェクトの参照を表します。すべての親を XML としてエンコードし、オブジェクトを記述するタグを使用して表します。|  
|Severity|22|1|Reported イベントに関連付けられた例外の重大度レベルを表します。 値は次のとおりです。<br /><br /> 0 = 成功<br /><br /> 1 = 情報<br /><br /> 2 = 警告<br /><br /> 3 = エラー|  
|Success|23|1|Reported イベントの成功または失敗を表します。 値は次のとおりです。<br /><br /> 0 = 失敗<br /><br /> 1 = 成功|  
|[エラー]|24|1|特定のイベントのエラー番号が含まれます。|  
|ConnectionID|25|1|Reported イベントに関連付けられた一意の接続 ID を表します。|  
|DatabaseName|28|8|Reported イベントが発生したデータベースの名前を表します。|  
|NTUserName|32|8|Reported イベントに関連付けられた Windows ユーザー アカウントを表します。|  
|NTDomainName|33|8|Reported イベントに関連付けられた Windows ドメイン アカウントを表します。|  
|SessionID|39|8|Reported イベントに関連付けられたセッション ID を表します。|  
|NTCanonicalUserName|40|8|Reported イベントに関連付けられた Windows ユーザー名を表します。 ユーザー名は正規の形式です。 たとえば、engineering.microsoft.com/software/user などです。|  
|SPID|41|1|Reported イベントに関連付けられたユーザー セッションを一意に識別するサーバー プロセス ID (SPID) を表します。 SPID は、XML for Analysis (XMLA) で使用するセッション GUID に直接対応します。|  
|TextData|42|9|Reported イベントに関連付けられたテキスト データを表します。|  
|ServerName|43|8|Reported イベントが発生した [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスの名前を表します。|  
  
## <a name="progress-report-currentdata-columns"></a>Progress Report Current のデータ列  
  
|**列名**|**列 ID**|**列の型**|**列の説明**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|イベント クラスを使用してイベントを分類します。|  
|EventSubclass|1|1|イベント サブクラスにより、各イベント クラスに関する追加情報が提供されます。<br /><br /> 1: プロセス<br /><br /> 2: マージ<br /><br /> 3: 削除<br /><br /> 4: DeleteOldAggregations<br /><br /> 5: 再構築<br /><br /> 6: コミット<br /><br /> 7: ロールバック<br /><br /> 8: CreateIndexes<br /><br /> 9: CreateTable<br /><br /> 10: InsertInto<br /><br /> 11: トランザクション<br /><br /> 12: 初期化<br /><br /> 13: 分離<br /><br /> 14: クエリ<br /><br /> 15: CreateView<br /><br /> 16: WriteData<br /><br /> 17: ReadData<br /><br /> 18: GroupData<br /><br /> 19: GroupDataRecord<br /><br /> 20: BuildIndex<br /><br /> 21: 集計<br /><br /> 22: BuildDecode<br /><br /> 23: WriteDecode<br /><br /> 24: BuildDMDecode<br /><br /> 25: ExecuteSQL<br /><br /> 26: ExecuteModifiedSQL<br /><br /> 27: 接続<br /><br /> 28: BuildAggsAndIndexes<br /><br /> 29: MergeAggsOnDisk<br /><br /> 30: BuildIndexForRigidAggs<br /><br /> 31: BuildIndexForFlexibleAggs<br /><br /> 32: WriteAggsAndIndexes<br /><br /> 33: WriteSegment<br /><br /> 34: DataMiningProgress<br /><br /> 35: ReadBufferFullReport<br /><br /> 36: ProactiveCacheConversion<br /><br /> 37: バックアップ<br /><br /> 38: 復元<br /><br /> 39: 同期<br /><br /> 40: 処理のスケジュールを作成<br /><br /> 41: デタッチ<br /><br /> 42: アタッチ<br /><br /> 43: Analyze\Encode データ<br /><br /> 44: 圧縮セグメント<br /><br /> 45: テーブル列の記述<br /><br /> 46: リレーションシップのビルドを準備します。<br /><br /> 47: リレーションシップのセグメントを構築<br /><br /> 48: 負荷<br /><br /> 49: メタデータの読み込み<br /><br /> 50: データの読み込み<br /><br /> 51: ポスト ロード<br /><br /> 52: バックアップ中にメタデータの検査<br /><br /> 53: VertiPaq<br /><br /> 54: 階層の処理<br /><br /> 55: 辞書の切り替え|  
|CurrentTime|2|5|Reported イベントの現在の時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|StartTime|3|5|イベントが開始された時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|JobID|7|1|Reported イベントに関連付けられたジョブ ID を表します。|  
|SessionType|8|8|Reported イベントに関連付けられたセッションの種類 (イベントを発生させたエンティティ) を表します。 イベントを処理する場合、値は次のとおりです。<br /><br /> 1 = ユーザー<br /><br /> 2 = プロアクティブ キャッシュ<br /><br /> 3 = レイジー処理|  
|ProgressTotal|9|1|Reported イベントの進行状況の合計を表します。|  
|IntegerData|10|1|処理イベントに対して処理される行数の現在のカウントなど、Reported イベントに関連付けられた整数データを表します。|  
|ObjectID|11|8|Reported イベントに関連付けられたオブジェクト ID (文字列) を表します。|  
|ObjectType|12|1|オブジェクトの種類が含まれます。|  
|ObjectName|13|8|Reported イベントに関連付けられたオブジェクトの名前を表します。|  
|ObjectPath|14|8|Reported イベントに関連付けられたオブジェクトのオブジェクト パスを表します。パスは、オブジェクトの親を先頭に、コンマで区切った親のリストとして表されます。|  
|ObjectReference|15|8|Reported イベントのオブジェクトの参照を表します。すべての親を XML としてエンコードし、オブジェクトを記述するタグを使用して表します。|  
|ConnectionID|25|1|Reported イベントに関連付けられた一意の接続 ID を表します。|  
|DatabaseName|28|8|Reported イベントが発生したデータベースの名前を表します。|  
|SessionID|39|8|Reported イベントに関連付けられたセッション ID を表します。|  
|SPID|41|1|Reported イベントに関連付けられたユーザー セッションを一意に識別するサーバー プロセス ID (SPID) を表します。 SPID は、XML for Analysis (XMLA) で使用するセッション GUID に直接対応します。|  
|TextData|42|9|Reported イベントに関連付けられたテキスト データを表します。|  
|ServerName|43|8|Reported イベントが発生した [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスの名前を表します。|  
  
## <a name="progress-report-errordata-columns"></a>Progress Report Error のデータ列  
  
|**列名**|**列 ID**|**列の型**|**列の説明**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|イベント クラスを使用してイベントを分類します。|  
|EventSubclass|1|1|イベント サブクラスにより、各イベント クラスに関する追加情報が提供されます。<br /><br /> 1: プロセス<br /><br /> 2: マージ<br /><br /> 3: 削除<br /><br /> 4: DeleteOldAggregations<br /><br /> 5: 再構築<br /><br /> 6: コミット<br /><br /> 7: ロールバック<br /><br /> 8: CreateIndexes<br /><br /> 9: CreateTable<br /><br /> 10: InsertInto<br /><br /> 11: トランザクション<br /><br /> 12: 初期化<br /><br /> 13: 分離<br /><br /> 14: クエリ<br /><br /> 15: CreateView<br /><br /> 16: WriteData<br /><br /> 17: ReadData<br /><br /> 18: GroupData<br /><br /> 19: GroupDataRecord<br /><br /> 20: BuildIndex<br /><br /> 21: 集計<br /><br /> 22: BuildDecode<br /><br /> 23: WriteDecode<br /><br /> 24: BuildDMDecode<br /><br /> 25: ExecuteSQL<br /><br /> 26: ExecuteModifiedSQL<br /><br /> 27: 接続<br /><br /> 28: BuildAggsAndIndexes<br /><br /> 29: MergeAggsOnDisk<br /><br /> 30: BuildIndexForRigidAggs<br /><br /> 31: BuildIndexForFlexibleAggs<br /><br /> 32: WriteAggsAndIndexes<br /><br /> 33: WriteSegment<br /><br /> 34: DataMiningProgress<br /><br /> 35: ReadBufferFullReport<br /><br /> 36: ProactiveCacheConversion<br /><br /> 37: バックアップ<br /><br /> 38: 復元<br /><br /> 39: 同期<br /><br /> 40: 処理のスケジュールを作成<br /><br /> 41: デタッチ<br /><br /> 42: アタッチ<br /><br /> 43: Analyze\Encode データ<br /><br /> 44: 圧縮セグメント<br /><br /> 45: テーブル列の記述<br /><br /> 46: リレーションシップのビルドを準備します。<br /><br /> 47: リレーションシップのセグメントを構築<br /><br /> 48: 負荷<br /><br /> 49: メタデータの読み込み<br /><br /> 50: データの読み込み<br /><br /> 51: ポスト ロード<br /><br /> 52: バックアップ中にメタデータの検査<br /><br /> 53: VertiPaq<br /><br /> 54: 階層の処理<br /><br /> 55: 辞書の切り替え|  
|CurrentTime|2|5|Reported イベントの現在の時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|StartTime|3|5|イベントが開始された時刻を表します (取得できた場合)。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|EndTime|4|5|イベントが終了した時刻を表します。 SQL:BatchStarting や SP:Starting などの開始イベント クラスについては、この列に値が格納されません。 フィルター選択を行うには、'YYYY-MM-DD' および 'YYYY-MM-DD HH:MM:SS' の形式である必要があります。|  
|Duration|5|2|イベントにかかった時間 (ミリ秒) を表します。|  
|JobID|7|1|Reported イベントに関連付けられたジョブ ID を表します。|  
|SessionType|8|8|Reported イベントに関連付けられたセッションの種類 (イベントを発生させたエンティティ) を表します。 イベントを処理する場合、値は次のとおりです。<br /><br /> 1 = ユーザー<br /><br /> 2 = プロアクティブ キャッシュ<br /><br /> 3 = レイジー処理|  
|ProgressTotal|9|1|Reported イベントの進行状況の合計を表します。|  
|IntegerData|10|1|処理イベントに対して処理される行数の現在のカウントなど、Reported イベントに関連付けられた整数データを表します。|  
|ObjectID|11|8|Reported イベントに関連付けられたオブジェクト ID (文字列) を表します。|  
|ObjectType|12|1|オブジェクトの種類が含まれます。|  
|ObjectName|13|8|Reported イベントに関連付けられたオブジェクトの名前を表します。|  
|ObjectPath|14|8|Reported イベントに関連付けられたオブジェクトのオブジェクト パスを表します。パスは、オブジェクトの親を先頭に、コンマで区切った親のリストとして表されます。|  
|ObjectReference|15|8|Reported イベントのオブジェクトの参照を表します。すべての親を XML としてエンコードし、オブジェクトを記述するタグを使用して表します。|  
|Severity|22|1|Reported イベントに関連付けられた例外の重大度レベルを表します。 値は次のとおりです。<br /><br /> 0 = 成功<br /><br /> 1 = 情報<br /><br /> 2 = 警告<br /><br /> 3 = エラー|  
|Error|24|1|特定のイベントのエラー番号が含まれます。|  
|ConnectionID|25|1|Reported イベントに関連付けられた一意の接続 ID を表します。|  
|DatabaseName|28|8|Reported イベントが発生したデータベースの名前を表します。|  
|SessionID|39|8|Reported イベントに関連付けられたセッション ID を表します。|  
|SPID|41|1|Reported イベントに関連付けられたユーザー セッションを一意に識別するサーバー プロセス ID (SPID) を表します。 SPID は、XML for Analysis (XMLA) で使用するセッション GUID に直接対応します。|  
|TextData|42|9|Reported イベントに関連付けられたテキスト データを表します。|  
|ServerName|43|8|Reported イベントが発生した [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスの名前を表します。|  
  
## <a name="see-also"></a>参照  
 [進行状況レポート イベント カテゴリ](progress-reports-event-category.md)  
  
  
