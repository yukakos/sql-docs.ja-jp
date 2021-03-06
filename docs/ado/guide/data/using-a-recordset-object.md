---
title: レコード セット オブジェクトを使用して |Microsoft ドキュメント
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [ADO]
ms.assetid: 01c630d8-eb35-4bd0-a99f-7c0f85316cc1
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 05a2c989d1f14849ef39b4ec93f4677ebc52510e
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "35273181"
---
# <a name="using-a-recordset-object"></a>レコード セット オブジェクトの使用
また、使用することができます**Recordset.Open**を暗黙的に接続を確立し、単一の操作では、その接続経由でコマンドを実行します。 たとえば、Visual Basic: で  
  
```  
Dim oRs As ADODB.Recordset  
Dim sConn As String  
Dim sSQL as String  
  
sConn = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _             "Initial Catalog='Northwind';Integrated Security='SSPI';"  
  
sSQL = "SELECT ProductID, ProductName, CategoryID, UnitPrice " & _  
             "FROM Products"  
  
' Create and Open the Recordset object.  
Set oRs = New ADODB.Recordset  
oRs.CursorLocation = adUseClient  
oRs.Open sSQL, sConn, adOpenStatic, _  
               adLockBatchOptimistic, adCmdText  
  
MsgBox oRs.RecordCount  
  
oRs.MarshalOptions = adMarshalModifiedOnly  
' Disconnect the Recordset.  
Set oRs.ActiveConnection = Nothing  
oRs.Close          
Set oRs = Nothing  
```  
  
 注意して**oRs.Open**は接続文字列を受け取ります (*sConn*) の代わりに、**接続**オブジェクト (*oConn*)、そのの値として**ActiveConnection**パラメーター。 設定して、クライアント側カーソルの種類にも適用は、 **CursorLocation**プロパティを**Recordset**オブジェクト。 もう一度とこれに対し、 **HelloData**例です。
