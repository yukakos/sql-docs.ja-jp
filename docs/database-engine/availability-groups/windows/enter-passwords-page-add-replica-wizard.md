---
title: '[パスワードの入力] ページ (レプリカ追加ウィザード) | Microsoft Docs'
ms.custom: ''
ms.date: 05/17/2016
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.swb.addreplicawizard.enterpasswords.f1
ms.assetid: e69207a0-c5c4-44e4-ae9a-4afbb67251d1
caps.latest.revision: 7
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 62845db1fc14d357a414b9f3ea8ecf65f9b0a364
ms.sourcegitcommit: 8aa151e3280eb6372bf95fab63ecbab9dd3f2e5e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "34771338"
---
# <a name="enter-passwords-page-add-replica-wizard"></a>[パスワードの入力] ページ (レプリカ追加ウィザード)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  このヘルプ トピックでは、 **[パスワードの入力]** ページのオプションについて説明します。 このトピックの対象は、 [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] の [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]です。  
  
 **[レプリカの指定]** ページで選択したレプリカに、データベース マスター キーがあるデータベースが含まれている場合は、[パスワードの入力] ページが表示されます。  
  
## <a name="enter-passwords-options"></a>パスワード入力オプション  
 **[この SQL Server のインスタンス上のユーザー データベース]** グリッドには、すべてのローカル ユーザー データベースが表示されます。 次の列で構成されます。  
  
 **名前**  
 ローカル ユーザー データベースの名前が表示されます。  
  
 **[サイズ]**  
 データベースのサイズが表示されます (サイズをウィザードで使用できる場合)。  
  
 **ステータス**  
 データベース マスターキーがあるデータベースに対して " **パスワードが必要です** " と表示されます。 データベース マスター キーのパスワードを **[パスワード]** 列に入力し、 **[更新]** をクリックします。 パスワードを正しく入力した場合、 **[状態]** 列に **[パスワードが入力されました]** が表示されます。  
  
 データベースにデータベース マスター キーがない場合、 **[状態]** 列には **[パスワードは必要ありません]** が表示されます。  
  
 **Password**  
 **[状態]** 列に " **パスワードが必要です**" と表示されている場合は、データベース マスター キーのパスワードを入力します。  
  
 **[更新]**  
 クリックしてグリッドを最新の情報に更新します。 これは、必要なパスワードを入力した後で役に立ちます。  
  
## <a name="related-tasks"></a>Related Tasks  
  
-   [可用性グループへのレプリカ追加ウィザードの使用 &#40;SQL Server Management Studio&#41;](../../../database-engine/availability-groups/windows/use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a>参照  
 [AlwaysOn 可用性グループの前提条件、制限事項、および推奨事項 &#40;SQL Server&#41;](../../../database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
