---
title: 数値属性を作成する (マスター データ サービス) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], creating number attributes
- creating number attributes [Master Data Services]
ms.assetid: c0dbb6d8-ba78-485a-a40d-6d5cb7e75d0a
caps.latest.revision: 9
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: e6965c60178eec6405e249ff2801e139fa1e3244
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2018
ms.locfileid: "35407274"
---
# <a name="create-a-numeric-attribute-master-data-services"></a>数値属性を作成する (マスター データ サービス)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]で、ユーザーにより属性値として数値が入力される場合は、数値属性を作成します。  
  
> [!NOTE]  
>  数値属性には制限があります。 詳細については、「 [属性 (マスター データ サービス)](../master-data-services/attributes-master-data-services.md)」を参照してください。  
  
## <a name="prerequisites"></a>Prerequisites  
 この手順を実行するには  
  
-   **[システム管理]** 機能領域にアクセスする権限が必要です。  
  
-   モデル管理者である必要があります。 詳細については、「 [管理者 (マスター データ サービス)](../master-data-services/administrators-master-data-services.md)にアクセスすることなくグループに対してユーザーの追加または削除を行うことができます。  
  
-   属性を作成するエンティティが存在する必要があります。 詳細については、「[エンティティを作成する (マスター データ サービス)](../master-data-services/create-an-entity-master-data-services.md)」を参照してください。  
  
## <a name="attribute-information"></a>属性情報  
 作成された属性ごとに、7 列の行がグリッドに追加されます。 次の表で各列について説明します。  
  
|[列]|[説明]|  
|------------|-----------------|  
|状態|属性の状態。<br /><br /> [保存] をクリックしたときに表示される ![更新中状態のアイコン](../master-data-services/media/mds-statusicon-updating.png "更新中状態のアイコン") 画像は、属性が更新中であることを示します。<br /><br /> 属性の作成中または編集中にエラーが発生すると、![エラー状態のアイコン](../master-data-services/media/mds-statusicon-error.png "エラー状態のアイコン") 画像が表示されます。<br /><br /> それ以外の場合は適切な状態であり、![適切な状態のアイコン](../master-data-services/media/mds-statusicon-ok.png "適切な状態のアイコン") が表示されます。|  
|[オブジェクト名]|属性名です。|  
|表示名|属性の表示名。|  
|[説明]|属性の説明。|  
|ピクセル幅の表示|属性の幅。|  
|種類とプロパティ|属性の種類とデータ型の情報。|  
|変更の追跡を有効化|変更の追跡に対して属性が有効になっているかどうかを指定し、グループ番号を括弧で表示します。|  
  
 属性をクリックすると、次の情報が表示されます。  
  
-   **作成者**: 属性を作成したユーザーの名前。  
  
-   **作成日時**: 属性が作成された日時。  
  
-   **更新者**: 属性を最後に更新したユーザーの名前。  
  
-   **更新日時**: 属性が最後に更新された日時。  
  
### <a name="to-create-a-numeric-attribute"></a>数値属性を作成するには  
  
1.  [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]で **[システム管理]** をクリックします。  
  
2.  **[モデルの管理]** ページでグリッドからモデルを選択し、 **[エンティティ]** をクリックします。  
  
3.  **[エンティティの管理]** ページで、属性を作成するエンティティの行を選択します。  
  
4.  **[属性]** をクリックします。  
  
5.  **[属性の管理]** ページで、次のいずれかの操作を行い、 **[追加]** をクリックします。  
  
    -   属性の対象がリーフ メンバーの場合、 **[メンバーの種類]** ボックスの一覧から **[リーフ]** を選択します。  
  
    -   属性の対象が統合メンバーの場合、 **[メンバーの種類]** ボックスの一覧から **[統合]** を選択します。  
  
    -   属性の対象がコレクションの場合、 **[メンバーの種類]** ボックスの一覧から **[コレクション]** を選択します。  
  
6.  **[名前]** ボックスに属性の名前を入力します。 属性名として使用できない単語の一覧については、「[予約語 (マスター データ サービス)](../master-data-services/reserved-words-master-data-services.md)」を参照してください。  
  
7.  (省略可能) 表示名を入力し、 **[説明]** ボックスに説明を入力します。  
  
8.  **[ピクセル幅の表示]** ボックスに、 **[エクスプローラー]** グリッドに表示する属性列の幅を入力します。  
  
9. **[属性の種類]** リストから、 **[自由形式]** を選択します。  
  
10. **[データ型]** ボックスの一覧から **[Number]** を選択します。  
  
11. **[10 進]** ボックスに、小数点の後に入力できる数字の桁数を入力します。  
  
12. **[定型入力]** ボックスの一覧から負の数値の形式を選択します。  
  
13. 必要に応じて、 **[変更の追跡を有効化]** を選択して、属性のグループに対する変更を追跡します。 詳細については、「[変更の追跡グループに属性を追加する方法 (マスター データ サービス)](../master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md)」を参照してください。  
  
14. **[保存]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [属性 (マスター データ サービス)](../master-data-services/attributes-master-data-services.md)   
 [属性名とデータ型を変更する &#40;マスター データ サービス&#41;](../master-data-services/change-an-attribute-name-and-data-type-master-data-services.md)   
 [ドメイン ベースの属性を作成する &#40;マスター データ サービス&#41;](../master-data-services/create-a-domain-based-attribute-master-data-services.md)   
 [ファイル属性を作成する (マスター データ サービス)](../master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
