---
title: パッケージの実行とその他の操作の監視 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: cbbcd79f-ab9b-46ec-84cb-4821c1d16b99
caps.latest.revision: 14
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 97005d3d222019da9fad96ea9c4ab427acd1a384
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37279778"
---
# <a name="monitoring-for-package-executions-and-other-operations"></a>パッケージの実行およびその他の操作の監視
  次の 1 つ以上のツールを使用して、 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] パッケージの実行、プロジェクトの検証、およびその他の操作を監視できます。 データ タップなどの特定のツールは、 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] サーバーに配置されたプロジェクトに対してのみ使用できます。  
  
-   ログ  
  
     詳細については、「[Integration Services (SSIS) のログ記録](integration-services-ssis-logging.md)」をご覧ください。  
  
-   [レポート]  
  
     詳細については、「 [Reports for the Integration Services Server](../reports-for-the-integration-services-server.md)」を参照してください。  
  
-   ビュー  
  
     詳細については、「[ビュー &#40Integration Services カタログ&#41;](/sql/integration-services/system-views/views-integration-services-catalog)」を参照してください。  
  
-   パフォーマンス カウンター  
  
     これらのパフォーマンス カウンターの詳細については、「 [パフォーマンス カウンター](performance-counters.md)」を参照してください。  
  
-   データ タップ  
  
## <a name="operation-types"></a>操作の種類  
 いくつかの異なる種類の操作が監視されます、`SSISDB`カタログで、[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]サーバー。 各操作には、複数のメッセージを関連付けることができます。 各メッセージは、複数の種類のうちの 1 つに分類できます。 たとえば、メッセージの種類は、情報、警告、またはエラーとなります。 メッセージの種類の一覧については、Transact-SQL の [catalog.operation_messages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operation-messages-ssisdb-database) ビューに関するドキュメントを参照してください。 操作の種類の一覧については、「[catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database)」を参照してください。  
  
 9 つの状態の種類を使用して、操作の状態を示します。 状態の種類の一覧については、「[catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database)」を参照してください。  
  
## <a name="related-content"></a>関連コンテンツ  
 blogs.msdn.com のブログ エントリ「 [SSIS の T-SQL API の概要](http://go.microsoft.com/fwlink/?LinkId=249051)」  
  
  
