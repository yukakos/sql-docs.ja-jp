---
title: DECOMPRESS (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 11/30/2015
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DECOMPRESS
- DECOMPRESS_TSQL
helpviewer_keywords:
- DECOMPRESS function
ms.assetid: 738d56be-3870-4774-b112-3dce27becc11
caps.latest.revision: 8
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9c2eb8c020127211b25b762d96e6e376be7e234c
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38002694"
---
# <a name="decompress-transact-sql"></a>DECOMPRESS (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

この関数は GZIP アルゴリズムを使用して、入力式の値の圧縮を解除します。 `DECOMPRESS` はバイト配列 (VARBINARY(MAX) 型) を返します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
DECOMPRESS ( expression )  
```  
  
## <a name="arguments"></a>引数  
 *式 (expression)*  
**varbinary(***n***)**、**varbinary(max)**、**binary(***n***)** 値。 詳細については、「[式 &#40;Transact-SQL&#41;](../../t-sql/language-elements/expressions-transact-sql.md)」を参照してください。  
  
## <a name="return-types"></a>戻り値の型  
データ型 **varbinary(max)** の値。 `DECOMPRESS` は ZIP アルゴリズムを使用し、入力引数の圧縮を解除します。 ユーザーは、必要な場合、結果をターゲットの型に明示的にキャストする必要があります。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="examples"></a>使用例  
  
### <a name="a-decompress-data-at-query-time"></a>A. クエリ時にデータの圧縮を解除する  
この例では、圧縮されたテーブル データを返す方法を示します。  
  
```  
SELECT _id, name, surname, datemodified,  
             CAST(DECOMPRESS(info) AS NVARCHAR(MAX)) AS info  
FROM player;  
```  
  
### <a name="b-display-compressed-data-using-computed-column"></a>B. 計算列を使用して圧縮されたデータを表示する  
この例では、圧縮解除されたデータを格納するテーブルの作成方法を示しています。  
  
```  
CREATE TABLE example_table (  
    _id int primary key identity,  
    name nvarchar(max),  
    surname nvarchar(max),  
    info varbinary(max),  
    info_json as CAST(decompress(info) as nvarchar(max))  
);  
```  
  
## <a name="see-also"></a>参照  
 [文字列関数 &#40;Transact-SQL&#41;](../../t-sql/functions/string-functions-transact-sql.md)   
 [COMPRESS &#40;Transact-SQL&#41;](../../t-sql/functions/compress-transact-sql.md)  
  
  
