---
title: 在 Microsoft SharePoint Syntex 中將敏感度標籤套用至模型
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 本文將討論如何在 SharePoint Syntex 中將敏感度標籤套用至模型。
ms.openlocfilehash: 799ab3fa0fcdc9af9d227428056d2cd7abeaf539
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706689"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="b8ace-103">在 Microsoft SharePoint Syntex 中將敏感度標籤套用至模型</span><span class="sxs-lookup"><span data-stu-id="b8ace-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="b8ace-104">您可以在 Microsoft SharePoint Syntex 中輕鬆套用 [敏感度標籤](../compliance/sensitivity-labels.md) 到文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="b8ace-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="b8ace-105">表單處理模型尚未能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b8ace-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="b8ace-106">敏感度等級讓您可以在您的模型識別的文件中套用加密、共用及條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b8ace-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="b8ace-107">例如，您希望您的模型不僅識別將上傳到您文檔庫且包含銀行帳號或信用卡號的任何財務文件，而且還對它們套用 *加密* 敏感度標籤，以限制誰可以存取該內容以及可以如何使用它。</span><span class="sxs-lookup"><span data-stu-id="b8ace-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span>

<span data-ttu-id="b8ace-108">透過模型首頁上的模型設定，您可以將現有的敏感度標籤套用至你的模型。</span><span class="sxs-lookup"><span data-stu-id="b8ace-108">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="b8ace-109">標籤必須已發佈，並可以在模型設定中選取。</span><span class="sxs-lookup"><span data-stu-id="b8ace-109">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="b8ace-110">若要讓敏感度等級可以套用至您的文件瞭解模型，需要[在 Microsoft 365 合規性中心中建立並發佈它們](../business-video/create-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="b8ace-110">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="b8ace-111">新增保留標籤至文件瞭解模型</span><span class="sxs-lookup"><span data-stu-id="b8ace-111">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="b8ace-112">從模型首頁中，選取 **[模型設定]**。</span><span class="sxs-lookup"><span data-stu-id="b8ace-112">From the model home page, select **Model settings**.</span></span>

   ![模型頁面的螢幕擷取畫面，[模型設定] 選項已突出顯示。](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="b8ace-114">在 **[模型設定]** 窗格的 **[合規性]** 章節，選取 **[敏感度標籤]** 選單，以查看可用於模型的敏感度標籤清單。</span><span class="sxs-lookup"><span data-stu-id="b8ace-114">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![顯示敏感度標籤選單的模型設定窗格的螢幕擷取畫面。](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="b8ace-116">選取您要套用至模型的敏感度標籤，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b8ace-116">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="b8ace-117">當您在模型上套用了敏感度標籤之後，您可以將它套用至:</span><span class="sxs-lookup"><span data-stu-id="b8ace-117">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="b8ace-118">新增文件庫</span><span class="sxs-lookup"><span data-stu-id="b8ace-118">New document library</span></span>
- <span data-ttu-id="b8ace-119">已套用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="b8ace-119">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="b8ace-120">將敏感度標籤套用至已套用模型的文件庫</span><span class="sxs-lookup"><span data-stu-id="b8ace-120">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="b8ace-121">如果文件瞭解模型已套用至文件庫，則可以執行以下動作來同步敏感度標籤更新以將其套用至文件庫:</span><span class="sxs-lookup"><span data-stu-id="b8ace-121">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="b8ace-122">在模型主頁的 **[具有此模型的文件庫]** 章節，選取要套用敏感度標籤更新的文件庫。</span><span class="sxs-lookup"><span data-stu-id="b8ace-122">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="b8ace-123">選取 **[同步處理]**。</span><span class="sxs-lookup"><span data-stu-id="b8ace-123">Select **Sync**.</span></span>

   ![螢幕擷取畫面顯示了具有此模型部分的文件庫，並突出顯示了同步。](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="b8ace-125">套用更新並將其與模型同步後，可以透過執行以下動作來確認已套用更新:</span><span class="sxs-lookup"><span data-stu-id="b8ace-125">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="b8ace-126">在内容中心的 **[具有此模型的文件庫]** 章節，選取已套用更新模型的文件庫。</span><span class="sxs-lookup"><span data-stu-id="b8ace-126">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="b8ace-127">在您的文件庫檢視中，選取 [資訊] 圖示以檢查模型屬性。</span><span class="sxs-lookup"><span data-stu-id="b8ace-127">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="b8ace-128">在 **[使用中模型]** 清單中，選取您的更新模型。</span><span class="sxs-lookup"><span data-stu-id="b8ace-128">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="b8ace-129">在 **敏感度標籤** 章節，您將看得到已套用的敏感度標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="b8ace-129">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="b8ace-130">在文件庫中的模型檢視頁面上，將顯示新的 **[敏感度標籤]** 資料行。</span><span class="sxs-lookup"><span data-stu-id="b8ace-130">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="b8ace-131">當模型對其識別為屬於其內容類型的檔案進行分類，並在文件庫檢視中列出這些檔案時，**[敏感度標籤]** 資料行還將顯示透過模型套用至它的敏感度標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="b8ace-131">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="b8ace-132">例如，您的模型識別的所有財務文件也將套用 *加密* 敏感度標籤，以防止未經授權的人員存取它們。</span><span class="sxs-lookup"><span data-stu-id="b8ace-132">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="b8ace-133">如果未經授權的人員試圖從文件庫中存取該檔案，系統將顯示錯誤訊息，指出由於套用了敏感度標籤而不允許此動作。</span><span class="sxs-lookup"><span data-stu-id="b8ace-133">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="b8ace-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b8ace-134">See also</span></span>

[<span data-ttu-id="b8ace-135">套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="b8ace-135">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="b8ace-136">建立分類器</span><span class="sxs-lookup"><span data-stu-id="b8ace-136">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="b8ace-137">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="b8ace-137">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="b8ace-138">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="b8ace-138">Document Understanding overview</span></span>](document-understanding-overview.md)