---
title: 在 Microsoft SharePoint Syntex 中複製模型
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: 了解在 Microsoft SharePoint Syntex 中複製模型的方式及原因。
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445978"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="e8d35-103">在 Microsoft SharePoint Syntex 中複製模型</span><span class="sxs-lookup"><span data-stu-id="e8d35-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="e8d35-104">如果您需要建立新模型，且知道現有的模型與您需要的模型非常類似，則複製文件瞭解模型可以節省您的時間和精力。</span><span class="sxs-lookup"><span data-stu-id="e8d35-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="e8d35-105">例如，名為「合約」的現有模型會分類您需要處理的相同檔案。</span><span class="sxs-lookup"><span data-stu-id="e8d35-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="e8d35-106">您的新模型會擷取一些現有的資料，但需要更新以擷取一些額外的資料。</span><span class="sxs-lookup"><span data-stu-id="e8d35-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="e8d35-107">無須從頭開始建立和訓練新模型，您可以使用重複的模型功能來建立合約模型的複本，這也會複製所有相關聯的訓練項目，例如範例檔案和實體擷取程式。</span><span class="sxs-lookup"><span data-stu-id="e8d35-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="e8d35-108">當您複製模型時，重新命名模型 (例如，重新命名為「合約續約」) 之後，就可以進行更新。</span><span class="sxs-lookup"><span data-stu-id="e8d35-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="e8d35-109">例如，您可以選擇移除一些不需要的現有已擷取欄位，然後訓練模型以擷取新的欄位 (例如「續約日期」)。</span><span class="sxs-lookup"><span data-stu-id="e8d35-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="e8d35-110">複製模型</span><span class="sxs-lookup"><span data-stu-id="e8d35-110">Duplicate a model</span></span>

<span data-ttu-id="e8d35-111">請遵循下列步驟來複製文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="e8d35-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="e8d35-112">從內容中心選取 **[模型]** 查看您的模型清單。</span><span class="sxs-lookup"><span data-stu-id="e8d35-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="e8d35-113">在 **[模型]** 頁面上，選取您想要複製的模型。</span><span class="sxs-lookup"><span data-stu-id="e8d35-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="e8d35-114">使用功能區或 **[顯示動作]** 按鈕 (在模型名稱旁邊)，選取 **[複製]**。</span><span class="sxs-lookup"><span data-stu-id="e8d35-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![模型頁面的螢幕擷取畫面，其顯示選取的模型，且醒目提示 [複製] 選項。](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="e8d35-116">在 **[複製模型]** 面板：</span><span class="sxs-lookup"><span data-stu-id="e8d35-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="e8d35-117">a.</span><span class="sxs-lookup"><span data-stu-id="e8d35-117">a.</span></span> <span data-ttu-id="e8d35-118">在 **[名稱]** 下，輸入要複製之模型的新名稱。</span><span class="sxs-lookup"><span data-stu-id="e8d35-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![顯示複製模型面板的螢幕擷取畫面。](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="e8d35-120">b.</span><span class="sxs-lookup"><span data-stu-id="e8d35-120">b.</span></span> <span data-ttu-id="e8d35-121">在 **[描述]** 下，新增新模型的描述。</span><span class="sxs-lookup"><span data-stu-id="e8d35-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="e8d35-122">c.</span><span class="sxs-lookup"><span data-stu-id="e8d35-122">c.</span></span> <span data-ttu-id="e8d35-123">(選用) 在 **[進階設定]** 下，選取您是否要相關聯現有的[內容類型](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)。</span><span class="sxs-lookup"><span data-stu-id="e8d35-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="e8d35-124">選取 **[複製]**。</span><span class="sxs-lookup"><span data-stu-id="e8d35-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8d35-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e8d35-125">See Also</span></span>
[<span data-ttu-id="e8d35-126">建立分類器</span><span class="sxs-lookup"><span data-stu-id="e8d35-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="e8d35-127">重新命名模型</span><span class="sxs-lookup"><span data-stu-id="e8d35-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="e8d35-128">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="e8d35-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="e8d35-129">文件瞭解概觀</span><span class="sxs-lookup"><span data-stu-id="e8d35-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="e8d35-130">說明類型</span><span class="sxs-lookup"><span data-stu-id="e8d35-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="e8d35-131">套用模型</span><span class="sxs-lookup"><span data-stu-id="e8d35-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="e8d35-132">SharePoint Syntex 協助工具模式</span><span class="sxs-lookup"><span data-stu-id="e8d35-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)