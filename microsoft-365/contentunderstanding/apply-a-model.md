---
title: 將檔理解模型套用至文件庫
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何將已發佈的模型套用至 SharePoint 文件庫
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295487"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中套用檔理解模型

本文內容適用于 Project Cortex 私人預覽。 [進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

在發佈檔理解模型之後，您可以將它套用至 Microsoft 365 租使用者中的 SharePoint 文件庫。

> [!NOTE]
> 您只能將模型套用至您具有存取權的文件庫。


## <a name="apply-your-model-to-a-document-library"></a>將您的模型套用至文件庫。

若要將模型套用至 SharePoint 文件庫：

1. 從模型首頁的 [ **將模型套用至文件庫** ] 磚上，選取 [ **發行模型**]。 或者，您可以選取 [**使用此模型**的文件庫中**新增文件庫**] 區段。 </br>

    ![將模型新增至文件庫](../media/content-understanding/apply-to-library.png)</br>

2. 選取包含您要套用模型之文件庫的 SharePoint 網站。 如果網站未顯示在清單中，請使用搜尋方塊加以尋找。</br>

    ![選取網站](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > 您必須具有您要套用模型之文件庫的「 *管理清單* 」許可權或「 *編輯* 」許可權。</br>

3. 選取網站後，請選取您要套用模型的文件庫。 在範例中，從*Contoso 案例追蹤*網站選取*檔*文件庫。</br>

    ![選取 doc 文件庫](../media/content-understanding/select-doc-library.png)</br>

4. 由於模型會與內容類型相關聯，因此當您將其套用至文件庫時，它會建立內容類型的視圖，並以您已解壓縮的標籤顯示為欄。 這個視圖預設為文件庫的預設視圖，但是您可以選擇 [ **高級設定** ] 並取消選取 [以 **預設設定這個新的視圖**]，以選擇不讓它成為預設的視圖。</br>

    ![文件庫視圖](../media/content-understanding/library-view.png)</br>

5. 選取 [ **新增** ]，將模型套用至文件庫。 
6. 在模型首頁上，在 [ **此模型** 的文件庫] 區段中，您應該會看到所列 SharePoint 網站的 URL。</br>

    ![選取的文件庫](../media/content-understanding/selected-library.png)</br>

7. 移至您的文件庫，並確定您位於模型的文件庫視圖中。 請注意，如果您選取文件庫名稱旁邊的 [資訊] 按鈕，便會出現一則訊息，指出您的模型已套用至文件庫。

    ![資訊視圖](../media/content-understanding/info-du.png)</br> 


將模型套用至文件庫之後，您可以開始將檔上傳至網站並查看結果。

模型識別任何具有模型關聯內容類型的檔案，並在您的視圖中列出這些檔案。 如果您的模型有任何擷取器，則 view 會顯示每個檔案中所提取之資料的資料行。

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>將模型套用至文件庫中已存在的檔案

在套用的模型處理所有已上傳至文件庫的檔案之後，您也可以執行下列動作，對已存在於文件庫中的檔案執行模型，然後再執行該模型：

1. 在您的文件庫中，選取您要由模型處理的檔案。
2. 選取檔案之後， **分類及解壓縮** 會出現在文件庫功能區中。 選取 [ **分類及解壓縮**]。
3. 您選取的檔案會新增至佇列進行處理。

      ![分類及解壓縮](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)</br>
[建立提取程式](create-an-extractor.md)</br>
[檔理解概述](document-understanding-overview.md)</br>
[建立表單處理模型](create-a-form-processing-model.md)  
