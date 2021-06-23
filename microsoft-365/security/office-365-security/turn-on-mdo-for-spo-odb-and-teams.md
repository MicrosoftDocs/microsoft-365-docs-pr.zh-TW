---
title: 開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: 系統管理員可以瞭解如何開啟 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件，包括如何設定偵測到檔案的警示。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083089"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1e13d-103">開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="1e13d-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1e13d-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1e13d-104">**Applies to**</span></span>
- [<span data-ttu-id="1e13d-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="1e13d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1e13d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e13d-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1e13d-107">適用于 SharePoint、OneDrive 和 Microsoft Teams 的 Microsoft Defender Office 365，可防止您的組織意外共用惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="1e13d-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="1e13d-108">如需詳細資訊，請參閱[保管庫 SharePoint、OneDrive 和 Microsoft Teams 的附件](mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="1e13d-109">本文包含啟用及設定 SharePoint、OneDrive 及 Microsoft Teams 的保管庫附件的步驟。</span><span class="sxs-lookup"><span data-stu-id="1e13d-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e13d-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="1e13d-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1e13d-111">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="1e13d-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="1e13d-112">若要直接移至 [**保管庫附件**] 頁面，請開啟] <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="1e13d-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="1e13d-113">若要開啟 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件，您必須是 Microsoft 365 Defender 入口網站中「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1e13d-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="1e13d-114">如需詳細資訊，請參閱 [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="1e13d-115">若要使用 SharePoint 線上 PowerShell 以避免人員下載惡意檔案，您必須是[全域系統管理員](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator)的成員或 Azure AD 中[SharePoint 系統管理員](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator)角色。</span><span class="sxs-lookup"><span data-stu-id="1e13d-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="1e13d-116">確認已為您的組織啟用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="1e13d-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="1e13d-117">如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="1e13d-118">允許最多30分鐘的設定才會生效。</span><span class="sxs-lookup"><span data-stu-id="1e13d-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1e13d-119">步驟1：使用 Microsoft 365 Defender 入口網站開啟 SharePoint、OneDrive 及 Microsoft Teams 保管庫附件</span><span class="sxs-lookup"><span data-stu-id="1e13d-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="1e13d-120">在 Microsoft 365 Defender 入口網站中，移至 [**原則 & 規則** 威脅原則原則] \>  \> 區段 \> **保管庫附件**。</span><span class="sxs-lookup"><span data-stu-id="1e13d-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1e13d-121">在 [**保管庫附件**] 頁面上，按一下 [**通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="1e13d-122">在 [**全域設定**] 顯示的 [飛出] 中，移至 [SharePoint 中的 **檔、OneDrive 及 Microsoft Teams** ] 區段中的 [保護檔案]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="1e13d-123">移動 **SharePoint、OneDrive 及 Microsoft Teams** 切換至右開啟的 Office 365， ![ ](../../media/scc-toggle-on.png) 以開啟保管庫、SharePoint 和 OneDrive 的 Microsoft Teams 附件。</span><span class="sxs-lookup"><span data-stu-id="1e13d-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="1e13d-124">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1e13d-125">使用 Exchange Online PowerShell 開啟 SharePoint、OneDrive 和 Microsoft Teams 保管庫附件</span><span class="sxs-lookup"><span data-stu-id="1e13d-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="1e13d-126">如果您不想使用 PowerShell 開啟 SharePoint、OneDrive 及 Microsoft Teams 的保管庫附件，請連線[至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1e13d-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="1e13d-127">如需詳細的語法及參數資訊，請參閱 [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="1e13d-128">步驟2： (建議) 使用 SharePoint 線上 PowerShell 以避免使用者下載惡意檔</span><span class="sxs-lookup"><span data-stu-id="1e13d-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="1e13d-129">根據預設，使用者無法開啟、移動、複製或分享 <sup>\*</sup> 保管庫 SharePoint、OneDrive 及 Microsoft Teams 的附件所偵測到的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="1e13d-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="1e13d-130">不過，他們可以刪除及下載惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="1e13d-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="1e13d-131"><sup>\*</sup> 如果使用者移至 [ **管理存取**]，則 [ **共用** ] 選項仍可供使用。</span><span class="sxs-lookup"><span data-stu-id="1e13d-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="1e13d-132">若要防止使用者下載惡意檔案，請[連線至 SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1e13d-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="1e13d-133">**附註**：</span><span class="sxs-lookup"><span data-stu-id="1e13d-133">**Notes**:</span></span>

- <span data-ttu-id="1e13d-134">這項設定會影響使用者和系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1e13d-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="1e13d-135">人員仍可刪除惡意檔。</span><span class="sxs-lookup"><span data-stu-id="1e13d-135">People can still delete malicious files.</span></span>

<span data-ttu-id="1e13d-136">如需詳細的語法及參數資訊，請參閱 [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="1e13d-137">建議的步驟 3 () 使用 Microsoft 365 Defender 入口網站來建立偵測到的檔案的警示原則</span><span class="sxs-lookup"><span data-stu-id="1e13d-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="1e13d-138">您可以建立警示原則，當 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件時，通知您和其他系統管理員偵測惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="1e13d-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="1e13d-139">若要深入瞭解提醒，請參閱[在 Microsoft 365 Defender 入口網站中建立活動警示](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="1e13d-140">在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **警示原則**] 或 [開啟] <https://security.microsoft.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="1e13d-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="1e13d-141">在 [ **警示原則** ] 頁面上，按一下 [ **新增警示原則**]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="1e13d-142">**新的警示原則** 嚮導會在飛出時開啟。在 [**名稱您的提醒**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1e13d-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="1e13d-143">**名稱**：輸入唯一且具描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="1e13d-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="1e13d-144">例如，文件庫中的惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="1e13d-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="1e13d-145">**描述**：輸入選用的描述。</span><span class="sxs-lookup"><span data-stu-id="1e13d-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="1e13d-146">例如，在 SharePoint 線上、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，會通知系統管理員。</span><span class="sxs-lookup"><span data-stu-id="1e13d-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="1e13d-147">**嚴重性**：從下拉式清單中選取 [ **低**]、[ **中**] 或 [ **高** ]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="1e13d-148">**類別**：從下拉式清單中選取 [ **威脅管理** ]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="1e13d-149">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="1e13d-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1e13d-150">在 [ **建立警示設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1e13d-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="1e13d-151">**您想要提醒什麼？** section \> **活動會** \> 從下拉式清單中選取 [ **在檔案中偵測到惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="1e13d-152">**您要如何觸發警示？** 區段： **每次活動符合選取的規則時** 保留預設值。</span><span class="sxs-lookup"><span data-stu-id="1e13d-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="1e13d-153">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="1e13d-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1e13d-154">在 [ **設定您** 的收件者] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1e13d-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="1e13d-155">確認已選取 [ **傳送電子郵件通知** ]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="1e13d-156">在 [ **電子郵件** 收件者] 方塊中，選取一或多個全域管理員、安全性管理員或安全性讀者，當偵測到惡意檔案時，應該會收到通知。</span><span class="sxs-lookup"><span data-stu-id="1e13d-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="1e13d-157">**每日通知限制**：保留預設值 **沒有選取限制** 。</span><span class="sxs-lookup"><span data-stu-id="1e13d-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="1e13d-158">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="1e13d-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1e13d-159">在 [ **複查您的設定** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="1e13d-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="1e13d-160">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="1e13d-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="1e13d-161">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="1e13d-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="1e13d-162">在 [ **您想要立即開啟原則嗎？** ] 區段中，保留預設值 **[是]，並將其立即開啟** 為 [選取]。</span><span class="sxs-lookup"><span data-stu-id="1e13d-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="1e13d-163">完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="1e13d-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="1e13d-164">使用安全性 & 合規性 PowerShell 建立偵測到的檔案的警示原則</span><span class="sxs-lookup"><span data-stu-id="1e13d-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="1e13d-165">如果您想要使用 PowerShell 建立與上一節所述相同的警示原則，請連線 [至 Security & 合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) ，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1e13d-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="1e13d-166">**附注**：預設 _嚴重性_ 值是 Low。</span><span class="sxs-lookup"><span data-stu-id="1e13d-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="1e13d-167">若要指定「中」或「高」，請在命令中包含 _嚴重性_ 參數和值。</span><span class="sxs-lookup"><span data-stu-id="1e13d-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="1e13d-168">如需詳細的語法及參數資訊，請參閱 [New-ActivityAlert](/powershell/module/exchange/new-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1e13d-169">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="1e13d-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="1e13d-170">若要確認您是否已成功開啟 SharePoint、OneDrive 和 Microsoft Teams 的保管庫附件，請使用下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="1e13d-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="1e13d-171">在 Microsoft 365 Defender 入口網站中，移 **&** 至 [原則] [規則 \> **威脅原則** 原則] \> 區段中 \> **保管庫附件**]，選取 [**通用設定**]，然後確認 [開啟 Office 365 的 Defender] 的值 **SharePoint、OneDrive 和 Microsoft Teams** 設定。</span><span class="sxs-lookup"><span data-stu-id="1e13d-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="1e13d-172">在 Exchange Online PowerShell 中，執行下列命令來驗證屬性設定：</span><span class="sxs-lookup"><span data-stu-id="1e13d-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="1e13d-173">如需詳細的語法及參數資訊，請參閱 [AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="1e13d-174">若要確認您是否已成功封鎖人員下載惡意檔案、開啟 SharePoint 線上 PowerShell，並執行下列命令，以確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="1e13d-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="1e13d-175">如需詳細的語法及參數資訊，請參閱 [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="1e13d-176">若要確認您是否已成功設定偵測到的檔案的警示原則，請使用下列任何一項步驟：</span><span class="sxs-lookup"><span data-stu-id="1e13d-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="1e13d-177">在 Microsoft 365 Defender 入口網站中，移至 [**原則] & 規則** \> **警示原則** \> 選取警示原則，然後驗證設定。</span><span class="sxs-lookup"><span data-stu-id="1e13d-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="1e13d-178">在 Microsoft 365 Defender 入口網站 PowerShell 中， \<AlertPolicyName\> 以警示原則的名稱取代，執行下列命令，並確認屬性值：</span><span class="sxs-lookup"><span data-stu-id="1e13d-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="1e13d-179">如需詳細的語法及參數資訊，請參閱 [set-activityalert](/powershell/module/exchange/get-activityalert)。</span><span class="sxs-lookup"><span data-stu-id="1e13d-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="1e13d-180">使用 [[威脅防護狀態] 報告](view-email-security-reports.md#threat-protection-status-report)可查看 SharePoint、OneDrive 及 Microsoft Teams 中偵測到檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1e13d-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="1e13d-181">具體而言，您可以使用 **View 資料：內容 \> 惡意程式碼** 視圖。</span><span class="sxs-lookup"><span data-stu-id="1e13d-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
