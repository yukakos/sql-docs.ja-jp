---
title: JDBC ドライバーのデータ型について |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 7802328d-4d23-4775-9573-4169b127d258
caps.latest.revision: 27
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 399037b5f888c767edf28c40c0658d31e8703ddc
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "37982167"
---
# <a name="understanding-the-jdbc-driver-data-types"></a>JDBC ドライバーのデータ型について
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] は、[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] をデータベースとして使用する Java アプリケーション内での、JDBC の基本データ型と高度なデータ型の使用をサポートします。  
  
 JDBC の型システムは、[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] データ型と Java 言語の型やオブジェクトとの間の変換を仲介します。 JDBC の型は、SQL-92 および SQL-99 の型をモデルにしています。 JDBC ドライバーは、JDBC 仕様を満たし、予測可能性と柔軟性の適切なバランスを維持できるように設計されています。  
  
 このセクションのトピックでは、基本型および高度な型の使用方法と、データ型を他のデータ型に変換する方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|トピック|[説明]|  
|-----------|-----------------|  
|[基本データ型の使用](../../connect/jdbc/using-basic-data-types.md)|JDBC の基本データ型について説明します。 これには、結果セット、パラメーター化クエリ、およびストアド プロシージャを使用してデータ型を操作する方法の例が含まれます。|  
|[java.sql.Time の値をサーバーに送信する方法の構成](../../connect/jdbc/configuring-how-java-sql-time-values-are-sent-to-the-server.md)|JDBC Driver での日付の生成方法について説明します。|  
|[高度なデータ型の使用](../../connect/jdbc/using-advanced-data-types.md)|JDBC の高度なデータ型について説明します。|  
|[データ型の違いについて](../../connect/jdbc/understanding-data-type-differences.md)|JDBC ドライバーのさまざまなデータ型の違いについて説明します。|  
|[データ型変換について](../../connect/jdbc/understanding-data-type-conversions.md)|getter メソッドおよび setter メソッドを使用するときに、データ型の変換を処理する方法について説明します。|  
|[各国語文字セットのサポート](../../connect/jdbc/national-character-set-support.md)|National Character Set の型のサポートについて説明します。|  
|[XML データのサポート](../../connect/jdbc/supporting-xml-data.md)|SQLXML インターフェイスについて説明します。 **SQLXML** Java データ型を使用して、リレーショナル データベースから XML データを読み取ったり、リレーショナル データベースに XML データを書き込んだりする方法についても説明します。|  
|[ラッパーとインターフェイス](../../connect/jdbc/wrappers-and-interfaces.md)|アプリケーション サーバーでクラスのプロキシを作成できる [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] 固有のメソッドと定数を持つインターフェイスについて説明します。また、java.sql.Wrapper インターフェイスに対するサポートについても説明します。|  
  
## <a name="see-also"></a>参照  
 [JDBC ドライバーの概要](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
  
  
