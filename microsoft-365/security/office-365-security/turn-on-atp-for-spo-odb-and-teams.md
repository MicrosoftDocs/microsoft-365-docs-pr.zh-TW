---
title: 開啟 Microsoft Defender for Office 365-SharePoint、OneDrive、& 團隊
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解如何開啟適用於 SharePoint、OneDrive 和 Teams 的 ATP，包括如何為偵測到的檔案設定警示。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44d487810156d5de5ae152e08040e8dccd2a4ee0
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682588"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="a56a2-103">開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="a56a2-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a56a2-104">適用于 SharePoint、OneDrive 和 Microsoft 團隊的 microsoft Defender for Office 365，可防止您的組織意外共用惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="a56a2-104">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="a56a2-105">如需詳細資訊，請參閱 [SharePoint、OneDrive 和 Microsoft 小組的 ATP](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="a56a2-106">本文包含啟用及設定 SharePoint、OneDrive 和 Microsoft 小組之 ATP 的步驟。</span><span class="sxs-lookup"><span data-stu-id="a56a2-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a56a2-107">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="a56a2-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a56a2-108">您要在 <https://protection.office.com> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="a56a2-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="a56a2-109">若要直接移至 [ **ATP 安全附件** ] 頁面，請開啟] <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="a56a2-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="a56a2-110">若要為 SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP，您必須是 [安全性 & 規範中心] 中「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a56a2-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a56a2-111">如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a56a2-112">若要使用 SharePoint 線上 PowerShell 以避免人員下載惡意檔案，您必須是 [全域系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 的成員或 Azure AD 中 [SharePoint 系統管理員](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) 角色。</span><span class="sxs-lookup"><span data-stu-id="a56a2-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="a56a2-113">確認已為您的組織啟用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="a56a2-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="a56a2-114">如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="a56a2-115">允許最多30分鐘的設定才會生效。</span><span class="sxs-lookup"><span data-stu-id="a56a2-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="a56a2-116">步驟1：使用安全性 & 合規性中心開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP</span><span class="sxs-lookup"><span data-stu-id="a56a2-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="a56a2-117">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="a56a2-118">在 [ **全域設定** ] 中顯示的 [飛出] 中，移至 [ **開啟 ATP] SharePoint、[OneDrive] 和 [Microsoft 小組** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="a56a2-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="a56a2-119">將切換移至右 ![ 切換開啟， ](../../media/scc-toggle-on.png) 以開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP。</span><span class="sxs-lookup"><span data-stu-id="a56a2-119">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="a56a2-120">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="a56a2-121">使用 Exchange Online PowerShell 開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP</span><span class="sxs-lookup"><span data-stu-id="a56a2-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="a56a2-122">如果您不想使用 PowerShell 開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP，請連線 [至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a56a2-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="a56a2-123">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="a56a2-124">步驟2： (建議) 使用 SharePoint 線上 PowerShell 以避免使用者下載惡意檔</span><span class="sxs-lookup"><span data-stu-id="a56a2-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="a56a2-125">根據預設，使用者無法開啟、移動、複製或共用 ATP 所偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="a56a2-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="a56a2-126">不過，他們可以刪除及下載惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="a56a2-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="a56a2-127">若要防止使用者下載惡意檔案，請 [連線至 SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a56a2-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="a56a2-128">**附註**：</span><span class="sxs-lookup"><span data-stu-id="a56a2-128">**Notes**:</span></span>

- <span data-ttu-id="a56a2-129">這項設定會影響使用者和系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a56a2-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="a56a2-130">人員仍可刪除惡意檔。</span><span class="sxs-lookup"><span data-stu-id="a56a2-130">People can still delete malicious files.</span></span>

<span data-ttu-id="a56a2-131">如需詳細的語法及參數資訊，請參閱 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="a56a2-132">建議的步驟 3 () 使用安全性 & 合規性中心建立偵測到的檔案的警示原則</span><span class="sxs-lookup"><span data-stu-id="a56a2-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="a56a2-133">您可以建立警示原則，當 SharePoint、OneDrive 和 Microsoft 小組偵測到惡意檔案時，通知您及其他系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a56a2-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="a56a2-134">若要深入瞭解提醒，請參閱 [在安全性 & 規範中心建立活動警示](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="a56a2-135">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，移至 [ **警示** \> **警示原則** ] 或 [開啟] <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="a56a2-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="a56a2-136">在 [ **警示原則** ] 頁面上，按一下 [ **新增警示原則**]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="a56a2-137">**新的警示原則** 嚮導會在飛出時開啟。在 [**名稱您的提醒**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a56a2-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="a56a2-138">**名稱**：輸入唯一且具描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="a56a2-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="a56a2-139">例如，文件庫中的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="a56a2-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="a56a2-140">**描述**：輸入選用的描述。</span><span class="sxs-lookup"><span data-stu-id="a56a2-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="a56a2-141">例如，在 SharePoint 線上、OneDrive 或 Microsoft 小組中偵測到惡意檔案時，會通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a56a2-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="a56a2-142">**嚴重性**：保持選取的預設值為 [ **低** ]，或選取 [ **中** ] 或 [ **高**]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="a56a2-143">**選取類別**： [選取 **威脅管理**]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="a56a2-144">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a56a2-145">在 [ **建立警示設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a56a2-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="a56a2-146">**您要在哪個專案上發出警示？：活動是**：選取 [檔案 **中偵測到惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="a56a2-147">**您要如何觸發警示？**： **每次活動符合選取的規則時** ，請保留預設值。</span><span class="sxs-lookup"><span data-stu-id="a56a2-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="a56a2-148">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a56a2-149">在 [ **設定您** 的收件者] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="a56a2-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="a56a2-150">**傳送電子郵件通知**：確認已選取此設定。</span><span class="sxs-lookup"><span data-stu-id="a56a2-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="a56a2-151">在 [ **電子郵件** 收件者] 方塊中，選取一或多個全域管理員、安全性管理員或安全性讀者，當偵測到惡意檔案時，應該會收到通知。</span><span class="sxs-lookup"><span data-stu-id="a56a2-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="a56a2-152">**每日通知限制**：保留預設值 **沒有選取限制** 。</span><span class="sxs-lookup"><span data-stu-id="a56a2-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="a56a2-153">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a56a2-154">在 [ **複查您的設定** ] 頁面上，複查設定，然後按一下任何區段中的 [ **編輯** ] 進行變更。</span><span class="sxs-lookup"><span data-stu-id="a56a2-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="a56a2-155">在 [ **您想要立即開啟原則嗎？** ] 區段中，保留預設值 **[是]，並將其立即開啟** 為 [選取]。</span><span class="sxs-lookup"><span data-stu-id="a56a2-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="a56a2-156">完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a56a2-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="a56a2-157">使用安全性 & 合規性 PowerShell 建立偵測到的檔案的警示原則</span><span class="sxs-lookup"><span data-stu-id="a56a2-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="a56a2-158">如果您想要使用 PowerShell 建立與上一節所述相同的警示原則，請連線 [至 Security & 合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) ，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a56a2-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="a56a2-159">**附注**：預設 _嚴重性_ 值是 Low。</span><span class="sxs-lookup"><span data-stu-id="a56a2-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="a56a2-160">若要指定「中」或「高」，請在命令中包含 _嚴重性_ 參數和值。</span><span class="sxs-lookup"><span data-stu-id="a56a2-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="a56a2-161">如需詳細的語法及參數資訊，請參閱 [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a56a2-162">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="a56a2-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="a56a2-163">若要確認您是否已成功為 SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP，請使用下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="a56a2-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="a56a2-164">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，移至 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，選取 [ **通用設定**]，然後確認 [ **開啟 SharePoint、OneDrive 和 Microsoft 小組的 ATP** ] 設定的值。</span><span class="sxs-lookup"><span data-stu-id="a56a2-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="a56a2-165">在 Exchange Online PowerShell 中，執行下列命令來驗證屬性設定：</span><span class="sxs-lookup"><span data-stu-id="a56a2-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="a56a2-166">如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="a56a2-167">若要確認您是否已成功封鎖人員下載惡意檔案、開啟 SharePoint 線上 PowerShell，並執行下列命令，以確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="a56a2-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="a56a2-168">如需詳細的語法及參數資訊，請參閱 [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="a56a2-169">若要確認您是否已成功設定偵測到的檔案的警示原則，請使用下列任何一項步驟：</span><span class="sxs-lookup"><span data-stu-id="a56a2-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="a56a2-170">在安全性 & 規範中心內，移至 **警示** \> **警示原則** \> 選取警示原則，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="a56a2-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="a56a2-171">在 [安全性 & 規範中心] PowerShell 中， \<AlertPolicyName\> 以警示原則的名稱取代，執行下列命令，並確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="a56a2-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="a56a2-172">如需詳細的語法及參數資訊，請參閱 [set-activityalert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="a56a2-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="a56a2-173">使用「 [威脅防護狀態」報告](view-email-security-reports.md#threat-protection-status-report) 可查看 SharePoint、OneDrive 和 Microsoft 小組中偵測到檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a56a2-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="a56a2-174">具體而言，您可以使用 **View 資料：內容 \> 惡意程式碼** 視圖。</span><span class="sxs-lookup"><span data-stu-id="a56a2-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
