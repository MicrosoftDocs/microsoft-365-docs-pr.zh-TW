---
title: 將文件瞭解模型套用至文件庫
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 瞭解如何將已發佈的模型套用至 SharePoint 文件庫
ms.openlocfilehash: 771b0f451d404c6e90f62091ca466bfaf34bae39
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338670"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>在 Microsoft SharePoint Syntex 中套用文件瞭解模型。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

在發佈檔文件瞭解模型之後，您可以將它套用至 Microsoft 365 租用戶中的一或多個 SharePoint 文件庫。

> [!NOTE]
> 您只能將模型套用到您有權存取的文件庫。


## <a name="apply-your-model-to-a-document-library"></a>將您的模型套用至文件庫。

若要將您的模型套用至 SharePoint 文件庫：

1. 在 [模型] 首頁的 **[將模型套用至文件庫]** 磚上，選取 **[發佈模型]**。 或者您也可以在 **[有此模型的文件庫]** 中選取 **[+ 新增文件庫]**。 </br>

    ![新增模型至文件庫](../media/content-understanding/apply-to-library.png)</br>

2. 然後您可以選取包含您要套用模型之文件庫的 SharePoint 網站。 如果網站沒有顯示在清單中，請使用搜尋方塊尋找。</br>

    ![選取網站](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > 您必須要有您將套用模型的文件庫的*管理清單*權限或*編輯*權限。</br>

3. 選取網站之後，選取您要套用模型的文件庫。 在範例中，從 *Contoso 案列追蹤*網站中選取*檔案* 文件庫。</br>

    ![選取文件庫](../media/content-understanding/select-doc-library.png)</br>

4. 由於模型與內容類型相關聯，因此當您將它套用到文件庫時，會新增內容類型及其檢視，並將您所擷取的標籤顯示為欄。 這個檢視為文件庫的預設檢視，但您也可以選擇不將它設為預設檢視，只需要選擇 **[進階設定]** ，然後取消選擇 **[將這個新檢視設為預設]** 即可。</br>

    ![文件庫檢視](../media/content-understanding/library-view.png)</br>

5. 選取 **[新增]** 將模型套用到文件庫。 
6. 在模型首頁上的 **[有此模型的文件庫]** 章節，您應該會看到列出 SharePoint 網站的 URL。</br>

    ![已選取的文件庫](../media/content-understanding/selected-library.png)</br>

7. 移至您的文件庫，並確定您使用的是模型的文件庫檢視。 請注意，如果您選取文件庫名稱旁邊的 [資訊] 按鈕，會出現一則訊息，指出您的模型已套用至文件庫。

    ![資訊檢視](../media/content-understanding/info-du.png)</br> 


將模型套用到文件庫之後，您就可以開始將文件上傳至網站，然後查看結果。

模型會識別任何含有模型相關內容類型的檔案，並在您的檢視中列出這些檔案。 如果您的模型有任何擷取器，則該檢視會將您從每個檔案中擷取的資料顯示為欄。

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>將模型套用至已在文件庫中的檔案

雖然在模型套用以後，套用的模型會處理所有上傳到文件庫的檔案，但您也可以執行下列動作，以將模型套用在文件庫中已存的檔案上：

1. 在您的文件庫中，選取您希望由模型處理的檔案。
2. 選取檔案之後，文件庫功能區將會出現 **[分類和擷取]** 。 選取 **[分類和擷取]**。
3. 您選取的檔案會新增到佇列中，以便進行處理。

      ![分類和擷取](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>另請參閱
[建立分類器](create-a-classifier.md)

[建立擷取器](create-an-extractor.md)

[文件瞭解概觀](document-understanding-overview.md)


