---
title: 開啟或關閉稽核記錄搜尋
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: 如何在安全性 & 規範中心開啟或關閉「審核記錄搜尋」功能，以啟用或停用系統管理員搜尋審核記錄的能力。
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976326"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="f7fbf-103">開啟或關閉稽核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="f7fbf-103">Turn audit log search on or off</span></span>

<span data-ttu-id="f7fbf-104">預設會針對 Microsoft 365 和 Office 365 企業組織開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="f7fbf-105">這包括具有 E3/G3 或 E5/G5 訂閱的組織。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="f7fbf-106">在規範中心開啟審核記錄搜尋時，您組織中的使用者和系統管理員活動會記錄在審核記錄中，並在90天內保留，而且會根據指派給使用者的授權，保留一年。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="f7fbf-107">不過，您的組織可能會有不想要記錄和保留審核記錄資料的原因。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="f7fbf-108">在這種情況下，全域管理員可能會決定在 Microsoft 365 中關閉審核。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7fbf-109">如果您在 Microsoft 365 中關閉「審計記錄搜尋」，您就無法使用 Office 365 管理活動 API 或 Azure Sentinel 來存取您組織的審計資料。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="f7fbf-110">依照本文中的步驟關閉審核記錄搜尋，表示當您使用安全性 & 合規性中心或在 Exchange Online PowerShell 中執行 **Search-UnifiedAuditLog** Cmdlet 來搜尋審核記錄時，不會傳回任何結果。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="f7fbf-111">這也表示無法透過 Office 365 管理活動 API 或 Azure Sentinel 使用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="f7fbf-112">開啟或關閉「審核記錄搜尋」之前</span><span class="sxs-lookup"><span data-stu-id="f7fbf-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="f7fbf-113">您必須在 Exchange Online 中指派「審核記錄」角色，以在 Microsoft 365 組織中開啟或關閉審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="f7fbf-114">根據預設，此角色會指派給 Exchange 系統管理中心的 [ **許可權** ] 頁面上的 [規範管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="f7fbf-115">Microsoft 365 中的全域系統管理員是 Exchange Online 中「組織管理」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f7fbf-116">在 Exchange Online 中，必須將許可權指派給使用者，以開啟或關閉審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="f7fbf-117">如果您在安全性 & 合規性中心的 [ **許可權** ] 頁面上指派「審核記錄」角色，則使用者將無法開啟或關閉審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="f7fbf-118">這是因為基準 Cmdlet 是 Exchange Online PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="f7fbf-119">如需搜尋審核記錄的逐步指示，請參閱在 [安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="f7fbf-120">如需 Microsoft 365 管理活動 API 的詳細資訊，請參閱 [開始使用 microsoft 365 管理 APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="f7fbf-121">若要確認已開啟「審計記錄搜尋」，您可以在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f7fbf-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="f7fbf-122">`True` _UnifiedAuditLogIngestionEnabled_ 屬性的值表示已開啟審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="f7fbf-123">開啟審計記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="f7fbf-123">Turn on audit log search</span></span>

<span data-ttu-id="f7fbf-124">如果您的組織未開啟「審計記錄搜尋」，您可以在「規範中心」或使用 Exchange Online PowerShell 中開啟它。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="f7fbf-125">在您開啟審核記錄搜尋後，可能需要數小時的時間，才能在搜尋審核記錄檔時傳回結果。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="f7fbf-126">使用規範中心來開啟審計記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="f7fbf-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="f7fbf-127">[移至 [規範中心](https://protection.office.com) ] 並登入。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="f7fbf-128">在 [規範中心] 中，移至 [**搜尋**  >  **審核記錄搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="f7fbf-129">如果您的組織未開啟「審計記錄搜尋」，就會顯示橫幅，告訴您必須開啟審計來記錄使用者和系統管理員活動。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="f7fbf-130">按一下 [ **開啟審計**]。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-130">Click **Turn on auditing**.</span></span>

    ![按一下 [開啟審計]](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="f7fbf-132">橫幅已更新，表示已準備好審核記錄，而且您可以在數小時內搜尋使用者和系統管理員活動。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="f7fbf-133">使用 PowerShell 開啟審計記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="f7fbf-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="f7fbf-134">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7fbf-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="f7fbf-135">執行下列 PowerShell 命令，在 Office 365 中開啟審計記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="f7fbf-136">隨即顯示一則訊息，指出可能需要長達60分鐘的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="f7fbf-137">關閉審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="f7fbf-137">Turn off audit log search</span></span>

<span data-ttu-id="f7fbf-138">您必須使用 Exchange Online PowerShell 關閉「審核記錄搜尋」。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="f7fbf-139">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7fbf-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="f7fbf-140">執行下列 PowerShell 命令，以關閉審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="f7fbf-141">經過一段時間後，請確認已停用審核記錄搜尋 (停用) 。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="f7fbf-142">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="f7fbf-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="f7fbf-143">在 Exchange Online PowerShell 中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f7fbf-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="f7fbf-144">`False` _UnifiedAuditLogIngestionEnabled_ 屬性的值表示已關閉審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="f7fbf-145">在 [ [規範中心](https://protection.office.com)] 中，移至 [ **搜尋** \> **審核記錄搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="f7fbf-146">顯示旗標，指出必須開啟審計，才能錄製使用者和系統管理員活動。</span><span class="sxs-lookup"><span data-stu-id="f7fbf-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
