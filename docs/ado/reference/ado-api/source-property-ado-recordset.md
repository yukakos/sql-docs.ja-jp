---
title: "Source プロパティ (ADO レコード セット) |Microsoft ドキュメント"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Recordset15::putref_Source
- Recordset15::Source
- Recordset15::PutSource
- Recordset15::get_Source
- Recordset15::GetSource
- Recordset15::PutRefSource
- Recordset15::put_Source
helpviewer_keywords:
- Source property [ADO Recordset]
ms.assetid: a05ba2c9-2821-4343-8607-4de9b764ec91
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ea45eae107fa55355adeb195e7e4fc5cf0a3c762
ms.contentlocale: ja-jp
ms.lasthandoff: 09/09/2017

---
# <a name="source-property-ado-recordset"></a>Source プロパティ (ADO レコード セット)
データ ソースを示す、 [Recordset](../../../ado/reference/ado-api/recordset-object-ado.md)オブジェクト。  
  
## <a name="settings-and-return-values"></a>設定と戻り値  
 セット、**文字列**値または[コマンド](../../../ado/reference/ado-api/command-object-ado.md)オブジェクト参照; だけを返す、**文字列**のソースを示す値、**レコード セット**です。  
  
## <a name="remarks"></a>解説  
 使用して、**ソース**のデータ ソースを指定するプロパティ、 **Recordset**オブジェクトを使用して、次のいずれかの:**コマンド**オブジェクト変数、SQL ステートメント、ストアド プロシージャでは、または、テーブル名。  
  
 設定した場合、**ソース**プロパティを**コマンド**オブジェクト、 [ActiveConnection](../../../ado/reference/ado-api/activeconnection-property-ado.md)のプロパティ、**レコード セット**オブジェクトが継承、値、 **ActiveConnection**プロパティに指定された**コマンド**オブジェクト。 ただし、読み取り、**ソース**プロパティは返されません、**コマンド**オブジェクトです代わりに、を返します、 [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md)のプロパティ、**コマンド。**オブジェクトを設定する、**ソース**プロパティです。  
  
 場合、**ソース**プロパティは、SQL ステートメント、ストアド プロシージャ、またはテーブル名、パフォーマンスを最適化するには、適切なを渡すことによって*オプション*引数と、 [を開く](../../../ado/reference/ado-api/open-method-ado-recordset.md)メソッドの呼び出しです。  
  
 **ソース**閉じられたために、プロパティは読み取り/書き込み**Recordset**オブジェクトおよび読み取り専用開く**レコード セット**オブジェクト。  
  
## <a name="applies-to"></a>適用対象  
 [レコード セット オブジェクト (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>参照  
 [ソース プロパティの例 (VB)](../../../ado/reference/ado-api/source-property-example-vb.md)   
 [Source プロパティ (ADO エラー)](../../../ado/reference/ado-api/source-property-ado-error.md)   
 [Source プロパティ (ADO レコード)](../../../ado/reference/ado-api/source-property-ado-record.md)