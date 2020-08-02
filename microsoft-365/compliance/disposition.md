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
ms.openlocfilehash: 55b57891732f50eba09425fce4d2be34c94740f3
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533820"
---
# <a name="disposition-of-content"></a><span data-ttu-id="359f0-103">內容處置</span><span class="sxs-lookup"><span data-stu-id="359f0-103">Disposition of content</span></span>

><span data-ttu-id="359f0-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="359f0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="359f0-105">使用 Microsoft 365 規範中心內的**記錄管理**中的 [**部署**] 索引標籤，管理處置檢查，並查看在保留期間結束時自動刪除的[記錄](records.md)。</span><span class="sxs-lookup"><span data-stu-id="359f0-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="359f0-106">查看內容處置的必要條件</span><span class="sxs-lookup"><span data-stu-id="359f0-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="359f0-107">若要管理處置檢查，並確認已刪除記錄，您必須啟用足夠的許可權和審核。</span><span class="sxs-lookup"><span data-stu-id="359f0-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="359f0-108">進行處置的許可權</span><span class="sxs-lookup"><span data-stu-id="359f0-108">Permissions for disposition</span></span>

<span data-ttu-id="359f0-109">若要成功存取 Microsoft 365 規範中心的「**處置**」索引標籤，使用者必須具有「**處置管理**」角色和「 **View-Only 審核記錄**」角色。</span><span class="sxs-lookup"><span data-stu-id="359f0-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="359f0-110">雖然標準建議是將使用者新增至預設角色群組，在此情況下，建議您建立一個名為「**處置檢閱者**」的新角色群組，其具有這兩個角色，並視需要將使用者新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="359f0-110">Although the standard advice is to add users to the default role groups, in this case, we recommend you create a new role group called **Disposition Reviewers** that has these two roles and add users to this group as needed.</span></span> <span data-ttu-id="359f0-111">用於進行處理的單一角色群組可減少管理開銷，並可讓使用者更輕鬆地取得所需的組合許可權。</span><span class="sxs-lookup"><span data-stu-id="359f0-111">A single role group for disposition reduces administration overheads and makes it easier for users have the combined permissions that they need.</span></span>

> [!NOTE]
> <span data-ttu-id="359f0-112">即使全域管理員也必須授與**處置管理**角色。</span><span class="sxs-lookup"><span data-stu-id="359f0-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> <span data-ttu-id="359f0-113">因此，如果全域管理員需要存取「處置」索引標籤，則其為「**處置檢閱者**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="359f0-113">So if global admins need to access the disposition tab, them as members of the **Disposition Reviewers** role group.</span></span> 

