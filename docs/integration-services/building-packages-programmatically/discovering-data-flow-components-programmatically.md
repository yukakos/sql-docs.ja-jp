---
title: プログラムによるデータ フロー コンポーネントの検出 | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- PipelineComponentInfos collection
- data flow task [Integration Services], components
- discovering data flow components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: ff92a96a-8af6-4532-82cc-c0bbff92401b
caps.latest.revision: 44
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: e7e1b4fc380182279fa2215f0ba696d27a5f32bb
ms.sourcegitcommit: f16003fd1ca28b5e06d5700e730f681720006816
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "35313171"
---
# <a name="discovering-data-flow-components-programmatically"></a>プログラムによるデータ フロー コンポーネントの検出
  データ フロー タスクをパッケージに追加したら、次の手順として、使用できるようにするデータ フロー コンポーネントを決定できます。 ローカル コンピューター上にインストールされ、使用可能なデータ フローの変換元、変換、および変換先は、プログラムによって検出できます。 パッケージにデータ フロー タスクを追加する方法について詳しくは、「[プログラムによるデータ フロー タスクの追加](../../integration-services/building-packages-programmatically/adding-the-data-flow-task-programmatically.md)」をご覧ください。  
  
## <a name="discovering-components"></a>コンポーネントの検出  
 <xref:Microsoft.SqlServer.Dts.Runtime.Application> クラスには、ローカル コンピューター上に正しくインストールされたコンポーネントごとに <xref:Microsoft.SqlServer.Dts.Runtime.Application.PipelineComponentInfos%2A> オブジェクトを格納する、<xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> コレクションが用意されています。 各 <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo> には、コンポーネントの名前、説明、および作成名など、コンポーネントに関する情報が含まれています。 コンポーネントをパッケージに追加したら、<xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> プロパティの戻り値を使用して、<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> の <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> プロパティを設定できます。  
  
## <a name="next-step"></a>次の手順  
 使用可能なコンポーネントを検出したら、次の手順として、コンポーネントを追加して構成します。この手順については、次のトピック「[プログラムによるデータ フロー コンポーネントの追加](../../integration-services/building-packages-programmatically/adding-data-flow-components-programmatically.md)」で説明します。  
  
## <a name="sample"></a>サンプル  
 次のコード例では、<xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfos> オブジェクトの <xref:Microsoft.SqlServer.Dts.Runtime.Application> コレクションを列挙し、ローカル コンピューターで使用可能なデータ フロー コンポーネントをプログラムによって検出する方法を示します。 このサンプルでは、Microsoft.SqlServer.ManagedDTS アセンブリへの参照が必要です。  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Application application = new Application();  
      PipelineComponentInfos componentInfos = application.PipelineComponentInfos;  
  
      foreach (PipelineComponentInfo componentInfo in componentInfos)  
      {  
        Console.WriteLine("Name: " + componentInfo.Name + "\n" +  
          " CreationName: " + componentInfo.CreationName + "\n");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim application As Application = New Application()  
  
    Dim componentInfos As PipelineComponentInfos = application.PipelineComponentInfos  
  
    For Each componentInfo As PipelineComponentInfo In componentInfos  
      Console.WriteLine("Name: " & componentInfo.Name & vbCrLf & _  
        " CreationName: " & componentInfo.CreationName & vbCrLf)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```
  
## <a name="see-also"></a>参照  
 [プログラムによるデータ フロー コンポーネントの追加](../../integration-services/building-packages-programmatically/adding-data-flow-components-programmatically.md)  
  
  
