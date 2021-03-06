---
title: nchar と nvarchar (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 7/22/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- nvarchar data type
- nchar data type
ms.assetid: 81ee5637-ee31-4c4d-96d0-56c26a742354
caps.latest.revision: 44
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 16ecf183a7f3378b3730b73bfd2c18aef92a0649
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37417371"
---
# <a name="nchar-and-nvarchar-transact-sql"></a>nchar および nvarchar (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

文字データ型は固定長、 **nchar**, 、または可変長の **nvarchar**, 、Unicode データで使用する UNICODE ucs-2 文字セットです。
  
## <a name="arguments"></a>引数  
**nchar** [ ( n ) ]  
固定長の Unicode 文字列データです。 *n* では文字列の長さを定義し、指定できる値の範囲は 1 ～ 4,000 です。 ストレージのサイズは、*n* の 2 倍のバイト数です。 照合順序のコード ページで 2 バイト文字が使用されている場合、記憶領域のサイズは *n* バイトのままです。 文字列によっては、*n* バイトの記憶領域のサイズが *n* に指定された値よりも小さくなる可能性があります。 **nchar** の ISO シノニムは、**national char** および **national character** です。
  
**nvarchar** [ ( n | **max** ) ]  
可変長の Unicode 文字列データです。 *n* では文字列の長さを定義し、指定できる値の範囲は 1 ～ 4,000 です。 **max** は、ストレージの最大サイズが 2^30-1 文字であることを示します。  ストレージの最大サイズ (バイト単位) は 2 GB です。 実際のストレージ サイズは、入力文字数の 2 倍のバイト数に 2 バイトを足した数です。 ISO シノニム **nvarchar** は national char のさまざまな **と** 各国語文字がさまざまな**です**。
  
## <a name="remarks"></a>Remarks  
データ定義または変数宣言ステートメントで *n* を指定しないと、既定の長さは 1 になります。 CAST 関数で *n* を指定しないと、既定の長さは 30 になります。
  
使用して **nchar** 列データ エントリのサイズと同等になると思われる場合。
  
使用して **nvarchar** 列データ エントリのサイズが大幅に異なると思われる場合。
  
**sysname** と機能的に等価であるシステム提供のユーザー定義データ型は、 **nvarchar (128)**, が許容されない点が異なります。 **sysname** データベース オブジェクト名を参照するために使用します。
  
使用するオブジェクト **nchar** または **nvarchar** COLLATE 句を使用して、特定の照合順序が割り当てられていない限り、データベースの既定の照合順序は割り当てられます。
  
SET ANSI_PADDING が ON にでは常に **nchar** と **nvarchar**です。 SET ANSI_PADDING OFF には適用されませんが、 **nchar** または **nvarchar** データ型。
  
プレフィックスの Unicode 文字列定数には、文字 n を付けます。なし、N プレフィックスは、文字列は、データベースの既定のコード ページに変換されます。 この既定のコード ページでは、一部の文字が認識されない場合があります。
 
> [!NOTE]  
>  文字列定数にプレフィックスとして 文字 N を付けたときに、定数への変換で Unicode 文字列データ型の最大長 (4,000) を超えない場合、暗黙的な変換では Unicode 文字列が生成されます。 それ以外の場合、暗黙的な変換では Unicode large-value (max).が生成されます。
  
> [!WARNING]  
>  Null 以外の **varchar(max)** または **nvarchar(max)** の各列には、24 バイトの追加の固定割り当てが必要で、これは並べ替え操作中の 8,060 バイトの行制限におけるカウント対象となります。 これらの追加バイトにより、テーブル内の Null 以外の **varchar(max)** または **nvarchar(max)** の列数について、暗黙的な制限が生じます。 テーブルの作成時やデータ挿入時に、最大行サイズが許容最大値の 8060 バイトを超えるという通常の警告以外の、特別なエラーは提供されません。 この大きな行サイズにより、一部の通常操作の間に、ユーザーが予期しないエラー (エラー 512 など) が発生することがあります。  このような操作の 2 つの例は、クラスター化インデックス キーの更新と、列セット全体の並べ替えです。
  
## <a name="converting-character-data"></a>文字データの変換  
文字データを変換する方法の詳細については、を参照してください。 [char と varchar (&) #40 です。TRANSACT-SQL と #41;](../../t-sql/data-types/char-and-varchar-transact-sql.md).
  
## <a name="examples"></a>使用例  
  
```sql
CREATE TABLE dbo.MyTable  
(  
  MyNCharColumn nchar(15)  
,MyNVarCharColumn nvarchar(20)
  
);  
  
GO  
INSERT INTO dbo.MyTable VALUES (N'Test data', N'More test data');  
GO  
SELECT MyNCharColumn, MyNVarCharColumn  
FROM dbo.MyTable;  
```  
  
[!INCLUDE[ssResult](../../includes/ssresult-md.md)]
  
```sql
MyNCharColumn   MyNVarCharColumn  
--------------- --------------------  
Test data       More test data  
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>参照
[ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)  
[CAST および CONVERT &#40;Transact-SQL&#41;](../../t-sql/functions/cast-and-convert-transact-sql.md)  
[COLLATE &#40;Transact-SQL&#41;](http://msdn.microsoft.com/library/4ba6b7d8-114a-4f4e-bb38-fe5697add4e9)  
[CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)  
[データ型 &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)  
[DECLARE @local_variable &#40;Transact-SQL&#41;](../../t-sql/language-elements/declare-local-variable-transact-sql.md)  
[ように (& a) #40 です。TRANSACT-SQL と #41 です。](../../t-sql/language-elements/like-transact-sql.md)  
[SET ANSI_PADDING &#40;Transact-SQL&#41;](../../t-sql/statements/set-ansi-padding-transact-sql.md)  
[SET @local_variable &#40;Transact-SQL&#41;](../../t-sql/language-elements/set-local-variable-transact-sql.md)  
[照合順序と Unicode のサポート](../../relational-databases/collations/collation-and-unicode-support.md)
  
  
