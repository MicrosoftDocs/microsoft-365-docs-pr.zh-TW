---
title: 防範威脅
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 深入瞭解 Office 365 威脅防護，並設定如何針對您的組織使用它。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bdc7d619f3c48318572116fbc52647a0858ec5e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033887"
---
# <a name="protect-against-threats"></a><span data-ttu-id="8b1f2-103">防範威脅</span><span class="sxs-lookup"><span data-stu-id="8b1f2-103">Protect against threats</span></span>

<span data-ttu-id="8b1f2-104">Microsoft 365 包含各種威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="8b1f2-105">以下是一個快速入門手冊，您可以用來做為檢查清單，以確保為您的組織設定威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="8b1f2-106">如果您是 Office 365 中威脅防護功能的新功能，或您不確定開始的位置，請使用下列指南做為開始點。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b1f2-107">**每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="8b1f2-108">允許大約30分鐘的原則或變更以透過您的資料中心來運作。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b1f2-109">需求</span><span class="sxs-lookup"><span data-stu-id="8b1f2-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="8b1f2-110">訂閱</span><span class="sxs-lookup"><span data-stu-id="8b1f2-110">Subscriptions</span></span>

<span data-ttu-id="8b1f2-111">威脅防護功能包含在所有 Microsoft 365 訂閱中;不過，某些訂閱包含更多的高級功能。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="8b1f2-112">下表列出本文所含的保護功能及最低訂閱需求。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|||
|---|---|
|<span data-ttu-id="8b1f2-113">**保護類型**</span><span class="sxs-lookup"><span data-stu-id="8b1f2-113">**Protection type**</span></span>|<span data-ttu-id="8b1f2-114">**訂閱需求**</span><span class="sxs-lookup"><span data-stu-id="8b1f2-114">**Subscription requirement**</span></span>|
|<span data-ttu-id="8b1f2-115">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="8b1f2-115">Anti-malware protection</span></span>|<span data-ttu-id="8b1f2-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) （EOP）</span><span class="sxs-lookup"><span data-stu-id="8b1f2-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="8b1f2-117">保護電子郵件和 Office 檔中的惡意 URLs 和檔案</span><span class="sxs-lookup"><span data-stu-id="8b1f2-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="8b1f2-118">[Office 365 高級威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)（ATP）</span><span class="sxs-lookup"><span data-stu-id="8b1f2-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="8b1f2-119">防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="8b1f2-119">Anti-phishing protection</span></span>|[<span data-ttu-id="8b1f2-120">EOP</span><span class="sxs-lookup"><span data-stu-id="8b1f2-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="8b1f2-121">高級反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="8b1f2-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="8b1f2-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8b1f2-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="8b1f2-123">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="8b1f2-123">Anti-spam protection</span></span>|[<span data-ttu-id="8b1f2-124">EOP</span><span class="sxs-lookup"><span data-stu-id="8b1f2-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="8b1f2-125">自動清除零小時（電子郵件）</span><span class="sxs-lookup"><span data-stu-id="8b1f2-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="8b1f2-126">EOP</span><span class="sxs-lookup"><span data-stu-id="8b1f2-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="8b1f2-127">審核記錄（用於報告目的）</span><span class="sxs-lookup"><span data-stu-id="8b1f2-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="8b1f2-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b1f2-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="8b1f2-129">角色及權限</span><span class="sxs-lookup"><span data-stu-id="8b1f2-129">Roles and permissions</span></span>

<span data-ttu-id="8b1f2-130">您必須獲指派適當的角色，才能設定[安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)的原則。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="8b1f2-131">下表包括一些範例：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-131">The following table includes some examples:</span></span>

|<span data-ttu-id="8b1f2-132">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="8b1f2-132">Role or role group</span></span>|<span data-ttu-id="8b1f2-133">深入瞭解</span><span class="sxs-lookup"><span data-stu-id="8b1f2-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="8b1f2-134">全域管理員</span><span class="sxs-lookup"><span data-stu-id="8b1f2-134">global administrator</span></span>|[<span data-ttu-id="8b1f2-135">關於 Microsoft 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8b1f2-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="8b1f2-136">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="8b1f2-136">Security Administrator</span></span>|[<span data-ttu-id="8b1f2-137">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="8b1f2-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="8b1f2-138">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="8b1f2-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="8b1f2-139">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="8b1f2-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="8b1f2-140">和</span><span class="sxs-lookup"><span data-stu-id="8b1f2-140">and</span></span><br> [<span data-ttu-id="8b1f2-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b1f2-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

<span data-ttu-id="8b1f2-142">若要深入瞭解，請參閱[安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="8b1f2-143">第1部分-反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="8b1f2-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="8b1f2-144">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中提供[反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8b1f2-145">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **反惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="8b1f2-146">按兩下**預設**原則，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="8b1f2-147">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-147">Specify the following settings:</span></span>

    - <span data-ttu-id="8b1f2-148">在 [**惡意程式碼偵測回應**] 區段中，保留預設設定 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="8b1f2-149">在 [**一般附件類型篩選**] 區段中，選擇 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="8b1f2-150">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-150">Click **Save**.</span></span>

<span data-ttu-id="8b1f2-151">若要深入瞭解反惡意程式碼原則選項，請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="8b1f2-152">第2部分-防護惡意 URLs 和檔案</span><span class="sxs-lookup"><span data-stu-id="8b1f2-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="8b1f2-153">在包含[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) （atp）的訂閱中，可使用從惡意 URLs 和檔案進行的時刻防護，並透過[atp 安全附件](atp-safe-attachments.md)和[atp 安全連結](atp-safe-links.md)原則進行設定。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="8b1f2-154">ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="8b1f2-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="8b1f2-155">若要設定[Atp 安全附件](atp-safe-attachments.md)，您必須至少定義一個 Atp 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="8b1f2-156">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="8b1f2-157">選取 [為**SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP**] 選項。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="8b1f2-158">在 [**保護電子郵件附件**] 區段中，按一下加號**+**（）。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="8b1f2-159">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-159">Specify the following settings:</span></span>

   - <span data-ttu-id="8b1f2-160">在 [**名稱**] 方塊中`Block malware`，輸入。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="8b1f2-161">在 [回應] 區段中，選擇 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="8b1f2-162">在 [重新**導向附件**] 區段中，選取 [**啟用重新導向**] 選項，然後指定組織之安全性管理員或操作員的電子郵件地址，以查看偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="8b1f2-163">在 [套用**于**] 區段中，選擇 **[收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="8b1f2-164">然後，選取您的網域，選擇 [**新增**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="8b1f2-165">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-165">Click **Save**.</span></span>

6. <span data-ttu-id="8b1f2-166">（**建議的其他步驟**）以全域管理員或 SharePoint Online 管理員的身分，針對您的 Microsoft 365 環境執行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet 並將**DisallowInfectedFileDownload**參數設定為*true* 。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="8b1f2-167">（這樣可防止使用者開啟、移動、複製或共用偵測為惡意的檔案。）</span><span class="sxs-lookup"><span data-stu-id="8b1f2-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="8b1f2-168">若要深入瞭解，請參閱[設定 office 365 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md)，並[為 SharePoint、OneDrive 和 Microsoft 團隊開啟 office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="8b1f2-169">ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="8b1f2-169">ATP Safe Links policies</span></span>

<span data-ttu-id="8b1f2-170">若要設定[ATP 安全連結](atp-safe-links.md)，請複查和編輯您的預設原則，並新增特定使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="8b1f2-171">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="8b1f2-172">連按兩下**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="8b1f2-173">在 [**使用安全連結**] 區段中，選取 [ **Microsoft 365 應用程式適用于企業，Office iOS 和 Android**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="8b1f2-174">在 [套用**至特定**收件者的原則] 區段中，按一下**+** 加號（）。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="8b1f2-175">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-175">Specify the following settings:</span></span>

   - <span data-ttu-id="8b1f2-176">在 [**名稱**] 方塊中，輸入名稱，例如`Safe Links`。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="8b1f2-177">在 [選取動作]\*\*\*\* 區段中，選擇 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="8b1f2-178">選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-178">Select these options:</span></span>

     - <span data-ttu-id="8b1f2-179">**使用安全附件掃描可下載的內容**</span><span class="sxs-lookup"><span data-stu-id="8b1f2-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="8b1f2-180">**對組織內傳送的電子郵件套用安全連結**</span><span class="sxs-lookup"><span data-stu-id="8b1f2-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="8b1f2-181">**不要讓使用者點擊至原始 URL 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="8b1f2-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="8b1f2-182">在 [套用**于**] 區段中，選擇 **[收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="8b1f2-183">然後，選取您的網域，選擇 [**新增**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="8b1f2-184">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-184">Click **Save**.</span></span>

<span data-ttu-id="8b1f2-185">若要深入了解，請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="8b1f2-186">第3部分-反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="8b1f2-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="8b1f2-187">[防網路釣魚]</span><span class="sxs-lookup"><span data-stu-id="8b1f2-187">[Anti-phishing]</span></span>

<span data-ttu-id="8b1f2-188">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8b1f2-189">您可以使用[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中的高級反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="8b1f2-190">下列程式說明如何設定 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="8b1f2-191">步驟類似于設定反網路釣魚原則（沒有 ATP）。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="8b1f2-192">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="8b1f2-193">按一下 [**預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="8b1f2-194">在 [**類比**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8b1f2-195">在 [**新增要保護的使用者**] 索引標籤上，開啟 [保護]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="8b1f2-196">然後新增使用者，例如貴組織的董事會成員、CEO、CFO 和其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="8b1f2-197">（您可以輸入個別的電子郵件地址，或按一下以顯示清單）。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="8b1f2-198">在 [**新增要保護的網域**] 索引標籤上，開啟 [**自動包含我擁有的網域**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="8b1f2-199">如果您有自訂網域，請同時新增這些網域。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="8b1f2-200">在 [**動作**] 索引標籤上，選取 [隔離**使用者**和模擬的**網域**] 選項的 **[郵件**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="8b1f2-201">此外，開啟類比安全提示。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="8b1f2-202">在 [**信箱智慧**] 索引標籤上，確認已開啟信箱智慧。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="8b1f2-203">此外，開啟信箱智慧型類比保護。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="8b1f2-204">在 [**如果模擬使用者傳送電子郵件**] 清單中，選擇 [**隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8b1f2-205">在 [**新增信任的寄件者和網域**] 索引標籤上，指定您要新增的任何信任寄件者或網域。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="8b1f2-206">在 [**複查您的設定**] 索引標籤上，在您檢查好設定後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="8b1f2-207">在 [**哄騙**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8b1f2-208">在 [**哄騙篩選設定**] 索引標籤上，確定已開啟反欺詐保護。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="8b1f2-209">在 [**動作**] 索引標籤上，選擇 [**隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="8b1f2-210">在 [**複查您的設定**] 索引標籤上，在您檢查好設定後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="8b1f2-211">（如果您未進行任何變更，請按一下 [**取消**]）。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="8b1f2-212">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-212">Close the default policy settings page.</span></span>

<span data-ttu-id="8b1f2-213">若要深入瞭解您的反網路釣魚原則選項，請參閱[在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="8b1f2-214">第4部分-反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="8b1f2-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="8b1f2-215">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中取得[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="8b1f2-216">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > ]**反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="8b1f2-217">在 [**自訂**] 索引標籤上，開啟 [**自訂設定**]。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="8b1f2-218">展開 [**預設垃圾郵件篩選原則**]，按一下 [**編輯原則**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="8b1f2-219">在 [**垃圾郵件及大量動作**] 區段中，將臨界值設為5或6。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="8b1f2-220">在 [**允許清單**] 區段中，複查（必要時編輯）您允許的寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="8b1f2-221">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-221">Click **Save**.</span></span>

<span data-ttu-id="8b1f2-222">若要深入瞭解您的反垃圾郵件原則選項，請參閱[設定 Office 365 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="8b1f2-223">第5部分-要設定的其他設定</span><span class="sxs-lookup"><span data-stu-id="8b1f2-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="8b1f2-224">除了設定惡意程式碼保護、惡意 URLs 和檔案、網路釣魚和垃圾郵件之外，我們建議您設定零小時自動清除和審核記錄設定。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="8b1f2-225">電子郵件自動清除零小時</span><span class="sxs-lookup"><span data-stu-id="8b1f2-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="8b1f2-226">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中，可以使用[零小時自動清除](zero-hour-auto-purge.md)（ZAP）。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="8b1f2-227">此保護功能預設為開啟狀態;不過，保護生效的情況必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="8b1f2-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="8b1f2-228">垃圾[訊息原則](anti-spam-protection.md)中的垃圾郵件動作會設定為**將郵件移至 [垃圾郵件] 資料夾**。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="8b1f2-229">使用者保留其預設的[垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但未關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="8b1f2-230">若要深入瞭解，請參閱[零時自動清除-防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="8b1f2-231">報告和調查的審計記錄</span><span class="sxs-lookup"><span data-stu-id="8b1f2-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="8b1f2-232">在包含[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的訂閱中可使用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="8b1f2-233">為了在威脅防護報告中查看資料（如[安全性儀表板](security-dashboard.md)、[電子郵件安全性報告](view-email-security-reports.md)和[Explorer](threat-explorer.md)），必須為您的組織開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="8b1f2-234">若要深入瞭解，請參閱[開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="8b1f2-235">安裝後的工作</span><span class="sxs-lookup"><span data-stu-id="8b1f2-235">Post-setup tasks</span></span>

<span data-ttu-id="8b1f2-236">設定威脅防護功能之後，請務必監視這些功能的運作方式、視需要複查及修改原則，以及觀賞新功能和服務更新。</span><span class="sxs-lookup"><span data-stu-id="8b1f2-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|||
|---|---|
|<span data-ttu-id="8b1f2-237">**處理方式**</span><span class="sxs-lookup"><span data-stu-id="8b1f2-237">**What to do**</span></span>|<span data-ttu-id="8b1f2-238">**可深入了解的資源**</span><span class="sxs-lookup"><span data-stu-id="8b1f2-238">**Resources to learn more**</span></span>|
|<span data-ttu-id="8b1f2-239">查看您的組織如何使用威脅防護功能，以查看報告</span><span class="sxs-lookup"><span data-stu-id="8b1f2-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="8b1f2-240">安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="8b1f2-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="8b1f2-241">電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="8b1f2-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="8b1f2-242">Office 365 ATP 報告</span><span class="sxs-lookup"><span data-stu-id="8b1f2-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="8b1f2-243">威脅總管</span><span class="sxs-lookup"><span data-stu-id="8b1f2-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="8b1f2-244">視需要定期複查和修正威脅防護原則</span><span class="sxs-lookup"><span data-stu-id="8b1f2-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="8b1f2-245">安全分數</span><span class="sxs-lookup"><span data-stu-id="8b1f2-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="8b1f2-246">智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="8b1f2-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="8b1f2-247">Microsoft 365 威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="8b1f2-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="8b1f2-248">監視新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="8b1f2-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="8b1f2-249">標準及目標發行選項</span><span class="sxs-lookup"><span data-stu-id="8b1f2-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="8b1f2-250">訊息中心</span><span class="sxs-lookup"><span data-stu-id="8b1f2-250">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="8b1f2-251">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="8b1f2-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="8b1f2-252">服務說明</span><span class="sxs-lookup"><span data-stu-id="8b1f2-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
