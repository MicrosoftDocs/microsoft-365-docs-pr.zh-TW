---
title: 將保留標籤套用至模型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 本文將討論如何在 SharePoint Syntex 中將保留標籤套用至模型
ms.openlocfilehash: 796130bfa967663b5696f49279154cfe9b16f703
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925365"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>在 SharePoint Syntex 中將保留標籤套用至模型

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


您可以在 Microsoft SharePoint Syntex 中輕鬆將[保留標籤](../compliance/retention.md)套用至模型。 您可以為文件瞭解和表單處理模型都執行這個操作。

保留標籤讓您可以將保留設定套用至模型識別的文件。  例如，您希望您的模型不僅識別上傳到文件庫的任何 *保險通知* 文件，而且還要對其應用 *商務* 保留標記，以便在指定的時間段（例如，接下來的五個月）內無法從文件庫中删除這些檔案。

透過模型首頁上的模型設定，可以將預存的保留標籤套用至模型。 

> [!Important]
> 若要讓保留標籤可以套用至您的文件瞭解模型，需要[在 Microsoft 365 合規性中心中建立並發佈它們](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)。

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>新增保留標籤至文件瞭解模型

1. 從模型首頁中，選取 **[模型設定]**。</br>
2. 在 **[模型設定]** 的 **[安全性和合規性]** 部分中，選取 **[保留標籤]** 選單，以查看可用於模型的保留標籤清單。</br>
 ![保留標籤選單](../media/content-understanding/retention-labels-menu.png)</br> 
3. 選取您要套用至模型的保留標籤，然後選取 **[儲存]**。</br>

將保留標籤套用至您的模型後，您可以將它套用至：
- 新增文件庫
- 已套用模型的文件庫
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>將保留標籤套用至已應用模型的文件庫

如果文件瞭解模型已套用至文件庫，則可以執行以下動作來同步保留標籤更新以將其套用至文件庫：</br>

1. 在模型主頁的 **[具有此模型的庫]** 部分中，選取要套用保留標籤更新的文件庫。 </br> 
2. 選取 **[同步處理]**。 </br>
 ![同步處理模型](../media/content-understanding/sync-model.png)</br> 


套用更新並將其同步到模型後，可以透過執行以下動作來確認已套用更新：

1. 在内容中心的 **[具有此模型的庫]** 部分中，按一下已套用更新模型的庫。 </br>
2. 在您的文件庫檢視中，選取 [資訊] 圖示以檢查模型屬性。</br>  
3. 在 **[使用中模型]** 清單中，選取您的更新模型。</br>
4. 在 **[保留標籤]** 部分中，您會看到已套用保留標籤的名稱。</br>


在文件庫中模型的檢視頁面上，將顯示新的 **[保留標籤]** 欄。  當模型對其識別為屬於其內容類型的檔案進行分類並在庫視圖中列出這些檔案時，[保留標籤] 欄還將顯示透過模型套用至它的保留標籤的名稱。


例如，您的模型識別的所有 *保險通知* 文件也將套用 *[商務]* 保留標籤，以防止它們在五個月內從文件庫中删除。 如果試圖從文件庫中删除該檔案，系統將顯示錯誤訊息，指出由於套用了保留標籤而不允許此動作。

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>將保留標籤新增至表單處理模型

> [!Important]
> 若要讓保留標籤可以套用至您的表單處理模型，需要[在 Microsoft 365 合規性中心中建立並發佈它們](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels)。

您可以在建立模型時將保留標籤套用至表單處理模型，或將它套用至現有模型。

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>若要在您建立表單處理模型時新增保留標籤

1. 當您[建立新的表單處理模型](./create-a-form-processing-model.md)時，選取 [<b>進階設定</b>]。
2. 在 [<b>進階設定</b>] 的 [<b>保留標籤</b>] 區段中，選取功能表，然後選取您想要套用至模型的保留標籤。</b>

 
     ![新增至新的表單處理模型](../media/content-understanding/retention-label-forms.png)</br>

3.  完成其餘模型設定之後，請選取 [<b>建立</b>] 以建立您的模型。

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>將保留標籤新增至現有表單處理模型

您可以使用下列不同方法，將保留標籤新增至現有表單處理模型：
- 透過文件庫中的 [自動化] 功能表
- 透過文件庫中的 [使用中] 模型設定 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>透過 [自動化] 功能表將保留標籤新增至現有表單處理模型

您可以透過已在其中套用模型之文件庫中的 [自動化] 功能表，將保留標籤新增至您擁有的表單處理模型。


1. 在要將表單處理模型套用至其中的文件庫中，選取 [<b>自動化</b>] 功能表，選取 [<b>AI Builder</b>]，然後選取 [<b>檢視表單處理模型詳細資料</b>]。

   ![自動化功能表](../media/content-understanding/automate-menu.png)</br>

2. 在模型詳細資料的 [<b>保留標籤</b>] 區段中，選取您想要套用的保留標籤。  然後選取 [<b>儲存</b>]。

     ![新增至現有表單處理模型](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>若要在使用中模型設定中將保留標籤新增至現有表單處理模型

您可以透過已在其中套用模型之文件庫中的 [使用中] 模型設定，將保留標籤新增至您擁有的表單處理模型。

1. 在其中套用模型的 SharePoint 文件庫中，選取 [<b>檢視使用中模型</b>] 圖示，然後選取 [<b>檢視使用中模型</b>]。</b>

   ![檢視使用中模型](../media/content-understanding/info-du.png)</br> 

2. 在 [<b>使用中模型</b>] 中，選取您要在其中套用保留標籤的表單處理模型。

     ![模型詳細資料](../media/content-understanding/retention-label-model-details.png)</br> 


3. 在模型詳細資料的 [<b>保留標籤</b>] 區段中，選取您想要套用的保留標籤。  然後選取 [<b>儲存</b>]。

> [!NOTE]
> 您必須是模型擁有者，才能編輯模型設定窗格。 


## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)

[建立擷取器](create-an-extractor.md)

[文件瞭解概觀](document-understanding-overview.md)