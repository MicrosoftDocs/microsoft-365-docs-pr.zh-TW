---
title: 內容處置
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
description: 無論您使用處置檢閱或根據設定自動刪除內容，監視和管理內容的處置。
ms.openlocfilehash: c49f669498424169a89fa99fcdd259de1f5c720b
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488166"
---
# <a name="disposition-of-content"></a><span data-ttu-id="5daf5-103">內容處置</span><span class="sxs-lookup"><span data-stu-id="5daf5-103">Disposition of content</span></span>

><span data-ttu-id="5daf5-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="5daf5-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="5daf5-105">使用 Microsoft 365 合規性中心 **[記錄管理]** 中的 **[處置]** 索引標籤來管理處置檢閱，並檢視在其保留期間結束時自動刪除的 [記錄](records-management.md#records)。</span><span class="sxs-lookup"><span data-stu-id="5daf5-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="5daf5-106">檢視內容處置的先決條件</span><span class="sxs-lookup"><span data-stu-id="5daf5-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="5daf5-107">若要管理處置檢閱並確認記錄已刪除，您必須具備足夠的權限，而且必須啟用審核。</span><span class="sxs-lookup"><span data-stu-id="5daf5-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="5daf5-108">處置的權限</span><span class="sxs-lookup"><span data-stu-id="5daf5-108">Permissions for disposition</span></span>

<span data-ttu-id="5daf5-109">若要在 Microsoft 365 合規性中心中成功存取 **[處置]** 索引標籤，使用者必須具備 **[處置管理]** 系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="5daf5-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="5daf5-110">從 2020 年 12 月起，此角色現在包含在 **[記錄管理]** 預設系統管理員角色群組中。</span><span class="sxs-lookup"><span data-stu-id="5daf5-110">From December 2020, this role is now included in the **Records Management** default admin role group.</span></span>

> [!NOTE]
> <span data-ttu-id="5daf5-111">預設情况下，全域系統管理員不被授與 **[處置管理]** 角色。</span><span class="sxs-lookup"><span data-stu-id="5daf5-111">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="5daf5-112">若要僅授與使用者進行處置檢閲所需的權限，而不授與其檢視和設定其他保留和記錄管理功能的權限，請建立一個自訂角色群組 (例如，名為 [處置檢閲者]) 並向該組授與 [處置管理角色]。</span><span class="sxs-lookup"><span data-stu-id="5daf5-112">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>

<span data-ttu-id="5daf5-113">此外，要在處置程序中檢視項目的內容，請將使用者新增到以下兩個角色群組：**[內容總管內容檢視器]** 和 **[內容總管清單檢視器]**。</span><span class="sxs-lookup"><span data-stu-id="5daf5-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="5daf5-114">如果使用者沒有這些角色群組的存取權限，他們仍然可以選取處置檢閱動作來完成處置檢閲，但不能從合規性中心檢視項目的內容。</span><span class="sxs-lookup"><span data-stu-id="5daf5-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="5daf5-115">如需設定這些權限的相關指示，請參閱[讓使用者能夠存取 Office 365 安全規範中心](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5daf5-115">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="5daf5-116">啟用稽核</span><span class="sxs-lookup"><span data-stu-id="5daf5-116">Enable auditing</span></span>

<span data-ttu-id="5daf5-117">請確認至少在第一個處置動作進行的前一天啟用稽核。</span><span class="sxs-lookup"><span data-stu-id="5daf5-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="5daf5-118">如需詳細資訊，請參閱[在 Office 365 安全性與合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="5daf5-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="5daf5-119">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="5daf5-119">Disposition reviews</span></span>

<span data-ttu-id="5daf5-120">當內容的保留期間結束時，基於多種原因，您可能會想要檢閱該內容，以確認是否可以永久刪除 (亦即「處置」)。</span><span class="sxs-lookup"><span data-stu-id="5daf5-120">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed").</span></span> <span data-ttu-id="5daf5-121">例如，不要刪除內容，您可能需要：</span><span class="sxs-lookup"><span data-stu-id="5daf5-121">For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="5daf5-122">如果發生訴訟或稽核，則暫停相關內容的刪除。</span><span class="sxs-lookup"><span data-stu-id="5daf5-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>

- <span data-ttu-id="5daf5-123">為內容指派不同的保留期間，可能是因為原始保留設定是暫時或臨時解決方案。</span><span class="sxs-lookup"><span data-stu-id="5daf5-123">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="5daf5-124">例如，如果內容具有研究或歷史價值，則從內容的現有位置移至封存位置。</span><span class="sxs-lookup"><span data-stu-id="5daf5-124">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="5daf5-125">在保留期間結束後觸發處置檢閱時：</span><span class="sxs-lookup"><span data-stu-id="5daf5-125">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="5daf5-126">您選擇的人員會收到一封電子郵件，通知他們有內容需檢閱。</span><span class="sxs-lookup"><span data-stu-id="5daf5-126">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="5daf5-127">這些檢閱者可以是個別使用者，或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5daf5-127">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="5daf5-128">請注意，通知是每週發送一次。</span><span class="sxs-lookup"><span data-stu-id="5daf5-128">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="5daf5-129">檢閱者移至 Microsoft 365 合規性中心的 **[處置]** 索引標籤，以檢閱內容並決定是否要永久刪除內容、延長其保留期間或套用其他保留標籤。</span><span class="sxs-lookup"><span data-stu-id="5daf5-129">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="5daf5-130">處置檢閱可以包括 Exchange 信箱、SharePoint 網站、OneDrive 帳戶和 Microsoft 365 群組中的內容。</span><span class="sxs-lookup"><span data-stu-id="5daf5-130">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="5daf5-131">只有在檢閱者選擇永久刪除內容之後，才會刪除在這些位置等待處置檢閱的內容。</span><span class="sxs-lookup"><span data-stu-id="5daf5-131">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="5daf5-132">信箱必須至少具有 10 MB 的資料才能支援處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="5daf5-132">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="5daf5-133">您可以在 **[概觀]** 索引標籤中檢閱所有擱置中的處置概觀。例如：</span><span class="sxs-lookup"><span data-stu-id="5daf5-133">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![[記錄管理] 概觀中擱置中的處置](../media/dispositions-overview.png)

<span data-ttu-id="5daf5-135">當您選取 **[檢視所有擱置中的處置]**，您將移至 **[處置]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="5daf5-135">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="5daf5-136">例如：</span><span class="sxs-lookup"><span data-stu-id="5daf5-136">For example:</span></span>

![Microsoft 365 合規性中心的 [處置] 頁面](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="5daf5-138">處置檢閱的工作流程</span><span class="sxs-lookup"><span data-stu-id="5daf5-138">Workflow for a disposition review</span></span>

<span data-ttu-id="5daf5-139">下圖顯示使用者在發佈保留標籤並手動套用之後，處置檢閱的基本工作流程。</span><span class="sxs-lookup"><span data-stu-id="5daf5-139">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="5daf5-140">或者，可以將設定用於處置檢閱的保留標籤自動套用到內容。</span><span class="sxs-lookup"><span data-stu-id="5daf5-140">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![顯示處置運作流程的圖表](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="5daf5-142">在保留期間結束時觸發處置檢閱是一個設定選項，僅搭配保留標籤使用。</span><span class="sxs-lookup"><span data-stu-id="5daf5-142">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="5daf5-143">保留原則無法使用此選項。</span><span class="sxs-lookup"><span data-stu-id="5daf5-143">This option is not available for a retention policy.</span></span> <span data-ttu-id="5daf5-144">如需有關這兩個保留解決方案的詳細資訊，請參閱[瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="5daf5-144">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="5daf5-145">保留標籤的 **[定義保留設定]** 頁面：</span><span class="sxs-lookup"><span data-stu-id="5daf5-145">From the **Define retention settings** page for a retention label:</span></span>

![標籤的保留設定](../media/disposition-review-option.png)
 
<span data-ttu-id="5daf5-147">選取此 **[觸發處置檢閱]** 選項後，您可以在精靈的下一頁指定處置檢閱者：</span><span class="sxs-lookup"><span data-stu-id="5daf5-147">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![指定處置檢閱者](../media/disposition-reviewers.png)

<span data-ttu-id="5daf5-149">針對檢閱者，請指定使用者或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5daf5-149">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="5daf5-150">此選項不支援 Microsoft 365 群組 ([之前稱為 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))。</span><span class="sxs-lookup"><span data-stu-id="5daf5-150">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="5daf5-151">檢視和處置內容</span><span class="sxs-lookup"><span data-stu-id="5daf5-151">Viewing and disposing of content</span></span>

<span data-ttu-id="5daf5-152">當檢閱者收到電子郵件通知內容可供檢閱時，他們會前往 Microsoft 365 合規性中心內，**[記錄管理]** 中的 **[處置]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5daf5-152">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5daf5-153">檢閱者可以看到每個保留標籤有多少項目正在等待處置，然後選取某個保留標籤可查看帶有該標籤的所有內容。</span><span class="sxs-lookup"><span data-stu-id="5daf5-153">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="5daf5-154">選取保留標籤後，您可以從 **[擱置中的處置]** 索引標籤中查看該標籤的所有擱置中的處置。選取一個或多個項目，然後可以選擇一個動作並輸入理由註解：</span><span class="sxs-lookup"><span data-stu-id="5daf5-154">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![處置選項](../media/retention-disposition-options.png)

<span data-ttu-id="5daf5-156">如圖所見，支援的動作如下：</span><span class="sxs-lookup"><span data-stu-id="5daf5-156">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="5daf5-157">永久刪除項目</span><span class="sxs-lookup"><span data-stu-id="5daf5-157">Permanently delete the item</span></span>
- <span data-ttu-id="5daf5-158">延長保留期間</span><span class="sxs-lookup"><span data-stu-id="5daf5-158">Extend the retention period</span></span>
- <span data-ttu-id="5daf5-159">套用不同的保留標籤</span><span class="sxs-lookup"><span data-stu-id="5daf5-159">Apply a different retention label</span></span>

<span data-ttu-id="5daf5-160">如果您具有位置和內容的權限，則可以使用 **[位置]** 欄中的連結在文件的原始位置檢視文件。</span><span class="sxs-lookup"><span data-stu-id="5daf5-160">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="5daf5-161">在處置檢閱期間，內容永遠不會從其原始位置移動，且除非檢閱者選擇刪除內容，否則內容絕不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="5daf5-161">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="5daf5-162">每週一次自動傳送電子郵件通知給檢閱者。</span><span class="sxs-lookup"><span data-stu-id="5daf5-162">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="5daf5-163">此排程程序表示，當內容的保留期間結束時，檢閱者最多可能需要 7 天才能收到內容正等待處置的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="5daf5-163">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="5daf5-164">可以稽核所有處置動作，而檢閱者輸入的理由文字也將儲存並顯示於 **[已處置項目]** 頁面上的 **[註解]** 欄中。</span><span class="sxs-lookup"><span data-stu-id="5daf5-164">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="5daf5-165">多久會永久刪除處置的內容</span><span class="sxs-lookup"><span data-stu-id="5daf5-165">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="5daf5-166">只有在檢閱者選擇永久刪除內容之後，才會刪除等待處置檢閱的內容。</span><span class="sxs-lookup"><span data-stu-id="5daf5-166">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="5daf5-167">當檢閱者選擇此選項時，SharePoint 網站或 OneDrive 帳戶中的內容就會符合[保留設定如何與就地內容搭配使用](retention.md#how-retention-settings-work-with-content-in-place)所述的標準清理程序。</span><span class="sxs-lookup"><span data-stu-id="5daf5-167">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="5daf5-168">記錄處置</span><span class="sxs-lookup"><span data-stu-id="5daf5-168">Disposition of records</span></span>

<span data-ttu-id="5daf5-169">使用 **[記錄管理]** 頁面中的 **[處置]** 索引標籤來識別：</span><span class="sxs-lookup"><span data-stu-id="5daf5-169">Use the **Disposition** tab from the **Records Management** page to identify:</span></span>

- <span data-ttu-id="5daf5-170">因處置檢閱而刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="5daf5-170">Items deleted as a result of a disposition review.</span></span>
- <span data-ttu-id="5daf5-171">標示為記錄或法規記錄的項目，會在保留期間結束時自動刪除。</span><span class="sxs-lookup"><span data-stu-id="5daf5-171">Items marked as a record or regulatory record that were automatically deleted at the end of their retention period.</span></span>

<span data-ttu-id="5daf5-172">這些項目會在 **[類型]** 欄中顯示 **[記錄已處置]**。</span><span class="sxs-lookup"><span data-stu-id="5daf5-172">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="5daf5-173">例如：</span><span class="sxs-lookup"><span data-stu-id="5daf5-173">For example:</span></span>

![未經處置檢閱而處置的項目](../media/records-disposed2.png)

<span data-ttu-id="5daf5-175">**[已處置項目]** 索引標籤中顯示的項目在處置後最多可保存七年，在此期間，每個記錄限制保存一百萬個項目。</span><span class="sxs-lookup"><span data-stu-id="5daf5-175">Items that are shown in the **Disposed Items** tab are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="5daf5-176">如果您看到 **[計數]** 數字接近上限一百萬，而且您需要記錄的處置證明，請與 [Microsoft 支援服務](/office365/admin/contact-support-for-business-products)聯繫。</span><span class="sxs-lookup"><span data-stu-id="5daf5-176">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="5daf5-177">此功能使用來自[整合稽核記錄](search-the-audit-log-in-security-and-compliance.md)的資訊，因此需要[啟用並搜尋](turn-audit-log-search-on-or-off.md)稽核，以便擷取相應的事件。</span><span class="sxs-lookup"><span data-stu-id="5daf5-177">This functionality uses information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="5daf5-178">針對標示為記錄或法規記錄的已刪除項目稽核，請搜尋 **[檔案和頁面活動]** 類別中的 **[標示為記錄的已刪除檔案]**。</span><span class="sxs-lookup"><span data-stu-id="5daf5-178">For auditing of deleted items that were marked as records or regulatory records, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="5daf5-179">此稽核事件適用於文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5daf5-179">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="5daf5-180">篩選及匯出檢視</span><span class="sxs-lookup"><span data-stu-id="5daf5-180">Filter and export the views</span></span>

<span data-ttu-id="5daf5-181">當您從 **[處置]** 頁面選取保留標籤時，**[擱置中的處置]** 索引標籤 (如果適用) 和 **[已處置的項目]** 索引標籤可讓您篩選檢視，以協助您更輕鬆地找到項目。</span><span class="sxs-lookup"><span data-stu-id="5daf5-181">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="5daf5-182">針對擱置中的處置，時間範圍根據到期日而定。</span><span class="sxs-lookup"><span data-stu-id="5daf5-182">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="5daf5-183">針對已處置的項目，時間範圍根據刪除日而定。</span><span class="sxs-lookup"><span data-stu-id="5daf5-183">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="5daf5-184">您可以將其中一個檢視的項目資訊匯出為 .csv 檔案，然後使用 Excel 排序和管理：</span><span class="sxs-lookup"><span data-stu-id="5daf5-184">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![處置的匯出選項](../media/retention-export-option.png)