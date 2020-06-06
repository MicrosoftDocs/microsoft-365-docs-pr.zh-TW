---
title: 開啟 Office 365 ATP-SharePoint、OneDrive、& 團隊
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
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
ms.openlocfilehash: 41cb5a5e5af6247331765bcfd0a78c50f89775ae
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588345"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="af71a-103">開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="af71a-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af71a-104">本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。</span><span class="sxs-lookup"><span data-stu-id="af71a-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="af71a-105">如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="af71a-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="af71a-106">[適用於 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](atp-for-spo-odb-and-teams.md) 可防止組織不小心共用惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="af71a-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="af71a-107">偵測到惡意檔案時，該檔案會遭到封鎖，因此在組織的安全性小組採取進一步動作之前，任何人都無法開啟、複製、移動或共用該檔案。</span><span class="sxs-lookup"><span data-stu-id="af71a-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="af71a-108">請參閱這篇文章以開啟適用於 SharePoint、OneDrive 和 Teams 的 ATP、設定通知以通知您偵測到的檔案，並採取後續步驟。</span><span class="sxs-lookup"><span data-stu-id="af71a-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="af71a-109">若要定義 (或編輯) ATP 原則，您必須獲派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="af71a-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="af71a-110">下表中有一些範例描述：</span><span class="sxs-lookup"><span data-stu-id="af71a-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="af71a-111">角色</span><span class="sxs-lookup"><span data-stu-id="af71a-111">Role</span></span>|<span data-ttu-id="af71a-112">指派位置/條件</span><span class="sxs-lookup"><span data-stu-id="af71a-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="af71a-113">全域管理員</span><span class="sxs-lookup"><span data-stu-id="af71a-113">global administrator</span></span>|<span data-ttu-id="af71a-114">簽署購買 Microsoft 365 的人員預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="af71a-114">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="af71a-115">（請參閱[關於 Microsoft 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)以深入瞭解。）</span><span class="sxs-lookup"><span data-stu-id="af71a-115">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="af71a-116">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="af71a-116">Security Administrator</span></span>|<span data-ttu-id="af71a-117">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="af71a-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="af71a-118">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="af71a-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="af71a-119">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="af71a-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="af71a-120">或</span><span class="sxs-lookup"><span data-stu-id="af71a-120">or</span></span> <br>  <span data-ttu-id="af71a-121">PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="af71a-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="af71a-122">開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="af71a-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="af71a-123">**開始此程式之前，請確定已為您的 Microsoft 365 環境開啟了審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="af71a-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="af71a-124">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="af71a-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="af71a-125">如需詳細資訊，請參閱[開啟或關閉稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="af71a-125">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="af71a-126">移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="af71a-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="af71a-127">在 [安全性 & 規範中心] 的左功能窗格中，選擇 [**威脅管理**] 底下的 [**原則** \> **安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="af71a-127">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![在 [安全性 & 規範中心] 中，選擇 [威脅管理 \> 原則]](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="af71a-129">選取 **[開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP]**。</span><span class="sxs-lookup"><span data-stu-id="af71a-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![開啟適用於 SharePoint Online、商務用 OneDrive 與 Microsoft Teams 的進階威脅防護](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="af71a-131">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="af71a-131">Click **Save**.</span></span>

5. <span data-ttu-id="af71a-132">檢閱 (並視需要編輯) 組織的 [[安全附件原則]](set-up-atp-safe-attachments-policies.md) 和 [[安全連結原則]](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="af71a-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="af71a-133">推薦以全域管理員或 SharePoint 線上管理員身分執行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet，並將_DisallowInfectedFileDownload_參數設定為*true*。</span><span class="sxs-lookup"><span data-stu-id="af71a-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="af71a-134">將參數設定為 *true* 可封鎖偵測到的檔案的所有動作 (刪除除外)。</span><span class="sxs-lookup"><span data-stu-id="af71a-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="af71a-135">使用者將無法開啟、移動、複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="af71a-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="af71a-136">將參數設定為 *false* 可封鎖所有動作 (刪除和下載除外)。</span><span class="sxs-lookup"><span data-stu-id="af71a-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="af71a-137">使用者可以選擇接受風險並下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="af71a-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="af71a-138">允許最多30分鐘的變更，以散佈至所有 Microsoft 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="af71a-138">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

8. <span data-ttu-id="af71a-139">(建議) 繼續為偵測到的檔案設定警示。</span><span class="sxs-lookup"><span data-stu-id="af71a-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="af71a-140">若要深入瞭解搭配 Microsoft 365 使用 PowerShell，請參閱使用[PowerShell 管理 Microsoft 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="af71a-140">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="af71a-141">若要深入了解當檔案被偵測為惡意檔案時的使用者體驗，請參閱[在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到惡意檔案時該怎麼做](https://support.microsoft.com/en-us/office/what-to-do-when-a-malicious-file-is-found-in-sharepoint-online-onedrive-or-microsoft-teams-01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="af71a-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/en-us/office/what-to-do-when-a-malicious-file-is-found-in-sharepoint-online-onedrive-or-microsoft-teams-01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="af71a-142">為偵測到的檔案設定警示</span><span class="sxs-lookup"><span data-stu-id="af71a-142">Set up alerts for detected files</span></span>

<span data-ttu-id="af71a-143">若要在 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的檔案被識別為惡意檔案時收到通知，您可以設定警示。</span><span class="sxs-lookup"><span data-stu-id="af71a-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="af71a-144">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**警示**] [ \> **管理提醒**]。</span><span class="sxs-lookup"><span data-stu-id="af71a-144">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="af71a-145">選擇 **[新警示原則]**。</span><span class="sxs-lookup"><span data-stu-id="af71a-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="af71a-146">指定警示的名稱。</span><span class="sxs-lookup"><span data-stu-id="af71a-146">Specify a name for the alert.</span></span> <span data-ttu-id="af71a-147">例如，您可以輸入「程式庫中的惡意檔案」。</span><span class="sxs-lookup"><span data-stu-id="af71a-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="af71a-148">輸入警示描述。</span><span class="sxs-lookup"><span data-stu-id="af71a-148">Type a description for the alert.</span></span> <span data-ttu-id="af71a-149">例如，當您在 SharePoint Online、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，您可以輸入「通知系統管理員」。</span><span class="sxs-lookup"><span data-stu-id="af71a-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="af71a-150">在 **[下列情況時傳送此通知...]** 區段中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="af71a-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="af71a-151">a.</span><span class="sxs-lookup"><span data-stu-id="af71a-151">a.</span></span> <span data-ttu-id="af71a-152">在 **[活動]** 清單中，選擇 **[已偵測到檔案中的惡意程式碼]**。</span><span class="sxs-lookup"><span data-stu-id="af71a-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="af71a-153">b.</span><span class="sxs-lookup"><span data-stu-id="af71a-153">b.</span></span> <span data-ttu-id="af71a-154">將 **[使用者]** 欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="af71a-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="af71a-155">在 **[傳送此通知到...]** 區段中，選取一或多位全域系統管理員、安全性系統管理員，或在偵測到惡意檔案時應收到通知的安全性讀者。</span><span class="sxs-lookup"><span data-stu-id="af71a-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="af71a-156">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="af71a-156">Click **Save**.</span></span>

<span data-ttu-id="af71a-157">若要深入瞭解提醒，請參閱[在安全性 & 規範中心建立活動警示](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="af71a-157">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="af71a-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="af71a-158">Next steps</span></span>

1. [<span data-ttu-id="af71a-159">檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊</span><span class="sxs-lookup"><span data-stu-id="af71a-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="af71a-160">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="af71a-160">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
