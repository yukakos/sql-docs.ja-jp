---
title: クライアント接続 (OLE DB) でサービス プリンシパル名 (Spn) |Microsoft Docs
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
ms.assetid: e212010e-a5b6-4ad1-a3c0-575327d3ffd3
caps.latest.revision: 17
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 74bd1f2482825fa2a8115df018d8a86b8f34845f
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37409671"
---
# <a name="service-principal-names-spns-in-client-connections-ole-db"></a>クライアント接続 (OLE DB) でのサービス プリンシパル名 (SPN)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  このトピックでは、クライアント アプリケーションでサービス プリンシパル名 (SPN) をサポートする OLE DB のプロパティとメンバー関数について説明します。 クライアント アプリケーションでの Spn の詳細については、次を参照してください。[サービス プリンシパル名&#40;SPN&#41;クライアント接続でサポート](../../../relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections.md)します。 サンプルについては、次を参照してください。[統合 Kerberos 認証&#40;OLE DB&#41;](../../../relational-databases/native-client-ole-db-how-to/integrated-kerberos-authentication-ole-db.md)します。  
  
## <a name="provider-initialization-string-keywords"></a>プロバイダー初期化文字列のキーワード  
 次に示すプロバイダー初期化文字列のキーワードは、OLE DB アプリケーションで SPN をサポートします。 次の表では、キーワードの列の値が idbinitialize::initialize のプロバイダー文字列に使用されます。 [説明] 列の値は、ADO または idatainitialize::getdatasource を使用して接続するときに、初期化文字列で使用されます。  
  
|Keyword|説明|値|  
|-------------|-----------------|-----------|  
|ServerSPN|サーバー SPN|サーバーの SPN。 既定値は空の文字列です。この場合、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client はプロバイダーが生成した SPN を既定値として使用します。|  
|FailoverPartnerSPN|フェールオーバー パートナー SPN|フェールオーバー パートナーの SPN。 既定値は空の文字列です。この場合、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client はプロバイダーが生成した SPN を既定値として使用します。|  
  
## <a name="data-source-initialization-properties"></a>データ ソース初期化プロパティ  
 次のプロパティ、 **DBPROPSET_SQLSERVERDBINIT**プロパティ セットを使用すると、アプリケーションの Spn を指定します。  
  
|名前|型|使用方法|  
|----------|----------|-----------|  
|SSPROP_INIT_SERVERSPN|VT_BSTR、読み取り/書き込み|サーバーの SPN を指定します。 既定値は空の文字列です。この場合、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client はプロバイダーが生成した SPN を既定値として使用します。|  
|SSPROP_INIT_FAILOVERPARTNERSPN|VT_BSTR、読み取り/書き込み|フェールオーバー パートナーの SPN を指定します。 既定値は空の文字列です。この場合、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client はプロバイダーが生成した SPN を既定値として使用します。|  
  
## <a name="data-source-properties"></a>データ ソースのプロパティ  
 次のプロパティ、 **DBPROPSET_SQLSERVERDATASOURCEINFO**プロパティ セットを使用すると、アプリケーションが認証メソッドを検出します。  
  
