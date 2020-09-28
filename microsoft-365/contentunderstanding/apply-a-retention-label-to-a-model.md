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
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="342d8-103">將保留標籤套用至檔理解模型</span><span class="sxs-lookup"><span data-stu-id="342d8-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="342d8-104">您可以輕鬆地將 [保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention) 套用至 Microsoft SharePoint Syntex 中的檔理解模型。</span><span class="sxs-lookup"><span data-stu-id="342d8-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="342d8-105">保留標籤可讓您將保留設定套用至檔理解模型所識別的檔。</span><span class="sxs-lookup"><span data-stu-id="342d8-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="342d8-106">例如，您的模型不只識別任何上傳至文件庫的 *保險通知* 檔，也可以對其套用 *商務* 保留標記，如此一來，您就無法從文件庫中刪除這些檔， (接下來的五個月內，例如) 。</span><span class="sxs-lookup"><span data-stu-id="342d8-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="342d8-107">您可以透過模型首頁上的模型設定，將預先存在的保留標籤套用至檔理解模型。</span><span class="sxs-lookup"><span data-stu-id="342d8-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="342d8-108">若要將保留標籤套用至內容理解模型，必須 [在 Microsoft 365 規範中心建立併發布](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)這些標籤。</span><span class="sxs-lookup"><span data-stu-id="342d8-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="342d8-109">若要將保留標籤新增至檔理解模型</span><span class="sxs-lookup"><span data-stu-id="342d8-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="342d8-110">從模型的首頁中，選取 [ **模型設定**]。</span><span class="sxs-lookup"><span data-stu-id="342d8-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="342d8-111">在 [ **模型設定**] 的 [ **安全性與規範** ] 區段中，選取 [ **保留標籤** ] 功能表，以查看適用于模型的保留標籤清單。</span><span class="sxs-lookup"><span data-stu-id="342d8-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="342d8-112">![保留標籤功能表](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="342d8-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="342d8-113">選取您要套用到模型的保留標籤，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="342d8-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="342d8-114">將保留標籤套用至模型之後，您可以將它套用至：</span><span class="sxs-lookup"><span data-stu-id="342d8-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="342d8-115">新文件庫</span><span class="sxs-lookup"><span data-stu-id="342d8-115">New document library</span></span>
- <span data-ttu-id="342d8-116">已套用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="342d8-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="342d8-117">將保留標籤套用至已套用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="342d8-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="342d8-118">如果您的檔理解模型已套用至文件庫，您可以執行下列動作來同步保留標籤更新，以將其套用至文件庫：</span><span class="sxs-lookup"><span data-stu-id="342d8-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="342d8-119">在您的模型首頁上，選取 [ **包含此模型** 的文件庫] 區段中，選取您要套用保留標籤更新的文件庫。</span><span class="sxs-lookup"><span data-stu-id="342d8-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="342d8-120">選取 [ **同步**處理]。</span><span class="sxs-lookup"><span data-stu-id="342d8-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="342d8-121">![同步模型](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="342d8-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="342d8-122">套用更新並同步處理至您的模型之後，您可以執行下列動作，確認已套用此更新：</span><span class="sxs-lookup"><span data-stu-id="342d8-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="342d8-123">在內容中心的 [ **包含此模型** 的文件庫] 區段中，按一下要套用更新的模型所在的文件庫。</span><span class="sxs-lookup"><span data-stu-id="342d8-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="342d8-124">在您的文件庫視圖中，選取 [資訊] 圖示以檢查模型屬性。</span><span class="sxs-lookup"><span data-stu-id="342d8-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="342d8-125">在 [ **現用模型** ] 清單中，選取您更新的模型。</span><span class="sxs-lookup"><span data-stu-id="342d8-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="342d8-126">在 [ **保留標籤** ] 區段中，您將會看到已套用之保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="342d8-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="342d8-127">在您的模型視圖頁面上的文件庫中，會顯示新的 **保留標籤** 欄。</span><span class="sxs-lookup"><span data-stu-id="342d8-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="342d8-128">當您的模型將其識別為屬於其內容類型的檔案，並將這些檔案列于文件庫視圖中時，[保留標籤] 欄也會顯示透過模型套用至該標籤的保留標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="342d8-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="342d8-129">例如，您模型所識別的所有 *保險通知* 檔也會有套用 *商務* 保留標籤，以防從文件庫中刪除五個月。</span><span class="sxs-lookup"><span data-stu-id="342d8-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="342d8-130">如果嘗試刪除文件庫中的檔案，則會顯示錯誤，指出由於已套用的保留標籤，因此不允許這樣做。</span><span class="sxs-lookup"><span data-stu-id="342d8-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="342d8-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="342d8-131">See Also</span></span>
[<span data-ttu-id="342d8-132">建立分類器</span><span class="sxs-lookup"><span data-stu-id="342d8-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="342d8-133">建立提取程式</span><span class="sxs-lookup"><span data-stu-id="342d8-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="342d8-134">檔理解概述</span><span class="sxs-lookup"><span data-stu-id="342d8-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="342d8-135">建立表單處理模型</span><span class="sxs-lookup"><span data-stu-id="342d8-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
