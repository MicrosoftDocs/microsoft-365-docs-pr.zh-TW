---
title: 客戶加密箱要求
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 深入瞭解客戶密碼箱要求，可讓您控制當您遇到問題時，Microsoft 支援工程師可如何存取您的資料。
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922707"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="6c397-103">Office 365 中的客戶加密箱</span><span class="sxs-lookup"><span data-stu-id="6c397-103">Customer Lockbox in Office 365</span></span>

<span data-ttu-id="6c397-104">本文提供客戶加密箱的部署和設定指導。</span><span class="sxs-lookup"><span data-stu-id="6c397-104">This article provides deployment and configuration guidance for Customer Lockbox.</span></span> <span data-ttu-id="6c397-105">客戶加密箱支援存取 Exchange Online 中的資料、SharePoint 線上和商務 OneDrive 的要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-105">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="6c397-106">若要建議支援其他服務，請提交 [Office 365 UserVoice](https://office365.uservoice.com/)的要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-106">To recommend support for other services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

<span data-ttu-id="6c397-107">若要查看授權您的使用者受益于 Microsoft 365 規範服務（包含這項服務）2020的選項，請參閱 [microsoft 365 授權指南以取得安全性 & 合規性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="6c397-107">To see the options for licensing your users to benefit from Microsoft 365 compliance offerings, including this one, as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="6c397-108">客戶加密箱可確保 Microsoft 無法存取您的內容，即可在未明確核准的情況下執行服務作業。</span><span class="sxs-lookup"><span data-stu-id="6c397-108">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="6c397-109">客戶加密箱會將您帶入核准工作流程，以取得存取內容的要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-109">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="6c397-110">在某些情況下，Microsoft 工程師會協助疑難排解並修正支援流程中的客戶報告問題。</span><span class="sxs-lookup"><span data-stu-id="6c397-110">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="6c397-111">通常，您可以透過 Microsoft 已針對其服務所具備的大量遙測和調試工具，修正問題。</span><span class="sxs-lookup"><span data-stu-id="6c397-111">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="6c397-112">不過，某些案例需要 Microsoft 工程師存取客戶內容，以判斷根本原因並修正問題。</span><span class="sxs-lookup"><span data-stu-id="6c397-112">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="6c397-113">客戶加密箱會要求工程師在核准工作流程的最後一個步驟向客戶要求存取。</span><span class="sxs-lookup"><span data-stu-id="6c397-113">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="6c397-114">這可讓組織選擇核准或拒絕這些要求，並為客戶提供直接存取控制。</span><span class="sxs-lookup"><span data-stu-id="6c397-114">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="6c397-115">客戶加密箱概述影片</span><span class="sxs-lookup"><span data-stu-id="6c397-115">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="6c397-116">客戶加密箱工作流程</span><span class="sxs-lookup"><span data-stu-id="6c397-116">Customer Lockbox workflow</span></span>

<span data-ttu-id="6c397-117">當 Microsoft 工程師初始化客戶加密箱要求時，下列步驟會概括一般的工作流程：</span><span class="sxs-lookup"><span data-stu-id="6c397-117">The following steps outline the typical workflow when a Microsoft engineer initiates a Customer Lockbox request:</span></span>

1. <span data-ttu-id="6c397-118">組織中的某人遇到 Microsoft 365 信箱的問題。</span><span class="sxs-lookup"><span data-stu-id="6c397-118">Someone at an organization experiences an issue with their Microsoft 365 mailbox.</span></span>

2. <span data-ttu-id="6c397-119">在使用者診斷問題，但無法修正時，他們會以 Microsoft 支援服務開啟支援要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-119">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="6c397-120">Microsoft 支援工程師會檢查服務要求，並決定是否需要存取組織的承租人，以在 Exchange Online 中修復問題。</span><span class="sxs-lookup"><span data-stu-id="6c397-120">A Microsoft support engineer reviews the service request and determines a need to access the organization's tenant to repair the issue in Exchange Online.</span></span>

4. <span data-ttu-id="6c397-121">Microsoft 支援工程師會登入客戶加密箱要求工具，並進行資料存取要求，其中包含組織的租使用者名稱、服務要求號碼，以及工程師需要存取資料的預估時間。</span><span class="sxs-lookup"><span data-stu-id="6c397-121">The Microsoft support engineer logs into the Customer Lockbox request tool and makes a data access request that includes the organization's tenant name, service request number, and the estimated time the engineer needs access to the data.</span></span>

5. <span data-ttu-id="6c397-122">Microsoft 支援管理員核准要求後，客戶加密箱會傳送組織中指定的核准者的電子郵件通知，告知 Microsoft 的未決存取要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-122">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the organization an email notification about the pending access request from Microsoft.</span></span>

    ![客戶加密箱電子郵件通知範例](../media/CustomerLockbox1.png)

   <span data-ttu-id="6c397-124">在 Microsoft 365 系統管理中心中指派 [客戶密碼箱存取核准者](/office365/admin/add-users/about-admin-roles) 系統管理員角色的任何人，都可以核准客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-124">Anyone who is assigned the [Customer Lockbox access approver](/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

6. <span data-ttu-id="6c397-125">核准者會登入 Microsoft 365 系統管理中心，並核准要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-125">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="6c397-126">此步驟會觸發搜尋審核記錄檔，以建立可使用的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="6c397-126">This step triggers the creation of an audit record available by searching the audit log.</span></span> <span data-ttu-id="6c397-127">如需詳細資訊，請參閱 [審核客戶密碼箱要求](#auditing-customer-lockbox-requests)。</span><span class="sxs-lookup"><span data-stu-id="6c397-127">For more information, see [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).</span></span>

   <span data-ttu-id="6c397-128">如果客戶拒絕要求，或未在12小時內核准要求，要求就會到期，而且不會授與 Microsoft 工程師的存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-128">If the customer rejects the request or doesn't approve the request within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6c397-129">Microsoft 不會在客戶密碼箱的電子郵件通知中包含任何需要您登入 Office 365 的連結。</span><span class="sxs-lookup"><span data-stu-id="6c397-129">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

7. <span data-ttu-id="6c397-130">組織中的核准者核准要求之後，Microsoft 工程師會收到核准訊息，登入 Exchange Online 中的租使用者，並修正客戶的問題。</span><span class="sxs-lookup"><span data-stu-id="6c397-130">After the approver from the organization approves the request, the Microsoft engineer receives the approval message, logs into the tenant in Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="6c397-131">Microsoft 工程師已要求期間修正問題，之後將自動撤銷存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-131">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="6c397-132">Microsoft 工程師所執行的所有動作都會記錄在審計記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="6c397-132">All actions performed by a Microsoft engineer are logged in the audit log.</span></span> <span data-ttu-id="6c397-133">您可以搜尋並複查這些審計記錄。</span><span class="sxs-lookup"><span data-stu-id="6c397-133">You can search for and review these audit records.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="6c397-134">開啟或關閉客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="6c397-134">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="6c397-135">您可以在 Microsoft 365 系統管理中心中開啟客戶密碼箱控制項。</span><span class="sxs-lookup"><span data-stu-id="6c397-135">You can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6c397-136">當您開啟客戶密碼箱時，Microsoft 必須先取得您的組織核准，才能存取任何租使用者的內容。</span><span class="sxs-lookup"><span data-stu-id="6c397-136">When you turn on Customer Lockbox, Microsoft must obtain your organization's approval before accessing any of your tenant's content.</span></span>

1. <span data-ttu-id="6c397-137">使用指派有全域管理員或 **客戶密碼箱存取核准者** 角色的工作或學校帳戶，移至並登 [https://admin.microsoft.com](https://admin.microsoft.com) 入。</span><span class="sxs-lookup"><span data-stu-id="6c397-137">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="6c397-138">選擇 [ **設定] > 的組織設定**。</span><span class="sxs-lookup"><span data-stu-id="6c397-138">Choose **Settings > Org Settings**.</span></span>

3. <span data-ttu-id="6c397-139">選取 [**安全性 & 隱私權**  >  **客戶密碼箱**  >  **編輯**]，然後將開關移至 [**開啟**] 或 [**關閉**] 開啟或關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="6c397-139">Select **Security & Privacy** > **Customer Lockbox** > **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="6c397-141">核准或拒絕客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="6c397-141">Approve or deny a Customer Lockbox request</span></span>

1. <span data-ttu-id="6c397-142">使用指派有全域管理員或 **客戶密碼箱存取核准者** 角色的工作或學校帳戶，移至並登 [https://admin.microsoft.com](https://admin.microsoft.com) 入。</span><span class="sxs-lookup"><span data-stu-id="6c397-142">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="6c397-143">選擇 [ **支援 > 客戶加密箱要求**。</span><span class="sxs-lookup"><span data-stu-id="6c397-143">Choose **Support > Customer Lockbox Requests**.</span></span>

    ![按一下 [支援]，然後按一下 [客戶密碼箱要求]](../media/CustomerLockbox5.png)

    <span data-ttu-id="6c397-145">客戶加密箱要求的清單隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="6c397-145">A list of Customer Lockbox requests displays.</span></span>

    ![客戶加密箱要求的清單](../media/CustomerLockbox6.png)

3. <span data-ttu-id="6c397-147">選取客戶加密箱要求，然後選擇 [ **核准** ] 或 [ **拒絕**]。</span><span class="sxs-lookup"><span data-stu-id="6c397-147">Select a Customer Lockbox request, and then choose **Approve** or **Deny**.</span></span>

    ![核准或拒絕客戶加密箱要求](../media/CustomerLockbox7.png)

    <span data-ttu-id="6c397-149">會顯示客戶加密箱要求之核准的確認訊息。</span><span class="sxs-lookup"><span data-stu-id="6c397-149">A confirmation message about the approval of the Customer Lockbox request displays.</span></span>

    ![核准或拒絕客戶加密箱要求](../media/CustomerLockbox8.png)

> [!NOTE]
> <span data-ttu-id="6c397-151">使用 Set-AccessToCustomerDataRequest Cmdlet 來核准、拒絕或取消由 Microsoft 支援工程師控制您資料存取權的 Microsoft 365 客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-151">Use the Set-AccessToCustomerDataRequest cmdlet to approve, deny, or cancel Microsoft 365 customer lockbox requests that control access to your data by Microsoft support engineers.</span></span> <span data-ttu-id="6c397-152">如需詳細資訊，請參閱 [AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest)。</span><span class="sxs-lookup"><span data-stu-id="6c397-152">For more information, see [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest).</span></span>


## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="6c397-153">審核客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="6c397-153">Auditing Customer Lockbox requests</span></span>

<span data-ttu-id="6c397-154">對應至客戶密碼箱要求的審計記錄會記錄在審計記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="6c397-154">Audit records that correspond to the Customer Lockbox requests are logged in the audit log.</span></span> <span data-ttu-id="6c397-155">您可以使用安全性 & 規範中心中的「 [審核記錄搜尋」工具](search-the-audit-log-in-security-and-compliance.md) ，存取這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="6c397-155">You can access these logs by using the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="6c397-156">有關接受或拒絕客戶加密箱要求的動作，以及 Microsoft 工程師所執行的動作) 也會記錄在審計記錄檔中 (當存取要求獲核准時。</span><span class="sxs-lookup"><span data-stu-id="6c397-156">Actions related to accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are also logged in the audit log.</span></span> <span data-ttu-id="6c397-157">您可以搜尋並複查這些審計記錄。</span><span class="sxs-lookup"><span data-stu-id="6c397-157">You can search for and review these audit records.</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="6c397-158">在審計記錄檔中搜尋與客戶加密箱要求相關的活動</span><span class="sxs-lookup"><span data-stu-id="6c397-158">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="6c397-159">在您可以使用「審核記錄檔」追蹤客戶的要求之後，您必須採取一些步驟來設定審核記錄。</span><span class="sxs-lookup"><span data-stu-id="6c397-159">Before you can use the audit log to track requests for Customer Lockbox, there are some steps you need to take to set up audit logging.</span></span> <span data-ttu-id="6c397-160">如需詳細資訊，請參閱在 [安全性 & 規範中心搜尋審核記錄](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)檔。</span><span class="sxs-lookup"><span data-stu-id="6c397-160">For more information, see [Search the audit log in the Security & Compliance Center](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span> <span data-ttu-id="6c397-161">完成安裝後，請使用下列步驟來建立審核記錄搜尋查詢，以傳回與客戶密碼箱相關的審計記錄：</span><span class="sxs-lookup"><span data-stu-id="6c397-161">Once you've completed setup, use these steps to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="6c397-162">請移至 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="6c397-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="6c397-163">使用您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6c397-163">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="6c397-164">在安全性 & 規範中心的左窗格中，選擇 [**搜尋 & 調查**  >  **審核記錄搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="6c397-164">In the left pane of the Security & Compliance Center, choose **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="6c397-165">[ **審計記錄檔搜尋** ] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="6c397-165">The **Audit log search** page displays.</span></span>

    ![審核記錄搜尋頁面](../media/auditlogsearch1.png)
  
4. <span data-ttu-id="6c397-167">設定下列搜尋準則：</span><span class="sxs-lookup"><span data-stu-id="6c397-167">Configure the following search criteria:</span></span>

    1. <span data-ttu-id="6c397-168">**活動** -將此欄位保留空白，讓搜尋傳回所有活動的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="6c397-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="6c397-169">若要傳回與 Microsoft 工程師所執行之客戶加密箱要求和對應活動相關的任何審計記錄，必須這麼做。</span><span class="sxs-lookup"><span data-stu-id="6c397-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    1. <span data-ttu-id="6c397-170">**開始日期** 和 **結束日期** -選取日期和時間範圍，以顯示在該期間內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="6c397-170">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    1. <span data-ttu-id="6c397-171">**使用者** -將此欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="6c397-171">**Users** - Leave this field blank.</span></span>

    1. <span data-ttu-id="6c397-172">**檔、資料夾或網站** -將此欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="6c397-172">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="6c397-173">按一下 **[搜尋]** 以使用您的搜尋準則執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="6c397-173">Click **Search** to run the search using your search criteria.</span></span>

    <span data-ttu-id="6c397-174">搜尋結果會經過載入，然後在 [**審計記錄檔搜尋**] 頁面的 [**結果**] 底下出現一段時間。</span><span class="sxs-lookup"><span data-stu-id="6c397-174">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="6c397-175">按一下搜尋結果頁面上的 [ **篩選結果** ]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="6c397-175">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="6c397-176">若要顯示與組織中核准或拒絕客戶加密箱要求相關之核准的審計記錄：在 [ **活動** ] 欄下方的方塊中，輸入 **AccessToCustomerDataRequest**。</span><span class="sxs-lookup"><span data-stu-id="6c397-176">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="6c397-177">顯示與 Microsoft 工程師相關的審計記錄，以回應核准的客戶加密箱要求：在 [ **使用者** ] 欄下方的方塊中，輸入 **Microsoft 接線員**。</span><span class="sxs-lookup"><span data-stu-id="6c397-177">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="6c397-178">[ **活動** ] 欄會顯示工程師所執行的動作。</span><span class="sxs-lookup"><span data-stu-id="6c397-178">The **Activity** column displays the action performed by the engineer.</span></span>

      ![在 "Microsoft 接線員" 上篩選以顯示審計記錄](../media/CustomerLockbox10.png)

7. <span data-ttu-id="6c397-180">在結果清單中，按一下要顯示的審計記錄。</span><span class="sxs-lookup"><span data-stu-id="6c397-180">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="6c397-181">客戶加密箱存取要求的審計記錄</span><span class="sxs-lookup"><span data-stu-id="6c397-181">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="6c397-182">當您組織中的人員核准或拒絕客戶加密箱要求時，會在審計記錄檔中記錄審計記錄。</span><span class="sxs-lookup"><span data-stu-id="6c397-182">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the audit log.</span></span> <span data-ttu-id="6c397-183">此記錄包含下列資訊。</span><span class="sxs-lookup"><span data-stu-id="6c397-183">This record contains the following information.</span></span>

| <span data-ttu-id="6c397-184">Audit record 屬性</span><span class="sxs-lookup"><span data-stu-id="6c397-184">Audit record property</span></span>| <span data-ttu-id="6c397-185">描述</span><span class="sxs-lookup"><span data-stu-id="6c397-185">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="6c397-186">日期</span><span class="sxs-lookup"><span data-stu-id="6c397-186">Date</span></span>       | <span data-ttu-id="6c397-187">客戶加密箱要求核准或拒絕的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="6c397-187">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="6c397-188">IP 位址</span><span class="sxs-lookup"><span data-stu-id="6c397-188">IP address</span></span> | <span data-ttu-id="6c397-189">核准者用來核准或拒絕要求之電腦的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6c397-189">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="6c397-190">使用者</span><span class="sxs-lookup"><span data-stu-id="6c397-190">User</span></span>       | <span data-ttu-id="6c397-191">服務帳戶 BOXServiceAccount@ \[ customerforest \] 。 prod.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="6c397-191">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="6c397-192">活動</span><span class="sxs-lookup"><span data-stu-id="6c397-192">Activity</span></span>   | <span data-ttu-id="6c397-193">Set-AccessToCustomerDataRequest;這是當您核准或拒絕客戶加密箱要求時所記錄的審計活動。</span><span class="sxs-lookup"><span data-stu-id="6c397-193">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="6c397-194">項目</span><span class="sxs-lookup"><span data-stu-id="6c397-194">Item</span></span>       | <span data-ttu-id="6c397-195">客戶加密箱要求的 Guid</span><span class="sxs-lookup"><span data-stu-id="6c397-195">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="6c397-196">下列螢幕擷取畫面顯示對應至已核准客戶加密箱要求的審計記錄檔範例。</span><span class="sxs-lookup"><span data-stu-id="6c397-196">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="6c397-197">如果客戶加密箱要求遭到拒絕，則 **ApprovalDecision** 參數的值將會是 **Deny**。</span><span class="sxs-lookup"><span data-stu-id="6c397-197">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![核准客戶加密箱要求的審計記錄](../media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="6c397-199">若要在審計記錄中顯示更詳細的資訊，請按一下 [ **詳細資訊**]。</span><span class="sxs-lookup"><span data-stu-id="6c397-199">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="6c397-200">Microsoft 工程師所執行動作的審計記錄</span><span class="sxs-lookup"><span data-stu-id="6c397-200">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="6c397-201">客戶加密箱要求經過核准後，Microsoft 工程師會執行的動作 (，而且可能會導致存取客戶內容) 記錄在審計記錄中。</span><span class="sxs-lookup"><span data-stu-id="6c397-201">The actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="6c397-202">這些記錄包含下列資訊。</span><span class="sxs-lookup"><span data-stu-id="6c397-202">These records contain the following information.</span></span>

| <span data-ttu-id="6c397-203">Audit record 屬性</span><span class="sxs-lookup"><span data-stu-id="6c397-203">Audit record property</span></span>| <span data-ttu-id="6c397-204">描述</span><span class="sxs-lookup"><span data-stu-id="6c397-204">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="6c397-205">日期</span><span class="sxs-lookup"><span data-stu-id="6c397-205">Date</span></span>       | <span data-ttu-id="6c397-206">執行動作的日期時間。</span><span class="sxs-lookup"><span data-stu-id="6c397-206">Date time when the action was performed.</span></span> <span data-ttu-id="6c397-207">請注意，此動作執行的時間會在客戶加密箱要求核准的4小時內。</span><span class="sxs-lookup"><span data-stu-id="6c397-207">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="6c397-208">IP 位址</span><span class="sxs-lookup"><span data-stu-id="6c397-208">IP address</span></span> | <span data-ttu-id="6c397-209">Microsoft 工程師使用的電腦 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6c397-209">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="6c397-210">使用者</span><span class="sxs-lookup"><span data-stu-id="6c397-210">User</span></span>       | <span data-ttu-id="6c397-211">Microsoft 操作員;此值表示此記錄與客戶加密箱要求相關。</span><span class="sxs-lookup"><span data-stu-id="6c397-211">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="6c397-212">活動</span><span class="sxs-lookup"><span data-stu-id="6c397-212">Activity</span></span>   | <span data-ttu-id="6c397-213">Microsoft 工程師所執行的活動名稱。</span><span class="sxs-lookup"><span data-stu-id="6c397-213">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="6c397-214">項目</span><span class="sxs-lookup"><span data-stu-id="6c397-214">Item</span></span>       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a><span data-ttu-id="6c397-215">常見問題集</span><span class="sxs-lookup"><span data-stu-id="6c397-215">Frequently asked questions</span></span>

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="6c397-216">客戶加密箱適用于哪些 Microsoft 365 服務？</span><span class="sxs-lookup"><span data-stu-id="6c397-216">Which Microsoft 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="6c397-217">客戶加密箱目前在 Exchange Online 中支援，SharePoint 線上，且 OneDrive 商務。</span><span class="sxs-lookup"><span data-stu-id="6c397-217">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-customers"></a><span data-ttu-id="6c397-218">客戶加密箱是否可供所有客戶使用？</span><span class="sxs-lookup"><span data-stu-id="6c397-218">Is Customer Lockbox available to all customers?</span></span>

<span data-ttu-id="6c397-219">客戶加密箱隨附于 Microsoft 365 或 Office 365 E5 訂閱中，而且可以新增至具有資訊保護和合規性的其他計畫，也可以新增至其他計畫。</span><span class="sxs-lookup"><span data-stu-id="6c397-219">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="6c397-220">如需詳細資訊，請參閱 [方案和價格](https://products.office.com/business/office-365-enterprise-e5-business-software) 。</span><span class="sxs-lookup"><span data-stu-id="6c397-220">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="6c397-221">何謂客戶內容？</span><span class="sxs-lookup"><span data-stu-id="6c397-221">What is customer content?</span></span>

<span data-ttu-id="6c397-222">客戶內容是由 Microsoft 365 服務和應用程式的使用者所建立的資料。</span><span class="sxs-lookup"><span data-stu-id="6c397-222">Customer content is the data created by users of Microsoft 365 services and applications.</span></span> <span data-ttu-id="6c397-223">客戶內容的範例包括：</span><span class="sxs-lookup"><span data-stu-id="6c397-223">Examples of customer content include:</span></span>

- <span data-ttu-id="6c397-224">電子郵件內文或電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="6c397-224">Email body or email attachments</span></span>

- <span data-ttu-id="6c397-225">SharePoint 網站內容</span><span class="sxs-lookup"><span data-stu-id="6c397-225">SharePoint site contents</span></span>

- <span data-ttu-id="6c397-226">SharePoint 檔本文中的資訊</span><span class="sxs-lookup"><span data-stu-id="6c397-226">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="6c397-227">商務用 Skype 簡報檔內文</span><span class="sxs-lookup"><span data-stu-id="6c397-227">Skype for Business presentation file body</span></span>

- <span data-ttu-id="6c397-228">立即訊息 (IM) 或語音交談</span><span class="sxs-lookup"><span data-stu-id="6c397-228">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="6c397-229">客戶產生的 blob 或結構化儲存資料 (例如，SQL 容器) </span><span class="sxs-lookup"><span data-stu-id="6c397-229">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="6c397-230">客戶擁有的安全性資訊 (例如憑證、加密金鑰和密碼) </span><span class="sxs-lookup"><span data-stu-id="6c397-230">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="6c397-231">推斷及所有後續的推斷，如果客戶內容仍然存在</span><span class="sxs-lookup"><span data-stu-id="6c397-231">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="6c397-232">如需 Office 365 中客戶內容的詳細資訊，請參閱 [Office 365 信任中心](https://products.office.com/business/office-365-trust-center-privacy/)。</span><span class="sxs-lookup"><span data-stu-id="6c397-232">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="6c397-233">要求存取我的內容時，誰會收到通知？</span><span class="sxs-lookup"><span data-stu-id="6c397-233">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="6c397-234">全域管理員及已指派客戶密碼箱存取核准者系統管理員角色的任何人都會收到通知。</span><span class="sxs-lookup"><span data-stu-id="6c397-234">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="6c397-235">這些使用者也是可核准客戶加密箱要求的使用者。</span><span class="sxs-lookup"><span data-stu-id="6c397-235">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="6c397-236">誰可以核准或拒絕組織中的這些要求？</span><span class="sxs-lookup"><span data-stu-id="6c397-236">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="6c397-237">全域系統管理員和任何獲指派客戶密碼箱存取權管理員角色的人員，都可以核准客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-237">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="6c397-238">客戶在其組織中控制這些角色指派。</span><span class="sxs-lookup"><span data-stu-id="6c397-238">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="6c397-239">如何加入宣告客戶密碼箱？</span><span class="sxs-lookup"><span data-stu-id="6c397-239">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="6c397-240">全域管理員可以在 Microsoft 365 或 Microsoft 365 系統管理中心內啟用和設定客戶加密箱。</span><span class="sxs-lookup"><span data-stu-id="6c397-240">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="6c397-241">如果我核准客戶加密箱要求，工程師可以做什麼，如何知道我的 Microsoft 工程師會怎麼做？</span><span class="sxs-lookup"><span data-stu-id="6c397-241">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="6c397-242">核准客戶加密箱要求之後，Microsoft 工程師會授與這些必要的許可權，以使用預先核准的 Cmdlet 存取客戶內容。</span><span class="sxs-lookup"><span data-stu-id="6c397-242">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="6c397-243">Microsoft 工程師在回應客戶加密箱要求時所採取的動作會在安全性 & 合規性中心的審計記錄檔中記錄和存取。</span><span class="sxs-lookup"><span data-stu-id="6c397-243">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="6c397-244">如何知道 Microsoft 遵循核准程式？</span><span class="sxs-lookup"><span data-stu-id="6c397-244">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="6c397-245">您可以使用 Microsoft 365 系統管理中心內的客戶加密箱要求記錄，在組織中相互參照傳送給系統管理員和核准者的電子郵件核准通知。</span><span class="sxs-lookup"><span data-stu-id="6c397-245">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="6c397-246">客戶加密箱包含在最新的 [SOC 1 SSAE 16 審核報告](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)中。</span><span class="sxs-lookup"><span data-stu-id="6c397-246">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="6c397-247">如需詳細資訊，您可以在 [Microsoft 服務信任入口網站](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)中尋找最新的報告。</span><span class="sxs-lookup"><span data-stu-id="6c397-247">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="6c397-248">Microsoft 是否可以修改我租使用者的核准者清單？</span><span class="sxs-lookup"><span data-stu-id="6c397-248">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="6c397-249">如果不是，它會如何避免？</span><span class="sxs-lookup"><span data-stu-id="6c397-249">If not, how is it prevented?</span></span>

<span data-ttu-id="6c397-250">只有組織中的全域管理員可以指定誰可以核准客戶加密箱要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-250">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="6c397-251">這表示只有 Azure Active Directory 中全域管理員群組的成員可以指定誰可以核准要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-251">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="6c397-252">Azure Active Directory 中全域管理員群組的成員資格只由您的組織管理。</span><span class="sxs-lookup"><span data-stu-id="6c397-252">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="6c397-253">如果我需要內容存取要求的詳細資訊來核准它，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="6c397-253">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="6c397-254">每個客戶加密箱要求都包含 Microsoft 365 服務要求號碼。</span><span class="sxs-lookup"><span data-stu-id="6c397-254">Each Customer Lockbox request contains a Microsoft 365 service request number.</span></span> <span data-ttu-id="6c397-255">您可以聯繫 Microsoft 支援部門並參考此服務號碼，以取得有關要求的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6c397-255">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="6c397-256">客戶加密箱要求獲批准時，許可權的有效期是多久？</span><span class="sxs-lookup"><span data-stu-id="6c397-256">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="6c397-257">目前，授與 Microsoft 工程師之存取權限的最長期限是4小時。</span><span class="sxs-lookup"><span data-stu-id="6c397-257">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="6c397-258">Microsoft 工程師也可以要求較短的期間。</span><span class="sxs-lookup"><span data-stu-id="6c397-258">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="6c397-259">如何取得所有客戶加密箱要求的歷史記錄？</span><span class="sxs-lookup"><span data-stu-id="6c397-259">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="6c397-260">所有客戶加密箱要求都是在 Microsoft 365 系統管理中心中查看。</span><span class="sxs-lookup"><span data-stu-id="6c397-260">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="6c397-261">如何將內容存取要求與相關的審計記錄檔關聯？</span><span class="sxs-lookup"><span data-stu-id="6c397-261">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="6c397-262">「規範中心」活動摘要包含客戶密碼箱的記錄活動。</span><span class="sxs-lookup"><span data-stu-id="6c397-262">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="6c397-263">客戶可以對照接收的電子郵件要求，從活動摘要中，對客戶加密箱記錄活動進行互交。</span><span class="sxs-lookup"><span data-stu-id="6c397-263">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="6c397-264">當客戶未回應客戶加密箱要求時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="6c397-264">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="6c397-265">客戶加密箱要求的預設工期為12小時。</span><span class="sxs-lookup"><span data-stu-id="6c397-265">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="6c397-266">如果您未在12小時內回應要求，要求就會到期。</span><span class="sxs-lookup"><span data-stu-id="6c397-266">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="6c397-267">當客戶拒絕客戶加密箱要求時，Microsoft 會執行什麼動作？</span><span class="sxs-lookup"><span data-stu-id="6c397-267">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="6c397-268">如果客戶拒絕客戶加密箱要求，就不會發生客戶內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-268">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="6c397-269">如果您組織中的使用者繼續遇到服務問題，而要求 Microsoft 存取客戶內容以解決問題，則服務問題可能會繼續，而 Microsoft 會通知使用者這一點。</span><span class="sxs-lookup"><span data-stu-id="6c397-269">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="6c397-270">客戶加密箱是否要防範法律強制執行機構或其他協力廠商的資料要求？</span><span class="sxs-lookup"><span data-stu-id="6c397-270">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="6c397-271">否。</span><span class="sxs-lookup"><span data-stu-id="6c397-271">No.</span></span> <span data-ttu-id="6c397-272">Microsoft 會認真對待客戶資料的協力廠商要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-272">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="6c397-273">身為雲端服務提供者，Microsoft 總支援客戶資料的隱私權。</span><span class="sxs-lookup"><span data-stu-id="6c397-273">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="6c397-274">在我們取得傳票的情況下，Microsoft 一定會嘗試將協力廠商重新導向至客戶以取得資訊。</span><span class="sxs-lookup"><span data-stu-id="6c397-274">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="6c397-275"> (讀取 Brad Smith 的博客： [防止客戶資料) 政府窺探](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 。</span><span class="sxs-lookup"><span data-stu-id="6c397-275">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="6c397-276">我們會定期發佈 Microsoft 所收到之法律強制要求的 [詳細資訊](https://www.microsoft.com/corporate-responsibility/lerr) 。</span><span class="sxs-lookup"><span data-stu-id="6c397-276">We periodically publish [detailed information](https://www.microsoft.com/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="6c397-277">如需詳細資訊，請參閱有關協力廠商資料要求和[線上服務條款](https://www.microsoft.com/Licensing/product-licensing/products.aspx)中「客戶資料的洩漏」一節的[Microsoft 信任中心](https://www.microsoft.com/trustcenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6c397-277">See the [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="6c397-278">Microsoft 如何確保其員工的成員無法存取 Office 365 應用程式中的客戶內容？</span><span class="sxs-lookup"><span data-stu-id="6c397-278">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="6c397-279">Microsoft 透過存取控制系統來執行大量的預防措施，以及偵探措施來識別並處理繞過這些存取控制系統的企圖。</span><span class="sxs-lookup"><span data-stu-id="6c397-279">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="6c397-280">Microsoft 365 的運作方式是最低許可權和即時存取的原則。</span><span class="sxs-lookup"><span data-stu-id="6c397-280">Microsoft 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="6c397-281">因此，任何 Microsoft 人員都沒有任何可讓您不斷存取客戶內容的許可權。</span><span class="sxs-lookup"><span data-stu-id="6c397-281">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="6c397-282">如果授與許可權，它會在有限期限內。</span><span class="sxs-lookup"><span data-stu-id="6c397-282">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="6c397-283">Microsoft 365 使用稱為「 *密碼箱* 」的存取控制系統，處理授與服務中執行作業和系統管理功能之許可權的許可權要求。</span><span class="sxs-lookup"><span data-stu-id="6c397-283">Microsoft 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="6c397-284">操作員必須使用密碼箱要求存取客戶內容，然後再要求第二個人採取要求的動作 (例如，核准它) ，再授與存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-284">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="6c397-285">第二個人不能是要求者，必須指定以核准客戶內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-285">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="6c397-286">只有在核准要求時，操作員才能取得客戶內容的暫時存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-286">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="6c397-287">提升期限到期後，密碼箱會撤銷存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-287">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="6c397-288">請參閱 [線上服務條款](https://www.microsoft.com/licensing/product-licensing/products) ，以取得 Microsoft 一般安全性作法的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6c397-288">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="6c397-289">在哪些情況下，Microsoft 工程師需要存取我的內容？</span><span class="sxs-lookup"><span data-stu-id="6c397-289">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="6c397-290">最常見的情形是 Microsoft 工程師需要存取客戶內容的情形是，當客戶進行支援的支援要求時，需要存取權。</span><span class="sxs-lookup"><span data-stu-id="6c397-290">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="6c397-291">Microsoft 365 的基礎原則是服務的運作方式，不需要 Microsoft 存取客戶內容。</span><span class="sxs-lookup"><span data-stu-id="6c397-291">A foundational principle of Microsoft 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="6c397-292">Microsoft 所執行的所有服務作業幾乎都是完全自動化的，人工干預是高度控制的，而且會從客戶內容中進一步抽象出來。</span><span class="sxs-lookup"><span data-stu-id="6c397-292">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="6c397-293">Microsoft 365 的目標是存取客戶內容以支援服務，直到客戶核准特定的 Microsoft access 要求為止。</span><span class="sxs-lookup"><span data-stu-id="6c397-293">The goal for Microsoft 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="6c397-294">我已將我的資料設為與 Microsoft 雲端的安全性，所以我為何需要客戶密碼箱？</span><span class="sxs-lookup"><span data-stu-id="6c397-294">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="6c397-295">客戶加密箱為客戶提供服務作業的明確存取授權功能，提供額外的控制層級。</span><span class="sxs-lookup"><span data-stu-id="6c397-295">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="6c397-296">透過示範明確資料存取授權的程式，客戶加密箱也可協助客戶符合特定合規性義務，例如 HIPAA 和 FEDRAMP。</span><span class="sxs-lookup"><span data-stu-id="6c397-296">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>