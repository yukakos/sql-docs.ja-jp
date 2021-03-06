---
title: INSERT ステートメントまたは UPDATE ステートメントに対して外部キー制約を無効にする方法 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: table-view-index, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: table-view-index
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
- UPDATE statement [SQL Server], foreign key constraints
- INSERT statement [SQL Server], foreign key constraints
ms.assetid: 029168d7-085e-4b13-9b86-5644b67c6e24
caps.latest.revision: 18
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: f516accaa507a1bb4f1bcce42e42f20c21a85fc3
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "37969734"
---
# <a name="disable-foreign-key-constraints-with-insert-and-update-statements"></a>INSERT ステートメントまたは UPDATE ステートメントに対して外部キー制約を無効にする方法
[!INCLUDE[tsql-appliesto-ss2016-all-md](../../includes/tsql-appliesto-ss2016-all-md.md)]

  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] では、 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] または [!INCLUDE[tsql](../../includes/tsql-md.md)]を使用して、INSERT トランザクションまたは UPDATE トランザクションの実行中に外部キー制約を無効にできます。 新しいデータが既存の制約に違反しないことがわかっている場合、またはデータベース内の既存のデータのみに制約を適用する場合に、このオプションを使用します。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [制限事項と制約事項](#Restrictions)  
  
     [Security](#Security)  
  
-   **以下を使用して INSERT ステートメントまたは UPDATE ステートメントに対して外部キー制約を無効にするには:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 作業を開始する準備  
  
###  <a name="Restrictions"></a> 制限事項と制約事項  
 これらの制約を無効にすると、今後列に行われる挿入または更新は、制約条件に対して検証されません。  
  
###  <a name="Security"></a> セキュリティ  
  
####  <a name="Permissions"></a> Permissions  
 テーブルに対する ALTER 権限が必要です。  
  
##  <a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a>INSERT ステートメントまたは UPDATE ステートメントに対して外部キー制約を無効にするには  
  
1.  **オブジェクト エクスプローラー**で、制約が含まれているテーブルを展開し、 **[キー]** フォルダーを展開します。  
  
2.  制約を右クリックし、 **[変更]** をクリックします。  
  
3.  **[テーブル デザイナー]** の下のグリッドで、 **[外部キーの制約を適用]** をクリックし、ドロップダウン ボックスの一覧の **[いいえ]** をクリックします。  
  
4.  **[閉じる]** をクリックします。  
  
##  <a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a>INSERT ステートメントまたは UPDATE ステートメントに対して外部キー制約を無効にするには  
  
1.  **オブジェクト エクスプローラー**で、 [!INCLUDE[ssDE](../../includes/ssde-md.md)]のインスタンスに接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT FK_PurchaseOrderHeader_Employee_EmployeeID;  
    GO  
    ```  
  
 詳細については、「[ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)」を参照してください。  
  
###  <a name="TsqlExample"></a>  
