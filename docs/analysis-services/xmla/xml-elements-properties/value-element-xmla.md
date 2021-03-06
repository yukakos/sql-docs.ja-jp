---
title: 要素 (XMLA) の値 |Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 2ecaaf902ee1f29700b2d6333bbccd549d9c2193
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38062853"
---
# <a name="value-element-xmla"></a>Value 要素 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  目的の値が含まれています、[属性](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md)によって追加される要素、[挿入](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)コマンド、または[セル](../../../analysis-services/xmla/xml-elements-properties/cell-element-xmla.md)によって更新される要素、 [UpdateCells](../../../analysis-services/xmla/xml-elements-commands/updatecells-element-xmla.md)コマンド。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Attribute> <!-- or Cell --!>  
   ...  
   <Value>...</Value>  
   ...  
</Attribute>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|Any|  
|既定値|なし|  
|Cardinality|1-1 : 必須要素で、1 回だけ出現します|  
  
## <a name="element-relationships"></a>要素間のリレーションシップ  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[属性](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md)、[セル](../../../analysis-services/xmla/xml-elements-properties/cell-element-xmla.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 **属性**、要素、**値**要素は、後に、メンバーを含める必要がありますを目的の値を含む、**挿入**コマンドがコミットされました。 メンバーの挿入の詳細については、次を参照してください。[挿入、更新、および削除するメンバー &#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/inserting-updating-and-dropping-members-xmla.md)します。  
  
 **セル**、要素、**値**要素は、後に、セルを含める必要がありますを目的の値を含む、 **UpdateCells**コマンドがコミットされました。 そのセルの書き戻しテーブルに格納される実際の値は、セルの元の値と目的の値との差異です。  
  
 この要素が使用するデータ型は、更新対象のセルのデータ型と一致している必要があります。  
  
 セルの更新の詳細については、「[セルの更新 &#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/updating-cells-xmla.md)」を参照してください。  
  
## <a name="see-also"></a>参照
 [CellOrdinal 要素&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/cellordinal-element-xmla.md)   
 [要素を挿入&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)   
 [UpdateCells 要素&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-commands/updatecells-element-xmla.md)   
 [プロパティ&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
