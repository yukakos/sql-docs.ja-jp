---
title: システム オブジェクトを削除するステートメントを削除する |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
caps.latest.revision: 18
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 7bb577db82aae98356481657faa9bd76a0ab2a82
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37161833"
---
# <a name="remove-statements-that-drop-system-objects"></a>システム オブジェクトを破棄するステートメントを削除する
  アップグレード アドバイザーによって、システム オブジェクトを削除するステートメントが検出されました。 拡張ストアド プロシージャを含む、システム オブジェクトは、読み取り専用でデプロイされる**リソース**データベース (mssqlsystemresource) を削除できません。 システム オブジェクトに対する EXECUTE 権限を禁止または拒否するように、アプリケーションを変更します。  
  
## <a name="component"></a>コンポーネント  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a>説明  
 DROP TABLE、DROP PROCEDURE などのステートメントと**sp_dropextendedproc** 、読み取り専用でこれらのオブジェクトが展開されるため、システム オブジェクトを削除するのには使用できません**リソース**データベース。  
  
## <a name="corrective-action"></a>修正措置  
 アプリケーションからシステム オブジェクトの削除を試行するすべてのステートメントを削除します。 システム オブジェクトに対する EXECUTE 権限を禁止または拒否するように、アプリケーションを変更します。 または、セキュリティ構成 (SAC) ツールを使用して、システム オブジェクトの一部を無効にすることもできます。 たとえば、 **xp_cmdshell**拡張ストアド プロシージャを無効にできますか、SAC ツールを使用して有効になっています。  
  
## <a name="see-also"></a>参照  
 [データベース エンジンのアップグレードに関する問題](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [SQL Server 2014 アップグレード アドバイザー&#91;新規&#93;](/sql/2014/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
