---
title: Type プロパティ (ADO ストリーム) |Microsoft ドキュメント
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
- _Stream::Type
- _Stream::get_Type
- _Stream::put_Type
helpviewer_keywords:
- Type property [ADO Stream]
ms.assetid: f6a17e8c-7a28-48d0-bded-76b9e0cf7639
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b334a6f6feab4e8a9a491624a5a3a43d2bd333ff
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "35282773"
---
# <a name="type-property-ado-stream"></a>Type プロパティ (ADO Stream)
含まれるデータの種類を示す、[ストリーム](../../../ado/reference/ado-api/stream-object-ado.md)(バイナリまたはテキスト)。  
  
## <a name="settings-and-return-values"></a>設定と戻り値  
 取得または設定、 [StreamTypeEnum](../../../ado/reference/ado-api/streamtypeenum.md)に含まれるデータの種類を指定する値、**ストリーム**オブジェクト。 既定値は**adTypeText**です。 ただし、バイナリ データが、新規に書き込まれた最初に空にする**ストリーム**、**型**に変更されます**adTypeBinary**です。  
  
## <a name="remarks"></a>コメント  
 **型**プロパティが読み取り/書き込みの先頭には、現在の位置は場合にのみ、**ストリーム**([位置](../../../ado/reference/ado-api/position-property-ado.md)は 0)、およびその他の任意の位置に読み取り専用です。  
  
 **型**プロパティは、読み取りと書き込みに使用するどの方法を決定、**ストリーム**です。 テキストの**ストリーム**を使用して[ReadText](../../../ado/reference/ado-api/readtext-method.md)と[WriteText](../../../ado/reference/ado-api/writetext-method.md)です。 バイナリの**ストリーム**を使用して[読み取り](../../../ado/reference/ado-api/read-method.md)と[書き込み](../../../ado/reference/ado-api/write-method.md)です。  
  
## <a name="applies-to"></a>適用対象  
 [Stream オブジェクト (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## <a name="see-also"></a>参照  
 [RecordType プロパティ (ADO)](../../../ado/reference/ado-api/recordtype-property-ado.md)   
 [Type プロパティ (ADO)](../../../ado/reference/ado-api/type-property-ado.md)
