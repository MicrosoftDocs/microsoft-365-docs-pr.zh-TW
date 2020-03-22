---
title: 保護 Office 365 中的威脅
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 請使用本文做為指南，以立即設定威脅防護功能。
ms.openlocfilehash: da920083b521e905633473efbabc5930ad7a6770
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895308"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="19310-103">保護 Office 365 中的威脅</span><span class="sxs-lookup"><span data-stu-id="19310-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="19310-104">Office 365 包含各種威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="19310-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="19310-105">以下是一個快速入門手冊，您可以用來做為檢查清單，以確保為您的組織設定威脅防護功能。</span><span class="sxs-lookup"><span data-stu-id="19310-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="19310-106">如果您是 Office 365 中威脅防護功能的新功能，或您不確定開始的位置，請使用下列指南做為開始點。</span><span class="sxs-lookup"><span data-stu-id="19310-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19310-107">**每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。</span><span class="sxs-lookup"><span data-stu-id="19310-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="19310-108">允許大約30分鐘的原則或變更以透過您的資料中心來運作。</span><span class="sxs-lookup"><span data-stu-id="19310-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="19310-109">需求</span><span class="sxs-lookup"><span data-stu-id="19310-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="19310-110">訂閱</span><span class="sxs-lookup"><span data-stu-id="19310-110">Subscriptions</span></span>

