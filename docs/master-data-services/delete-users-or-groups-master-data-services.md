---
title: ユーザーまたはグループを削除する (マスター データ サービス) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- deleting groups [Master Data Services]
- groups [Master Data Services], deleting
- users [Master Data Services], deleting
- deleting users [Master Data Services]
ms.assetid: 0bbf9d2c-b826-48bb-8aa9-9905db6e717f
caps.latest.revision: 7
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: e89369c4ece00ec5114801a560fc6cf81ef02fcf
ms.sourcegitcommit: de5e726db2f287bb32b7910831a0c4649ccf3c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2018
ms.locfileid: "35333726"
---
# <a name="delete-users-or-groups-master-data-services"></a>ユーザーまたはグループを削除する (マスター データ サービス)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]にアクセスする必要のなくなったユーザーまたはグループを削除します。  
  
 ユーザーおよびグループを削除する場合、次の点に注意してください。  
  
-   ユーザーが [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]へのアクセスを持つグループのメンバーである場合、そのユーザーは、Active Directory またはローカル グループから削除されるまで [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] にアクセスできます。  
  
-   グループを削除した場合、そのメンバーを削除するまで、 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] にアクセスしたことのあるグループのすべてのメンバーは **[ユーザー]** ボックスの一覧に表示されます。  
  
-   セキュリティの変更は、20 分間は MDS [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] に反映されません。  
  
## <a name="prerequisites"></a>Prerequisites  
 この手順を実行するには  
  
-   **[ユーザー/グループの権限]** 機能領域にアクセスするための権限が必要です。  
  
### <a name="to-delete-users-or-groups"></a>ユーザーまたはグループを削除するには  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]で **[ユーザー/グループの権限]** をクリックします。  
  
2.  ユーザーを削除するには、 **[ユーザー]** ページを表示します。 グループを削除するには、メニュー バーの **[グループの管理]** をクリックします。  
  
3.  グリッドで、削除するユーザーまたはグループの行を選択します。  
  
4.  **[選択したユーザーの削除]** または **[選択したグループの削除]** をクリックします。  
  
5.  確認のダイアログ ボックスで **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [セキュリティ (マスター データ サービス)](../master-data-services/security-master-data-services.md)  
  
  
