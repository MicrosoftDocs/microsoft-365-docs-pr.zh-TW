---
title: '將檔理解模型套用至文件庫 (預覽) '
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解如何將已發佈的模型套用至 SharePoint 文件庫。
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950245"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="2dbb8-103">套用檔理解模型 (預覽) </span><span class="sxs-lookup"><span data-stu-id="2dbb8-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="2dbb8-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="2dbb8-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="2dbb8-106">在發佈檔理解模型之後，您可以將它套用至 Microsoft 365 租使用者中的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="2dbb8-107">您只能將模型套用至您具有存取權的文件庫。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="2dbb8-108">將您的模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-108">Apply your model to a document library.</span></span>

<span data-ttu-id="2dbb8-109">若要將模型套用至 SharePoint 文件庫：</span><span class="sxs-lookup"><span data-stu-id="2dbb8-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="2dbb8-110">在模型首頁上，在 [ **將模型套用至文件庫** ] 磚上，選取 [ **發行模型**]。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="2dbb8-111">或者，您可以選取 [**使用此模型**的文件庫中**新增文件庫**] 區段。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![將模型新增至文件庫](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="2dbb8-113">然後，您可以選取包含您要套用模型之文件庫的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="2dbb8-114">如果網站未顯示在清單中，請使用搜尋方塊加以尋找。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![選取網站](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="2dbb8-116">您必須具有您要套用模型之文件庫的「 *管理清單* 」許可權或「 *編輯* 」許可權。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="2dbb8-117">選取網站後，您必須選取要套用模型的文件庫。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="2dbb8-118">在此範例中，我們會從*Contoso 案例追蹤*網站選取*檔*文件庫。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![選取 doc 文件庫](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="2dbb8-120">由於模型會與內容類型相關聯，因此當您將其套用至文件庫時，它會建立內容類型的視圖，並以您已解壓縮的標籤顯示為欄。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="2dbb8-121">這個視圖預設會是文件庫的預設視圖，但是您可以選擇 [ **高級設定** ] 並取消選取 [ **將這個新的視圖設定為預設**值]，以選擇不讓它成為預設的視圖。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![文件庫視圖](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="2dbb8-123">選取 [ **新增** ]，將模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="2dbb8-124">在模型首頁上，在 [ **此模型** 的文件庫] 區段中，您會看到所列 SharePoint 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![文件庫視圖](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="2dbb8-126">移至您的文件庫，並確定您位於模型的文件庫視圖中。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="2dbb8-127">請注意，如果您選取文件庫名稱旁邊的 [資訊] 按鈕，會出現一則訊息，指出您的模型已套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![文件庫視圖](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="2dbb8-129">將模型套用至文件庫之後，您可以開始將檔上傳至網站並查看結果。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="2dbb8-130">模型會識別任何具有模型關聯內容類型的檔案，並將這些檔案列在您的視圖中。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="2dbb8-131">如果您的模型有任何擷取器，則 view 會顯示您要從每個檔案提取之資料的欄。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="2dbb8-132">將模型套用至文件庫中已存在的檔案</span><span class="sxs-lookup"><span data-stu-id="2dbb8-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="2dbb8-133">雖然套用的模型會處理所有檔案上傳至文件庫之後，您也可以執行下列動作，針對已存在於文件庫中的檔案執行模型，然後再執行該模型：</span><span class="sxs-lookup"><span data-stu-id="2dbb8-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="2dbb8-134">在您的文件庫中，選取您要由模型處理的檔案。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="2dbb8-135">選取檔案之後， **分類及解壓縮** 會出現在文件庫功能區中。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="2dbb8-136">選取 [ **分類及解壓縮**]。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="2dbb8-137">您選取的檔案會新增至佇列進行處理。</span><span class="sxs-lookup"><span data-stu-id="2dbb8-137">The files you selected will be added to the queue to be processed.</span></span>

      ![分類及解壓縮](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="2dbb8-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2dbb8-139">See Also</span></span>
[<span data-ttu-id="2dbb8-140">建立分類器</span><span class="sxs-lookup"><span data-stu-id="2dbb8-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="2dbb8-141">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="2dbb8-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="2dbb8-142">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="2dbb8-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="2dbb8-143">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="2dbb8-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




