---
title: ディメンションの書き戻しを有効にする |Microsoft Docs
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
- modifying dimensions
- writeback [Analysis Services], setting up
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], writeback
- dimensions [Analysis Services], writeback
- writeback [Analysis Services]
- dimensions [Analysis Services], modifying
- manual dimension structure modifications
ms.assetid: a4b5eb5a-366d-4fc8-ad0d-5bdb8e7b4163
caps.latest.revision: 32
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 0e7ee13d4fdfa021e050c4357dc8796289a3cd4d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37247432"
---
# <a name="enable-dimension-writeback"></a>[ディメンションの書き戻しの有効化]
  キューブまたはディメンションにディメンション書き戻し拡張機能を追加すると、ユーザーはディメンション構造とメンバーを手動で変更できます。 書き込みが可能なディメンションに加えた更新は、ディメンション テーブルに直接記録されます。 この拡張機能により、ディメンションの `WriteEnabled` プロパティ設定が変更されます。  
  
 ディメンションの書き戻しを追加するには、ビジネス インテリジェンス ウィザードを使用して、 **[拡張機能の選択]** ページの **[ディメンションの書き戻しの有効化]** オプションを選択します。 次に、ウィザードに従って、ディメンションの書き戻しを適用するディメンションを選択し、そのディメンションにこのオプションを設定します。  
  
> [!NOTE]  
>  書き戻しは、SQL Server リレーショナル データベースおよびデータ マートでのみサポートされます。  
  
## <a name="selecting-a-dimension"></a>ディメンションの選択  
 ウィザードの最初の **[ディメンションの書き戻しの有効化]** ページで、ディメンションの書き戻しを適用するディメンションを指定します。 選択したこのディメンションに追加されたディメンション書き戻し拡張機能により、ディメンションが変更されます。 これらの変更は、選択したディメンションを含むすべてのキューブによって継承されます。  
  
## <a name="setting-dimension-writeback-capability"></a>ディメンションの書き戻し機能の設定  
 ウィザードの **[ディメンションの書き戻しの有効化]** の 2 ページ目で、実際に **[ディメンションへの書き戻しを有効にする]** オプションを設定します。 このオプションを選択すると、自動的に設定、`WriteEnabled`ディメンションのプロパティ`True`します。 このオプションを自動的にクリアするプロパティを設定して`False`します。  
  
## <a name="remarks"></a>コメント  
 新しいメンバーを作成するときは、ディメンションにすべての属性を含める必要があります。 ディメンションのキー属性値を指定せずにメンバーを挿入することはできません。 このため、メンバーの作成は、ディメンション テーブルに定義されている制約 (NULL 以外のキー値など) に拘束されます。 指定した列など、必要に応じて、ディメンションのプロパティで指定された列も考慮する必要があります、 `CustomRollupColumn`、`CustomRollupPropertiesColumn`または`UnaryOperatorColumn`ディメンション プロパティ。  
  
> [!WARNING]  
>  SQL Azure をデータ ソースとして使用して Analysis Services データベースへの書き戻しを実行すると、操作は失敗します。 これは仕様による結果です。既定では、複数のアクティブな結果セット (MARS) を有効にするプロバイダー オプションがオンになっていないためです。  
>   
>  これを回避するには、次の設定を接続文字列に追加し、MARS をサポートして書き戻しを有効にします。  
>   
>  `"MultipleActiveResultSets=True"`  
>   
>  詳細については、「[複数のアクティブな結果セット &#40;MARS&#41; の使用](../../relational-databases/native-client/features/using-multiple-active-result-sets-mars.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [書き込み許可ディメンション](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md)  
  
  
