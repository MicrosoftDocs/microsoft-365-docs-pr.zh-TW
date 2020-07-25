---
title: 了解記錄
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解可協助您在 Microsoft 365 中實施記錄管理解決方案的記錄。
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372518"
---
# <a name="learn-about-records"></a><span data-ttu-id="89f7b-103">了解記錄</span><span class="sxs-lookup"><span data-stu-id="89f7b-103">Learn about records</span></span>

><span data-ttu-id="89f7b-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="89f7b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="89f7b-105">在 Microsoft 365 中管理記錄可協助組織遵守公司政策、法律或法規義務，同時降低風險和法律責任。</span><span class="sxs-lookup"><span data-stu-id="89f7b-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="89f7b-106">當內容標示為記錄時：</span><span class="sxs-lookup"><span data-stu-id="89f7b-106">When content is marked as a record:</span></span>

- <span data-ttu-id="89f7b-107">根據[允許或封鎖的動作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)，對項目施加限制。</span><span class="sxs-lookup"><span data-stu-id="89f7b-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="89f7b-108">關於項目的其他活動會予以記錄。</span><span class="sxs-lookup"><span data-stu-id="89f7b-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="89f7b-109">在項目保留期結束時將其刪除時，您會有處置證明。</span><span class="sxs-lookup"><span data-stu-id="89f7b-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="89f7b-110">使用[保留標籤](retention.md#retention-labels)將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="89f7b-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="89f7b-111">您可以發佈這些標籤，讓使用者和系統管理員手動將這些標籤套用至內容，或自動將這些標籤套用到您想要標記為記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="89f7b-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="89f7b-112">透過使用保留標籤來將內容標記為記錄，您可以在 Microsoft 365 環境中實作單一且一致的管理記錄策略。</span><span class="sxs-lookup"><span data-stu-id="89f7b-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="89f7b-113">比較允許或封鎖動作的限制</span><span class="sxs-lookup"><span data-stu-id="89f7b-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="89f7b-114">使用下表來找出由於套用標準保留標籤，對內容施加的限制，以及將內容標示為記錄的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="89f7b-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="89f7b-115">標準保留標籤的設定可保留資料，而不會將內容標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="89f7b-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="89f7b-116">為了完整起見，表格包含鎖定和解除鎖定記錄的欄，這適用於 SharePoint 和 OneDrive，但不適用 Exchange。</span><span class="sxs-lookup"><span data-stu-id="89f7b-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="89f7b-117">鎖定和解除鎖定記錄的功能會使用[記錄版本設定](#record-versioning)，其不支援 Exchange 項目。</span><span class="sxs-lookup"><span data-stu-id="89f7b-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="89f7b-118">因此，針對標示為記錄的所有 Exchange 項目，行為會對應到**記錄 - 鎖定**欄，而**記錄 - 解除鎖定**則不相關。</span><span class="sxs-lookup"><span data-stu-id="89f7b-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="89f7b-119">動作</span><span class="sxs-lookup"><span data-stu-id="89f7b-119">Action</span></span>| <span data-ttu-id="89f7b-120">保留標籤</span><span class="sxs-lookup"><span data-stu-id="89f7b-120">Retention label</span></span> |<span data-ttu-id="89f7b-121">記錄 - 鎖定</span><span class="sxs-lookup"><span data-stu-id="89f7b-121">Record - locked</span></span>| <span data-ttu-id="89f7b-122">記錄 - 解除鎖定</span><span class="sxs-lookup"><span data-stu-id="89f7b-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="89f7b-123">編輯內容</span><span class="sxs-lookup"><span data-stu-id="89f7b-123">Edit contents</span></span>|<span data-ttu-id="89f7b-124">允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-124">Allowed</span></span> | <span data-ttu-id="89f7b-125">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="89f7b-125">**Blocked**</span></span> | <span data-ttu-id="89f7b-126">允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-126">Allowed</span></span>|
|<span data-ttu-id="89f7b-127">編輯內容，包括重新命名</span><span class="sxs-lookup"><span data-stu-id="89f7b-127">Edit properties, including rename</span></span>|<span data-ttu-id="89f7b-128">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-128">Allowed</span></span> |<span data-ttu-id="89f7b-129">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-129">Allowed</span></span> | <span data-ttu-id="89f7b-130">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-130">Allowed</span></span>|
|<span data-ttu-id="89f7b-131">刪除</span><span class="sxs-lookup"><span data-stu-id="89f7b-131">Delete</span></span>|<span data-ttu-id="89f7b-132">允許 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="89f7b-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="89f7b-133">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="89f7b-133">**Blocked**</span></span> | <span data-ttu-id="89f7b-134">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="89f7b-134">**Blocked**</span></span>|
|<span data-ttu-id="89f7b-135">複製</span><span class="sxs-lookup"><span data-stu-id="89f7b-135">Copy</span></span>|<span data-ttu-id="89f7b-136">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-136">Allowed</span></span> |<span data-ttu-id="89f7b-137">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-137">Allowed</span></span> | <span data-ttu-id="89f7b-138">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-138">Allowed</span></span>|
|<span data-ttu-id="89f7b-139">在容器內移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="89f7b-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="89f7b-140">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-140">Allowed</span></span> |<span data-ttu-id="89f7b-141">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-141">Allowed</span></span> | <span data-ttu-id="89f7b-142">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-142">Allowed</span></span>|
|<span data-ttu-id="89f7b-143">在容器間移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="89f7b-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="89f7b-144">允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-144">Allowed</span></span> |<span data-ttu-id="89f7b-145">如果從未解除鎖定則允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-145">Allowed if never unlocked</span></span> | <span data-ttu-id="89f7b-146">允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-146">Allowed</span></span>|
|<span data-ttu-id="89f7b-147">開啟/讀取</span><span class="sxs-lookup"><span data-stu-id="89f7b-147">Open/Read</span></span>|<span data-ttu-id="89f7b-148">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-148">Allowed</span></span> |<span data-ttu-id="89f7b-149">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-149">Allowed</span></span> | <span data-ttu-id="89f7b-150">已允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-150">Allowed</span></span>|
|<span data-ttu-id="89f7b-151">變更標籤</span><span class="sxs-lookup"><span data-stu-id="89f7b-151">Change label</span></span>|<span data-ttu-id="89f7b-152">允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-152">Allowed</span></span> |<span data-ttu-id="89f7b-153">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="89f7b-153">Allowed - container admin only</span></span> | <span data-ttu-id="89f7b-154">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="89f7b-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="89f7b-155">移除標籤</span><span class="sxs-lookup"><span data-stu-id="89f7b-155">Remove label</span></span>|<span data-ttu-id="89f7b-156">允許</span><span class="sxs-lookup"><span data-stu-id="89f7b-156">Allowed</span></span> |<span data-ttu-id="89f7b-157">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="89f7b-157">Allowed - container admin only</span></span> | <span data-ttu-id="89f7b-158">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="89f7b-158">Allowed - container admin only</span></span>|

<span data-ttu-id="89f7b-159">註腳：</span><span class="sxs-lookup"><span data-stu-id="89f7b-159">Footnotes:</span></span>

<span data-ttu-id="89f7b-160"><sup>1</sup> OneDrive 和 Exchange 透過將複本保留在安全的位置但由 SharePoint 鎖定而支援。</span><span class="sxs-lookup"><span data-stu-id="89f7b-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="89f7b-161">使用者嘗試刪除 SharePoint 中的加標籤文件時會看見的訊息：</span><span class="sxs-lookup"><span data-stu-id="89f7b-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![無法從 SharePoint 中刪除項目的訊息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="89f7b-163"><sup>2</sup> 容器包括 SharePoint 文件庫和 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="89f7b-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="89f7b-164">使用 [保留標籤] 宣告記錄</span><span class="sxs-lookup"><span data-stu-id="89f7b-164">Using retention labels to declare records</span></span>

<span data-ttu-id="89f7b-165">當您建立保留標籤時，可以選擇使用保留標籤將內容標記為記錄：</span><span class="sxs-lookup"><span data-stu-id="89f7b-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="89f7b-166">在 Microsoft 365 合規性中心中，移至 [記錄管理]\*\*\*\* \> [檔案計畫]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89f7b-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="89f7b-167">選取在 **[檔案計畫]** 頁面上的 **[建立標籤]**。</span><span class="sxs-lookup"><span data-stu-id="89f7b-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="89f7b-168">在精靈的 [標籤設定]\*\*\*\* 頁面上，選擇將內容分類為記錄的選項。</span><span class="sxs-lookup"><span data-stu-id="89f7b-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![按一下 [使用標籤以將內容分類為「記錄」] 核取方塊](../media/recordversioning6.png)

3. <span data-ttu-id="89f7b-170">視需要將保留標籤套用至 SharePoint 或 OneDrive 文件和 Exchange 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="89f7b-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="89f7b-171">如需詳細指示：</span><span class="sxs-lookup"><span data-stu-id="89f7b-171">For instructions:</span></span>
    
    - [<span data-ttu-id="89f7b-172">建立保留標籤，並在應用程式中使用這些標籤</span><span class="sxs-lookup"><span data-stu-id="89f7b-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="89f7b-173">自動將保留標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="89f7b-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="89f7b-174">將已設定的保留標籤套用至內容</span><span class="sxs-lookup"><span data-stu-id="89f7b-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="89f7b-175">將內容標示為記錄的保留標籤可供使用者在應用程式中套用：</span><span class="sxs-lookup"><span data-stu-id="89f7b-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="89f7b-176">針對 Exchange，任何信箱存取權的使用者都可以套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="89f7b-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="89f7b-177">對於 SharePoint 和 OneDrive，預設 [成員] 群組 ([參與] 權限等級) 中的任何使用者都能套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="89f7b-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="89f7b-178">使用保留標籤將文件標示為記錄的範例：</span><span class="sxs-lookup"><span data-stu-id="89f7b-178">Example of a document marked as record by using a retention label:</span></span>

![標記為記錄之文件的詳細資料窗格](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="89f7b-180">記錄版本設定</span><span class="sxs-lookup"><span data-stu-id="89f7b-180">Record versioning</span></span>

<span data-ttu-id="89f7b-181">將文件標示為記錄的功能，以及限制可對記錄執行的動作，是任何記錄管理解決方案的重要目標。</span><span class="sxs-lookup"><span data-stu-id="89f7b-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="89f7b-182">不過，可能也會需要共同作業，讓人員建立後續的版本。</span><span class="sxs-lookup"><span data-stu-id="89f7b-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="89f7b-183">例如，您將銷售合約標示為記錄，但是之後需要使用新的條款來更新合約，並將最新的版本標示為新記錄，同時保留前一份記錄版本。</span><span class="sxs-lookup"><span data-stu-id="89f7b-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="89f7b-184">針對這些類型的案例，SharePoint 和 OneDrive 支援*記錄版本設定*。</span><span class="sxs-lookup"><span data-stu-id="89f7b-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="89f7b-185">OneNote 筆記本資料夾不支援記錄版本設定。</span><span class="sxs-lookup"><span data-stu-id="89f7b-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="89f7b-186">若要使用記錄版本設定，請先為文件加上標籤並將它標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="89f7b-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="89f7b-187">此時，保留標籤旁會顯示名為 [記錄狀態]\*\* 的文件內容，而初始記錄狀態會是 [鎖定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89f7b-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="89f7b-188">您現在可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="89f7b-188">You can now do the following things:</span></span>

  - <span data-ttu-id="89f7b-189">**解除鎖定和鎖定記錄狀態內容，持續編輯並將文件的個別版本保留為記錄。**</span><span class="sxs-lookup"><span data-stu-id="89f7b-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="89f7b-190">只有當 [記錄狀態]\*\*\*\* 內容設為 [鎖定]\*\*\*\* 時，才會保留記錄的新版本。</span><span class="sxs-lookup"><span data-stu-id="89f7b-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="89f7b-191">這個鎖定和解除鎖定的切換，可降低保留不必要文件版本和複本的風險。</span><span class="sxs-lookup"><span data-stu-id="89f7b-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="89f7b-192">**將記錄自動儲存在位於網站集合內的就地記錄儲存庫中。**</span><span class="sxs-lookup"><span data-stu-id="89f7b-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="89f7b-193">SharePoint 和 OneDrive 中的每個網站集合會在其 [文件保留庫] 中保留內容。</span><span class="sxs-lookup"><span data-stu-id="89f7b-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="89f7b-194">記錄版本會儲存在此文件庫的 [記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="89f7b-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="89f7b-195">**維護包含所有版本的長青文件。**</span><span class="sxs-lookup"><span data-stu-id="89f7b-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="89f7b-196">根據預設，每個 SharePoint 和 OneDrive 文件在項目功能表上都會有版本歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="89f7b-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="89f7b-197">在這個版本歷程記錄中，您可以輕鬆查看記錄的版本，並檢視這些文件。</span><span class="sxs-lookup"><span data-stu-id="89f7b-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="89f7b-198">如果任何文件的保留標籤會將項目標示為記錄，則會自動提供記錄版本設定。</span><span class="sxs-lookup"><span data-stu-id="89f7b-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="89f7b-199">當使用者透過 [詳細資料] 窗格檢視文件內容時，系統會將 [記錄狀態]\*\*\*\* 從 [鎖定]\*\*\*\* 切換為 [解除鎖定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89f7b-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="89f7b-200">此動作會在 [文件保留庫] 的 [記錄] 資料夾中建立記錄，該記錄將在保留期的剩餘時間內保留在其中。</span><span class="sxs-lookup"><span data-stu-id="89f7b-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="89f7b-201">文件解除鎖定後，任何擁有標準編輯權限的使用者都可以編輯該檔案。</span><span class="sxs-lookup"><span data-stu-id="89f7b-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="89f7b-202">不過，使用者無法刪除檔案，因為它仍是記錄。</span><span class="sxs-lookup"><span data-stu-id="89f7b-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="89f7b-203">編輯完成後，使用者就可以將 [記錄狀態]\*\*\*\* 從 [解除鎖定]\*\*\*\* 切換為 [鎖定]\*\*\*\*，這會在此狀態中防止進一步編輯。</span><span class="sxs-lookup"><span data-stu-id="89f7b-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![標記為記錄之文件的 [記錄狀態] 內容](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="89f7b-205">鎖定和解除鎖定記錄</span><span class="sxs-lookup"><span data-stu-id="89f7b-205">Locking and unlocking a record</span></span>

<span data-ttu-id="89f7b-206">將會將內容標示為記錄的保留標籤套用至文件之後，具有 [參與] 權限或更低權限等級的任何使用者都可以解除鎖定記錄或鎖定已解除鎖定的記錄。</span><span class="sxs-lookup"><span data-stu-id="89f7b-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![記錄狀態顯示記錄文件已解鎖](../media/recordversioning9.png)

<span data-ttu-id="89f7b-208">當使用者解鎖記錄後，會發生下列動作：</span><span class="sxs-lookup"><span data-stu-id="89f7b-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="89f7b-209">如果目前的網站集合沒有文件保留庫，則會建立一個。</span><span class="sxs-lookup"><span data-stu-id="89f7b-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="89f7b-210">如果 [文件保留庫] 沒有 [記錄] 資料夾，則會建立一個。</span><span class="sxs-lookup"><span data-stu-id="89f7b-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="89f7b-211">[複製到]\*\*\*\* 動作會將最新版本的文件複製到 [記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="89f7b-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="89f7b-212">[複製到]\*\*\*\* 動作只會包含最新版本，而不包含先前的版本。</span><span class="sxs-lookup"><span data-stu-id="89f7b-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="89f7b-213">複製的文件現在被視為文件的記錄版本，其檔案名稱的格式為：\[標題 GUID 版本\#\]</span><span class="sxs-lookup"><span data-stu-id="89f7b-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="89f7b-214">在 [記錄] 資料夾中建立的複本會新增到原始文件的版本歷程記錄中，而這個版本則會在 [註解] 欄位中顯示**記錄**一詞。</span><span class="sxs-lookup"><span data-stu-id="89f7b-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="89f7b-215">原始文件是可以編輯但無法刪除的新版本。</span><span class="sxs-lookup"><span data-stu-id="89f7b-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="89f7b-216">[文件庫] 欄位 [項目是一筆記錄]\*\*\*\* 仍然會顯示 [是]\*\*\*\* 值，因為文件仍是記錄，即使現在可以編輯。</span><span class="sxs-lookup"><span data-stu-id="89f7b-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="89f7b-217">當使用者鎖定記錄後，就不能再次編輯原始檔案。</span><span class="sxs-lookup"><span data-stu-id="89f7b-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="89f7b-218">但是，解鎖記錄的動作會將版本複製到 [文件保留庫] 中的 [記錄] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="89f7b-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="89f7b-219">記錄版本</span><span class="sxs-lookup"><span data-stu-id="89f7b-219">Record versions</span></span>

<span data-ttu-id="89f7b-220">每次使用者解鎖記錄時，系統會將最新版本複製到 [文件保留庫] 的 [記錄] 資料夾中，而該版本則會在版本歷程記錄的 [註解]\*\*\*\* 欄位中包含 [記錄]\*\*\*\* 的值。</span><span class="sxs-lookup"><span data-stu-id="89f7b-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![在 [文件保留庫] 中顯示的記錄](../media/recordversioning10.png)

<span data-ttu-id="89f7b-222">若要查看版本歷程記錄，請選取文件庫中的文件，然後按一下項目功能表中的 [版本歷程記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89f7b-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="89f7b-223">記錄的儲存位置</span><span class="sxs-lookup"><span data-stu-id="89f7b-223">Where records are stored</span></span>

<span data-ttu-id="89f7b-224">記錄會儲存在網站集合中，頂層網站中 [文件保留庫] 的 [記錄] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="89f7b-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="89f7b-225">在頂層網站的左側導覽中，選擇 [網站內容]\*\*\*\* \> [文件保留庫]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="89f7b-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![文件保留庫](../media/recordversioning11.png)

<br/><br/>

![[文件保留庫] 中的記錄資料夾](../media/recordversioning12.png)

<span data-ttu-id="89f7b-228">只有網站集合系統管理員才能看到 [文件保留庫]。</span><span class="sxs-lookup"><span data-stu-id="89f7b-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="89f7b-229">此外，預設不存在 [文件保留庫]。</span><span class="sxs-lookup"><span data-stu-id="89f7b-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="89f7b-230">只有在網站集中第一次刪除具有保留標籤或保留原則的內容時，才會建立。</span><span class="sxs-lookup"><span data-stu-id="89f7b-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="89f7b-231">搜尋記錄版本設定事件的稽核記錄</span><span class="sxs-lookup"><span data-stu-id="89f7b-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="89f7b-232">鎖定和解鎖記錄的動作會記錄在稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="89f7b-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="89f7b-233">您可以搜尋 [已將記錄狀態變更為「鎖定」]\*\*\*\* 和 [已將記錄狀態變更為「未鎖定」]\*\*\*\* 的特定活動，其位於 [安全性與合規性中心]\*\*\*\* 的 [稽核記錄搜尋]\*\*\*\* 頁面上，[檔案與頁面活動] 區段的 [活動]\*\*\*\* 下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="89f7b-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![搜尋記錄版本設定事件的稽核記錄](../media/recordversioning13.png)

<span data-ttu-id="89f7b-235">如需搜尋這些活動的詳細資訊，請參閱[在安全性與合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities)中的「檔案和頁面活動」一節。</span><span class="sxs-lookup"><span data-stu-id="89f7b-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="89f7b-236">後續步驟</span><span class="sxs-lookup"><span data-stu-id="89f7b-236">Next steps</span></span>

<span data-ttu-id="89f7b-237">如果您還未有保留標籤可用以記錄管理，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="89f7b-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="89f7b-238">若要了解記錄的處置，請參閱[內容處置](disposition.md)。</span><span class="sxs-lookup"><span data-stu-id="89f7b-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
