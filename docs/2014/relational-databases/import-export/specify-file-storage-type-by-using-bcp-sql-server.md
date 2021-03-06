---
title: bcp を使用したファイル ストレージ型の指定 (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: data-movement
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], file storage types
- importing data, file storage types
- native data format [SQL Server]
- file storage types [SQL Server]
- data formats [SQL Server], file storage types
ms.assetid: 85e12df8-1be7-4bdc-aea9-05aade085c06
caps.latest.revision: 30
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: fff9084513f21333125eaee8995eebfd3e22e1a4
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37251994"
---
# <a name="specify-file-storage-type-by-using-bcp-sql-server"></a>bcp を使用したファイル ストレージ型の指定 (SQL Server)
  *ファイル ストレージ型* は、データ ファイルへのデータの格納方法を記述します。 データとしてエクスポートできますデータ ファイルに、データベース テーブルの型 (ネイティブ形式)、文字表現 (文字形式)、または任意のデータ型を暗黙的な変換がサポートされています。たとえば、コピー、`smallint`として、`int`します。 ユーザー定義のデータ型は、基本データ型としてエクスポートされます。  
  
## <a name="the-bcp-prompt-for-file-storage-type"></a>ファイル ストレージ型の bcp プロンプト  
 対話型の **bcp** コマンドで、フォーマット ファイル スイッチ ( **-f** ) またはデータ形式スイッチ ( **-n** 、**-c**、**-w**、または **-N**) のどちらも付けずに **in**または **out**オプションを指定すると、次のように各データ フィールドのファイル ストレージ型を要求するプロンプトが表示されます。  
  
 `Enter the file storage type of field <field_name> [<default>]:`  
  
 この要求への応答は、次のように、実行するタスクによって異なります。  
  
