---
title: "現在の (MDX) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CURRENT
dev_langs:
- kbMDX
helpviewer_keywords:
- Current function
ms.assetid: 6f689742-f9b6-4339-a691-31ff28582c36
caps.latest.revision: 32
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 0e12e6549e02161589c769610625c82243decd17
ms.contentlocale: ja-jp
ms.lasthandoff: 08/02/2017

---
# <a name="current-mdx"></a>Current (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  繰り返し処理の実行時に、セットから現在の組を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
Set_Expression.Current   
```  
  
## <a name="arguments"></a>引数  
 *Set_Expression*  
 セットを返す有効な多次元式 (MDX) です。  
  
## <a name="remarks"></a>解説  
 繰り返し処理の各ステップで操作の対象になっている組が現在の組です。 **現在**関数は、その組を返します。 この関数は、セットに対する繰り返し処理の実行中のみ有効です。  
  
 セットを反復処理する MDX 関数が含まれて、[生成](../mdx/generate-mdx.md)関数。  
  
> [!NOTE]  
>  この関数は、セットの別名を使用するか名前付きセットを定義することによって名前が付けられたセットに対してのみ使用できます。  
  
## <a name="examples"></a>使用例  
 次の例を使用する方法を示しています、**現在**関数**生成**:  
  
 `WITH`  
  
 `//Creates a set of tuples consisting of all Calendar Years crossjoined with`  
  
 `//all Product Categories`  
  
 `SET MyTuples AS CROSSJOIN(`  
  
 `[Date].[Calendar Year].[Calendar Year].MEMBERS,`  
  
 `[Product].[Category].[Category].MEMBERS)`  
  
 `//Iterates through each tuple in the set and returns the name of the Calendar`  
  
 `//Year in each tuple`  
  
 `MEMBER MEASURES.CURRENTDEMO AS`  
  
 `GENERATE(MyTuples, MyTuples.CURRENT.ITEM(0).NAME, ", ")`  
  
 `SELECT MEASURES.CURRENTDEMO ON 0`  
  
 `FROM [Adventure Works]`  
  
## <a name="see-also"></a>参照  
 [MDX 関数リファレンス & #40 です。MDX と #41 です。](../mdx/mdx-function-reference-mdx.md)  
  
  
