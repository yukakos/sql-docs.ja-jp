---
title: "データの変更 (MDX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/13/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
caps.latest.revision: 30
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2f703f4f86c7c16118026ff2209bf0a1e35c8d3a
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="mdx-data-modification---modifying-data"></a>MDX データ変更のデータの変更
  多次元式 (MDX) は、ディメンションやキューブのデータの取得や操作を行うためだけでなく、ディメンションやキューブのデータの更新、つまり *書き戻し* を行うためにも使用できます。 これらの更新は、推測分析または "what-if" 分析の場合のように一時的なものであることも、データ分析に基づいて変更を加える必要がある場合のように永続的なものになることもあります。  
  
 データの更新は、ディメンション レベルまたはキューブ レベルで実行できます。  
  
 **ディメンションの書き戻し**  
 書き込み可能なディメンションのデータを変更するには、 [ALTER CUBE ステートメント (MDX)](../../../mdx/mdx-data-definition-alter-cube.md) を使用します。属性値の削除、作成、更新を反映するには、 [REFRESH CUBE ステートメント (MDX)](../../../mdx/mdx-data-definition-refresh-cube.md) を使用します。 ALTER CUBE ステートメントを使用すると、階層内のサブツリー全体を削除したり、削除されたメンバーの子を昇格させるなど、複雑な操作を実行することもできます。  
  
 **キューブの書き戻し**  
 書き込み可能なキューブに対する更新を実行するには、 [UPDATE CUBE](../../../mdx/mdx-data-manipulation-update-cube.md) ステートメントを使用します。 UPDATE CUBE ステートメントを使用すると、特定の値で組を更新できます。 サーバーにある更新されたデータをクライアント セッションのデータに適用するには、[REFRESH CUBE ステートメント (MDX)](../../../mdx/mdx-data-definition-refresh-cube.md) を使用します。  
  
 詳細については、「[キューブの書き戻しの使用 (MDX)](../../../analysis-services/multidimensional-models/mdx/mdx-data-modification-using-cube-writebacks.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [MDX クエリの基礎 &#40;Analysis Services&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  