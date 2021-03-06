---
title: MSSQLSERVER_2570 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
caps.latest.revision: 20
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9aff7469725314ec0e8f2c4a4eb41a12ac53b367
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2018
ms.locfileid: "37428821"
---
# <a name="mssqlserver2570"></a>MSSQLSERVER_2570
    
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|SQL Server|  
|イベント ID|2570|  
|イベント ソース|MSSQLSERVER|  
|コンポーネント|SQLEngine|  
|シンボル名|DBCC_COLUMN_VALUE_OUT_OF_RANGE|  
|メッセージ テキスト|ページ P_ID、オブジェクト ID O_ID のスロット S_ID、インデックス ID I_ID、パーティション ID PN_ID、アロケーション ユニット ID A_ID (型 TYPE)。 列 COLUMN_NAME の値が、データ型 "DATATYPE" の範囲外です。 列を有効な値に更新してください。|  
  
## <a name="explanation"></a>説明  
 指定した列に格納されている値は、列のデータ型に対する有効値の範囲外です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーは修復できません。 列のデータ型に対する範囲内に収まるよう列の値を更新して、再度コマンドを実行してください。  詳細については、サポート技術情報の資料 [923247](http://support.microsoft.com/kb/923247) を参照してください。  
  
## <a name="see-also"></a>参照  
 [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql)   
 [データ型 &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
