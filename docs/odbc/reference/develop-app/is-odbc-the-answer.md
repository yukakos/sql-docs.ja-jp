---
title: ODBC の答えですか。 | Microsoft Docs
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
- interoperability [ODBC], ODBC
ms.assetid: bfa5e6ee-5979-42a9-be6f-a84d1ee7a54c
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: be3439dd75ac7e67fc83c630f9cf0e2ef670a863
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32911677"
---
# <a name="is-odbc-the-answer"></a>ODBC の答えですか。
相互運用性の問題を詳しく調べる前に、次の質問を検討してください必要があります、アプリケーションを使用して ODBC にしますか?。 奇妙な ODBC では、ガイドの「にたずねる質問かもしれませんが、実際には、正当なものです。 完全にデータベースを置き換えるネイティブ Api、ODBC がものではありません。 またが、すべての環境でデータベースへのアクセスを提供するよう設計されています。 データベースに共通のインターフェイスを提供するように設計されましたし、空きについて学習し、複数のデータベースへのリンクを維持することから、アプリケーション プログラマが想定されていました。  
  
 カスタム アプリケーションは、ネイティブ データベース Api の主要な候補です。 主な理由は、カスタム アプリケーションが多くの場合、1 つの DBMS での作業し、相互運用できるようにする必要があるないことです。 ネイティブ データベース Api は、特定の DBMS の機能を公開するための ODBC より的確を実行して ODBC によって公開されていない機能を公開する可能性があります。 さらに、カスタム アプリケーションの開発者は、DBMS のネイティブ データベース API を使い慣れて通常であるためには ODBC を学習する理由はほとんどです。 ただし、一部の Dbms の ODBC は、ネイティブ データベース API 興味深いはします。  
  
 どのアプリケーションも ODBC の候補としますか。 最適な候補は、1 つ以上の DBMS で動作するアプリケーションです。 これには、ほぼすべてのジェネリックおよび垂直方向のアプリケーションが含まれます。 また、カスタム アプリケーションの数も含まれます。 たとえば、いくつかのさまざまな Dbms を使用するカスタム アプリケーションより簡単かつよりも ODBC 複数のネイティブ Api を使用して記述するクリーナーです。 ODBC で記述されたカスタム アプリケーションでは、会社が 1 つの DBMS 間を移動するか、さまざまな Dbms に対して同じアプリケーションを展開の移行が容易です。
