---
title: 列名の制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- desktop database drivers [ODBC], column names
- ODBC desktop database drivers [ODBC], column names
ms.assetid: 5a339f61-c52f-40ad-8deb-d785f72753d4
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3f3f384b9a2080ab683c8148effe7c6a9a13fcd6
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32899187"
---
# <a name="column-name-limitations"></a>列名の制限
列名は、有効な文字 (スペースなど) を含めることができます。 列名に文字、数字、およびアンダー スコアを除く任意の文字が含まれている場合は、逆引用符 (') で囲んだ名前を区切る必要があります。  
  
 Microsoft Access または Microsoft Excel のドライバーを使用する場合は、列名は 64 文字に制限されより長い名前がエラーを生成します。 Paradox ドライバーを使用すると、最大の列名は、25 文字です。 テキストのドライバーを使用すると最大の列名は 64 文字より長い名前は切り捨てられます。  
  
 DBASE ドライバーを使用すると、127 より大きい ASCII 値を持つ文字はアンダー スコアに変換されます。  
  
 Microsoft Excel ドライバーを使用すると、列名が存在する場合は、最初の行であることが必要です。 Microsoft excel を使用する名前、"!"文字は、逆引用符 (') で囲む必要があります。 "!"文字は、「$」文字に変換されますので、"!"文字は名前がバック引用符で囲まれている場合でも、ODBC 名では無効です。 その他のすべての有効な Excel 文字 (パイプ文字を除く (&#124;))、スペースを含めて、列名で使用できます。 区切られた識別子は、Microsoft Excel の列名のスペースを含めるにするために使用する必要があります。 指定されていない列の名前はドライバーで生成された名前、たとえば、"Col1"の最初の列に置き換えられます。  
  
 パイプ文字 (&#124;) バック引用符で囲まれた名前が囲まれているかどうかどうか、列名では使用できません。  
  
 テキストのドライバーを使用すると、ドライバーは、列名が指定されていない場合、既定の名前を提供します。 たとえば、ドライバーは、最初の列 F1、F2、2 列目となどを呼び出します。
