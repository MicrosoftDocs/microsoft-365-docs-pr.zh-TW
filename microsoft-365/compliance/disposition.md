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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 監視和管理內容處置，不論您使用的是處置檢查，還是會根據您設定的設定自動刪除內容。
ms.openlocfilehash: 3ef98e07df37d429567534e252c15abee69d0044
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245934"
---
# <a name="disposition-of-content"></a><span data-ttu-id="ae0f1-103">內容處置</span><span class="sxs-lookup"><span data-stu-id="ae0f1-103">Disposition of content</span></span>

><span data-ttu-id="ae0f1-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="ae0f1-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="ae0f1-105">使用 Microsoft 365 規範中心內的**記錄管理**中的 [**部署**] 索引標籤，管理處置檢查，並查看在保留期間結束時自動刪除的[記錄](records-management.md#records)。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="ae0f1-106">查看內容處置的必要條件</span><span class="sxs-lookup"><span data-stu-id="ae0f1-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="ae0f1-107">若要管理處置檢查，並確認已刪除記錄，您必須啟用足夠的許可權和審核。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="ae0f1-108">進行處置的許可權</span><span class="sxs-lookup"><span data-stu-id="ae0f1-108">Permissions for disposition</span></span>

<span data-ttu-id="ae0f1-109">若要在 Microsoft 365 規範中心中成功存取「 **處置** 」索引標籤，使用者必須具有「處理 **管理** 」管理角色。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="ae0f1-110">此角色包含在預設的系統管理員角色群組中（ **合規性管理員** 和 **合規性資料管理員**）。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="ae0f1-111">若要授與使用者這項必要的處理管理角色，請將其新增至其中一個預設角色群組，或建立自訂角色群組 (例如，名稱為「處置檢閱者」 ) 並授與此群組為「處置管理」角色。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="ae0f1-112">即使全域管理員也必須授與 **處置管理** 角色。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="ae0f1-113">如需相關指示，請參閱[讓使用者能夠存取 Office 365 安全規範中心](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="ae0f1-114">啟用審核</span><span class="sxs-lookup"><span data-stu-id="ae0f1-114">Enable auditing</span></span>

<span data-ttu-id="ae0f1-115">請確定已在第一次處理動作之前，至少啟用一天的審計。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-115">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="ae0f1-116">如需詳細資訊，請參閱在 [Office 365 安全性與 &amp; 合規性中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-116">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="ae0f1-117">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="ae0f1-117">Disposition reviews</span></span>

<span data-ttu-id="ae0f1-118">當內容到達保留期間結束時，可能會有幾個原因會讓您檢查內容，以決定是否可以安全地刪除 ( 「已處置」 ) 。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-118">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="ae0f1-119">例如，您可能需要：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-119">For example, you might need to:</span></span>
  
- <span data-ttu-id="ae0f1-120">在訴訟或審計事件中，封存相關內容的刪除。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-120">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="ae0f1-121">若內容有調研或歷史值，請將內容從處置清單中移除儲存在封存中。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-121">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="ae0f1-122">將不同的保留期間指派給內容，這可能是因為原始保留設定為暫時或臨時的解決方案。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-122">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="ae0f1-123">將內容傳回給用戶端或轉接至另一個組織。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-123">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="ae0f1-124">在保留期間結束時，會觸發處置檢查：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-124">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="ae0f1-125">您選擇的人員會收到電子郵件通知，告知他們具有要審閱的內容。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-125">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="ae0f1-126">這些檢閱者可以是個別的使用者或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-126">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="ae0f1-127">請注意，每週會傳送通知。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-127">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="ae0f1-128">檢閱者會移至 Microsoft 365 合規性中心的「 **處置** 」索引標籤，以查看內容，並決定是否要永久刪除、擴充保留期間或套用其他保留標籤。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-128">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="ae0f1-129">處置評審可將內容包含在 Exchange 信箱、SharePoint 網站、OneDrive 帳戶和 Microsoft 365 群組中。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-129">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="ae0f1-130">只有在檢閱者選擇永久刪除內容之後，才會刪除等候在這些位置中進行處置檢查的內容。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-130">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="ae0f1-131">信箱至少必須有 10 MB 的資料，才可支援處理審閱。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-131">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="ae0f1-132">您可以在 [ **概覽** ] 索引標籤中看到所有擱置的處理的概覽。例如：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-132">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![記錄管理綜述中的擱置處置](../media/dispositions-overview.png)

<span data-ttu-id="ae0f1-134">當您選取 [ **查看所有擱置**中的處理] 時，就會移至 [ **部署** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-134">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="ae0f1-135">例如：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-135">For example:</span></span>

![Microsoft 365 規範中心的「處置」頁面](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="ae0f1-137">用於處置評審的工作流程</span><span class="sxs-lookup"><span data-stu-id="ae0f1-137">Workflow for a disposition review</span></span>

<span data-ttu-id="ae0f1-138">下圖顯示保留標籤發佈後，使用者手動套用的處理審閱基本工作流程。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-138">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="ae0f1-139">或者，設定用於處置檢查的保留標籤，會自動套用至內容。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-139">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![顯示處置運作方式之流程的圖表](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="ae0f1-141">在保留期間結束處置檢查時，只會有保留標籤的設定選項。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-141">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="ae0f1-142">保留原則無法使用此選項。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-142">This option is not available for a retention policy.</span></span> <span data-ttu-id="ae0f1-143">如需這兩個保留解決方案的詳細資訊，請參閱 [瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-143">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![標籤的保留設定](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="ae0f1-145">當您選取 [選項] 時，當 **有可供查看的專案時通知**使用者，請指定使用者或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-145">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="ae0f1-146">此選項不支援 Microsoft 365 群組 ([先前的 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) 。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-146">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="ae0f1-147">內容的查看與處置</span><span class="sxs-lookup"><span data-stu-id="ae0f1-147">Viewing and disposing of content</span></span>

<span data-ttu-id="ae0f1-148">當檢閱者透過電子郵件通知出內容可供審閱時，他們會從 Microsoft 365 規範中心的**記錄管理**移至 [**處置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-148">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ae0f1-149">檢閱者可以查看每個保留標籤的專案數目等候處理，然後選取保留標籤以查看具有該標籤的所有內容。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-149">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="ae0f1-150">選取保留標籤之後，您就會看到 [ **擱置的部署** ] 索引標籤中該標籤的所有擱置中的處理。選取一個或多個專案，您可以在其中選擇動作並輸入對齊批註：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-150">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![處置選項](../media/retention-disposition-options.png)

<span data-ttu-id="ae0f1-152">您可以從圖片看到，支援的動作如下：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-152">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="ae0f1-153">永久刪除專案</span><span class="sxs-lookup"><span data-stu-id="ae0f1-153">Permanently delete the item</span></span>
- <span data-ttu-id="ae0f1-154">延長保留期間</span><span class="sxs-lookup"><span data-stu-id="ae0f1-154">Extend the retention period</span></span>
- <span data-ttu-id="ae0f1-155">套用其他保留標籤</span><span class="sxs-lookup"><span data-stu-id="ae0f1-155">Apply a different retention label</span></span>

<span data-ttu-id="ae0f1-156">提供您具有位置和內容的許可權，您可以使用 [ **位置** ] 欄中的連結，以查看其原始位置中的檔。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-156">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="ae0f1-157">在處置檢查期間，內容永遠不會從其原始位置移動，永遠不會刪除，除非檢閱者選擇這麼做。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-157">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="ae0f1-158">電子郵件通知會以每週為單位自動傳送給檢閱者。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-158">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="ae0f1-159">此排定的程式表示當內容到達其保留期間結束時，最多可能需要7天的時間，檢閱者收到內容正等待處置的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-159">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="ae0f1-160">所有的處理動作都可以經過審核，而且檢閱者所輸入的調整文字會儲存並顯示在 [已**釋放的專案**] 頁面上的 [**批註**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-160">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="ae0f1-161">永久刪除處置內容之前的時間</span><span class="sxs-lookup"><span data-stu-id="ae0f1-161">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="ae0f1-162">只有在檢閱者選擇永久刪除內容之後，才會刪除等候進行處置檢查的內容。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-162">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="ae0f1-163">當檢閱者選擇此選項時，SharePoint 網站或 OneDrive 帳戶中的內容，就會符合 [保留設定如何使用內容就地運作](retention.md#how-retention-settings-work-with-content-in-place)所述的標準清理程式。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-163">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="ae0f1-164">記錄處置</span><span class="sxs-lookup"><span data-stu-id="ae0f1-164">Disposition of records</span></span>

<span data-ttu-id="ae0f1-165">使用 [**記錄管理**] 頁面中的 [**部署**] 索引標籤，識別現在已刪除的記錄（自動或在處置檢查之後）。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-165">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="ae0f1-166">這些專案會在 [**類型**] 欄中顯示已**處置的記錄**。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-166">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="ae0f1-167">例如：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-167">For example:</span></span>

![未進行處置評審的已處置專案](../media/records-disposed2.png)

<span data-ttu-id="ae0f1-169">已釋放的 [ **專案** ] 索引標籤中的記錄標籤所顯示的專案，在專案被處置後，最多可保留7年，每筆記錄的每一筆記錄的限制為1000000個專案。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-169">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="ae0f1-170">如果您看到的 **計數** 值接近此限制1000000，而您需要為記錄進行處置，請與 [Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-170">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="ae0f1-171">這種功能是以 [整合的審計記錄](search-the-audit-log-in-security-and-compliance.md) 資訊為基礎，因此需要 [啟用並](turn-audit-log-search-on-or-off.md) 可搜尋審計，以便捕獲對應的事件。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-171">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="ae0f1-172">篩選和匯出視圖</span><span class="sxs-lookup"><span data-stu-id="ae0f1-172">Filter and export the views</span></span>

<span data-ttu-id="ae0f1-173">當您從 [ **處置** ] 頁面中選取保留標籤時，[ **擱置的處理** ] 索引標籤 (（如果適用）) 和 [已 **釋放的專案** ] 索引標籤可讓您篩選視圖，以協助您更輕鬆找到</span><span class="sxs-lookup"><span data-stu-id="ae0f1-173">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="ae0f1-174">針對暫止的處理，時間範圍是以到期日為基礎。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-174">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="ae0f1-175">若為已處置的專案，時間範圍會根據刪除日期。</span><span class="sxs-lookup"><span data-stu-id="ae0f1-175">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="ae0f1-176">您可以將上述專案的相關資訊匯出為 .csv 檔案，然後您就可以使用 Excel 進行排序和管理：</span><span class="sxs-lookup"><span data-stu-id="ae0f1-176">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![用於處置的匯出選項](../media/retention-export-option.png)
  
![在 Excel 中匯出的處置資料](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


