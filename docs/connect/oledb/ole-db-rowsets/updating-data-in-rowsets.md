---
title: 行セットのデータの更新 |Microsoft Docs
description: SQL Server の OLE DB ドライバーを使用して行セット内のデータを更新しています
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.component: oledb|ole-db-rowsets
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- updating data [SQL Server]
- rowsets [OLE DB], updating data
- OLE DB Driver for SQL Server, rowsets
- OLE DB rowsets, updating data
- OLE DB Driver for SQL Server, data updates
- data updates [SQL Server], OLE DB
author: pmasl
ms.author: Pedro.Lopes
manager: craigg
ms.openlocfilehash: 20484bce71d0e776b4090f743c65e3a78d655a70
ms.sourcegitcommit: 50838d7e767c61dd0b5e677b6833dd5c139552f2
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2018
ms.locfileid: "39108814"
---
# <a name="updating-data-in-rowsets"></a>行セット内のデータの更新
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB プロバイダーでは、コンシューマーが  のデータを含む変更可能な行セットを更新するときに、該当するデータが更新されます。 コンシューマーが IRowsetChange **インターフェイスまたは IRowsetUpdate** インターフェイスのいずれかのサポートを要求すると、変更可能な行セットが作成されます。  
  
 すべて OLE DB Driver for SQL Server が変更可能な行セットの使用[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]行セットをサポートするカーソル。 行セット プロパティ DBPROP_LOCKMODE は、カーソルでの [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] の同時実行制御動作を変更し、更新可能な行セット内の行をフェッチする動作や、その行セット内のデータの整合性に関するエラーを生成する動作を決定します。  
  
 OLE DB Driver for SQL Server では前に、または更新後の行の同期をサポートします。  
  
> [!NOTE]  
>  IRowChange::SetColumns を使用して、行オブジェクトの 1 つ以上の名前付き列の値を設定できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL Server カーソルでのデータ更新](../../oledb/ole-db-rowsets/updating-data-in-sql-server-cursors.md)  
  
-   [行の再同期](../../oledb/ole-db-rowsets/updating-data-in-rowsets-resynchronizing-rows.md)  
  
## <a name="see-also"></a>参照  
 [行セット](../../oledb/ole-db-rowsets/rowsets.md)  
  
  
