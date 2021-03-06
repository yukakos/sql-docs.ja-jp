---
title: Oracle CDC インスタンス | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ed71e8c4-e013-4bf2-8b6c-1e833ff2a41d
caps.latest.revision: 7
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: a9b063510595a4c80f31433a1f793857ca35dd0c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37322732"
---
# <a name="the-oracle-cdc-instance"></a>Oracle CDC インスタンス
  Oracle CDC インスタンスは、単一の Oracle ソース データベースからキャプチャされた変更を処理するために、Oracle CDC Service によって作成されたプロセスです。 Oracle CDC インスタンスは、その構成を **cdc.xdbcdc_config** テーブルから取得し、その状態を **cdc.xdbcdc_state** テーブルで維持します。 これらのテーブルは、Oracle CDC インスタンスを定義する CDC データベースの一部です。 xdbcdc データベースおよびテーブルの詳細については、「 [The CDC Databases](the-oracle-cdc-service.md)」を参照してください。  
  
 Oracle CDC インスタンスによって実行されるタスクを次に示します。  
  
-   **サービス開始時の検証の処理**: 起動した CDC インスタンスは、 **xdbcdc_config** テーブルから構成を読み込み、一連の状態検証を実行します。この検証で、CDC インスタンスの永続化された状態に一貫性があり、変更の処理を開始できることを確認します。  
  
-   **変更のキャプチャの準備**: 検証が正常に終了した場合、Oracle CDC インスタンスは現在定義されているすべてのキャプチャ インスタンスをスキャンし、変更のキャプチャに必要な Oracle LogMiner クエリおよびその他のサポート構造を準備します。 また、Oracle インスタンスは Oracle CDC インスタンスが最後に実行されたときに保存された内部キャプチャ状態を再度読み込みます。  
  
-   **Oracle の変更のキャプチャ**: Oracle CDC インスタンスは、Oracle LogMiner 機能を利用して Oracle の変更をプールし、トランザクションのコミットに従ってそれらを並べ替え、トランザクションの時刻を変更して CDC データベースの [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 変更テーブルに書き込みます。  
  
-   
  **サービスのシャットダウンの処理**: Oracle CDC インスタンスのライフ サイクルは、Oracle CDC Service によって管理されます。 シャットダウンを要求された場合、Oracle CDC インスタンスは次のタスクを実行します。  
  
    -   Oracle トランザクション ログからの読み取りを停止します。  
  
    -   完了した Oracle トランザクションの CDC データベースへの書き込みを停止します。  
  
    -   必要に応じて、現在のトランザクションの CDC データベースへの書き込みが終了するまで、最大で 30 秒待機します。 30 秒以上が経過した場合、書き込みはキャンセルされ、トランザクションはロールバックされます (CDC インスタンスが再起動したときに再試行されます)。  
  
    -   個別のスレッドで、ステージングされたトランザクション テーブルに最大で 30 秒間、メモリにキャッシュされたレコードをできるだけ多く書き込み (最も古いトランザクションから最新のトランザクションの順)、 **xdbcdc_state** テーブルを更新してすべての変更をコミットします。  
  
-   **構成の変更の処理**: Oracle CDC インスタンスは、CDC Service から、または **cdc.xdbcdc_config** テーブルで新しいバージョンを検出することにより、構成の変更に関する通知を受けます。 ほとんどの変更では、Oracle CDC インスタンスを再起動する必要はありません (キャプチャ インスタンスの追加または削除など)。 しかし、Oracle 接続文字列やアクセス資格情報の変更など、一部の変更では、Oracle CDC インスタンスを再起動する必要があります。  
  
-   **復旧の処理**: Oracle CDC インスタンスが起動すると、その内部状態が **xdbcdc_state** テーブルおよび **xdbcdc_staged_transactions** テーブルから復元されます。 状態が復元されると、CDC インスタンスは通常どおり実行されます。  
  
## <a name="see-also"></a>参照  
 [エラー処理](error-handling.md)  
  
  
