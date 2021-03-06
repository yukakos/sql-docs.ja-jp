---
title: MDX 演算子リファレンス (MDX) |Microsoft ドキュメント
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: aded187be089b3c1af004bd6f7e88d75780b9f22
ms.sourcegitcommit: 97bef3f248abce57422f15530c1685f91392b494
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34742481"
---
# <a name="mdx-operator-reference-mdx"></a>MDX 演算子リファレンス (MDX)


  多次元式 (MDX) 言語は、算術演算子、論理演算子、比較演算子、セット演算子、文字列演算子、単項演算子をサポートしています。 次の表は、サポートされている演算子とその説明の一覧です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|トピック|説明|  
|-----------|-----------------|  
|[--&#40;コメント&#41; &#40;MDX&#41;](../mdx/comment-mdx-operator-reference.md)|ユーザーが指定したコメントのテキストを示します。|  
|[-&#40;を除く&#41; &#40;MDX&#41;](../mdx/except-mdx-operator.md)|2 つのセットの重複メンバーを削除して差集合を返すセット演算を実行します。|  
|[-&#40;負&#41; &#40;MDX&#41;](../mdx/negative-mdx.md)|数値式の負の値を返す単項演算を実行します。|  
|[-&#40;減算&#41; &#40;MDX&#41;](../mdx/subtract-mdx.md)|1 つの数から別の数を減算する算術演算を実行します。|  
|[&#42;&#40;Crossjoin&#41; &#40;MDX&#41;](../mdx/crossjoin-mdx-operator-reference.md)|2 つのセットのクロス積を返すセット演算を実行します。|  
|[&#42;&#40;乗算&#41; &#40;MDX&#41;](../mdx/multiply-mdx.md)|2 つの数を乗算する算術演算を実行します。|  
|[&#40;分割&#41; &#40;MDX&#41;](../mdx/divide-mdx-operator-reference.md)|1 つの数を別の数で除算する算術演算を実行します。|  
|[^ &#40;Power&#41; &#40;MDX&#41;](../mdx/power-mdx.md)|1 つの数を別の数で累乗する算術演算を実行します。|  
|[コメント&#40;MDX&#41;](../mdx/comment-mdx.md)|ユーザーが指定したコメントのテキストを示します。|  
|[&#40;コメント&#41; &#40;MDX&#41;](../mdx/comment-mdx-double-slash.md)|ユーザーが入力したテキストを示します。|  
|[:&#40;範囲&#41; &#40;MDX&#41;](../mdx/range-mdx.md)|自然な順序で並べたセットを返すセット演算を実行します。指定された 2 つのメンバーが終端になり、その 2 つのメンバーの間にあるすべてのメンバーがセットのメンバーに含まれます。|  
|[+&#40;追加&#41; &#40;MDX&#41;](../mdx/add-mdx.md)|2 つの数を加算する算術演算を実行します。|  
|[+&#40;正&#41; &#40;MDX&#41;](../mdx/positive-mdx.md)|数値式の正の値を返す単項演算を実行します。|  
|[+&#40;文字列連結&#41; &#40;MDX&#41;](../mdx/string-concatenation-mdx.md)|2 つ以上の文字列、組、または文字列と組の組み合わせを連結する文字列演算を実行します。|  
|[+&#40;共用体&#41; &#40;MDX&#41;](../mdx/union-mdx-operator-reference.md)|2 つのセットの重複部分を削除して和集合を返すセット演算を実行します。|  
|[&#60;&#40;より小さい&#41; &#40;MDX&#41;](../mdx/less-than-mdx.md)|1 つの MDX 式の値が別の MDX 式の値よりも小さいかどうかを判別する比較演算を実行します。|  
|[&#60;=&#40;以下に&#41; &#40;MDX&#41;](../mdx/less-than-or-equal-to-mdx.md)|1 つの MDX 式の値が別の MDX 式の値以下であるかどうかを判別する比較演算を実行します。|  
|[&#60;&#62;&#40;等しくない&#41; &#40;MDX&#41;](../mdx/not-equal-to-mdx.md)|1 つの MDX 式の値が別の MDX 式の値と等しくないかどうかを判別する比較演算を実行します。|  
|[=&#40;と等しい&#41; &#40;MDX&#41;](../mdx/equal-to-mdx.md)|1 つの MDX 式の値が別の MDX 式の値と等しいかどうかを判別する比較演算を実行します。|  
|[&#62;&#40;より大きい&#41; &#40;MDX&#41;](../mdx/greater-than-mdx.md)|1 つの MDX 式の値が別の MDX 式の値よりも大きいかどうかを判別する比較演算を実行します。|  
|[&#62;=&#40;より大きいか等しい&#41; &#40;MDX&#41;](../mdx/greater-than-or-equal-to-mdx.md)|1 つの MDX 式の値が別の MDX 式の値以上であるかどうかを判別する比較演算を実行します。|  
|[AND &#40;MDX&#41;](../mdx/and-mdx.md)|2 つの数値式の論理積演算を実行します。|  
|[IS &#40;MDX&#41;](../mdx/is-mdx.md)|2 つのオブジェクト式の論理比較を実行します。|  
|[NOT &#40;MDX&#41;](../mdx/not-mdx.md)|1 つの数値式の論理否定を実行します。|  
|[OR &#40;MDX&#41;](../mdx/or-mdx.md)|2 つの数値式の論理和を実行します。|  
|[XOR &#40;MDX&#41;](../mdx/xor-mdx.md)|2 つの数値式の排他的論理和演算を実行します。|  
  
## <a name="see-also"></a>参照  
 [MDX 言語リファレンス&#40;MDX&#41;](../mdx/mdx-language-reference-mdx.md)  
  
  
