---
title: 使用稽核記錄中的共用稽核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 系統管理員可以瞭解如何在 Microsoft 365 審核記錄檔中使用共用審核，以找出與組織外部使用者共用的資源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819293"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a><span data-ttu-id="08b62-103">使用稽核記錄中的共用稽核</span><span class="sxs-lookup"><span data-stu-id="08b62-103">Use sharing auditing in the audit log</span></span>

<span data-ttu-id="08b62-104">「共用」是 SharePoint 線上和商務用 OneDrive 中的主要活動，而且在組織中廣泛使用。</span><span class="sxs-lookup"><span data-stu-id="08b62-104">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in organizations.</span></span> <span data-ttu-id="08b62-105">管理員可以在審核記錄中使用共用審核，以決定組織中共用的使用方式。</span><span class="sxs-lookup"><span data-stu-id="08b62-105">Administrators can use sharing auditing in the audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="08b62-106">SharePoint 共用架構</span><span class="sxs-lookup"><span data-stu-id="08b62-106">The SharePoint Sharing schema</span></span>

<span data-ttu-id="08b62-107">共用事件 (不包括與共享原則及共用) 連結相關的事件，其主要方式是與檔案及資料夾相關的事件不同：一個使用者執行的動作會影響另一個使用者。</span><span class="sxs-lookup"><span data-stu-id="08b62-107">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="08b62-108">例如，當資源使用者 A 給使用者 B 存取檔時。</span><span class="sxs-lookup"><span data-stu-id="08b62-108">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="08b62-109">在此範例中，使用者 A 是  *作用*  中的使用者，而使用者 B 是  *目標使用者*。</span><span class="sxs-lookup"><span data-stu-id="08b62-109">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="08b62-110">在 SharePoint 檔案架構中，作用中使用者的動作只會影響檔本身。</span><span class="sxs-lookup"><span data-stu-id="08b62-110">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="08b62-111">當使用者 A 開啟檔案時， **FileAccessed** 事件所需的唯一資訊就是作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="08b62-111">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="08b62-112">若要解決這種差異，有一個稱為「 *SharePoint 共用架構*」的不同架構，可捕獲共用事件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="08b62-112">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="08b62-113">這可確保系統管理員可以查看共用資源和共用資源之使用者的人員。</span><span class="sxs-lookup"><span data-stu-id="08b62-113">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="08b62-114">共用架構會在與共享事件相關的審計記錄中提供兩個額外的欄位：</span><span class="sxs-lookup"><span data-stu-id="08b62-114">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="08b62-115">**TargetUserOrGroupType：** 識別目標使用者或群組是成員、來賓、SharePointGroup、SecurityGroup 或 Partner。</span><span class="sxs-lookup"><span data-stu-id="08b62-115">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="08b62-116">**TargetUserOrGroupName：** 儲存與上一個範例中 (使用者 B 共用資源之目標使用者或群組的 UPN 或名稱) 。</span><span class="sxs-lookup"><span data-stu-id="08b62-116">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="08b62-117">除了來自審計記錄架構（如 User、 *Operation 及 Date*）以外的其他屬性之外，這兩個欄位也可告訴您完整的 *情景，告訴* 您 *哪些* 使用者已 *與其共用哪個* 資源。</span><span class="sxs-lookup"><span data-stu-id="08b62-117">These two fields, in addition to other properties from the audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="08b62-118">還有另一個架構屬性非常重要的共用案例。</span><span class="sxs-lookup"><span data-stu-id="08b62-118">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="08b62-119">當您匯出審計記錄檔搜尋結果時，匯出之 CSV 檔案中的 [ **AuditData** ] 欄會儲存共用事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="08b62-119">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="08b62-120">例如，當使用者與其他使用者共用網站時，可將目標使用者新增至 SharePoint 群組來完成。</span><span class="sxs-lookup"><span data-stu-id="08b62-120">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="08b62-121">**AuditData** 欄會捕獲此資訊，以提供系統管理員的上下文。</span><span class="sxs-lookup"><span data-stu-id="08b62-121">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="08b62-122">請參閱 [步驟 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) 以取得如何在 **AuditData** ] 欄中剖析資訊的指示。</span><span class="sxs-lookup"><span data-stu-id="08b62-122">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="08b62-123">共用事件 SharePoint</span><span class="sxs-lookup"><span data-stu-id="08b62-123">SharePoint sharing events</span></span>

