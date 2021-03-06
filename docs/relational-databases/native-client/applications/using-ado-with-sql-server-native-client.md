---
title: SQL Server Native Client と ADO を使用して |Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, ADO
- data access [SQL Server Native Client], ADO
- ADO [SQL Server Native Client]
- SQLNCLI, ADO
ms.assetid: 118a7cac-4c0d-44fd-b63e-3d542932d239
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 7a09bd10314d8533152c7317682501df8b28eb9a
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37428291"
---
# <a name="using-ado-with-sql-server-native-client"></a>SQL Server Native Client と ADO の併用
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  導入された新機能を活用するために[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]など、複数のアクティブな結果セット (MARS)、クエリ通知、ユーザー定義型 (Udt)、または新しい**xml**データ型、ActiveX を使用する既存のアプリケーションデータ オブジェクト (ADO) を使用する必要があります、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーは、データ アクセス プロバイダーとして。  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] の新機能を一切使用する必要がない場合は、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーを使用する必要はありません。つまり、現在のデータ アクセス プロバイダー (通常は SQLOLEDB) を継続して使用できます。 既存のアプリケーションを強化して、[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] の新機能を使用する必要がある場合は、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーを使用してください。  
  
> [!NOTE]  
>  新しいアプリケーションを開発している場合は、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] の最新バージョンのすべての新機能にアクセスできるように、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ではなく、ADO.NET および .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] の使用を検討することをお勧めします。 .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] の詳細については、ADO.NET に関する .NET Framework SDK のドキュメントを参照してください。  
  
 ADO から [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] の最新バージョンの新機能を使用できるように、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーを機能強化し、OLE DB の中核となる機能を拡張しました。 これらの拡張によりを使用する ADO アプリケーションが新しい[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]機能で導入された型の 2 つのデータを使用して[!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml**と**udt**します。 これらの機能強化もデータ型に対する機能、 **varchar**、 **nvarchar**、および**varbinary**データ型。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client では、新しいデータ型が ADO を使用した互換性のある方法で公開されているように使用する ADO アプリケーションで設定 DBPROPSET_SQLSERVERDBINIT プロパティに、SSPROP_INIT_DATATYPECOMPATIBILITY 初期化プロパティを追加します。 さらに、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーは、という名前の新しい接続文字列キーワードも定義されています。 **DataTypeCompatibility**接続文字列に設定されています。  
  
> [!NOTE]  
>  既存の ADO アプリケーションは、SQLOLEDB プロバイダーを使用して、XML、UDT、および大きな値のテキストやバイナリのフィールド値にアクセスして更新できます。 新しい大きな**varchar (max)**、 **nvarchar (max)**、および**varbinary (max)** データ型が ADO 型として返される**adLongVarChar**、**adLongVarWChar**と**adLongVarBinary**それぞれします。 として XML 列が返されます**adLongVarChar**、UDT 列として返されますと**adVarBinary**します。 ただし、使用する場合、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] SQLOLEDB ではなく Native Client OLE DB プロバイダー (SQLNCLI11) を設定することを確認する必要があります、 **DataTypeCompatibility**キーワードを「80」、新しいデータ型が ADO データに正しく対応するように型。  
  
## <a name="enabling-sql-server-native-client-from-ado"></a>ADO からの SQL Server Native Client の有効化  
 使用を有効にする[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client は、ADO アプリケーションは、接続文字列で、次のキーワードを実装する必要があります。  
  
-   `Provider=SQLNCLI11`  
  
-   `DataTypeCompatibility=80`  
  
 接続文字列でサポートされているキーワードの ADO の詳細については[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client を参照してください[使用した Connection String Keywords with SQL Server Native Client を使用して](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md)します。  
  
 使用する完全に有効になっている ADO 接続文字列を作成する例を次に[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]MARS 機能の有効化などのネイティブ クライアント。  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
```  
  
## <a name="examples"></a>使用例  
 次のセクションでは、ADO とを使用する方法の例を提供する、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダー。  
  
### <a name="retrieving-xml-column-data"></a>XML 列データの取得  
 取得および XML 列からデータを表示、この例では、レコード セットが使用される、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **AdventureWorks**サンプル データベース。  
  
```  
Dim con As New ADODB.Connection  
Dim rst As New ADODB.Recordset  
Dim sXMLResult As String  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _   
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the xml data as a recordset.  
Set rst.ActiveConnection = con  
rst.Source = "SELECT AdditionalContactInfo FROM Person.Contact " _  
   & "WHERE AdditionalContactInfo IS NOT NULL"  
rst.Open  
  
' Display the data in the recordset.  
While (Not rst.EOF)  
   sXMLResult = rst.Fields("AdditionalContactInfo").Value  
   Debug.Print (sXMLResult)  
   rst.MoveNext  
End While  
  
con.Close  
Set con = Nothing  
```  
  
> [!NOTE]  
>  レコードセットのフィルター選択は、XML 列でサポートされません。 これを使用すると、エラーが返されます。  
  
### <a name="retrieving-udt-column-data"></a>UDT 列データの取得  
 この例で、**コマンド**オブジェクトは、UDT を返す SQL クエリを実行するために使用、UDT データを更新すると、および新しいデータをデータベースに挿入されます。 この例では、**ポイント**UDT が既にデータベースに登録されています。  
  
```  
Dim con As New ADODB.Connection  
Dim cmd As New ADODB.Command  
Dim rst As New ADODB.Recordset  
Dim strOldUDT As String  
Dim strNewUDT As String  
Dim aryTempUDT() As String  
Dim strTempID As String  
Dim i As Integer  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the UDT value.  
Set cmd.ActiveConnection = con  
cmd.CommandText = "SELECT ID, Pnt FROM dbo.Points.ToString()"  
Set rst = cmd.Execute  
strTempID = rst.Fields(0).Value  
strOldUDT = rst.Fields(1).Value  
  
' Do something with the UDT by adding i to each point.  
arytempUDT = Split(strOldUDT, ",")  
i = 3  
strNewUDT = LTrim(Str(Int(aryTempUDT(0)) + i)) + "," + _  
   LTrim(Str(Int(aryTempUDT(1)) + i))  
  
' Insert the new value back into the database.  
cmd.CommandText = "UPDATE dbo.Points SET Pnt = '" + strNewUDT + _  
   "' WHERE ID = '" + strTempID + "'"  
cmd.Execute  
  
con.Close  
Set con = Nothing  
```  
  
### <a name="enabling-and-using-mars"></a>MARS の有効化と使用  
 この例では、MARS を有効にする接続文字列を構築、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダー、および 2 つのレコード セット オブジェクトからは、同じ接続を使用して実行を作成します。  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
  
Dim recordset1 As New ADODB.Recordset  
Dim recordset2 As New ADODB.Recordset  
  
Dim recordsaffected As Integer  
Set recordset1 =  con.Execute("SELECT * FROM Table1", recordsaffected, adCmdText)  
Set recordset2 =  con.Execute("SELECT * FROM Table2", recordsaffected, adCmdText)  
  
con.Close  
Set con = Nothing  
```  
  
 以前のバージョンの OLE DB プロバイダーでは、アクティブな結果セットを 1 つの接続ごとに 1 つしか開くことができなかったので、このコードにより 2 回目の実行時に暗黙の接続が作成されました。 暗黙の接続が OLE DB 接続プールにプールされなかったので、これが原因でオーバーヘッドが増加することになります。 MARS 機能によって公開されている、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーでは、1 つの接続で複数のアクティブな結果が発生しました。  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client を使用したアプリケーションのビルド](../../../relational-databases/native-client/applications/building-applications-with-sql-server-native-client.md)  
  
  
