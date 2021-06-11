---
title: 在 Microsoft 365 中設定基本審核
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
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文說明如何設定基本審核，讓您可以開始搜尋組織中使用者和系統管理員所執行的審計活動。
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564820"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a><span data-ttu-id="188be-103">在 Microsoft 365 中設定基本審核</span><span class="sxs-lookup"><span data-stu-id="188be-103">Set up Basic Audit in Microsoft 365</span></span>

<span data-ttu-id="188be-104">Microsoft 365 的基本審核可讓您針對使用者和系統管理員在不同 Microsoft 365 服務中執行的活動，搜尋審計記錄。</span><span class="sxs-lookup"><span data-stu-id="188be-104">Basic Audit in Microsoft 365 lets you search for audit records for activities performed in the different Microsoft 365 services by users and admins.</span></span> <span data-ttu-id="188be-105">因為對於大多數的 Microsoft 365 和 Office 365 組織而言，預設會啟用基本審核，所以組織中的其他人可以搜尋審核記錄之前，只需要做一些工作。</span><span class="sxs-lookup"><span data-stu-id="188be-105">Because Basic Audit is enabled by default for most Microsoft 365 and Office 365 organizations, there's only a few things you need to do before you and others in your organization can search the audit log.</span></span>

<span data-ttu-id="188be-106">本文討論設定基本審核所需的下列步驟。</span><span class="sxs-lookup"><span data-stu-id="188be-106">This article discusses the following steps necessary to set up Basic Audit.</span></span>

![設定基本審核的步驟](../media/BasicAuditingWorkflow.png)

<span data-ttu-id="188be-108">這些步驟包括確定適當的組織訂閱和使用者授權，以產生及保留審計記錄，並將安全性作業、IT、規範和法律團隊的許可權指派給小組成員，以便搜尋審核記錄。</span><span class="sxs-lookup"><span data-stu-id="188be-108">These steps include ensuring the proper organizational subscriptions and user licensing required to generate and preserve audit records and assigning permissions to team members of your security operations, IT, compliance, and legal teams so that can search the audit log.</span></span>

