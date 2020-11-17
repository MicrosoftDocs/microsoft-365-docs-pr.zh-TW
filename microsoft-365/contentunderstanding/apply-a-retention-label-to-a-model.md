---
title: 將保留標籤套用至文件瞭解模型
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 本文將討論如何將保留標籤套用至文件瞭解模型
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087472"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>將保留標籤套用至文件瞭解模型

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


您可以在 Microsoft SharePoint Syntex 中輕鬆套用 [保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention) 到文件瞭解模型。

保留標籤讓您可以將保留設定套用至文件瞭解模型識別的文件。  例如，您希望您的模型不僅識別上傳到文件庫的任何 *保險通知* 文件，而且還要對其應用 *商務* 保留標記，以便在指定的時間段（例如，接下來的五個月）內無法從文件庫中删除這些檔案。

頭過模型首頁上的模型設定，可以將預存的保留標籤套用至文件瞭解模型。 

> [!Important]
> 要使保留標籤套用至您的內容瞭解模型可用，需要在 [Microsoft 365 合規性中心中](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)建立並發佈它們。

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

## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)

[建立擷取器](create-an-extractor.md)

[文件瞭解概觀](document-understanding-overview.md)