<span data-ttu-id="08b62-124">當使用者 *(使用者)* 想要與另一個使用者 (*目標* 使用者) 共用資源時，就會定義「共用」。</span><span class="sxs-lookup"><span data-stu-id="08b62-124">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="08b62-125">與外部使用者共用資源相關的審計記錄 (您組織外部的使用者，且在組織的 Azure Active Directory 中沒有來賓帳戶) 由下列事件（記錄在審計記錄檔中）識別：</span><span class="sxs-lookup"><span data-stu-id="08b62-125">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the audit log:</span></span>

- <span data-ttu-id="08b62-126">**SharingInvitationCreated：** 您組織中的使用者企圖共用資源 (可能是與外部使用者) 網站。</span><span class="sxs-lookup"><span data-stu-id="08b62-126">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="08b62-127">這會產生外部共用邀請傳送給目標使用者。</span><span class="sxs-lookup"><span data-stu-id="08b62-127">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="08b62-128">此時不會授與資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="08b62-128">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="08b62-129">**SharingInvitationAccepted：** 外部使用者已接受由行動使用者傳送的共用邀請，而且現在可以存取該資源。</span><span class="sxs-lookup"><span data-stu-id="08b62-129">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="08b62-130">**AnonymousLinkCreated：** 匿名連結 (也稱為「任何人」連結) 會為資源建立。</span><span class="sxs-lookup"><span data-stu-id="08b62-130">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="08b62-131">因為匿名連結可以建立並複製，所以假設具有匿名連結的任何檔都已與目標使用者共用。</span><span class="sxs-lookup"><span data-stu-id="08b62-131">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="08b62-132">**AnonymousLinkUsed：** 顧名思義，當使用匿名連結存取資源時，會記錄此事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-132">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="08b62-133">**SecureLinkCreated：** 使用者已建立「特定人員連結」，以與特定人員共用資源。</span><span class="sxs-lookup"><span data-stu-id="08b62-133">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="08b62-134">這個目標使用者可能是您組織外部的人員。</span><span class="sxs-lookup"><span data-stu-id="08b62-134">This target user may be someone who is external to your organization.</span></span> <span data-ttu-id="08b62-135">共用資源的人員會在 **AddedToSecureLink** 事件的「審計」記錄中識別。</span><span class="sxs-lookup"><span data-stu-id="08b62-135">The person that the resource is shared with is identified in the audit record for the **AddedToSecureLink** event.</span></span> <span data-ttu-id="08b62-136">這兩個事件的時間戳記幾乎相同。</span><span class="sxs-lookup"><span data-stu-id="08b62-136">The time stamps for these two events are nearly identical.</span></span>

- <span data-ttu-id="08b62-137">**AddedToSecureLink：** 已將使用者新增至特定人員連結。</span><span class="sxs-lookup"><span data-stu-id="08b62-137">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="08b62-138">使用此事件中的 [ **TargetUserOrGroupName** ] 欄位來識別新增至對應的 [特定人員] 連結的使用者。</span><span class="sxs-lookup"><span data-stu-id="08b62-138">Use the **TargetUserOrGroupName** field in this event to identify the user added to the corresponding specific people link.</span></span> <span data-ttu-id="08b62-139">這個目標使用者可能是您組織外部的人員。</span><span class="sxs-lookup"><span data-stu-id="08b62-139">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="08b62-140">共用審核工作流程</span><span class="sxs-lookup"><span data-stu-id="08b62-140">Sharing auditing work flow</span></span>
  
