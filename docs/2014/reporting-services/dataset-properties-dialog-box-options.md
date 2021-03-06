---
title: データセットのプロパティ ダイアログ ボックス、オプション |Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- "10130"
- sql12.rtp.rptdesigner.datasetproperties.options.f1
ms.assetid: 95299049-71ba-427f-b723-775cb696243f
caps.latest.revision: 39
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 7018038707462c2cf32a733b31cf66d25a275bfb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37319742"
---
# <a name="dataset-properties-dialog-box-options"></a>[オプション] ([データセットのプロパティ] ダイアログ ボックス)
  選択**オプション**上、**データセット**照合順序オプションや小計クエリなどのデータ オプションを変更するダイアログ ボックス。 詳細については、「 [Collation and Unicode Support](../relational-databases/collations/collation-and-unicode-support.md)」を参照してください。  
  
## <a name="options"></a>および  
 **[照合順序]**  
 データの並べ替えに使用される照合順序を決めるロケールを選択します。 **[既定]** は、レポート サーバーが、レポートの実行時にデータ プロバイダーから値の取得を試みる必要があることを示します。 値を取得できない場合、既定値はコンピューターのロケール設定から取得されます。  
  
 **大文字と小文字の区別**  
 大文字と小文字の区別を決める値を選択します。 データが大文字と小文字を区別するかどうかを示します。 **[大文字と小文字の区別]** は、 **[True]**、 **[False]**、または **[自動]** に設定できます。既定値の **[自動]** は、レポート サーバーが、レポートの実行時にデータ プロバイダーから値の取得を試みる必要があることを示します。 データ プロバイダーが大文字と小文字の区別をサポートしない場合、レポートは値が **[False]** の場合と同じように実行されます。 値を正確に把握しており、その値が確実にサポートされる場合は、 **[True]** を選択します。  
  
 **[アクセントの区別]**  
 アクセントの区別を決める値を選択します。 **[アクセントの区別]** は、データでアクセントを区別するかどうかを示します。 **[True]**、 **[False]**、または **[自動]** に設定できます。既定値の **[自動]** は、レポート サーバーが、レポートの実行時にデータ プロバイダーから値の取得を試みる必要があることを示します。 データ プロバイダーがアクセントの区別をサポートしない場合、レポートは値が **[False]** の場合と同じように実行されます。 値を正確に把握しており、その値が確実にサポートされる場合は、 **[True]** を選択します。  
  
 **[かなの区別]**  
 かなの区別を決める値を選択します。 データでかなを区別するかどうかを示します。 **[True]**、 **[False]**、または **[自動]** に設定できます。既定値の **[自動]** は、レポート サーバーが、レポートの実行時にデータ プロバイダーから値の取得を試みる必要があることを示します。 データ プロバイダーがかなの区別をサポートしない場合、レポートは値が **[False]** の場合と同じように実行されます。 値を正確に把握しており、その値が確実にサポートされる場合は、 **[True]** を選択します。  
  
 **[文字幅の区別]**  
 文字幅の区別を決める値を選択します。 データで文字幅を区別するかどうかを示します。 **[True]**、 **[False]**、または **[自動]** に設定できます。既定値の **[自動]** は、レポート サーバーが、レポートの実行時にデータ プロバイダーから値の取得を試みる必要があることを示します。 データ プロバイダーが文字幅の区別をサポートしない場合、レポートは値が **[False]** の場合と同じように実行されます。 値を正確に把握しており、その値が確実にサポートされる場合は、 **[True]** を選択します。  
  
 **[小計を詳細行として解釈]**  
 集計行ではなく詳細行として小計行を解釈するかどうかを示す値を選択します。 既定値は**自動**、レポートを使用しない場合に、小計行の詳細行として処理することを示します、`Aggregate`データ セット内のフィールドにアクセスする関数。 小計行を集計行として解釈する必要がある場合は、 **[False]** を選択します。 小計行の詳細行として解釈して、使用しないことがわかっている場合、 `Aggregate`() 関数を選択**True**します。  
  
## <a name="see-also"></a>参照  
 [レポートまたはテキスト ボックスのロケールを設定&#40;Reporting Services&#41;](report-design/set-the-locale-for-a-report-or-text-box-reporting-services.md)   
 [レポートにデータを追加&#40;レポート ビルダーおよび SSRS&#41;](report-data/report-datasets-ssrs.md)   
 [Windows 照合順序名 &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql)   
 [SQL Server 照合順序名 &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql)   
 [集計関数&#40;レポート ビルダーおよび SSRS&#41;](report-design/report-builder-functions-aggregate-function.md)  
  
  
