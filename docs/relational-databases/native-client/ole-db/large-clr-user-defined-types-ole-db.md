---
title: 大きな CLR ユーザー定義型 (OLE DB) |Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: native-client-ole-db
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types [OLE DB]
ms.assetid: 4bf12058-0534-42ca-a5ba-b1c23b24d90f
caps.latest.revision: 24
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 36a553d8c9117289d1c20174fe3c7f1a4a70511a
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37408361"
---
# <a name="large-clr-user-defined-types-ole-db"></a>大きな CLR ユーザー定義型 (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  このトピックでは、大きな共通言語ランタイム (CLR) ユーザー定義型 (UDT) をサポートするための、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client の OLE DB に対する変更について説明します。  
  
 における大きな CLR Udt のサポートの詳細については[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client を参照してください[Large CLR User-Defined 型](../../../relational-databases/native-client/features/large-clr-user-defined-types.md)します。 サンプルについては、次を参照してください。[大きな CLR Udt を使用して&#40;OLE DB&#41;](../../../relational-databases/native-client-ole-db-how-to/use-large-clr-udts-ole-db.md)します。  
  
## <a name="data-format"></a>データ形式  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client では、大きなオブジェクト (LOB) の型についてサイズが無制限である値の長さを表す場合に、~0 が使用されます。 8,000 バイトを超える CLR UDT のサイズも ~0 で表されます。  
  
 次の表に、パラメーターおよび行セットでのデータ型のマッピングを示します。  
  
|SQL Server データ型|OLE DB データ型|メモリ レイアウト|値|  
|--------------------------|----------------------|-------------------|-----------|  
|CLR UDT|DBTYPE_UDT|Byte[] (バイト配列\)|132 (oledb.h)|  
  
 UDT 値はバイト配列として表されます。 16 進文字列との間の変換がサポートされています。 リテラル値は、"0x" で始まる 16 進文字列として表されます。 16 進文字列は、ベース 16 のバイナリ データをテキストで表現したものです。 例は、サーバーの種類からの変換**varbinary(10)** DBTYPE_STR に 1 対の文字が 1 バイトを表す 20 文字の 16 進表現になります。  
  
## <a name="parameter-properties"></a>パラメーターのプロパティ  
 DBPROPSET_SQLSERVERPARAMETER プロパティ セットは、OLE DB を介して UDT をサポートします。 詳細については、次を参照してください。[ユーザー種類](~/relational-databases/native-client/features/using-user-defined-types.md)します。  
  
## <a name="column-properties"></a>列のプロパティ  
 DBPROPSET_SQLSERVERCOLUMN プロパティ セットは、OLE DB を介してテーブルの作成をサポートします。 詳細については、次を参照してください。[ユーザー種類](~/relational-databases/native-client/features/using-user-defined-types.md)します。  
  
## <a name="data-type-mapping-in-itabledefinitioncreatetable"></a>ITableDefinition::CreateTable でのデータ型マッピング  
 次の情報が使用される**DBCOLUMNDESC** itabledefinition::createtable で UDT 列が必要な場合に使用される構造。  
  
|OLE DB データ型 (*wType*)|*pwszTypeName*|SQL Server データ型|*rgPropertySets*|  
|----------------------------------|--------------------|--------------------------|----------------------|  
|DBTYPE_UDT|無視|UDT (UDT)|DBPROPSET_SQLSERVERCOLUMN プロパティ セットを含める必要があります。|  
  
## <a name="icommandwithparametersgetparameterinfo"></a>ICommandWithParameters::GetParameterInfo  
 介して DBPARAMINFO 構造体に情報が返されます**prgParamInfo**のとおりです。  
  
|パラメーターの型|*wType*|*ulParamSize*|*bPrecision*|*bScale*|*dwFlags* DBPARAMFLAGS_ISLONG|  
|--------------------|-------------|-------------------|------------------|--------------|------------------------------------|  
|DBTYPE_UDT<br /><br /> (8,000 バイト以下の長さ)|"DBTYPE_UDT"|*n*|未定義|未定義|オフ|  
|DBTYPE_UDT<br /><br /> (8,000 バイトを超える長さ)|"DBTYPE_UDT"|~0|未定義|未定義|セット (set)|  
  
## <a name="icommandwithparameterssetparameterinfo"></a>ICommandWithParameters::SetParameterInfo  
 DBPARAMBINDINFO 構造体で提供される情報は、次の表に準拠する必要があります。  
  
|パラメーターの型|*pwszDataSourceType*|*ulParamSize*|*bPrecision*|*bScale*|*dwFlags* DBPARAMFLAGS_ISLONG|  
|--------------------|--------------------------|-------------------|------------------|--------------|------------------------------------|  
|DBTYPE_UDT<br /><br /> (8,000 バイト以下の長さ)|DBTYPE_UDT|*n*|無視されます。|無視されます。|パラメーターが DBTYPE_IUNKNOWN を使用して渡される場合に設定する必要があります。|  
|DBTYPE_UDT<br /><br /> (8,000 バイトを超える長さ)|DBTYPE_UDT|~0|無視されます。|無視されます。|無視されます。|  
  
## <a name="isscommandwithparameters"></a>ISSCommandWithParameters  
 アプリケーションを使用して、 **ISSCommandWithParameters**を取得およびパラメーターのプロパティ セクションで定義されているパラメーターのプロパティを設定します。  
  
## <a name="icolumnsrowsetgetcolumnsrowset"></a>IColumnsRowset::GetColumnsRowset  
 返される列は次のとおりです。  
  
|列の型|DBCOLUMN_TYPE|DBCOLUMN_COLUMNSIZE|DBCOLUMN_PRECISION|DBCOLUMN_SCALE|DBCOLUMN_FLAGS_ISLONG|DBCOLUMNS_ISSEARCHABLE|DBCOLUMN_OCTETLENGTH|  
|-----------------|--------------------|--------------------------|-------------------------|---------------------|-----------------------------|-----------------------------|---------------------------|  
|DBTYPE_UDT<br /><br /> (8,000 バイト以下の長さ)|DBTYPE_UDT|*n*|NULL|NULL|Clear|DB_ALL_EXCEPT_LIKE|n|  
|DBTYPE_UDT<br /><br /> (8,000 バイトを超える長さ)|DBTYPE_UDT|~0|NULL|NULL|Set|DB_ALL_EXCEPT_LIKE|0|  
  
 UDT には次の列も定義されています。  
  
|列識別子|型|説明|  
|-----------------------|----------|-----------------|  
|DBCOLUMN_UDT_CATALOGNAME|DBTYPE_WSTR|UDT 列の場合は、UDT が定義されているカタログの名前。|  
|DBCOLUMN_UDT_SCHEMANAME|DBTYPE_WSTR|UDT 列の場合は、UDT が定義されているスキーマの名前。|  
|DBCOLUMN_UDT_NAME|DBTYPE_WSTR|UDT 列の場合は、UDT の 1 部構成の名前。|  
|DBCOLUMN_ASSEMBLY_TYPENAME|DBTYPE_WSTR|UDT 列の場合、UDT の完全な型名。 アセンブリ型の完全修飾名を使用することで、Type.GetType メソッドを使用してその型のオブジェクトのインスタンスを作成できます。|  
  
## <a name="icolumnsinfogetcolumninfo"></a>IColumnsInfo::GetColumnInfo  
 DBCOLUMNINFO 構造体で返される情報は次のとおりです。  
  
|パラメーターの型|*wType*|*ulColumnSize*|*bPrecision*|*bScale*|*dwFlags*<br /><br /> DBCOLUMNFLAGS_ISLONG|  
|--------------------|-------------|--------------------|------------------|--------------|-----------------------------------------|  
|DBTYPE_UDT<br /><br /> (8,000 バイト以下の長さ)|DBTYPE_UDT|*n*|~0|~0|Clear|  
|DBTYPE_UDT<br /><br /> (8,000 バイトを超える長さ)|DBTYPE_UDT|~0|~0|~0|Set|  
  
## <a name="columns-rowset-schema-rowsets"></a>COLUMNS 行セット (スキーマ行セット)  
 UDT 型に対して返される列値を次に示します。  
  
|列の型|DATA_TYPE|COLUMN_FLAGS、DBCOLUMFLAGS_ISLONG|CHARACTER_OCTET_LENGTH|  
|-----------------|----------------|-----------------------------------------|------------------------------|  
|DBTYPE_UDT<br /><br /> (8,000 バイト以下の長さ)|DBTYPE_UDT|Clear|*n*|  
|DBTYPE_UDT<br /><br /> (8,000 バイトを超える長さ)|DBTYPE_UDT|Set|0|  
  
 UDT には、次の追加の列が定義されています。  
  
|列の識別子|型|説明|  
|-----------------------|----------|-----------------|  
|SS_UDT_CATALOGNAME|DBTYPE_WSTR|UDT 列の場合は、UDT が定義されているカタログの名前。|  
|SS_UDT_SCHEMANAME|DBTYPE_WSTR|UDT 列の場合は、UDT が定義されているスキーマの名前。|  
|SS_UDT_NAME|DBTYPE_WSTR|UDT 列の場合は、UDT の 1 部構成の名前。|  
|SS_ASSEMBLY_TYPENAME|DBTYPE_WSTR|UDT 列の場合は、UDT の完全な型名。 アセンブリ型の完全修飾名を使用することで、Type.GetType メソッドを使用してその型のオブジェクトのインスタンスを作成できます。|  
  
 PROCEDURE_PARAMETERS 行セットに関しては、DATA_TYPE に COLUMNS スキーマ行セットと同じ値が格納され、TYPE_NAME に UDT が格納されます。 同じ追加の列も定義されています。  
  
 PROVIDER_TYPES スキーマ行セットには、ユーザー定義型が表示されません。  
  
## <a name="bindings-and-conversions"></a>バインドと変換  
  
|Binding データ型|UDT からサーバー|UDT 以外からサーバー|サーバーから UDT|サーバーから UDT 以外|  
|----------------------|-------------------|------------------------|---------------------|--------------------------|  
|DBTYPE_UDT|サポートされている (5)|エラー (1)|サポートされている (5)|エラー (4)|  
|DBTYPE_BYTES|サポートされている (5)|なし|サポートされている (5)|なし|  
|DBTYPE_WSTR|サポート (2)、(5)|なし|サポート (3)、(5)、(6)|なし|  
|DBTYPE_BSTR|サポート (2)、(5)|なし|サポートされている (3), (5)|なし|  
|DBTYPE_STR|サポート (2)、(5)|なし|サポートされている (3), (5)|なし|  
|DBTYPE_IUNKNOWN|サポートされている (6)|なし|サポートされている (6)|なし|  
|DBTYPE_VARIANT (VT_UI1 &AMP;#124; VT_ARRAY)|サポート (5)|なし|サポートされている (3), (5)|なし|  
|DBTYPE_VARIANT (VT_BSTR)|サポート (2)、(5)|なし|なし|なし|  
  
### <a name="key-to-symbols"></a>記号の説明  
  
|シンボル|説明|  
|------------|-------------|  
|1|Dbtype_udt 型を指定した以外のサーバー型の場合**icommandwithparameters::setparameterinfo**アクセサーの型が dbtype_udt の場合と、ステートメントが実行されるときにエラーが発生します。  発生するエラーは DB_E_ERRORSOCCURRED、パラメーターの状態は DBSTATUS_E_BADACCESSOR です。<br /><br /> UDT ではないサーバー パラメーターに UDT 型のパラメーターを指定すると、エラーになります。|  
|2|データが 16 進数文字列からバイナリ データに変換されます。|  
|3|データがバイナリ データから 16 進文字列に変換されます。|  
|4|検証を使用する場合に発生することができます**CreateAccessor**または**GetNextRows**します。 このエラーは DB_E_ERRORSOCCURRED です。 バインドの状態は、DBBINDSTATUS_UNSUPPORTEDCONVERSION に設定されます。|  
|5|BY_REF を使用できます。|  
|6|UDT パラメーターを、DBBINDING で DBTYPE_IUNKNOWN としてバインドできます。 DBTYPE_IUNKNOWN にバインドするには、アプリケーションは、ISequentialStream インターフェイスを使用してストリームとしてデータを処理する必要があることを示します。 コンシューマーを示す*wType*ストアド プロシージャのパラメーターは、UDT を DBTYPE_IUNKNOWN 型としてバインドし、対応する列または出力で、SQL Server Native Client には ISequentialStream が返されます。 クエリは、入力パラメーターでは、SQL Server Native Client、ISequentialStream インターフェイス。<br /><br /> UDT が大きい場合は、DBTYPE_IUNKNOWN バインドを使用しながら UDT データの長さをバインドしないようにすることができます。 ただし、小さな UDT の場合は長さをバインドする必要があります。 次の条件が 1 つ以上当てはまる場合は、DBTYPE_UDT パラメーターを大きな UDT として指定できます。<br />*ulParamParamSize*は ~ 0。<br />DBPARAMBINDINFO 構造体で DBPARAMFLAGS_ISLONG が設定されている。<br /><br /> 行データの場合は、DBTYPE_IUNKNOWN バインドを大きな UDT だけに使用できます。 コマンド オブジェクトの IColumnsInfo インターフェイスまたは列が行セットに対して icolumnsinfo::getcolumninfo メソッドを使用して、大きな UDT 型がかどうかを確認できます。 次の条件が 1 つ以上当てはまる場合、DBTYPE_UDT 列は大きな UDT 列です。<br />DBCOLUMNFLAGS_ISLONG フラグが設定*dwFlags* DBCOLUMNINFO 構造体のメンバー。 <br />*ulColumnSize* DBCOLUMNINFO のメンバーが ~ 0。|  
  
 DBTYPE_NULL と DBTYPE_EMPTY は入力パラメーターにバインドできますが、出力パラメーターや結果にはバインドできません。 入力パラメーターにバインドした場合は、状態を DBSTATUS_S_ISNULL (DBTYPE_NULL の場合) または DBSTATUS_S_DEFAULT (DBTYPE_EMPTY の場合) に設定する必要があります。 DBTYPE_BYREF を、DBTYPE_NULL または DBTYPE_EMPTY と共に使用することはできません。  
  
 DBTYPE_UDT は、DBTYPE_EMPTY および DBTYPE_NULL に変換することもできます。 ただし、DBTYPE_NULL および DBTYPE_EMPTY を DBTYPE_UDT に変換することはできません。 この動作は、DBTYPE_BYTES 型と一貫性があります。 **ISSCommandWithParameters**プロセス Udt をパラメーターとして使用されます。  
  
 OLE DB core services で提供されるデータ変換 (**IDataConvert**) dbtype_udt 型には適用されません。  
  
 また、その他のバインドもサポートされません。  
  
## <a name="comparability-for-irowsetfind"></a>IRowsetFind での比較  
 UDT 型については、次の比較のみがサポートされています。  
  
-   EQ  
  
-   NE  
  
-   IGNORE  
  
 その他の比較を試みると、DB_E_BADCOMPAREOP が返されます。  
  
## <a name="bcp-support-for-udts"></a>BCP による UDT のサポート  
 UDT 値は、インポートおよび文字またはバイナリ値としてのみエクスポートすることができます。  
  
## <a name="down-level-client-behavior-for-udts"></a>Udt に対する下位クライアントの動作  
 UDT に対しては、下位クライアントで次のように型マッピングが行われます。  
  
|クライアントのバージョン|DBTYPE_UDT<br /><br /> (8,000 バイト以下の長さ)|DBTYPE_UDT<br /><br /> (8,000 バイトを超える長さ)|  
|--------------------|------------------------------------------------------------------|---------------------------------------------------------|  
|SQL Server 2005|UDT (UDT)|varbinary(max)|  
|SQL Server 2008 以降|UDT (UDT)|UDT (UDT)|  
  
 ときに**DataTypeCompatibility** (SSPROP_INIT_DATATYPECOMPATIBILITY) が「80」に設定されている、大きな UDT 型が下位レベル クライアントに表示されるのと同じ方法でクライアントに表示されます。  
  
## <a name="see-also"></a>参照  
 [大きな CLR ユーザー定義型](~/relational-databases/native-client/features/large-clr-user-defined-types.md)  
  
  

