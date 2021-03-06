---
title: 変換元アシスタントを使用してソースの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 5e850b7c-4b89-42ad-b0a6-d63ac7cc9568
caps.latest.revision: 5
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4166c51bb083cbdf588c082e88e3c6cfc6b01f93
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37173313"
---
# <a name="add-a-source-using-source-assistant"></a>ソース アシスタントを使用してソースを追加する
  このトピックでは、変換元アシスタントを使用して新しい変換元を追加する手順について説明します。また、**[新しい変換元の追加]** ダイアログで使用できるオプションも示します。このダイアログは、変換元アシスタントを SSIS デザイナーにドラッグ アンド ドロップしたときに表示されます。  
  
### <a name="to-use-source-assistant-to-add-a-source"></a>変換元アシスタントを使用して変換元を追加するには  
  
1.  [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]で、変換元コンポーネントを追加する [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] パッケージを開きます。  
  
2.  **変換元アシスタント** コンポーネントを SSIS ツールボックスから **[データ フロー]** タブにドラッグします。**[新しい変換元の追加]** ダイアログ ボックスが表示されます。 次のセクションでは、ダイアログ ボックスで使用できるオプションについて詳しく説明します。  
  
3.  **[種類]** 一覧で、変換先の種類を選択します。  
  
4.  **[接続マネージャー]** 一覧で既存の接続マネージャーを選択するか、**[\<新規作成>]** を選択して新しい接続マネージャーを作成します。  
  
5.  既存の接続マネージャーを選択した場合は、**[OK]** をクリックして **[新しい変換先の追加]** ダイアログ ボックスを閉じます。 変換先と接続マネージャーがデータ フローに追加されます。  
  
6.  **[\<新規作成>]** をクリックして新しい接続マネージャーを作成する場合は、**[接続マネージャー]** ダイアログ ボックスが表示され、接続のパラメーターを指定できます。 新しい接続マネージャーの作成が完了すると、変換先と接続マネージャーが SSIS デザイナーに表示されます。  
  
  
