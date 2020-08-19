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
ms.openlocfilehash: 7286e65be2313f5716bfc59399c1755cadb9f6d6
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778523"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="febae-103">事件發生時，開始保留</span><span class="sxs-lookup"><span data-stu-id="febae-103">Start retention when an event occurs</span></span>

><span data-ttu-id="febae-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="febae-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="febae-p101">當您保留內容時，保留期間通常是依據內容的存留期。例如，您在文件建立之後保留 7 年，然後刪除。但當您設定[保留標籤](labels.md)，您也可以讓發生特定類型事件的時間作為保留期間的依據。事件會觸發啟動保留期間，有保留標籤套用至該類型事件的所有內容，都會強制執行標籤的保留動作。</span><span class="sxs-lookup"><span data-stu-id="febae-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="febae-109">使用事件導向保留的範例：</span><span class="sxs-lookup"><span data-stu-id="febae-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="febae-110">**員工離開組織** 假設員工記錄必須從員工離開組織起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="febae-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="febae-111">經過 10 年之後，所有與該名員工相關的雇用、績效和離職文件都必須加以處置。</span><span class="sxs-lookup"><span data-stu-id="febae-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="febae-112">會觸發 10 年保留期間的事件是員工離開組織。</span><span class="sxs-lookup"><span data-stu-id="febae-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="febae-113">**合約到期** 假設與合約相關的所有記錄必須從合約到期時間起保留五年。</span><span class="sxs-lookup"><span data-stu-id="febae-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="febae-114">會觸發五年保留期間的事件是合約到期。</span><span class="sxs-lookup"><span data-stu-id="febae-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="febae-p104">**產品生命週期**貴組織可能有與產品最後製造日期相關的保留需求，例如技術規格。在此情況下，最後製造日期是觸發保留期間的事件。</span><span class="sxs-lookup"><span data-stu-id="febae-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="febae-p105">事件導向保留通常作為記錄管理處理程序的一部分。這表示：</span><span class="sxs-lookup"><span data-stu-id="febae-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="febae-119">依事件標示的標籤通常也會將其內容分類成一個資料列，為記錄管理解決方案的其中一部分。</span><span class="sxs-lookup"><span data-stu-id="febae-119">Labels based on events also usually classify content as a record, as a part of a records management solution.</span></span> <span data-ttu-id="febae-120">如需詳細資訊，請參閱[了解記錄管理](records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="febae-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="febae-121">已分類為記錄但是其事件觸發程序尚未發生的文件，會無限期保留 (記錄無法永久刪除)，直到事件觸發該文件的保留期間。</span><span class="sxs-lookup"><span data-stu-id="febae-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="febae-122">根據事件的保留標籤通常會在保留期間結束時觸發處置檢閱，這樣記錄管理員就能手動檢閱並處置內容。</span><span class="sxs-lookup"><span data-stu-id="febae-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="febae-123">如需詳細資訊，請參閱[處置內容](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="febae-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="febae-124">根據事件的標籤與 Microsoft 365 中任何保留標籤具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="febae-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="febae-125">如需詳細資訊，請參閱[[瞭解保留原則及保留標籤]](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="febae-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="febae-126">了解事件類型、標籤、事件和資產識別碼之間的關聯性</span><span class="sxs-lookup"><span data-stu-id="febae-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="febae-127">若要成功使用事件導向保留，請務必了解事件類型、保留標籤、事件和資產識別碼之間的關聯性，如下列圖表所示且圖表後有說明。</span><span class="sxs-lookup"><span data-stu-id="febae-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![事件類型、標籤、事件和資產識別碼的圖表](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件類型、標籤、事件和資產識別碼的圖表](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="febae-130">您為各種類型的內容建立保留標籤，然後將其與某種事件類型建立關聯。</span><span class="sxs-lookup"><span data-stu-id="febae-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="febae-131">例如，不同類型產品檔案和記錄的保留標籤會與名為「產品生命週期」的事件類型相關聯，因為這些記錄必須從產品達到其生命週期結束開始保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="febae-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="febae-132">使用者 (通常是記錄管理員) 會將這些保留標籤套用到內容，並且 (若是 SharePoint 和 OneDrive 文件) 為每個項目輸入資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="febae-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="febae-133">在此範例中，資產識別碼是組織所使用的產品名稱或代碼。</span><span class="sxs-lookup"><span data-stu-id="febae-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="febae-134">因此，每個產品的記錄都會獲派一個保留標籤，而每筆記錄都會有包含資產識別碼的屬性。</span><span class="sxs-lookup"><span data-stu-id="febae-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="febae-135">此圖表描繪組織中所有產品記錄的**所有內容**，而每個項目都會承載記錄所屬產品的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="febae-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="febae-p111">產品生命週期是事件類型；達到生命週期結尾的特定產品是事件。該事件類型的事件發生時 - 在此情況下，當產品達到其生命週期結尾時 - 您建立事件，指定：</span><span class="sxs-lookup"><span data-stu-id="febae-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="febae-138">資產識別碼 (適用於 SharePoint 和 OneDrive 文件)</span><span class="sxs-lookup"><span data-stu-id="febae-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="febae-p112">關鍵字 (適用於 Exchange 項目)。在此範例中，組織在包含產品記錄的訊息中使用產品代碼，因此 Exchange 項目的關鍵字與 SharePoint 和 OneDrive 文件中的資產識別碼相同。</span><span class="sxs-lookup"><span data-stu-id="febae-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="febae-p113">發生事件的日期。此日期作為保留期間的開始日期。此日期可能是目前、過去或未來的日期。</span><span class="sxs-lookup"><span data-stu-id="febae-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="febae-144">建立事件之後，該事件日期會同步處理到保留標籤屬於該事件類型的所有內容，以及包含指定資產識別碼或關鍵字的所有內容。</span><span class="sxs-lookup"><span data-stu-id="febae-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="febae-145">如同任何保留標籤，同步處理最多可能需要七天。</span><span class="sxs-lookup"><span data-stu-id="febae-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="febae-146">上圖中以紅色圈出的所有項目，其保留期間都是由此事件觸發。</span><span class="sxs-lookup"><span data-stu-id="febae-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="febae-147">換句話說，當這項產品的生命週期結束時，該事件會觸發該產品記錄的保留期間。</span><span class="sxs-lookup"><span data-stu-id="febae-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="febae-148">請務必了解，如果您沒有為事件指定資產識別碼或關鍵字，具有該事件類型之標籤的**所有內容**都將有其被事件觸發的保留期間。</span><span class="sxs-lookup"><span data-stu-id="febae-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="febae-149">這表示在上圖中，所有內容都會開始進行保留。</span><span class="sxs-lookup"><span data-stu-id="febae-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="febae-150">這可能不是您原本的打算。</span><span class="sxs-lookup"><span data-stu-id="febae-150">This might not be what you intend.</span></span> 

<span data-ttu-id="febae-151">最後，請記住，每個保留標籤都有自己的保留設定。</span><span class="sxs-lookup"><span data-stu-id="febae-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="febae-152">在此範例中，全都指定 10 年，但有可能事件觸發的保留標籤是每個標籤都有不同的保留期間。</span><span class="sxs-lookup"><span data-stu-id="febae-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="febae-153">如何設定事件導向保留</span><span class="sxs-lookup"><span data-stu-id="febae-153">How to set up event-driven retention</span></span>

<span data-ttu-id="febae-154">事件導向保留的整體工作流程：</span><span class="sxs-lookup"><span data-stu-id="febae-154">High-level workflow for event-driven retention:</span></span>
  
![設定事件導向保留工作流程的圖表](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="febae-156">請參閱 [使用保留標籤來管理儲存在 SharePoint 中的文件生命週期](auto-apply-retention-labels-scenario.md)，以瞭解如何在 SharePoint 中使用管理屬性以自動套用保留標籤及實施事件導向保留。</span><span class="sxs-lookup"><span data-stu-id="febae-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="febae-157">步驟 1：建立其保留期間根據事件的標籤</span><span class="sxs-lookup"><span data-stu-id="febae-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="febae-158">若要建立及設定您的保留標籤，請使用[建立及設定保留標籤](create-retention-labels.md#create-and-configure-retention-labels)的相關指示，並在開啟保留時，選擇根據事件保留或刪除內容的選項。</span><span class="sxs-lookup"><span data-stu-id="febae-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="febae-159">此設定表示當您在 [事件]\*\*\*\* 頁面上建立事件時，保留設定在步驟 5 之前都不會生效。</span><span class="sxs-lookup"><span data-stu-id="febae-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="febae-160">事件導向的保留通常是用於分類為記錄的內容，因此很適合用來檢查您是否也需要選取將內容標示為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="febae-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="febae-161">事件導向保留需要保留設定：</span><span class="sxs-lookup"><span data-stu-id="febae-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="febae-162">保留內容。</span><span class="sxs-lookup"><span data-stu-id="febae-162">Retain the content.</span></span>
    
- <span data-ttu-id="febae-163">自動刪除內容或在保留期間結束時觸發處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="febae-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![讓標籤以事件為依據的選項](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="febae-165">步驟 2：選擇該標籤的事件類型</span><span class="sxs-lookup"><span data-stu-id="febae-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="febae-166">在標籤設定中，在您選擇讓標籤根據 **[事件]** 的選項後，您會看見 **[選擇事件類型]** 的選項。</span><span class="sxs-lookup"><span data-stu-id="febae-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="febae-167">事件類型只是您要讓標籤與事件建立關聯之事件的一般描述。</span><span class="sxs-lookup"><span data-stu-id="febae-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="febae-168">例如，如果您建立名為「產品生命週期」的事件類型，您會建立事件型保留標籤，具有名稱說明您想要將標籤套用到什麼類型的內容，例如「產品開發檔案」或「產品業務決策記錄」。</span><span class="sxs-lookup"><span data-stu-id="febae-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="febae-169">選取其中一個內建的事件類型，或建立您自己的事件類型，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="febae-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="febae-170">在您選擇事件類型並儲存保留標籤之後，就無法變更事件類型。</span><span class="sxs-lookup"><span data-stu-id="febae-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![建立或選擇事件類型的選項](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="febae-172">步驟 3：發佈或自動套用事件型保留標籤</span><span class="sxs-lookup"><span data-stu-id="febae-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="febae-173">和任何保留標籤一樣，您必須發佈或自動套用事件型標籤，以使標籤可以手動或自動套用到內容中：</span><span class="sxs-lookup"><span data-stu-id="febae-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="febae-174">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="febae-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="febae-175">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="febae-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="febae-176">如果您是從 [記錄管理] \*\*\*\*  >  [檔案方案]\*\*\*\* 索引標籤或 [資料控管]\*\*\*\*  >  [標籤]\*\*\*\* 索引標籤選取事件型保留標籤，則 [自動套用標籤]\*\*\*\* 按鈕無法使用。</span><span class="sxs-lookup"><span data-stu-id="febae-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="febae-177">請勿使用這個按鈕，改用下列其中一個位置中，標籤或原則清單上的 [自動套用標籤]\*\*\*\* 選項：</span><span class="sxs-lookup"><span data-stu-id="febae-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="febae-178">[記錄管理]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤</span><span class="sxs-lookup"><span data-stu-id="febae-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="febae-179">**[資料控管]** > **[標籤]** 索引標籤或 **[標籤原則]** 索引標籤</span><span class="sxs-lookup"><span data-stu-id="febae-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![發佈或自動套用保留標籤的選項](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="febae-181">步驟 4：輸入資產識別碼</span><span class="sxs-lookup"><span data-stu-id="febae-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="febae-182">在事件型標籤套用到內容之後，您可以輸入每個項目的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="febae-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="febae-183">例如，貴組織可能使用：</span><span class="sxs-lookup"><span data-stu-id="febae-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="febae-184">產品代碼，您可以用來保留僅限特定產品的內容。</span><span class="sxs-lookup"><span data-stu-id="febae-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="febae-185">專案代碼，您可以用來保留僅限特定專案的內容。</span><span class="sxs-lookup"><span data-stu-id="febae-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="febae-186">員工識別碼，您可以用來保留僅限特定人員的內容。</span><span class="sxs-lookup"><span data-stu-id="febae-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="febae-187">資產識別碼只是 SharePoint 和 OneDrive 中可用的另一個文件屬性。</span><span class="sxs-lookup"><span data-stu-id="febae-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="febae-188">貴組織可能已經使用其他文件屬性和識別碼來分類內容。</span><span class="sxs-lookup"><span data-stu-id="febae-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="febae-189">若是如此，您也可以在建立事件時使用這些屬性和值，請參閱後續的步驟 6。</span><span class="sxs-lookup"><span data-stu-id="febae-189">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="febae-190">重點是，您必須在文件屬性中使用一些 *property:value* 組合，以將該項目與事件類型建立關聯。</span><span class="sxs-lookup"><span data-stu-id="febae-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![在其中輸入資產識別碼的文字方塊](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="febae-192">步驟 5：建立事件</span><span class="sxs-lookup"><span data-stu-id="febae-192">Step 5: Create an event</span></span>

<span data-ttu-id="febae-193">發生該事件類型的特定執行個體時，例如，產品達到其生命週期的結尾，請移至 Microsoft 365 合規性中心的 [記錄管理]\*\*\*\*  >  [事件]\*\*\*\* 頁面，並建立事件。</span><span class="sxs-lookup"><span data-stu-id="febae-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="febae-194">您可以建立事件來觸發事件。</span><span class="sxs-lookup"><span data-stu-id="febae-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="febae-195">步驟 6：選擇與步驟 2 中的標籤所使用相同的事件類型</span><span class="sxs-lookup"><span data-stu-id="febae-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="febae-196">當您建立事件時，請選擇步驟 2 中保留標籤所使用的相同事件類型，例如「產品生命週期」。</span><span class="sxs-lookup"><span data-stu-id="febae-196">When you create the event, choose the same event type used by the retention label in step 2—for example, Product Lifetime.</span></span> <span data-ttu-id="febae-197">只有已套用該事件類型保留標籤的內容會觸發其保留期間。</span><span class="sxs-lookup"><span data-stu-id="febae-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![在事件設定中選擇事件類型的選項](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="febae-199">步驟 7：輸入關鍵字或資產識別碼</span><span class="sxs-lookup"><span data-stu-id="febae-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="febae-200">現在您可以指定 SharePoint 和 OneDrive 內容的資產識別碼或 Exchange 內容的關鍵字，藉此縮小內容的範圍。</span><span class="sxs-lookup"><span data-stu-id="febae-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="febae-201">針對資產識別碼，只有在具有指定 *property:value* 組的內容上才會強制執行保留。</span><span class="sxs-lookup"><span data-stu-id="febae-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="febae-202">若未輸入資產識別碼，具有該事件類型之標籤的所有內容都會套用相同的保留日期。</span><span class="sxs-lookup"><span data-stu-id="febae-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="febae-203">例如：如果您使用的是 [資產識別碼] 屬性，請在以下顯示的資產識別碼方塊中輸入 `ComplianceAssetID:<value>`。</span><span class="sxs-lookup"><span data-stu-id="febae-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="febae-204">組織可能已將其他屬性和識別碼套用到與此事件類型相關的文件。</span><span class="sxs-lookup"><span data-stu-id="febae-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="febae-205">例如，如果您需要偵測特定產品的記錄，識別碼可能會是您的自訂屬性 ProductID 和值 "XYZ"。</span><span class="sxs-lookup"><span data-stu-id="febae-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="febae-206">在此情況下，您會在下圖所示的資產識別碼方塊中輸入 `ProductID:XYZ`。</span><span class="sxs-lookup"><span data-stu-id="febae-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="febae-207">若為 Exchange 項目，請使用關鍵字。</span><span class="sxs-lookup"><span data-stu-id="febae-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="febae-208">您可以使用 AND、OR 和 NOT 這類搜尋運算子來使用查詢。</span><span class="sxs-lookup"><span data-stu-id="febae-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="febae-209">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="febae-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="febae-210">最後，選擇事件的發生日期；此日期作為保留期間的開始日期。</span><span class="sxs-lookup"><span data-stu-id="febae-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="febae-211">建立事件之後，該事件日期會同步處理到保留標籤屬於該事件類型、具有資產識別碼和關鍵字的所有內容。</span><span class="sxs-lookup"><span data-stu-id="febae-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="febae-212">如同任何保留標籤，同步處理最多可能需要七天。</span><span class="sxs-lookup"><span data-stu-id="febae-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![事件設定頁面](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="febae-214">建立事件之後，保留設定就會對已套用標籤和已編製索引的內容生效。</span><span class="sxs-lookup"><span data-stu-id="febae-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="febae-215">如果在建立事件之後，將保留標籤新增至新內容，則您必須使用相同的詳細資料建立新事件。</span><span class="sxs-lookup"><span data-stu-id="febae-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="febae-216">刪除事件不會取消目前對已套用標籤之內容生效的保留設定。</span><span class="sxs-lookup"><span data-stu-id="febae-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="febae-217">若要這麼做，請建立具有相同詳細資料的新事件，但將日期保留空白。</span><span class="sxs-lookup"><span data-stu-id="febae-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="febae-218">使用內容搜尋來尋找具有特定標籤或資產識別碼的所有內容</span><span class="sxs-lookup"><span data-stu-id="febae-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="febae-219">將保留標籤指派給內容之後，您可以使用內容搜尋，尋找以特定保留標籤分類或包含特定資產識別碼的所有內容：</span><span class="sxs-lookup"><span data-stu-id="febae-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="febae-220">若要尋找具有特定保留標籤的所有內容時，請選擇 **[保留標籤]** 條件，然後輸入完整標籤名稱或，或輸入部分標籤名稱並使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="febae-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="febae-221">若要尋找具有特定資產識別碼的所有內容，請使用格式 `ComplianceAssetID:<value>` 輸入 **ComplianceAssetID** 屬性和值。</span><span class="sxs-lookup"><span data-stu-id="febae-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="febae-222">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="febae-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="febae-223">權限</span><span class="sxs-lookup"><span data-stu-id="febae-223">Permissions</span></span>

<span data-ttu-id="febae-p129">若要取得 [事件]\*\*\*\* 頁面的存取權，檢閱者必須是具有**處置管理**角色和**僅限檢視稽核記錄**角色之角色群組的成員。我們建議建立稱為「處置檢閱者」的新角色群組，將這兩個角色新增至該角色群組，然後將成員新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="febae-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="febae-226">如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="febae-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="febae-227">使用 PowerShell 讓事件自動化</span><span class="sxs-lookup"><span data-stu-id="febae-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="febae-228">您可以使用 PowerShell 指令碼來自動化商務應用程式中以事件為基礎的保留。</span><span class="sxs-lookup"><span data-stu-id="febae-228">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="febae-229">適用於事件型保留的 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="febae-229">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="febae-230">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="febae-230">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="febae-231">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="febae-231">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="febae-232">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="febae-232">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="febae-233">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="febae-233">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="febae-234">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="febae-234">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="febae-235">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="febae-235">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="febae-236">使用 REST API 讓事件自動化</span><span class="sxs-lookup"><span data-stu-id="febae-236">Automate events by using a REST API</span></span>

<span data-ttu-id="febae-237">您可以使用 REST API 自動建立觸發保留時間開始的事件。</span><span class="sxs-lookup"><span data-stu-id="febae-237">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="febae-238">REST API 是支援 HTTP 操作組 (方法) 的服務端點，提供服務資源的建立、擷取、更新、刪除等存取權。</span><span class="sxs-lookup"><span data-stu-id="febae-238">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="febae-239">如需詳細資訊，請參閱 [REST API 要求/回應的元件](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。</span><span class="sxs-lookup"><span data-stu-id="febae-239">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="febae-240">透過使用 Microsoft 365 REST API，使用 POST 和 GET 方法可以建立和擷取事件。</span><span class="sxs-lookup"><span data-stu-id="febae-240">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="febae-241">有兩個選項可以使用 REST API：</span><span class="sxs-lookup"><span data-stu-id="febae-241">There are two options for using the REST API:</span></span>

- <span data-ttu-id="febae-242">**Microsoft Power Automate 或類似的應用程式**可以用於自動觸發事件的發生。</span><span class="sxs-lookup"><span data-stu-id="febae-242">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="febae-243">Microsoft Power Automate 是連線到其他系統的協調器，因此您不需要撰寫自訂解決方案。</span><span class="sxs-lookup"><span data-stu-id="febae-243">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="febae-244">如需詳細資訊，請參閱 [Power Automate 網站](https://flow.microsoft.com/zh-TW/)。</span><span class="sxs-lookup"><span data-stu-id="febae-244">For more information, see the [Power Automate website](https://flow.microsoft.com/zh-TW/).</span></span>

- <span data-ttu-id="febae-245">**PowerShell 或 HTTP 用戶端呼叫 REST API** 以透過 PowerShell （版本6或更新版本）建立事件，這是自訂解決方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="febae-245">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="febae-246">在您使用 REST API 之前，請先確認用於保留事件呼叫的 URL。</span><span class="sxs-lookup"><span data-stu-id="febae-246">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="febae-247">若要這麼做，請使用 REST API URL 執行 [獲取] 保留事件呼叫:</span><span class="sxs-lookup"><span data-stu-id="febae-247">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="febae-248">檢查回應碼。</span><span class="sxs-lookup"><span data-stu-id="febae-248">Check the response code.</span></span> <span data-ttu-id="febae-249">如果是302，請從回應標題的地址屬性取得重新導向的 URL，並使用該 URL，而非後續指示中的 `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`。</span><span class="sxs-lookup"><span data-stu-id="febae-249">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="febae-250">自動建立的事件可以在 Microsoft 365 合規性中心裡透過查看以進行確認 > **記錄管理** >  **事件**。</span><span class="sxs-lookup"><span data-stu-id="febae-250">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="febae-251">使用 Microsoft Power Automate 建立活動</span><span class="sxs-lookup"><span data-stu-id="febae-251">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="febae-252">建立使用 Microsoft 365 REST API 建立事件的流程:</span><span class="sxs-lookup"><span data-stu-id="febae-252">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![使用 Flow 建立事件](../media/automate-event-driven-retention-flow-1.png)

![使用流程呼叫 REST API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="febae-255">建立事件</span><span class="sxs-lookup"><span data-stu-id="febae-255">Create an event</span></span>

<span data-ttu-id="febae-256">呼叫 REST API 的範例程式碼：</span><span class="sxs-lookup"><span data-stu-id="febae-256">Sample code to call the REST API:</span></span>

- <span data-ttu-id="febae-257">**方法**：POST</span><span class="sxs-lookup"><span data-stu-id="febae-257">**Method**: POST</span></span>
- <span data-ttu-id="febae-258">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="febae-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="febae-259">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="febae-259">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="febae-260">**本文**：</span><span class="sxs-lookup"><span data-stu-id="febae-260">**Body**:</span></span>
    
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
    
- <span data-ttu-id="febae-261">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="febae-261">**Authentication**: Basic</span></span>
- <span data-ttu-id="febae-262">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="febae-262">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="febae-263">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="febae-263">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="febae-264">可用的參數</span><span class="sxs-lookup"><span data-stu-id="febae-264">Available parameters</span></span>


|<span data-ttu-id="febae-265">參數</span><span class="sxs-lookup"><span data-stu-id="febae-265">Parameters</span></span>|<span data-ttu-id="febae-266">描述</span><span class="sxs-lookup"><span data-stu-id="febae-266">Description</span></span>|<span data-ttu-id="febae-267">附註</span><span class="sxs-lookup"><span data-stu-id="febae-267">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="febae-268"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="febae-268"><d:Name></d:Name></span></span>|<span data-ttu-id="febae-269">提供事件的唯一名稱，</span><span class="sxs-lookup"><span data-stu-id="febae-269">Provide a unique name for the event,</span></span>|<span data-ttu-id="febae-270">結尾不可包含空格或下列字元：% \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="febae-270">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="febae-271">, : ;</span><span class="sxs-lookup"><span data-stu-id="febae-271">, : ;</span></span>|
|<span data-ttu-id="febae-272"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="febae-272"><d:EventType></d:EventType></span></span>|<span data-ttu-id="febae-273">輸入事件類型名稱 (或 Guid)</span><span class="sxs-lookup"><span data-stu-id="febae-273">Enter event type name (or Guid),</span></span>|<span data-ttu-id="febae-274">範例：「員工離職」。</span><span class="sxs-lookup"><span data-stu-id="febae-274">Example: "Employee termination".</span></span> <span data-ttu-id="febae-275">事件類型必須與保留標籤相關聯。</span><span class="sxs-lookup"><span data-stu-id="febae-275">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="febae-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="febae-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="febae-277">輸入「ComplianceAssetId：」 + 「員工識別碼」</span><span class="sxs-lookup"><span data-stu-id="febae-277">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="febae-278">範例："ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="febae-278">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="febae-279"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="febae-279"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="febae-280">事件的日期和時間</span><span class="sxs-lookup"><span data-stu-id="febae-280">Event Date and Time</span></span>|<span data-ttu-id="febae-281">格式：yyyy-MM-ddTHH:mm:ssZ，例如：2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="febae-281">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="febae-282">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-282">Response codes</span></span>

| <span data-ttu-id="febae-283">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-283">Response Code</span></span> | <span data-ttu-id="febae-284">描述</span><span class="sxs-lookup"><span data-stu-id="febae-284">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="febae-285">302</span><span class="sxs-lookup"><span data-stu-id="febae-285">302</span></span>               | <span data-ttu-id="febae-286">重新導向</span><span class="sxs-lookup"><span data-stu-id="febae-286">Redirect</span></span>              |
| <span data-ttu-id="febae-287">201</span><span class="sxs-lookup"><span data-stu-id="febae-287">201</span></span>               | <span data-ttu-id="febae-288">建立時間</span><span class="sxs-lookup"><span data-stu-id="febae-288">Created</span></span>               |
| <span data-ttu-id="febae-289">403</span><span class="sxs-lookup"><span data-stu-id="febae-289">403</span></span>               | <span data-ttu-id="febae-290">授權失敗</span><span class="sxs-lookup"><span data-stu-id="febae-290">Authorization Failed</span></span>  |
| <span data-ttu-id="febae-291">401</span><span class="sxs-lookup"><span data-stu-id="febae-291">401</span></span>               | <span data-ttu-id="febae-292">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="febae-292">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="febae-293">依據時間範圍取得事件</span><span class="sxs-lookup"><span data-stu-id="febae-293">Get events based on a time range</span></span>

- <span data-ttu-id="febae-294">**方法**：GET</span><span class="sxs-lookup"><span data-stu-id="febae-294">**Method**: GET</span></span>

- <span data-ttu-id="febae-295">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="febae-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="febae-296">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="febae-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="febae-297">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="febae-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="febae-298">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="febae-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="febae-299">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="febae-299">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="febae-300">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-300">Response codes</span></span>

| <span data-ttu-id="febae-301">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-301">Response Code</span></span> | <span data-ttu-id="febae-302">描述</span><span class="sxs-lookup"><span data-stu-id="febae-302">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="febae-303">200</span><span class="sxs-lookup"><span data-stu-id="febae-303">200</span></span>               | <span data-ttu-id="febae-304">好的，以 atom+ xml 格式列出事件清單</span><span class="sxs-lookup"><span data-stu-id="febae-304">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="febae-305">404</span><span class="sxs-lookup"><span data-stu-id="febae-305">404</span></span>               | <span data-ttu-id="febae-306">找不到</span><span class="sxs-lookup"><span data-stu-id="febae-306">Not found</span></span>                         |
| <span data-ttu-id="febae-307">302</span><span class="sxs-lookup"><span data-stu-id="febae-307">302</span></span>               | <span data-ttu-id="febae-308">重新導向</span><span class="sxs-lookup"><span data-stu-id="febae-308">Redirect</span></span>                          |
| <span data-ttu-id="febae-309">401</span><span class="sxs-lookup"><span data-stu-id="febae-309">401</span></span>               | <span data-ttu-id="febae-310">授權失敗</span><span class="sxs-lookup"><span data-stu-id="febae-310">Authorization Failed</span></span>              |
| <span data-ttu-id="febae-311">403</span><span class="sxs-lookup"><span data-stu-id="febae-311">403</span></span>               | <span data-ttu-id="febae-312">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="febae-312">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="febae-313">依 ID 取得事件</span><span class="sxs-lookup"><span data-stu-id="febae-313">Get an event by ID</span></span>

- <span data-ttu-id="febae-314">**方法**：GET</span><span class="sxs-lookup"><span data-stu-id="febae-314">**Method**: GET</span></span>

- <span data-ttu-id="febae-315">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="febae-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="febae-316">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="febae-316">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="febae-317">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="febae-317">**Authentication**: Basic</span></span>

- <span data-ttu-id="febae-318">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="febae-318">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="febae-319">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="febae-319">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="febae-320">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-320">Response codes</span></span>

| <span data-ttu-id="febae-321">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-321">Response Code</span></span> | <span data-ttu-id="febae-322">描述</span><span class="sxs-lookup"><span data-stu-id="febae-322">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="febae-323">200</span><span class="sxs-lookup"><span data-stu-id="febae-323">200</span></span>               | <span data-ttu-id="febae-324">好的，回應本文包含有 atom+xml 格式的事件</span><span class="sxs-lookup"><span data-stu-id="febae-324">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="febae-325">404</span><span class="sxs-lookup"><span data-stu-id="febae-325">404</span></span>               | <span data-ttu-id="febae-326">找不到</span><span class="sxs-lookup"><span data-stu-id="febae-326">Not found</span></span>                                            |
| <span data-ttu-id="febae-327">302</span><span class="sxs-lookup"><span data-stu-id="febae-327">302</span></span>               | <span data-ttu-id="febae-328">重新導向</span><span class="sxs-lookup"><span data-stu-id="febae-328">Redirect</span></span>                                             |
| <span data-ttu-id="febae-329">401</span><span class="sxs-lookup"><span data-stu-id="febae-329">401</span></span>               | <span data-ttu-id="febae-330">授權失敗</span><span class="sxs-lookup"><span data-stu-id="febae-330">Authorization Failed</span></span>                                 |
| <span data-ttu-id="febae-331">403</span><span class="sxs-lookup"><span data-stu-id="febae-331">403</span></span>               | <span data-ttu-id="febae-332">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="febae-332">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="febae-333">依名稱取得事件</span><span class="sxs-lookup"><span data-stu-id="febae-333">Get an event by name</span></span>

- <span data-ttu-id="febae-334">**方法**：GET</span><span class="sxs-lookup"><span data-stu-id="febae-334">**Method**: GET</span></span>

- <span data-ttu-id="febae-335">**URL**：`https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="febae-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="febae-336">**標頭**：Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="febae-336">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="febae-337">**驗證**：基本</span><span class="sxs-lookup"><span data-stu-id="febae-337">**Authentication**: Basic</span></span>

- <span data-ttu-id="febae-338">**使用者名稱**："Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="febae-338">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="febae-339">**密碼**："Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="febae-339">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="febae-340">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-340">Response codes</span></span>

| <span data-ttu-id="febae-341">回應碼</span><span class="sxs-lookup"><span data-stu-id="febae-341">Response Code</span></span> | <span data-ttu-id="febae-342">描述</span><span class="sxs-lookup"><span data-stu-id="febae-342">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="febae-343">200</span><span class="sxs-lookup"><span data-stu-id="febae-343">200</span></span>               | <span data-ttu-id="febae-344">好的，回應本文包含有 atom+xml 格式的事件</span><span class="sxs-lookup"><span data-stu-id="febae-344">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="febae-345">404</span><span class="sxs-lookup"><span data-stu-id="febae-345">404</span></span>               | <span data-ttu-id="febae-346">找不到</span><span class="sxs-lookup"><span data-stu-id="febae-346">Not found</span></span>                                            |
| <span data-ttu-id="febae-347">302</span><span class="sxs-lookup"><span data-stu-id="febae-347">302</span></span>               | <span data-ttu-id="febae-348">重新導向</span><span class="sxs-lookup"><span data-stu-id="febae-348">Redirect</span></span>                                             |
| <span data-ttu-id="febae-349">401</span><span class="sxs-lookup"><span data-stu-id="febae-349">401</span></span>               | <span data-ttu-id="febae-350">授權失敗</span><span class="sxs-lookup"><span data-stu-id="febae-350">Authorization Failed</span></span>                                 |
| <span data-ttu-id="febae-351">403</span><span class="sxs-lookup"><span data-stu-id="febae-351">403</span></span>               | <span data-ttu-id="febae-352">驗證失敗</span><span class="sxs-lookup"><span data-stu-id="febae-352">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="febae-353">使用 PowerShell 或任何 HTTP 用戶端來建立事件</span><span class="sxs-lookup"><span data-stu-id="febae-353">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="febae-354">PowerShell 必須是版本6或更新版本。</span><span class="sxs-lookup"><span data-stu-id="febae-354">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="febae-355">在 PowerShell 工作階段中，執行下列腳本：</span><span class="sxs-lookup"><span data-stu-id="febae-355">In a PowerShell session, run the following script:</span></span>

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

