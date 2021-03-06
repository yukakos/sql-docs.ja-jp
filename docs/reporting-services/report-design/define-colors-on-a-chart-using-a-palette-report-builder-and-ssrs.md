---
title: パレットを使用したグラフの色の定義 (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-design
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: d95efc22-5a32-43d4-9bd2-12753e7fd395
caps.latest.revision: 6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19d6a221e21211640c99acfde02c0758249c0709
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "33019099"
---
# <a name="define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs"></a>パレットを使用したグラフの色の定義 (レポート ビルダーおよび SSRS)
  グラフの色パレットは、定義済みのパレットを選択するかカスタム パレットを定義すると、変更できます。 カスタム パレットはレポート固有です。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-the-colors-on-the-chart-using-a-built-in-color-palette"></a>組み込みの色パレットを使用してグラフの色を変更するには  
  
1.  プロパティ ペインを開きます。  
  
2.  デザイン画面で、グラフをクリックします。 グラフ オブジェクトのプロパティがプロパティ ペインに表示されます。  
  
     プロパティ ペインの上部のドロップダウン リストに、オブジェクト名 (既定では**Chart1** ) が表示されます。  
  
3.  **[グラフ]** セクションの Palette プロパティで、ドロップダウン リストから新しいパレットを選択します。  
  
    > [!NOTE]  
    >  定義済みのパレットでは、色および順序を変更することはできません。  
  
### <a name="to-define-your-own-colors-on-the-chart-using-a-custom-color-palette"></a>カスタムの色パレットを使用してグラフの色を独自に定義するには  
  
1.  プロパティ ペインを開きます。  
  
2.  デザイン画面で、グラフをクリックします。 グラフ オブジェクトのプロパティがプロパティ ペインに表示されます。  
  
3.  **[グラフ]** セクションの **Palette** プロパティで、 **Custom**を選択します。  
  
4.  CustomPaletteColors プロパティで、コレクションの編集ボタン (**[...]**) をクリックします。 **[ReportColorExpression コレクション エディター]** が表示されます。  
  
5.  **[追加]** をクリックして、色を追加します。 ドロップダウン リストから色を選択するか、[式] を選択して具体的な色の 16 進値 (たとえば "オレンジ" の場合は ff6600) を指定します。  
  
     16 進値の詳細については、MSDN の「 [カラー テーブル](http://go.microsoft.com/fwlink/?linkid=9258) 」を参照してください。  
  
6.  さらにパレットに色を追加するには、 **[追加]** をクリックします。  
  
7.  終了したら **[OK]** をクリックします。  
  
 カスタム パレットを使用している場合は、色の順序を変更して、グラフ内の各系列の色を変更することができます。  
  
## <a name="see-also"></a>参照  
 [グラフの系列の色の書式設定 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)   
 [グラフ (レポート ビルダーおよび SSRS)](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
 [複数の図形グラフでの色の統一 &#40;レポート ビルダーおよび SSRS&#41;](../../reporting-services/report-design/specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs.md)  
  
  