-   できるだけコンパクトなストレージ型 (ネイティブ データ形式) で [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスからデータ ファイルにデータを一括エクスポートするには、 **bcp**によって提供される既定のファイル ストレージ型をそのまま使用します。 ネイティブのファイル ストレージ型の一覧については、このトピックの「ネイティブのファイル ストレージ型」を参照してください。  
  
-   インスタンスからデータの一括エクスポートする[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]文字形式でデータ ファイルに次のように指定します。`char`テーブル内のすべての列のファイル ストレージ型として。  
  
-   インスタンスにデータを一括インポートする[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]、データ ファイルから指定のファイル ストレージ型として`char`文字に格納された型は、書式設定し、ネイティブ データ型の形式で格納されているデータの適切なファイル ストレージの種類のいずれかを指定します。  
  
    |ファイル ストレージ型|コマンド プロンプトで入力する文字|  
    |-----------------------|-----------------------------|  
    |`char` <sup>1</sup>|`c`[`har`]|  
    |`varchar`|`c[har]`|  
    |`nchar`|`w`|  
    |`nvarchar`|`w`|  
    |`text` <sup>2</sup>|`T`[`ext`]|  
    |`ntext2`|`W`|  
    |`binary`|`x`|  
    |`varbinary`|`x`|  
    |`image` <sup>2</sup>|`I`[`mage`]|  
    |`datetime`|**d[ate]**|  
    |`smalldatetime`|`D`|  
    |`time`|`te`|  
    |`date`|`de`|  
    |`datetime2`|`d2`|  
    |`datetimeoffset`|`do`|  
    |`decimal`|`n`|  
    |`numeric`|`n`|  
    |`float`|**f[loat]**|  
    |`real`|`r`|  
    |`Int`|**i[nt]**|  
    |`bigint`|`B[igint]`|  
    |`smallint`|**s[mallint]**|  
    |`tinyint`|**t[inyint]**|  
    |`money`|**m[oney]**|  
    |`smallmoney`|`M`|  
    |`bit`|`b[it]`|  
    |`uniqueidentifier`|`u`|  
    |`sql_variant`|`V[ariant]`|  
    |`timestamp`|`x`|  
    |`UDT` (ユーザー定義データ型)|`U`|  
    |`XML`|`X`|  
  
     <sup>1</sup>フィールド長、プレフィックス長、およびターミネータの相互作用としてエクスポートされた非文字データのデータ ファイルに割り当てられる記憶域スペースの量を決定する、`char`ファイル ストレージ型。  
  
     <sup>2</sup> 、 `ntext`、 `text`、および`image`データ型はの将来のバージョンで削除される[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]します。 新しい開発作業ではこれらのデータ型の使用を避け、現在このデータ型を使用しているアプリケーションは変更を検討してください。 使用`nvarchar(max)`、 `varchar(max)`、および`varbinary(max)`代わりにします。  
  
## <a name="native-file-storage-types"></a>ネイティブのファイル ストレージ型  
 各ネイティブのファイル ストレージ型は、対応するホスト ファイル データ型として、フォーマット ファイルに記録されます。  
  
|ファイル ストレージ型|ホスト ファイル データ型|  
|-----------------------|-------------------------|  
|`char` <sup>1</sup>|SQLCHAR|  
|`varchar`|SQLCHAR|  
|`nchar`|SQLNCHAR|  
|`nvarchar`|SQLNCHAR|  
|`text` <sup>2</sup>|SQLCHAR|  
|`ntext` <sup>2</sup>|SQLNCHAR|  
|`binary`|SQLBINARY|  
|`varbinary`|SQLBINARY|  
|`image` <sup>2</sup>|SQLBINARY|  
|`datetime`|SQLDATETIME|  
|`smalldatetime`|SQLDATETIM4|  
|`decimal`|SQLDECIMAL|  
|`numeric`|SQLNUMERIC|  
|`float`|SQLFLT8|  
|`real`|SQLFLT4|  
|`int`|SQLINT|  
|`bigint`|SQLBIGINT|  
|`smallint`|SQLSMALLINT|  
|`tinyint`|SQLTINYINT|  
|`money`|SQLMONEY|  
|`smallmoney`|SQLMONEY4|  
|`bit`|SQLBIT|  
|`uniqueidentifier`|SQLUNIQUEID|  
|`sql_variant`|SQLVARIANT|  
|`timestamp`|SQLBINARY|  
|UDT (ユーザー定義データ型)|SQLUDT|  
  
 <sup>1</sup>形式の使用を文字に格納されているデータ ファイル`char`ファイル ストレージ型として。 したがって、文字データ ファイルの場合、フォーマット ファイルに表示されるデータ型は SQLCHAR のみです。  
  
 <sup>2</sup>へデータのインポートを一括できません`text`、 `ntext`、および`image`既定値を持つ列。  
  
## <a name="additional-considerations-for-file-storage-types"></a>ファイル ストレージ型のその他の考慮事項  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] のインスタンスからデータ ファイルにデータを一括エクスポートするときは、次のことを考慮してください。  
  
-   `char` 型は、常にファイル ストレージ型として指定できます。  
  
-   無効な暗黙的な変換を表すファイル ストレージ型を入力すると**bcp**は失敗します指定できますが、`int`の`smallint`を指定する場合は、データ`smallint`の`int`データ。オーバーフロー エラーの結果。  
  
-   非文字データ型がなど`float`、 `money`、 `datetime`、または`int`が格納されているそれぞれのデータベース型として、データが内のデータ ファイルに書き込まれます、[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ネイティブ形式。  
  
    > [!NOTE]  
    >  **bcp** コマンドですべてのフィールドを対話形式で指定すると、各フィールドへの応答を XML 形式以外のファイルに保存するように要求するプロンプトが表示されます。 XML 以外のフォーマット ファイルの詳細については、「[XML 以外のフォーマット ファイル &#40;SQL Server&#41;](xml-format-files-sql-server.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [bcp ユーティリティ](../../tools/bcp-utility.md)   
 [データ型 &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql)   
 [bcp を使用したフィールド長の指定 &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md)   
 [フィールド ターミネータと行ターミネータの指定 &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md)   
 [bcp を使用したデータ ファイルのプレフィックス長の指定 &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
  
