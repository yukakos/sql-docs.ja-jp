---
title: キュー リーダー エージェント (Queue Reader Agent) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.rep.monitor.queuereaderagent.f1
helpviewer_keywords:
- Queue Reader Agent dialog box
ms.assetid: f02d24b6-dcb5-4126-b56e-fab41cfe4337
caps.latest.revision: 18
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f5ec06133574580cdd2c0ee42a529bcb7f631b2a
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37360083"
---
# <a name="queue-reader-agent"></a>キュー リーダー エージェント (Queue Reader Agent)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  **[キュー リーダー エージェント]** ダイアログ ボックスでは、状態、履歴、情報メッセージ、およびすべてのエラー メッセージを含む、キュー リーダー エージェントの詳細情報が表示されます。  
  
## <a name="options"></a>および  
 **[表示]** メニューから表示するキュー リーダー エージェントのセッションを選択し、次に **[キュー リーダー エージェントのセッション]** というラベルのグリッド内で特定のセッションを選択します。 このセッションの詳細情報は、 **[選択されたセッションのアクション]** というラベルのグリッドに表示されます。 選択したセッションがエラーで終了した場合は、 **[選択されたセッションのエラーの詳細またはメッセージ]** というラベルのテキスト領域も表示されます。  
  
 **[表示]**  
 表示するキュー リーダー エージェントのセッションを選択します。 通常、キュー リーダー エージェントは継続的に実行されるため、表示するセッションが 1 つのみの場合があります。  
  
 **[状態]**  
 キュー リーダー エージェントの状態です。 表示される状態の種類を、次に示します。  
  
-   [エラー]  
  
-   [失敗したコマンドの再試行]  
  
-   [実行されていません]  
  
-   実行中  
  
 **Start Time**  
 セッションの開始時刻です。  
  
 **[終了時刻]**  
 セッションの終了時刻です。 エージェントが停止していない場合は、このフィールドは空になっています。  
  
 **Duration**  
 このセッションでキュー リーダー エージェントが実行された時間です。 この時間は、エージェントが現在実行中の場合の経過時間と、エージェント セッションが終了した場合のセッションの合計時間を表します。  
  
 **エラー メッセージ**  
 セッションがエラーで終了した場合、キュー リーダー エージェントによって記録された最新のエラー メッセージがこのフィールドに表示されます。 セッションがエラーで終了しなかった場合は、このフィールドは空白です。  
  
 **[動作メッセージ]**  
 選択したセッション中にキュー リーダー エージェントによって記録された、すべての情報メッセージとエラー メッセージです。  
  
 **[動作時間]**  
 **[動作メッセージ]** 列で説明されたアクションが実行された時間です。  
  
 **[選択されたセッションのエラーの詳細またはメッセージ]**  
 選択したセッションの **[状態]** 列に **[エラー]** の値が表示されている場合にのみ表示されます。 このテキスト領域では、エラーの詳細情報とエラーの発生時に試行されたコマンドが表示されます。 エラーに関連する追加コンテンツへのリンクも含まれます。  
  
## <a name="see-also"></a>参照  
 [レプリケーション モニターの開始](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [パブリケーションに関連付けられているエージェントの情報を表示し、タスクを実行する &#40;レプリケーション モニター&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-publication-agents.md)   
 [レプリケーションの監視](../../relational-databases/replication/monitor/monitoring-replication-overview.md)   
 [レプリケーション エージェントの概要](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  
