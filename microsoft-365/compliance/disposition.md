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
ms.openlocfilehash: dfea1cfece8a9faccced134cf30923527bd241f5
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941364"
---
# <a name="disposition-of-content"></a><span data-ttu-id="c2d14-103">內容處置</span><span class="sxs-lookup"><span data-stu-id="c2d14-103">Disposition of content</span></span>

><span data-ttu-id="c2d14-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="c2d14-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c2d14-105">使用 Microsoft 365 合規性中心 **[記錄管理]** 中的 **[處置]** 索引標籤來管理處置檢閱，並檢視在其保留期間結束時自動刪除的 [記錄](records-management.md#records)。</span><span class="sxs-lookup"><span data-stu-id="c2d14-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="c2d14-106">檢視內容處置的先決條件</span><span class="sxs-lookup"><span data-stu-id="c2d14-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="c2d14-107">若要管理處置檢閱並確認記錄已刪除，您必須具備足夠的權限，而且必須啟用審核。</span><span class="sxs-lookup"><span data-stu-id="c2d14-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="c2d14-108">處置的權限</span><span class="sxs-lookup"><span data-stu-id="c2d14-108">Permissions for disposition</span></span>

<span data-ttu-id="c2d14-109">若要在 Microsoft 365 合規性中心中成功存取 **[處置]** 索引標籤，使用者必須具備 **[處置管理]** 系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="c2d14-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="c2d14-110">此角色包含在預設系統管理員角色群組、 **[合規性系統管理員]** 與 **[合規性資料系統管理員]** 中。</span><span class="sxs-lookup"><span data-stu-id="c2d14-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="c2d14-111">若要授與使用者此必要的處置管理角色，可以將它們新增到其中一個預設角色群組，或建立自訂角色群組 (例如，名為「處置檢閱者」)，並授與此群組處置管理角色。</span><span class="sxs-lookup"><span data-stu-id="c2d14-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="c2d14-112">即使是全域系統管理員，也需要獲得 **[處置管理]** 角色指派。</span><span class="sxs-lookup"><span data-stu-id="c2d14-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="c2d14-113">如需相關指示，請參閱[讓使用者能夠存取 Office 365 安全性與合規性中心](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="c2d14-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="c2d14-114">啟用稽核</span><span class="sxs-lookup"><span data-stu-id="c2d14-114">Enable auditing</span></span>

<span data-ttu-id="c2d14-115">請確認至少在第一個處置動作進行的前一天啟用稽核。</span><span class="sxs-lookup"><span data-stu-id="c2d14-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="c2d14-116">如需詳細資訊，請參閱[在 Office 365 安全性與合規性中心搜尋稽核記錄](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d14-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="c2d14-117">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="c2d14-117">Disposition reviews</span></span>

<span data-ttu-id="c2d14-118">當內容的保留期間結束時，基於多種原因，您可能會想要檢閱該內容以決定是否可以安全刪除 (亦即「處置」)。</span><span class="sxs-lookup"><span data-stu-id="c2d14-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="c2d14-119">例如，您可能會需要：</span><span class="sxs-lookup"><span data-stu-id="c2d14-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="c2d14-120">如果發生訴訟或稽核，則暫停相關內容的刪除。</span><span class="sxs-lookup"><span data-stu-id="c2d14-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="c2d14-121">如果內容具有研究或歷史價值，將內容從處置清單中移除，以儲存在封存中。</span><span class="sxs-lookup"><span data-stu-id="c2d14-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="c2d14-122">為內容指派不同的保留期間，可能是因為原始保留設定是暫時或臨時解決方案。</span><span class="sxs-lookup"><span data-stu-id="c2d14-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="c2d14-123">將內容送交回客戶或轉移至其他組織。</span><span class="sxs-lookup"><span data-stu-id="c2d14-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="c2d14-124">在保留期間結束後觸發處置檢閱時：</span><span class="sxs-lookup"><span data-stu-id="c2d14-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="c2d14-125">您選擇的人員會收到一封電子郵件，通知他們有內容需檢閱。</span><span class="sxs-lookup"><span data-stu-id="c2d14-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="c2d14-126">這些檢閱者可以是個別使用者，或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="c2d14-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="c2d14-127">請注意，通知是每週發送一次。</span><span class="sxs-lookup"><span data-stu-id="c2d14-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="c2d14-128">檢閱者移至 Microsoft 365 合規性中心的 **[處置]** 索引標籤，以檢閱內容並決定是否要永久刪除內容、延長其保留期間或套用其他保留標籤。</span><span class="sxs-lookup"><span data-stu-id="c2d14-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="c2d14-129">處置檢閱可以包括 Exchange 信箱、SharePoint 網站、OneDrive 帳戶和 Microsoft 365 群組中的內容。</span><span class="sxs-lookup"><span data-stu-id="c2d14-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="c2d14-130">只有在檢閱者選擇永久刪除內容之後，才會刪除在這些位置等待處置檢閱的內容。</span><span class="sxs-lookup"><span data-stu-id="c2d14-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="c2d14-131">信箱必須至少具有 10 MB 的資料才能支援處置檢閱。</span><span class="sxs-lookup"><span data-stu-id="c2d14-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="c2d14-132">您可以在 **[概觀]** 索引標籤中檢閱所有擱置中的處置概觀。例如：</span><span class="sxs-lookup"><span data-stu-id="c2d14-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![[記錄管理] 概觀中擱置中的處置](../media/dispositions-overview.png)

<span data-ttu-id="c2d14-134">當您選取 **[檢視所有擱置中的處置]** ，您將移至 **[處置]** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c2d14-134">When you select the **View all pending dispositions** , you're taken to the **Disposition** page.</span></span> <span data-ttu-id="c2d14-135">例如：</span><span class="sxs-lookup"><span data-stu-id="c2d14-135">For example:</span></span>

![Microsoft 365 合規性中心的 [處置] 頁面](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="c2d14-137">處置檢閱的工作流程</span><span class="sxs-lookup"><span data-stu-id="c2d14-137">Workflow for a disposition review</span></span>

<span data-ttu-id="c2d14-138">下圖顯示使用者在發佈保留標籤並手動套用之後，處置檢閱的基本工作流程。</span><span class="sxs-lookup"><span data-stu-id="c2d14-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="c2d14-139">或者，可以將設定用於處置檢閱的保留標籤自動套用到內容。</span><span class="sxs-lookup"><span data-stu-id="c2d14-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![顯示處置運作流程的圖表](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="c2d14-141">在保留期間結束時觸發處置檢閱是一個設定選項，僅搭配保留標籤使用。</span><span class="sxs-lookup"><span data-stu-id="c2d14-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="c2d14-142">保留原則無法使用此選項。</span><span class="sxs-lookup"><span data-stu-id="c2d14-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="c2d14-143">如需有關這兩個保留解決方案的詳細資訊，請參閱[瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d14-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="c2d14-144">保留標籤的 **[定義保留設定]** 頁面：</span><span class="sxs-lookup"><span data-stu-id="c2d14-144">From the **Define retention settings** page for a retention label:</span></span>

![標籤的保留設定](../media/disposition-review-option.png)
 
<span data-ttu-id="c2d14-146">選取此 **[觸發處置檢閱]** 選項後，您可以在精靈的下一頁指定處置檢閱者：</span><span class="sxs-lookup"><span data-stu-id="c2d14-146">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![指定處置檢閱者](../media/disposition-reviewers.png)

<span data-ttu-id="c2d14-148">針對檢閱者，請指定使用者或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="c2d14-148">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="c2d14-149">此選項不支援 Microsoft 365 群組 ([之前稱為 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))。</span><span class="sxs-lookup"><span data-stu-id="c2d14-149">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="c2d14-150">檢視和處置內容</span><span class="sxs-lookup"><span data-stu-id="c2d14-150">Viewing and disposing of content</span></span>

<span data-ttu-id="c2d14-151">當檢閱者收到電子郵件通知內容可供檢閱時，他們會前往 Microsoft 365 合規性中心內， **[記錄管理]** 中的 **[處置]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c2d14-151">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c2d14-152">檢閱者可以看到每個保留標籤有多少項目正在等待處置，然後選取某個保留標籤可查看帶有該標籤的所有內容。</span><span class="sxs-lookup"><span data-stu-id="c2d14-152">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="c2d14-153">選取保留標籤後，您可以從 **[擱置中的處置]** 索引標籤中查看該標籤的所有擱置中的處置。選取一個或多個項目，然後可以選擇一個動作並輸入理由註解：</span><span class="sxs-lookup"><span data-stu-id="c2d14-153">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![處置選項](../media/retention-disposition-options.png)

<span data-ttu-id="c2d14-155">如圖所見，支援的動作如下：</span><span class="sxs-lookup"><span data-stu-id="c2d14-155">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="c2d14-156">永久刪除項目</span><span class="sxs-lookup"><span data-stu-id="c2d14-156">Permanently delete the item</span></span>
- <span data-ttu-id="c2d14-157">延長保留期間</span><span class="sxs-lookup"><span data-stu-id="c2d14-157">Extend the retention period</span></span>
- <span data-ttu-id="c2d14-158">套用不同的保留標籤</span><span class="sxs-lookup"><span data-stu-id="c2d14-158">Apply a different retention label</span></span>

<span data-ttu-id="c2d14-159">如果您具有位置和內容的權限，則可以使用 **[位置]** 欄中的連結在文件的原始位置檢視文件。</span><span class="sxs-lookup"><span data-stu-id="c2d14-159">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="c2d14-160">在處置檢閱期間，內容永遠不會從其原始位置移動，且除非檢閱者選擇刪除內容，否則內容絕不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="c2d14-160">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="c2d14-161">每週一次自動傳送電子郵件通知給檢閱者。</span><span class="sxs-lookup"><span data-stu-id="c2d14-161">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="c2d14-162">此排程程序表示，當內容的保留期間結束時，檢閱者最多可能需要 7 天才能收到內容正等待處置的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="c2d14-162">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="c2d14-163">可以稽核所有處置動作，而檢閱者輸入的理由文字也將儲存並顯示於 **[已處置項目]** 頁面上的 **[註解]** 欄中。</span><span class="sxs-lookup"><span data-stu-id="c2d14-163">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="c2d14-164">多久會永久刪除處置的內容</span><span class="sxs-lookup"><span data-stu-id="c2d14-164">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="c2d14-165">只有在檢閱者選擇永久刪除內容之後，才會刪除等待處置檢閱的內容。</span><span class="sxs-lookup"><span data-stu-id="c2d14-165">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="c2d14-166">當檢閱者選擇此選項時，SharePoint 網站或 OneDrive 帳戶中的內容就會符合[保留設定如何與就地內容搭配使用](retention.md#how-retention-settings-work-with-content-in-place)所述的標準清理程序。</span><span class="sxs-lookup"><span data-stu-id="c2d14-166">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="c2d14-167">記錄處置</span><span class="sxs-lookup"><span data-stu-id="c2d14-167">Disposition of records</span></span>

<span data-ttu-id="c2d14-168">使用 **[記錄管理]** 頁面中的 **[處置]** 索引標籤，以找出現在已自動刪除，或在處置檢閱之後刪除的記錄。</span><span class="sxs-lookup"><span data-stu-id="c2d14-168">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="c2d14-169">這些項目會在 **[類型]** 欄中顯示 **[記錄已處置]** 。</span><span class="sxs-lookup"><span data-stu-id="c2d14-169">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="c2d14-170">例如：</span><span class="sxs-lookup"><span data-stu-id="c2d14-170">For example:</span></span>

![未經處置檢閱而處置的項目](../media/records-disposed2.png)

<span data-ttu-id="c2d14-172">記錄標籤的 **[已處置項目]** 索引標籤中顯示的項目在處置後最多可保存七年，在此期間，每個記錄限制保存一百萬個項目。</span><span class="sxs-lookup"><span data-stu-id="c2d14-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="c2d14-173">如果您看到 **[計數]** 數字接近上限一百萬，而且您需要記錄的處置證明，請與 [Microsoft 支援服務](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)聯繫。</span><span class="sxs-lookup"><span data-stu-id="c2d14-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="c2d14-174">此功能基於來自[整合稽核記錄](search-the-audit-log-in-security-and-compliance.md)的資訊，因此需要[啟用並搜尋](turn-audit-log-search-on-or-off.md)稽核，以便擷取相應的事件。</span><span class="sxs-lookup"><span data-stu-id="c2d14-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="c2d14-175">若要進行稽核，請搜尋 **標示為記錄的已刪除檔案** 。</span><span class="sxs-lookup"><span data-stu-id="c2d14-175">For auditing, search for **Deleted file marked as a record**.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="c2d14-176">篩選及匯出檢視</span><span class="sxs-lookup"><span data-stu-id="c2d14-176">Filter and export the views</span></span>

<span data-ttu-id="c2d14-177">當您從 **[處置]** 頁面選取保留標籤時， **[擱置中的處置]** 索引標籤 (如果適用) 和 **[已處置的項目]** 索引標籤可讓您篩選檢視，以協助您更輕鬆地找到項目。</span><span class="sxs-lookup"><span data-stu-id="c2d14-177">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="c2d14-178">針對擱置中的處置，時間範圍根據到期日而定。</span><span class="sxs-lookup"><span data-stu-id="c2d14-178">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="c2d14-179">針對已處置的項目，時間範圍根據刪除日而定。</span><span class="sxs-lookup"><span data-stu-id="c2d14-179">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="c2d14-180">您可以將其中一個檢視的項目資訊匯出為 .csv 檔案，然後使用 Excel 排序和管理：</span><span class="sxs-lookup"><span data-stu-id="c2d14-180">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![處置的匯出選項](../media/retention-export-option.png)

