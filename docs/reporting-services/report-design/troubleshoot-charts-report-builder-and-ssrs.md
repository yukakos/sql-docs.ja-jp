---
title: グラフのトラブルシューティング (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 01/17/2018
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-design
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 3a327ffa-3b69-40d6-8015-cc01cfae9161
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e9bd6c14bcc6157b65d851d25019c8090a8f8485
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="troubleshoot-charts-report-builder-and-ssrs"></a>グラフのトラブルシューティング (レポート ビルダーおよび SSRS)
  グラフを使用するときに役立つヒントを以下に示します。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="why-does-my-chart-count-not-sum-the-values-on-the-value-axis"></a>グラフの値軸で件数がカウントされ、値が合計されない  
 ほとんどの種類のグラフでは、正確に描画するために値軸 (通常は Y 軸) に数値が必要です。 値フィールドのデータ型が **String**の場合、フィールドに数字が入っていても、グラフでは数値を表示できません。 その代わり、グラフには、そのフィールドに値が格納されている行の総数が表示されます。 この動作を回避するには、値系列に使用するフィールドに、書式設定された数値を格納した文字列ではなく、数値データ型を設定してください。  

## <a name="need-more-help"></a>他に支援が必要でしょうか。  
   
  次の方法をお試しください。  
 * スタック オーバーフローの [SQL Server Reporting Services](https://stackoverflow.com/questions/tagged/reporting-services)  
 * [Microsoft SQL Server UserVoice](https://feedback.azure.com/forums/908035-sql-server) で問題や提案を報告  
  
## <a name="see-also"></a>参照  
 [グラフ (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  
