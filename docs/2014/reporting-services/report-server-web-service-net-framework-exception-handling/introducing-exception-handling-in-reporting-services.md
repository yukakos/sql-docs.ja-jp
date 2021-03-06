---
title: Reporting Services における例外処理の概要 | Microsoft Docs
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
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
caps.latest.revision: 28
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 3c4ff1e27ada53361879335d90daeac5fc4f21be
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37185839"
---
# <a name="introducing-exception-handling-in-reporting-services"></a>Reporting Services における例外処理の概要
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] アプリケーションが要求をレポート サーバー Web サービスに送信し、サービスが要求を処理できない場合、サービスは SOAP 例外をクライアントに返します。 レポート サーバー Web サービスによってスローされた例外の処理は、開発するアプリケーションの重要な部分です。エラーが発生した場合にユーザーに有益な情報を返すことができるからです。  
  
 ここでは、例外の処理、無効なユーザー入力の回避、およびユーザーへの有意義なエラー情報の送信について説明します。 例外処理の一般的な情報については、[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK ドキュメントの「例外の処理とスロー」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|トピック|説明|  
|-----------|-----------------|  
|[Reporting Services での例外を処理](handling-exceptions-in-reporting-services.md)|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] における例外および Web サービスからエラーを返すときの SOAP の役割について説明します。|  
|[Reporting Services 例外処理のベスト プラクティス](best-practices/best-practices-for-reporting-services-exception-handling.md)|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] での例外処理に関する推奨事項が記載されています。|  
|[Reporting Services SoapException クラス](soapexception-class/reporting-services-soapexception-class.md)|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] の **SoapException** クラスについて説明します。|  
  
## <a name="see-also"></a>参照  
 [Web サービスと .NET Framework を使用してのアプリケーションの構築](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
