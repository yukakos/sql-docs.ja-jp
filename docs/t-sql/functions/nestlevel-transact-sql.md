---
title: "@@NESTLEVEL (TRANSACT-SQL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '@@NESTLEVEL'
- '@@NESTLEVEL_TSQL'
dev_langs:
- TSQL
helpviewer_keywords:
- '@@NESTLEVEL function'
- nesting stored procedures
- stored procedure nesting levels [SQL Server]
ms.assetid: 8c0b2134-8616-44f6-addc-6583c432fb62
caps.latest.revision: 40
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: ce6980ba008189a1588dc87e955a26125dc6a30d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/01/2017

---
# <a name="nestlevel-transact-sql"></a>@@NESTLEVEL (TRANSACT-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  現在のストアド プロシージャがローカル サーバーで実行中のトランザクションの入れ子レベルを返します (初期値は 0)。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
@@NESTLEVEL  
```  
  
## <a name="return-types"></a>戻り値の型  
 **int**  
  
## <a name="remarks"></a>解説  
 ストアド プロシージャが別のストアド プロシージャを呼び出したり、共通言語ランタイム (CLR) のルーチン、型、または集計を参照してマネージ コードを実行するたびに、入れ子レベルが増加します。 この値が最大値の 32 を超えると、そのトランザクションは終了します。  
  
 場合 @@NESTLEVEL内で実行される、[!INCLUDE[tsql](../../includes/tsql-md.md)]文字列は 1 + 現在の入れ子レベルに、値が返されます。 場合 @@NESTLEVELが実行される動的に sp_executesql を使用して、返される値は 2 + 現在の入れ子レベル。  
  
## <a name="examples"></a>使用例  
  
### <a name="a-using-nestlevel-in-a-procedure"></a>A. を使用して@NESTLEVELプロシージャ  
 次の例では、別のプロシージャを呼び出すプロシージャと、それぞれの `@@NESTLEVEL` 設定を表示するプロシージャの、2 つのプロシージャを作成します。  
  
```  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID (N'usp_OuterProc', N'P')IS NOT NULL  
    DROP PROCEDURE usp_OuterProc;  
GO  
IF OBJECT_ID (N'usp_InnerProc', N'P')IS NOT NULL  
    DROP PROCEDURE usp_InnerProc;  
GO  
CREATE PROCEDURE usp_InnerProc AS   
    SELECT @@NESTLEVEL AS 'Inner Level';  
GO  
CREATE PROCEDURE usp_OuterProc AS   
    SELECT @@NESTLEVEL AS 'Outer Level';  
    EXEC usp_InnerProc;  
GO  
EXECUTE usp_OuterProc;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Outer Level`  
  
 `-----------`  
  
 `1`  
  
 `Inner Level`  
  
 `-----------`  
  
 `2`  
  
### <a name="b-calling-nestlevel"></a>B. を呼び出す@NESTLEVEL  
 次の例では、`SELECT`、`EXEC`、および `sp`_`executesql` のそれぞれが `@@NESTLEVEL` を呼び出すときに、それらが返す値の違いを示します。  
  
```  
CREATE PROC usp_NestLevelValues AS  
    SELECT @@NESTLEVEL AS 'Current Nest Level';  
EXEC ('SELECT @@NESTLEVEL AS OneGreater');   
EXEC sp_executesql N'SELECT @@NESTLEVEL as TwoGreater' ;  
GO  
EXEC usp_NestLevelValues;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Current Nest Level`  
  
 `------------------`  
  
 `1`  
  
 `(1 row(s) affected)`  
  
 `OneGreater`  
  
 `-----------`  
  
 `2`  
  
 `(1 row(s) affected)`  
  
 `TwoGreater`  
  
 `-----------`  
  
 `3`  
  
 `(1 row(s) affected)`  
  
## <a name="see-also"></a>参照  
 [構成関数 &#40;Transact-SQL&#41;](../../t-sql/functions/configuration-functions-transact-sql.md)   
 [ストアド プロシージャの作成](../../relational-databases/stored-procedures/create-a-stored-procedure.md)   
 [@@TRANCOUNT &#40;Transact-SQL&#41;](../../t-sql/functions/trancount-transact-sql.md)  
  
  