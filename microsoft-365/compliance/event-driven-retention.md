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
description: 使用保留標籤，您可以讓發生特定類型事件的時間作為保留期間的依據。事件會觸發啟動保留期間，具有套用至該類型事件之保留標籤的所有事件，會強制執行標籤的保留動作。事件導向保留通常是作為記錄管理處理程序的一部分。
ms.openlocfilehash: da5e10735e8980199a829ac50d096052abe93d14
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074495"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="5df5d-105">事件導向保留的概觀</span><span class="sxs-lookup"><span data-stu-id="5df5d-105">Overview of event-driven retention</span></span>

<span data-ttu-id="5df5d-p102">當您保留內容時，保留期間通常是依據內容的存留期 - 例如，您在文件建立之後保留 7 年，然後刪除。但是使用 Office 365 中的保留標籤，您也可以讓發生特定類型事件的時間作為保留期間的依據。事件會觸發啟動保留期間，具有套用至該類型事件之保留標籤的所有事件，會強制執行標籤的保留動作。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p102">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them. But with retention labels in Office 365, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="5df5d-109">例如，您可以針對下列項目，使用具有事件導向保留的標籤：</span><span class="sxs-lookup"><span data-stu-id="5df5d-109">For example, you can use labels with event-driven retention for:</span></span>
  
- <span data-ttu-id="5df5d-p103">**員工離開組織**假設員工記錄必須從員工離開組織之後開始保留 10 年。經過 10 年之後，與該員工雇用、績效及離職相關的所有文件都需要處置。觸發 10 年保留期間的事件是員工離開組織。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p103">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization. After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed. The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="5df5d-p104">**合約到期**假設與合約相關的所有記錄必須從合約到期時間起保留 5 年。觸發 5 年保留期間的事件是合約到期日。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p104">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="5df5d-p105">**產品生命週期**貴組織可能有與產品最後製造日期相關的保留需求，例如技術規格。在此情況下，最後製造日期是觸發保留期間的事件。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p105">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="5df5d-p106">事件導向保留通常作為記錄管理處理程序的一部分。這表示：</span><span class="sxs-lookup"><span data-stu-id="5df5d-p106">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="5df5d-p107">根據事件的標籤通常也會將內容分類為記錄。如需詳細資訊，請參閱[使用內容搜尋來尋找套用特定保留標籤的所有內容](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it)。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p107">Labels based on events also usually classify content as a record. For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span></span>
    
- <span data-ttu-id="5df5d-121">已宣告為記錄但是其事件觸發程序尚未發生的文件，會無限期保留 (記錄無法永久刪除)，直到事件觸發該文件的保留期間。</span><span class="sxs-lookup"><span data-stu-id="5df5d-121">A document that's been declared as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="5df5d-p108">根據事件的標籤通常會在保留期間結束時觸發處置檢閱，讓記錄管理員可以手動檢查並處置內容。如需詳細資訊，請參閱[處置檢閱概觀](disposition-reviews.md)。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p108">Labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content. For more information, see [Overview of disposition reviews](disposition-reviews.md).</span></span>
    
