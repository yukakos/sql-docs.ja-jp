---
title: 物理アーキテクチャ (Analysis Services - データ マイニング) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- server architecture [Analysis Services]
- architecture [Analysis Services]
ms.assetid: 25eeecf0-6e85-4527-b94d-5503d27edaed
caps.latest.revision: 21
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4ac47ea9dbc166790d96128a758905f84d16880c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37226552"
---
# <a name="physical-architecture-analysis-services---data-mining"></a>物理アーキテクチャ (Analysis Services - データ マイニング)
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] では、サーバーとクライアントの両方のコンポーネントを使用して、ビジネス インテリジェンス アプリケーションにデータ マイニング機能を提供しています。  
  
-   サーバー コンポーネントは、Microsoft Windows サービスとして実装されます。 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のインスタンスは Windows サービスの別個のインスタンスとして実装されるため、同一のコンピューター上で複数のインスタンスがサポートされます。  
  
-   クライアントは、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] との通信に、コマンドの発行や応答の受信のための SOAP ベースのプロトコルで、Web サービスとして公開されているパブリック標準の XML for Analysis (XMLA) を使用します。 クライアント オブジェクト モデルも XMLA 経由で提供されます。クライアント オブジェクト モデルには、ADOMD.NET などのマネージド プロバイダーまたはネイティブ OLE DB プロバイダーを使用してアクセスできます。  
  
-   クエリ コマンドは、データ マイニング指向の業界標準クエリ言語であるデータ マイニング拡張機能 (DMX) を使用して発行できます。 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] データベース オブジェクトの管理には、Analysis Services スクリプト言語 (ASSL) を使用することもできます。  
  
## <a name="architectural-diagram"></a>アーキテクチャの図  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] のインスタンスはスタンドアロン サービスとして実行され、サービスとの通信は、HTTP または TCP を使用して XML for Analysis (XMLA) 経由で行われます。  
  
 AMO は、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 管理オブジェクトへのアクセスを提供する、ユーザー アプリケーションと [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンスの間のレイヤーです。 AMO は、クライアント アプリケーションからコマンドを受け取り、それを [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンス用の XMLA メッセージに変換するクラス ライブラリです。 AMO は、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンス オブジェクトをクラスとして、エンド ユーザー アプリケーションに提示します。このクラスには、コマンドを実行するメソッド メンバーと、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] オブジェクトのデータを持つプロパティ メンバーが含まれます。  
  
 次の図は、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] コンポーネントのアーキテクチャを示しており、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] インスタンス内のサービスと、インスタンスと連携するユーザー コンポーネントを含んでいます。  
  
 この図は、XML for Analysis (XMLA) リスナーと、HTTP または TCP のいずれかを使用する以外に、インスタンスにアクセスする方法がないことも示しています。  
  
> [!WARNING]  
>  DSO は非推奨とされます。 ソリューションの開発に DSO を使用しないでください。  
  
 ![Analysis Services システムのアーキテクチャ ダイアグラム](../dev-guide/media/analysisservicessystemarchitecture.gif "Analysis Services システムのアーキテクチャ ダイアグラム")  
  
## <a name="server-configuration"></a>[サーバーの構成]  
 1 つのサーバー インスタンスで複数の [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] データベースをサポートできます。各データベースに、クライアント要求に応答してオブジェクトを処理する [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] サービスの固有のインスタンスがあります。  
  
 テーブル モデルとデータ マイニング モデル/多次元モデルの両方を操作する場合は、別個のインスタンスをインストールする必要があります。 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] では、表形式モードで実行される (xVelocity メモリ内分析エンジン (VertiPaq) ストレージ エンジンを使用する) インスタンスと従来の OLAP、MOLAP、ROLAP 構成のいずれかで実行されるインスタンスのサイド バイ サイド インストールがサポートされます。 詳細については、「 [Analysis Services インスタンスのサーバー モードの決定](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)」を参照してください。  
  
 クライアントと Analysis Services サーバーの間のすべての通信には、プラットフォームや言語に依存しないプロトコルである XMLA が使用されます。 Analysis Services は、クライアントからの要求を受け取ると、その要求が OLAP に関連しているかデータ マイニングに関連しているかを判断して、適切にルーティングします。 サーバー コンポーネントの詳細については、「 [OLAP エンジンのサーバー コンポーネント](../multidimensional-models/olap-physical/olap-engine-server-components.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [論理アーキテクチャ&#40;Analysis Services - データ マイニング&#41;](logical-architecture-analysis-services-data-mining.md)  
  
  