<span data-ttu-id="08b62-141">當使用者 (作用中使用者) 想要與另一個使用者共用資源時 (目標使用者) 、SharePoint (或商務用 OneDrive) 會先檢查目標使用者的電子郵件地址是否已與組織目錄中的使用者帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="08b62-141">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="08b62-142">[！注意事項] 如果目標使用者在目錄中 (，且具有對應的 guest 使用者帳戶) ，SharePoint 會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="08b62-142">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="08b62-143">將目標使用者新增至適當的 SharePoint 群組，然後記錄 **AddedToGroup** 事件，立即指派目標使用者的許可權以存取資源。</span><span class="sxs-lookup"><span data-stu-id="08b62-143">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="08b62-144">將共用通知傳送至目標使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="08b62-144">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="08b62-145">記錄 **SharingSet** 事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-145">Logs a **SharingSet** event.</span></span> <span data-ttu-id="08b62-146">在「審核記錄搜尋」工具的 [活動] 中，此事件的「共用檔、資料夾或網站」的易記名稱是「共用」 **和「存取權要求** 」。</span><span class="sxs-lookup"><span data-stu-id="08b62-146">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="08b62-147">請參閱 [步驟 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)中的螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="08b62-147">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="08b62-148">若目標使用者的使用者帳戶不在目錄中，SharePoint 會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="08b62-148">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="08b62-149">根據共用資源的方式，記錄下列其中一項事件：</span><span class="sxs-lookup"><span data-stu-id="08b62-149">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="08b62-150">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="08b62-150">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="08b62-151">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="08b62-151">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="08b62-152">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="08b62-152">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="08b62-153">**SharingInvitationCreated** (只有當共用資源是網站時，才會記錄此事件) </span><span class="sxs-lookup"><span data-stu-id="08b62-153">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="08b62-154">當目標使用者接受傳送給他們的共用邀請時 (按一下邀請函) 中的連結時，SharePoint 會記錄 **SharingInvitationAccepted** 事件，並指派目標使用者許可權來存取資源。</span><span class="sxs-lookup"><span data-stu-id="08b62-154">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="08b62-155">若目標使用者已傳送匿名連結，則會在目標使用者使用連結存取資源之後記錄 **AnonymousLinkUsed** 事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-155">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="08b62-156">針對安全連結，當外部使用者使用連結存取資源時，會記錄 **FileAccessed** 事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-156">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="08b62-157">也會記錄有關目標使用者的其他資訊，例如邀請的使用者識別碼，以及接受邀請的使用者。</span><span class="sxs-lookup"><span data-stu-id="08b62-157">Additional information about the target user is also logged, such as the identity of the user the invitation is to and the user who accepts the invitation.</span></span> <span data-ttu-id="08b62-158">在某些情況下，這些使用者 (或電子郵件地址) 可能不同。</span><span class="sxs-lookup"><span data-stu-id="08b62-158">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="08b62-159">如何識別與外部使用者共用的資源</span><span class="sxs-lookup"><span data-stu-id="08b62-159">How to identify resources shared with external users</span></span>

