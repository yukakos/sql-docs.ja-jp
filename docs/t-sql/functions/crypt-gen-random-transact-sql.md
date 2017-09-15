---
title: "CRYPT_GEN_RANDOM (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CRYPT_GEN_RANDOM_TSQL
- CRYPT_GEN_RANDOM
dev_langs:
- TSQL
helpviewer_keywords:
- CRYPT_GEN_RANDOM function
ms.assetid: b74bd9d4-758e-4b94-89a0-76dcda6d8c42
caps.latest.revision: 11
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: f2732196567dc98dc768e81b305ffa72ed453a94
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="cryptgenrandom-transact-sql"></a>CRYPT_GEN_RANDOM (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Crypto API (CAPI) で生成された暗号乱数を返します。 出力は、指定されたバイト数の 16 進数です。
  
![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>構文  
  
```sql
CRYPT_GEN_RANDOM ( length [ , seed ] )   
```  
  
## <a name="arguments"></a>引数  
*length*  
作成される数の長さ。 最大値は 8000 です。 *長さ*は型です。 **int**です。
  
*シード*  
ランダム シードとして使用するデータ (省略可能)。  以上である必要がある*長さ*データのバイト数。 *シード*は**varbinary (8000)**です。
  
## <a name="returned-types"></a>返された型  
**varbinary (8000)**
  
## <a name="permissions"></a>Permissions  
この関数はパブリックであり、特別な権限は必要ありません。
  
## <a name="examples"></a>使用例  
  
### <a name="a-generating-a-random-number"></a>A. 乱数を生成する  
次の例では、50 バイト長の乱数を生成します。
  
```sql
SELECT CRYPT_GEN_RANDOM(50) ;  
```  
  
次の例では、4 バイトのシードを使用して、4 バイト長の乱数を生成します。
  
```sql
SELECT CRYPT_GEN_RANDOM(4, 0x25F18060) ;  
```  
  
## <a name="see-also"></a>参照
[Rand 関数 & #40 です。TRANSACT-SQL と #41 です。](../../t-sql/functions/rand-transact-sql.md)
  
  
