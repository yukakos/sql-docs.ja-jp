---
title: STPolyFromText (geometry データ型) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- STPolyFromText_TSQL
- STPolyFromText (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STPolyFromText (geometry Data Type)
ms.assetid: a7c1c9f0-1dd5-493b-b206-83bbfa33452b
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: ed2211f32c4d315a125744c81a5460c5bae286dc
ms.sourcegitcommit: a6596c62f607041c4402f7d5b41a232fca257c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36255044"
---
# <a name="stpolyfromtext-geometry-data-type"></a>STPolyFromText (geometry データ型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

インスタンスに格納されている Z (標高) 値と M (メジャー) 値で補完された、Open Geospatial Consortium (OGC) の Well-Known Text (WKT) 表現を基に **geometry** インスタンスを返します。
  
## <a name="syntax"></a>構文  
  
```  
  
STPolyFromText ( 'polygon_tagged_text' , SRID )  
```  
  
## <a name="arguments"></a>引数  
 *polygon_tagged_text*  
 返される **geometryPolygon** インスタンスの WKT 表現です。 *polygon_tagged_text* は **nvarchar(max)** 式です。  
  
 *SRID*  
 返される **geometryPolygon** インスタンスの SRID (spatial reference ID) を表す **int** 式です。  
  
## <a name="return-types"></a>戻り値の型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の戻り値の型: **geometry**  
  
 CLR の戻り値の型: **SqlGeometry**  
  
 OGC の型: **Polygon**  
  
## <a name="remarks"></a>Remarks  
 このメソッドでは、入力が正しい形式でない場合に、**FormatException** をスローします。  
  
## <a name="examples"></a>使用例  
 `STPolyFromText()` を使用して `geometry` インスタンスを作成する例を次に示します。  
  
```  
DECLARE @g geometry;   
SET @g = geometry::STPolyFromText('POLYGON ((5 5, 10 5, 10 10, 5 5))', 0);  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>参照  
 [OGC の静的なジオメトリ メソッド](../../t-sql/spatial-geometry/ogc-static-geometry-methods.md)  
  
  

