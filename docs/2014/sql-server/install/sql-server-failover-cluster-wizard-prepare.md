---
title: SQL Server フェールオーバー クラスター ウィザード - 準備 |Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c446730a-cc71-4aaa-b142-99fd004ffb1a
caps.latest.revision: 15
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 291537f78d9d0ebfeab1fe3095ffda6e7fc4c6c9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37196622"
---
# <a name="sql-server-failover-cluster-wizard---prepare"></a>SQL Server フェールオーバー クラスター ウィザード - 準備
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] セットアップは、セットアップ操作が完了する前に、コンピューターの構成を検証します。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] セットアップの実行中、システム構成チェッカー (SCC) は [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインストール先コンピューターをスキャンします。 SCC は、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] セットアップ操作の成功を妨げる条件がないかどうかを調べます。 セットアップで [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] インストール ウィザードが起動する前に、SCC は各項目の状態を取得します。 次に、必要な条件と取得した結果を比較し、ブロックの問題解決に関するガイダンスを提供します。  
  
 システム構成チェッカーは、実行された各ルールの簡単な記述と、実行ステータスを含むレポートを生成します。 システム構成チェッカーのレポートは %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\< YYYYMMDD_HHMM >\\します。  
  
 セットアップ操作を実行する前に、次のトピックを確認してください。  
  
1.  [SQL Server 2014 のインストールに必要なハードウェアおよびソフトウェア](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [SQL Server 2014 の各エディションがサポートする機能](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [SQL Server インストールにおけるセキュリティの考慮事項](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [SQL Server のローカル言語版](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 その他の参考資料:  
  
1.  [サポートされているバージョンとエディションのアップグレード](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [フェールオーバー クラスタリングをインストールする前に](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a>参照  
 [インストール ルール](../../../2014/sql-server/install/install-rules.md)  
  
  
