---
title: サーバーの管理者アクセス許可の付与 (Analysis Services) |Microsoft Docs
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
- administrator rights [Analysis Services]
- server-wide administrative permissions [Analysis Services]
ms.assetid: 20d1234b-a457-4a84-ae08-fe356870c466
caps.latest.revision: 34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4af61a59de6175d4241cb6b1b9700ff7ba816430
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37328852"
---
# <a name="grant-server-administrator-permissions-analysis-services"></a>サーバーの管理権限の許可 (Analysis Services)
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のインスタンス内のサーバー管理者ロールのメンバーは、そのインスタンスのすべての [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] オブジェクトとデータに制限なくアクセスできます。 データベースの作成または処理、サーバーのプロパティの変更、トレースの起動など、イベントの処理を除くサーバー全体のタスクを実行するためには、ユーザーがサーバー管理者ロールのメンバーである必要があります。  
  
 ロールのメンバーシップは、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] がインストールされるときに設定されます。 セットアップ プログラムを実行するユーザーは、サーバーを準備するときに自分または別のユーザーをロールに追加することができます。 次の手順に従うと、インストール後のタスクとしてロールのメンバーシップを変更できます。  
  
## <a name="modify-server-role-membership"></a>サーバー ロールのメンバーシップの変更  
  
1.  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]で [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]のインスタンスに接続し、オブジェクト エクスプローラーでそのインスタンス名を右クリックして、 **[プロパティ]** をクリックします。  
  
2.  **[ページの選択]** ペインで **[セキュリティ]** をクリックし、ページの下部にある **[追加]** をクリックして、サーバー ロールに 1 つまたは複数の Windows ユーザーまたはグループを追加します。  
  
     ![Management studio で、追加のユーザー ダイアログ ボックス](../media/ssas-serveradminadd.png "management studio で、追加のユーザー ダイアログ ボックス")  
  
 インストール時に、Analysis Services システム管理者としてのユーザー アカウントを 1 つ以上指定するよう求められます。  
  
 既定では、ローカルの Administrators グループのメンバーにも、Analysis Services の管理者権限が付与されます。 ローカル グループには [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のサーバー管理者ロールのメンバーシップが明示的に付与されているわけではありませんが、ローカル管理者はデータベースの作成、ユーザーとアクセス許可の追加、およびシステム管理者に許可されたその他のタスクを実行できます。 この動作は構成可能です。 によって決定されます、`BuiltinAdminsAreServerAdmins`に設定されているサーバー プロパティ**true**既定。 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]でこのプロパティを変更できます。 詳細については、「 [Security Properties](../server-properties/security-properties.md)」を参照してください。  
  
 また、分析管理オブジェクト (AMO) を使用してもサーバー ロールを管理できます。 詳細については、「[分析管理オブジェクト (AMO) による開発](../multidimensional-models/analysis-management-objects/developing-with-analysis-management-objects-amo.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [オブジェクトと操作へのアクセスの承認&#40;Analysis Services&#41;](../multidimensional-models/authorizing-access-to-objects-and-operations-analysis-services.md)   
 [セキュリティ ロール&#40;Analysis Services - 多次元データ&#41;](../multidimensional-models/olap-logical/security-roles-analysis-services-multidimensional-data.md)  
  
  
