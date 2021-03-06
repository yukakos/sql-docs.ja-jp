---
title: sp_pkeys (TRANSACT-SQL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_pkeys
- sp_pkeys_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_pkeys
ms.assetid: e614c75d-847b-4726-8f6f-cd18de688eda
caps.latest.revision: 27
author: edmacauley
ms.author: edmaca
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: d5321f34ae72051bc84a83dca70f12f772f22fc9
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33259482"
---
# <a name="sppkeys-transact-sql"></a>sp_pkeys (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  現在の環境における、単一のテーブルに関する主キーの情報を返します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
sp_pkeys [ @table_name = ] 'name'       
    [ , [ @table_owner = ] 'owner' ]   
    [ , [ @table_qualifier = ] 'qualifier' ]  
```  
  
## <a name="arguments"></a>引数  
 [ @table_name=] '*名前*'  
 情報を返す対象のテーブルです。 *名前*は**sysname**、既定値はありません。 ワイルドカードによるパターン照合はサポートされていません。  
  
 [ @table_owner=] '*所有者*'  
 指定したテーブルのテーブル所有者を指定します。 *所有者*は**sysname**、既定値は NULL です。 ワイルドカードによるパターン照合はサポートされていません。 場合*所有者*が指定されていない、基になる DBMS の既定のテーブル可視性規則が適用されます。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]、現在のユーザーには、指定した名前を持つテーブルを所有している、そのテーブルの列が返されます。 場合、*所有者*が指定されていない、現在のユーザーが、指定したテーブルを所有していないと*名前*、このプロシージャは、指定したテーブルを探します*名前*が所有する、データベース所有者です。 そのテーブルが存在する場合、そのテーブルの列が返されます。  
  
 [ @table_qualifier=] '*修飾子*'  
 テーブルの修飾名を指定します。 *修飾子*は**sysname**、既定値は NULL です。 さまざまな DBMS 製品は、3 部構成テーブルの名前付けをサポート (*修飾子 ***.*** 所有者 ***.*** 名前*)。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]、この列は、データベースの名前を表します。 製品によっては、テーブルのデータベース環境のサーバー名を表す場合があります。  
  
## <a name="return-code-values"></a>リターン コードの値  
 なし  
  
## <a name="result-sets"></a>結果セット  
  
|列名|データ型|Description|  
|-----------------|---------------|-----------------|  
|TABLE_QUALIFIER|**sysname**|テーブル識別子の名前。 このフィールドには NULL を指定できます。|  
|TABLE_OWNER|**sysname**|テーブルの所有者の名前です。 このフィールドは常に値を返します。|  
|TABLE_NAME|**sysname**|テーブルの名前。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では、この列は、sysobjects テーブルに記録されているテーブル名を表します。 このフィールドは常に値を返します。|  
|COLUMN_NAME|**sysname**|返される TABLE_NAME の各列の列名。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] では、この列は、sys.columns テーブルに記録されている列名を表します。 このフィールドは常に値を返します。|  
|KEY_SEQ|**smallint**|複数列の主キーにおける、列のシーケンス番号です。|  
|PK_NAME|**sysname**|主キー識別子。 データ ソースに適用されない場合は NULL が返されます。|  
  
## <a name="remarks"></a>解説  
 sp_pkeys では、PRIMARY KEY 制約で明示的に定義された列に関する情報が返されます。 すべてのシステムで、明示的に名前の付けられた主キーがサポートされているわけではないため、主キーの構成はゲートウェイのインプリメンタによって決定されます。 "主キー" という用語は、あるテーブルに対する論理的主キーを意味することに注意してください。 論理的主キーとして示されている各キーには、それぞれに一意なインデックスが定義されていることが前提となります。 sp_statistics には、この一意なインデックスも返されます。  
  
 Sp_pkeys ストアド プロシージャは、ODBC で SQLPrimaryKeys と同じです。 返される結果は、TABLE_QUALIFIER、TABLE_OWNER、TABLE_NAME、および KEY_SEQ の値で並べ替えられます。  
  
## <a name="permissions"></a>権限  
 スキーマに対する SELECT 権限が必要です。  
  
## <a name="examples"></a>使用例  
 次の例では、`HumanResources.Department` データベースの `AdventureWorks2012` テーブルの主キーを取得します。  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sp_pkeys @table_name = N'Department'  
    ,@table_owner = N'HumanResources';  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>例: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] および [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 次の例では、`DimAccount` データベースの `AdventureWorksPDW2012` テーブルの主キーを取得します。 テーブルに主キーがないことを示すゼロ行を返します。  
  
```  
-- Uses AdventureWorks  
  
EXEC sp_pkeys @table_name = N'DimAccount;  
```  
  
## <a name="see-also"></a>参照  
 [ストアド プロシージャ カタログ&#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/catalog-stored-procedures-transact-sql.md)   
 [システム ストアド プロシージャ &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  

