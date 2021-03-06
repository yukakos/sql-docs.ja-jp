---
title: 要素 (XMLA) コマンド |Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 6886bcd7372d4071db562a612d934e34586cdea0
ms.sourcegitcommit: c7a98ef59b3bc46245b8c3f5643fad85a082debe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2018
ms.locfileid: "38979234"
---
# <a name="command-element-xmla"></a>Command 要素 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  によって実行されるコマンドが含まれています、 [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md)メソッド。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Execute>  
   ...  
   <Command>  
      <Alter>...</Alter>  
      <!-- or -->  
      <Backup>...</Backup>  
      <!-- or -->  
      <Batch>...</Batch>  
      <!-- or -->  
      <BeginTransaction>...</BeginTransaction>  
      <!-- or -->  
      <Cancel>...</Cancel>  
      <!-- or -->  
      <ClearCache>...</ClearCache>  
      <!-- or -->  
      <CommitTransaction>...</CommitTransaction>  
      <!-- or -->  
      <Create>...</Create>  
      <!-- or -->  
      <Delete>...</Delete>  
      <!-- or -->  
      <DesignAggregations>...</DesignAggregations>  
      <!-- or -->  
      <Drop>...</Drop>  
      <!-- or -->  
      <Insert>...</Insert>  
      <!-- or -->  
      <Lock>...</Lock>  
      <!-- or -->  
      <MergePartitions>...</MergePartitions>  
      <!-- or -->  
      <NotifyTableChange>...</NotifyTableChange>  
      <!-- or -->  
      <Process>...</Process>  
      <!-- or -->  
      <Restore>...</Restore>  
      <!-- or -->  
      <RollbackTransaction>...</RollbackTransaction>  
      <!-- or -->  
      <SetPasswordEncryptionKey>...</SetPasswordEncryptionKey>  
      <!-- or -->  
      <Statement>...</Statement>  
      <!-- or -->  
      <Subscribe>...</Subscribe>  
      <!-- or -->  
      <Synchronize>...</Synchronize>  
      <!-- or -->  
      <Unlock>...</Unlock>  
      <!-- or -->  
      <Update>...</Update>  
      <!-- or -->  
      <UpdateCells>...</UpdateCells>  
   </Command>  
   ...  
</Execute>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|なし|  
|既定値|なし|  
|Cardinality|1-1 : 必須要素で、1 回だけ出現します|  
  
## <a name="element-relationships"></a>要素間のリレーションシップ  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[実行](../../../analysis-services/xmla/xml-elements-methods-execute.md)|  
|子要素|[Alter](../../../analysis-services/xmla/xml-elements-commands/alter-element-xmla.md)、[バックアップ](../../../analysis-services/xmla/xml-elements-commands/backup-element-xmla.md)、[バッチ](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md)、 [BeginTransaction](../../../analysis-services/xmla/xml-elements-commands/begintransaction-element-xmla.md)、[キャンセル](../../../analysis-services/xmla/xml-elements-commands/cancel-element-xmla.md)、 [ClearCache](../../../analysis-services/xmla/xml-elements-commands/clearcache-element-xmla.md)、 [CommitTransaction](../../../analysis-services/xmla/xml-elements-commands/committransaction-element-xmla.md)、[作成](../../../analysis-services/xmla/xml-elements-commands/create-element-xmla.md)、[削除](../../../analysis-services/xmla/xml-elements-commands/delete-element-xmla.md)、 [DesignAggregations](../../../analysis-services/xmla/xml-elements-commands/designaggregations-element-xmla.md)、[ドロップ](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md)、[挿入](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)、[ロック](../../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md)、 [MergePartitions](../../../analysis-services/xmla/xml-elements-commands/mergepartitions-element-xmla.md)、 [NotifyTableChange](../../../analysis-services/xmla/xml-elements-commands/notifytablechange-element-xmla.md)、[プロセス](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)、[復元](../../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md)、 [RollbackTransaction](../../../analysis-services/xmla/xml-elements-commands/rollbacktransaction-element-xmla.md)、 [SetPasswordEncryptionKey](http://msdn.microsoft.com/fb262737-f0f4-4441-985e-3b2a94d00a9e)、[ステートメント](../../../analysis-services/xmla/xml-elements-commands/statement-element-xmla.md)、 [サブスクライブ](../../../analysis-services/xmla/xml-elements-commands/subscribe-element-xmla.md)、[同期](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)、[のロックを解除](../../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md)、 [Update](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)、 [UpdateCells](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md)|  
  
## <a name="remarks"></a>コメント  
 **コマンド**要素によって使用されます、 **Execute**メソッドがデータ ソースにコマンドをリレーします。 XML をのみ Analysis (XMLA) 1.1 仕様をサポートしているときに、**ステートメント**コマンドを Analysis Services は、新しい XMLA コマンドの多くをサポートしています。 サポートされる XMLA コマンドの詳細については[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]を参照してください[コマンド&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)します。  
  
## <a name="see-also"></a>参照
 [XML データ型&#40;XMLA&#41;](../../../analysis-services/xmla/xml-data-types/xml-data-types-xmla.md)   
 [プロパティ&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