|名前|型|使用方法|  
|----------|----------|-----------|  
|SSPROP_INTEGRATEDAUTHENTICATIONMETHOD|VT_BSTR、読み取り専用|接続に使用された認証方法を返します。 アプリケーションに返される値は、Windows が [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client に返す値です。 返される値は次のとおりです。 <br />"NTLM"。これは NTLM 認証を使用して接続を開いたときに返されます。<br />"Kerberos"。これは Kerberos 認証を使用して接続を開いたときに返されます。<br /><br /> 接続が開いていて認証方法を特定できない場合は、VT_EMPTY が返されます。<br /><br /> このプロパティは、データ ソースが初期化されている場合にのみ読み取ることができます。 データ ソースが初期化されている前に、プロパティの読み取りを試みると、IDBProperties::GetProperies は DB_S_ERRORSOCCURRED または DB_E_ERRORSOCCURRED、必要に応じて、返し DBPROPSET_PROPERTIESINERROR に DBPROPSTATUS_NOTSUPPORTED が設定されます。このプロパティ。 この動作は、OLE DB のコア仕様に従っています。|  
|SSPROP_MUTUALLYAUTHENICATED|VT_BOOL、読み取り専用|接続されているサーバーが相互に認証されている場合は VARIANT_TRUE を返し、それ以外の場合は VARIANT_FALSE を返します。<br /><br /> このプロパティは、データ ソースが初期化されている場合にのみ読み取ることができます。 データ ソースが初期化されている前に、プロパティを読み取ろうとする場合は、IDBProperties::GetProperies は DB_S_ERRORSOCCURRED または DB_E_ERRORSOCCURRED、必要に応じて、返し DBPROPSET_ に DBPROPSTATUS_NOTSUPPORTED が設定されます。このプロパティの PROPERTIESINERROR します。 この動作は、OLE DB のコア仕様に従って、します。<br /><br /> Windows 認証を使用していない接続に対してこの属性が照会されると、VARIANT_FALSE が返されます。|  
  
## <a name="ole-db-api-support-for-spns"></a>OLE DB API による SPN のサポート  
 次の表では、クライアント接続で SPN をサポートする OLE DB メンバー関数について説明します。  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|IDataInitialize::GetDataSource|*pwszInitializationString* new キーワードを含めることができます**ServerSPN**と**FailoverPartnerSPN**します。|  
|IDataInitialize::GetInitializationString|SSPROP_INIT_SERVERSPN と ssprop_init_failoverpartnerspn の値には既定以外の値がある場合、対象になりますを通じて、初期化文字列*ppwszInitString*キーワード値として**ServerSPN**と**FailoverPartnerSPN**します。 それ以外の場合、これらのキーワードは初期化文字列に取り込まれません。|  
|IDBInitialize::Initialize|データ ソース初期化プロパティに DBPROP_INIT_PROMPT を設定して入力要求を有効にすると、OLE DB の [ログイン] ダイアログ ボックスが表示されます。 これにより、プリンシパル サーバーとそのフェールオーバー パートナーの両方に対して SPN を入力できます。<br /><br /> 場合は、DPPROP_INIT_PROVIDERSTRING にプロバイダーの文字列を設定、新しいキーワードを認識し、 **ServerSPN**と**FailoverPartnerSPN** SSPROP_INIT_SERVER_ を初期化するために、存在する場合、その値を使用して、SPN および SSPROP_INIT_FAILOVER_PARTNER_SPN します。<br /><br /> Idbinitialize::initialize が呼び出される前に、プロパティ SSPROP_INIT_SERVER_SPN および SSPROP_INIT_FAILOVER_PARTNER_SPN を設定するのには、idbproperties::setproperties を呼び出すことができます。 この方法は、プロバイダー文字列を使用する代わりに使用できます。<br /><br /> プロパティが複数の場所で設定されている場合は、プログラムによって設定された値が、プロバイダー文字列に設定された値より優先されます。 初期化文字列に設定された値は、ログイン ダイアログ ボックスで設定された値より優先されます。<br /><br /> プロバイダー文字列に同じキーワードが複数回使用されている場合は、最初に使用された値が優先されます。|  
|IDBProperties::GetProperties|Idbproperties::getproperties を呼び出すと、新しいデータ ソース プロパティ SSPROP_AUTHENTICATIONMETHOD と SSPROP_、新しいデータ ソース初期化プロパティ SSPROP_INIT_SERVERSPN と SSPROP_INIT_FAILOVERPARTNERSPN の値を取得することができます。MUTUALLYAUTHENTICATED します。|  
|IDBProperties::GetPropertyInfo|Idbproperties::getpropertyinfo には、新しいデータ ソース初期化プロパティ SSPROP_INIT_SERVERSPN と SSPROP_INIT_FAILOVERPARTNERSPN、または新しいデータ ソース プロパティ SSPROP_AUTHENTICATION_METHOD と SSPROP_MUTUALLYAUTHENTICATED が含まれます。|  
|IDBProperties::SetProperties|新しいデータ ソースの値に初期化プロパティ SSPROP_INITSERVERSPN と ssprop_init_failoverpartnerspn の値を設定するのには、idbproperties::setproperties を呼び出すことができます。<br /><br /> これらのプロパティはいつでも設定できますが、データ ソースが既に開いている場合は、次のエラーが返されます。DB_E_ERRORSOCCURRED、"複数ステップの OLE DB の操作でエラーが発生しました。 各 OLE DB の状態の値を確認してください。 作業は終了しませんでした。"|  
  
## <a name="see-also"></a>参照  
 [SQL Server Native Client &#40;OLE DB&#41;](../../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
