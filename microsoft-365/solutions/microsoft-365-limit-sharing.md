---
title: 在 Microsoft 365 中限制共用
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
description: 了解在 Microsoft 365 中限制或停用共用的選項。
ms.openlocfilehash: 69a71d84f32316278353f8de392202f1a92dc22d
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528179"
---
# <a name="limit-sharing-in-microsoft-365"></a><span data-ttu-id="a7f4b-103">在 Microsoft 365 中限制共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-103">Limit sharing in Microsoft 365</span></span>

<span data-ttu-id="a7f4b-104">雖然您無法完全將內部共用停用，或移除網站的 [共用] 按鈕，但您可以透過多種方式在 Microsoft 365 中限制共用，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-104">While you can't disable internal sharing entirely or remove the Share button from sites, there are a variety of ways that you can limit sharing in Microsoft 365 to meet the needs of your organization.</span></span>

<span data-ttu-id="a7f4b-105">下表列出共用檔案的方法。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-105">The methods of sharing files are listed in the table below.</span></span> <span data-ttu-id="a7f4b-106">如需詳細資訊，請按一下 **[共用方法]** 欄中的連結。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-106">Click the link in the **Sharing method** column for detailed information.</span></span>

|<span data-ttu-id="a7f4b-107">共用方法</span><span class="sxs-lookup"><span data-stu-id="a7f4b-107">Sharing method</span></span>|<span data-ttu-id="a7f4b-108">描述</span><span class="sxs-lookup"><span data-stu-id="a7f4b-108">Description</span></span>|<span data-ttu-id="a7f4b-109">限制選項</span><span class="sxs-lookup"><span data-stu-id="a7f4b-109">Limiting options</span></span>|
|:-------------|:----------|:-------------|
|[<span data-ttu-id="a7f4b-110">Microsoft 365 群組或團隊</span><span class="sxs-lookup"><span data-stu-id="a7f4b-110">Microsoft 365 group or team</span></span>](#microsoft-365-group-or-team)|<span data-ttu-id="a7f4b-111">獲授與 Microsoft Teams 團隊或 Microsoft 365 群組存取權的人員對於相關聯 SharePoint 網站中的檔案具有編輯存取權。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-111">People granted access to a Microsoft Teams team or Microsoft 365 group have edit access to files in the associated SharePoint site.</span></span>|<span data-ttu-id="a7f4b-112">如果群組或團隊是私人的，加入團隊的共用邀請會送往擁有者以進行核准。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-112">If the group or team is private, sharing invitations to join the team go to the owner for approval.</span></span> <span data-ttu-id="a7f4b-113">系統管理員可以停用來賓存取，以防止組織外部的人員存取。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-113">Admins can disable guest access to prevent access by people from outside the organization.</span></span>|
|[<span data-ttu-id="a7f4b-114">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="a7f4b-114">SharePoint site</span></span>](#sharepoint-site)|<span data-ttu-id="a7f4b-115">人員可以獲授與擁有 SharePoint 網站的擁有者、成員或來賓存取，並將擁有網站中檔案的該層級存取權。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-115">People can be granted Owner, Member, or Visitor access to a SharePoint site and will have that level of access to files in the site.</span></span>|<span data-ttu-id="a7f4b-116">您可以限制網站權限，以便只有網站擁有者可以共用網站。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-116">Site permissions can be restricted so that only site owners can share the site.</span></span>|
|[<span data-ttu-id="a7f4b-117">與特定人員共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-117">Sharing with specific people</span></span>](#sharing-with-specific-people)|<span data-ttu-id="a7f4b-118">網站成員與擁有編輯權限的人員可以提供檔案和資料夾的直接權限，或使用 *[特定人員]* 連結來共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-118">Site members and people with edit permissions can give direct permissions to files and folders or share them by using *Specific people* links.</span></span>|<span data-ttu-id="a7f4b-119">您可以限制網站權限，以便只有網站擁有者可以共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-119">Site permissions can be restricted so that only site owners can share files and folders.</span></span> <span data-ttu-id="a7f4b-120">在此情況下，由網站成員共用的直接存取和 *[特定人員]* 連結會送往網站擁有者以進行核准。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-120">In this case, direct access and *Specific people* link sharing by site members goes to site owner for approval.</span></span>|
|[<span data-ttu-id="a7f4b-121">SharePoint 來賓共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-121">SharePoint guest sharing</span></span>](#sharepoint-guest-sharing)|<span data-ttu-id="a7f4b-122">SharePoint 網站擁有者和成員可以與組織外部人員共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-122">SharePoint site owners and members can share files and folders with people outside the organization.</span></span>|<span data-ttu-id="a7f4b-123">您可以為整個組織或個別網站停用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-123">Guest sharing can be disabled for the entire organization or for individual sites.</span></span>|
|<span data-ttu-id="a7f4b-124">[[貴組織中的人員]\*\* 共用連結](#people-in-your-organization-sharing-links)</span><span class="sxs-lookup"><span data-stu-id="a7f4b-124">[*People in your organization* sharing links](#people-in-your-organization-sharing-links)</span></span>|<span data-ttu-id="a7f4b-125">SharePoint 網站擁有者和成員可以使用 *[貴組織中的人員]* 連結來共用檔案，此功能適用於組織內部的任何人。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-125">SharePoint site owners and members can share files using *People in your organization* links, which will work for anyone inside the organization.</span></span>|<span data-ttu-id="a7f4b-126">可在網站層級停用 *[貴組織中的人員]* 連結。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-126">*People in your organization* links can be disabled at the site level.</span></span>|
|[<span data-ttu-id="a7f4b-127">電子郵件</span><span class="sxs-lookup"><span data-stu-id="a7f4b-127">Email</span></span>](#email)|<span data-ttu-id="a7f4b-128">具有檔案存取權的人員可以透過電子郵件將檔案傳送給其他人。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-128">People with access to a file can send it to others via email.</span></span>|<span data-ttu-id="a7f4b-129">系統管理員可以使用敏感度標籤來加密檔案，以防止將檔案與未經授權的人員共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-129">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|
|[<span data-ttu-id="a7f4b-130">下載或檔案複製</span><span class="sxs-lookup"><span data-stu-id="a7f4b-130">Download or file copy</span></span>](#download-or-file-copy)|<span data-ttu-id="a7f4b-131">具有檔案存取權的人員可以下載或複製檔案，並與 Microsoft 365 以外的其他人共用檔案。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-131">People with access to a file can download or copy it and share it with others outside the scope of Microsoft 365.</span></span>|<span data-ttu-id="a7f4b-132">系統管理員可以使用敏感度標籤來加密檔案，以防止將檔案與未經授權的人員共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-132">Admins can encrypt files by using sensitivity labels to prevent them being shared with unauthorized people.</span></span>|

<span data-ttu-id="a7f4b-133">雖然您可以使用本文所述的系統管理控制項來限制貴組織中的共用，我們高度建議您考慮使用 Microsoft 365 中提供的安全性與合規性功能，以建立安全的共用環境。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-133">While you can use the admin controls described in this article to limit sharing in your organization, we highly recommend that you consider using the security and compliance features available in Microsoft 365 to create a secure sharing environment.</span></span> <span data-ttu-id="a7f4b-134">如需詳細資訊，請參閱[在 SharePoint 中使用 Microsoft 365 進行檔案共同作業](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)和[適用於高度管制資料的 Teams](https://docs.microsoft.com/microsoft-365/enterprise/secure-teams-highly-regulated-data-scenario)。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-134">See [File collaboration in SharePoint with Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) and [Teams for highly regulated data](https://docs.microsoft.com/microsoft-365/enterprise/secure-teams-highly-regulated-data-scenario) for information.</span></span>

<span data-ttu-id="a7f4b-135">若要了解貴組織使用共用功能的方式，請[執行有關檔案和資料夾共用的報告](https://docs.microsoft.com/sharepoint/sharing-reports)。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-135">To understand how sharing is being used in your organization, [run a report on file and folder sharing](https://docs.microsoft.com/sharepoint/sharing-reports).</span></span>

## <a name="microsoft-365-group-or-team"></a><span data-ttu-id="a7f4b-136">Microsoft 365 群組或團隊</span><span class="sxs-lookup"><span data-stu-id="a7f4b-136">Microsoft 365 group or team</span></span>

<span data-ttu-id="a7f4b-137">如果想要限制 Microsoft 365 群組或 Microsoft Teams 團隊中的共用，請務必將群組或團隊設為私人。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-137">If you want to limit sharing in a Microsoft 365 group or Microsoft Teams team, it's important to make the group or team private.</span></span> <span data-ttu-id="a7f4b-138">貴組織內部的人員可以隨時加入公開群組或團隊。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-138">People inside your organization can join a public group or team anytime.</span></span> <span data-ttu-id="a7f4b-139">除非群組或團隊是私人的，否則無法限制在組織內共用團隊或其檔案。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-139">Unless the group or team is private, there's no way to limit sharing of the team or its files within the organization.</span></span>

### <a name="guest-sharing"></a><span data-ttu-id="a7f4b-140">來賓共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-140">Guest sharing</span></span>

<span data-ttu-id="a7f4b-141">如果想要在 Teams 中防止來賓存取，您可以在 Teams 系統管理中心中關閉來賓共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-141">If you want to prevent guest access in Teams, you can turn off guest sharing in the Teams admin center.</span></span>

<span data-ttu-id="a7f4b-142">關閉 Teams 的來賓共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-142">To turn off guest sharing for Teams</span></span>
1. <span data-ttu-id="a7f4b-143">在 Teams 系統管理中心中，展開 **[全組織設定]**，然後按一下 **[來賓存取]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-143">In the Teams admin center, expand **Org-wide settings**, and then click **Guest access**.</span></span>
2. <span data-ttu-id="a7f4b-144">關閉 **[在 Teams 中允許來賓存取]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-144">Turn off **Allow guest access in Teams**.</span></span>
3. <span data-ttu-id="a7f4b-145">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-145">Click **Save**.</span></span>

<span data-ttu-id="a7f4b-146">如果想要在 Microsoft 365 群組中防止來賓存取，您可以在 Microsoft 365 系統管理中心中關閉群組來賓存取設定。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-146">If you want to prevent guest access in Microsoft 365 Groups, you can turn off the groups guest access settings in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="a7f4b-147">若要關閉 Microsoft 365 群組中的來賓共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-147">To turn off guest sharing in Microsoft 365 Groups</span></span>
1. <span data-ttu-id="a7f4b-148">在 Microsoft 365 系統管理中心中，按一下 **[設定]**，然後按一下 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-148">In the Microsoft 365 admin center, click **Settings**, and then click **Settings**.</span></span>
2. <span data-ttu-id="a7f4b-149">在 [服務]\*\*\*\* 索引標籤上，按一下 [Microsoft 365 群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-149">On the **Services** tab, click **Microsoft 365 Groups**.</span></span>
3. <span data-ttu-id="a7f4b-150">清除 **[讓貴組織外部的群組成員存取群組內容]** 和 **[讓群組擁有者將貴組織外部的人員新增到群組]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-150">Clear the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes.</span></span>
4. <span data-ttu-id="a7f4b-151">按一下 [儲存變更]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-151">Click **Save changes**.</span></span>

    ![Microsoft 365 系統管理中心中 Microsoft 365 群組共用設定的螢幕擷取畫面](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> <span data-ttu-id="a7f4b-153">如果想要防止特定群組或團隊的來賓共用，您可以使用 Microsoft PowerShell 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-153">If you want to prevent guest sharing for a particular group or team, you can do so by using Microsoft PowerShell.</span></span> <span data-ttu-id="a7f4b-154">如需詳細資料，請參閱[允許或封鎖來自特定群組的來賓使用者](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#block-guest-users-from-a-specific-group)。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-154">See [Block guest users from a specific group](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#block-guest-users-from-a-specific-group) for details.</span></span>

<span data-ttu-id="a7f4b-155">在 Azure Active Directory 中允許或封鎖網域，即可限制對來自特定網域的使用者進行來賓共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-155">You can limit guest sharing to users from specific domains by allowing or blocking domains in Azure Active Directory.</span></span> <span data-ttu-id="a7f4b-156">如果您已啟用 [SharePoint 和 OneDrive 與 Azure AD B2B 整合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)，則這也會影響 SharePoint 中的來賓共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-156">This will also affect guest sharing in SharePoint if you have enabled [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

<span data-ttu-id="a7f4b-157">僅允許從指定網域共用邀請</span><span class="sxs-lookup"><span data-stu-id="a7f4b-157">To allow sharing invitations only from specified domains</span></span>
1. <span data-ttu-id="a7f4b-158">在 Azure Active Directory 的 [概觀] 頁面上，按一下 **[組織關聯]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-158">In Azure Active Directory, on the Overview page, click **Organizational relationships**.</span></span>
2. <span data-ttu-id="a7f4b-159">按一下 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-159">Click **Settings**.</span></span>
3. <span data-ttu-id="a7f4b-160">在 **[共同作業限制]** 底下，選取 **[拒絕指定網域的邀請]** 或 **[僅對指定的網域允許邀請]**，然後輸入您要使用的網域。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-160">Under **Collaboration restrictions**, select **Deny invitations to the specified domains** or **Allow invitations only to the specified domains**, and then type the domains that you want to use.</span></span>
4. <span data-ttu-id="a7f4b-161">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-161">Click **Save**.</span></span>

    ![Azure Active Directory 中共同作業限制設定的螢幕擷取畫面](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a><span data-ttu-id="a7f4b-163">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="a7f4b-163">SharePoint site</span></span>

<span data-ttu-id="a7f4b-164">您可以將 SharePoint 網站共用限制於僅限網站擁有者。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-164">You can limit SharePoint site sharing to site owners only.</span></span> <span data-ttu-id="a7f4b-165">這麼做會防止網站成員共用網站。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-165">This prevents site members from sharing the site.</span></span> <span data-ttu-id="a7f4b-166">請記住，如果網站連接至 Microsoft 365 群組，群組成員可以邀請其他人加入群組，而這些使用者將擁有網站存取權。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-166">Keep in mind that if the site is connected to a Microsoft 365 group, group members can invite others to the group and those users will have site access.</span></span>

<span data-ttu-id="a7f4b-167">限制擁有者的網站共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-167">To limit site sharing to owners</span></span>
1. <span data-ttu-id="a7f4b-168">在網站中，按一下齒輪圖示，然後按一下 **[網站權限]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-168">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="a7f4b-169">按一下 **[共用設定]** 下的 **[變更共用設定]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-169">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="a7f4b-170">選取 **[網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-170">Select **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**.</span></span>
4. <span data-ttu-id="a7f4b-171">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-171">Click **Save**.</span></span>

    ![SharePoint 網站中共用權限設定的螢幕擷取畫面](../media/sharepoint-site-sharing-permissions-level-two.png)

<span data-ttu-id="a7f4b-173">您可以關閉存取要求，以防止不是網站成員的使用者要求存取權。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-173">You can prevent users who are not members of the site from requesting access by turning off access requests.</span></span>

<span data-ttu-id="a7f4b-174">關閉存取要求</span><span class="sxs-lookup"><span data-stu-id="a7f4b-174">To turn off access requests</span></span>
1. <span data-ttu-id="a7f4b-175">在網站中，按一下齒輪圖示，然後按一下 **[網站權限]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-175">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="a7f4b-176">按一下 **[共用設定]** 下的 **[變更共用設定]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-176">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="a7f4b-177">關閉 **[允許存取要求]**，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-177">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="a7f4b-178">您可以允許或封鎖網站的網域，以限制對特定網域的網站共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-178">You can limit site sharing to specific domains by allowing or blocking domains for the site.</span></span>

<span data-ttu-id="a7f4b-179">依網域限制網站共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-179">To limit site sharing by domain</span></span>
1. <span data-ttu-id="a7f4b-180">在 SharePoint 系統管理中心的 **[網站]** 底下，按一下 **[使用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-180">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="a7f4b-181">按一下您要設定的網站。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-181">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="a7f4b-182">在 **[原則]** 索引標籤的 **[外部共用]** 底下，按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-182">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="a7f4b-183">在 **[外部共用的進階設定]** 底下，選取 **[依網域限制共用]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-183">Under **Advanced settings for external sharing**, select the **Limit sharing by domain**.</span></span>
5. <span data-ttu-id="a7f4b-184">新增您想要允許或封鎖的網域，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-184">Add the domains that you want to allow or block, and then click **Save**.</span></span>
6. <span data-ttu-id="a7f4b-185">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-185">Click **Save**.</span></span>

    ![允許的網域網站層級設定的螢幕擷取畫面](../media/limit-site-sharing-by-domain.png)

## <a name="sharing-with-specific-people"></a><span data-ttu-id="a7f4b-187">與特定人員共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-187">Sharing with specific people</span></span>

<span data-ttu-id="a7f4b-188">如果想要限制網站或其內容的共用，可以將網站設定為僅允許網站擁有者共用檔案、資料夾和網站。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-188">if you want to limit the sharing of a site or its contents, you can configure the site to only allow site owners to share files, folders, and the site.</span></span> <span data-ttu-id="a7f4b-189">設定此設定之後，網站成員若嘗試使用 *[特定人員]* 連結共用檔案或資料夾，即會送往網站擁有者以進行核准。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-189">When this is configured, site members' attempts to share files or folders by using *Specific people* links will go to the site owner for approval.</span></span>

<span data-ttu-id="a7f4b-190">將網站、檔案和資料夾共用限制在擁有者</span><span class="sxs-lookup"><span data-stu-id="a7f4b-190">To limit site, file, and folder sharing to owners</span></span>
1. <span data-ttu-id="a7f4b-191">在網站中，按一下齒輪圖示，然後按一下 **[網站權限]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-191">In the site, click the gear icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="a7f4b-192">按一下 **[共用設定]** 下的 **[變更共用設定]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-192">Under **Sharing settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="a7f4b-193">選取 **[只有網站擁有者可以共用檔案、資料夾和網站]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-193">Select **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="a7f4b-194">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-194">Click **Save**.</span></span>

    ![SharePoint 網站中共用權限設定的螢幕擷取畫面](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a><span data-ttu-id="a7f4b-196">SharePoint 來賓共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-196">SharePoint guest sharing</span></span>

<span data-ttu-id="a7f4b-197">如果想要防止與組織外部人員共用 SharePoint 或 OneDrive 檔案和資料夾，您可以關閉整個組織或個別網站的來賓共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-197">If you want to prevent sharing SharePoint or OneDrive files and folders with people outside your organization, you can turn off guest sharing for the entire organization or for an individual site.</span></span>

<span data-ttu-id="a7f4b-198">關閉組織的 SharePoint 來賓共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-198">To turn off SharePoint guest sharing for your organization</span></span>
1. <span data-ttu-id="a7f4b-199">在 SharePoint 系統管理中心的 **[原則]** 底下，按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-199">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="a7f4b-200">在 **[外部共用]** 底下，將 SharePoint 滑桿向下拖曳到 **[只有貴組織中的人員]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-200">Under **External sharing**, drag the SharePoint slider down to **Only people in your organization**.</span></span>
3. <span data-ttu-id="a7f4b-201">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-201">Click **Save**.</span></span>

    ![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-tenant-sharing-off.png)


<span data-ttu-id="a7f4b-203">關閉網站的來賓共用</span><span class="sxs-lookup"><span data-stu-id="a7f4b-203">To turn off guest sharing for a site</span></span>
1. <span data-ttu-id="a7f4b-204">在 SharePoint 系統管理中心的 **[網站]** 底下，按一下 **[使用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-204">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="a7f4b-205">按一下您要設定的網站。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-205">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="a7f4b-206">在 **[原則]** 索引標籤的 **[外部共用]** 底下，按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-206">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="a7f4b-207">在 **[外部共用]** 底下，選擇 **[只有貴組織中的人員]**，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-207">Under **External sharing**, choose **Only people in your organization**, and then click **Save**.</span></span>

    ![SharePoint 網站層級共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings-off.png)

<span data-ttu-id="a7f4b-209">如果想要與組織外部人員共用，但想要確保每個人都能驗證，您可以停用整個組織或個別網站的 *[任何人]* (匿名共用) 連結。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-209">If you would like to allow sharing with people outside your organization but you want to make sure that everyone authenticates, you can disable *Anyone* (anonymous sharing) links for the entire organization or for an individual site.</span></span>

<span data-ttu-id="a7f4b-210">關閉組織層級的 *[任何人]* 連結</span><span class="sxs-lookup"><span data-stu-id="a7f4b-210">To turn off *Anyone* links at the organization level</span></span>
1. <span data-ttu-id="a7f4b-211">在 SharePoint 系統管理中心的 **[原則]** 底下，按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-211">In the SharePoint admin center, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="a7f4b-212">在 **[外部共用]** 底下，將 SharePoint 滑桿向下拖曳至 **[新的及現有的來賓]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-212">Under **External sharing**, drag the SharePoint slider down to **New and existing guests**.</span></span>
3. <span data-ttu-id="a7f4b-213">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-213">Click **Save**.</span></span>

    ![SharePoint 網站層級共用設定的螢幕擷取畫面](../media/sharepoint-guest-sharing-new-existing-guests.png)

<span data-ttu-id="a7f4b-215">關閉網站的 *[任何人]* 連結</span><span class="sxs-lookup"><span data-stu-id="a7f4b-215">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="a7f4b-216">在 SharePoint 系統管理中心的 **[網站]** 底下，按一下 **[使用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-216">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="a7f4b-217">按一下您要設定的網站。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-217">Click the site that you want to configure.</span></span>
3. <span data-ttu-id="a7f4b-218">在 **[原則]** 索引標籤的 **[外部共用]** 底下，按一下 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-218">On the **Policies** tab, under **External sharing** click **Edit**.</span></span>
4. <span data-ttu-id="a7f4b-219">在 **[外部共用]** 底下，選擇 **[新的及現有的來賓]**，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-219">Under **External sharing**, choose **New and existing guests**, and then click **Save**.</span></span>

    ![SharePoint 網站層級共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a><span data-ttu-id="a7f4b-221">*[貴組織中的人員]* 共用連結</span><span class="sxs-lookup"><span data-stu-id="a7f4b-221">*People in your organization* sharing links</span></span>

<span data-ttu-id="a7f4b-222">根據預設，網站的成員可以使用 *[貴組織中的人員]* 連結來與組織中的其他人員共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-222">By default, members of a site can share files and folders with other people in your organization by using a *People in your organization* link.</span></span> <span data-ttu-id="a7f4b-223">您可以使用 PowerShell 停用 *[貴組織中的人員]* 連結：</span><span class="sxs-lookup"><span data-stu-id="a7f4b-223">You can disable *People in your organization* links by using PowerShell:</span></span>

`Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks`

<span data-ttu-id="a7f4b-224">例如：</span><span class="sxs-lookup"><span data-stu-id="a7f4b-224">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks`

## <a name="email"></a><span data-ttu-id="a7f4b-225">電子郵件</span><span class="sxs-lookup"><span data-stu-id="a7f4b-225">Email</span></span>

<span data-ttu-id="a7f4b-226">您可以使用加密來防止非必要地共用電子郵件。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-226">You can prevent unwanted sharing of emails by using encryption.</span></span> <span data-ttu-id="a7f4b-227">這麼做會防止將電子郵件轉寄或以其他方式與未經授權的使用者共用。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-227">This prevents emails being forwarded or otherwise shared with unauthorized users.</span></span> <span data-ttu-id="a7f4b-228">您可以使用敏感度標籤來啟用電子郵件加密。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-228">Email encryption can be enabled by using sensitivity labels.</span></span> <span data-ttu-id="a7f4b-229">如需詳細資料，請參閱[使用敏感度標籤中的加密來限制內容的存取](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-229">See [Restrict access to content by using encryption in sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) for details.</span></span>

## <a name="download-or-file-copy"></a><span data-ttu-id="a7f4b-230">下載或檔案複製</span><span class="sxs-lookup"><span data-stu-id="a7f4b-230">Download or file copy</span></span>

<span data-ttu-id="a7f4b-231">擁有 Microsoft 365 中檔案和資料夾存取權的使用者可以下載檔案，並將檔案複製到外部媒體。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-231">Users who have access to files and folders in Microsoft 365 can download files and copy them to external media.</span></span> <span data-ttu-id="a7f4b-232">若要降低非必要檔案共用的風險，您可以使用敏感度標籤來加密內容。</span><span class="sxs-lookup"><span data-stu-id="a7f4b-232">To reduce the risk of unwanted file sharing, you can encrypt the content by using sensitivity labels.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7f4b-233">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a7f4b-233">See also</span></span>

[<span data-ttu-id="a7f4b-234">Microsoft 365 來賓共用設定參考</span><span class="sxs-lookup"><span data-stu-id="a7f4b-234">Microsoft 365 guest sharing settings reference</span></span>](microsoft-365-guest-settings.md)
