---
title: '[データ ビューアー] | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
caps.latest.revision: 13
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 31a33e37ec08ea8aac2a6e958ec91ee4cf0bb7af
ms.sourcegitcommit: de5e726db2f287bb32b7910831a0c4649ccf3c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2018
ms.locfileid: "35330956"
---
# <a name="data-viewer"></a>[データ ビューアー]
  パスがデータ ビューアーを使用するように構成されている場合、データ ビューアーはデータが 2 つのデータ フロー コンポーネントを移動するときに、バッファーによるデータ バッファーを表示します。  
  
## <a name="options"></a>および  
 **緑色の矢印**  
 クリックすると、次のバッファーのデータが表示されます。 データが 1 つのバッファーに移動される場合、このオプションは使用できません。  
  
 **[デタッチ]**  
 データ ビューアーをデタッチします。  
  
 **注** &#xA0;&#xA0;&#xA0;データ ビューアーをデタッチしてもデータ ビューアーは削除されません。 データ ビューアーがデタッチされた場合、データはパスを流れますが、ビューアー内のデータを各バッファーのデータに一致させる更新は行われません。  
  
 **[アタッチ]**  
 データ ビューアーをアタッチします。  
  
 **注** &#xA0;&#xA0;&#xA0;アタッチされたデータ ビューアーは、データ フロー内の各バッファーからの情報を表示してから、一時停止します。 緑色の矢印を使用して次のバッファーに進むことができます。  
  
 **[データのコピー]**  
 現在のバッファーのデータをクリップボードにコピーします。  
  
## <a name="see-also"></a>参照  
 [データ フローのデバッグ](../../integration-services/troubleshooting/debugging-data-flow.md)  
  
  
