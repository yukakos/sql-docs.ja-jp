---
title: カスタム ビジネス オブジェクトを登録する |Microsoft ドキュメント
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
- custom business object in RDS [ADO]
- registering custom business objects in RDS [ADO]
- business objects in RDS [ADO]
ms.assetid: e9032ad8-d14c-42e3-ba13-cb5f00084a79
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2ac3e25b0770ae2e7617f8cb10ff35496d26a5c0
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "35274261"
---
# <a name="registering-a-custom-business-object"></a>カスタム ビジネス オブジェクトを登録します。
Web サーバーを経由 (.dll または .exe) は、カスタム ビジネス オブジェクトが正常に起動するにはこの手順で説明したようにビジネス オブジェクトの ProgID レジストリに入力する必要があります。 この RDS 機能は、認められている実行可能ファイルだけを実行して、Web サーバーのセキュリティを保護します。  
  
> [!IMPORTANT]
>  Windows 8 および Windows Server 2012 から始まり、RDS サーバー コンポーネントは含まれなく Windows オペレーティング システムで (Windows 8 を参照し、 [Windows Server 2012 の互換性クックブック](https://www.microsoft.com/en-us/download/details.aspx?id=27416)詳細については)。 RDS クライアント コンポーネントが Windows の将来のバージョンで削除されます。 新規の開発作業ではこの機能を使用しないようにし、現在この機能を使用しているアプリケーションは修正することを検討してください。 RDS を使用するアプリケーションに移行する必要があります[WCF Data Service](http://go.microsoft.com/fwlink/?LinkId=199565)です。  
  
> [!NOTE]
>  MDAC 2.0 およびそれ以降および Windows DAC、既定のビジネス オブジェクトの[RDSServer.DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)MDAC/Windows DAC のインストール時に既定で登録されていません。 ただし場合、 **RDSServer.DataFactory**登録されたインストールの前に、コンピューター上で実行するセーフであると、レジストリ エントリを保持する、新しいインストールします。  
  
### <a name="to-register-a-custom-business-object"></a>カスタム ビジネス オブジェクトを登録します。  
  
1.  をクリックして**開始** をクリックし、**実行**です。  
  
2.  型**RegEdit**  をクリック**OK**です。  
  
3.  レジストリ エディターに移動、 **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\W3SVC\Parameters\ADCLaunch**レジストリ キー。  
  
4.  選択、 **ADCLaunch**キー、し、**編集** メニューのをポイント**新規** をクリック**キー**です。  
  
5.  カスタム ビジネス オブジェクトの ProgID を入力し、をクリックして**Enter**です。 ままにして、**値**空白エントリです。


