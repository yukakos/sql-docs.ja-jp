---
title: sp_help_jobactivity (TRANSACT-SQL) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_help_jobactivity_TSQL
- sp_help_jobactivity
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_jobactivity
ms.assetid: d344864f-b4d3-46b1-8933-b81dec71f511
caps.latest.revision: 33
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 648fb94f5a14365356a293f6fb0652336ca0625b
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33259402"
---
# <a name="sphelpjobactivity-transact-sql"></a>sp_help_jobactivity (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェント ジョブのランタイム状態に関する情報を一覧表示します。  
  
 ![トピック リンク アイコン](../../database-engine/configure-windows/media/topic-link.gif "トピック リンク アイコン") [Transact-SQL 構文表記規則](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>構文  
  
```  
  
sp_help_jobactivity { [ @job_id = ] job_id | [ @job_name = ] 'job_name' }  
     [ , [ @session_id = ] session_id ]  
```  
  
## <a name="arguments"></a>引数  
 [ **@job_id =**] *job_id*  
 ジョブの識別番号。 *job_id*は**uniqueidentifier**、既定値は NULL です。  
  
 [ **@job_name =**] **'***job_name***'**  
 ジョブの名前を指定します。 *job_name*は**sysname**、既定値は NULL です。  
  
> [!NOTE]  
>  いずれか*job_id*または*job_name*指定する必要がありますが、両方を指定することはできません。  
  
 [ **@session_id** =] *session_id*  
 情報をレポートするセッション ID を指定します。 *session_id*は**int**、既定値は NULL です。  
  
## <a name="return-code-values"></a>リターン コードの値  
 **0** (成功) または**1** (失敗)  
  
## <a name="result-sets"></a>結果セット  
 次の結果セットを返します。  
  
|列名|データ型|Description|  
|-----------------|---------------|-----------------|  
|**session_id**|**int**|エージェント セッションの ID 番号。|  
|**job_id**|**uniqueidentifier**|ジョブの識別子。|  
|**job_name**|**sysname**|ジョブの名前。|  
|**run_requested_date**|**datetime**|ジョブの実行が要求された日付。|  
|**run_requested_source**|**sysname**|ジョブの実行を要求するソース。 次のいずれかです。<br /><br /> **1**スケジュールに基づいて実行を =<br /><br /> **2**警告に対する応答の実行を =<br /><br /> **3**起動時に実行を =<br /><br /> **4**ユーザーが実行を =<br /><br /> **6** CPU アイドル スケジュールに基づいて実行を =|  
|**queued_date**|**datetime**|要求がキューに登録された日付。 ジョブが直接実行された場合は NULL になります。|  
|**start_execution_date**|**datetime**|ジョブが実行可能なスレッドに割り当てられた日付。|  
|**last_executed_step_id**|**int**|最後にジョブ ステップを実行したステップ ID。|  
|**last_exectued_step_date**|**datetime**|最後にジョブ ステップを開始した日付。|  
|**stop_execution_date**|**datetime**|ジョブが停止した日付。|  
|**next_scheduled_run_date**|**datetime**|ジョブは、次にスケジュール設定する場合を実行します。|  
|**job_history_id**|**int**|ジョブ履歴テーブルにあるジョブ履歴の識別子。|  
|**message**|**nvarchar(1024)**|前回のジョブ実行中に生成したメッセージ。|  
|**run_status**|**int**|前回のジョブの実行で返されたステータス。<br /><br /> **0** = 失敗エラー<br /><br /> **1** = に成功しました<br /><br /> **3** = キャンセル<br /><br /> **5** = 状態不明|  
|**operator_id_emailed**|**int**|ジョブの完了時に電子メールの通知を受けたオペレーターの ID 番号。|  
|**operator_id_netsent**|**int**|経由で通知を受けるオペレーターの ID 番号**net send**でジョブの実行が完了します。|  
|**operator_id_paged**|**int**|ジョブの完了時に、ポケットベルの通知を受けたオペレーターの ID 番号。|  
  
## <a name="remarks"></a>解説  
 このプロシージャでは、ジョブに関する現在の状態のスナップショットが生成されます。 返された結果は、要求が処理された時点での情報です。  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントは、エージェント サービスが開始されるたびに、セッション id を作成します。 セッション id は、テーブルに格納される**msdb.dbo.syssessions**です。  
  
 ない場合*session_id*には、最新のセッションに関する情報を表示します。  
  
 ない場合*job_name*または*job_id*には、すべてのジョブの情報を一覧表示します。  
  
## <a name="permissions"></a>権限  
 既定では、メンバー、 **sysadmin**固定サーバー ロールは、このストアド プロシージャを実行できます。 他のユーザーには、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb **データベースの次のいずれかの** エージェント固定データベース ロールが許可されている必要があります。  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 これらのロールの権限の詳細については、「 [SQL Server エージェントの固定データベース ロール](http://msdn.microsoft.com/library/719ce56b-d6b2-414a-88a8-f43b725ebc79)」を参照してください。  
  
 メンバーだけ**sysadmin**他のユーザーが所有するジョブの利用状況を表示することができます。  
  
## <a name="examples"></a>使用例  
 次の例では、現在のユーザーが表示する権限を持つ、すべてのジョブの利用状況を一覧表示します。  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_jobactivity ;  
GO  
```  
  
## <a name="see-also"></a>参照  
 [SQL Server エージェント ストアド プロシージャ&#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sql-server-agent-stored-procedures-transact-sql.md)  
  
  
