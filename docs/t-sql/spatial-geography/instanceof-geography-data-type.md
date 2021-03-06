---
title: InstanceOf (geography データ型) | Microsoft Docs
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
- InstanceOf
- InstanceOf_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- InstanceOf method
ms.assetid: 1eaed0e4-1c72-45a9-9926-5b513335cf33
caps.latest.revision: 28
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: b97e5f1f1f42935311114a776794bff7cf6bed3e
ms.sourcegitcommit: a6596c62f607041c4402f7d5b41a232fca257c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36256984"
---
# <a name="instanceof-geography-data-type"></a>InstanceOf (geography データ型)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  **geography** インスタンスが、指定した型と同じであるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
  
.InstanceOf ( 'geography_type')  
```  
  
## <a name="arguments"></a>引数  
 *geography_type*  
 **geography** 型の階層で公開されている 16 種類の型のうちの 1 つを指定する **nvarchar(4000)** 文字列です。  
  
## <a name="return-types"></a>戻り値の型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 戻り値の型: **bit**  
  
 CLR の戻り値の型: **SqlBoolean**  
  
## <a name="remarks"></a>Remarks  
 **geography** インスタンスの型が指定した型と同じである場合、または指定した型がインスタンスの型の先祖である場合は 1 を返します。それ以外の場合は 0 を返します。  
  
 この **geography** データ型メソッドは、半球より大きい **FullGlobe** インスタンスまたは空間インスタンスをサポートします。  
  
 メソッドへの入力は、Geometry、Point、Curve、LineString、Surface、Polygon、CurvePolygon、**GeometryCollection**、**MultiSurface**、**MultiPolygon、MultiCurve、MultiLineString**、**MultiPoint**、**FullGlobe** のいずれかである必要があります。  
  
 このメソッドは、上記以外の文字列が入力に使用された場合、`ArgumentException` をスローします。  
  
 このメソッドは正確ではありません。  
  
## <a name="examples"></a>使用例  
 `MultiPoint` インスタンスを作成し、`InstanceOf()` を使用して、このインスタンスが `GeometryCollection` であるかどうかを判定する例を次に示します。  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('MULTIPOINT(-122.360 47.656, -122.343 47.656)', 4326);  
SELECT @g.InstanceOf('GEOMETRYCOLLECTION');  
```  
  
## <a name="see-also"></a>参照  
 [Geography インスタンスの拡張メソッド](../../t-sql/spatial-geography/extended-methods-on-geography-instances.md)  
  
  
