---
title: 親子階層の属性 |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- data members [Analysis Services]
- nonleaf members
- MembersWithDataCaption property
- members [Analysis Services]
- members [Analysis Services], data
- leaf members
- parent-child dimensions [Analysis Services]
- MembersWithData property
ms.assetid: 249971cc-4bcd-44f1-8241-bdacc04d3d38
caps.latest.revision: 29
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: bbf5919d44a4e36e1bdddaf5c34c5e3ab6aa4315
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37220284"
---
# <a name="attributes-in-parent-child-hierarchies"></a>親子階層の属性
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] では通常、ディメンションのメンバーのコンテンツに関して一般的な前提条件が適用されます。 リーフ メンバーには、基になるデータ ソースから直接派生したデータが含まれ、非リーフ メンバーには、子メンバーで実行した集計から算出したデータが含まれています。  
  
 ただし、親子階層では、一部の非リーフ メンバーに、子メンバーから取得したデータだけでなく、基になるデータ ソースから取得したデータも含まれている場合があります。 親子階層の非リーフ メンバーの場合、基になるファクト テーブル データを含む特殊なシステム生成の子メンバーが作成されます。 これらの子メンバーは *データ メンバー*と呼ばれ、非リーフ メンバーの子孫から計算される集計値に依存しない、非リーフ メンバーに直接関係付けられた値が含まれます。  
  
 データ メンバーは、親子階層を持つディメンションでのみ使用でき、親属性によって許可される場合にのみ表示されます。 ディメンション デザイナーを使用すると、データ メンバーの表示を制御できます。 データ メンバーを公開するには設定、`MembersWithData`に親属性プロパティ`NonLeafDataVisible.`親属性に含まれるデータ メンバーを非表示にするには設定、`MembersWithData`に親属性のプロパティ`NonLeafDataHidden`します。  
  
 この設定により、非リーフ メンバーの通常の集計動作がオーバーライドされることはありません。データ メンバーは、常に集計の目的で子メンバーとして含まれています。 ただし、カスタム ロールアップ式を使用して通常の集計動作をオーバーライドすることはできます。 多次元式 (MDX) [DataMember](/sql/mdx/datamember-mdx)関数がの値に関係なく、関連付けられているデータ メンバーの値にアクセスする機能を使用する、`MembersWithData`プロパティ。  
  
 `MembersWithDataCaption` 、親属性のプロパティを提供[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]データ メンバーのメンバー名を生成するために使用する名前付けテンプレートを使用します。  
  
## <a name="using-data-members"></a>データ メンバーの使用  
 データ メンバーは、親子階層を持つ組織ディメンションに従ってメジャーを集計する際に便利です。 たとえば、次の図は、製品の総売上高を表す 3 つのレベルを持つディメンションを示しています。 最初のレベルは、全販売員の総売上高を示します。 第 2 のレベルには営業責任者別にグループ化された全販売担当者の総売上高が含まれ、第 3 のレベルには販売員別にグループ化された全販売担当者の総売上高が含まれています。  
  
 ![3 つのレベルの総売り上げ高ディメンション](../media/agdatamember1.gif "3 つのレベルの総売り上げ高ディメンション")  
  
 通常、Sales Manager 1 メンバーの値は、Salesperson 1 メンバーと Salesperson 2 メンバーの値を集計することによって取得されます。 ただし、Sales Manager 1 も製品を販売でき、Sales Manager 1 に関連した総売上が存在する場合もあるため、このメンバーにはファクト テーブルから取得したデータも格納されていることがあります。  
  
 さらに、各販売担当者メンバーの個々の歩合は異なることがあります。 この場合、販売員による総売上の合計ではなく、2 つの異なる尺度を使用して営業責任者の個々の総売上に対する歩合が計算されます。 そのため、非リーフ メンバーの基になるファクト テーブル データにアクセスできることが重要になります。 MDX`DataMember`関数を使用して、個々 の総売り上げ高、Sales Manager 1 メンバーを取得することし、gross を提供する、Sales Manager 1 メンバーの集計値からデータ メンバーを除外するは、カスタム ロールアップ式を使用できますそのメンバーに関連付けられた販売員の売り上げ。  
  
## <a name="see-also"></a>参照  
 [ディメンション属性のプロパティの参照](dimension-attribute-properties-reference.md)   
 [親子階層](parent-child-dimension.md)  
  
  
