---
title: STNumGeometries (geography データ型) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- STNumGeometries (geography Data Type)
- STNumGeometries_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STNumGeometries method
ms.assetid: 6ae7fac2-62f1-420f-9fc9-a09606be9605
caps.latest.revision: 14
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2a00e343b0bb0dd5c5d980c0d78e9a1b62748f12
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "37988414"
---
# <a name="stnumgeometries-geography-data-type"></a>STNumGeometries (geography データ型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  **geography** インスタンスを構成する**ジオメトリ**の数を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
.STNumGeometries ( )  
```  
  
## <a name="return-types"></a>戻り値の型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] の戻り値の型: **int**  
  
 CLR の戻り値の型: **SqlInt32**  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、**geography** インスタンスが **MultiPoint**、**MultiLineString**、**MultiPolygon**、**GeometryCollection** インスタンスではない場合に 1 を返し、**geography** インスタンスが空の場合に 0 を返します。  
  
## <a name="examples"></a>使用例  
 `MultiPoint` インスタンスを作成し、`STNumGeometries()` を使用して**ジオメトリ**の数を確認する例を次に示します。  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('MULTIPOINT((-122.360 47.656), (-122.343 47.656))', 4326);  
SELECT @g.STNumGeometries();  
```  
  
## <a name="see-also"></a>参照  
 [Geography インスタンスの OGC メソッド](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
