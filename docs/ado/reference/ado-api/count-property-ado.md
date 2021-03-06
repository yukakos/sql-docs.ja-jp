---
title: Count プロパティ (ADO) |Microsoft ドキュメント
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Collection::Count
helpviewer_keywords:
- Count property [ADO]
ms.assetid: da9ccd1f-d402-41a2-940c-45556fc5340d
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: bccb2760b124040973baa7ba889d2110ec5efe95
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "35277231"
---
# <a name="count-property-ado"></a>Count プロパティ (ADO)
コレクション内のオブジェクトの数を示します。  
  
## <a name="return-value"></a>戻り値  
 返します、**長い**値。  
  
## <a name="remarks"></a>コメント  
 使用して、**カウント**プロパティを指定したコレクション内のオブジェクトの数を調べる。  
  
 コレクションのメンバーの番号付けは 0 から始まるため、する必要がありますループ常に 0 から始まるの値で終わる、**カウント**から 1 を引いたプロパティです。 Microsoft Visual Basic を使用しているし、確認せずにコレクションのメンバーをループ処理する場合、**カウント**プロパティを使用して、**ごとにしています.[次へ]** コマンド。  
  
 場合、**カウント**プロパティが 0 で、コレクションにオブジェクトがありません。  
  
## <a name="applies-to"></a>適用対象  
  
||||  
|-|-|-|  
|[Axes コレクション (ADO MD)](../../../ado/reference/ado-md-api/axes-collection-ado-md.md)|[Columns コレクション (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)|[CubeDefs コレクション (ADO MD)](../../../ado/reference/ado-md-api/cubedefs-collection-ado-md.md)|  
|[Dimensions コレクション (ADO MD)](../../../ado/reference/ado-md-api/dimensions-collection-ado-md.md)|[Errors コレクション (ADO)](../../../ado/reference/ado-api/errors-collection-ado.md)|[Fields コレクション (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)|  
|[Groups コレクション (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)|[Hierarchies コレクション (ADO MD)](../../../ado/reference/ado-md-api/hierarchies-collection-ado-md.md)|[Indexes コレクション (ADOX)](../../../ado/reference/adox-api/indexes-collection-adox.md)|  
|[Keys コレクション (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)|[Levels コレクション (ADO MD)](../../../ado/reference/ado-md-api/levels-collection-ado-md.md)|[Members コレクション (ADO MD)](../../../ado/reference/ado-md-api/members-collection-ado-md.md)|  
|[Parameters コレクション (ADO)](../../../ado/reference/ado-api/parameters-collection-ado.md)|[Positions コレクション (ADO MD)](../../../ado/reference/ado-md-api/positions-collection-ado-md.md)|[Procedures コレクション (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)|  
|[Properties コレクション (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)|[Tables コレクション (ADOX)](../../../ado/reference/adox-api/tables-collection-adox.md)|[Users コレクション (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)|  
|[Views コレクション (ADOX)](../../../ado/reference/adox-api/views-collection-adox.md)|||  
  
## <a name="see-also"></a>参照  
 [Count プロパティの例 (VB)](../../../ado/reference/ado-api/count-property-example-vb.md)   
 [Count プロパティの例 (vc++)](../../../ado/reference/ado-api/count-property-example-vc.md)   
 [Refresh メソッド (ADO)](../../../ado/reference/ado-api/refresh-method-ado.md)
