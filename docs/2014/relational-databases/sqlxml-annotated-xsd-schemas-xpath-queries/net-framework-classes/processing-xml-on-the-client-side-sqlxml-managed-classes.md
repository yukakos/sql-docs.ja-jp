---
title: クライアント側の XML の処理 (SQLXML マネージ クラス) |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- processing XML on client side [SQLXML]
- client-side XML formatting
- Managed Classes [SQLXML], client-side XML formatting
- SQLXML Managed Classes, client-side XML formatting
- ClientSideXml property
ms.assetid: 5e7ecf18-66fc-49ff-bc50-83635cd7ac0b
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 242e06d72b7a1773235e51c7211b2526af6d4608
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37201102"
---
# <a name="processing-xml-on-the-client-side-sqlxml-managed-classes"></a>クライアント側での XML の処理 (SQLXML マネージド クラス)
  この例では、ClientSideXml プロパティの使用を示します。 サーバーで、アプリケーションによってストアド プロシージャが実行されると、 クライアント側でその結果 (2 列の行セット) が処理され、XML ドキュメントが生成されます。  
  
 次の GetContacts、ストアド プロシージャ**FirstName**と**LastName** AdventureWorks データベースの Person.Contact テーブル内の従業員のです。  
  
```  
USE AdventureWorks  
CREATE PROCEDURE GetContacts @LastName varchar(20)  
AS  
SELECT FirstName, LastName  
FROM   Person.Contact  
WHERE LastName = @LastName  
Go  
```  
  
 この c# アプリケーションでは、ストアド プロシージャを実行し、CommandText 値を指定するときに、FOR XML AUTO オプションを指定します。 SqlXmlCommand オブジェクトの ClientSideXml プロパティを設定するアプリケーションでは、true に設定します。 これにより、前から存在するストアド プロシージャを実行して行セットを返すことができ、クライアント側で XML 変換を適用することができます。  
  
> [!NOTE]  
>  コードでは、接続文字列に Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] インスタンス名を含める必要があります。  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
    static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         //Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.ClientSideXml = true;  
         cmd.CommandText = "EXEC GetContacts ? FOR XML NESTED";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         using (Stream strm = cmd.ExecuteStream())   
         {  
            using (StreamReader sr = new StreamReader(strm))  
                  {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
  
public static int Main(String[] args)  
{  
    testParams();  
    return 0;  
}  
}  
```  
  
 この例をテストするには、コンピューターに [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework がインストールされている必要があります。  
  
### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  ストアド プロシージャを作成します。  
  
2.  この例で提供される C# コード (DocSample.cs) をフォルダーに保存します。 コードを編集し、適切なログインおよびパスワード情報を指定します。  
  
3.  コードをコンパイルします。 コマンド プロンプトでコードをコンパイルするには、次を使用します。  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     これにより、実行可能ファイル (DocSample.exe) が作成されます。  
  
4.  コマンド プロンプトで、DocSample.exe を実行します。  
  
  
