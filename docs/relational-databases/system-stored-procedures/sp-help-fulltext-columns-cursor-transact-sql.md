---
title: sp_help_fulltext_columns_cursor (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_help_fulltext_columns_cursor
- sp_help_fulltext_columns_cursor_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_fulltext_columns_cursor
ms.assetid: 26054e76-53b7-4004-8d48-92ba3435e9d7
caps.latest.revision: 28
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 075411f7cfd3f8439a9cb15a4111fa3c3a5d1421
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "37999654"
---
# <a name="sphelpfulltextcolumnscursor-transact-sql"></a>sp_help_fulltext_columns_cursor (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  カーソルを使用して、フルテキスト インデックスの作成用に指定された列を返します。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] 使用して、 [sys.fulltext_index_columns](../../relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql.md)カタログ ビューを代わりにします。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_help_fulltext_columns_cursor [ @cursor_return = ] @cursor_variable OUTPUT   
     [ , [ @table_name = ] 'table_name' ]   
     [ , [ @column_name = ] 'column_name' ]  
```  
  
## <a name="arguments"></a>引数  
 [  **@cursor_return =**] *@cursor_variable*出力  
 型の output 変数は、**カーソル**します。 結果として得られるカーソルとは、読み取り専用で、スクロール可能な動的カーソルです。  
  
 [ **@table_name =**] **'***table_name***'**  
 フルテキスト インデックス情報を要求するテーブル名を指定します。この名前は 1 つまたは 2 つの要素で構成されます。 *table_name*は**nvarchar (517)** 既定値は NULL です。 場合*table_name*を省略すると、すべてのフルテキスト インデックス付きテーブルのフルテキスト インデックス列情報を取得します。  
  
 [ **@column_name =**] **'***column_name***'**  
 フルテキスト インデックス メタデータが要求された列の名前を指定します。 *column_name*は**sysname**既定値は NULL です。 場合*column_name*を省略するかが null の場合のすべてのフルテキスト インデックス付き列のフルテキスト列情報が返されます*table_name*します。 場合*table_name*はも省略するかが null の場合、データベース内のすべてのテーブルのすべてのフルテキスト インデックス付き列のフルテキスト インデックス列情報が返されます。  
  
## <a name="return-code-values"></a>リターン コードの値  
 0 (成功) または (1) の失敗  
  
## <a name="result-sets"></a>結果セット  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**TABLE_OWNER**|**sysname**|テーブル所有者 テーブルを作成したデータベース ユーザーの名前です。|  
|**TABLE_ID**|**int**|テーブルの ID を指定します。|  
|**TABLE_NAME**|**sysname**|テーブル名です。|  
|**FULLTEXT_COLUMN_NAME**|**sysname**|フルテキスト インデックスが作成されたテーブル内にある、インデックス作成用に指定された列。|  
|**FULLTEXT_COLID**|**int**|フルテキスト インデックスが作成された列の列 ID。|  
|**FULLTEXT_BLOBTP_COLNAME**|**sysname**|フルテキスト インデックスが作成されたテーブル内の列で、フルテキスト インデックス列のドキュメントの種類を指定する列。 この値は、フルテキスト インデックス列がときにのみ適用されます、 **varbinary (max)** または**イメージ**列。|  
|**FULLTEXT_BLOBTP_COLID**|**int**|ドキュメント型列の列 ID。 この値は、フルテキスト インデックス列がときにのみ適用されます、 **varbinary (max)** または**イメージ**列。|  
|**FULLTEXT_LANGUAGE**|**sysname**|列のフルテキスト検索に使用される言語。|  
  
## <a name="permissions"></a>アクセス許可  
 実行権限は、既定のメンバーに、**パブリック**ロール。  
  
## <a name="examples"></a>使用例  
 次の例では、データベース内のすべてのテーブルを対象に、フルテキスト インデックスの作成用に指定された列に関する情報を返します。  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @mycursor CURSOR;  
EXEC sp_help_fulltext_columns_cursor @mycursor OUTPUT  
FETCH NEXT FROM @mycursor;  
WHILE (@@FETCH_STATUS <> -1)  
   BEGIN  
      FETCH NEXT FROM @mycursor;  
   END;  
CLOSE @mycursor;  
DEALLOCATE @mycursor;  
GO   
```  
  
## <a name="see-also"></a>参照  
 [COLUMNPROPERTY &#40;Transact-SQL&#41;](../../t-sql/functions/columnproperty-transact-sql.md)   
 [sp_fulltext_column &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-fulltext-column-transact-sql.md)   
 [照会する&#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-fulltext-columns-transact-sql.md)   
 [システム ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
