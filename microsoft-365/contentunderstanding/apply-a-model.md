---
title: 將文件瞭解模型套用至文件庫
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: 瞭解如何將已發佈的模型套用至 SharePoint 文件庫
ms.openlocfilehash: 0ca58e863d42d41b634978f53f55201a10a5ed93
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087484"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="8c8a0-103">在 Microsoft SharePoint Syntex 中套用文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="8c8a0-104">在發佈檔文件瞭解模型之後，您可以將它套用至 Microsoft 365 租用戶中的一或多個 SharePoint 文件庫。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="8c8a0-105">您只能將模型套用到您有權存取的文件庫。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="8c8a0-106">將您的模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-106">Apply your model to a document library.</span></span>

<span data-ttu-id="8c8a0-107">若要將您的模型套用至 SharePoint 文件庫：</span><span class="sxs-lookup"><span data-stu-id="8c8a0-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="8c8a0-108">在 [模型] 首頁的 **[將模型套用至文件庫]** 磚上，選取 **[發佈模型]**。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="8c8a0-109">或者您也可以在 **[有此模型的文件庫]** 中選取 **[+ 新增文件庫]**。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![新增模型至文件庫](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="8c8a0-111">然後您可以選取包含您要套用模型之文件庫的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="8c8a0-112">如果網站沒有顯示在清單中，請使用搜尋方塊尋找。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![選取網站](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="8c8a0-114">您必須要有您將套用模型的文件庫的 *管理清單* 權限或 *編輯* 權限。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="8c8a0-115">選取網站之後，選取您要套用模型的文件庫。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="8c8a0-116">在範例中，從 *Contoso 案列追蹤* 網站中選取 *檔案* 文件庫。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![選取文件庫](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="8c8a0-118">由於模型與內容類型相關聯，因此當您將它套用到文件庫時，會新增內容類型及其檢視，並將您所擷取的標籤顯示為欄。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="8c8a0-119">這個檢視為文件庫的預設檢視，但您也可以選擇不將它設為預設檢視，只需要選擇 **[進階設定]** ，然後取消選擇 **[將這個新檢視設為預設]** 即可。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![文件庫檢視](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="8c8a0-121">選取 **[新增]** 將模型套用到文件庫。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="8c8a0-122">在模型首頁上的 **[有此模型的文件庫]** 章節，您應該會看到列出 SharePoint 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![已選取的文件庫](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="8c8a0-124">移至您的文件庫，並確定您使用的是模型的文件庫檢視。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="8c8a0-125">請注意，如果您選取文件庫名稱旁邊的 [資訊] 按鈕，會出現一則訊息，指出您的模型已套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![資訊檢視](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="8c8a0-127">將模型套用到文件庫之後，您就可以開始將文件上傳至網站，然後查看結果。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="8c8a0-128">模型會識別任何含有模型相關內容類型的檔案，並在您的檢視中列出這些檔案。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="8c8a0-129">如果您的模型有任何擷取器，則該檢視會將您從每個檔案中擷取的資料顯示為欄。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="8c8a0-130">將模型套用至已在文件庫中的檔案</span><span class="sxs-lookup"><span data-stu-id="8c8a0-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="8c8a0-131">雖然在模型套用以後，套用的模型會處理所有上傳到文件庫的檔案，但您也可以執行下列動作，以將模型套用在文件庫中已存的檔案上：</span><span class="sxs-lookup"><span data-stu-id="8c8a0-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="8c8a0-132">在您的文件庫中，選取您希望由模型處理的檔案。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="8c8a0-133">選取檔案之後，文件庫功能區將會出現 **[分類和擷取]** 。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="8c8a0-134">選取 **[分類和擷取]**。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="8c8a0-135">您選取的檔案會新增到佇列中，以便進行處理。</span><span class="sxs-lookup"><span data-stu-id="8c8a0-135">The files you selected will be added to the queue to be processed.</span></span>

      ![分類和擷取](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="8c8a0-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8c8a0-137">See Also</span></span>
[<span data-ttu-id="8c8a0-138">建立分類器</span><span class="sxs-lookup"><span data-stu-id="8c8a0-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="8c8a0-139">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="8c8a0-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="8c8a0-140">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="8c8a0-140">Document Understanding overview</span></span>](document-understanding-overview.md)


