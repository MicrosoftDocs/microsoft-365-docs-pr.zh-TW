---
title: 在網站中與來賓共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: 瞭解如何與 SharePoint 網站中的客人共同作業。
ms.openlocfilehash: 5a8bc5da55f3582a7e298dab97ec4d6b3d147b60
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630734"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="21de4-103">在網站中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="21de4-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="21de4-104">如果您需要跨檔、資料和清單共同處理來賓，您可以使用 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="21de4-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="21de4-105">新式 SharePoint 網站會連線至 Microsoft 365 群組，並可管理網站成員資格，並提供其他共同作業工具，例如共用信箱和行事曆。</span><span class="sxs-lookup"><span data-stu-id="21de4-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="21de4-106">在本文中，我們將逐步完成設定 SharePoint 網站與來賓共同作業所需的 Microsoft 365 設定步驟。</span><span class="sxs-lookup"><span data-stu-id="21de4-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="21de4-107">影片示範</span><span class="sxs-lookup"><span data-stu-id="21de4-107">Video demonstration</span></span>

<span data-ttu-id="21de4-108">這段影片顯示本檔所述的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="21de4-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="21de4-109">Azure 組織關聯性設定</span><span class="sxs-lookup"><span data-stu-id="21de4-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="21de4-110">Microsoft 365 中的共用可透過 Azure Active Directory 中的組織關聯設定受到最高層級的制約。</span><span class="sxs-lookup"><span data-stu-id="21de4-110">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="21de4-111">如果 Azure AD 中已停用來賓共用或已限制來賓共用，這會覆寫您在 Microsoft 365 中設定的任何共用設定。</span><span class="sxs-lookup"><span data-stu-id="21de4-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="21de4-112">檢查 [組織關聯] 設定，以確保未封鎖與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="21de4-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="21de4-114">設定組織關聯設定</span><span class="sxs-lookup"><span data-stu-id="21de4-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="21de4-115">登入 Microsoft Azure，網址[https://portal.azure.com](https://portal.azure.com)為。</span><span class="sxs-lookup"><span data-stu-id="21de4-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="21de4-116">在左側導覽中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="21de4-117">在 [**一覽表**] 窗格中，按一下 [**組織關聯**性]。</span><span class="sxs-lookup"><span data-stu-id="21de4-117">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="21de4-118">在 [**組織關聯**] 窗格中，按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-118">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="21de4-119">確定**guest 和 guest inviter role 中的系統管理員和使用者都可以邀請**和**成員可以邀請**皆設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="21de4-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="21de4-120">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="21de4-121">請記下 [**協同限制**] 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="21de4-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="21de4-122">確定您要與之來賓進行共同作業的網域不會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="21de4-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="21de4-123">Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="21de4-123">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="21de4-124">新式 SharePoint 網站使用 Microsoft 365 群組來控制網站存取。</span><span class="sxs-lookup"><span data-stu-id="21de4-124">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="21de4-125">為了讓 SharePoint 網站中的來賓存取能夠運作，必須開啟 Microsoft 365 群組來賓設定。</span><span class="sxs-lookup"><span data-stu-id="21de4-125">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 admin center 中 Microsoft 365 群組來賓設定的螢幕擷取畫面](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="21de4-127">設定 Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="21de4-127">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="21de4-128">在 Microsoft 365 系統管理中心的左側流覽窗格中，展開 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-128">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="21de4-129">按一下 [**服務] & 增益集**。</span><span class="sxs-lookup"><span data-stu-id="21de4-129">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="21de4-130">在清單中，按一下 [ **Microsoft 365 群組**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-130">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="21de4-131">確定 [**讓組織外部的成員存取群組內容**] 和 [**允許群組擁有者將組織外部人員新增至群組**] 核取方塊皆已勾選。</span><span class="sxs-lookup"><span data-stu-id="21de4-131">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="21de4-132">如果您進行變更，請按一下 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-132">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="21de4-133">SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="21de4-133">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="21de4-134">為了讓來賓能夠存取 SharePoint 網站，SharePoint 組織層級的共用設定必須允許與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="21de4-134">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="21de4-135">組織層級設定會決定個別網站可使用的設定。</span><span class="sxs-lookup"><span data-stu-id="21de4-135">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="21de4-136">網站設定不能超過組織層級設定的許可。</span><span class="sxs-lookup"><span data-stu-id="21de4-136">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="21de4-137">如果您想要允許未驗證的檔案和資料夾共用，請選擇 [**任何人**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-137">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="21de4-138">若要確定您組織外部的人員必須進行驗證，請選擇 [**新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-138">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="21de4-139">選擇您的組織中的任何網站所需的功能最寬鬆設定。</span><span class="sxs-lookup"><span data-stu-id="21de4-139">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="21de4-141">設定 SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="21de4-141">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="21de4-142">在 Microsoft 365 系統管理中心的左側導覽中，按一下 [系統**管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-142">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="21de4-143">在 SharePoint 管理中心中，按一下左側導覽窗格中的 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-143">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="21de4-144">確定 SharePoint 的外部共用已設定為**任何人**或**新的和現有的客人**。</span><span class="sxs-lookup"><span data-stu-id="21de4-144">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="21de4-145">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-145">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="21de4-146">建立網站</span><span class="sxs-lookup"><span data-stu-id="21de4-146">Create a site</span></span>

<span data-ttu-id="21de4-147">下一步是建立您計畫用以與來賓合作的網站。</span><span class="sxs-lookup"><span data-stu-id="21de4-147">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="21de4-148">若要建立網站</span><span class="sxs-lookup"><span data-stu-id="21de4-148">To create a site</span></span>
1. <span data-ttu-id="21de4-149">在 SharePoint 系統管理中心的 **[網站]** 底下，按一下 **[使用中網站]**。</span><span class="sxs-lookup"><span data-stu-id="21de4-149">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="21de4-150">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="21de4-150">Click **Create**.</span></span>
3. <span data-ttu-id="21de4-151">按一下 [**小組網站**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-151">Click **Team site**.</span></span>
4. <span data-ttu-id="21de4-152">輸入網站名稱，並為群組擁有者（網站擁有者）輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="21de4-152">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="21de4-153">在 [**高級設定**] 底下，選擇您要讓它成為公用或私人網站。</span><span class="sxs-lookup"><span data-stu-id="21de4-153">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="21de4-154">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-154">Click **Next**.</span></span>
7. <span data-ttu-id="21de4-155">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="21de4-155">Click **Finish**.</span></span>

<span data-ttu-id="21de4-156">我們稍後會邀請使用者。</span><span class="sxs-lookup"><span data-stu-id="21de4-156">We'll invite users later.</span></span> <span data-ttu-id="21de4-157">接下來，請務必檢查此網站的網站層級共用設定。</span><span class="sxs-lookup"><span data-stu-id="21de4-157">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="21de4-158">網站層級共用設定 SharePoint</span><span class="sxs-lookup"><span data-stu-id="21de4-158">SharePoint site level sharing settings</span></span>

<span data-ttu-id="21de4-159">請檢查網站層級的共用設定，以確定其允許您要用於此網站的訪問類型。</span><span class="sxs-lookup"><span data-stu-id="21de4-159">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="21de4-160">例如，如果您將組織層級設定設定為 [**任何人**]，但您希望所有來賓都對此網站進行驗證，請確定網站層級共用設定已設定為 [**新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-160">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="21de4-161">請注意，網站無法與未驗證的人員（**任何人**設定）共用，但是個別的檔案和資料夾可以。</span><span class="sxs-lookup"><span data-stu-id="21de4-161">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="21de4-163">設定網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="21de4-163">To set site-level sharing settings</span></span>
1. <span data-ttu-id="21de4-164">在 SharePoint 管理中心中，在左側導覽窗格中展開 [網站]\*\*\*\*，然後按一下 [使用中網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-164">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="21de4-165">選取您剛建立的網站。</span><span class="sxs-lookup"><span data-stu-id="21de4-165">Select the site that you just created.</span></span>
3. <span data-ttu-id="21de4-166">在功能區中，按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-166">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="21de4-167">確定 [共用] 設定為 [**任何人**] 或 [**現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-167">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="21de4-168">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-168">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="21de4-169">邀請使用者</span><span class="sxs-lookup"><span data-stu-id="21de4-169">Invite users</span></span>

<span data-ttu-id="21de4-170">現在已設定來賓共用設定，因此您可以開始將內部使用者和來賓新增至您的網站。</span><span class="sxs-lookup"><span data-stu-id="21de4-170">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="21de4-171">網站存取是透過相關的 Microsoft 365 群組來控制，因此我們將會在那裡新增使用者。</span><span class="sxs-lookup"><span data-stu-id="21de4-171">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="21de4-172">邀請內部使用者加入群組</span><span class="sxs-lookup"><span data-stu-id="21de4-172">To invite internal users to a group</span></span>
1. <span data-ttu-id="21de4-173">流覽至您要新增使用者的網站。</span><span class="sxs-lookup"><span data-stu-id="21de4-173">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="21de4-174">按一下右上角的 [**成員**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-174">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="21de4-175">按一下 [新增成員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-175">Click **Add members**.</span></span>
4. <span data-ttu-id="21de4-176">輸入您要邀請加入網站之使用者的名稱或電子郵件地址，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-176">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="21de4-177">無法從網站新增來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="21de4-177">Guest users can't be added from the site.</span></span> <span data-ttu-id="21de4-178">您必須使用 Outlook 網頁版來新增這些檔案。</span><span class="sxs-lookup"><span data-stu-id="21de4-178">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="21de4-179">若要邀請客人加入群組</span><span class="sxs-lookup"><span data-stu-id="21de4-179">To invite guests to a group</span></span>
1. <span data-ttu-id="21de4-180">在網頁版的 Outlook 中的 [**群組**] 下，按一下您要新增成員的群組。</span><span class="sxs-lookup"><span data-stu-id="21de4-180">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="21de4-181">開啟群組連絡人卡片，然後在 [**其他選項**] （[...]）下，按一下 [**新增成員**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-181">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="21de4-182">輸入您要邀請之來賓的電子郵件地址，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="21de4-182">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="21de4-183">按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21de4-183">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="21de4-184">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21de4-184">See Also</span></span>

[<span data-ttu-id="21de4-185">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="21de4-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="21de4-186">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="21de4-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="21de4-187">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="21de4-187">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="21de4-188">使用受管理來賓建立 B2B 外部網路</span><span class="sxs-lookup"><span data-stu-id="21de4-188">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

