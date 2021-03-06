---
title: SUSE Linux Enterprise Server 上の SQL Server 2017 の概要 |Microsoft Docs
description: このクイック スタートでは、SUSE Linux Enterprise Server 上の SQL Server 2017 のインストールを作成し、sqlcmd を使用したデータベースの照会方法を示します。
author: rothja
ms.author: jroth
manager: craigg
ms.date: 07/16/2018
ms.topic: conceptual
ms.prod: sql
ms.component: ''
ms.suite: sql
ms.custom: sql-linux
ms.technology: linux
ms.assetid: 31ddfb80-f75c-4f51-8540-de6213cb68b8
ms.openlocfilehash: 7534ea052c5c277edb195c2a6a2a12ead1661e33
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2018
ms.locfileid: "39102590"
---
# <a name="quickstart-install-sql-server-and-create-a-database-on-suse-linux-enterprise-server"></a>クイック スタート: SQL Server をインストールし、SUSE Linux Enterprise Server 上のデータベースの作成

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-linuxonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-linuxonly.md)]

このクイック スタートで最初に SUSE Linux Enterprise Server (SLES) v12 SP2 の SQL Server 2017 をインストールします。 その後 **sqlcmd** で接続して最初のデータベースを作成し、クエリを実行します。

> [!TIP]
> このチュートリアルでは、ユーザー入力と、インターネット接続が必要です。 [無人](sql-server-linux-setup.md#unattended) または [オフライン](sql-server-linux-setup.md#offline) インストール手順に興味のある場合、[Linux 上の SQL Server のインストールのガイダンス](sql-server-linux-setup.md) を参照してください。

## <a name="prerequisites"></a>前提条件

SLES v12 SP2 コンピューターでする必要があります**に少なくとも 2 GB**メモリ。 ファイル システムは **XFS** または **EXT4** でなければいけません。 **BTRFS** といったその他のファイル システムはサポートされていません。

を、自分のマシンを SUSE Linux Enterprise Server をインストールするには[ https://www.suse.com/products/server](https://www.suse.com/products/server)します。 Azure SLES 仮想マシンを作成することもできます。 参照してください[の作成と Azure CLI を使用した Linux Vm の管理](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-manage-vm)、および使用`--image SLES`への呼び出しで`az vm create`します。

> [!NOTE]
> 現時点で、 Windows 10 の [Windows Subsystem for Linux](https://msdn.microsoft.com/commandline/wsl/about) は、インストール対象としてサポートされていません。

その他のシステム要件については、次を参照してください。 [Linux の SQL Server のシステム要件](sql-server-linux-setup.md#system)

## <a id="install"></a>SQL Server をインストールします。

Sles SQL Server を構成するには、インストールするターミナルで次のコマンドを実行、 **mssql server**パッケージ。

> [!IMPORTANT]
> 既に SQL Server 2017 の CTP または RC リリースをインストールしている場合は、古いリポジトリを削除してからその GA リポジトリの一つを登録する必要があります。 詳細については、 [リポジトリをプレビュー リポジトリからGA リポジトリに変更する](sql-server-linux-change-repo.md) を参照してください。

1. Microsoft SQL Server SLES リポジトリの構成ファイルをダウンロードするには。

   ```bash
   sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/mssql-server-2017.repo
   ```

   > [!NOTE]
   > これは、累積的な更新プログラム (CU) リポジトリです。 リポジトリ オプションとそれらの相違点についての詳細は、次を参照してください。 [Linux に SQL Server 用のリポジトリを構成する](sql-server-linux-change-repo.md)です。

1. リポジトリを更新します。

   ```bash
   sudo zypper --gpg-auto-import-keys refresh 
   ```
   
1. SQL Server をインストールするには、次のコマンドを実行します。

   ```bash
   sudo zypper install -y mssql-server
   ```

1. パッケージのインストールが完了したら、**mssql-conf setup** の実行後に、SA パスワードの設定とエディションを選択する指示に従います。

   ```bash
   sudo /opt/mssql/bin/mssql-conf setup
   ```

   > [!TIP]
   > このチュートリアルで SQL Server 2017 を試す場合、次のエディションはライセンスフリーです: Evaluation、Developer、および Express

   > [!NOTE]
   > SA アカウントは強力なパスワードを指定していることを確認してください。(最小長さが 8 文字で、大文字と小文字のアルファベット、10 進数の数字や英数字以外の記号を含む)。

1. 構成が完了したら、サービスが実行されていることを確認します。

   ```bash
   systemctl status mssql-server
   ```

1. リモートで接続する場合はファイアウォールで SQL Server の TCP ポート (既定は 1433) を開く必要もあります。 編集する必要があります、SuSE ファイアウォールを使用している場合、 **/etc/sysconfig/SuSEfirewall2**構成ファイル。 変更、 **FW_SERVICES_EXT_TCP**エントリを SQL Server のポート番号が含まれます。

   ```
   FW_SERVICES_EXT_TCP="1433"
   ```

この時点では、SQL Server は SLES コンピューター上で実行しを使用する準備ができました!

## <a id="tools"></a>SQL Server コマンド ライン ツールをインストールします。

データベースを作成するには、SQL Server で TRANSACT-SQL ステートメントを実行できるツールを使用して接続する必要があります。 次の手順で、SQL Server コマンド ライン ツール: [sqlcmd](../tools/sqlcmd-utility.md) と [bcp](../tools/bcp-utility.md) をインストールします。

1. Zypper を Microsoft SQL Server リポジトリを追加します。

   ```bash
   sudo zypper addrepo -fc https://packages.microsoft.com/config/sles/12/prod.repo 
   sudo zypper --gpg-auto-import-keys refresh
   ```

1. インストール**mssql ツール**unixODBC 開発者パッケージにします。

   ```bash
   sudo zypper install -y mssql-tools unixODBC-devel
   ```

1. 利便性のために、`/opt/mssql-tools/bin/` を **PATH** 環境変数に追加します。 これにより、完全なパスを指定せずに、ツールを実行することができます。 次のコマンドを実行し、**PATH** をログイン セッションと対話型/非ログイン セッションの両方に変更します。

   ```bash
   echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
   echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
   source ~/.bashrc
   ```

[!INCLUDE [Connect, create, and query data](../includes/sql-linux-quickstart-connect-query.md)]
