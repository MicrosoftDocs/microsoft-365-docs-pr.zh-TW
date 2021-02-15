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
ms.openlocfilehash: 48c0b983316cfe29019d09cb20546fa4b325b3b0
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242759"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="c747b-103">在 SharePoint Syntex 中將保留標籤套用至模型</span><span class="sxs-lookup"><span data-stu-id="c747b-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="c747b-104">您可以在 Microsoft SharePoint Syntex 中輕鬆將[保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention)套用至模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="c747b-105">您可以為文件瞭解和表單處理模型都執行這個操作。</span><span class="sxs-lookup"><span data-stu-id="c747b-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="c747b-106">保留標籤讓您可以將保留設定套用至模型識別的文件。</span><span class="sxs-lookup"><span data-stu-id="c747b-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="c747b-107">例如，您希望您的模型不僅識別上傳到文件庫的任何 *保險通知* 文件，而且還要對其應用 *商務* 保留標記，以便在指定的時間段（例如，接下來的五個月）內無法從文件庫中删除這些檔案。</span><span class="sxs-lookup"><span data-stu-id="c747b-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="c747b-108">透過模型首頁上的模型設定，可以將預存的保留標籤套用至模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="c747b-109">若要讓保留標籤可以套用至您的文件瞭解模型，需要[在 Microsoft 365 合規性中心中建立並發佈它們](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="c747b-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="c747b-110">新增保留標籤至文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="c747b-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="c747b-111">從模型首頁中，選取 **[模型設定]**。</span><span class="sxs-lookup"><span data-stu-id="c747b-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="c747b-112">在 **[模型設定]** 的 **[安全性和合規性]** 部分中，選取 **[保留標籤]** 選單，以查看可用於模型的保留標籤清單。</span><span class="sxs-lookup"><span data-stu-id="c747b-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="c747b-113">![保留標籤選單](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="c747b-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="c747b-114">選取您要套用至模型的保留標籤，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c747b-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="c747b-115">將保留標籤套用至您的模型後，您可以將它套用至：</span><span class="sxs-lookup"><span data-stu-id="c747b-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="c747b-116">新增文件庫</span><span class="sxs-lookup"><span data-stu-id="c747b-116">New document library</span></span>
- <span data-ttu-id="c747b-117">已套用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="c747b-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="c747b-118">將保留標籤套用至已應用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="c747b-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="c747b-119">如果文件瞭解模型已套用至文件庫，則可以執行以下動作來同步保留標籤更新以將其套用至文件庫：</span><span class="sxs-lookup"><span data-stu-id="c747b-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="c747b-120">在模型主頁的 **[具有此模型的庫]** 部分中，選取要套用保留標籤更新的文件庫。</span><span class="sxs-lookup"><span data-stu-id="c747b-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="c747b-121">選取 **[同步處理]**。</span><span class="sxs-lookup"><span data-stu-id="c747b-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="c747b-122">![同步處理模型](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="c747b-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="c747b-123">套用更新並將其同步到模型後，可以透過執行以下動作來確認已套用更新：</span><span class="sxs-lookup"><span data-stu-id="c747b-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="c747b-124">在内容中心的 **[具有此模型的庫]** 部分中，按一下已套用更新模型的庫。</span><span class="sxs-lookup"><span data-stu-id="c747b-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="c747b-125">在您的文件庫檢視中，選取 [資訊] 圖示以檢查模型屬性。</span><span class="sxs-lookup"><span data-stu-id="c747b-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="c747b-126">在 **[使用中模型]** 清單中，選取您的更新模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="c747b-127">在 **[保留標籤]** 部分中，您會看到已套用保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="c747b-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="c747b-128">在文件庫中模型的檢視頁面上，將顯示新的 **[保留標籤]** 欄。</span><span class="sxs-lookup"><span data-stu-id="c747b-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="c747b-129">當模型對其識別為屬於其內容類型的檔案進行分類並在庫視圖中列出這些檔案時，[保留標籤] 欄還將顯示透過模型套用至它的保留標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="c747b-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="c747b-130">例如，您的模型識別的所有 *保險通知* 文件也將套用 *[商務]* 保留標籤，以防止它們在五個月內從文件庫中删除。</span><span class="sxs-lookup"><span data-stu-id="c747b-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="c747b-131">如果試圖從文件庫中删除該檔案，系統將顯示錯誤訊息，指出由於套用了保留標籤而不允許此動作。</span><span class="sxs-lookup"><span data-stu-id="c747b-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="c747b-132">將保留標籤新增至表單處理模型</span><span class="sxs-lookup"><span data-stu-id="c747b-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="c747b-133">若要讓保留標籤可以套用至您的表單處理模型，需要[在 Microsoft 365 合規性中心中建立並發佈它們](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="c747b-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="c747b-134">您可以在建立模型時將保留標籤套用至表單處理模型，或將它套用至現有模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="c747b-135">若要在您建立表單處理模型時新增保留標籤</span><span class="sxs-lookup"><span data-stu-id="c747b-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="c747b-136">當您[建立新的表單處理模型](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-form-processing-model)時，選取 [<b>進階設定</b>]。</span><span class="sxs-lookup"><span data-stu-id="c747b-136">When you are [creating a new form processing model](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-form-processing-model), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="c747b-137">在 [<b>進階設定</b>] 的 [<b>保留標籤</b>] 區段中，選取功能表，然後選取您想要套用至模型的保留標籤。</b></span><span class="sxs-lookup"><span data-stu-id="c747b-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![新增至新的表單處理模型](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="c747b-139">完成其餘模型設定之後，請選取 [<b>建立</b>] 以建立您的模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="c747b-140">將保留標籤新增至現有表單處理模型</span><span class="sxs-lookup"><span data-stu-id="c747b-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="c747b-141">您可以使用下列不同方法，將保留標籤新增至現有表單處理模型：</span><span class="sxs-lookup"><span data-stu-id="c747b-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="c747b-142">透過文件庫中的 [自動化] 功能表</span><span class="sxs-lookup"><span data-stu-id="c747b-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="c747b-143">透過文件庫中的 [使用中] 模型設定</span><span class="sxs-lookup"><span data-stu-id="c747b-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="c747b-144">透過 [自動化] 功能表將保留標籤新增至現有表單處理模型</span><span class="sxs-lookup"><span data-stu-id="c747b-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="c747b-145">您可以透過已在其中套用模型之文件庫中的 [自動化] 功能表，將保留標籤新增至您擁有的表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="c747b-146">在要將表單處理模型套用至其中的文件庫中，選取 [<b>自動化</b>] 功能表，選取 [<b>AI Builder</b>]，然後選取 [<b>檢視表單處理模型詳細資料</b>]。</span><span class="sxs-lookup"><span data-stu-id="c747b-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![自動化功能表](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="c747b-148">在模型詳細資料的 [<b>保留標籤</b>] 區段中，選取您想要套用的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="c747b-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="c747b-149">然後選取 [<b>儲存</b>]。</span><span class="sxs-lookup"><span data-stu-id="c747b-149">Then select <b>Save</b>.</span></span>

     ![新增至現有表單處理模型](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="c747b-151">若要在使用中模型設定中將保留標籤新增至現有表單處理模型</span><span class="sxs-lookup"><span data-stu-id="c747b-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="c747b-152">您可以透過已在其中套用模型之文件庫中的 [使用中] 模型設定，將保留標籤新增至您擁有的表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="c747b-153">在其中套用模型的 SharePoint 文件庫中，選取 [<b>檢視使用中模型</b>] 圖示，然後選取 [<b>檢視使用中模型</b>]。</b></span><span class="sxs-lookup"><span data-stu-id="c747b-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![檢視使用中模型](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="c747b-155">在 [<b>使用中模型</b>] 中，選取您要在其中套用保留標籤的表單處理模型。</span><span class="sxs-lookup"><span data-stu-id="c747b-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![模型詳細資料](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="c747b-157">在模型詳細資料的 [<b>保留標籤</b>] 區段中，選取您想要套用的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="c747b-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="c747b-158">然後選取 [<b>儲存</b>]。</span><span class="sxs-lookup"><span data-stu-id="c747b-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="c747b-159">您必須是模型擁有者，才能編輯模型設定窗格。</span><span class="sxs-lookup"><span data-stu-id="c747b-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="c747b-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c747b-160">See Also</span></span>
[<span data-ttu-id="c747b-161">建立分類器</span><span class="sxs-lookup"><span data-stu-id="c747b-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="c747b-162">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="c747b-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c747b-163">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="c747b-163">Document Understanding overview</span></span>](document-understanding-overview.md)


