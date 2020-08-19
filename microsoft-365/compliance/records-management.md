---
title: 記錄管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 使用 Microsoft 365 中的記錄管理，您可以將保留時間表套用到管理保留、記錄聲明和處置的檔案計畫中。
ms.openlocfilehash: c2ff344d22286fcd865aa08344389dad6334d48d
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778321"
---
# <a name="learn-about-records-management"></a><span data-ttu-id="69844-103">了解記錄管理</span><span class="sxs-lookup"><span data-stu-id="69844-103">Learn about records management</span></span>

><span data-ttu-id="69844-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="69844-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="69844-105">所有類型的組織都需要記錄管理解決方案，用來管理其公司資料間的法規、法務及業務關鍵記錄。</span><span class="sxs-lookup"><span data-stu-id="69844-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="69844-106">Microsoft 365 中的記錄管理可幫助組織管理其法律義務，提供展現法規遵循的能力，並提高不再需要保留、不再具有價值或商業用途不再需要的項目一般處置的效率。</span><span class="sxs-lookup"><span data-stu-id="69844-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="69844-107">請使用下列功能以支援 Microsoft 365 中的記錄管理解決方案：</span><span class="sxs-lookup"><span data-stu-id="69844-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="69844-108">**標籤內容做為記錄**。</span><span class="sxs-lookup"><span data-stu-id="69844-108">**Label content as a record**.</span></span> <span data-ttu-id="69844-109">建立並設定保留標籤，以便將內容標示為[記錄](#records)，讓使用者自行套用或透過辨識敏感性資訊、關鍵字、或內容類型而自動套用。</span><span class="sxs-lookup"><span data-stu-id="69844-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="69844-110">**使用檔案計劃來移轉和管理您的保留需求**。</span><span class="sxs-lookup"><span data-stu-id="69844-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="69844-111">透過使用[檔案計劃](file-plan-manager.md)，您可以將現有的保留計劃帶入 Microsoft 365，或是建立新的保留方案以增強管理功能。</span><span class="sxs-lookup"><span data-stu-id="69844-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="69844-112">**使用保留標籤以便設置保留和刪除的設定值**。</span><span class="sxs-lookup"><span data-stu-id="69844-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="69844-113">依照各種因素，包括建立的日期或最近一次修改的日期，使用保留期間和動作設定[保留標籤](retention.md#retention-labels)。</span><span class="sxs-lookup"><span data-stu-id="69844-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="69844-114">利用[事件型保留](event-driven-retention.md)，**當事件發生時開始不同的保留期間**。</span><span class="sxs-lookup"><span data-stu-id="69844-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="69844-115">使用[處置檢閱](disposition.md#disposition-reviews)和[記錄刪除](disposition.md#disposition-of-records)證明來**檢閱並驗證處置**。</span><span class="sxs-lookup"><span data-stu-id="69844-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="69844-116">使用[匯出選項](disposition.md#filter-and-export-the-views)來**匯出所有已處置項目的相關資訊**。</span><span class="sxs-lookup"><span data-stu-id="69844-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="69844-117">為組織中的記錄管理員功能**設定特定權限**，以讓其[具有適當權限](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="69844-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="69844-118">藉由使用這些功能，您可以將組織的保留排程和需求整合成一份記錄管理解決方案，以便管理保留、紀錄聲明和處置，以支援完整的內容生命週期。</span><span class="sxs-lookup"><span data-stu-id="69844-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="69844-119">除了線上文件，您可能會發現，收聽記錄管理的[網路研討會錄音檔](https://aka.ms/MIPC/Video-RecordsManagementWebinar)，並下載隨附的[常見問題投影片組](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)是很實用的。</span><span class="sxs-lookup"><span data-stu-id="69844-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="69844-120">記錄</span><span class="sxs-lookup"><span data-stu-id="69844-120">Records</span></span>

<span data-ttu-id="69844-121">當內容標示為記錄時：</span><span class="sxs-lookup"><span data-stu-id="69844-121">When content is marked as a record:</span></span>

- <span data-ttu-id="69844-122">根據[允許或封鎖的動作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)，對項目施加限制。</span><span class="sxs-lookup"><span data-stu-id="69844-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="69844-123">關於項目的其他活動會予以記錄。</span><span class="sxs-lookup"><span data-stu-id="69844-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="69844-124">在項目保留期結束時將其刪除時，您會有處置證明。</span><span class="sxs-lookup"><span data-stu-id="69844-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="69844-125">使用[保留標籤](retention.md#retention-labels)將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="69844-125">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="69844-126">您可以發佈這些標籤，讓使用者和系統管理員手動將這些標籤套用至內容，或自動將這些標籤套用到您想要標記為記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="69844-126">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="69844-127">透過使用保留標籤來將內容標記為記錄，您可以在 Microsoft 365 環境中實作單一且一致的管理記錄策略。</span><span class="sxs-lookup"><span data-stu-id="69844-127">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="69844-128">比較允許或封鎖動作的限制</span><span class="sxs-lookup"><span data-stu-id="69844-128">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="69844-129">使用下表來找出由於套用標準保留標籤，對內容施加的限制，以及將內容標示為記錄的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="69844-129">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="69844-130">標準的保留標籤具有保留設定和動作，但不能將內容標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="69844-130">A standard retention label has retention settings and actions but doesn't mark content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="69844-131">為了完整起見，表格包含鎖定和解除鎖定記錄的欄，這適用於 SharePoint 和 OneDrive，但不適用 Exchange。</span><span class="sxs-lookup"><span data-stu-id="69844-131">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="69844-132">鎖定和解除鎖定記錄的功能會使用[記錄版本設定](record-versioning.md)，其不支援 Exchange 項目。</span><span class="sxs-lookup"><span data-stu-id="69844-132">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="69844-133">因此，針對標示為記錄的所有 Exchange 項目，行為會對應到**記錄 - 鎖定**欄，而**記錄 - 解除鎖定**則不相關。</span><span class="sxs-lookup"><span data-stu-id="69844-133">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="69844-134">動作</span><span class="sxs-lookup"><span data-stu-id="69844-134">Action</span></span>| <span data-ttu-id="69844-135">保留標籤</span><span class="sxs-lookup"><span data-stu-id="69844-135">Retention label</span></span> |<span data-ttu-id="69844-136">記錄 - 鎖定</span><span class="sxs-lookup"><span data-stu-id="69844-136">Record - locked</span></span>| <span data-ttu-id="69844-137">記錄 - 解除鎖定</span><span class="sxs-lookup"><span data-stu-id="69844-137">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69844-138">編輯內容</span><span class="sxs-lookup"><span data-stu-id="69844-138">Edit contents</span></span>|<span data-ttu-id="69844-139">允許</span><span class="sxs-lookup"><span data-stu-id="69844-139">Allowed</span></span> | <span data-ttu-id="69844-140">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="69844-140">**Blocked**</span></span> | <span data-ttu-id="69844-141">允許</span><span class="sxs-lookup"><span data-stu-id="69844-141">Allowed</span></span>|
|<span data-ttu-id="69844-142">編輯內容，包括重新命名</span><span class="sxs-lookup"><span data-stu-id="69844-142">Edit properties, including rename</span></span>|<span data-ttu-id="69844-143">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-143">Allowed</span></span> |<span data-ttu-id="69844-144">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-144">Allowed</span></span> | <span data-ttu-id="69844-145">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-145">Allowed</span></span>|
|<span data-ttu-id="69844-146">刪除</span><span class="sxs-lookup"><span data-stu-id="69844-146">Delete</span></span>|<span data-ttu-id="69844-147">允許 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="69844-147">Allowed <sup>1</sup></span></span> |<span data-ttu-id="69844-148">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="69844-148">**Blocked**</span></span> | <span data-ttu-id="69844-149">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="69844-149">**Blocked**</span></span>|
|<span data-ttu-id="69844-150">複製</span><span class="sxs-lookup"><span data-stu-id="69844-150">Copy</span></span>|<span data-ttu-id="69844-151">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-151">Allowed</span></span> |<span data-ttu-id="69844-152">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-152">Allowed</span></span> | <span data-ttu-id="69844-153">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-153">Allowed</span></span>|
|<span data-ttu-id="69844-154">在容器內移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="69844-154">Move within container <sup>2</sup></span></span>|<span data-ttu-id="69844-155">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-155">Allowed</span></span> |<span data-ttu-id="69844-156">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-156">Allowed</span></span> | <span data-ttu-id="69844-157">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-157">Allowed</span></span>|
|<span data-ttu-id="69844-158">在容器間移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="69844-158">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="69844-159">允許</span><span class="sxs-lookup"><span data-stu-id="69844-159">Allowed</span></span> |<span data-ttu-id="69844-160">如果從未解除鎖定則允許</span><span class="sxs-lookup"><span data-stu-id="69844-160">Allowed if never unlocked</span></span> | <span data-ttu-id="69844-161">允許</span><span class="sxs-lookup"><span data-stu-id="69844-161">Allowed</span></span>|
|<span data-ttu-id="69844-162">開啟/讀取</span><span class="sxs-lookup"><span data-stu-id="69844-162">Open/Read</span></span>|<span data-ttu-id="69844-163">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-163">Allowed</span></span> |<span data-ttu-id="69844-164">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-164">Allowed</span></span> | <span data-ttu-id="69844-165">已允許</span><span class="sxs-lookup"><span data-stu-id="69844-165">Allowed</span></span>|
|<span data-ttu-id="69844-166">變更標籤</span><span class="sxs-lookup"><span data-stu-id="69844-166">Change label</span></span>|<span data-ttu-id="69844-167">允許</span><span class="sxs-lookup"><span data-stu-id="69844-167">Allowed</span></span> |<span data-ttu-id="69844-168">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="69844-168">Allowed - container admin only</span></span> | <span data-ttu-id="69844-169">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="69844-169">Allowed - container admin only</span></span>|
|<span data-ttu-id="69844-170">移除標籤</span><span class="sxs-lookup"><span data-stu-id="69844-170">Remove label</span></span>|<span data-ttu-id="69844-171">允許</span><span class="sxs-lookup"><span data-stu-id="69844-171">Allowed</span></span> |<span data-ttu-id="69844-172">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="69844-172">Allowed - container admin only</span></span> | <span data-ttu-id="69844-173">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="69844-173">Allowed - container admin only</span></span>|

<span data-ttu-id="69844-174">註腳：</span><span class="sxs-lookup"><span data-stu-id="69844-174">Footnotes:</span></span>

<span data-ttu-id="69844-175"><sup>1</sup> OneDrive 和 Exchange 透過將複本保留在安全的位置但由 SharePoint 鎖定而支援。</span><span class="sxs-lookup"><span data-stu-id="69844-175"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="69844-176">使用者嘗試刪除 SharePoint 中的加標籤文件時會看見的訊息：</span><span class="sxs-lookup"><span data-stu-id="69844-176">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![無法從 SharePoint 中刪除項目的訊息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="69844-178"><sup>2</sup> 容器包括 SharePoint 文件庫和 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="69844-178"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69844-179">後續步驟</span><span class="sxs-lookup"><span data-stu-id="69844-179">Next steps</span></span>

<span data-ttu-id="69844-180">請參照[開始使用記錄管理](get-started-with-records-management.md)。</span><span class="sxs-lookup"><span data-stu-id="69844-180">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="69844-181">若要將內容標示為記錄，請參閱[使用保留標籤宣告記錄](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="69844-181">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
