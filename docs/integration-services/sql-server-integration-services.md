---
title: SQL Server Integration Services | Microsoft Docs
description: エンタープライズ レベルのデータ統合およびデータ変換ソリューションを構築するための Microsoft のプラットフォームである SQL Server Integration Services について説明します
ms.custom: ''
ms.date: 07/06/2018
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
keywords:
- SSIS
helpviewer_keywords:
- SSIS
- DTS [Integration Services]
- SQL Server Integration Services
- Integration Services
- DTS [Integration Services], about Integration Services
- data integration [Integration Services]
- Data Transformation Services
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 1872cef23e9680cbec037b1d2170e8e3b02c8564
ms.sourcegitcommit: 731c5aed039607a8df34c63e780d23a8fac937e1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909862"
---
# <a name="sql-server-integration-services"></a>SQL Server Integration Services

 > 以前のバージョンの SQL Server に関連するコンテンツについては、「[SQL Server Integration Services](https://msdn.microsoft.com/library/ms141026(SQL.120).aspx)」をご覧ください。

[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] は、エンタープライズ レベルのデータ統合およびデータ変換ソリューションを構築するためのプラットフォームです。 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] を使用すると、ファイルのコピーやダウンロード、データ ウェアハウスの読み込み、データのクリーニングとマイニング、[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] のオブジェクトやデータの管理などにより、複雑なビジネスの問題を解決できます。

[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] では、XML データ ファイル、フラット ファイル、リレーショナル データ ソースなど、さまざまなソースのデータを抽出および変換して、1 つ以上のターゲットに読み込むことができます。

[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] には、組み込みのタスクと変換のリッチなセット、パッケージ作成用のグラフィカル ツール、パッケージを格納、実行、管理する [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] カタログ データベースが含まれます。

グラフィカルな [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ツールを使って、コードを 1 行も書かずにソリューションを作成できます。 広範な [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] オブジェクト モデルをプログラミングしてパッケージをプログラムで作成したり、カスタム タスクや他のパッケージ オブジェクトをコーディングしたりすることもできます。

## <a name="get-sql-server-integration-services"></a>SQL Server Integration Services を入手する

SQL Server での SQL Server Integration Services のインストール、および必要な他のダウンロードについては、「[Integration Services のインストール](install-windows/install-integration-services.md)」をご覧ください。

##  <a name="infotipsql-servermediainfo-tippng-resources"></a>![info_tip](../sql-server/media/info-tip.png) リソース
-   [SSIS フォーラムのヘルプの表示](https://social.msdn.microsoft.com/Forums/home?forum=sqlintegrationservices)
-   [Stack Overflow のヘルプの表示](http://stackoverflow.com/questions/tagged/ssis)  
-   [SSIS チーム ブログのフォロー](https://blogs.msdn.microsoft.com/ssis/)
-   [問題と要求の報告機能](https://feedback.azure.com/forums/908035-sql-server)
-   [PC のドキュメントを入手](../sql-server/sql-server-help-installation.md)
