---
title: 將保留標籤套用至檔理解模型
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 本文討論如何將保留標籤套用至檔理解模型
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294915"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>將保留標籤套用至檔理解模型

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

您可以輕鬆地將 [保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention) 套用至 Microsoft SharePoint Syntex 中的檔理解模型。

保留標籤可讓您將保留設定套用至檔理解模型所識別的檔。  例如，您的模型不只識別任何上傳至文件庫的 *保險通知* 檔，也可以對其套用 *商務* 保留標記，如此一來，您就無法從文件庫中刪除這些檔， (接下來的五個月內，例如) 。

您可以透過模型首頁上的模型設定，將預先存在的保留標籤套用至檔理解模型。 

> [!Important]
> 若要將保留標籤套用至內容理解模型，必須 [在 Microsoft 365 規範中心建立併發布](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)這些標籤。

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>若要將保留標籤新增至檔理解模型

1. 從模型的首頁中，選取 [ **模型設定**]。</br>
2. 在 [ **模型設定**] 的 [ **安全性與規範** ] 區段中，選取 [ **保留標籤** ] 功能表，以查看適用于模型的保留標籤清單。</br>
 ![保留標籤功能表](../media/content-understanding/retention-labels-menu.png)</br> 
3. 選取您要套用到模型的保留標籤，然後選取 [ **儲存**]。</br>

將保留標籤套用至模型之後，您可以將它套用至：
- 新文件庫
- 已套用模型的文件庫
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>將保留標籤套用至已套用模型的文件庫

如果您的檔理解模型已套用至文件庫，您可以執行下列動作來同步保留標籤更新，以將其套用至文件庫：</br>

1. 在您的模型首頁上，選取 [ **包含此模型** 的文件庫] 區段中，選取您要套用保留標籤更新的文件庫。 </br> 
2. 選取 [ **同步**處理]。 </br>
 ![同步模型](../media/content-understanding/sync-model.png)</br> 


套用更新並同步處理至您的模型之後，您可以執行下列動作，確認已套用此更新：

1. 在內容中心的 [ **包含此模型** 的文件庫] 區段中，按一下要套用更新的模型所在的文件庫。 </br>
2. 在您的文件庫視圖中，選取 [資訊] 圖示以檢查模型屬性。</br>  
3. 在 [ **現用模型** ] 清單中，選取您更新的模型。</br>
4. 在 [ **保留標籤** ] 區段中，您將會看到已套用之保留標籤的名稱。</br>


在您的模型視圖頁面上的文件庫中，會顯示新的 **保留標籤** 欄。  當您的模型將其識別為屬於其內容類型的檔案，並將這些檔案列于文件庫視圖中時，[保留標籤] 欄也會顯示透過模型套用至該標籤的保留標籤名稱。


例如，您模型所識別的所有 *保險通知* 檔也會有套用 *商務* 保留標籤，以防從文件庫中刪除五個月。 如果嘗試刪除文件庫中的檔案，則會顯示錯誤，指出由於已套用的保留標籤，因此不允許這樣做。

## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)</br>
[建立提取程式](create-an-extractor.md)</br>
[檔理解概述](document-understanding-overview.md)</br>
[建立表單處理模型](create-a-form-processing-model.md)  
