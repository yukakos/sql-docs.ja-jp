---
title: 換算の種類 (ビジネス インテリジェンス ウィザード) を選択します |。Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.conversiontype.f1
ms.assetid: 2c664138-e8a1-4c47-8e7d-ee01c57e4692
caps.latest.revision: 23
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 34fab6780a6c10601b3f5bf31fbb7cffee3fd888
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37267348"
---
# <a name="select-conversion-type-business-intelligence-wizard"></a>[換算の種類の選択] (ビジネス インテリジェンス ウィザード)
  **[換算の種類の選択]** ページを使用すると、複数の通貨で保存されているトランザクションに関して、現地通貨とレポート用通貨の間のリレーションシップを定義できます。 現地通貨とは、 **[メジャーの選択]** ページで選択されたメジャーのトランザクションが保存される通貨です。 レポート用通貨とは、 **[メジャーの選択]** ページで選択されたトランザクションが変換される通貨です。  
  
> [!NOTE]  
>  ビジネス インテリジェンス ウィザードをディメンション デザイナーから起動した場合や、 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]のソリューション エクスプローラーでディメンションを右クリックして起動した場合、このページは表示されません。  
  
## <a name="options"></a>および  
 **[多対多]**  
 現地通貨を使用してトランザクションを格納します。 この通貨換算機能は、このようなトランザクションを **[通貨換算オプションの設定]** ページで指定された、ピボット通貨に換算した後、1 つまたは複数の他のレポート用通貨に換算します。  
  
 たとえば、ピボット通貨を米国ドル (USD) に設定し、トランザクションをユーロ (EUR)、豪ドル (AUD)、およびメキシコ ペソ (MXN) でファクト テーブルに格納するように設定できます。 このオプションを選択すると、これらのトランザクションは、指定された現地通貨からピボット通貨に換算されます。その後、換算されたトランザクションは、ピボット通貨から指定されたレポート用通貨に再び換算されます。 その結果、トランザクションを指定された現地通貨で格納して、指定のピボット通貨または **[レポート用通貨の指定]** ページで指定されたいずれかのレポート用通貨で表示できるようになります。  
  
 **多対一**  
 現地通貨を使用してトランザクションを格納します。 この通貨換算機能は、このようなトランザクションを **[通貨換算オプションの設定]** ページで指定された、ピボット通貨に換算します。 ピボット通貨は、指定された唯一のレポート用通貨としての役割を持ちます。  
  
> [!NOTE]  
>  このオプションを選択した場合、 **[レポート用通貨の指定]** ページは表示されません。  
  
 たとえば、ピボット通貨を米国ドル (USD) に設定し、トランザクションをユーロ (EUR)、豪ドル (AUD)、およびメキシコ ペソ (MXN) でファクト テーブルに格納するように設定できます。 このオプションを選択すると、これらのトランザクションは、指定された現地通貨からピボット通貨に換算されます。 その結果、トランザクションを指定された現地通貨で格納して、指定のピボット通貨で表示できるようになります。  
  
 **[一対多]**  
 トランザクションを **[通貨換算オプションの設定]** ページで指定された、ピボット通貨を使用して格納した後、1 つまたは複数の他のレポート用通貨に換算します。  
  
> [!NOTE]  
>  このオプションを選択した場合、 **[現地の通貨参照の定義]** ページは表示されません。  
  
 たとえば、ピボット通貨を米国ドル (USD) に設定し、トランザクションを USD でファクト テーブルに格納するように設定できます。 このオプションを選択すると、これらのトランザクションは、ピボット通貨から指定されたレポート用通貨に換算されます。 その結果、トランザクションを指定のピボット通貨で格納して、指定のピボット通貨または **[レポート用通貨の指定]** ページで指定されたいずれかのレポート用通貨で表示できるようになります。  
  
## <a name="see-also"></a>参照  
 [ビジネス インテリジェンス ウィザードの F1 ヘルプ](business-intelligence-wizard-f1-help.md)   
 [キューブ デザイナー &#40;Analysis Services - 多次元データ&#41;](cube-designer-analysis-services-multidimensional-data.md)   
 [ディメンション デザイナー &#40;Analysis Services - 多次元データ&#41;](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
