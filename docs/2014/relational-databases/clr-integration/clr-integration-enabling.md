---
title: CLR 統合の有効化 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
caps.latest.revision: 17
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: f6f17415e13b3f0a9774a1e530756955f28c32dd
ms.sourcegitcommit: 022d67cfbc4fdadaa65b499aa7a6a8a942bc502d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37353294"
---
# <a name="enabling-clr-integration"></a>CLR 統合の有効化
  CLR (共通言語ランタイム) 統合機能は既定では無効になっているので、CLR 統合を使用して実装されるオブジェクトを使用するには、この機能を有効にする必要があります。 CLR 統合を有効にするには使用、 **clr を有効になっている**のオプション、 **sp_configure**ストアド プロシージャ。  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 CLR の統合を無効に設定して、 **clr を有効になっている**オプションを 0 にします。 CLR 統合を無効にすると、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ではすべての CLR ルーチンの実行が停止され、すべてのアプリケーション ドメインがアンロードされます。  
  
> [!NOTE]  
>  CLR 統合を有効にするには ALTER SETTINGS サーバー レベルのアクセス許可のメンバーが暗黙的に保持されるが必要、 **sysadmin**と**serveradmin**固定サーバー ロール。  
  
> [!NOTE]  
>  コンピューターを構成しているメモリ サイズとプロセッサ数が非常に大きい場合、SQL Server の CLR 統合機能をサーバーの起動時に読み込めないことがあります。 この問題に対処するを使用してサーバーを起動、 **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]サービス スタートアップ オプション、および十分な大きさのメモリ値を指定します。 詳細については、「 [データベース エンジン サービスのスタートアップ オプション](../../database-engine/configure-windows/database-engine-service-startup-options.md)」を参照してください。  
  
> [!NOTE]  
>  簡易プーリングでは、共通言語ランタイム (CLR) の実行はサポートされていません。 CLR 統合を有効にする前に、簡易プーリングを無効にする必要があります。 詳細については、「 [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)   
 [clr enabled サーバー構成オプション](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md)   
 [RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql)   
 [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)   
 [サーバーレベルのロール](../security/authentication-access/server-level-roles.md)  
  
  
