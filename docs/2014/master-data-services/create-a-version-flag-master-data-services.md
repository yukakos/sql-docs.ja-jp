---
title: バージョン フラグを作成する (マスター データ サービス) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- creating version flags [Master Data Services]
- version flags [Master Data Services], creating
- versions [Master Data Services], creating flags
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 8e749d7e0be27ec7ea749073f89f192972a354f2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37287548"
---
# <a name="create-a-version-flag-master-data-services"></a>バージョン フラグを作成する (マスター データ サービス)
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]で、バージョンに割り当てるバージョン フラグを作成します。 フラグによって、ユーザーまたはサブスクライブ システムが使用する必要があるバージョンを示すことができます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには  
  
-   **[バージョン管理]** 機能領域にアクセスする権限が必要です。  
  
-   モデル管理者である必要があります。 詳細については、「[Administrators &#40;Master Data Services&#41; (管理者 &#40;マスター データ サービス&#41;)](administrators-master-data-services.md)」を参照してください。  
  
### <a name="to-create-a-version-flag"></a>バージョン フラグを作成するには  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]で **[バージョン管理]** をクリックします。  
  
2.  **[バージョンの管理]** ページのメニュー バーから **[管理]** をポイントして **[フラグ]** をクリックします。  
  
3.  **[バージョン フラグの管理]** ページの **[モデル]** フィールドから、フラグを作成するモデルを選択します。  
  
4.  **[追加]** をクリックします。  
  
5.  **[名前]** ボックスに名前を入力します。  
  
6.  **[説明]** ボックスに説明を入力します。  
  
7.  **[コミット済みのバージョンのみ]** フィールドで **[True]** を選択すると、フラグは **[コミット済み]** の状態のバージョンにのみ割り当てることができます。 **[False]** を選択すると、フラグは任意の状態のバージョンに割り当てることができます。  
  
8.  **[保存]** をクリックします。  
  
## <a name="next-steps"></a>次の手順  
  
-   [バージョンにフラグを割り当てる&#40;マスター データ サービス&#41;](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## <a name="see-also"></a>参照  
 [バージョン&#40;マスター データ サービス&#41;](../../2014/master-data-services/versions-master-data-services.md)   
 [バージョン フラグ名を変更する&#40;マスター データ サービス&#41;](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  