<span data-ttu-id="19310-111">威脅防護功能包含在所有 Office 365 訂閱中;不過，某些訂閱包含更多的高級功能。</span><span class="sxs-lookup"><span data-stu-id="19310-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="19310-112">下表列出本文所含的保護功能及最低訂閱需求。</span><span class="sxs-lookup"><span data-stu-id="19310-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|<span data-ttu-id="19310-113">保護類型</span><span class="sxs-lookup"><span data-stu-id="19310-113">Protection type</span></span>|<span data-ttu-id="19310-114">訂閱需求</span><span class="sxs-lookup"><span data-stu-id="19310-114">Subscription requirement</span></span>|
|---------|---------|
|<span data-ttu-id="19310-115">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="19310-115">Anti-malware protection</span></span>|<span data-ttu-id="19310-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) （EOP）</span><span class="sxs-lookup"><span data-stu-id="19310-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="19310-117">保護電子郵件和 Office 檔中的惡意 URLs 和檔案</span><span class="sxs-lookup"><span data-stu-id="19310-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="19310-118">[Office 365 高級威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)（ATP）</span><span class="sxs-lookup"><span data-stu-id="19310-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="19310-119">反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="19310-119">Anti-phishing protection</span></span>|[<span data-ttu-id="19310-120">EOP</span><span class="sxs-lookup"><span data-stu-id="19310-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="19310-121">高級反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="19310-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="19310-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="19310-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="19310-123">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="19310-123">Anti-spam protection</span></span>|[<span data-ttu-id="19310-124">EOP</span><span class="sxs-lookup"><span data-stu-id="19310-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="19310-125">自動清除零小時（電子郵件）</span><span class="sxs-lookup"><span data-stu-id="19310-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="19310-126">EOP</span><span class="sxs-lookup"><span data-stu-id="19310-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="19310-127">審核記錄（用於報告目的）</span><span class="sxs-lookup"><span data-stu-id="19310-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="19310-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="19310-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="19310-129">角色及權限</span><span class="sxs-lookup"><span data-stu-id="19310-129">Roles and permissions</span></span>

<span data-ttu-id="19310-130">您必須獲指派適當的角色，才能設定[安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)的原則。</span><span class="sxs-lookup"><span data-stu-id="19310-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="19310-131">下表包括一些範例：</span><span class="sxs-lookup"><span data-stu-id="19310-131">The following table includes some examples:</span></span>

|<span data-ttu-id="19310-132">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="19310-132">Role or role group</span></span>|<span data-ttu-id="19310-133">深入瞭解</span><span class="sxs-lookup"><span data-stu-id="19310-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="19310-134">Office 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="19310-134">Office 365 Global Administrator</span></span>|[<span data-ttu-id="19310-135">關於 Office 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="19310-135">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="19310-136">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="19310-136">Security Administrator</span></span>|[<span data-ttu-id="19310-137">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="19310-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="19310-138">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="19310-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="19310-139">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="19310-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="19310-140">和</span><span class="sxs-lookup"><span data-stu-id="19310-140">and</span></span><br> [<span data-ttu-id="19310-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="19310-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|

<span data-ttu-id="19310-142">若要深入瞭解，請參閱[Office 365 安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-142">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="19310-143">第1部分-反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="19310-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="19310-144">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中提供[反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="19310-145">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **反惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="19310-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="19310-146">按兩下**預設**原則，然後選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="19310-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="19310-147">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="19310-147">Specify the following settings:</span></span>

    - <span data-ttu-id="19310-148">在 [**惡意程式碼偵測回應**] 區段中，保留預設設定 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="19310-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="19310-149">在 [**一般附件類型篩選**] 區段中，選擇 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="19310-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="19310-150">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="19310-150">Click **Save**.</span></span>

<span data-ttu-id="19310-151">若要深入瞭解反惡意程式碼原則選項，請參閱[設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="19310-152">第2部分-防護惡意 URLs 和檔案</span><span class="sxs-lookup"><span data-stu-id="19310-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="19310-153">在包含[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) （atp）的訂閱中，可使用從惡意 URLs 和檔案進行的時刻防護，並透過[atp 安全附件](atp-safe-attachments.md)和[atp 安全連結](atp-safe-links.md)原則進行設定。</span><span class="sxs-lookup"><span data-stu-id="19310-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="19310-154">ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="19310-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="19310-155">若要設定[Atp 安全附件](atp-safe-attachments.md)，您必須至少定義一個 Atp 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="19310-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="19310-156">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="19310-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="19310-157">選取 [為**SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP**] 選項。</span><span class="sxs-lookup"><span data-stu-id="19310-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="19310-158">在 [**保護電子郵件附件**] 區段中，按一下加號**+**（）。</span><span class="sxs-lookup"><span data-stu-id="19310-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="19310-159">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="19310-159">Specify the following settings:</span></span>

   - <span data-ttu-id="19310-160">在 [**名稱**] 方塊中`Block malware`，輸入。</span><span class="sxs-lookup"><span data-stu-id="19310-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="19310-161">在 [回應] 區段中，選擇 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="19310-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="19310-162">在 [重新**導向附件**] 區段中，選取 [**啟用重新導向**] 選項，然後指定組織之安全性管理員或操作員的電子郵件地址，以查看偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="19310-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="19310-163">在 [套用**于**] 區段中，選擇 **[收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="19310-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="19310-164">然後，選取您的網域，選擇 [**新增**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="19310-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="19310-165">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="19310-165">Click **Save**.</span></span>

6. <span data-ttu-id="19310-166">（**建議的其他步驟**）以全域管理員或 SharePoint Online 管理員的身分，針對您的 Office 365 環境執行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet 並將**DisallowInfectedFileDownload**參數設定為*true* 。</span><span class="sxs-lookup"><span data-stu-id="19310-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="19310-167">（這樣可防止使用者開啟、移動、複製或共用偵測為惡意的檔案。）</span><span class="sxs-lookup"><span data-stu-id="19310-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="19310-168">若要深入瞭解，請參閱[設定 office 365 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md)，並[為 SharePoint、OneDrive 和 Microsoft 團隊開啟 office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="19310-169">ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="19310-169">ATP Safe Links policies</span></span>

<span data-ttu-id="19310-170">若要設定[ATP 安全連結](atp-safe-links.md)，請複查和編輯您的預設原則，並新增特定使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="19310-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="19310-171">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="19310-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="19310-172">連按兩下**預設**原則。</span><span class="sxs-lookup"><span data-stu-id="19310-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="19310-173">在 [**使用安全連結**] 區段中，選取 [ **office 365 ProPlus]、[iOS 和 Android 的 office**] 選項，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="19310-173">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="19310-174">在 [套用**至特定**收件者的原則] 區段中，按一下**+** 加號（）。</span><span class="sxs-lookup"><span data-stu-id="19310-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="19310-175">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="19310-175">Specify the following settings:</span></span>

   - <span data-ttu-id="19310-176">在 [**名稱**] 方塊中，輸入名稱，例如`Safe Links`。</span><span class="sxs-lookup"><span data-stu-id="19310-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="19310-177">在 [選取動作]\*\*\*\* 區段中，選擇 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="19310-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="19310-178">選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="19310-178">Select these options:</span></span>

     - <span data-ttu-id="19310-179">**使用安全附件掃描可下載的內容**</span><span class="sxs-lookup"><span data-stu-id="19310-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="19310-180">**對組織內傳送的電子郵件套用安全連結**</span><span class="sxs-lookup"><span data-stu-id="19310-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="19310-181">**不要讓使用者點擊至原始 URL 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="19310-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="19310-182">在 [套用**于**] 區段中，選擇 **[收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="19310-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="19310-183">然後，選取您的網域，選擇 [**新增**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="19310-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="19310-184">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="19310-184">Click **Save**.</span></span>

<span data-ttu-id="19310-185">若要深入了解，請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="19310-186">第3部分-反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="19310-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="19310-187">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-187">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="19310-188">您可以使用[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中的高級反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="19310-188">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="19310-189">下列程式說明如何設定 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="19310-189">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="19310-190">步驟類似于設定反網路釣魚原則（沒有 ATP）。</span><span class="sxs-lookup"><span data-stu-id="19310-190">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="19310-191">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="19310-191">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="19310-192">按一下 [**預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="19310-192">Click **Default policy**.</span></span>

3. <span data-ttu-id="19310-193">在 [**類比**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="19310-193">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="19310-194">在 [**新增要保護的使用者**] 索引標籤上，開啟 [保護]。</span><span class="sxs-lookup"><span data-stu-id="19310-194">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="19310-195">然後新增使用者，例如貴組織的董事會成員、CEO、CFO 和其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="19310-195">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="19310-196">（您可以輸入個別的電子郵件地址，或按一下以顯示清單）。</span><span class="sxs-lookup"><span data-stu-id="19310-196">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="19310-197">在 [**新增要保護的網域**] 索引標籤上，開啟 [**自動包含我擁有的網域**]。</span><span class="sxs-lookup"><span data-stu-id="19310-197">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="19310-198">如果您有自訂網域，請同時新增這些網域。</span><span class="sxs-lookup"><span data-stu-id="19310-198">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="19310-199">在 [**動作**] 索引標籤上，選取 [隔離**使用者**和模擬的**網域**] 選項的 **[郵件**]。</span><span class="sxs-lookup"><span data-stu-id="19310-199">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="19310-200">此外，開啟類比安全提示。</span><span class="sxs-lookup"><span data-stu-id="19310-200">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="19310-201">在 [**信箱智慧**] 索引標籤上，確認已開啟信箱智慧。</span><span class="sxs-lookup"><span data-stu-id="19310-201">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="19310-202">此外，開啟信箱智慧型類比保護。</span><span class="sxs-lookup"><span data-stu-id="19310-202">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="19310-203">在 [**如果模擬使用者傳送電子郵件**] 清單中，選擇 [**隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="19310-203">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="19310-204">在 [**新增信任的寄件者和網域**] 索引標籤上，指定您要新增的任何信任寄件者或網域。</span><span class="sxs-lookup"><span data-stu-id="19310-204">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="19310-205">在 [**複查您的設定**] 索引標籤上，在您檢查好設定後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="19310-205">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="19310-206">在 [**哄騙**] 區段中，按一下 [**編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="19310-206">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="19310-207">在 [**哄騙篩選設定**] 索引標籤上，確定已開啟反欺詐保護。</span><span class="sxs-lookup"><span data-stu-id="19310-207">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="19310-208">在 [**動作**] 索引標籤上，選擇 [**隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="19310-208">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="19310-209">在 [**複查您的設定**] 索引標籤上，在您檢查好設定後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="19310-209">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="19310-210">（如果您未進行任何變更，請按一下 [**取消**]）。</span><span class="sxs-lookup"><span data-stu-id="19310-210">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="19310-211">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="19310-211">Close the default policy settings page.</span></span>

<span data-ttu-id="19310-212">若要深入瞭解您的反網路釣魚原則選項，請參閱[設定反網路釣魚](set-up-anti-phishing-policies.md)原則。</span><span class="sxs-lookup"><span data-stu-id="19310-212">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="19310-213">第4部分-反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="19310-213">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="19310-214">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中取得[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-214">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="19310-215">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理** > **原則** > ]**反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="19310-215">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="19310-216">在 [**自訂**] 索引標籤上，開啟 [**自訂設定**]。</span><span class="sxs-lookup"><span data-stu-id="19310-216">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="19310-217">展開 [**預設垃圾郵件篩選原則**]，按一下 [**編輯原則**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="19310-217">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="19310-218">在 [**垃圾郵件及大量動作**] 區段中，將臨界值設為5或6。</span><span class="sxs-lookup"><span data-stu-id="19310-218">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="19310-219">在 [**允許清單**] 區段中，複查（必要時編輯）您允許的寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="19310-219">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="19310-220">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="19310-220">Click **Save**.</span></span>

<span data-ttu-id="19310-221">若要深入瞭解您的反垃圾郵件原則選項，請參閱[設定 Office 365 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-221">To learn more about your anti-spam policy options, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="19310-222">第5部分-要設定的其他設定</span><span class="sxs-lookup"><span data-stu-id="19310-222">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="19310-223">除了設定惡意程式碼保護、惡意 URLs 和檔案、網路釣魚和垃圾郵件之外，我們建議您設定零小時自動清除和審核記錄設定。</span><span class="sxs-lookup"><span data-stu-id="19310-223">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="19310-224">電子郵件自動清除零小時</span><span class="sxs-lookup"><span data-stu-id="19310-224">Zero-hour auto purge for email</span></span>

<span data-ttu-id="19310-225">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的訂閱中，可以使用[零小時自動清除](zero-hour-auto-purge.md)（ZAP）。</span><span class="sxs-lookup"><span data-stu-id="19310-225">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="19310-226">此保護功能預設為開啟狀態;不過，保護生效的情況必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="19310-226">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="19310-227">垃圾[訊息原則](anti-spam-protection.md)中的垃圾郵件動作會設定為**將郵件移至 [垃圾郵件] 資料夾**。</span><span class="sxs-lookup"><span data-stu-id="19310-227">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="19310-228">使用者保留其預設的[垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但未關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="19310-228">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="19310-229">若要深入瞭解，請參閱[零時自動清除-防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。</span><span class="sxs-lookup"><span data-stu-id="19310-229">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="19310-230">報告和調查的審計記錄</span><span class="sxs-lookup"><span data-stu-id="19310-230">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="19310-231">在包含[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的訂閱中可使用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="19310-231">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="19310-232">為了在威脅防護報告中查看資料（如[安全性儀表板](security-dashboard.md)、[電子郵件安全性報告](view-email-security-reports.md)和[Explorer](threat-explorer.md)），必須為您的組織開啟審核記錄。</span><span class="sxs-lookup"><span data-stu-id="19310-232">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="19310-233">若要深入瞭解，請參閱[開啟或關閉 Office 365 審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="19310-233">To learn more, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="19310-234">安裝後的工作</span><span class="sxs-lookup"><span data-stu-id="19310-234">Post-setup tasks</span></span>

<span data-ttu-id="19310-235">設定威脅防護功能之後，請務必監視這些功能的運作方式、視需要複查及修改原則，以及觀賞新功能和服務更新。</span><span class="sxs-lookup"><span data-stu-id="19310-235">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|<span data-ttu-id="19310-236">處理方式</span><span class="sxs-lookup"><span data-stu-id="19310-236">What to do</span></span>|<span data-ttu-id="19310-237">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="19310-237">Resources to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="19310-238">查看您的組織如何使用威脅防護功能，以查看報告</span><span class="sxs-lookup"><span data-stu-id="19310-238">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="19310-239">安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="19310-239">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="19310-240">電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="19310-240">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="19310-241">Office 365 ATP 報告</span><span class="sxs-lookup"><span data-stu-id="19310-241">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="19310-242">威脅總管</span><span class="sxs-lookup"><span data-stu-id="19310-242">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="19310-243">視需要定期複查和修正威脅防護原則</span><span class="sxs-lookup"><span data-stu-id="19310-243">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="19310-244">安全分數</span><span class="sxs-lookup"><span data-stu-id="19310-244">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="19310-245">智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="19310-245">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="19310-246">Office 365 威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="19310-246">Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="19310-247">監視新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="19310-247">Watch for new features and service updates</span></span>|[<span data-ttu-id="19310-248">標準及目標發行選項</span><span class="sxs-lookup"><span data-stu-id="19310-248">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="19310-249">訊息中心</span><span class="sxs-lookup"><span data-stu-id="19310-249">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="19310-250">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="19310-250">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="19310-251">服務說明</span><span class="sxs-lookup"><span data-stu-id="19310-251">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
