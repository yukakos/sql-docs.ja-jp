---
title: SharePoint と Reporting Services サーバーと追加の (SQL Server 2014) のサポートされる組み合わせ |Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SharePoint mode
- add-in for sharepoint
ms.assetid: dc6a3372-db26-43f0-b7aa-f725acc635c2
caps.latest.revision: 27
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 49b19aaf7d34b052eac0e53c44814a961d6c4b74
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37194808"
---
# <a name="supported-combinations-of-sharepoint-and-reporting-services-server-and-add-in-sql-server-2014"></a>SharePoint、Reporting Services サーバー、Reporting Services アドインのサポートされる組み合わせ (SQL Server 2014)
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] レポート サーバーは SharePoint モードでインストールし、SharePoint 配置と統合できます。 レポート サーバー、SharePoint 用 Reporting Services アドイン、および SharePoint 製品のすべての組み合わせで、すべての機能がサポートされているわけではありません。 このトピックでは、サポートされる組み合わせの概要を説明します。 [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]統合は、次の組み合わせの結果です。  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] レポート サーバーのバージョンが SharePoint モード用に構成されていること。  
  
-   SharePoint 製品。  
  
-   SharePoint 製品用 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] アドインを SharePoint サーバーにインストールします。  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010 &#124; SharePoint 2007|  
  
## <a name="supported-combinations-of-sharepoint-and-reporting-services-components"></a>SharePoint および Reporting Services コンポーネントのサポートされる組み合わせ  
 次の表には、レポート サーバー、SharePoint 製品用 Reporting Services アドイン、および SharePoint 製品のサポートされる組み合わせの概要が示されています。 次の表に記載されていない組み合わせはサポートされません。  
  
### <a name="supported-combinations"></a>サポートされる組み合わせ  
  
||レポート サーバー|アドイン|SharePoint バージョン|Supported|  
|-|-------------------|-------------|------------------------|---------------|  
|1|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|SharePoint 2013|はい|  
|2|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|SharePoint 2010|はい|  
|3|[!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] および [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]|SharePoint 2013|はい|  
|4|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] および [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|SharePoint 2010|はい<br /><br /> 例外: Power View の統合はサポートされていません。|  
|5|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|SharePoint 2010|はい|  
|6|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|SharePoint 2010|はい|  
|7|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] および [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)]|SharePoint 2010|はい|  
|8|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|SharePoint 2010|はい|  
|9|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] SP2|SharePoint 2007|はい|  
|10|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] SP2|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] R2|SharePoint 2010|はい|  
|11|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] SP2|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] および [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] SP2|SharePoint 2007|はい|  
  
 詳細については[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]機能とレポート サーバー モードを参照してください。 [Reporting Services レポート サーバー](../reporting-services-report-server.md)します。  
  
 **追加情報:**  
  
-   Power View の統合など、SharePoint 2013 のサポートには、 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] レポート サーバーと SQL Server 2012 SP1 以降のバージョンの [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] アドインが必要です。  
  
-   Power View は [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]で導入されました。 したがって、SharePoint 2010 と Power View の統合には、 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] 以降のアドインが必要です。  
  
-   SQL Server 2008 R2 アドインは、SQL Server 2012 (以降) のレポート サーバーではサポートされていません。 SharePoint 2010 の必須コンポーネントのインストーラーによって、SQL Server 2008 R2 アドインが自動的にインストールされます。 新しいバージョンのアドインをインストールする前に、SQL Server 2008 R2 アドインをアンインストールする必要があります。 アドインのインプレース アップグレードはサポートされていません。  
  
-   **アップグレード:** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] アドインと共にインストールされた SharePoint 2010 を SharePoint 2013 にインプレース アップグレードすることはできません。 SharePoint 2013 には、 [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] 以降の [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] アドインとレポート サーバーが必要です。 アップグレードの詳細については、次を参照してください。 [Upgrade and Migrate Reporting Services](upgrade-and-migrate-reporting-services.md)します。  
  
## <a name="see-also"></a>参照  
 [SharePoint 製品用 Reporting Services アドインの検索場所](where-to-find-the-reporting-services-add-in-for-sharepoint-products.md)   
 [SQL Server 2014 のエディションでサポートされる機能](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)   
 [Reporting Services のアップグレードと移行](upgrade-and-migrate-reporting-services.md)  
  
  
