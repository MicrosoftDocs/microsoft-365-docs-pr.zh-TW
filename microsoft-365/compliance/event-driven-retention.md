---
title: 事件導向保留的概觀
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
ms.openlocfilehash: a0e0025d23bda36d8b9e6315cb932e58d4237a5c
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068122"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="cbe53-103">事件導向保留的概觀</span><span class="sxs-lookup"><span data-stu-id="cbe53-103">Overview of event-driven retention</span></span>

><span data-ttu-id="cbe53-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="cbe53-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="cbe53-105">When you retain content, the retention period is often based on the age of the content.</span><span class="sxs-lookup"><span data-stu-id="cbe53-105">When you retain content, the retention period is often based on the age of the content.</span></span> <span data-ttu-id="cbe53-106">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="cbe53-106">For example, you might retain documents for seven years after they're created and then delete them.</span></span> <span data-ttu-id="cbe53-107">But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs.</span><span class="sxs-lookup"><span data-stu-id="cbe53-107">But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs.</span></span> <span data-ttu-id="cbe53-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="cbe53-108">The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="cbe53-109">使用事件導向保留的範例：</span><span class="sxs-lookup"><span data-stu-id="cbe53-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="cbe53-110">**員工離開組織** 假設員工記錄必須從員工離開組織起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="cbe53-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="cbe53-111">經過 10 年之後，所有與該名員工相關的雇用、績效和離職文件都必須加以處置。</span><span class="sxs-lookup"><span data-stu-id="cbe53-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="cbe53-112">會觸發 10 年保留期間的事件是員工離開組織。</span><span class="sxs-lookup"><span data-stu-id="cbe53-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="cbe53-113">**合約到期** 假設與合約相關的所有記錄必須從合約到期時間起保留五年。</span><span class="sxs-lookup"><span data-stu-id="cbe53-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="cbe53-114">會觸發五年保留期間的事件是合約到期。</span><span class="sxs-lookup"><span data-stu-id="cbe53-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="cbe53-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span><span class="sxs-lookup"><span data-stu-id="cbe53-115">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications.</span></span> <span data-ttu-id="cbe53-116">In this case, the last manufacturing date is the event that triggers the retention period.</span><span class="sxs-lookup"><span data-stu-id="cbe53-116">In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="cbe53-117">Event-driven retention is typically used as part of a records-management process.</span><span class="sxs-lookup"><span data-stu-id="cbe53-117">Event-driven retention is typically used as part of a records-management process.</span></span> <span data-ttu-id="cbe53-118">This means that:</span><span class="sxs-lookup"><span data-stu-id="cbe53-118">This means that:</span></span>
  
