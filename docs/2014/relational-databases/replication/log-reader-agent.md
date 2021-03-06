---
title: ログ リーダー エージェント (Log Reader Agent) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.logreaderagent.f1
helpviewer_keywords:
- Log Reader Agent dialog box
ms.assetid: 300a3c46-0e48-4334-99c0-9ee690d2ef4f
caps.latest.revision: 17
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 40a2b87a8746a77f5d431d6674013e2158ebbaf0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37179679"
---
# <a name="log-reader-agent"></a>ログ リーダー エージェント (Log Reader Agent)
  **[ログ リーダー エージェント]** ダイアログ ボックスには、ログ リーダー エージェントの状態、履歴、情報メッセージ、エラー メッセージなどの詳細情報が表示されます。  
  
## <a name="options"></a>および  
 **[表示]** メニューから表示するログ リーダー エージェントのセッションを選択し、 **[ログ リーダー エージェントのセッション]** というラベルのグリッド内で特定のセッションを選択します。 このセッションの詳細情報は、 **[選択されたセッションのアクション]** というラベルのグリッドに表示されます。 選択したセッションがエラーで終了した場合は、 **[選択されたセッションのエラーの詳細またはメッセージ]** というラベルのテキスト領域も表示されます。  
  
 **[表示]**  
 表示するログ リーダー エージェントのセッションを選択します。 通常、ログ リーダー エージェントは継続的に実行されるため、表示するセッションが 1 つのみの場合があります。  
  
 **ステータス**  
 ログ リーダー エージェントの状態です。 表示される状態の種類を、次に示します。  
  
-   [エラー]  
  
-   [失敗したコマンドの再試行]  
  
-   [実行されていません]  
  
-   実行中  
  
 **Start Time**  
 セッションの開始時刻です。  
  
 **[終了時刻]**  
 セッションの終了時刻です。 エージェントが停止していない場合は、このフィールドは空になっています。  
  
 **Duration**  
 ログ リーダー エージェントがこのセッション中に実行されている合計時間です。 この時間は、エージェントが現在実行中の場合の経過時間と、エージェント セッションが終了した場合のセッションの合計時間を表します。  
  
 **エラー メッセージ**  
 セッションがエラーで終了した場合、ログ リーダー エージェントによって記録された最新のエラー メッセージがこのフィールドに表示されます。 セッションがエラーで終了しなかった場合は、このフィールドは空白です。  
  
 **[動作メッセージ]**  
 選択したセッション中にログ リーダー エージェントによって記録された、すべての情報メッセージとエラー メッセージです。  
  
 **[動作時間]**  
 **[動作メッセージ]** 列で説明されたアクションが実行された時間です。  
  
 **[選択されたセッションのエラーの詳細またはメッセージ]**  
 選択したセッションの **[状態]** 列に **[エラー]** の値が表示されている場合にのみ表示されます。 このテキスト領域では、エラーの詳細情報とエラーの発生時に試行されたコマンドが表示されます。 エラーに関連する追加コンテンツへのリンクも含まれます。  
  
## <a name="see-also"></a>参照  
 [レプリケーション モニターの開始](monitor/start-the-replication-monitor.md)   
 [パブリケーションに関連付けられているエージェントの情報を表示し、タスクを実行する &#40;レプリケーション モニター&#41;](monitor/view-information-and-perform-tasks-for-publication-agents.md)   
 [レプリケーションの監視](monitoring-replication.md)   
 [レプリケーション エージェントの概要](agents/replication-agents-overview.md)  
  
  
