---
title: 重複する行の除外 (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-visual-db
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- search criteria [SQL Server], excluding rows
- row duplicates [SQL Server]
- duplicate rows
- row excluded in search [SQL Server]
- result sets [SQL Server], duplicate values
- excluding rows
ms.assetid: ab35a363-421d-4665-946b-ae3f6397af50
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 3353bcc208de8fb73a135bb7370e24cbec135ba1
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "33048784"
---
# <a name="exclude-duplicate-rows-visual-database-tools"></a>重複する行の除外 (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
結果セットに一意の値だけが必要な場合は、結果セットからの重複の削除を指定できます。  
  
### <a name="to-exclude-duplicate-rows-from-the-result-set"></a>結果セットから重複行を削除するには  
  
1.  ダイアグラム ペインの背景を右クリックし、ショートカット メニューの **[プロパティ]** を選択します。  
  
2.  プロパティ ウィンドウの **[一意の値]** をクリックし、値を **[はい]** に設定します。  
  
    SQL ステートメントの表示列の一覧の前にキーワード DISTINCT が挿入されます。  
  
    > [!NOTE]  
    > DISTINCT キーワードを使用する場合、結果ペインで結果セットを変更できない場合があります。  
  
## <a name="see-also"></a>参照  
[検索基準の指定 (Visual Database Tools)](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
[クエリ結果の並べ替えおよびグループ化 (Visual Database Tools)](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
  
