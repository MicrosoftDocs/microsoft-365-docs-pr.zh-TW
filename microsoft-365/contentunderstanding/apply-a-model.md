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
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="507ea-103">在 Microsoft SharePoint Syntex 中套用檔理解模型</span><span class="sxs-lookup"><span data-stu-id="507ea-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="507ea-104">本文內容適用于 Project Cortex 私人預覽。</span><span class="sxs-lookup"><span data-stu-id="507ea-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="507ea-105">[進一步瞭解專案 Cortex](https://aka.ms/projectcortex)。</span><span class="sxs-lookup"><span data-stu-id="507ea-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="507ea-106">在發佈檔理解模型之後，您可以將它套用至 Microsoft 365 租使用者中的 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="507ea-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="507ea-107">您只能將模型套用至您具有存取權的文件庫。</span><span class="sxs-lookup"><span data-stu-id="507ea-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="507ea-108">將您的模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="507ea-108">Apply your model to a document library.</span></span>

<span data-ttu-id="507ea-109">若要將模型套用至 SharePoint 文件庫：</span><span class="sxs-lookup"><span data-stu-id="507ea-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="507ea-110">從模型首頁的 [ **將模型套用至文件庫** ] 磚上，選取 [ **發行模型**]。</span><span class="sxs-lookup"><span data-stu-id="507ea-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="507ea-111">或者，您可以選取 [**使用此模型**的文件庫中**新增文件庫**] 區段。</span><span class="sxs-lookup"><span data-stu-id="507ea-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![將模型新增至文件庫](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="507ea-113">選取包含您要套用模型之文件庫的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="507ea-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="507ea-114">如果網站未顯示在清單中，請使用搜尋方塊加以尋找。</span><span class="sxs-lookup"><span data-stu-id="507ea-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![選取網站](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="507ea-116">您必須具有您要套用模型之文件庫的「 *管理清單* 」許可權或「 *編輯* 」許可權。</span><span class="sxs-lookup"><span data-stu-id="507ea-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="507ea-117">選取網站後，請選取您要套用模型的文件庫。</span><span class="sxs-lookup"><span data-stu-id="507ea-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="507ea-118">在範例中，從*Contoso 案例追蹤*網站選取*檔*文件庫。</span><span class="sxs-lookup"><span data-stu-id="507ea-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![選取 doc 文件庫](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="507ea-120">由於模型會與內容類型相關聯，因此當您將其套用至文件庫時，它會建立內容類型的視圖，並以您已解壓縮的標籤顯示為欄。</span><span class="sxs-lookup"><span data-stu-id="507ea-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="507ea-121">這個視圖預設為文件庫的預設視圖，但是您可以選擇 [ **高級設定** ] 並取消選取 [以 **預設設定這個新的視圖**]，以選擇不讓它成為預設的視圖。</span><span class="sxs-lookup"><span data-stu-id="507ea-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![文件庫視圖](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="507ea-123">選取 [ **新增** ]，將模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="507ea-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="507ea-124">在模型首頁上，在 [ **此模型** 的文件庫] 區段中，您應該會看到所列 SharePoint 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="507ea-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![選取的文件庫](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="507ea-126">移至您的文件庫，並確定您位於模型的文件庫視圖中。</span><span class="sxs-lookup"><span data-stu-id="507ea-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="507ea-127">請注意，如果您選取文件庫名稱旁邊的 [資訊] 按鈕，便會出現一則訊息，指出您的模型已套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="507ea-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![資訊視圖](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="507ea-129">將模型套用至文件庫之後，您可以開始將檔上傳至網站並查看結果。</span><span class="sxs-lookup"><span data-stu-id="507ea-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="507ea-130">模型識別任何具有模型關聯內容類型的檔案，並在您的視圖中列出這些檔案。</span><span class="sxs-lookup"><span data-stu-id="507ea-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="507ea-131">如果您的模型有任何擷取器，則 view 會顯示每個檔案中所提取之資料的資料行。</span><span class="sxs-lookup"><span data-stu-id="507ea-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="507ea-132">將模型套用至文件庫中已存在的檔案</span><span class="sxs-lookup"><span data-stu-id="507ea-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="507ea-133">在套用的模型處理所有已上傳至文件庫的檔案之後，您也可以執行下列動作，對已存在於文件庫中的檔案執行模型，然後再執行該模型：</span><span class="sxs-lookup"><span data-stu-id="507ea-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="507ea-134">在您的文件庫中，選取您要由模型處理的檔案。</span><span class="sxs-lookup"><span data-stu-id="507ea-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="507ea-135">選取檔案之後， **分類及解壓縮** 會出現在文件庫功能區中。</span><span class="sxs-lookup"><span data-stu-id="507ea-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="507ea-136">選取 [ **分類及解壓縮**]。</span><span class="sxs-lookup"><span data-stu-id="507ea-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="507ea-137">您選取的檔案會新增至佇列進行處理。</span><span class="sxs-lookup"><span data-stu-id="507ea-137">The files you selected will be added to the queue to be processed.</span></span>

      ![分類及解壓縮](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="507ea-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="507ea-139">See Also</span></span>
[<span data-ttu-id="507ea-140">建立分類器</span><span class="sxs-lookup"><span data-stu-id="507ea-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="507ea-141">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="507ea-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="507ea-142">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="507ea-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="507ea-143">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="507ea-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
