---
title: バッチ要素 (XMLA) |Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 2f249402d3348e491a409da52db76f531bcd594f
ms.sourcegitcommit: c7a98ef59b3bc46245b8c3f5643fad85a082debe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2018
ms.locfileid: "38981894"
---
# <a name="batch-element-xmla"></a>Batch 要素 (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  順番にまたは Analysis Services のインスタンスに同時に、1 つまたは複数の XML をバッチ操作として for Analysis (XMLA) コマンド実行します。  
  
## <a name="syntax"></a>構文  
  
```xml  
  
<Command>  
   <Batch Transaction="Boolean" ProcessAffectedObjects="Boolean">  
      <Bindings>...</Bindings>  
      <DataSource>...</DataSource>  
      <DataSourceView>...</DataSourceView>  
      <ErrorConfiguration>...</ErrorConfiguration>  
      <Parallel>...</Parallel>  
      <!-- One or more XMLA commands -->  
   </Batch>  
</Command>  
```  
  
## <a name="element-characteristics"></a>要素の特性  
  
|特性|説明|  
|--------------------|-----------------|  
|データ型と長さ|なし|  
|既定値|なし|  
|Cardinality|0-n : 省略可能な要素で、出現する場合は複数回の出現が可能です|  
  
## <a name="element-relationships"></a>要素間のリレーションシップ  
  
|リレーションシップ|要素|  
|------------------|-------------|  
|親要素|[Command](../../../analysis-services/xmla/xml-elements-properties/command-element-xmla.md)|  
|子要素|[バインド](../../../analysis-services/xmla/xml-elements-properties/bindings-element-xmla.md)、 [DataSource](../../../analysis-services/xmla/xml-elements-properties/datasource-element-xmla.md)、 [DataSourceView](../../../analysis-services/xmla/xml-elements-properties/datasourceview-element-xmla.md)、 [ErrorConfiguration](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md)、[並列](../../../analysis-services/xmla/xml-elements-properties/parallel-element-xmla.md)<br /><br /> 1 つ以上の次の XMLA コマンド: [Alter](../../../analysis-services/xmla/xml-elements-commands/alter-element-xmla.md)、[バックアップ](../../../analysis-services/xmla/xml-elements-commands/backup-element-xmla.md)、 [BeginTransaction](../../../analysis-services/xmla/xml-elements-commands/begintransaction-element-xmla.md)、 [ClearCache](../../../analysis-services/xmla/xml-elements-commands/clearcache-element-xmla.md)、 [CommitTransaction](../../../analysis-services/xmla/xml-elements-commands/committransaction-element-xmla.md)、[作成](../../../analysis-services/xmla/xml-elements-commands/create-element-xmla.md)、[削除](../../../analysis-services/xmla/xml-elements-commands/delete-element-xmla.md)、 [DesignAggregations](../../../analysis-services/xmla/xml-elements-commands/designaggregations-element-xmla.md)、[ドロップ](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md)、 [挿入](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)、[ロック](../../../analysis-services/xmla/xml-elements-commands/lock-element-xmla.md)、 [MergePartitions](../../../analysis-services/xmla/xml-elements-commands/mergepartitions-element-xmla.md)、 [NotifyTableChange](../../../analysis-services/xmla/xml-elements-commands/notifytablechange-element-xmla.md)、[プロセス](../../../analysis-services/xmla/xml-elements-commands/process-element-xmla.md)、 [復元](../../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md)、 [RollbackTransaction](../../../analysis-services/xmla/xml-elements-commands/rollbacktransaction-element-xmla.md)、 [SetPasswordEncryptionKey](http://msdn.microsoft.com/fb262737-f0f4-4441-985e-3b2a94d00a9e)、[ステートメント](../../../analysis-services/xmla/xml-elements-commands/statement-element-xmla.md)、[サブスクライブ](../../../analysis-services/xmla/xml-elements-commands/subscribe-element-xmla.md)、[同期](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)、[のロックを解除](../../../analysis-services/xmla/xml-elements-commands/unlock-element-xmla.md)、 [Update](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)、 [UpdateCells](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md)|  
  
## <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|ProcessAffectedObjects|(省略可能な**ブール**属性) を再処理を必要とするすべてのオブジェクトを処理するかどうかを示します。<br /><br /> 場合は true に設定する、[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]インスタンスに含まれるオブジェクトの処理結果として再処理を必要とする任意のオブジェクトを処理する、**バッチ**コマンド。<br /><br /> 場合設定**false**、[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]インスタンスに含まれるオブジェクトのみを処理する、**バッチ**コマンド。|  
|トランザクション|(省略可能な**ブール**属性) で、コマンドが含まれるかどうかを示します、**バッチ**コマンドは、単一のトランザクションまたは個々 のトランザクションとして扱われます。<br /><br /> 場合に含まれるコマンドはすべて true に設定する、**バッチ**コマンドは、単一のトランザクションと見なされます。 いずれかのコマンドが失敗した場合、失敗したコマンドの前に実行されるコマンドはロールバック、**バッチ**せず、後続のコマンドを実行するコマンドを停止します。<br /><br /> 場合設定**false**、**バッチ**コマンドは、すべてのコマンドを実行しようとし、正常に完了した各コマンドの結果をコミットします。|  
  
## <a name="remarks"></a>コメント  
  
> [!WARNING]  
>  バッチ操作内でのコマンド/実行/ステートメントは現在サポートされません。  
  
 XMLA におけるバッチ操作の実行の詳細については、次を参照してください。[バッチ操作の実行&#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/performing-batch-operations-xmla.md)します。  
  
## <a name="see-also"></a>参照
 [コマンド&#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)  
  
  
