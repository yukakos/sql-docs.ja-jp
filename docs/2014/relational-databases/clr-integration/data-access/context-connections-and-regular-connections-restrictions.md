---
title: 標準モードとコンテキスト接続に関する制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
caps.latest.revision: 25
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: aaff8841ec9ccd7b61b5ab7646daaf700a05b3df
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37349454"
---
# <a name="restrictions-on-regular-and-context-connections"></a>通常の接続とコンテキスト接続に関する制限事項
  このトピックで説明して実行するコードに関する制限事項、[!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)]コンテキストと通常の接続を処理します。  
  
## <a name="restrictions-on-context-connections"></a>コンテキスト接続に関する制限事項  
 アプリケーションを開発するときは、コンテキスト接続に適用される次の制限事項を考慮してください。  
  
-   特定の接続に対して特定の時点に開くことができるコンテキスト接続は 1 つだけです。 複数のステートメントをそれぞれ独立した接続で同時に実行する場合、その中の 1 つの接続しか独自のコンテキスト接続を取得できません。 この制限事項は、異なる接続からの同時実行要求には影響しません。つまり、特定の接続の特定の要求にしか影響しません。  
  
-   コンテキスト接続では、MARS (複数のアクティブな結果セット) がサポートされません。  
  
-   コンテキスト接続では、`SqlBulkCopy` クラスを使用できません。  
  
-   コンテキスト接続では、更新バッチ処理がサポートされません。  
  
-   `SqlNotificationRequest` は、コンテキスト接続に対して実行するコマンドと併用できません。  
  
-   コンテキスト接続に対して実行しているコマンドはキャンセルできません。 `SqlCommand.Cancel` メソッドでは、この要求が暗黙に無視されます。  
  
-   "context connection=true" を使用する場合は、他の接続文字列キーワードを使用できません。  
  
-   `SqlConnection.DataSource` の接続文字列が、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] のインスタンス名ではなく、"context connection=true" である場合、`SqlConnection` プロパティは NULL を返します。  
  
-   コンテキスト接続に対してコマンドを実行する場合に `SqlCommand.CommandTimeout` プロパティを設定しても、影響はありません。  
  
## <a name="restrictions-on-regular-connections"></a>通常の接続に関する制限事項  
 アプリケーションを開発するときは、通常の接続に適用される次の制限事項を考慮してください。  
  
-   内部サーバーに対する非同期コマンドの実行はサポートされません。 コマンドの接続文字列に "async=true" を含めてコマンドを実行すると、`System.NotSupportedException` がスローされます。 このメッセージが表示されます:"内で実行されるときに、非同期処理がサポートされていません、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]プロセスです"。  
  
-   `SqlDependency` オブジェクトはサポートされません。  
  
## <a name="see-also"></a>参照  
 [コンテキスト接続](context-connection.md)  
  
  