- <span data-ttu-id="cbe53-119">根據事件的標籤通常也會將內容分類為記錄。</span><span class="sxs-lookup"><span data-stu-id="cbe53-119">Labels based on events also usually classify content as a record.</span></span> <span data-ttu-id="cbe53-120">如需詳細資訊，請參閱[了解記錄](records.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe53-120">For more information, see [Learn about records](records.md).</span></span>
    
- <span data-ttu-id="cbe53-121">已分類為記錄但是其事件觸發程序尚未發生的文件，會無限期保留 (記錄無法永久刪除)，直到事件觸發該文件的保留期間。</span><span class="sxs-lookup"><span data-stu-id="cbe53-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="cbe53-122">根據事件的保留標籤通常會在保留期間結束時觸發處置檢閱，這樣記錄管理員就能手動檢閱並處置內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="cbe53-123">如需詳細資訊，請參閱[處置內容](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe53-123">For more information, see [Disposition of content](disposition.md).</span></span>
    
<span data-ttu-id="cbe53-124">根據事件的保留標籤與 Microsoft 365 中任何保留標籤具有相同的功能。</span><span class="sxs-lookup"><span data-stu-id="cbe53-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="cbe53-125">如需詳細資訊，請參閱[[瞭解保留標籤]](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe53-125">For more information, see [Learn about retention labels](labels.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="cbe53-126">了解事件類型、標籤、事件和資產識別碼之間的關聯性</span><span class="sxs-lookup"><span data-stu-id="cbe53-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="cbe53-127">若要成功使用事件導向保留，請務必了解事件類型、保留標籤、事件和資產識別碼之間的關聯性，如下列圖表所示且圖表後有說明。</span><span class="sxs-lookup"><span data-stu-id="cbe53-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![事件類型、標籤、事件和資產識別碼的圖表](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件類型、標籤、事件和資產識別碼的圖表](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="cbe53-130">您為各種類型的內容建立保留標籤，然後將其與某種事件類型建立關聯。</span><span class="sxs-lookup"><span data-stu-id="cbe53-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="cbe53-131">例如，不同類型產品檔案和記錄的保留標籤會與名為「產品生命週期」的事件類型相關聯，因為這些記錄必須從產品達到其生命週期結束開始保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="cbe53-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="cbe53-132">使用者 (通常是記錄管理員) 會將這些保留標籤套用到內容，並且 (若是 SharePoint 和 OneDrive 文件) 為每個項目輸入資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="cbe53-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="cbe53-133">在此範例中，資產識別碼是組織所使用的產品名稱或代碼。</span><span class="sxs-lookup"><span data-stu-id="cbe53-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="cbe53-134">因此，每個產品的記錄都會獲派一個保留標籤，而每筆記錄都會有包含資產識別碼的屬性。</span><span class="sxs-lookup"><span data-stu-id="cbe53-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="cbe53-135">此圖表描繪組織中所有產品記錄的**所有內容**，而每個項目都會承載記錄所屬產品的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="cbe53-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="cbe53-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span><span class="sxs-lookup"><span data-stu-id="cbe53-136">Product Lifetime is the event type; a specific product reaching end of life is an event.</span></span> <span data-ttu-id="cbe53-137">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span><span class="sxs-lookup"><span data-stu-id="cbe53-137">When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="cbe53-138">資產識別碼 (適用於 SharePoint 和 OneDrive 文件)</span><span class="sxs-lookup"><span data-stu-id="cbe53-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="cbe53-139">Keywords (for Exchange items).</span><span class="sxs-lookup"><span data-stu-id="cbe53-139">Keywords (for Exchange items).</span></span> <span data-ttu-id="cbe53-140">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span><span class="sxs-lookup"><span data-stu-id="cbe53-140">In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="cbe53-141">The date when the event occurred.</span><span class="sxs-lookup"><span data-stu-id="cbe53-141">The date when the event occurred.</span></span> <span data-ttu-id="cbe53-142">This date is used as the start of the retention period.</span><span class="sxs-lookup"><span data-stu-id="cbe53-142">This date is used as the start of the retention period.</span></span> <span data-ttu-id="cbe53-143">This date can be the current, a past, or a future date.</span><span class="sxs-lookup"><span data-stu-id="cbe53-143">This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="cbe53-144">建立事件之後，該事件日期會同步處理到保留標籤屬於該事件類型的所有內容，以及包含指定資產識別碼或關鍵字的所有內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="cbe53-145">如同任何保留標籤，同步處理最多可能需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="cbe53-145">Like any retention label, this synchronization can take up to 7 days.</span></span> <span data-ttu-id="cbe53-146">上圖中以紅色圈出的所有項目，其保留期間都是由此事件觸發。</span><span class="sxs-lookup"><span data-stu-id="cbe53-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="cbe53-147">換句話說，當這項產品的生命週期結束時，該事件會觸發該產品記錄的保留期間。</span><span class="sxs-lookup"><span data-stu-id="cbe53-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="cbe53-148">請務必了解，如果您沒有為事件指定資產識別碼或關鍵字，具有該事件類型之標籤的**所有內容**都將有其被事件觸發的保留期間。</span><span class="sxs-lookup"><span data-stu-id="cbe53-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="cbe53-149">這表示在上圖中，所有內容都會開始進行保留。</span><span class="sxs-lookup"><span data-stu-id="cbe53-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="cbe53-150">這可能不是您原本的打算。</span><span class="sxs-lookup"><span data-stu-id="cbe53-150">This might not be what you intend.</span></span> 
  
<span data-ttu-id="cbe53-151">最後，請記住，每個保留標籤都有自己的保留設定。</span><span class="sxs-lookup"><span data-stu-id="cbe53-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="cbe53-152">在此範例中，全都指定 10 年，但有可能事件觸發的保留標籤是每個標籤都有不同的保留期間。</span><span class="sxs-lookup"><span data-stu-id="cbe53-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="cbe53-153">如何設定事件導向保留</span><span class="sxs-lookup"><span data-stu-id="cbe53-153">How to set up event-driven retention</span></span>

<span data-ttu-id="cbe53-154">事件導向保留的整體工作流程：</span><span class="sxs-lookup"><span data-stu-id="cbe53-154">High-level workflow for event-driven retention:</span></span>
  
![設定事件導向保留工作流程的圖表](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="cbe53-156">請參閱[管理具有保留標籤之 SharePoint 文件的生命週期](auto-apply-retention-labels-scenario.md)，以了解使用 SharePoint 中受管理屬性來自動套用保留標籤和實作事件導向保留的詳細案例。</span><span class="sxs-lookup"><span data-stu-id="cbe53-156">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="cbe53-157">步驟 1：建立其保留期間根據事件的標籤</span><span class="sxs-lookup"><span data-stu-id="cbe53-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="cbe53-158">若要建立及設定您的保留標籤，請使用[建立及設定保留標籤](create-retention-labels.md#create-and-configure-retention-labels)的相關指示，並在開啟保留時，選擇根據事件保留或刪除內容的選項。</span><span class="sxs-lookup"><span data-stu-id="cbe53-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="cbe53-159">此設定表示當您在 [事件]\*\*\*\* 頁面上建立事件時，保留設定在步驟 5 之前都不會生效。</span><span class="sxs-lookup"><span data-stu-id="cbe53-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="cbe53-160">事件導向的保留通常是用於分類為記錄的內容，因此很適合用來檢查您是否也需要選取將內容標示為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="cbe53-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="cbe53-161">事件導向保留需要保留設定：</span><span class="sxs-lookup"><span data-stu-id="cbe53-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="cbe53-162">保留內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-162">Retain the content.</span></span>
    
- <span data-ttu-id="cbe53-163">自動刪除內容或在保留期間結束時觸發處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="cbe53-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![讓標籤以事件為依據的選項](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="cbe53-165">步驟 2：選擇該標籤的事件類型</span><span class="sxs-lookup"><span data-stu-id="cbe53-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="cbe53-166">在標籤設定中，在您選擇讓標籤根據 **[事件]** 的選項後，您會看見 **[選擇事件類型]** 的選項。</span><span class="sxs-lookup"><span data-stu-id="cbe53-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="cbe53-167">事件類型只是您要讓標籤與事件建立關聯之事件的一般描述。</span><span class="sxs-lookup"><span data-stu-id="cbe53-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="cbe53-168">例如，如果您建立名為「產品生命週期」的事件類型，您會建立事件型保留標籤，具有名稱說明您想要將標籤套用到什麼類型的內容，例如「產品開發檔案」或「產品業務決策記錄」。</span><span class="sxs-lookup"><span data-stu-id="cbe53-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="cbe53-169">選取其中一個內建的事件類型，或建立您自己的事件類型，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="cbe53-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="cbe53-170">在您選擇事件類型並儲存保留標籤之後，就無法變更事件類型。</span><span class="sxs-lookup"><span data-stu-id="cbe53-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![建立或選擇事件類型的選項](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="cbe53-172">步驟 3：發佈或自動套用事件型保留標籤</span><span class="sxs-lookup"><span data-stu-id="cbe53-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="cbe53-173">和任何保留標籤一樣，您必須[發佈或自動套用](create-retention-labels.md)事件型標籤，以便將它套用至文件或電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cbe53-173">Just like any retention label, you need to [publish or auto-apply](create-retention-labels.md) an event-based label, so it can be applied to documents or emails.</span></span>

> [!NOTE]
> <span data-ttu-id="cbe53-174">如果您是從 [記錄管理] \*\*\*\*  >  [檔案方案]\*\*\*\* 索引標籤或 [資料控管]\*\*\*\*  >  [標籤]\*\*\*\* 索引標籤選取事件型保留標籤，則 [自動套用標籤]\*\*\*\* 按鈕無法使用。</span><span class="sxs-lookup"><span data-stu-id="cbe53-174">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="cbe53-175">請勿使用這個按鈕，改用下列其中一個位置中，標籤或原則清單上的 [自動套用標籤]\*\*\*\* 選項：</span><span class="sxs-lookup"><span data-stu-id="cbe53-175">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="cbe53-176">[記錄管理]\*\*\*\*  >  [標籤原則]\*\*\*\* 索引標籤</span><span class="sxs-lookup"><span data-stu-id="cbe53-176">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="cbe53-177">**[資料控管]** > **[標籤]** 索引標籤或 **[標籤原則]** 索引標籤</span><span class="sxs-lookup"><span data-stu-id="cbe53-177">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![發佈或自動套用保留標籤的選項](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="cbe53-179">步驟 4：輸入資產識別碼</span><span class="sxs-lookup"><span data-stu-id="cbe53-179">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="cbe53-180">在事件型標籤套用到內容之後，您可以輸入每個項目的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="cbe53-180">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="cbe53-181">例如，貴組織可能使用：</span><span class="sxs-lookup"><span data-stu-id="cbe53-181">For example, your organization might use:</span></span>
  
- <span data-ttu-id="cbe53-182">產品代碼，您可以用來保留僅限特定產品的內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-182">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="cbe53-183">專案代碼，您可以用來保留僅限特定專案的內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-183">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="cbe53-184">員工識別碼，您可以用來保留僅限特定人員的內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-184">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="cbe53-185">資產識別碼只是 SharePoint 和 OneDrive 中可用的另一個文件屬性。</span><span class="sxs-lookup"><span data-stu-id="cbe53-185">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="cbe53-186">貴組織可能已經使用其他文件屬性和識別碼來分類內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-186">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="cbe53-187">若是如此，您也可以在建立事件時使用這些屬性和值，請參閱後續的步驟 6。</span><span class="sxs-lookup"><span data-stu-id="cbe53-187">If so, you can also use those properties and values when you create an event - see step 6 that follows.</span></span> <span data-ttu-id="cbe53-188">重點是，您必須在文件屬性中使用一些 *property:value* 組合，以將該項目與事件類型建立關聯。</span><span class="sxs-lookup"><span data-stu-id="cbe53-188">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![在其中輸入資產識別碼的文字方塊](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="cbe53-190">步驟 5：建立事件</span><span class="sxs-lookup"><span data-stu-id="cbe53-190">Step 5: Create an event</span></span>

<span data-ttu-id="cbe53-191">發生該事件類型的特定執行個體時，例如，產品達到其生命週期的結尾，請移至 Microsoft 365 合規性中心的 [記錄管理]\*\*\*\*  >  [事件]\*\*\*\* 頁面，並建立事件。</span><span class="sxs-lookup"><span data-stu-id="cbe53-191">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="cbe53-192">您可以建立事件來觸發事件。</span><span class="sxs-lookup"><span data-stu-id="cbe53-192">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="cbe53-193">步驟 6：選擇與步驟 2 中的標籤所使用相同的事件類型</span><span class="sxs-lookup"><span data-stu-id="cbe53-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="cbe53-194">當您建立事件時，請選擇步驟 2 中保留標籤所使用的相同事件類型，例如「產品生命週期」。</span><span class="sxs-lookup"><span data-stu-id="cbe53-194">When you create the event, choose the same event type used by the retention label in step 2 - for example, Product Lifetime.</span></span> <span data-ttu-id="cbe53-195">只有已套用該事件類型保留標籤的內容會觸發其保留期間。</span><span class="sxs-lookup"><span data-stu-id="cbe53-195">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![在事件設定中選擇事件類型的選項](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="cbe53-197">步驟 7：輸入關鍵字或資產識別碼</span><span class="sxs-lookup"><span data-stu-id="cbe53-197">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="cbe53-198">現在您可以指定 SharePoint 和 OneDrive 內容的資產識別碼或 Exchange 內容的關鍵字，藉此縮小內容的範圍。</span><span class="sxs-lookup"><span data-stu-id="cbe53-198">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="cbe53-199">針對資產識別碼，只有在具有指定 *property:value* 組的內容上才會強制執行保留。</span><span class="sxs-lookup"><span data-stu-id="cbe53-199">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="cbe53-200">若未輸入資產識別碼，具有該事件類型之標籤的所有內容都會套用相同的保留日期。</span><span class="sxs-lookup"><span data-stu-id="cbe53-200">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="cbe53-201">例如：如果您使用的是 [資產識別碼] 屬性，請在以下顯示的資產識別碼方塊中輸入 `ComplianceAssetID:<value>`。</span><span class="sxs-lookup"><span data-stu-id="cbe53-201">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="cbe53-202">組織可能已將其他屬性和識別碼套用到與此事件類型相關的文件。</span><span class="sxs-lookup"><span data-stu-id="cbe53-202">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="cbe53-203">例如，如果您需要偵測特定產品的記錄，識別碼可能會是您的自訂屬性 ProductID 和值 "XYZ"。</span><span class="sxs-lookup"><span data-stu-id="cbe53-203">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="cbe53-204">在此情況下，您會在下圖所示的資產識別碼方塊中輸入 `ProductID:XYZ`。</span><span class="sxs-lookup"><span data-stu-id="cbe53-204">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="cbe53-205">若為 Exchange 項目，請使用關鍵字。</span><span class="sxs-lookup"><span data-stu-id="cbe53-205">For Exchange items, use keywords.</span></span> <span data-ttu-id="cbe53-206">您可以使用 AND、OR 和 NOT 這類搜尋運算子來使用查詢。</span><span class="sxs-lookup"><span data-stu-id="cbe53-206">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="cbe53-207">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe53-207">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="cbe53-208">最後，選擇事件的發生日期；此日期作為保留期間的開始日期。</span><span class="sxs-lookup"><span data-stu-id="cbe53-208">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="cbe53-209">建立事件之後，該事件日期會同步處理到保留標籤屬於該事件類型、具有資產識別碼和關鍵字的所有內容。</span><span class="sxs-lookup"><span data-stu-id="cbe53-209">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="cbe53-210">如同任何保留標籤，同步處理最多可能需要七天。</span><span class="sxs-lookup"><span data-stu-id="cbe53-210">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![事件設定頁面](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="cbe53-212">建立事件之後，保留設定就會對已套用標籤和已編製索引的內容生效。</span><span class="sxs-lookup"><span data-stu-id="cbe53-212">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="cbe53-213">如果在建立事件之後，將保留標籤新增至新內容，則您必須使用相同的詳細資料建立新事件。</span><span class="sxs-lookup"><span data-stu-id="cbe53-213">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="cbe53-214">刪除事件不會取消目前對已套用標籤之內容生效的保留設定。</span><span class="sxs-lookup"><span data-stu-id="cbe53-214">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="cbe53-215">若要這麼做，請建立具有相同詳細資料的新事件，但將日期保留空白。</span><span class="sxs-lookup"><span data-stu-id="cbe53-215">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="cbe53-216">使用內容搜尋來尋找具有特定標籤或資產識別碼的所有內容</span><span class="sxs-lookup"><span data-stu-id="cbe53-216">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="cbe53-217">將保留標籤指派給內容之後，您可以使用內容搜尋，尋找以特定保留標籤分類或包含特定資產識別碼的所有內容：</span><span class="sxs-lookup"><span data-stu-id="cbe53-217">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="cbe53-218">若要尋找具有特定保留標籤的所有內容時，請選擇**合規性標籤**條件，然後輸入完整標籤名稱或，或輸入部分標籤名稱並使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="cbe53-218">To find all content with a specific retention label, choose the **Compliance label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="cbe53-219">若要尋找具有特定資產識別碼的所有內容，請使用格式 `ComplianceAssetID:<value>` 輸入 **ComplianceAssetID** 屬性和值。</span><span class="sxs-lookup"><span data-stu-id="cbe53-219">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="cbe53-220">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe53-220">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="cbe53-221">權限</span><span class="sxs-lookup"><span data-stu-id="cbe53-221">Permissions</span></span>

<span data-ttu-id="cbe53-222">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span><span class="sxs-lookup"><span data-stu-id="cbe53-222">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="cbe53-223">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span><span class="sxs-lookup"><span data-stu-id="cbe53-223">We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="cbe53-224">如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe53-224">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="cbe53-225">使用 PowerShell 讓事件自動化</span><span class="sxs-lookup"><span data-stu-id="cbe53-225">Automate events by using PowerShell</span></span>

<span data-ttu-id="cbe53-226">Microsoft 365 合規性中心可讓您手動建立事件，且不支援在事件發生時自動觸發事件。</span><span class="sxs-lookup"><span data-stu-id="cbe53-226">The Microsoft 365 compliance center lets you create events manually and doesn't support automatically triggering an event when it occurs.</span></span> <span data-ttu-id="cbe53-227">不過，您可以使用 REST API 自動觸發事件。</span><span class="sxs-lookup"><span data-stu-id="cbe53-227">However, you can use a Rest API to trigger events automatically.</span></span> <span data-ttu-id="cbe53-228">如需詳細資訊，請參閱[自動化事件型保留](automate-event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="cbe53-228">For more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="cbe53-229">您也可以使用 PowerShell 指令碼來自動化商務應用程式中以事件為基礎的保留。</span><span class="sxs-lookup"><span data-stu-id="cbe53-229">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="cbe53-230">適用於事件型保留的 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="cbe53-230">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="cbe53-231">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="cbe53-231">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="cbe53-232">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="cbe53-232">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="cbe53-233">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="cbe53-233">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="cbe53-234">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="cbe53-234">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="cbe53-235">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="cbe53-235">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="cbe53-236">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="cbe53-236">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

