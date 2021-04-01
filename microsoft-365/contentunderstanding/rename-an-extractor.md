---
title: 在 Microsoft SharePoint Syntex 中重新命名擷取器
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
description: 了解在 Microsoft SharePoint Syntex 中重新命名擷取器的方式及原因。
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445957"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="8a5a0-103">在 Microsoft SharePoint Syntex 中重新命名擷取器</span><span class="sxs-lookup"><span data-stu-id="8a5a0-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="8a5a0-104">有時，如果您想要以不同的名稱來指稱擷取的資料欄位，您可能需要重新命名擷取器。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="8a5a0-105">例如，貴組織決定變更其合約文件，並在文件中將「顧客」指稱為「客戶」。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="8a5a0-106">如果您在模型中擷取「顧客」欄位，您可以選擇將其重新命名為「客戶」。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="8a5a0-107">當您將更新的模型同步處理至 SharePoint 文件庫時，您的文件庫檢視中將會顯示新的「客戶」欄。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="8a5a0-108">您的檢視會保留過去活動的「顧客」欄，但會為模型所處理的所有新文件更新「客戶」欄。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="8a5a0-109">請務必將更新的模型同步處理至您先前已加以套用的文件庫，以顯示新欄名稱。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="8a5a0-110">重新命名擷取器</span><span class="sxs-lookup"><span data-stu-id="8a5a0-110">Rename an extractor</span></span>

<span data-ttu-id="8a5a0-111">請遵循下列步驟重新命名實體擷取器。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="8a5a0-112">從內容中心選取 **[模型]** 查看您的模型清單。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="8a5a0-113">在 **[模型]** 頁面的 **[名稱]** 欄中，選取要重新命名其擷取器的模型。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="8a5a0-114">在 **[實體]** 下，選取要重新命名的擷取器名稱，然後選取 **[重新命名]**。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![實體擷取器區段的螢幕擷取畫面，顯示已選取的擷取器 ，且醒目提示 [重新命名] 選項。](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="8a5a0-116">在 **[重新命名實體擷取器]** 面板：</span><span class="sxs-lookup"><span data-stu-id="8a5a0-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="8a5a0-117">a.</span><span class="sxs-lookup"><span data-stu-id="8a5a0-117">a.</span></span> <span data-ttu-id="8a5a0-118">在 **[新名稱]** 下，輸入擷取器的新名稱。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![顯示實體擷取器面板的螢幕擷取畫面。](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="8a5a0-120">b.</span><span class="sxs-lookup"><span data-stu-id="8a5a0-120">b.</span></span> <span data-ttu-id="8a5a0-121">(選用) 在 **[設定]** 下，選取您是否要相關聯現有的網站欄。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="8a5a0-122">選取 **[重新命名]**。</span><span class="sxs-lookup"><span data-stu-id="8a5a0-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a5a0-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8a5a0-123">See Also</span></span>
[<span data-ttu-id="8a5a0-124">建立擷取器</span><span class="sxs-lookup"><span data-stu-id="8a5a0-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="8a5a0-125">建立分類器</span><span class="sxs-lookup"><span data-stu-id="8a5a0-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="8a5a0-126">重新命名模型</span><span class="sxs-lookup"><span data-stu-id="8a5a0-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="8a5a0-127">說明類型</span><span class="sxs-lookup"><span data-stu-id="8a5a0-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="8a5a0-128">在建立擷取器時運用字詞庫分類法</span><span class="sxs-lookup"><span data-stu-id="8a5a0-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="8a5a0-129">文件了解概觀</span><span class="sxs-lookup"><span data-stu-id="8a5a0-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="8a5a0-130">套用模型</span><span class="sxs-lookup"><span data-stu-id="8a5a0-130">Apply a model</span></span>](apply-a-model.md) 
