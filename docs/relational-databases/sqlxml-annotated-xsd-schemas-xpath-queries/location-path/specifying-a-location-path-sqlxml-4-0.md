---
title: ロケーション パス (SQLXML 4.0) の指定 |Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: sqlxml
ms.reviewer: ''
ms.suite: sql
ms.technology: xml
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- absolute location path
- node-set [SQLXML]
- XPath queries [SQLXML], location paths
- relative location path [SQLXML]
- location path for XPath query
ms.assetid: a23a2b75-bc69-49f0-99db-05e14dc15bc0
caps.latest.revision: 24
author: douglaslMS
ms.author: douglasl
manager: craigg
monikerRange: = azuresqldb-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 2c2cad3730cd0948f94adc8ad5b877fd2e921bc3
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38032557"
---
# <a name="specifying-a-location-path-sqlxml-40"></a>ロケーション パスの指定 (SQLXML 4.0)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  XPath クエリは式の形式で指定され、 式の種類にはさまざまなものがあります。 ロケーション パスは、コンテキスト ノードに相対的なノードのセットを選択する式です。 ロケーション パスを評価すると、結果はノード セットになります。  
  
## <a name="types-of-location-paths"></a>ロケーション パスの種類  
 ロケーション パスは、次のいずれかの形式で指定できます。  
  
-   **絶対ロケーション パス**  
  
     絶対ロケーション パスは、ドキュメントのルート ノードから開始します。 構成要素はスラッシュ記号 (/) で、その後に相対ロケーション パスを続けることもできます。 スラッシュ記号 (/) によって、ドキュメントのルート ノードが選択されます。  
  
-   **相対ロケーション パス**  
  
     相対ロケーション パスは、ドキュメントのコンテキスト ノードから開始します。 構成要素は連続する 1 つ以上のロケーション ステップで、区切りにはスラッシュ記号 (/) を使用します。 各ステップで、コンテキスト ノードに対して相対的なノードのセットが選択されます。 最初のステップでは、コンテキスト ノードに対して相対的なノードのセットが選択され、 そのセットの各ノードが次のステップのコンテキスト ノードとして使用されます。 そのステップで指定されたノードのセットは結合されます。 たとえば、 **child::order/child::orderdetail**選択、  **\<OrderDetail >** の子要素、 **\<順序 >** 要素コンテキスト ノードの子です。  
  
    > [!NOTE]  
    >  SQLXML 4.0 における XPath の実装では、XPath が明示的に絶対として指定されていない場合でも、各 XPath クエリはルート コンテキストから開始します。 たとえば、"Customer" で開始する XPath クエリは "/Customer" として扱われます。 XPath クエリでは**Customer [Order]** 顧客はルート コンテキストから始まりますが、Order は Customer コンテキストから始まります。 詳細については、次を参照してください。[を使用して XPath クエリの概要&#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/introduction-to-using-xpath-queries-sqlxml-4-0.md)します。  
  
## <a name="location-steps"></a>ロケーション ステップ  
 ロケーション パス (絶対または相対) は、次の 3 つの部分から成るロケーション ステップで構成されます。  
  
-   **Axis**  
  
     軸によって、ロケーション ステップで選択されるノードと、コンテキスト ノードの間のツリー リレーションシップが指定されます。 **親**、**子**、**属性**、および**セルフ**軸がサポートされます。 場合、**子**軸は、クエリによって選択されたすべてのノードはコンテキスト ノードの子ロケーション パスで指定します。 場合、**親**軸を指定すると、選択したノードのコンテキスト ノードの親ノードです。 場合、**属性**軸を指定すると、選択されたノードはコンテキスト ノードの属性。  
  
-   **ノード テスト**  
  
     ノード テストによって、ロケーション ステップで選択されるノードの型が決まります。 すべての軸 (**子**、**親**、**属性**、および**セルフ**) 主ノード型があります。 **属性**軸の主ノード型は**\<属性 >** します。 **親**、**子**、および**セルフ**軸の場合、主ノード型は**\<要素 >** します。  
  
     たとえば、次の場所のパスを指定します**child::customer**、 **\<顧客 >** コンテキスト ノードの子要素を選択します。 **子**軸に**\<要素 >** 、主ノード型と、ノード テスト Customer 場合は、TRUE 顧客、 **\<要素 >** ノード。  
  
-   **選択述語 (0 個以上)**  
  
     述語では、軸に関してノード セットをフィルター選択します。 XPath 式内に選択述語を指定するときには、SELECT ステートメント内に WHERE 句を指定するときのように、 述語はかっこで囲みます。 選択述語に指定したテストを適用すると、そのノード テストによって返されたノードがフィルター選択されます。 フィルター選択されたノード セットの各ノードに対し、ノードをコンテキスト ノード、ノード セット内のノード数をコンテキストのサイズとして、述語式が評価されます。 述語式が TRUE と評価された場合、そのノードは結果のノード セットに含められます。  
  
     ロケーション ステップの構文では、軸名とノード テストを 2 つのコロン (::) で区切り、その後に式をそれぞれ角かっこで囲んで指定します。式は指定しなくてもかまいません。 たとえば、XPath 式 (ロケーション パス) **child::customer [@CustomerID= 'ALFKI']** すべて選択、 **\<顧客 >** コンテキスト ノードの子要素。 だけを返すノードのセットに、述語内のテストが適用されます、 **\<顧客 >** の値 'ALFKI' の属性を持つ要素ノード、 **CustomerID**属性。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [軸の指定&#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/location-path/specifying-an-axis-sqlxml-4-0.md)  
 軸を指定する例を示します。  
  
 [ロケーション パスでノード テストの指定&#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/location-path/specifying-a-node-test-in-the-location-path-sqlxml-4-0.md)  
 ノード テストを指定する例を示します。  
  
 [ロケーション パスでの述語の選択範囲を指定する&#40;SQLXML 4.0&#41;](../../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/location-path/specifying-selection-predicates-in-the-location-path-sqlxml-4-0.md)  
 選択述語を指定する例を示します。  
  
  