<span data-ttu-id="359f0-114">特定于**View-Only 的審計記錄**角色：</span><span class="sxs-lookup"><span data-stu-id="359f0-114">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="359f0-115">因為用於搜尋審核記錄的基準指令程式是 Exchange Online Cmdlet，所以您必須使用[Exchange online 中的 exchange 系統管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)，而不是使用安全性 & 規範中心中的 [**許可權**] 頁面，指派此角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="359f0-115">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="359f0-116">如需相關指示，請參閱[Manage role groups In Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="359f0-116">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="359f0-117">此角色不支援 Microsoft 365 群組（[先前稱為 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）。</span><span class="sxs-lookup"><span data-stu-id="359f0-117">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="359f0-118">請改為指派使用者信箱、郵件使用者或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="359f0-118">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="359f0-119">如需授與使用者**處置管理**角色及建立新的處理**檢閱者**角色的指示，請參閱[授與使用者存取 Office 365 安全性與 &amp; 合規性中心的許可權](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="359f0-119">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="359f0-120">啟用審核</span><span class="sxs-lookup"><span data-stu-id="359f0-120">Enable auditing</span></span>

<span data-ttu-id="359f0-121">請確定已在第一次處理動作之前，至少啟用一天的審計。</span><span class="sxs-lookup"><span data-stu-id="359f0-121">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="359f0-122">如需詳細資訊，請參閱在[Office 365 安全性與 &amp; 合規性中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="359f0-122">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="359f0-123">處置檢閱</span><span class="sxs-lookup"><span data-stu-id="359f0-123">Disposition reviews</span></span>

<span data-ttu-id="359f0-124">當內容到達保留期間結束時，可能會有幾個原因會讓您複查內容，以決定是否可以安全地刪除（「已處置」）。</span><span class="sxs-lookup"><span data-stu-id="359f0-124">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="359f0-125">例如，您可能需要：</span><span class="sxs-lookup"><span data-stu-id="359f0-125">For example, you might need to:</span></span>
  
- <span data-ttu-id="359f0-126">在訴訟或審計事件中，封存相關內容的刪除。</span><span class="sxs-lookup"><span data-stu-id="359f0-126">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="359f0-127">若內容有調研或歷史值，請將內容從處置清單中移除儲存在封存中。</span><span class="sxs-lookup"><span data-stu-id="359f0-127">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="359f0-128">將不同的保留期間指派給內容，這可能是因為原始保留設定為暫時或臨時的解決方案。</span><span class="sxs-lookup"><span data-stu-id="359f0-128">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="359f0-129">將內容傳回給用戶端或轉接至另一個組織。</span><span class="sxs-lookup"><span data-stu-id="359f0-129">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="359f0-130">在保留期間結束時，會觸發處置檢查：</span><span class="sxs-lookup"><span data-stu-id="359f0-130">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="359f0-131">您選擇的人員會收到電子郵件通知，告知他們具有要審閱的內容。</span><span class="sxs-lookup"><span data-stu-id="359f0-131">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="359f0-132">這些檢閱者可以是個別使用者、發佈或安全性群組或 Microsoft 365 群組（[以前稱為 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）。</span><span class="sxs-lookup"><span data-stu-id="359f0-132">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="359f0-133">請注意，每週會傳送通知。</span><span class="sxs-lookup"><span data-stu-id="359f0-133">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="359f0-134">檢閱者會移至 Microsoft 365 合規性中心的「**處置**」索引標籤，以查看內容，並決定是否要永久刪除、擴充保留期間或套用其他保留標籤。</span><span class="sxs-lookup"><span data-stu-id="359f0-134">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="359f0-135">處置評審可將內容包含在 Exchange 信箱、SharePoint 網站、OneDrive 帳戶和 Microsoft 365 群組中。</span><span class="sxs-lookup"><span data-stu-id="359f0-135">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="359f0-136">只有在檢閱者選擇永久刪除內容之後，才會刪除等候在這些位置中進行處置檢查的內容。</span><span class="sxs-lookup"><span data-stu-id="359f0-136">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="359f0-137">信箱至少必須有 10 MB 的資料，才可支援處理審閱。</span><span class="sxs-lookup"><span data-stu-id="359f0-137">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="359f0-138">您可以在 [**概覽**] 索引標籤中看到所有擱置的處理的概覽。例如：</span><span class="sxs-lookup"><span data-stu-id="359f0-138">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![記錄管理綜述中的擱置處置](../media/dispositions-overview.png)

<span data-ttu-id="359f0-140">當您選取 [**查看所有擱置**中的處理] 時，就會移至 [**部署**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="359f0-140">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="359f0-141">例如：</span><span class="sxs-lookup"><span data-stu-id="359f0-141">For example:</span></span>

![Microsoft 365 規範中心的「處置」頁面](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="359f0-143">用於處置評審的工作流程</span><span class="sxs-lookup"><span data-stu-id="359f0-143">Workflow for a disposition review</span></span>

<span data-ttu-id="359f0-144">下圖顯示保留標籤發佈後，使用者手動套用的處理審閱基本工作流程。</span><span class="sxs-lookup"><span data-stu-id="359f0-144">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="359f0-145">或者，設定用於處置檢查的保留標籤，會自動套用至內容。</span><span class="sxs-lookup"><span data-stu-id="359f0-145">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![顯示處置運作方式之流程的圖表](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="359f0-147">在保留期間結束處置檢查時，只會有保留標籤的設定選項。</span><span class="sxs-lookup"><span data-stu-id="359f0-147">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="359f0-148">保留原則無法使用此選項。</span><span class="sxs-lookup"><span data-stu-id="359f0-148">This option is not available for a retention policy.</span></span> <span data-ttu-id="359f0-149">如需這兩個保留解決方案的詳細資訊，請參閱[瞭解保留原則和保留標籤](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="359f0-149">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![標籤的保留設定](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="359f0-151">當您選取 [選項] 時，當**有可供查看的專案時通知**使用者，請指定使用者或擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="359f0-151">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="359f0-152">此選項不支援 Microsoft 365 群組（[先前稱為 Office 365 群組](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）。</span><span class="sxs-lookup"><span data-stu-id="359f0-152">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="359f0-153">內容的查看與處置</span><span class="sxs-lookup"><span data-stu-id="359f0-153">Viewing and disposing of content</span></span>

<span data-ttu-id="359f0-154">當檢閱者透過電子郵件通知出內容可供審閱時，他們會從 Microsoft 365 規範中心的**記錄管理**移至 [**處置**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="359f0-154">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="359f0-155">檢閱者可以查看每個保留標籤的專案數目等候處理，然後選取保留標籤以查看具有該標籤的所有內容。</span><span class="sxs-lookup"><span data-stu-id="359f0-155">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="359f0-156">選取保留標籤之後，您就會看到 [**擱置的部署**] 索引標籤中該標籤的所有擱置的處理。選取一個或多個專案，您可以在其中選擇動作並輸入對齊批註：</span><span class="sxs-lookup"><span data-stu-id="359f0-156">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![處置選項](../media/retention-disposition-options.png)

<span data-ttu-id="359f0-158">您可以從圖片看到，支援的動作如下：</span><span class="sxs-lookup"><span data-stu-id="359f0-158">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="359f0-159">永久刪除專案</span><span class="sxs-lookup"><span data-stu-id="359f0-159">Permanently delete the item</span></span>
- <span data-ttu-id="359f0-160">延長保留期間</span><span class="sxs-lookup"><span data-stu-id="359f0-160">Extend the retention period</span></span>
- <span data-ttu-id="359f0-161">套用其他保留標籤</span><span class="sxs-lookup"><span data-stu-id="359f0-161">Apply a different retention label</span></span>

<span data-ttu-id="359f0-162">提供您具有位置和內容的許可權，您可以使用 [**位置**] 欄中的連結，以查看其原始位置中的檔。</span><span class="sxs-lookup"><span data-stu-id="359f0-162">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="359f0-163">在處置檢查期間，內容永遠不會從其原始位置移動，永遠不會刪除，除非檢閱者選擇這麼做。</span><span class="sxs-lookup"><span data-stu-id="359f0-163">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="359f0-164">電子郵件通知會以每週為單位自動傳送給檢閱者。</span><span class="sxs-lookup"><span data-stu-id="359f0-164">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="359f0-165">此排定的程式表示當內容到達其保留期間結束時，最多可能需要7天的時間，檢閱者收到內容正等待處置的電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="359f0-165">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="359f0-166">所有的處理動作都可以經過審核，而且檢閱者所輸入的調整文字會儲存並顯示在 [已**釋放的專案**] 頁面上的 [**批註**] 欄中。</span><span class="sxs-lookup"><span data-stu-id="359f0-166">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="359f0-167">永久刪除處置內容之前的時間</span><span class="sxs-lookup"><span data-stu-id="359f0-167">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="359f0-168">只有在檢閱者選擇永久刪除內容之後，才會刪除等候進行處置檢查的內容。</span><span class="sxs-lookup"><span data-stu-id="359f0-168">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="359f0-169">當檢閱者選擇此選項時，SharePoint 網站或 OneDrive 帳戶中的內容，就會符合[保留設定如何使用內容就地運作](retention.md#how-retention-settings-work-with-content-in-place)所述的標準清理程式。</span><span class="sxs-lookup"><span data-stu-id="359f0-169">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="359f0-170">記錄處置</span><span class="sxs-lookup"><span data-stu-id="359f0-170">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="359f0-171">用於 SharePoint 和 OneDrive 中的記錄的處理證明已完成的展示。</span><span class="sxs-lookup"><span data-stu-id="359f0-171">The rollout for proof of disposal for records in SharePoint and OneDrive is complete.</span></span> <span data-ttu-id="359f0-172">您會在 Microsoft 365 規範中心的 [記錄管理] 頁面上，看到 [已標記內容] 做為 SharePoint 和 OneDrive 的保留標籤清單。</span><span class="sxs-lookup"><span data-stu-id="359f0-172">You will see the list of retention labels that marked content as records for SharePoint and OneDrive in the Disposition section of the Records Management page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="359f0-173">在 [這些標籤] 底下，您可以在 SharePoint 和 OneDrive 中看到專案的清單，該專案會自動處置或在進行處置檢查之後。</span><span class="sxs-lookup"><span data-stu-id="359f0-173">Under these labels, you can see the list of items in SharePoint and OneDrive that were disposed automatically or after a disposition review.</span></span>
>
> <span data-ttu-id="359f0-174">Exchange 中的記錄處置憑證尚未使用中。</span><span class="sxs-lookup"><span data-stu-id="359f0-174">Proof of disposal for records in Exchange is not yet active.</span></span> <span data-ttu-id="359f0-175">當此首展開始和完成時，我們將會更新此附注。</span><span class="sxs-lookup"><span data-stu-id="359f0-175">When this rollout begins and when it is complete, we will update this note.</span></span>

<span data-ttu-id="359f0-176">使用 [**記錄管理**] 頁面中的 [**部署**] 索引標籤來識別自動刪除的記錄。</span><span class="sxs-lookup"><span data-stu-id="359f0-176">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="359f0-177">這些專案會在 [**類型**] 欄中顯示已**處置的記錄**。</span><span class="sxs-lookup"><span data-stu-id="359f0-177">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="359f0-178">例如：</span><span class="sxs-lookup"><span data-stu-id="359f0-178">For example:</span></span>

![未進行處置評審的已處置專案](../media/records-disposed2.png)

<span data-ttu-id="359f0-180">已釋放的 [**專案**] 索引標籤中的記錄標籤所顯示的專案，在專案被處置後，最多可保留7年，每筆記錄的每一筆記錄的限制為1000000個專案。</span><span class="sxs-lookup"><span data-stu-id="359f0-180">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="359f0-181">如果您看到的**計數**值接近此限制1000000，而您需要為記錄進行處置，請與[Microsoft 支援](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="359f0-181">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="359f0-182">這種功能是以[整合的審計記錄](search-the-audit-log-in-security-and-compliance.md)資訊為基礎，因此需要[啟用並](turn-audit-log-search-on-or-off.md)可搜尋審計，以便捕獲對應的事件。</span><span class="sxs-lookup"><span data-stu-id="359f0-182">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="359f0-183">篩選和匯出視圖</span><span class="sxs-lookup"><span data-stu-id="359f0-183">Filter and export the views</span></span>

<span data-ttu-id="359f0-184">當您從 [**處置**] 頁面中選取保留標籤時，[**擱置處理**] 索引標籤（如果適用）及 [已**釋放的專案**] 索引標籤可讓您篩選視圖，以協助您更輕鬆地找到專案。</span><span class="sxs-lookup"><span data-stu-id="359f0-184">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="359f0-185">針對暫止的處理，時間範圍是以到期日為基礎。</span><span class="sxs-lookup"><span data-stu-id="359f0-185">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="359f0-186">若為已處置的專案，時間範圍會根據刪除日期。</span><span class="sxs-lookup"><span data-stu-id="359f0-186">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="359f0-187">您可以將上述專案的相關資訊匯出為 .csv 檔案，然後您就可以使用 Excel 進行排序和管理：</span><span class="sxs-lookup"><span data-stu-id="359f0-187">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![用於處置的匯出選項](../media/retention-export-option.png)
  
![在 Excel 中匯出的處置資料](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


