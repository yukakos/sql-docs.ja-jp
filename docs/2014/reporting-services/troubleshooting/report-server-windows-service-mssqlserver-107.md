---
title: レポート サーバー Windows サービス (MSSQLServer) 107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
caps.latest.revision: 19
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: f5f8f4ab62d893334cfab9020a7cf301e7b7761f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37275788"
---
# <a name="report-server-windows-service-mssqlserver-107"></a>レポート サーバー Windows サービス (MSSQLServer) 107
    
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|イベント ID|107|  
|イベント ソース|レポート サーバー Windows サービス|  
|コンポーネント|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|メッセージ テキスト|レポート サーバー Windows サービス (MSSQLSERVER) はレポート サーバー データベースに接続できません。|  
  
## <a name="explanation"></a>説明  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] レポート サーバー サービスは、レポート サーバー データベースに接続できません。 このエラーは、サービスの再起動中、レポート サーバー データベースへの接続を確立できない場合に発生します。 このエラーは、次のような状況で発生します。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] サービスが実行されていない場合。  
  
-   リモート接続または TCP/IP プロトコルが無効になっているため、 [!INCLUDE[ssDE](../../includes/ssde-md.md)] サービスへの接続に失敗する場合。  
  
-   レポート サーバー データベースが正しく構成されていない場合。  
  
-   サービス アカウントが正しく構成されていないか、レポート サーバー データベースに対する権限がアカウントにない場合。 この状況は、アカウントやレポート サーバー データベースの設定に [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 構成ツールを使用しない場合に発生することがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)] サービスが実行されていない場合はこのサービスを開始し、TCP/IP プロトコルでのリモート接続が有効になっていることを確認します。  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 構成ツールを使用して、レポート サーバー データベースとサービス アカウントを構成します。  
  
## <a name="internal-only"></a>内部使用のみ  
  
## <a name="see-also"></a>参照  
 [レポート サーバー サービス アカウントの構成&#40;SSRS 構成マネージャー&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)   
 [Reporting Services 構成マネージャー&#40;ネイティブ モード&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)   
 [レポート サーバー サービスの開始と停止](../report-server/start-and-stop-the-report-server-service.md)  
  
  
