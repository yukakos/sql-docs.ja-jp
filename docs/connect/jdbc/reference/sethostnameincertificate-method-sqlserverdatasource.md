---
title: setHostNameInCertificate メソッド (SQLServerDataSource) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- setHostNameInCertificate Method (SQLServerDataSource)
apilocation:
- setHostNameInCertificate Method (SQLServerDataSource)
apitype: Assembly
ms.assetid: 2bcf4f2e-a103-4374-abc4-ffad4ce8e3c0
caps.latest.revision: 14
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 774f2cd158612f0029212014e53e380cef180c04
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32842917"
---
# <a name="sethostnameincertificate-method-sqlserverdatasource"></a>setHostNameInCertificate メソッド (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  検証に使用されるホスト名を設定、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Secure Sockets Layer (SSL) 証明書。  
  
## <a name="syntax"></a>構文  
  
```  
  
public void setHostNameInCertificate(java.lang.String hostNameInCertificate)  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hostNameInCertificate*  
  
 A**文字列**ホスト名を格納しています。  
  
## <a name="remarks"></a>解説  
 HostNameInCertificate 値は検証に使用、[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]通信レイヤーが SSL を使用して暗号化されている場合、SSL 証明書。 既定値は、null です。  
  
 Null または指定されていない場合に、hostNameInCertificate プロパティが設定されている場合、[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]検証に使用する、serverName プロパティ値を使用、 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] SSL 証明書。 hostNameInCertificate プロパティが任意の文字列または空の文字列 "" に設定されている場合、ドライバーはその値を使用してサーバーの SSL 証明書を検証します。  
  
## <a name="see-also"></a>参照  
 [SQLServerDataSource のメンバー](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource クラス](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
