---
title: Reporting Services スクリプト ファイルを書式設定する | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: tools
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], formats
- formats [Reporting Services], script files
ms.assetid: 85a207dd-4e0f-4d40-a41e-0c75f65d719c
caps.latest.revision: 43
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 887f94e6cf72c046d86857cb1258bab44e1757ca
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="format-a-reporting-services-script-file"></a>Reporting Services スクリプト ファイルを書式設定する
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] のスクリプトは [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET コード ファイルであり、Web サービス記述言語 (WSDL) で構築されたプロキシに対して記述され、Reporting Services SOAP API を定義します。 スクリプト ファイルは、拡張子 .rss が付く Unicode または UTF-8 テキスト ファイルです。  
  
 スクリプト ファイルは [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] モジュールとして動作し、ユーザー定義プロシージャとモジュール レベル変数を含みます。 スクリプト ファイルを正常に実行するには、スクリプト ファイルに Main プロシージャが含まれている必要があります。 Main プロシージャは、スクリプト ファイルを実行したとき最初に呼び出されるプロシージャです。 Main で、Web サービスの操作を追加でき、ユーザー定義サブプロシージャを実行できます。 次のコードによって Main プロシージャを作成します。  
  
```  
Public Sub Main()  
    ' Your code goes here.  
End Sub  
```  
  
 スクリプト環境は、レポート サーバーと自動的に接続し、Web プロキシ クラスを作成し、Web サービス プロキシ オブジェクトへの参照変数 (*rs*) を生成します。 作成する個別のステートメントに必要なのは、Web サービス ライブラリで使用できる Web サービス操作を実行するために、 *rs* モジュール レベル変数を参照することだけです。 次の [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] コードは、スクリプト ファイル内の Web サービス <xref:ReportService2010.ReportingService2010.ListChildren%2A> メソッドを呼び出します。  
  
```  
Public Sub Main()  
    Dim items() As CatalogItem  
    items = rs.ListChildren("/", True)  
  
    Dim item As CatalogItem  
    For Each item In items  
        Console.WriteLine(item.Name)  
    Next item  
End Sub   
```  
  
> [!IMPORTANT]  
>  ユーザーの資格情報はスクリプト環境によって管理され、RS.exe の使用によりコマンド プロンプト引数をとおして渡されます。 *rs* 変数を使用して Web サービスの認証を設定できますが、スクリプト環境を使用することをお勧めします。 スクリプト ファイル内自体では Web サービスを認証する必要がありません。 スクリプト環境の認証の詳細については、「 [RS.exe ユーティリティ &#40;SSRS&#41;](../../reporting-services/tools/rs-exe-utility-ssrs.md)」を参照してください。  
  
 スクリプト ファイル内では名前空間を宣言しません。 スクリプト環境では、 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces available to you: **System.Web.Services**, **System.Web.Services.Protocols**, **System.Xml**, and **System.IO**.  
  
 スクリプトのサンプルについては、「 [SQL Server Reporting Services 製品サンプル](http://go.microsoft.com/fwlink/?LinkId=177889)」参照してください。  
  
## <a name="see-also"></a>参照  
 [レポート サーバー Web サービス](../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [テクニカル リファレンス (SSRS)](../../reporting-services/technical-reference-ssrs.md)   
 [RS.exe ユーティリティ &#40;SSRS&#41;](../../reporting-services/tools/rs-exe-utility-ssrs.md)  
  
  
