---
title: CaseCubeDimensionID 要素 (ASSL) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- CaseCubeDimensionID Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- CaseCubeDimensionID
helpviewer_keywords:
- CaseCubeDimensionID element
ms.assetid: 96720e13-7f9b-4768-ad4b-4def40758707
caps.latest.revision: 37
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8defd95c5c21acd1e6ffa1c6ca9a9546713f51f6
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37295502"
---
# <a name="casecubedimensionid-element-assl"></a>CaseCubeDimensionID 要素 (ASSL)
  データ マイニング ディメンションをメジャー グループに関連付けるキューブ ディメンションの識別子 (ID) を格納します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<DataMiningMeasureGroupDimension>  
   ...  
   <CaseCubeDimensionID>...</CaseCubeDimensionID>  
   ...  
</DataMiningMeasureGroupDimension>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|String|  
|既定値|なし|  
|Cardinality|1-1 : 必須要素で、1 回だけ出現可能です|  
  
## <a name="element-relationships"></a>要素の関係  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[DataMiningMeasureGroupDimension](../data-type/dimension-data-type-assl.md)|  
|子要素|なし|  
  
## <a name="remarks"></a>コメント  
 親に対応する要素`CaseCubeDimensionID`分析管理オブジェクト (AMO) オブジェクト モデルは<xref:Microsoft.AnalysisServices.DataMiningMeasureGroupDimension>します。  
  
## <a name="see-also"></a>参照  
 [プロパティ&#40;ASSL&#41;](properties-assl.md)  
  
  
