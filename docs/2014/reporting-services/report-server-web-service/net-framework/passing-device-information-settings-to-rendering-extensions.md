---
title: 表示拡張機能にデバイス情報設定を渡す | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- device information settings [Reporting Services]
- Render method
- Report Server Web service, device information settings
- Web service [Reporting Services], device information settings
- XML Web service [Reporting Services], device information settings
- passing device information [Reporting Services]
- rendering extensions [Reporting Services], device information settings
- rendering [Reporting Services], settings
- device information settings [Reporting Services], about device information settings
- extensions [Reporting Services], device information settings
ms.assetid: fe718939-7efe-4c7f-87cb-5f5b09caeff4
caps.latest.revision: 46
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 9fc300712ecac2eeb4e13257515e1300e704d21c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37240222"
---
# <a name="passing-device-information-settings-to-rendering-extensions"></a>表示拡張機能にデバイス情報設定を渡す
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]では、デバイス情報設定を使用して、表示パラメーターを表示拡張機能に渡します。 レポート サーバー Web サービスの設定は **DeviceInfo** XML 要素として渡し、レポート サーバーで処理されます。 デバイス情報設定には既定値があるため、表示プロセスでは省略可能な引数と見なされます。 しかし、デバイス情報設定を使用して、表示をカスタマイズし、サーバーで提供される既定値をオーバーライドできます。  
  
 デバイス情報設定はさまざまな方法で指定できます。 プログラムでは Render メソッドを使用できます。 URL によりレポートにアクセスする場合、URL パラメーターとしてデバイス情報を指定できます。 また、[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 構成ファイルのデバイス情報設定を編集し、表示パラメーターをグローバルに指定することもできます。 表示パラメーターをグローバルで指定する方法については、「[RSReportServer.Config で表示拡張機能パラメーターをカスタマイズする](../../customize-rendering-extension-parameters-in-rsreportserver-config.md)」を参照してください。  
  
## <a name="passing-device-information-using-the-render-method"></a>Render メソッドを使用してデバイス情報を渡す  
 表示拡張機能にデバイス情報設定を渡すには使用、<xref:ReportExecution2005.ReportExecutionService.Render%2A>メソッド。 たとえば、HTML に表示するときに HTML 断片を作成するには、次の XML 文字列を <xref:ReportExecution2005.ReportExecutionService.Render%2A> メソッドに渡すことができます。  
  
```  
<DeviceInfo>  
   <HTMLFragment>True</HTMLFragment>  
</DeviceInfo>  
```  
  
 レポートが HTML 断片として表示される場合、レポートの内容は TABLE 要素内に含まれ、HTML または BODY 要素は使用されません。 HTML 断片を使用して、既存の HTML ドキュメントにレポートを組み込むことができます。 HTML 出力のデバイス情報設定の詳細については、「[HTML デバイス情報設定](../../html-device-information-settings.md)」を参照してください。  
  
## <a name="passing-device-information-using-url-access"></a>URL アクセスを使用してデバイス情報を渡す  
 URL アクセスを使用してデバイス情報設定を渡すこともできます。 デバイス情報設定は URL パラメーターとして渡されます。 次の URL アクセス文字列をレポート サーバーに渡すと、HTML ビューアー ツール バーなしで表示するレポートを生成できます。  
  
```  
http://<Server Name>/reportserver?/SampleReports/Sales Order Detail&rs:Command=Render&rs:Format=HTML4.0&rc:Toolbar=False  
```  
  
 詳細については、「[URL でデバイス情報設定を指定する](../../specify-device-information-settings-in-a-url.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [表示拡張機能のデバイス情報設定 &#40;Reporting Services&#41;](../../device-information-settings-for-rendering-extensions-reporting-services.md)   
 [RSReportServer.Config で表示拡張機能パラメーターをカスタマイズする](../../customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Web サービスと .NET Framework を使用してのアプリケーションの構築](building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
