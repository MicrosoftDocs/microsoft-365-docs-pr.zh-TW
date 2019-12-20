---
title: 開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 Office 365 ATP
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
ms.openlocfilehash: 49e29f838fa8fbcd4b0b6eea36e9bbe2d5547a7f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806736"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="71e97-103">開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="71e97-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71e97-104">本文適用於擁有 [Office 365 進階威脅防護](office-365-atp.md)的企業客戶。</span><span class="sxs-lookup"><span data-stu-id="71e97-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="71e97-105">如果您是家用版使用者且正在尋找 Outlook 中安全連結的相關資訊，請參閱[進階 Outlook.com 安全性](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="71e97-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="71e97-106">[適用於 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](atp-for-spo-odb-and-teams.md) 可防止組織不小心共用惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="71e97-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="71e97-107">偵測到惡意檔案時，該檔案會遭到封鎖，因此在組織的安全性小組採取進一步動作之前，任何人都無法開啟、複製、移動或共用該檔案。</span><span class="sxs-lookup"><span data-stu-id="71e97-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="71e97-108">請參閱這篇文章以開啟適用於 SharePoint、OneDrive 和 Teams 的 ATP、設定通知以通知您偵測到的檔案，並採取後續步驟。</span><span class="sxs-lookup"><span data-stu-id="71e97-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="71e97-109">若要定義 (或編輯) ATP 原則，您必須獲派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="71e97-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="71e97-110">下表中有一些範例描述：</span><span class="sxs-lookup"><span data-stu-id="71e97-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="71e97-111">角色</span><span class="sxs-lookup"><span data-stu-id="71e97-111">Role</span></span>|<span data-ttu-id="71e97-112">指派位置/條件</span><span class="sxs-lookup"><span data-stu-id="71e97-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="71e97-113">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="71e97-113">Office 365 Global Administrator</span></span>|<span data-ttu-id="71e97-114">註冊購買 Office 365 的人會預設為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="71e97-114">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="71e97-115">(請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以深入了解。)</span><span class="sxs-lookup"><span data-stu-id="71e97-115">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="71e97-116">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="71e97-116">Security Administrator</span></span>|<span data-ttu-id="71e97-117">Azure Active Directory 系統管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="71e97-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="71e97-118">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="71e97-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="71e97-119">Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="71e97-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="71e97-120">或</span><span class="sxs-lookup"><span data-stu-id="71e97-120">or</span></span> <br>  <span data-ttu-id="71e97-121">PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="71e97-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="71e97-122">開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="71e97-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="71e97-123">**開始此程序之前，請先確認您的 Office 365 環境已開啟稽核記錄**。</span><span class="sxs-lookup"><span data-stu-id="71e97-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="71e97-124">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="71e97-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="71e97-125">如需詳細資訊，請參閱[開啟或關閉 Office 365 稽核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="71e97-125">For more information, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="71e97-126">移至 [https://protection.office.com](https://protection.office.com) 然後以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="71e97-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="71e97-127">在 Office 365 安全性的 & 合規性中心，在左側的導覽窗格中，**威脅管理**] 下選擇 [**原則** \> **安全附件**。</span><span class="sxs-lookup"><span data-stu-id="71e97-127">In the Office 365 Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![在安全性 & 合規性中心中，選擇 [威脅管理，\>原則](../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="71e97-129">選取 **[開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP]**。</span><span class="sxs-lookup"><span data-stu-id="71e97-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![開啟適用於 SharePoint Online、商務用 OneDrive 與 Microsoft Teams 的進階威脅防護](../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="71e97-131">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="71e97-131">Click **Save**.</span></span>

5. <span data-ttu-id="71e97-132">檢閱 (並視需要編輯) 組織的 [[安全附件原則]](set-up-atp-safe-attachments-policies.md) 和 [[安全連結原則]](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="71e97-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="71e97-133">（建議使用）以全域管理員或 SharePoint Online 系統管理員，執行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** 指令程式搭配_DisallowInfectedFileDownload_參數設為*true*。</span><span class="sxs-lookup"><span data-stu-id="71e97-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="71e97-134">將參數設定為 *true* 可封鎖偵測到的檔案的所有動作 (刪除除外)。</span><span class="sxs-lookup"><span data-stu-id="71e97-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="71e97-135">使用者將無法開啟、移動、複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="71e97-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="71e97-136">將參數設定為 *false* 可封鎖所有動作 (刪除和下載除外)。</span><span class="sxs-lookup"><span data-stu-id="71e97-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="71e97-137">使用者可以選擇接受風險並下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="71e97-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="71e97-138">最多需要 30 分鐘的時間，變更才會散佈至所有 Office 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="71e97-138">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>

8. <span data-ttu-id="71e97-139">(建議) 繼續為偵測到的檔案設定警示。</span><span class="sxs-lookup"><span data-stu-id="71e97-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="71e97-140">若要深入了解如何在 Office 365 中使用 PowerShell，請參閱[使用 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="71e97-140">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="71e97-141">若要深入了解當檔案被偵測為惡意檔案時的使用者體驗，請參閱[在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到惡意檔案時該怎麼做](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="71e97-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="71e97-142">為偵測到的檔案設定警示</span><span class="sxs-lookup"><span data-stu-id="71e97-142">Set up alerts for detected files</span></span>

<span data-ttu-id="71e97-143">若要在 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的檔案被識別為惡意檔案時收到通知，您可以設定警示。</span><span class="sxs-lookup"><span data-stu-id="71e97-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="71e97-144">在[Office 365 安全性 & 合規性中心](https://protection.office.com)中，選擇 [**提醒** \> **管理警示**。</span><span class="sxs-lookup"><span data-stu-id="71e97-144">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="71e97-145">選擇 **[新警示原則]**。</span><span class="sxs-lookup"><span data-stu-id="71e97-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="71e97-146">指定警示的名稱。</span><span class="sxs-lookup"><span data-stu-id="71e97-146">Specify a name for the alert.</span></span> <span data-ttu-id="71e97-147">例如，您可以輸入「程式庫中的惡意檔案」。</span><span class="sxs-lookup"><span data-stu-id="71e97-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="71e97-148">輸入警示描述。</span><span class="sxs-lookup"><span data-stu-id="71e97-148">Type a description for the alert.</span></span> <span data-ttu-id="71e97-149">例如，當您在 SharePoint Online、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，您可以輸入「通知系統管理員」。</span><span class="sxs-lookup"><span data-stu-id="71e97-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="71e97-150">在 **[下列情況時傳送此通知...]** 區段中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="71e97-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="71e97-151">a.</span><span class="sxs-lookup"><span data-stu-id="71e97-151">a.</span></span> <span data-ttu-id="71e97-152">在 **[活動]** 清單中，選擇 **[已偵測到檔案中的惡意程式碼]**。</span><span class="sxs-lookup"><span data-stu-id="71e97-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="71e97-153">b.</span><span class="sxs-lookup"><span data-stu-id="71e97-153">b.</span></span> <span data-ttu-id="71e97-154">將 **[使用者]** 欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="71e97-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="71e97-155">在 **[傳送此通知到...]** 區段中，選取一或多位全域系統管理員、安全性系統管理員，或在偵測到惡意檔案時應收到通知的安全性讀者。</span><span class="sxs-lookup"><span data-stu-id="71e97-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="71e97-156">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="71e97-156">Click **Save**.</span></span>

<span data-ttu-id="71e97-157">若要深入了解提醒，請參閱[建立 Office 365 安全性 & 合規性中心中的活動警訊](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="71e97-157">To learn more about alerts, see [Create activity alerts in the Office 365 Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="71e97-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="71e97-158">Next steps</span></span>

1. [<span data-ttu-id="71e97-159">檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊</span><span class="sxs-lookup"><span data-stu-id="71e97-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="71e97-160">以 Office 365 系統管理員身分管理隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="71e97-160">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
