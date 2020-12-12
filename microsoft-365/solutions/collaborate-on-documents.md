---
title: 在文件上與來賓共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 在本文中，您將瞭解如何在 SharePoint 和 OneDrive 的檔中與客人共同作業。
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663508"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="188e5-103">在文件上與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="188e5-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="188e5-104">如果您需要與組織外部的人員共同作業 SharePoint 或 OneDrive 中的檔，您可以將檔的共用連結傳送給他們。</span><span class="sxs-lookup"><span data-stu-id="188e5-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="188e5-105">在本文中，我們將逐步檢查必要的 Microsoft 365 設定步驟，以設定 SharePoint 和 OneDrive 組織需求的共用連結。</span><span class="sxs-lookup"><span data-stu-id="188e5-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="188e5-106">影片示範</span><span class="sxs-lookup"><span data-stu-id="188e5-106">Video demonstration</span></span>

<span data-ttu-id="188e5-107">這段影片顯示本檔所述的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="188e5-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="188e5-108">Azure 外部協同作業設定</span><span class="sxs-lookup"><span data-stu-id="188e5-108">Azure external collaboration settings</span></span>

<span data-ttu-id="188e5-109">Microsoft 365 中的共用受 [Azure Active Directory 中的 B2B 外部](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)共同作業設定的最高層級。</span><span class="sxs-lookup"><span data-stu-id="188e5-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="188e5-110">如果 Azure AD 中已停用或限制來賓共用，此設定會覆寫您在 Microsoft 365 中設定的任何共用設定。</span><span class="sxs-lookup"><span data-stu-id="188e5-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="188e5-111">檢查 B2B 的外部共同作業設定，以確保不會封鎖與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="188e5-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="188e5-113">設定外部協同作業設定</span><span class="sxs-lookup"><span data-stu-id="188e5-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="188e5-114">登入 Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="188e5-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="188e5-115">在左功能窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="188e5-116">按一下 [ **外部** 身分識別]。</span><span class="sxs-lookup"><span data-stu-id="188e5-116">Click **External identities**.</span></span>
4. <span data-ttu-id="188e5-117">在 [ **快速入門** ] 畫面上，按一下左功能窗格中的 [ **外部協同作業設定**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="188e5-118">確定 **guest 和 guest inviter role 中的系統管理員和使用者都可以邀請** 和 **成員可以邀請** 皆設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="188e5-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="188e5-119">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="188e5-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="188e5-120">請記下 [ **協同限制** ] 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="188e5-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="188e5-121">確定您要與之來賓進行共同作業的網域不會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="188e5-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="188e5-122">如果您與多個組織的客人合作，您可能想要限制其存取目錄資料的能力。</span><span class="sxs-lookup"><span data-stu-id="188e5-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="188e5-123">這可防止使用者看到目錄中的客人。</span><span class="sxs-lookup"><span data-stu-id="188e5-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="188e5-124">若要執行此動作，請在 [ **來賓使用者訪問限制**] 底下，選取 [來賓使用者對內容的 **存取權受到限制** ]，或 **[來賓使用者存取許可權制于自身目錄物件的屬性和成員資格]** 設定。</span><span class="sxs-lookup"><span data-stu-id="188e5-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="188e5-125">SharePoint 組織層級的共用設定</span><span class="sxs-lookup"><span data-stu-id="188e5-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="188e5-126">為了讓組織外部人員能夠存取 SharePoint 或 OneDrive 中的檔，SharePoint 和 OneDrive 組織層級的共用設定必須允許與組織外部的人員共用。</span><span class="sxs-lookup"><span data-stu-id="188e5-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="188e5-127">SharePoint 的組織層級設定會決定個別 SharePoint 網站可使用的設定。</span><span class="sxs-lookup"><span data-stu-id="188e5-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="188e5-128">網站設定不能超過組織層級設定的許可。</span><span class="sxs-lookup"><span data-stu-id="188e5-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="188e5-129">OneDrive 的組織層級設定會決定使用者 OneDrive 庫中可使用的共用層級。</span><span class="sxs-lookup"><span data-stu-id="188e5-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="188e5-130">若要 SharePoint 和 OneDrive，如果您想要允許未驗證的檔案和資料夾共用，請選擇 [ **任何人**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="188e5-131">若要確定您組織外部的人員必須進行驗證，請選擇 [ **新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="188e5-132">[*任何人*] 連結是最簡單的共用方式：貴組織外部的人員可以在未驗證的情況下開啟連結，而且可以隨意將其傳遞給其他人。</span><span class="sxs-lookup"><span data-stu-id="188e5-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="188e5-133">若為 SharePoint，請選擇您組織中的任何網站所需的功能最寬鬆設定。</span><span class="sxs-lookup"><span data-stu-id="188e5-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="188e5-135">設定 SharePoint 組織層級的共用設定</span><span class="sxs-lookup"><span data-stu-id="188e5-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="188e5-136">在 Microsoft 365 系統管理中心的左功能窗格中，按一下 [系統 **管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="188e5-137">在 [SharePoint 系統管理中心] 的左功能窗格中，按一下 [ **原則**] 底下的 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="188e5-138">確定 SharePoint 或 OneDrive 的外部共用已設定為 **任何人** 或 **新的和現有的客人**。</span><span class="sxs-lookup"><span data-stu-id="188e5-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="188e5-139"> (請注意，OneDrive 設定不能超過 SharePoint 設定的容許數目。 ) </span><span class="sxs-lookup"><span data-stu-id="188e5-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="188e5-140">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="188e5-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="188e5-141">SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="188e5-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="188e5-142">預設的檔案和資料夾連結設定會決定在使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。</span><span class="sxs-lookup"><span data-stu-id="188e5-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="188e5-143">如有需要，使用者可以在共用之前將連結類型變更為其他選項之一。</span><span class="sxs-lookup"><span data-stu-id="188e5-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="188e5-144">請記住，此設定會影響組織中 SharePoint 網站和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="188e5-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="188e5-145">選擇下列任何類型的連結，當使用者共用檔案和資料夾時，預設會選取此連結：</span><span class="sxs-lookup"><span data-stu-id="188e5-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="188e5-146">**任何具有連結的使用者** -如果您想要進行許多未驗證的檔案和資料夾共用，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="188e5-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="188e5-147">如果您想要允許 *任何人* 的連結，但擔心意外的共用驗證，請將其中一個其他選項視為預設值。</span><span class="sxs-lookup"><span data-stu-id="188e5-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="188e5-148">只有在您已啟用 **任何** 共用時，才可使用此連結類型。</span><span class="sxs-lookup"><span data-stu-id="188e5-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="188e5-149">**僅限貴組織中的人員** -如果您預期大多數的檔案和資料夾共用與組織內的人員有關，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="188e5-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="188e5-150">**特定人員** -如果您想要對來賓執行大量檔案和資料夾共用，請考慮此選項。</span><span class="sxs-lookup"><span data-stu-id="188e5-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="188e5-151">這種連結類型與來賓搭配使用，需要驗證。</span><span class="sxs-lookup"><span data-stu-id="188e5-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="188e5-153">設定 SharePoint，並 OneDrive 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="188e5-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="188e5-154">流覽至 SharePoint 系統管理中心的 [共用] 頁面。</span><span class="sxs-lookup"><span data-stu-id="188e5-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="188e5-155">在 [檔案 **和資料夾連結**] 底下，選取您要使用的預設共用連結。</span><span class="sxs-lookup"><span data-stu-id="188e5-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="188e5-156">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="188e5-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="188e5-157">若要設定共用連結的許可權，請在 **[選擇預設為共用連結所選取的許可權**] 底下。</span><span class="sxs-lookup"><span data-stu-id="188e5-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="188e5-158">如果您不想讓未驗證的使用者變更檔案和資料夾，請選取 [View] （ **查看** ）。</span><span class="sxs-lookup"><span data-stu-id="188e5-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="188e5-159">如果您想要允許未驗證的使用者對檔案和資料夾進行變更，請選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="188e5-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="188e5-160">請注意，上述兩個 premission-選項不僅可以套用於來賓/外部使用者，也可以套用至內部使用者。</span><span class="sxs-lookup"><span data-stu-id="188e5-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="188e5-161">您選擇的許可權選項是由自我判斷決定。</span><span class="sxs-lookup"><span data-stu-id="188e5-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="188e5-162">設定允許與任何人共用的連結許可權</span><span class="sxs-lookup"><span data-stu-id="188e5-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="188e5-163">在 [ **這些連結可提供下列許可權：** ] 子窗格中，</span><span class="sxs-lookup"><span data-stu-id="188e5-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="188e5-164">從 [ **檔案** ] 下拉式清單中，</span><span class="sxs-lookup"><span data-stu-id="188e5-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="188e5-165">如果您想要允許未驗證的使用者變更檔案，請選取 [ **查看] 和 [編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="188e5-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="188e5-166">如果您不想讓未驗證的使用者變更檔，請選取 [View] （ **查看** ）。</span><span class="sxs-lookup"><span data-stu-id="188e5-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="188e5-167">從 [ **資料夾** ] 下拉式清單中，</span><span class="sxs-lookup"><span data-stu-id="188e5-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="188e5-168">如果您想要允許未驗證的使用者對資料夾進行變更，請選取 **[查看]、[編輯] 及 [上傳** ]。</span><span class="sxs-lookup"><span data-stu-id="188e5-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="188e5-169">如果您不想讓未驗證的使用者對資料夾進行變更，請選取 [View] （ **查看** ）。</span><span class="sxs-lookup"><span data-stu-id="188e5-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="188e5-170">SharePoint 網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="188e5-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="188e5-171">如果您要共用 SharePoint 網站中的檔案與資料夾，您也需要檢查該網站的網站層級共用設定。</span><span class="sxs-lookup"><span data-stu-id="188e5-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="188e5-173">設定網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="188e5-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="188e5-174">在 SharePoint 系統管理中心的左功能窗格中，展開 [ **網站** ]，然後按一下 [作用中的 **網站**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="188e5-175">選取您要與來賓共用檔案和資料夾的網站。</span><span class="sxs-lookup"><span data-stu-id="188e5-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="188e5-176">向右滾動選取的網站所在的列 () 然後按一下 [ **外部共用** ] 欄中的任何地方。</span><span class="sxs-lookup"><span data-stu-id="188e5-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="188e5-177">在彈出的頁面上，按一下 [ **原則** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="188e5-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="188e5-178">在 [ **外部共用** ] 窗格中，按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="188e5-179">確定 [共用] 設定為 [ **任何人** ] 或 [ **現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="188e5-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="188e5-180">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="188e5-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="188e5-181">邀請使用者</span><span class="sxs-lookup"><span data-stu-id="188e5-181">Invite users</span></span>

<span data-ttu-id="188e5-182">現在已設定來賓共用設定;所以使用者現在可以與組織外部的人員共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="188e5-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="188e5-183">如需詳細資訊，請參閱 [共用 OneDrive 檔案和資料夾](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 及 [共用 SharePoint 檔案或資料夾](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 。</span><span class="sxs-lookup"><span data-stu-id="188e5-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="188e5-184">另請參閱</span><span class="sxs-lookup"><span data-stu-id="188e5-184">See also</span></span>

[<span data-ttu-id="188e5-185">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="188e5-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="188e5-186">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="188e5-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="188e5-187">與 Azure AD B2B 的 SharePoint 和 OneDrive 整合</span><span class="sxs-lookup"><span data-stu-id="188e5-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
