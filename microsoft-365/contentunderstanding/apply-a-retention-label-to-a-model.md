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
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="2c338-103">將保留標籤套用至文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="2c338-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="2c338-104">您可以在 Microsoft SharePoint Syntex 中輕鬆套用 [保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention) 到文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="2c338-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="2c338-105">保留標籤讓您可以將保留設定套用至文件瞭解模型識別的文件。</span><span class="sxs-lookup"><span data-stu-id="2c338-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="2c338-106">例如，您希望您的模型不僅識別上傳到文件庫的任何 *保險通知* 文件，而且還要對其應用 *商務* 保留標記，以便在指定的時間段（例如，接下來的五個月）內無法從文件庫中删除這些檔案。</span><span class="sxs-lookup"><span data-stu-id="2c338-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="2c338-107">頭過模型首頁上的模型設定，可以將預存的保留標籤套用至文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="2c338-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="2c338-108">要使保留標籤套用至您的內容瞭解模型可用，需要在 [Microsoft 365 合規性中心中](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)建立並發佈它們。</span><span class="sxs-lookup"><span data-stu-id="2c338-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="2c338-109">新增保留標籤至文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="2c338-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="2c338-110">從模型首頁中，選取 **[模型設定]**。</span><span class="sxs-lookup"><span data-stu-id="2c338-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="2c338-111">在 **[模型設定]** 的 **[安全性和合規性]** 部分中，選取 **[保留標籤]** 選單，以查看可用於模型的保留標籤清單。</span><span class="sxs-lookup"><span data-stu-id="2c338-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="2c338-112">![保留標籤選單](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="2c338-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="2c338-113">選取您要套用至模型的保留標籤，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="2c338-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="2c338-114">將保留標籤套用至您的模型後，您可以將它套用至：</span><span class="sxs-lookup"><span data-stu-id="2c338-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="2c338-115">新增文件庫</span><span class="sxs-lookup"><span data-stu-id="2c338-115">New document library</span></span>
- <span data-ttu-id="2c338-116">已套用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="2c338-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="2c338-117">將保留標籤套用至已應用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="2c338-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="2c338-118">如果文件瞭解模型已套用至文件庫，則可以執行以下動作來同步保留標籤更新以將其套用至文件庫：</span><span class="sxs-lookup"><span data-stu-id="2c338-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="2c338-119">在模型主頁的 **[具有此模型的庫]** 部分中，選取要套用保留標籤更新的文件庫。</span><span class="sxs-lookup"><span data-stu-id="2c338-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="2c338-120">選取 **[同步處理]**。</span><span class="sxs-lookup"><span data-stu-id="2c338-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="2c338-121">![同步處理模型](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="2c338-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="2c338-122">套用更新並將其同步到模型後，可以透過執行以下動作來確認已套用更新：</span><span class="sxs-lookup"><span data-stu-id="2c338-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="2c338-123">在内容中心的 **[具有此模型的庫]** 部分中，按一下已套用更新模型的庫。</span><span class="sxs-lookup"><span data-stu-id="2c338-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="2c338-124">在您的文件庫檢視中，選取 [資訊] 圖示以檢查模型屬性。</span><span class="sxs-lookup"><span data-stu-id="2c338-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="2c338-125">在 **[使用中模型]** 清單中，選取您的更新模型。</span><span class="sxs-lookup"><span data-stu-id="2c338-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="2c338-126">在 **[保留標籤]** 部分中，您會看到已套用保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="2c338-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="2c338-127">在文件庫中模型的檢視頁面上，將顯示新的 **[保留標籤]** 欄。</span><span class="sxs-lookup"><span data-stu-id="2c338-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="2c338-128">當模型對其識別為屬於其內容類型的檔案進行分類並在庫視圖中列出這些檔案時，[保留標籤] 欄還將顯示透過模型套用至它的保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="2c338-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="2c338-129">例如，您的模型識別的所有 *保險通知* 文件也將套用 *[商務]* 保留標籤，以防止它們在五個月內從文件庫中删除。</span><span class="sxs-lookup"><span data-stu-id="2c338-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="2c338-130">如果試圖從文件庫中删除該檔案，系統將顯示錯誤訊息，指出由於套用了保留標籤而不允許此動作。</span><span class="sxs-lookup"><span data-stu-id="2c338-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c338-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2c338-131">See Also</span></span>
[<span data-ttu-id="2c338-132">建立分類器</span><span class="sxs-lookup"><span data-stu-id="2c338-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="2c338-133">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="2c338-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="2c338-134">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="2c338-134">Document Understanding overview</span></span>](document-understanding-overview.md)