<span data-ttu-id="188be-109">如需詳細資訊，請參閱[Microsoft 365 中的基本審核](auditing-solutions-overview.md#basic-audit)。</span><span class="sxs-lookup"><span data-stu-id="188be-109">For more information, see [Basic Audit in Microsoft 365](auditing-solutions-overview.md#basic-audit).</span></span>

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a><span data-ttu-id="188be-110">步驟1：確認組織訂閱和使用者授權</span><span class="sxs-lookup"><span data-stu-id="188be-110">Step 1: Verify organization subscription and user licensing</span></span>

<span data-ttu-id="188be-111">授權進行基本審核需要適當的組織訂閱，以提供記錄及保留審計記錄所需之審核記錄搜尋工具和每個使用者授權的存取權。</span><span class="sxs-lookup"><span data-stu-id="188be-111">Licensing for Basic Audit requires the appropriate organization subscription that provides access to audit log search tool and per-user licensing that's required to log and retain audit records.</span></span>

<span data-ttu-id="188be-112">當使用者或系統管理員執行稽核的活動時，稽核記錄會隨即產生，並儲存在您組織的稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="188be-112">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="188be-113">在基本審核中，審計記錄會保留在90天的審計記錄中並可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="188be-113">In Basic Audit, audit records are retained and searchable in the audit log for 90 days.</span></span>

<span data-ttu-id="188be-114">如需基本審核的訂閱與授權需求清單，請參閱[Microsoft 365 中的審計方案](auditing-solutions-overview.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="188be-114">For a list of subscription and licensing requirements for Basic Audit, see [Auditing solutions in Microsoft 365](auditing-solutions-overview.md#licensing-requirements).</span></span>

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a><span data-ttu-id="188be-115">步驟2：指派許可權以搜尋審核記錄</span><span class="sxs-lookup"><span data-stu-id="188be-115">Step 2: Assign permissions to search the audit log</span></span>

<span data-ttu-id="188be-116">管理員和調查小組成員必須獲 Exchange Online 中的「View-Only 審計記錄」或「審計記錄」角色，才可搜尋審計記錄。</span><span class="sxs-lookup"><span data-stu-id="188be-116">Admins and members of investigation teams must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the audit log.</span></span> <span data-ttu-id="188be-117">根據預設，這些角色會在 Exchange 系統管理員中心的 **[權限]** 頁面上，指派給 [法務遵循管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="188be-117">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="188be-118">Office 365 和 Microsoft 365 中的全域系統管理員會自動新增為 Exchange Online 中的「組織管理」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="188be-118">Global administrators in Office 365 and Microsoft 365 are automatically added as members of the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="188be-119">若要提供讓使用者能夠搜尋稽核記錄的最低權限等級，您可以在 Exchange Online 中建立自訂角色群組、新增 [僅限檢視稽核記錄] 或 [稽核記錄] 角色，然後將使用者加入這個新的角色群組成為其中的成員。</span><span class="sxs-lookup"><span data-stu-id="188be-119">To give a user the ability to search the audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="188be-120">如需詳細資訊，請參閱[管理 Exchange Online 中的角色群組](/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="188be-120">For more information, see [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>

<span data-ttu-id="188be-121">下列螢幕擷取畫面顯示在 Exchange 系統管理中心中指派給組織管理角色群組的兩個與審核相關的角色。</span><span class="sxs-lookup"><span data-stu-id="188be-121">The following screenshot shows the two audit-related roles assigned to the Organization Management role group in the Exchange admin center.</span></span>

![在 Exchange Online 中指派給角色群組的審核角色](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a><span data-ttu-id="188be-123">步驟3：搜尋審核記錄檔</span><span class="sxs-lookup"><span data-stu-id="188be-123">Step 3: Search the audit log</span></span>

<span data-ttu-id="188be-124">現在，您已準備好在 Microsoft 365 規範中心搜尋審核記錄。</span><span class="sxs-lookup"><span data-stu-id="188be-124">Now you're ready to search the audit log in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="188be-125">移至 <https://compliance.microsoft.com> 並使用已獲指派適當的「審核」許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="188be-125">Go to <https://compliance.microsoft.com> and sign in using an account that has been assigned the appropriate audit permissions.</span></span>

2. <span data-ttu-id="188be-126">在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [**審計**]。</span><span class="sxs-lookup"><span data-stu-id="188be-126">In the left navigation pane of the Microsoft 365 compliance center, click **Show all** and then click **Audit**.</span></span>

3. <span data-ttu-id="188be-127">在 [ **審計** ] 頁面上的 [ **搜尋] 索引** 標籤上，使用下列條件設定搜尋。</span><span class="sxs-lookup"><span data-stu-id="188be-127">On the **Audit** page, configure the search using the following conditions on the **Search** tab.</span></span> 

   ![審核記錄搜尋的設定設定](../media/AuditLogSearchToolMCCCallouts.png)

   1. <span data-ttu-id="188be-129">**日期和時間範圍**。</span><span class="sxs-lookup"><span data-stu-id="188be-129">**Date and time range**.</span></span> <span data-ttu-id="188be-130">選取日期和時間範圍，以顯示該期間內已發生的事件。</span><span class="sxs-lookup"><span data-stu-id="188be-130">Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="188be-131">日期和時間以當地時間顯示。</span><span class="sxs-lookup"><span data-stu-id="188be-131">The date and time are presented in local time.</span></span> <span data-ttu-id="188be-132">預設會選取最後七天。</span><span class="sxs-lookup"><span data-stu-id="188be-132">The last seven days are selected by default.</span></span>
  
   2. <span data-ttu-id="188be-133">**活動**。</span><span class="sxs-lookup"><span data-stu-id="188be-133">**Activities**.</span></span> <span data-ttu-id="188be-134">選取要搜尋的活動。</span><span class="sxs-lookup"><span data-stu-id="188be-134">Select the activities to search for.</span></span> <span data-ttu-id="188be-135">使用 [搜尋] 方塊來搜尋要新增至清單的活動。</span><span class="sxs-lookup"><span data-stu-id="188be-135">Use the search box to search for activities to add to the list.</span></span> <span data-ttu-id="188be-136">如需已審核活動的部分清單，請參閱已 [審核的活動](search-the-audit-log-in-security-and-compliance.md#audited-activities)。</span><span class="sxs-lookup"><span data-stu-id="188be-136">For a partial list of audited activities, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="188be-137">將此方塊保留空白可傳回所有已審核活動的專案。</span><span class="sxs-lookup"><span data-stu-id="188be-137">Leave this box blank to return entries for all audited activities.</span></span>
  
   3. <span data-ttu-id="188be-138">**使用者**。</span><span class="sxs-lookup"><span data-stu-id="188be-138">**Users**.</span></span>  <span data-ttu-id="188be-139">在此方塊中按一下並開始輸入使用者名稱，以顯示的搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="188be-139">Click in this box and start typing the name of users to display search results for.</span></span> <span data-ttu-id="188be-140">您在此方塊中選取之使用者執行之選取活動的「審計記錄專案」會顯示在結果清單中。</span><span class="sxs-lookup"><span data-stu-id="188be-140">The audit log entries for the selected activities performed by the users you select in this box are displayed in the list of results.</span></span> <span data-ttu-id="188be-141">若要傳回貴組織中所有使用者 (及服務帳戶) 的項目，請將此方塊保留空白。</span><span class="sxs-lookup"><span data-stu-id="188be-141">Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
  
   4. <span data-ttu-id="188be-142">**檔、資料夾或網站**。</span><span class="sxs-lookup"><span data-stu-id="188be-142">**File, folder, or site**.</span></span> <span data-ttu-id="188be-143">輸入部分或所有檔案或資料夾名稱，以搜尋與包含指定關鍵字之資料夾檔案相關的活動。</span><span class="sxs-lookup"><span data-stu-id="188be-143">Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword.</span></span> <span data-ttu-id="188be-144">您也可以指定檔案或資料夾的 URL。</span><span class="sxs-lookup"><span data-stu-id="188be-144">You can also specify a URL of a file or folder.</span></span> <span data-ttu-id="188be-145">如果您使用的是檔案或資料夾的 URL，請確定輸入完整的 URL 路徑，或者，如果您輸入 URL 的一部分，請勿包含任何特殊字元或空格。</span><span class="sxs-lookup"><span data-stu-id="188be-145">If you use a URL of a file or folder, be sure the type the full URL path or if you type a portion of the URL, don't include any special characters or spaces.</span></span> <span data-ttu-id="188be-146">若要傳回貴組織中所有檔案和資料夾的項目，請將此方塊保留空白。</span><span class="sxs-lookup"><span data-stu-id="188be-146">Leave this box blank to return entries for all files and folders in your organization.</span></span>

4. <span data-ttu-id="188be-147">按一下 [ **搜尋** ] 以執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="188be-147">Click **Search** to run the search.</span></span>

<span data-ttu-id="188be-148">顯示 [正在執行審核記錄] 搜尋的新頁面。</span><span class="sxs-lookup"><span data-stu-id="188be-148">A new page is display that shows the audit log search is running.</span></span> <span data-ttu-id="188be-149">當搜尋完成時，就會在頁面上顯示審計記錄。</span><span class="sxs-lookup"><span data-stu-id="188be-149">When the search is completed, audit records are displayed on the page.</span></span> <span data-ttu-id="188be-150">按一下記錄以顯示具有詳細內容的飛出頁面。</span><span class="sxs-lookup"><span data-stu-id="188be-150">Click a record to display a flyout page with detailed properties.</span></span>

<span data-ttu-id="188be-151">如需詳細指示，請參閱 [在規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="188be-151">For more detailed instructions, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md).</span></span>