<span data-ttu-id="08b62-160">管理員的常見需求是建立與組織外部使用者共用的所有資源清單。</span><span class="sxs-lookup"><span data-stu-id="08b62-160">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="08b62-161">在 Office 365 中使用共用審核，管理員可以產生此清單。</span><span class="sxs-lookup"><span data-stu-id="08b62-161">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="08b62-162">方法如下。</span><span class="sxs-lookup"><span data-stu-id="08b62-162">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="08b62-163">步驟1：搜尋共用事件，並將結果匯出至 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="08b62-163">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="08b62-164">第一步是在審核記錄中搜尋共用事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-164">The first step is to search the audit log for sharing events.</span></span> <span data-ttu-id="08b62-165">如需詳細資訊 (包括搜尋審核記錄檔所需的許可權) ，請參閱在 [安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="08b62-165">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="08b62-166">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="08b62-166">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="08b62-167">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="08b62-167">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="08b62-168">在安全性與合規性中心的左窗格中，按一下 [搜尋]   >  [稽核記錄搜尋]。</span><span class="sxs-lookup"><span data-stu-id="08b62-168">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="08b62-169">[稽核記錄搜尋] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="08b62-169">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="08b62-170">在 [ **活動**] 底下，按一下 [ **共用和存取要求活動** ] 以搜尋共用相關事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-170">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![在 [活動] 底下，選取 [共用和存取要求活動]](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="08b62-172">選取 [日期和時間範圍]，以尋找在該期間內發生的共用事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-172">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="08b62-173">按一下 [ **搜尋** ] 以執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="08b62-173">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="08b62-174">當搜尋執行完畢並顯示結果之後，按一下 [ **匯出結果**] \> **下載所有結果**。</span><span class="sxs-lookup"><span data-stu-id="08b62-174">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="08b62-175">選取 [匯出] 選項之後，視窗底部的訊息會提示您開啟或儲存 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="08b62-175">After you select the export option, a message at the bottom of the window prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="08b62-176">按一下 [**另** 存新檔] \>  ，將 CSV 檔案儲存至本機電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="08b62-176">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="08b62-177">步驟2：使用 PowerQuery 編輯器格式化匯出的審計記錄檔</span><span class="sxs-lookup"><span data-stu-id="08b62-177">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="08b62-178">下一步是在 Power Query 編輯器 Excel 中使用 JSON 轉換功能，以分割 **AuditData** 欄中的每個屬性， (是由多屬性 JSON 物件) 放在自己的欄中。</span><span class="sxs-lookup"><span data-stu-id="08b62-178">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="08b62-179">這可讓您篩選欄，以查看與共享相關的記錄</span><span class="sxs-lookup"><span data-stu-id="08b62-179">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="08b62-180">如需逐步指示，請參閱[匯出、設定及檢視稽核記錄檔的記錄](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的「步驟 2：使用 Power Query 編輯器設定匯出之稽核記錄的格式」(部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="08b62-180">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="08b62-181">步驟3：篩選 CSV 檔案以取得與外部使用者共用的資源</span><span class="sxs-lookup"><span data-stu-id="08b62-181">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="08b62-182">下一步是篩選 CSV，以取得先前在「 [SharePoint 共用事件](#sharepoint-sharing-events)」區段中所述的不同共用相關事件。</span><span class="sxs-lookup"><span data-stu-id="08b62-182">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="08b62-183">或者，您也可以篩選 **TargetUserOrGroupType** 欄，以顯示此屬性的值為 **Guest** 的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="08b62-183">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="08b62-184">在您遵循上一個步驟中的指示，使用 PowerQuery 編輯器準備 CSV 檔案之後，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="08b62-184">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="08b62-185">開啟您在步驟2中建立的 Excel 檔案。</span><span class="sxs-lookup"><span data-stu-id="08b62-185">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="08b62-186">在 [ **首頁** ] 索引標籤上，按一下 [ **排序 & 篩選**]，然後按一下 [ **篩選**]。</span><span class="sxs-lookup"><span data-stu-id="08b62-186">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="08b62-187">在 [**作業**] 欄上的 [**排序 & 篩選**] 下拉式清單中，清除所有選取專案，然後選取下列一或多個與共享相關的事件，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08b62-187">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="08b62-188">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="08b62-188">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="08b62-189">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="08b62-189">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="08b62-190">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="08b62-190">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="08b62-191">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="08b62-191">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="08b62-192">Excel 會顯示所選取之事件的列。</span><span class="sxs-lookup"><span data-stu-id="08b62-192">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="08b62-193">移至名為 **TargetUserOrGroupType** 的欄，並選取它。</span><span class="sxs-lookup"><span data-stu-id="08b62-193">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="08b62-194">在 [ **排序 & 篩選** ] 下拉式清單中，清除所有選取專案，然後選取 [ **TargetUserOrGroupType：來賓**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08b62-194">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="08b62-195">現在 Excel 會顯示共用事件的列，以及目標使用者在組織外部的位置，因為 **TargetUserOrGroupType：來賓** 的值會識別外部使用者。</span><span class="sxs-lookup"><span data-stu-id="08b62-195">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="08b62-196">對於顯示的審計記錄，[ **ObjectId** ] 欄位會識別與目標使用者共用的資源;例如  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` 。</span><span class="sxs-lookup"><span data-stu-id="08b62-196">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
