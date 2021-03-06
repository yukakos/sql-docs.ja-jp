---
title: Append メソッド (ADOX ユーザー) |Microsoft ドキュメント
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
- Users::raw_Append
- Users::Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: b80bc5d5-78ca-4f75-956b-2ac658029cc7
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0a3c8bc74cf91e07fcac3bc9b58a7633a7083090
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "35285401"
---
# <a name="append-method-adox-users"></a>Append メソッド (ADOX ユーザー)
新しく追加[ユーザー](../../../ado/reference/adox-api/user-object-adox.md)オブジェクトを[ユーザー](../../../ado/reference/adox-api/users-collection-adox.md)コレクション。  
  
## <a name="syntax"></a>構文  
  
```  
  
Users.Append User[,Password]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ユーザー*  
 A**バリアント**値を含む、**ユーザー**追加するオブジェクトまたはユーザーを作成し、追加の名前。  
  
 *Password*  
 任意。 A**文字列**ユーザーのパスワードを含む値です。 *パスワード*パラメーターで指定された値に対応、 [ChangePassword](../../../ado/reference/adox-api/changepassword-method-adox.md)のメソッド、**ユーザー**オブジェクト。  
  
## <a name="remarks"></a>コメント  
 **ユーザー**のコレクション、[カタログ](../../../ado/reference/adox-api/catalog-object-adox.md)カタログのすべてのユーザーを表します。 **ユーザー**のコレクション、[グループ](../../../ado/reference/adox-api/group-object-adox.md)特定のグループ メンバーシップを持つユーザーのみを表します。  
  
 プロバイダーがユーザーの作成をサポートしていない場合は、エラーが発生します。  
  
> [!NOTE]
>  追加の前に、**ユーザー**オブジェクトを**ユーザー**のコレクション、**グループ**オブジェクト、**ユーザー**が同じオブジェクト[名](../../../ado/reference/adox-api/name-property-adox.md)追加する 1 つに既に存在すると、**ユーザー**のコレクション、**カタログ**です。  
  
## <a name="applies-to"></a>適用対象  
 [Users コレクション (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)  
  
## <a name="see-also"></a>参照  
 [グループとユーザーの追加、ChangePassword メソッドの例 (VB)](../../../ado/reference/adox-api/groups-and-users-append-changepassword-methods-example-vb.md)   
 [Append メソッド (ADOX 列)](../../../ado/reference/adox-api/append-method-adox-columns.md)   
 [Append メソッド (ADOX グループ)](../../../ado/reference/adox-api/append-method-adox-groups.md)   
 [Append メソッド (ADOX インデックス)](../../../ado/reference/adox-api/append-method-adox-indexes.md)   
 [Append メソッド (ADOX キー)](../../../ado/reference/adox-api/append-method-adox-keys.md)   
 [Append メソッド (ADOX プロシージャ)](../../../ado/reference/adox-api/append-method-adox-procedures.md)   
 [Append メソッド (ADOX テーブル)](../../../ado/reference/adox-api/append-method-adox-tables.md)   
 [Append メソッド (ADOX Views)](../../../ado/reference/adox-api/append-method-adox-views.md)
