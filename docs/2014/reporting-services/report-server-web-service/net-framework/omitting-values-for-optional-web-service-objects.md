---
title: 省略可能な Web サービス オブジェクトの値を省略 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
caps.latest.revision: 36
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 3713e1e401133e8a272e80f2b4060493aa405440
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37294072"
---
# <a name="omitting-values-for-optional-web-service-objects"></a>オプションの Web サービス オブジェクトの値の省略
  レポート サーバー Web サービス複合型のプロパティには、Specified プロパティと呼ばれる付随するプロパティを持つものがあります。 このプロパティには、元のプロパティ名に "Specified" が付加された名前が割り当てられます。 このプロパティが存在することは、元のプロパティ値が省略される可能性があることを示しています。 これは、Web サービス記述言語 (WSDL) から [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] のプロキシ クラスに変換した直接的な結果です。 たとえば、複合型 <xref:ReportService2010.DataSourceDefinition.Enabled%2A> の Web サービス プロパティ <xref:ReportService2010.DataSourceDefinition> には、<xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> という名前の付随するプロパティがあります。 アプリケーションを構築していて、<xref:ReportService2010.DataSourceDefinition.Enabled%2A> プロパティの値を設定したくない場合は、<xref:ReportService2010.DataSourceDefinition.Enabled%2A> の値を指定する必要はありません。`true` という既定値が使用されます。 ただし、<xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> は `false` に設定する必要があります。 <xref:ReportService2010.DataSourceDefinition.Enabled%2A> プロパティの値を指定する場合は、<xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> を `true` に設定する必要があります。 これは書き込み可能なプロパティに適用されます。 読み取り専用プロパティの場合は、アクションを行う必要がありません。  
  
> [!IMPORTANT]  
>  このような方法を使用したプロパティの設定に失敗すると、予想されない Web サービスの動作が発生する可能性があります。  
  
 通常、追加の Specified プロパティを処理するために必要とするデータ型は`Boolean`、 `DateTime`、および`Enumeration`します。  
  
 例については、<xref:ReportService2010.ReportingService2010.CreateDataSource%2A> メソッドを参照してください。  
  
## <a name="see-also"></a>参照  
 [Web サービスと .NET Framework を使用してのアプリケーションの構築](building-applications-using-the-web-service-and-the-net-framework.md)   
 [テクニカル リファレンス (SSRS)](../../technical-reference-ssrs.md)  
  
  
