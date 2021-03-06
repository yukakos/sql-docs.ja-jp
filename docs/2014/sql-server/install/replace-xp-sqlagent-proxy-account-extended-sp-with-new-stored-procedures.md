---
title: Xp_sqlagent_proxy_account 拡張ストアド プロシージャで新しいストアド プロシージャの使用状況を置き換える |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- xp_sqlagent_proxy_account
ms.assetid: 0e3cc931-6237-41dd-bf0d-0c03f4d8fff2
caps.latest.revision: 17
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 4cd609cca3f8197986799a7c9630d35eeaa57d41
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37159813"
---
# <a name="replace-usage-of-the-xpsqlagentproxyaccount-extended-stored-procedure-with-new-stored-procedures"></a>xp_sqlagent_proxy_account 拡張ストアド プロシージャの代わりに新しいストアド プロシージャを使用する
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントは複数のプロキシをサポートします。 これらのプロキシは新しい一連のストアド プロシージャを使用して定義します。 新しい [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントのストアド プロシージャの詳細については、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] オンライン ブックの以下のトピックを参照してください。  
  
-   「sp_add_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_delete_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_enum_login_for_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_enum_proxy_for_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_enum_sqlagent_subsystems ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_grant_proxy_to_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_grant_login_to_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_help_proxy" ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_revoke_login_from_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_revoke_proxy_from_subsystem ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
-   「sp_update_proxy ([!INCLUDE[tsql](../../includes/tsql-md.md)])」  
  
> [!NOTE]  
>  アップグレードした後[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]を使用するすべてのステートメント、 **xp_sqlagent_proxy_account**拡張ストアド プロシージャは機能しません。 使用**sp_xp_cmdshell_proxy_account**の代わりに**xp_sqlagent_proxy_account**のプロキシを設定する**xp_cmdshell**します。  
  
## <a name="component"></a>コンポーネント  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント  
  
## <a name="see-also"></a>参照  
 [SQL Server エージェントのアップグレードに関する問題](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
