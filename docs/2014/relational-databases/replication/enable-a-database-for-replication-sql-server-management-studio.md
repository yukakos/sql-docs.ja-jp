---
title: レプリケーションのデータベースの有効化 (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
caps.latest.revision: 31
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9be2fcfab6582aa801db160e45aa2968f7f65ff0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37210982"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a>レプリケーションのデータベースの有効化 (SQL Server Management Studio)
  固定サーバー ロール **sysadmin** のメンバーがパブリケーションの新規作成ウィザードでパブリケーションを作成すると、レプリケーションのデータベースが暗黙的に有効になります。 固定サーバー ロール **sysadmin** のメンバーは、レプリケーションのデータベースを明示的に有効にすることもできます。これにより、固定データベース ロール **db_owner** のメンバーが、そのデータベース内に 1 つ以上のパブリケーションを作成できるようになります。 データベースを明示的に有効にするには、**[パブリッシャーのプロパティ - \<Publisher>]** ボックスの **[パブリケーション データベース]** ページを使用します。 このダイアログ ボックスへのアクセスの詳細については、「 [Create a Publication](publish/create-a-publication.md)」を参照してください。  
  
### <a name="to-enable-a-database-for-replication"></a>レプリケーションのデータベースを有効化するには  
  
1.  **[パブリッシャーのプロパティ - \<Publisher>]** ダイアログ ボックスの **[パブリケーション データベース]** ページで、レプリケートする各データベースの **[トランザクション]** チェック ボックスまたは **[マージ]** チェック ボックスをオンにします。 スナップショット レプリケーションのデータベースを有効にするには、 **[トランザクション]** を選択します。  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
