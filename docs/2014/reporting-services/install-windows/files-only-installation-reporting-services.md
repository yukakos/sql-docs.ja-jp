---
title: ファイルのみのインストール (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- files-only installation [Reporting Services]
- installation options [Reporting Services]
ms.assetid: bdc74a8f-046c-4aa0-bfbd-4f1711dfb9ce
caps.latest.revision: 20
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 1a1617009f97b889cda7217268fc9a54e41c900c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37166275"
---
# <a name="files-only-installation-reporting-services"></a>ファイルのみのインストール (Reporting Services)
  *ファイルのみのインストール* とは、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] のインストール形態の 1 つです。このインストールでは、セットアップで、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] プログラム ファイルのフォルダー構造の作成、ディスクへのファイルのコピー、ローカル コンピューターへのレポート サーバー サービスの登録、サービス アカウントの構成、サービス アカウントへのファイル権限の付与、および [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] WMI プロバイダーの登録を行います。  
  
 ファイルのみのインストールに含まれる [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 機能は、レポート サーバー サービス (レポート サーバー Web サービス、バックグラウンド処理アプリケーション、およびレポート マネージャーをホストします)、レポート ビルダー、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 構成ツール、および [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] コマンド ライン ユーティリティ (rsconfig.exe、rskeymgmt.exe、および rs.exe) です。 このオプションは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], which must be specified as separate items if you want to install them.  
  
 他のインストール モードとは異なり、ファイルのみのモードでインストールされたレポート サーバーは、セットアップの終了時点ではまだ使用できません。 [Reporting Services 構成マネージャー &#40;ネイティブ モード&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) を使用してレポート サーバーをオンラインにするには、追加の構成が必要です。  
  
## <a name="when-to-select-files-only-installation-mode"></a>ファイルのみのインストール モードを選択する場合  
 次のような場合、ファイルのみのインストールを実行する必要があります。  
  
-   リモートのレポート サーバー データベースにレポート サーバーを接続する場合。  
  
-   レポート サーバーを名前付きインスタンスとしてインストールする場合。  
  
-   カスタムの設定や機能の使用が配置要件に含まれており、サーバー構成のタイミングと方法を完全に制御する必要がある場合。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] を含む [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]フェールオーバー クラスターをインストールする場合。  
  
## <a name="how-to-perform-a-files-only-installation"></a>ファイルのみのインストールを実行する方法  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]では、ファイルのみのインストールが既定値です。  
  
 ファイルのみのインストールを、コマンド ラインまたはインストール ウィザードで指定できます。 手順については次のトピックを参照してください。  
  
-   [SQL Server 2014 インストール ウィザードからインストール&#40;セットアップ&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md)します。  
  
-   [コマンド プロンプトから SQL Server 2014 インストール](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)します。  
  
#### <a name="example-command-line-script"></a>コマンド ライン スクリプトの例  
 わかりやすくするため、この例では /RSINSTALLMODE ="FilesOnlyMode" を指定しています。 実際には、ファイルのみのモードが既定値であるため、これを省略してもファイルのみのモードでインストールされます。  
  
```  
setup /q /ACTION=install /FEATURES=RS /InstanceName=MSSQLSERVER /RSSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE" /RSINSTALLMODE="FilesOnlyMode"  
```  
  
#### <a name="installation-wizard"></a>インストール ウィザード  
 [機能の選択] ページで [ [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ] を選択すると、[ [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 構成] ページでインストール モードを指定できるようになります。 ファイルのみのインストールを指定するには、 **[構成] ページで** [レポート サーバーを構成せずにインストールする] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] をクリックします。  
  
## <a name="see-also"></a>参照  
 [Reporting Services のインストールを確認します。](verify-a-reporting-services-installation.md)   
 [レポート サーバー サービス アカウントの構成&#40;SSRS 構成マネージャー&#41;](configure-the-report-server-service-account-ssrs-configuration-manager.md)   
 [レポート サーバー Url の構成&#40;SSRS 構成マネージャー&#41;](configure-report-server-urls-ssrs-configuration-manager.md)   
 [レポート サーバー データベース接続の構成&#40;SSRS 構成マネージャー&#41;](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)   
 [Reporting Services の SharePoint モード インストール&#40;SharePoint 2010 および SharePoint 2013&#41;](install-reporting-services-sharepoint-mode.md)   
 [Reporting Services ネイティブ モード レポート サーバーをインストールします。](install-reporting-services-native-mode-report-server.md)   
 [Reporting Services ツール](../tools/reporting-services-tools.md)  
  
  
