---
title: IP アドレスの制限の検出 (アップグレード アドバイザー) |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 9a154455-c68f-4403-a3a7-b90f4d35eecb
caps.latest.revision: 10
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 9dd20d23fbb18f67116d021b725796418ea2ccca
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37323752"
---
# <a name="ip-address-restriction-detected-upgrade-advisor"></a>IP アドレス制限が検出された (アップグレード アドバイザー)
  アップグレード アドバイザーによって、1 つ以上の IP アドレス制約が、レポート サーバー仮想ディレクトリまたはレポート マネージャー仮想ディレクトリをホストする IIS Web サイトで検出されました。 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] では、IP アドレス制約のネイティブ サポートは提供されません。  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ネイティブです。|  
  
## <a name="component"></a>コンポーネント  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a>説明  
 セットアップでは、アップグレード後のレポート サーバー用に作成された URL に IP アドレス制限を定義することはできません。 アップグレードを続行できますが、IP アドレス制限は [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URL に対して定義されません。  
  
## <a name="corrective-action"></a>修正措置  
 アップグレード後、ISA Server、ファイアウォール ソフトウェア、または別のソリューションを使用して、レポート サーバーに対する特定の IP アドレスからの要求を許可または除外してください。  
  
## <a name="see-also"></a>参照  
 [Reporting Services のアップグレードに関する問題&#40;アップグレード アドバイザー&#41;](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
