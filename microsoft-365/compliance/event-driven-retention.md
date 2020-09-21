---
title: 事件發生時，開始保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: 通常為記錄管理解決方案的一部分，您可以設定保留標籤，以根據您發現的事件來啟動保留期間。
ms.openlocfilehash: 1572995909f370c5c3a544cb3f85e20c35629f88
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816874"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="43fea-103">事件發生時，開始保留</span><span class="sxs-lookup"><span data-stu-id="43fea-103">Start retention when an event occurs</span></span>

><span data-ttu-id="43fea-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="43fea-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="43fea-p101">當您保留內容時，保留期間通常是依據內容的存留期。例如，您在文件建立之後保留 7 年，然後刪除。但當您設定[保留標籤](retention.md#retention-labels)，您也可以讓發生特定類型事件的時間作為保留期間的依據。事件會觸發啟動保留期間，有保留標籤套用至該類型事件的所有內容，都會強制執行標籤的保留動作。</span><span class="sxs-lookup"><span data-stu-id="43fea-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="43fea-109">使用事件型保留的範例：</span><span class="sxs-lookup"><span data-stu-id="43fea-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="43fea-110">**員工離開組織** 假設員工記錄必須從員工離開組織起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="43fea-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="43fea-111">經過 10 年之後，所有與該名員工相關的雇用、績效和離職文件都必須加以處置。</span><span class="sxs-lookup"><span data-stu-id="43fea-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="43fea-112">會觸發 10 年保留期間的事件是員工離開組織。</span><span class="sxs-lookup"><span data-stu-id="43fea-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="43fea-113">**合約到期** 假設與合約相關的所有記錄必須從合約到期時間起保留五年。</span><span class="sxs-lookup"><span data-stu-id="43fea-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="43fea-114">會觸發五年保留期間的事件是合約到期。</span><span class="sxs-lookup"><span data-stu-id="43fea-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="43fea-p104">**產品生命週期**貴組織可能有與產品最後製造日期相關的保留需求，例如技術規格。在此情況下，最後製造日期是觸發保留期間的事件。</span><span class="sxs-lookup"><span data-stu-id="43fea-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="43fea-p105">事件型保留通常作為記錄管理處理程序的一部分。這表示：</span><span class="sxs-lookup"><span data-stu-id="43fea-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="43fea-119">依保留事件標示的標籤通常也會將項目標記成一個資料列，為記錄管理解決方案的其中一部分。</span><span class="sxs-lookup"><span data-stu-id="43fea-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="43fea-120">如需詳細資訊，請參閱[了解記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="43fea-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="43fea-121">已宣告為記錄但是其事件觸發程序尚未發生的文件，會無限期保留 (記錄無法永久刪除)，直到事件觸發該文件的保留期間。</span><span class="sxs-lookup"><span data-stu-id="43fea-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="43fea-122">根據事件的保留標籤通常會在保留期間結束時觸發處置檢閱，這樣記錄管理員就能手動檢閱並處置內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="43fea-123">如需詳細資訊，請參閱[處置內容](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="43fea-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="43fea-124">根據事件的保留標籤與 Microsoft 365 中任何保留標籤具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="43fea-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="43fea-125">如需詳細資訊，請參閱[瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="43fea-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="43fea-126">了解事件類型、標籤、事件和資產識別碼之間的關聯性</span><span class="sxs-lookup"><span data-stu-id="43fea-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="43fea-127">若要成功使用事件型保留，請務必了解事件類型、保留標籤、事件和資產識別碼之間的關聯性，如下列圖表所示且圖表後有說明：</span><span class="sxs-lookup"><span data-stu-id="43fea-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![圖表 1/2：事件類型、標籤、事件和資產識別碼](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![圖表 2/2：事件類型、標籤、事件和資產識別碼](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="43fea-130">您為各種類型的內容建立保留標籤，然後將其與某種事件類型建立關聯。</span><span class="sxs-lookup"><span data-stu-id="43fea-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="43fea-131">例如，不同類型產品檔案和記錄的保留標籤會與名為「產品生命週期」的事件類型相關聯，因為這些記錄必須從產品達到其生命週期結束開始保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="43fea-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="43fea-132">使用者 (通常是記錄管理員) 會將這些保留標籤套用到內容，並且 (若是 SharePoint 和 OneDrive 中的文件) 為每個項目輸入資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="43fea-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="43fea-133">在此範例中，資產識別碼是組織所使用的產品名稱或代碼。</span><span class="sxs-lookup"><span data-stu-id="43fea-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="43fea-134">然後，每個產品的記錄都會獲派一個保留標籤，而每筆記錄都會有包含資產識別碼的屬性。</span><span class="sxs-lookup"><span data-stu-id="43fea-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="43fea-135">此圖表描繪組織中所有產品記錄的**所有內容**，而每個項目都會承載記錄所屬產品的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="43fea-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="43fea-p111">產品生命週期是事件類型；達到生命週期結尾的特定產品是事件。該事件類型的事件發生時 - 在此情況下，當產品達到其生命週期結尾時 - 您建立事件，指定：</span><span class="sxs-lookup"><span data-stu-id="43fea-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="43fea-138">資產識別碼 (適用於 SharePoint 和 OneDrive 文件)</span><span class="sxs-lookup"><span data-stu-id="43fea-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="43fea-p112">關鍵字 (適用於 Exchange 項目)。在此範例中，組織在包含產品記錄的訊息中使用產品代碼，因此 Exchange 項目的關鍵字與 SharePoint 和 OneDrive 文件中的資產識別碼功能相同。</span><span class="sxs-lookup"><span data-stu-id="43fea-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="43fea-p113">發生事件的日期。此日期作為保留期間的開始日期。此日期可能是目前、過去或未來的日期。</span><span class="sxs-lookup"><span data-stu-id="43fea-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="43fea-144">建立事件之後，該事件日期會同步處理到保留標籤屬於該事件類型的所有內容，以及包含指定資產識別碼或關鍵字的所有內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="43fea-145">如同任何保留標籤，同步處理最多可能需要七天。</span><span class="sxs-lookup"><span data-stu-id="43fea-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="43fea-146">上圖中以紅色圈出的所有項目，其保留期間都是由此事件觸發。</span><span class="sxs-lookup"><span data-stu-id="43fea-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="43fea-147">換句話說，當這項產品的生命週期結束時，該事件會觸發該產品記錄的保留期間。</span><span class="sxs-lookup"><span data-stu-id="43fea-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="43fea-148">請務必了解，如果您沒有為事件指定資產識別碼或關鍵字，則保留標籤屬於該事件類型的**所有內容**都將有由該事件觸發的保留期間。</span><span class="sxs-lookup"><span data-stu-id="43fea-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="43fea-149">這表示在上圖中，所有內容都會開始進行保留。</span><span class="sxs-lookup"><span data-stu-id="43fea-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="43fea-150">這可能不是您原本的打算。</span><span class="sxs-lookup"><span data-stu-id="43fea-150">This might not be what you intend.</span></span>

<span data-ttu-id="43fea-151">最後，請記住，每個保留標籤都有自己的保留設定。</span><span class="sxs-lookup"><span data-stu-id="43fea-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="43fea-152">在此範例中，全都指定 10 年，但有可能事件觸發的保留標籤是每個標籤都有不同的保留期間。</span><span class="sxs-lookup"><span data-stu-id="43fea-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="43fea-153">如何設定事件導向保留</span><span class="sxs-lookup"><span data-stu-id="43fea-153">How to set up event-driven retention</span></span>

<span data-ttu-id="43fea-154">事件導向保留的整體工作流程：</span><span class="sxs-lookup"><span data-stu-id="43fea-154">High-level workflow for event-driven retention:</span></span>
  
![設定事件導向保留工作流程的圖表](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="43fea-156">請參閱 [使用保留標籤來管理儲存在 SharePoint 中的文件生命週期](auto-apply-retention-labels-scenario.md)，以瞭解如何在 SharePoint 中使用管理屬性以自動套用保留標籤及實施事件導向保留。</span><span class="sxs-lookup"><span data-stu-id="43fea-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="43fea-157">步驟 1：建立其保留期間根據事件的標籤</span><span class="sxs-lookup"><span data-stu-id="43fea-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="43fea-158">若要建立和設定保留標籤，請使用 [創建和設定保留標籤](create-retention-labels.md#create-and-configure-retention-labels)中的指示。</span><span class="sxs-lookup"><span data-stu-id="43fea-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels).</span></span> <span data-ttu-id="43fea-159">但特定於事件型的保留，在 [建立保留標籤] 精靈的 **[定義保留設定]** 頁上，在啟動 **[開始保留期依據]** 後，從下拉清單中選取一種預設事件類型，或透過選取 **[建立新事件類型]** 來建立自己的事件類型：</span><span class="sxs-lookup"><span data-stu-id="43fea-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![建立保留標籤的新事件類型](../media/SPRetention6.png)

<span data-ttu-id="43fea-161">事件類型只是您要讓保留標籤與事件建立關聯之事件的一般描述。</span><span class="sxs-lookup"><span data-stu-id="43fea-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="43fea-162">預設事件類型在下拉清單中的名稱後面有 **(event type)** 以便於識別，您還可以從 **[記錄管理]** > \*\* [事件] 索引標籤\*\* > **[管理事件類型]** 中查看和建立事件類型。</span><span class="sxs-lookup"><span data-stu-id="43fea-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="43fea-163">事件型保留需要保留設定：</span><span class="sxs-lookup"><span data-stu-id="43fea-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="43fea-164">保留內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-164">Retain the content.</span></span>
    
- <span data-ttu-id="43fea-165">自動刪除內容或在保留期間結束時觸發處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="43fea-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="43fea-166">事件型的保留通常是用於作為記錄的內容，因此很適合用來檢查您是否也需要選取將內容標示為[記錄](records-management.md#records)的選項。</span><span class="sxs-lookup"><span data-stu-id="43fea-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="43fea-167">如果您正在使用現有的事件類型，而非建立新的事件類型，請跳到步驟 3。</span><span class="sxs-lookup"><span data-stu-id="43fea-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="43fea-168">在您選擇事件類型並儲存保留標籤之後，就無法變更事件類型。</span><span class="sxs-lookup"><span data-stu-id="43fea-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="43fea-169">步驟 2：建立你的標籤的新事件類型</span><span class="sxs-lookup"><span data-stu-id="43fea-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="43fea-170">針對保留設定，如果選取 **[建立新事件類型]**，請輸入事件類型的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="43fea-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="43fea-171">然後選取 **[下一個]**、 **[提交]** 和 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="43fea-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="43fea-172">回到 **[定義保留設定]** 頁面，使用下拉清單選取您建立的事件類型作為 **[開始保留期依據]**。</span><span class="sxs-lookup"><span data-stu-id="43fea-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="43fea-173">步驟 3：發佈或自動套用事件型保留標籤</span><span class="sxs-lookup"><span data-stu-id="43fea-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="43fea-174">和任何保留標籤一樣，您必須發佈或自動套用事件型標籤，以使標籤可以手動或自動套用到內容中：</span><span class="sxs-lookup"><span data-stu-id="43fea-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="43fea-175">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="43fea-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="43fea-176">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="43fea-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="43fea-177">步驟 4：輸入資產識別碼</span><span class="sxs-lookup"><span data-stu-id="43fea-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="43fea-178">在事件型標籤套用到內容之後，您可以輸入每個項目的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="43fea-178">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="43fea-179">例如，貴組織可能使用：</span><span class="sxs-lookup"><span data-stu-id="43fea-179">For example, your organization might use:</span></span>
  
- <span data-ttu-id="43fea-180">產品代碼，您可以用來保留僅限特定產品的內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="43fea-181">專案代碼，您可以用來保留僅限特定專案的內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="43fea-182">員工識別碼，您可以用來保留僅限特定人員的內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="43fea-183">資產識別碼只是 SharePoint 和 OneDrive 中可用的另一個文件屬性。</span><span class="sxs-lookup"><span data-stu-id="43fea-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="43fea-184">貴組織可能已經使用其他文件屬性和識別碼來分類內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="43fea-185">若是如此，您也可以在建立事件時使用這些屬性和值，請參閱後續的步驟 6。</span><span class="sxs-lookup"><span data-stu-id="43fea-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="43fea-186">重點是，您必須在文件屬性中使用一些 *property:value* 組合，以將該項目與事件類型建立關聯。</span><span class="sxs-lookup"><span data-stu-id="43fea-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![在其中輸入資產識別碼的文字方塊](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="43fea-188">步驟 5：建立事件</span><span class="sxs-lookup"><span data-stu-id="43fea-188">Step 5: Create an event</span></span>

<span data-ttu-id="43fea-189">發生該事件類型的特定執行個體時，例如，產品達到其生命週期的結尾，請移至 Microsoft 365 合規性中心的 **[記錄管理]**  >  **[事件]** 頁面，然後選取 **+ 建立**以建立事件。</span><span class="sxs-lookup"><span data-stu-id="43fea-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="43fea-190">您可以在此處建立事件來觸發事件。</span><span class="sxs-lookup"><span data-stu-id="43fea-190">You trigger the event by creating it, here.</span></span>

![建立活動以觸發事件型的保留標籤的保留開始時間](../media/create-event-records-management.png)


### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="43fea-192">步驟 6：選擇與步驟 2 中的標籤所使用相同的事件類型</span><span class="sxs-lookup"><span data-stu-id="43fea-192">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="43fea-193">當您建立事件時，請選擇步驟 2 中保留標籤設定所指定的相同事件類型。</span><span class="sxs-lookup"><span data-stu-id="43fea-193">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="43fea-194">例如，如果為標籤設定選取了 **[產品生命週期]** 作為事件類型，請在建立事件時選取 **[產品生命週期]**。</span><span class="sxs-lookup"><span data-stu-id="43fea-194">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="43fea-195">只有已套用該事件類型保留標籤的內容會觸發其保留期間。</span><span class="sxs-lookup"><span data-stu-id="43fea-195">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![在事件設定中選擇事件類型的選項](../media/choose-event-type-records-management.png)

<span data-ttu-id="43fea-197">或者，如果您需要為具有不同事件類型的多個保留標籤建立事件，請選取 **[選擇現有標籤]** 選項。</span><span class="sxs-lookup"><span data-stu-id="43fea-197">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="43fea-198">然後，選取您要與這個事件相關聯之事件類型設定的標籤。</span><span class="sxs-lookup"><span data-stu-id="43fea-198">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="43fea-199">步驟 7：輸入關鍵字或資產識別碼</span><span class="sxs-lookup"><span data-stu-id="43fea-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="43fea-200">現在您可以指定 SharePoint 和 OneDrive 內容的資產識別碼或 Exchange 內容的關鍵字，藉此縮小內容的範圍。</span><span class="sxs-lookup"><span data-stu-id="43fea-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="43fea-201">針對資產識別碼，只有在具有指定 *property:value* 組的內容上才會強制執行保留。</span><span class="sxs-lookup"><span data-stu-id="43fea-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="43fea-202">若未輸入資產識別碼，具有該事件類型之標籤的所有內容都會套用相同的保留日期。</span><span class="sxs-lookup"><span data-stu-id="43fea-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="43fea-203">例如：如果您使用的是 [資產識別碼] 屬性，請在以下顯示的資產識別碼方塊中輸入 `ComplianceAssetID:<value>`。</span><span class="sxs-lookup"><span data-stu-id="43fea-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="43fea-204">組織可能已將其他屬性和識別碼套用到與此事件類型相關的文件。</span><span class="sxs-lookup"><span data-stu-id="43fea-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="43fea-205">例如，如果您需要偵測特定產品的記錄，識別碼可能會是您的自訂屬性 ProductID 和值 "XYZ"。</span><span class="sxs-lookup"><span data-stu-id="43fea-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="43fea-206">在此情況下，您會在下圖所示的資產識別碼方塊中輸入 `ProductID:XYZ`。</span><span class="sxs-lookup"><span data-stu-id="43fea-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="43fea-207">若為 Exchange 項目，請使用關鍵字。</span><span class="sxs-lookup"><span data-stu-id="43fea-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="43fea-208">您可以使用 AND、OR 和 NOT 這類搜尋運算子來使用查詢。</span><span class="sxs-lookup"><span data-stu-id="43fea-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="43fea-209">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="43fea-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="43fea-210">最後，選擇事件的發生日期；此日期作為保留期間的開始日期。</span><span class="sxs-lookup"><span data-stu-id="43fea-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="43fea-211">建立事件之後，該事件日期會同步處理到保留標籤屬於該事件類型、具有資產識別碼和關鍵字的所有內容。</span><span class="sxs-lookup"><span data-stu-id="43fea-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="43fea-212">如同任何保留標籤，同步處理最多可能需要七天。</span><span class="sxs-lookup"><span data-stu-id="43fea-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![事件設定頁面](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="43fea-214">建立事件之後，保留設定就會對已套用標籤和已編製索引的內容生效。</span><span class="sxs-lookup"><span data-stu-id="43fea-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="43fea-215">如果在建立事件之後，將保留標籤新增至新內容，則您必須使用相同的詳細資料建立新事件。</span><span class="sxs-lookup"><span data-stu-id="43fea-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="43fea-216">刪除事件不會取消目前對已套用標籤之內容生效的保留設定。</span><span class="sxs-lookup"><span data-stu-id="43fea-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="43fea-217">若要這麼做，請建立具有相同詳細資料的新事件，但將日期保留空白。</span><span class="sxs-lookup"><span data-stu-id="43fea-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="43fea-218">使用內容搜尋來尋找具有特定標籤或資產識別碼的所有內容</span><span class="sxs-lookup"><span data-stu-id="43fea-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="43fea-219">將保留標籤指派給內容之後，您可以使用內容搜尋，尋找以特定保留標籤分類或包含特定資產識別碼的所有內容：</span><span class="sxs-lookup"><span data-stu-id="43fea-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="43fea-220">若要尋找具有特定保留標籤的所有內容時，請選擇 **[保留標籤]** 條件，然後輸入完整標籤名稱或，或輸入部分標籤名稱並使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="43fea-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="43fea-221">若要尋找具有特定資產識別碼的所有內容，請使用格式 `ComplianceAssetID:<value>` 輸入 **ComplianceAssetID** 屬性和值。</span><span class="sxs-lookup"><span data-stu-id="43fea-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="43fea-222">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="43fea-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="43fea-223">使用 PowerShell 讓事件自動化</span><span class="sxs-lookup"><span data-stu-id="43fea-223">Automate events by using PowerShell</span></span>

<span data-ttu-id="43fea-224">您可以使用 PowerShell 指令碼來自動化商務應用程式中以事件為基礎的保留。</span><span class="sxs-lookup"><span data-stu-id="43fea-224">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="43fea-225">適用於事件型保留的 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="43fea-225">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="43fea-226">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="43fea-226">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="43fea-227">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="43fea-227">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="43fea-228">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="43fea-228">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="43fea-229">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="43fea-229">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="43fea-230">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="43fea-230">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="43fea-231">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="43fea-231">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="43fea-232">使用 REST API 讓事件自動化</span><span class="sxs-lookup"><span data-stu-id="43fea-232">Automate events by using a REST API</span></span>

<span data-ttu-id="43fea-233">您可以使用 REST API 自動建立觸發保留時間開始的事件。</span><span class="sxs-lookup"><span data-stu-id="43fea-233">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="43fea-234">REST API 是支援 HTTP 操作組 (方法) 的服務端點，提供服務資源的建立、擷取、更新、刪除等存取權。</span><span class="sxs-lookup"><span data-stu-id="43fea-234">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="43fea-235">如需詳細資訊，請參閱 [REST API 要求/回應的元件](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。</span><span class="sxs-lookup"><span data-stu-id="43fea-235">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="43fea-236">透過使用 Microsoft 365 REST API，使用 POST 和 GET 方法可以建立和擷取事件。</span><span class="sxs-lookup"><span data-stu-id="43fea-236">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="43fea-237">有兩個選項可以使用 REST API：</span><span class="sxs-lookup"><span data-stu-id="43fea-237">There are two options for using the REST API:</span></span>

- <span data-ttu-id="43fea-238">**Microsoft Power Automate 或類似的應用程式**可以用於自動觸發事件的發生。</span><span class="sxs-lookup"><span data-stu-id="43fea-238">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="43fea-239">Microsoft Power Automate 是連線到其他系統的協調器，因此您不需要撰寫自訂解決方案。</span><span class="sxs-lookup"><span data-stu-id="43fea-239">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="43fea-240">如需詳細資訊，請參閱 [Power Automate 網站](https://flow.microsoft.com/zh-TW/)。</span><span class="sxs-lookup"><span data-stu-id="43fea-240">For more information, see the [Power Automate website](https://flow.microsoft.com/zh-TW/).</span></span>

- <span data-ttu-id="43fea-241">**PowerShell 或 HTTP 用戶端呼叫 REST API** 以透過 PowerShell （版本6或更新版本）建立事件，這是自訂解決方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="43fea-241">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="43fea-242">在您使用 REST API 之前，請先確認用於保留事件呼叫的 URL。</span><span class="sxs-lookup"><span data-stu-id="43fea-242">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="43fea-243">若要這麼做，請使用 REST API URL 執行 [獲取] 保留事件呼叫:</span><span class="sxs-lookup"><span data-stu-id="43fea-243">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="43fea-244">檢查回應碼。</span><span class="sxs-lookup"><span data-stu-id="43fea-244">Check the response code.</span></span> <span data-ttu-id="43fea-245">如果是302，請從回應標題的地址屬性取得重新導向的 URL，並使用該 URL，而非後續指示中的 `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`。</span><span class="sxs-lookup"><span data-stu-id="43fea-245">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="43fea-246">自動建立的事件可以在 Microsoft 365 合規性中心裡透過查看以進行確認 > **記錄管理** >  **事件**。</span><span class="sxs-lookup"><span data-stu-id="43fea-246">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="43fea-247">使用 Microsoft Power Automate 建立活動</span><span class="sxs-lookup"><span data-stu-id="43fea-247">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="43fea-248">建立使用 Microsoft 365 REST API 建立事件的流程:</span><span class="sxs-lookup"><span data-stu-id="43fea-248">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![使用 Flow 建立事件](../media/automate-event-driven-retention-flow-1.png)

![使用流程呼叫 REST API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="43fea-251">建立事件</span><span class="sxs-lookup"><span data-stu-id="43fea-251">Create an event</span></span>

<span data-ttu-id="43fea-252">呼叫 REST API 的範例程式碼：</span><span class="sxs-lookup"><span data-stu-id="43fea-252">Sample code to call the REST API:</span></span>

- <span data-ttu-id="43fea-253">**方法**：POST</span><span class="sxs-lookup"><span data-stu-id="43fea-253">**Method**: POST</span></span>
- <span data-ttu-id="43fea-254">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="43fea-254">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="43fea-255">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="43fea-255">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="43fea-256">**本文**：</span><span class="sxs-lookup"><span data-stu-id="43fea-256">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="43fea-257">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="43fea-257">**Authentication**: Basic</span></span>
- <span data-ttu-id="43fea-258">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="43fea-258">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="43fea-259">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="43fea-259">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="43fea-260">可用的參數</span><span class="sxs-lookup"><span data-stu-id="43fea-260">Available parameters</span></span>


|<span data-ttu-id="43fea-261">參數</span><span class="sxs-lookup"><span data-stu-id="43fea-261">Parameters</span></span>|<span data-ttu-id="43fea-262">描述</span><span class="sxs-lookup"><span data-stu-id="43fea-262">Description</span></span>|<span data-ttu-id="43fea-263">附註</span><span class="sxs-lookup"><span data-stu-id="43fea-263">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="43fea-264"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="43fea-264"><d:Name></d:Name></span></span>|<span data-ttu-id="43fea-265">提供事件的唯一名稱，</span><span class="sxs-lookup"><span data-stu-id="43fea-265">Provide a unique name for the event,</span></span>|<span data-ttu-id="43fea-266">結尾不可包含空格或下列字元：% \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="43fea-266">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="43fea-267">, : ;</span><span class="sxs-lookup"><span data-stu-id="43fea-267">, : ;</span></span>|
|<span data-ttu-id="43fea-268"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="43fea-268"><d:EventType></d:EventType></span></span>|<span data-ttu-id="43fea-269">輸入事件類型名稱 (或 Guid)</span><span class="sxs-lookup"><span data-stu-id="43fea-269">Enter event type name (or Guid),</span></span>|<span data-ttu-id="43fea-270">範例：「員工離職」。</span><span class="sxs-lookup"><span data-stu-id="43fea-270">Example: "Employee termination".</span></span> <span data-ttu-id="43fea-271">事件類型必須與保留標籤相關聯。</span><span class="sxs-lookup"><span data-stu-id="43fea-271">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="43fea-272"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="43fea-272"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="43fea-273">輸入「ComplianceAssetId：」 + 「員工識別碼」</span><span class="sxs-lookup"><span data-stu-id="43fea-273">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="43fea-274">範例："ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="43fea-274">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="43fea-275"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="43fea-275"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="43fea-276">事件的日期和時間</span><span class="sxs-lookup"><span data-stu-id="43fea-276">Event Date and Time</span></span>|<span data-ttu-id="43fea-277">格式：yyyy-MM-ddTHH:mm:ssZ，例如：2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="43fea-277">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="43fea-278">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-278">Response codes</span></span>

| <span data-ttu-id="43fea-279">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-279">Response Code</span></span> | <span data-ttu-id="43fea-280">描述</span><span class="sxs-lookup"><span data-stu-id="43fea-280">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="43fea-281">302</span><span class="sxs-lookup"><span data-stu-id="43fea-281">302</span></span>               | <span data-ttu-id="43fea-282">重新導向</span><span class="sxs-lookup"><span data-stu-id="43fea-282">Redirect</span></span>              |
| <span data-ttu-id="43fea-283">201</span><span class="sxs-lookup"><span data-stu-id="43fea-283">201</span></span>               | <span data-ttu-id="43fea-284">建立時間</span><span class="sxs-lookup"><span data-stu-id="43fea-284">Created</span></span>               |
| <span data-ttu-id="43fea-285">403</span><span class="sxs-lookup"><span data-stu-id="43fea-285">403</span></span>               | <span data-ttu-id="43fea-286">授權失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-286">Authorization Failed</span></span>  |
| <span data-ttu-id="43fea-287">401</span><span class="sxs-lookup"><span data-stu-id="43fea-287">401</span></span>               | <span data-ttu-id="43fea-288">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-288">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="43fea-289">依據時間範圍取得事件</span><span class="sxs-lookup"><span data-stu-id="43fea-289">Get events based on a time range</span></span>

- <span data-ttu-id="43fea-290">**方法**：GET</span><span class="sxs-lookup"><span data-stu-id="43fea-290">**Method**: GET</span></span>

- <span data-ttu-id="43fea-291">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="43fea-291">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="43fea-292">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="43fea-292">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="43fea-293">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="43fea-293">**Authentication**: Basic</span></span>

- <span data-ttu-id="43fea-294">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="43fea-294">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="43fea-295">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="43fea-295">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="43fea-296">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-296">Response codes</span></span>

| <span data-ttu-id="43fea-297">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-297">Response Code</span></span> | <span data-ttu-id="43fea-298">描述</span><span class="sxs-lookup"><span data-stu-id="43fea-298">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="43fea-299">200</span><span class="sxs-lookup"><span data-stu-id="43fea-299">200</span></span>               | <span data-ttu-id="43fea-300">好的，以 atom+ xml 格式列出事件清單</span><span class="sxs-lookup"><span data-stu-id="43fea-300">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="43fea-301">404</span><span class="sxs-lookup"><span data-stu-id="43fea-301">404</span></span>               | <span data-ttu-id="43fea-302">找不到</span><span class="sxs-lookup"><span data-stu-id="43fea-302">Not found</span></span>                         |
| <span data-ttu-id="43fea-303">302</span><span class="sxs-lookup"><span data-stu-id="43fea-303">302</span></span>               | <span data-ttu-id="43fea-304">重新導向</span><span class="sxs-lookup"><span data-stu-id="43fea-304">Redirect</span></span>                          |
| <span data-ttu-id="43fea-305">401</span><span class="sxs-lookup"><span data-stu-id="43fea-305">401</span></span>               | <span data-ttu-id="43fea-306">授權失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-306">Authorization Failed</span></span>              |
| <span data-ttu-id="43fea-307">403</span><span class="sxs-lookup"><span data-stu-id="43fea-307">403</span></span>               | <span data-ttu-id="43fea-308">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-308">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="43fea-309">依 ID 取得事件</span><span class="sxs-lookup"><span data-stu-id="43fea-309">Get an event by ID</span></span>

- <span data-ttu-id="43fea-310">**方法**：GET</span><span class="sxs-lookup"><span data-stu-id="43fea-310">**Method**: GET</span></span>

- <span data-ttu-id="43fea-311">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="43fea-311">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="43fea-312">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="43fea-312">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="43fea-313">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="43fea-313">**Authentication**: Basic</span></span>

- <span data-ttu-id="43fea-314">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="43fea-314">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="43fea-315">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="43fea-315">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="43fea-316">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-316">Response codes</span></span>

| <span data-ttu-id="43fea-317">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-317">Response Code</span></span> | <span data-ttu-id="43fea-318">描述</span><span class="sxs-lookup"><span data-stu-id="43fea-318">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="43fea-319">200</span><span class="sxs-lookup"><span data-stu-id="43fea-319">200</span></span>               | <span data-ttu-id="43fea-320">好的，回應本文包含有 atom+xml 格式的事件</span><span class="sxs-lookup"><span data-stu-id="43fea-320">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="43fea-321">404</span><span class="sxs-lookup"><span data-stu-id="43fea-321">404</span></span>               | <span data-ttu-id="43fea-322">找不到</span><span class="sxs-lookup"><span data-stu-id="43fea-322">Not found</span></span>                                            |
| <span data-ttu-id="43fea-323">302</span><span class="sxs-lookup"><span data-stu-id="43fea-323">302</span></span>               | <span data-ttu-id="43fea-324">重新導向</span><span class="sxs-lookup"><span data-stu-id="43fea-324">Redirect</span></span>                                             |
| <span data-ttu-id="43fea-325">401</span><span class="sxs-lookup"><span data-stu-id="43fea-325">401</span></span>               | <span data-ttu-id="43fea-326">授權失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-326">Authorization Failed</span></span>                                 |
| <span data-ttu-id="43fea-327">403</span><span class="sxs-lookup"><span data-stu-id="43fea-327">403</span></span>               | <span data-ttu-id="43fea-328">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-328">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="43fea-329">依名稱取得事件</span><span class="sxs-lookup"><span data-stu-id="43fea-329">Get an event by name</span></span>

- <span data-ttu-id="43fea-330">**方法**：GET</span><span class="sxs-lookup"><span data-stu-id="43fea-330">**Method**: GET</span></span>

- <span data-ttu-id="43fea-331">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="43fea-331">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="43fea-332">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="43fea-332">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="43fea-333">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="43fea-333">**Authentication**: Basic</span></span>

- <span data-ttu-id="43fea-334">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="43fea-334">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="43fea-335">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="43fea-335">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="43fea-336">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-336">Response codes</span></span>

| <span data-ttu-id="43fea-337">回應碼</span><span class="sxs-lookup"><span data-stu-id="43fea-337">Response Code</span></span> | <span data-ttu-id="43fea-338">描述</span><span class="sxs-lookup"><span data-stu-id="43fea-338">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="43fea-339">200</span><span class="sxs-lookup"><span data-stu-id="43fea-339">200</span></span>               | <span data-ttu-id="43fea-340">好的，回應本文包含有 atom+xml 格式的事件</span><span class="sxs-lookup"><span data-stu-id="43fea-340">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="43fea-341">404</span><span class="sxs-lookup"><span data-stu-id="43fea-341">404</span></span>               | <span data-ttu-id="43fea-342">找不到</span><span class="sxs-lookup"><span data-stu-id="43fea-342">Not found</span></span>                                            |
| <span data-ttu-id="43fea-343">302</span><span class="sxs-lookup"><span data-stu-id="43fea-343">302</span></span>               | <span data-ttu-id="43fea-344">重新導向</span><span class="sxs-lookup"><span data-stu-id="43fea-344">Redirect</span></span>                                             |
| <span data-ttu-id="43fea-345">401</span><span class="sxs-lookup"><span data-stu-id="43fea-345">401</span></span>               | <span data-ttu-id="43fea-346">授權失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-346">Authorization Failed</span></span>                                 |
| <span data-ttu-id="43fea-347">403</span><span class="sxs-lookup"><span data-stu-id="43fea-347">403</span></span>               | <span data-ttu-id="43fea-348">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="43fea-348">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="43fea-349">使用 PowerShell 或任何 HTTP 用戶端來建立事件</span><span class="sxs-lookup"><span data-stu-id="43fea-349">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="43fea-350">PowerShell 必須是版本6或更新版本。</span><span class="sxs-lookup"><span data-stu-id="43fea-350">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="43fea-351">在 PowerShell 工作階段中，執行下列腳本：</span><span class="sxs-lookup"><span data-stu-id="43fea-351">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

