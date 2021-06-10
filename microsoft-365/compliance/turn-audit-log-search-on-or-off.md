---
title: 開啟或關閉稽核
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
description: 如何在「Microsoft 365 規範中心」中開啟或關閉「審核記錄搜尋」功能，以啟用或停用系統管理員搜尋審核記錄的能力。
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706659"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="3c9d9-103">開啟或關閉稽核</span><span class="sxs-lookup"><span data-stu-id="3c9d9-103">Turn auditing on or off</span></span>

<span data-ttu-id="3c9d9-104">使用 Microsoft 365 和 Office 365 企業版的組織，預設會開啟 [稽核記錄]。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="3c9d9-105">其中包括使用 E3/G3 或 E5/G5 訂閱的組織。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="3c9d9-106">開啟規範中心的審計時，會將組織中的使用者和系統管理員活動記錄在審核記錄中，並在90天內保留，視指派給使用者的授權而定到一年。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="3c9d9-107">不過，您的組織可能會有不想要記錄和保留審核記錄資料的原因。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="3c9d9-108">在這種情況下，全域管理員可能會決定在 Microsoft 365 中關閉審核。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c9d9-109">如果您在 Microsoft 365 中關閉審核，您就無法使用 Office 365 管理活動 API 或 Azure Sentinel 來存取組織的審計資料。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="3c9d9-110">遵循本文中的步驟關閉審計，表示當您使用安全性 & 合規性中心或在 Exchange Online PowerShell 中執行 **Search-UnifiedAuditLog** Cmdlet 來搜尋審核記錄時，將不會傳回任何結果。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="3c9d9-111">這也表示無法透過 Office 365 管理活動 API 或 Azure Sentinel 使用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="3c9d9-112">開啟或關閉審計之前</span><span class="sxs-lookup"><span data-stu-id="3c9d9-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="3c9d9-113">您必須在 Exchange Online 中指派「審計記錄」角色，才能在 Microsoft 365 組織中開啟或關閉審計。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="3c9d9-114">根據預設，此角色會指派給 Exchange 系統管理中心的 [**許可權**] 頁面上的 [規範管理] 和 [組織管理] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="3c9d9-115">Microsoft 365 中的全域系統管理員是 Exchange Online 中的「組織管理」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="3c9d9-116">在 Exchange Online 開啟或關閉審核時，必須將許可權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="3c9d9-117">如果您在安全性 & 合規性中心的 [ **許可權** ] 頁面上指派「審核記錄」角色，則使用者將無法開啟或關閉審核功能。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="3c9d9-118">這是因為基準 Cmdlet 是 Exchange Online PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 

- <span data-ttu-id="3c9d9-119">如需搜尋審核記錄的逐步指示，請參閱在 [安全性 & 規範中心搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="3c9d9-120">如需 Microsoft 365 管理活動 API 的詳細資訊，請參閱[開始使用 Microsoft 365 管理 APIs](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="3c9d9-121">若要確認已開啟審核，您可以在 Exchange Online 中執行下列命令 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3c9d9-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="3c9d9-122">`True` _UnifiedAuditLogIngestionEnabled_ 屬性的值表示已開啟審計。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="3c9d9-123">開啟審計</span><span class="sxs-lookup"><span data-stu-id="3c9d9-123">Turn on auditing</span></span>

<span data-ttu-id="3c9d9-124">如果您的組織未開啟審核，您可以在「規範中心」或使用 Exchange Online PowerShell 來開啟審核。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="3c9d9-125">在您開啟審核後，可能需要數小時的時間，才能在搜尋審核記錄檔時傳回結果。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="3c9d9-126">使用規範中心來開啟審計</span><span class="sxs-lookup"><span data-stu-id="3c9d9-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="3c9d9-127">移至 <https://compliance.microsoft.com> 並登入。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="3c9d9-128">在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [**審計**]。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="3c9d9-129">如果您的組織未開啟審核，就會顯示橫幅，提示您開始錄製使用者和系統管理員活動。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![在審核頁面上的橫幅](../media/AuditingBanner.png)

3. <span data-ttu-id="3c9d9-131">按一下 [ **開始錄製使用者和系統管理員] 活動** 橫幅。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="3c9d9-132">可能需要長達60分鐘，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="3c9d9-133">使用 PowerShell 開啟審計</span><span class="sxs-lookup"><span data-stu-id="3c9d9-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="3c9d9-134">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c9d9-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="3c9d9-135">執行下列 PowerShell 命令，在 Office 365 中開啟審計。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="3c9d9-136">隨即顯示一則訊息，指出可能需要長達60分鐘的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="3c9d9-137">關閉審計</span><span class="sxs-lookup"><span data-stu-id="3c9d9-137">Turn off auditing</span></span>

<span data-ttu-id="3c9d9-138">您必須使用 Exchange Online PowerShell 關閉審核。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="3c9d9-139">連線到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c9d9-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="3c9d9-140">執行下列 PowerShell 命令以關閉審計。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="3c9d9-141">經過一段時間後，請確認已停用 (停用) 的審計功能。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="3c9d9-142">執行這項作業的方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="3c9d9-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="3c9d9-143">在 Exchange Online PowerShell 中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3c9d9-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="3c9d9-144">`False` _UnifiedAuditLogIngestionEnabled_ 屬性的值表示已關閉的審計功能。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="3c9d9-145">移至 Microsoft 365 規範中心的「**審計**」頁面。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="3c9d9-146">如果您的組織未開啟審核，就會顯示橫幅，提示您開始錄製使用者和系統管理員活動。</span><span class="sxs-lookup"><span data-stu-id="3c9d9-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
