---
title: 文字列データ型の FOR XML のサポート | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- strings [SQL Server], XML
ms.assetid: bf069da8-de1e-44d2-a1fb-ade383076ac1
caps.latest.revision: 22
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 3b81ccaf551f1d2a6d2a3edb106f45b8f9aa606f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37329322"
---
# <a name="for-xml-support-for-string-data-types"></a>文字列データ型の FOR XML のサポート
  FOR XML で XML が生成されるときに、データ内の空白文字はエンティティに変換されます。  
  
 次の例では、サンプル テーブル **T** を作成し、ライン フィード、キャリッジ リターン、およびタブ文字が含まれたサンプル データを挿入します。 SELECT ステートメントは、このテーブルからサンプル データを取得します。  
  
```  
CREATE TABLE T  
(  
  c1 int identity primary key,  
  c2 varchar(100)  
);  
go  
  
INSERT T (c2) VALUES ('Special character 0xD for carriage return ' + convert(varchar(10), 0xD) + ' after carriage return');  
INSERT T (c2) VALUES ('Special character 0x9 for tab ' + convert(varchar(10), 0x9) + ' after tab' );  
INSERT T (c2) VALUES ('Special character 0xA for line feed ' + convert(varchar(10), 0xA) + ' after line feed');  
go  
SELECT *   
FROM T  
FOR XML AUTO;  
go  
```  
  
 結果を次に示します。  
  
```  
 <T c1="1" c2="Special character 0xD for carriage return   
 after carriage return" />  
 <T c1="2" c2="Special character 0x9 for tab     after tab" />  
 <T c1="3" c2="Special character 0xA for line feed   
after line feed" />  
```  
  
 上のクエリに関して、次の点に注意してください。  
  
-   1 行目のキャリッジ リターンは、&#xD というエンティティに変換されます。  
  
-   2 行目のタブ文字は、&#x09 というエンティティに変換されます。  
  
-   3 行目のライン フィード文字は、&#xA というエンティティに変換されます。  
  
## <a name="see-also"></a>参照  
 [各種 SQL Server データ型の FOR XML サポート](for-xml-support-for-various-sql-server-data-types.md)  
  
  
