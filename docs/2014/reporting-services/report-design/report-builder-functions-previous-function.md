---
title: Previous 関数 (レポート ビルダーおよび SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 403a9384-6ca4-42e8-97ca-ac3f6fe4316b
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 95a2dfb8ef3ac1420f243355f732daa246d81d0a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37198542"
---
# <a name="previous-function-report-builder-and-ssrs"></a>Previous 関数 (レポート ビルダーおよび SSRS)
  アイテムの、指定されたスコープ内の直前のインスタンスに対応する値または指定された集計値を返します。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a>構文  
  
```  
  
Previous(expression, scope)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *式 (expression)*  
 (`Variant`または`Binary`) を使用してデータを識別する式と以前の値の取得対象となる`Fields!Fieldname.Value`または`Sum(Fields!Fieldname.Value)`します。  
  
 *スコープ (scope)*  
 (`String`) 省略可能です。 グループまたはデータ領域、または null の名前 (`Nothing`で[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)])、によって指定された以前の値を取得する対象のスコープを指定する*式*します。  
  
## <a name="return-type"></a>戻り値の型  
 返します、`Variant`または`Binary`します。  
  
## <a name="remarks"></a>コメント  
 `Previous` 関数は、すべての並べ替えおよびフィルター処理が適用された後、指定されたスコープで評価された式の直前の値を返します。  
  
 場合*式*集計が含まれていない、`Previous`既定値は、レポート アイテムの現在のスコープに機能します。  
  
 詳細グループで使用して`Previous`詳細行の前のインスタンスで、フィールドの参照の値を指定します。  
  
> [!NOTE]  
>  `Previous`関数では、詳細グループでフィールドへの参照のみがサポートしています。 たとえば、詳細グループのテキスト ボックスの場合、 `=Previous(Fields!Quantity.Value)` では、直前の行から `Quantity` フィールドのデータが返されます。 この式が先頭行にある場合は、NULL ([!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] では `Nothing`) が返されます。  
  
 場合*式*既定のスコープを使用する集計関数を含んで`Previous`集計関数の呼び出しに指定されたスコープの直前のインスタンス内のデータを集計します。  
  
 場合*式*、既定以外のスコープを指定する集計関数が含まれています、*スコープ*のパラメーター、`Previous`関数で指定されたスコープのコンテナー スコープを指定する必要があります集計関数の呼び出し。  
  
 関数は、 `Level`、 `InScope`、`Aggregate`と`Previous`では使用できません、*式*パラメーター。 集計関数に *recursive* パラメーターを指定することはサポートされていません。  
  
 詳細については、「[集計関数リファレンス &#40;レポート ビルダーおよび SSRS&#41;](report-builder-functions-aggregate-functions-reference.md)」および「[合計、集計、および組み込みコレクションの式のスコープ &#40;レポート ビルダーおよび SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)」を参照してください。  
  
## <a name="examples"></a>使用例  
  
### <a name="description"></a>説明  
 次のコード例は、データ領域の既定のデータ行に配置されると、直前の行の `LineTotal` フィールドの値が表示されます。  
  
### <a name="code"></a>コード  
  
```  
=Previous(Fields!LineTotal.Value)  
```  
  
### <a name="description"></a>説明  
 次の例では、特定の月日の売上合計と、前年のその月日の値を計算する式を示します。 この式は、子グループ `GroupbyDay`に属する行内のセルに追加されます。 その親グループは `GroupbyMonth`で、このグループの親グループは `GroupbyYear`です。 この式では、GroupbyDay (既定のスコープ) の結果、次に `GroupbyYear` (親グループ `GroupbyMonth`の親) の結果が表示されます。  
  
 たとえば、親グループが `Year`、その子グループが `Month`、そのまた子グループが `Day` という名前のデータ領域 (入れ子レベル 3) の場合、 グループ `=Previous(Sum(Fields!Sales.Value,"Day"),"Year")` に関連付けられた行内の式 `Day` は、前年の同じ月日の売上高の値を返します。  
  
### <a name="code"></a>コード  
  
```  
=Sum(Fields!Sales.Value) & " " & Previous(Sum(Fields!Sales.Value,"GroupbyDay"),"GroupbyYear")  
```  
  
## <a name="see-also"></a>参照  
 [レポートで式を使用して&#40;レポート ビルダーおよび SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [式の例 (レポート ビルダーおよび SSRS)](expression-examples-report-builder-and-ssrs.md)   
 [式で使用されるデータ型 &#40;レポート ビルダーおよび SSRS&#41;](expressions-report-builder-and-ssrs.md)   
 [合計、集計、および組み込みコレクションの式のスコープ&#40;レポート ビルダーおよび SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
