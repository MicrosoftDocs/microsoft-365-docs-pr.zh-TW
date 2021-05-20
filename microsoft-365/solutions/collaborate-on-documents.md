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
recommendations: false
description: 在本文中，您將瞭解如何在 SharePoint 和 OneDrive 的檔中與客人共同作業。
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537832"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="fef73-103">在文件上與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="fef73-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="fef73-104">如果您需要與組織外部的人員共同作業 SharePoint 或 OneDrive 中的檔，您可以將檔的共用連結傳送給他們。</span><span class="sxs-lookup"><span data-stu-id="fef73-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="fef73-105">在本文中，我們將逐步完成必要的 Microsoft 365 設定步驟，為您的組織的需求設定 SharePoint 和 OneDrive 的共用連結。</span><span class="sxs-lookup"><span data-stu-id="fef73-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="fef73-106">影片示範</span><span class="sxs-lookup"><span data-stu-id="fef73-106">Video demonstration</span></span>

<span data-ttu-id="fef73-107">這段影片顯示本文件中所述的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="fef73-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="fef73-108">Azure 外部協同作業設定</span><span class="sxs-lookup"><span data-stu-id="fef73-108">Azure external collaboration settings</span></span>

<span data-ttu-id="fef73-109">Microsoft 365 中的共用是由 [Azure Active Directory 中 B2B 外部共同作業設定](/azure/active-directory/external-identities/delegate-invitations) 的最高層級所控管。</span><span class="sxs-lookup"><span data-stu-id="fef73-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="fef73-110">如果 Azure AD 中已停用或限制來賓共用，此設定會覆寫您在 Microsoft 365 中設定的任何共用設定。</span><span class="sxs-lookup"><span data-stu-id="fef73-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="fef73-111">檢查 B2B 的外部共同作業設定，以確保不會封鎖與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="fef73-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="fef73-113">設定外部共同作業設定</span><span class="sxs-lookup"><span data-stu-id="fef73-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="fef73-114">登入 Azure Active Directory，網址為：[https://aad.portal.azure.com](https://aad.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="fef73-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="fef73-115">在左側瀏覽窗格中，按一下 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="fef73-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="fef73-116">按一下 **外部身分識別**。</span><span class="sxs-lookup"><span data-stu-id="fef73-116">Click **External identities**.</span></span>
4. <span data-ttu-id="fef73-117">在左側瀏覽窗格的 **開始** 畫面中，按一下 **外部共同作業設定**。</span><span class="sxs-lookup"><span data-stu-id="fef73-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="fef73-118">請確保 **系統管理員和來賓邀請者角色中的使用者可邀請** 及 **成員可邀請** 都設定為 **是**。</span><span class="sxs-lookup"><span data-stu-id="fef73-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="fef73-119">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="fef73-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="fef73-120">記下 **共同作業限制** 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="fef73-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="fef73-121">請確定您想要共同作業之來賓的網域未封鎖。</span><span class="sxs-lookup"><span data-stu-id="fef73-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="fef73-122">如果您與多個組織的來賓合作，建議您限制他們存取目錄資料的能力。</span><span class="sxs-lookup"><span data-stu-id="fef73-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="fef73-123">這可防止他們查看目錄中還有誰是來賓。</span><span class="sxs-lookup"><span data-stu-id="fef73-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="fef73-124">若要執行這項操作，請在 **來賓使用者存取限制** 下，選取 **來賓使用者對屬性及目錄物件設定的成員資格存取受限** 或 **來賓使用者存取受限於他們自己的目錄物件的屬性及成員資格**。</span><span class="sxs-lookup"><span data-stu-id="fef73-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="fef73-125">SharePoint 組織層級的共用設定</span><span class="sxs-lookup"><span data-stu-id="fef73-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="fef73-126">為了讓組織外部人員能夠存取 SharePoint 或 OneDrive 中的檔，SharePoint 和 OneDrive 組織層級的共用設定必須允許與組織外部的人員共用。</span><span class="sxs-lookup"><span data-stu-id="fef73-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="fef73-127">SharePoint 的組織層級設定會決定個別 SharePoint 網站可使用的設定。</span><span class="sxs-lookup"><span data-stu-id="fef73-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="fef73-128">網站設定不能比組織層級設定更寬鬆。</span><span class="sxs-lookup"><span data-stu-id="fef73-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="fef73-129">OneDrive 的組織層級設定會決定使用者 OneDrive 庫中可使用的共用層級。</span><span class="sxs-lookup"><span data-stu-id="fef73-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="fef73-130">若要 SharePoint 和 OneDrive，如果您想要允許未驗證的檔案和資料夾共用，請選擇 [**任何人**]。</span><span class="sxs-lookup"><span data-stu-id="fef73-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="fef73-131">若要確定您組織外部的人員必須進行驗證，請選擇 [ **新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="fef73-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="fef73-132">[*任何人*] 連結是最簡單的共用方式：貴組織外部的人員可以在未驗證的情況下開啟連結，而且可以隨意將其傳遞給其他人。</span><span class="sxs-lookup"><span data-stu-id="fef73-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="fef73-133">若為 SharePoint，請選擇您組織中的任何網站所需的功能最寬鬆設定。</span><span class="sxs-lookup"><span data-stu-id="fef73-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="fef73-135">設定 SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="fef73-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="fef73-136">在 Microsoft 365 系統管理中心的左側瀏覽窗格中，在 **系統管理中心** 下，按一下 **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="fef73-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="fef73-137">在 [SharePoint 系統管理中心] 的左功能窗格中，按一下 [**原則**] 底下的 [**共用**]。</span><span class="sxs-lookup"><span data-stu-id="fef73-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="fef73-138">確定 SharePoint 或 OneDrive 的外部共用已設定為 **任何人** 或 **新的和現有的客人**。</span><span class="sxs-lookup"><span data-stu-id="fef73-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="fef73-139"> (請注意，OneDrive 設定不能超過 SharePoint 設定的容許數目。 ) </span><span class="sxs-lookup"><span data-stu-id="fef73-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="fef73-140">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="fef73-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="fef73-141">SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="fef73-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="fef73-142">預設檔案和資料夾連結設定會決定當使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。</span><span class="sxs-lookup"><span data-stu-id="fef73-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="fef73-143">如有需要，使用者可以在共用前，將連結類型變更為其中一個其他選項。</span><span class="sxs-lookup"><span data-stu-id="fef73-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="fef73-144">請記住，此設定會影響組織中 SharePoint 網站和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="fef73-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="fef73-145">選擇下列任何類型的連結，當使用者共用檔案和資料夾時，預設會選取此連結：</span><span class="sxs-lookup"><span data-stu-id="fef73-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="fef73-146">**任何具有連結的使用者** -如果您想要進行許多未驗證的檔案和資料夾共用，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="fef73-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="fef73-147">如果您想要允許 *任何人* 連結，但擔心意外的未驗證共用，請考慮將其中一個其他選項設為預設值。</span><span class="sxs-lookup"><span data-stu-id="fef73-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="fef73-148">此連結類型只有在您已啟用 **任何人** 共用時才能使用。</span><span class="sxs-lookup"><span data-stu-id="fef73-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="fef73-149">**只有貴組織中的人員** - 如果您預期大部分檔案和資料夾共用都是與組織內部人員共用，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="fef73-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="fef73-150">**特定人員** - 如果您預期要與來賓共用許多檔案和資料夾，請考慮使用此選項。</span><span class="sxs-lookup"><span data-stu-id="fef73-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="fef73-151">這種類型的連結適用於來賓，且需要他們進行驗證。</span><span class="sxs-lookup"><span data-stu-id="fef73-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="fef73-153">設定 SharePoint，並 OneDrive 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="fef73-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="fef73-154">瀏覽至 SharePoint 系統管理中心的共用頁面。</span><span class="sxs-lookup"><span data-stu-id="fef73-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="fef73-155">在 **檔案與資料夾連結** 下，選取您想要使用的預設共用連結。</span><span class="sxs-lookup"><span data-stu-id="fef73-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="fef73-156">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="fef73-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="fef73-157">若要設定共用連結的許可權，請在 **[選擇預設為共用連結所選取的許可權**] 底下。</span><span class="sxs-lookup"><span data-stu-id="fef73-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="fef73-158">如果您不想讓未驗證的使用者變更檔案和資料夾，請選取 [View] （ **查看** ）。</span><span class="sxs-lookup"><span data-stu-id="fef73-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="fef73-159">如果您想要允許未驗證的使用者對檔案和資料夾進行變更，請選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="fef73-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="fef73-160">請注意，上述兩個 premission-選項不僅可以套用於來賓/外部使用者，也可以套用至內部使用者。</span><span class="sxs-lookup"><span data-stu-id="fef73-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="fef73-161">您選擇的許可權選項是由自我判斷決定。</span><span class="sxs-lookup"><span data-stu-id="fef73-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="fef73-162">設定允許與任何人共用的連結許可權</span><span class="sxs-lookup"><span data-stu-id="fef73-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="fef73-163">在 [ **這些連結可提供下列許可權：** ] 子窗格中，</span><span class="sxs-lookup"><span data-stu-id="fef73-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="fef73-164">從 [ **檔案** ] 下拉式清單中，</span><span class="sxs-lookup"><span data-stu-id="fef73-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="fef73-165">如果您想要允許未驗證的使用者變更檔案，請選取 [ **查看] 和 [編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="fef73-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="fef73-166">如果您不想讓未驗證的使用者變更檔，請選取 [View] （ **查看** ）。</span><span class="sxs-lookup"><span data-stu-id="fef73-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="fef73-167">從 [ **資料夾** ] 下拉式清單中，</span><span class="sxs-lookup"><span data-stu-id="fef73-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="fef73-168">如果您想要允許未驗證的使用者對資料夾進行變更，請選取 **[查看]、[編輯] 及 [上傳** ]。</span><span class="sxs-lookup"><span data-stu-id="fef73-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="fef73-169">如果您不想讓未驗證的使用者對資料夾進行變更，請選取 [View] （ **查看** ）。</span><span class="sxs-lookup"><span data-stu-id="fef73-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="fef73-170">SharePoint 網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="fef73-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="fef73-171">如果您要共用 SharePoint 網站中的檔案與資料夾，您也需要檢查該網站的網站層級共用設定。</span><span class="sxs-lookup"><span data-stu-id="fef73-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="fef73-173">設定網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="fef73-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="fef73-174">在 SharePoint 管理中心中，在左側導覽窗格中展開 **網站**，然後按一下 **使用中網站**。</span><span class="sxs-lookup"><span data-stu-id="fef73-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="fef73-175">選取您要與來賓共用檔案和資料夾的網站。</span><span class="sxs-lookup"><span data-stu-id="fef73-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="fef73-176">向右滾動選取的網站所在的列 () 然後按一下 [ **外部共用** ] 欄中的任何地方。</span><span class="sxs-lookup"><span data-stu-id="fef73-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="fef73-177">在彈出的頁面上，按一下 [ **原則** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fef73-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="fef73-178">在 [ **外部共用** ] 窗格中，按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="fef73-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="fef73-179">請確認共用設為 **任何人** 或 **新的及現有的來賓**。</span><span class="sxs-lookup"><span data-stu-id="fef73-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="fef73-180">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="fef73-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="fef73-181">邀請使用者</span><span class="sxs-lookup"><span data-stu-id="fef73-181">Invite users</span></span>

<span data-ttu-id="fef73-182">現在已設定來賓共用設定;所以使用者現在可以與組織外部的人員共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="fef73-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="fef73-183">如需詳細資訊，請參閱[共用 OneDrive 檔案和資料夾](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07)及[共用 SharePoint 檔案或資料夾](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)。</span><span class="sxs-lookup"><span data-stu-id="fef73-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="fef73-184">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fef73-184">See also</span></span>

[<span data-ttu-id="fef73-185">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="fef73-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="fef73-186">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="fef73-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="fef73-187">SharePoint 和 OneDrive 與 Azure AD B2B 整合</span><span class="sxs-lookup"><span data-stu-id="fef73-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)