<span data-ttu-id="5df5d-p109">根據事件的標籤具有與 Office 365 中的任何標籤相同的功能。若要深入了解，請參閱[標籤概觀](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p109">A label based on an event has the same capabilities as any label in Office 365. To learn more, see [Overview of labels](labels.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="5df5d-126">了解事件類型、標籤、事件和資產識別碼之間的關聯性</span><span class="sxs-lookup"><span data-stu-id="5df5d-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="5df5d-p110">若要成功使用事件導向保留，請務必了解如下所示的事件類型、標籤、事件和資產識別碼之間的關聯性。圖表後有說明。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p110">To successfully use event-driven retention, it's important to understand the relationship between event types, labels, events, and asset IDs as illustrated here. An explanation follows the diagram.</span></span>
  
![事件類型、標籤、事件和資產識別碼的圖表](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件類型、標籤、事件和資產識別碼的圖表](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="5df5d-p111">建立不同類型內容的標籤，然後將其與事件類型產生關聯。例如，不同類型產品檔案和記錄的標籤會與名為「產品生命週期」的事件類型相關聯，因為這些記錄必須從產品達到其生命週期結束開始保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p111">You create labels for different types of content and then associate them with a type of event. For example, labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="5df5d-p112">使用者 (通常是記錄管理員) 將標籤套用至內容和 (適用於 SharePoint 和 OneDrive 文件) 輸入每個項目的資產識別碼。在此範例中，資產識別碼是組織所使用的產品名稱或代碼。因此，每個產品的記錄會獲得指派標籤，而每一筆記錄具有包含資產識別碼的屬性。圖表代表組織中所有產品記錄的**所有內容**，每個項目都帶有記錄中產品的資產識別碼。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p112">Users (typically records managers) apply those labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item. In this example, the asset ID is a product name or code used by the organization. Thus, each product's records are assigned a label, and each record has a property that contains an asset ID. The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="5df5d-p113">產品生命週期是事件類型；達到生命週期結尾的特定產品是事件。該事件類型的事件發生時 - 在此情況下，當產品達到其生命週期結尾時 - 您建立事件，指定：</span><span class="sxs-lookup"><span data-stu-id="5df5d-p113">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="5df5d-139">資產識別碼 (適用於 SharePoint 和 OneDrive 文件)</span><span class="sxs-lookup"><span data-stu-id="5df5d-139">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="5df5d-p114">關鍵字 (適用於 Exchange 項目)。在此範例中，組織在包含產品記錄的訊息中使用產品代碼，因此 Exchange 項目的關鍵字與 SharePoint 和 OneDrive 文件中的資產識別碼相同。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p114">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="5df5d-p115">發生事件的日期。此日期作為保留期間的開始日期。此日期可能是目前、過去或未來的日期。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p115">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>
    
4. <span data-ttu-id="5df5d-p116">在您建立事件之後，事件日期會同步處理至具有該事件類型標籤和包含指定資產識別碼或關鍵字的所有內容。與其他任何標籤一樣，這個同步處理最多會耗費 7 天的時間。在上圖中，用紅色圈起來的所有項目具有由此事件觸發的保留期間，換句話說，當此產品達到其生命週期結尾時，該事件會觸發該產品記錄的保留期間。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p116">After you create an event, that event date is synced to all of the content that has a label of that event type and that contains the specified asset ID or keyword. Like any label, this syncing can take up to 7 days. In the diagram above, all of the items circled in red have their retention period triggered by this event - in other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="5df5d-p117">請務必了解如果您未指定資產識別碼或事件的關鍵字，具有該事件類型標籤的**所有內容**將會具有由事件觸發的保留期間。這表示在上圖中，所有內容都會開始保留。這可能不是您想要的結果。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p117">It's important to understand that if you don't specify an asset ID or keywords for an event, **all of the content** with a label of that event type will have its retention period triggered by the event. This means that in the diagram above, all of the content would start being retained. This may not be what you intend.</span></span> 
  
<span data-ttu-id="5df5d-p118">最後請記住，每個標籤具有自己的保留設定。在此範例中，全部都指定 10 年，但是事件有可能觸發具有不同保留期間的標籤。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p118">Finally, remember that each label has its own retention settings. In this example, they all specify 10 years, but it's possible for an event to trigger labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="5df5d-153">如何設定事件導向保留</span><span class="sxs-lookup"><span data-stu-id="5df5d-153">How to set up event-driven retention</span></span>

<span data-ttu-id="5df5d-p119">以下是事件導向保留的高階工作流程。隨後是更詳細的步驟。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p119">Here's the high-level workflow for event-driven retention. More detailed steps follow below.</span></span>
  
![設定事件導向保留工作流程的圖表](../media/161146d9-e0fc-4248-abc1-a18045eaad5c.png)
  
> [!TIP]
> <span data-ttu-id="5df5d-157">請參閱[管理具有保留標籤之 SharePoint 文件的生命週期](auto-apply-retention-labels-scenario.md)，以了解使用 SharePoint 中受管理屬性來自動套用保留標籤和實作事件導向保留的詳細案例。</span><span class="sxs-lookup"><span data-stu-id="5df5d-157">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePont to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="5df5d-158">步驟 1：建立其保留期間根據事件的標籤</span><span class="sxs-lookup"><span data-stu-id="5df5d-158">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="5df5d-159">在 Microsoft 365 合規性中心、Microsoft 365 安全性中心或 Office 365 安全性 &amp; 合規性中心的左側導覽列中，選擇 \*\* [分類]\*\* >  **[保留標籤]** >  **[標籤]** 索引標籤 > **[建立標籤]**。</span><span class="sxs-lookup"><span data-stu-id="5df5d-159">In the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security &amp; Compliance Center, in the left navigation, choose **Classification** > **Retention labels** > **Labels** tab > **Create a label**.</span></span>
  
<span data-ttu-id="5df5d-p120">當您建立標籤時，開啟保留，然後如下所示選擇選項，以根據事件保留或刪除內容。這表示當您在 [事件]\*\*\*\* 頁面上建立事件時，保留設定在 9 月 5 日之前不會生效。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p120">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event. This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="5df5d-p121">請注意，事件導向保留通常是用於分類為記錄的內容。基於這個原因，當您根據事件建立標籤時，通常會選擇選項 [使用標籤將內容分類為「記錄」]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p121">Note that event-driven retention is typically used for content that's classified as a record. For this reason, when you create labels based on an event, you typically choose the option to **Use label to classify content as a "Record"**.</span></span>
  
<span data-ttu-id="5df5d-164">另請注意，事件導向保留需要保留設定：</span><span class="sxs-lookup"><span data-stu-id="5df5d-164">Also note that event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="5df5d-165">保留內容。</span><span class="sxs-lookup"><span data-stu-id="5df5d-165">Retain the content.</span></span>
    
- <span data-ttu-id="5df5d-166">自動刪除內容或在保留期間結束時觸發處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="5df5d-166">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![讓標籤以事件為依據的選項](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="5df5d-168">步驟 2：選擇該標籤的事件類型</span><span class="sxs-lookup"><span data-stu-id="5df5d-168">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="5df5d-p122">在標籤設定中，當您選擇以**事件**作為標籤的依據選項之後，您會看到選項 [選擇事件類型]\*\*\*\*。事件類型只是您想要與標籤產生關聯之事件的一般說明。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p122">In the label settings, after you choose the option to base the label on **an event**, you'll see the option to **Choose an event type**. An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="5df5d-171">例如，如果您建立名為「產品生命週期」的事件類型，您會建立事件型標籤，具有名稱說明您想要將標籤套用到什麼類型的內容，例如「產品開發檔案」或「產品業務決策記錄」。</span><span class="sxs-lookup"><span data-stu-id="5df5d-171">For example, if you create an event type named Product Lifetime, you'll create event-based labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>
  
<span data-ttu-id="5df5d-172">請注意，一旦您選擇事件類型並建立標籤，就無法變更事件類型。</span><span class="sxs-lookup"><span data-stu-id="5df5d-172">Note that once you choose an event type and create the label, the event type cannot be changed.</span></span>
  
![建立或選擇事件類型的選項](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-label"></a><span data-ttu-id="5df5d-174">步驟 3：發佈或自動套用標籤</span><span class="sxs-lookup"><span data-stu-id="5df5d-174">Step 3: Publish or auto-apply the label</span></span>

<span data-ttu-id="5df5d-175">就像任何標籤，您必須發佈或自動套用以事件為基礎的標籤，這樣標籤才會手動或自動套用到內容。</span><span class="sxs-lookup"><span data-stu-id="5df5d-175">Just like any label, you need to publish or auto-apply an event-based label, so that it's manually or automatically applied to content.</span></span> <span data-ttu-id="5df5d-176">您可以在 [分類]\*\*\*\* >  [保留標籤]\*\*\*\* 頁面下進行這項操作。</span><span class="sxs-lookup"><span data-stu-id="5df5d-176">You can do this under **Classification** > **Retention labels** page.</span></span>
  
![發佈或自動套用保留標籤的選項](../media/options-to-publish-auto-apply-retention-label.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="5df5d-178">步驟 4：輸入資產識別碼</span><span class="sxs-lookup"><span data-stu-id="5df5d-178">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="5df5d-p124">在事件導向標籤套用到內容之後，您可以為每個項目輸入資產識別碼。例如，貴組織可能會使用：</span><span class="sxs-lookup"><span data-stu-id="5df5d-p124">After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:</span></span>
  
- <span data-ttu-id="5df5d-181">產品代碼，您可以用來保留僅限特定產品的內容。</span><span class="sxs-lookup"><span data-stu-id="5df5d-181">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="5df5d-182">專案代碼，您可以用來保留僅限特定專案的內容。</span><span class="sxs-lookup"><span data-stu-id="5df5d-182">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="5df5d-183">員工識別碼，您可以用來保留僅限特定人員的內容。</span><span class="sxs-lookup"><span data-stu-id="5df5d-183">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="5df5d-p125">了解 Asset ID 只是 SharePoint 和商務用 OneDrive 中的另一個文件屬性。貴組織可能已經使用其他文件屬性和識別碼來分類內容。若是如此，您也可以在建立事件時使用這些屬性和值 - 請參閱下方的步驟 6。重點是貴組織必須在文件中使用一些 property:value 組合，以便讓該項目與事件類型產生關聯。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p125">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business. Your organization may already use other document properties and IDs to classify content. If so, you can also use those properties and values when you create an event - see Step 6 below. The important point is that your organization must use some property:value combination in the document properties to associate that item with an event type.</span></span>
  
![在其中輸入資產識別碼的文字方塊](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="5df5d-189">步驟 5：建立事件</span><span class="sxs-lookup"><span data-stu-id="5df5d-189">Step 5: Create an event</span></span>

<span data-ttu-id="5df5d-p126">發生該事件類型的特定執行個體時 - 例如，產品達到其生命週期的結尾 - 請移至安全性 &amp; 合規性中心中的 [記錄管理]\*\*\*\* >  [事件]\*\*\*\* 頁面，並且建立事件。您需要藉由建立它來手動觸發事件。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p126">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Security &amp; Compliance Center and create an event. You need to manually trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="5df5d-192">步驟 6：選擇與步驟 2 中的標籤所使用相同的事件類型</span><span class="sxs-lookup"><span data-stu-id="5df5d-192">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="5df5d-p127">當您建立事件時，選擇與步驟 2 中的標籤所使用相同的事件類型 - 例如，產品生命週期。只有標籤套用至該事件類型的內容，會觸發其保留期間。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p127">When you create the event, choose the same event type used by the label in step 2 - for example, Product Lifetime. Only content with labels applied to it of that event type will have its retention period triggered.</span></span>
  
![在事件設定中選擇事件類型的選項](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="5df5d-196">步驟 7：輸入關鍵字或資產識別碼</span><span class="sxs-lookup"><span data-stu-id="5df5d-196">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="5df5d-p128">現在您可以藉由指定資產識別碼 (適用於 SharePoint 和 OneDrive 內容) 或關鍵字 (適用於 Exchange 內容)，來縮小內容的範圍。對於資產識別碼，只會在具有指定 property:value 配對的內容上強制執行保留。如果未輸入資產識別碼，具有該事件類型標籤的**所有內容**都會套用相同的保留日期。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p128">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all of the content** with labels of that event type get the same retention date applied to them.</span></span> 
  
<span data-ttu-id="5df5d-p129">了解 Asset ID 只是 SharePoint 和商務用 OneDrive 中的另一個文件屬性。如果您使用 Asset ID 屬性，您要在資產識別碼的方塊中輸入 ComplianceAssetID:\<value\>，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p129">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business. If you're using the Asset ID property, you would enter ComplianceAssetID:\<value\> in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="5df5d-p130">貴組織可能已將其他屬性和識別碼套用至與此事件類型相關的文件。例如，如果您必須偵測特定產品的記錄，識別碼可能是自訂屬性 ProductID 和值 "XYZ" 的組合。在此情況下，您要在資產識別碼的方塊中輸入 ProductID:XYZ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p130">Your organization might have applied other properties and IDs to the documents related to this event type. For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ". In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="5df5d-p131">對於 Exchange 項目，您可以包含關鍵字。您可以藉由使用像是 AND、OR 和 NOT 的搜尋運算子來精簡查詢。如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p131">For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="5df5d-p132">最後，請選擇發生事件的日期；此日期會作為保留期間的開始日期。在您建立事件之後，該事件日期會同步處理至具有該事件類型標籤、資產識別碼和關鍵字的所有內容。就像任何標籤一樣，此同步處理會耗費最多 7 天的時間。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p132">Finally, choose the date when the event occurred; this date is used as the start of the retention period. After you create an event, that event date is synced to all of the content with a label of that event type, asset ID, and keywords. Like any label, this syncing can take up to 7 days.</span></span>
  
![事件設定頁面](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="5df5d-212">使用內容搜尋來尋找具有特定標籤或資產識別碼的所有內容</span><span class="sxs-lookup"><span data-stu-id="5df5d-212">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="5df5d-213">將標籤指派給內容之後，您可以使用內容搜尋，尋找以特定標籤分類或包含特定資產識別碼的所有內容。</span><span class="sxs-lookup"><span data-stu-id="5df5d-213">After labels are assigned to content, you can use content search to find all content that's classified with a specific label or that contains a specific asset ID.</span></span>
  
<span data-ttu-id="5df5d-214">當您建立內容搜尋時：</span><span class="sxs-lookup"><span data-stu-id="5df5d-214">When you create a content search:</span></span>
  
- <span data-ttu-id="5df5d-215">若要尋找具有特定標籤的所有內容時，請選擇**合規性標記**條件，然後輸入完整標籤名稱或，或輸入部分標籤名稱並使用萬用字元。</span><span class="sxs-lookup"><span data-stu-id="5df5d-215">To find all content with a specific label, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="5df5d-216">若要尋找具有特定資產識別碼的所有內容，請輸入 **ComplianceAssetID** 屬性和值，例如 ComplianceAssetID:\<value\>。</span><span class="sxs-lookup"><span data-stu-id="5df5d-216">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, like ComplianceAssetID:\<value\>.</span></span> 
    
<span data-ttu-id="5df5d-217">如需詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="5df5d-217">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="5df5d-218">權限</span><span class="sxs-lookup"><span data-stu-id="5df5d-218">Permissions</span></span>

<span data-ttu-id="5df5d-p133">若要取得 [事件]\*\*\*\* 頁面的存取權，檢閱者必須是具有**處置管理**角色和**僅限檢視稽核記錄**角色之角色群組的成員。我們建議建立稱為「處置檢閱者」的新角色群組，將這兩個角色新增至該角色群組，然後將成員新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p133">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="5df5d-221">如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5df5d-221">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="5df5d-222">使用 PowerShell 讓事件自動化</span><span class="sxs-lookup"><span data-stu-id="5df5d-222">Automate events by using PowerShell</span></span>

<span data-ttu-id="5df5d-p134">在系統管理中心內，您只能手動建立事件；無法在事件發生時自動觸發事件。但是，您可以使用 Rest API 來自動觸發事件；如需詳細資訊，請參閱[自動化事件型保留](automate-event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="5df5d-p134">In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs. However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).</span></span>

<span data-ttu-id="5df5d-225">您也可以使用 PowerShell 指令碼來自動化商務應用程式中以事件為基礎的保留。</span><span class="sxs-lookup"><span data-stu-id="5df5d-225">You can also use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="5df5d-226">以下是適用於事件導向保留的 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5df5d-226">Here are the PowerShell cmdlets available for event-driven retention:</span></span>
  
- [<span data-ttu-id="5df5d-227">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="5df5d-227">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="5df5d-228">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="5df5d-228">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="5df5d-229">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="5df5d-229">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="5df5d-230">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="5df5d-230">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="5df5d-231">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="5df5d-231">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="5df5d-232">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="5df5d-232">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

