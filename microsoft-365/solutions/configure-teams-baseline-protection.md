---
title: 為小組設定基準保護
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: 了解如何使用基準層級的保護來部署小組。
ms.openlocfilehash: db1a58fd06a62240cbcfcc74f83ba6196f33df80
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114291"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="8b7be-103">為小組設定基準保護</span><span class="sxs-lookup"><span data-stu-id="8b7be-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="8b7be-104">在本文中，我們將說明如何使用基準層級的保護來部署小組。</span><span class="sxs-lookup"><span data-stu-id="8b7be-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="8b7be-105">此層級可讓使用者獲得廣泛的共同作業選項，同時又能增強權限管理功能並針對過度共用提供基本防護。</span><span class="sxs-lookup"><span data-stu-id="8b7be-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="8b7be-106">這個層級的建議保護包括身分識別和裝置存取原則，以及惡意程式碼防護。</span><span class="sxs-lookup"><span data-stu-id="8b7be-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="8b7be-107">此外，您也可以視需要套用條件式存取原則和資料外洩防護。</span><span class="sxs-lookup"><span data-stu-id="8b7be-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="8b7be-108">初始保護</span><span class="sxs-lookup"><span data-stu-id="8b7be-108">Initial protections</span></span>

<span data-ttu-id="8b7be-109">我們所建議的第一個步驟是設定基本身分識別和裝置存取原則。</span><span class="sxs-lookup"><span data-stu-id="8b7be-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="8b7be-110">如需詳細資訊，請參閱[用來保護 Teams 聊天、群組和檔案的原則建議](../security/office-365-security/teams-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7be-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="8b7be-111">我們也建議您開啟基本的適用於 Office 365 的 Defender 功能，以防範文件、附件和連結中的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="8b7be-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="8b7be-112">建議您開啟下表中的每個選項。</span><span class="sxs-lookup"><span data-stu-id="8b7be-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="8b7be-113">選項</span><span class="sxs-lookup"><span data-stu-id="8b7be-113">Option</span></span>|<span data-ttu-id="8b7be-114">資訊</span><span class="sxs-lookup"><span data-stu-id="8b7be-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="8b7be-115">適用於 SPO、OneDrive 和 Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="8b7be-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="8b7be-116">安全附件</span><span class="sxs-lookup"><span data-stu-id="8b7be-116">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)<br>[<span data-ttu-id="8b7be-117">適用於 Office 365 的 Defender - SharePoint、OneDrive 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b7be-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](../security/office-365-security/mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="8b7be-118">安全文件</span><span class="sxs-lookup"><span data-stu-id="8b7be-118">Safe Documents</span></span>|[<span data-ttu-id="8b7be-119">適用於 Office 365 的 Microsoft Defender 中的安全文件</span><span class="sxs-lookup"><span data-stu-id="8b7be-119">Safe Documents in Microsoft Defender for Office 365</span></span>](../security/office-365-security/safe-docs.md)|
|<span data-ttu-id="8b7be-120">適用於 Teams 的安全連結</span><span class="sxs-lookup"><span data-stu-id="8b7be-120">Safe Links for Teams</span></span>|[<span data-ttu-id="8b7be-121">Teams 中的 Office 365 安全連結</span><span class="sxs-lookup"><span data-stu-id="8b7be-121">Office 365 Safe Links in Teams</span></span>](../security/office-365-security/safe-links.md)<br>[<span data-ttu-id="8b7be-122">安全連結</span><span class="sxs-lookup"><span data-stu-id="8b7be-122">Safe Links</span></span>](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="8b7be-123">Teams 來賓共用</span><span class="sxs-lookup"><span data-stu-id="8b7be-123">Teams guest sharing</span></span>

<span data-ttu-id="8b7be-124">在每一層中，我們都有可讓您與組織外部的人員共用的選項。</span><span class="sxs-lookup"><span data-stu-id="8b7be-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="8b7be-125">針對敏感度和高敏感度層，我們會有選項可供您使用敏感度標籤在小組層級關閉來賓共用。</span><span class="sxs-lookup"><span data-stu-id="8b7be-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="8b7be-126">但必須開啟組織層級的來賓共用設定，才能讓來賓共用在 Teams 中完全生效。</span><span class="sxs-lookup"><span data-stu-id="8b7be-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Teams 來賓存取切換的螢幕擷取畫面](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="8b7be-128">設定 Teams 來賓存取設定</span><span class="sxs-lookup"><span data-stu-id="8b7be-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="8b7be-129">登入 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="8b7be-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="8b7be-130">在左側導覽窗格中，按一下 [顯示全部]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="8b7be-131">在 [系統管理中心] 底下，按一下 [Teams]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="8b7be-132">在 Teams 系統管理中心的左側導覽中展開 [全組織設定]，然後按一下 [來賓存取]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="8b7be-133">確定 [在 Teams 中允許來賓存取] 已設定為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="8b7be-134">對其他來賓設定進行所需的變更，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="8b7be-135">Teams 來賓設定在開啟後，最慢可能需要 24 小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="8b7be-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="8b7be-136">Office 365 群組和 SharePoint 預設會開啟來賓共用功能，但是如果您先前已變更組織的任何來賓共用設定，則建議您檢閱[在小組中與來賓共同作業](./collaborate-as-team.md)，以確保 Teams 中可以使用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="8b7be-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](./collaborate-as-team.md) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="8b7be-137">網站和檔案共用</span><span class="sxs-lookup"><span data-stu-id="8b7be-137">Site and file sharing</span></span>

<span data-ttu-id="8b7be-138">為了降低不小心與組織外的人員共用檔案和資料夾的風險，建議您將 SharePoint 的預設共用連結變更為 [只有貴組織中的人員]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="8b7be-139">(如果使用者需要對外共用，且您已啟用來賓共用，其仍可在共用時變更連結類型)。</span><span class="sxs-lookup"><span data-stu-id="8b7be-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="8b7be-140">變更預設的共用連結</span><span class="sxs-lookup"><span data-stu-id="8b7be-140">To change the default sharing link</span></span>
1. <span data-ttu-id="8b7be-141">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="8b7be-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="8b7be-142">在 [原則] 底下，按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="8b7be-143">在 [檔案與資料夾連結] 下，選取 [只有貴組織中的人員]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="8b7be-144">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-144">Click **Save**.</span></span>

<span data-ttu-id="8b7be-145">為了獲得最佳的來賓共用體驗，建議您啟用 [SharePoint 和 OneDrive 與 Azure AD B2B 整合](/sharepoint/sharepoint-azureb2b-integration-preview)。</span><span class="sxs-lookup"><span data-stu-id="8b7be-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="8b7be-146">建立小組</span><span class="sxs-lookup"><span data-stu-id="8b7be-146">Create a team</span></span>

<span data-ttu-id="8b7be-147">在與小組相關聯的 SharePoint 網站中，還會執行另外的基準層級保護設定。</span><span class="sxs-lookup"><span data-stu-id="8b7be-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="8b7be-148">請先[建立公用或私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)，再繼續進行下一節。</span><span class="sxs-lookup"><span data-stu-id="8b7be-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="8b7be-149">網站共用設定</span><span class="sxs-lookup"><span data-stu-id="8b7be-149">Site sharing settings</span></span>

<span data-ttu-id="8b7be-150">根據預設，SharePoint 網站的成員可以邀請其他人加入網站。</span><span class="sxs-lookup"><span data-stu-id="8b7be-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="8b7be-151">當網站屬於小組時，小組成員便會納入為網站成員。</span><span class="sxs-lookup"><span data-stu-id="8b7be-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="8b7be-152">不過，直接新增至網站的人員無法存取小組的其他資源。</span><span class="sxs-lookup"><span data-stu-id="8b7be-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="8b7be-153">因此，建議您透過小組來專門管理權限。</span><span class="sxs-lookup"><span data-stu-id="8b7be-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="8b7be-154">為了有助於管理權限，建議您將相關聯的網站設定為只允許擁有者可自行共用網站。</span><span class="sxs-lookup"><span data-stu-id="8b7be-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="8b7be-155">這可簡化權限管理工作，並有助於防止有人在小組擁有者不知情的情況下進行存取。</span><span class="sxs-lookup"><span data-stu-id="8b7be-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="8b7be-156">請為需要基準保護的每個小組執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8b7be-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="8b7be-157">更新網站共用設定</span><span class="sxs-lookup"><span data-stu-id="8b7be-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="8b7be-158">在小組的工具列中，按一下 [檔案]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="8b7be-159">按一下 [在 SharePoint 中開啟]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="8b7be-160">在 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="8b7be-161">在 **[網站權限]** 窗格的 **[網站共用]** 下，按一下 **[變更成員可以使用的共用方式]**。</span><span class="sxs-lookup"><span data-stu-id="8b7be-161">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
5. <span data-ttu-id="8b7be-162">在 [共用權限] 底下，選擇 [網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站]，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="8b7be-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="8b7be-163">其他保護</span><span class="sxs-lookup"><span data-stu-id="8b7be-163">Additional protections</span></span>

<span data-ttu-id="8b7be-164">Microsoft 365 提供了其他方法來保護您的內容。</span><span class="sxs-lookup"><span data-stu-id="8b7be-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="8b7be-165">請想想下列選項是否有助於改善貴組織的安全性。</span><span class="sxs-lookup"><span data-stu-id="8b7be-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="8b7be-166">讓來賓同意[使用規定](/azure/active-directory/conditional-access/terms-of-use)。</span><span class="sxs-lookup"><span data-stu-id="8b7be-166">Have guests agree to a [terms of use](/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="8b7be-167">為來賓設定[工作階段逾時原則](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)。</span><span class="sxs-lookup"><span data-stu-id="8b7be-167">Configure a [session timeout policy](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="8b7be-168">建立[敏感資訊類型](../compliance/sensitive-information-type-learn-about.md)，並使用[資料外洩防護](../compliance/dlp-learn-about-dlp.md) 來設定關於存取敏感資訊的原則。</span><span class="sxs-lookup"><span data-stu-id="8b7be-168">Create [sensitive information types](../compliance/sensitive-information-type-learn-about.md) and use [data loss protection](../compliance/dlp-learn-about-dlp.md) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b7be-169">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8b7be-169">See Also</span></span>

[<span data-ttu-id="8b7be-170">管理 Teams 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="8b7be-170">Manage meeting policies in Teams</span></span>](/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="8b7be-171">開始使用測試人員風險管理</span><span class="sxs-lookup"><span data-stu-id="8b7be-171">Get started with insider risk management</span></span>](../compliance/insider-risk-management-configure.md)