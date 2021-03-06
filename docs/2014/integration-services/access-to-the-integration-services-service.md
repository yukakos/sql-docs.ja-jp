---
title: サービスのサービスの統合へのアクセス |Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- viewing packages while running
- displaying packacges while running
- security [Integration Services], running packages
- packages [Integration Services], security
- current packages running
- Integration Services packages, security
- SQL Server Integration Services packages, security
ms.assetid: 1088aafc-14c5-4e7d-9930-606a24c3049b
caps.latest.revision: 14
author: douglaslms
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2eac9b692732d11903e358ef5e53e59a4a81bf6a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37180409"
---
# <a name="access-to-the-integration-services-service"></a>Integration Services サービスへのアクセス
  パッケージの保護レベルによって、パッケージを編集および実行できるユーザーを制限できます。 サーバーで現在実行中のパッケージの一覧を表示できるユーザー、および [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]で現在実行中のパッケージを停止できるユーザーを制限するには、追加の保護が必要です。  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] では、実行中のパッケージを一覧表示する際に [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] サービスが使用されます。 Windows の Administrators グループのメンバーは、実行中のすべてのパッケージを表示および停止できます。 Administrators グループのメンバーではないユーザーは、本人が起動したパッケージのみを表示および停止できます。  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] サービス (特に、リモート フォルダーの列挙を行う可能性のある [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] サービス) を実行するコンピューターへのアクセスを制限することは重要です。 認証を受けたユーザーであれば、パッケージの列挙を要求できます。 でも、サービスが検出されない場合、サービス、サービスにフォルダーを列挙します。 これらのフォルダー名が、悪意あるユーザーに悪用される場合があります。 管理者がリモート コンピューターのフォルダーを列挙できるようにサービスを設定した場合、ユーザーも通常は参照できないフォルダー名を参照することができます。  
  
  
