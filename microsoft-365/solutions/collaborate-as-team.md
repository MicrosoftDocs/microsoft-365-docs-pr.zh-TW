---
title: 在團隊中與來賓共同作業
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
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 了解所需的 Microsoft 365 設定步驟，以在 Teams 中成立團隊並與來賓進行工作、交談和文件共同作業。
ms.openlocfilehash: c17732705c1d88ff70e56f5d26d9e268e3ff7c19
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539260"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="0129b-103">在團隊中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="0129b-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="0129b-104">如果您需要跨文件、工作及交談與來賓共同作業，建議您使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0129b-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="0129b-105">Teams 提供 Office 和 SharePoint 中具備的所有共同作業功能，搭配持續聊天及一組可自訂且可擴展的共同作業工具，進而提供一致的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0129b-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="0129b-106">在本文中，我們會完成所需的 Microsoft 365 設定步驟，以成立團隊並與來賓進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="0129b-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="0129b-107">設定來賓存取權後，您可以遵循 [在 Teams 中新增來賓至團隊](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f) 的步驟來邀請來賓加入團隊。</span><span class="sxs-lookup"><span data-stu-id="0129b-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="0129b-108">影片示範</span><span class="sxs-lookup"><span data-stu-id="0129b-108">Video demonstration</span></span>

<span data-ttu-id="0129b-109">這段影片顯示本文件中所述的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="0129b-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="0129b-110">Azure 外部共同作業設定</span><span class="sxs-lookup"><span data-stu-id="0129b-110">Azure External collaboration settings</span></span>

<span data-ttu-id="0129b-111">Microsoft 365 中的共用是由 [Azure Active Directory 中 B2B 外部共同作業設定](/azure/active-directory/external-identities/delegate-invitations) 的最高層級所控管。</span><span class="sxs-lookup"><span data-stu-id="0129b-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="0129b-112">如果在 Azure AD 中停用或限制來賓共用，此設定會覆寫您於 Microsoft 365 中設定的任何共用設定。</span><span class="sxs-lookup"><span data-stu-id="0129b-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="0129b-113">檢查 B2B 外部共同作業設定，以確保不會封鎖與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="0129b-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="0129b-115">設定外部共同作業設定</span><span class="sxs-lookup"><span data-stu-id="0129b-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="0129b-116">登入 Azure Active Directory，網址為：[https://aad.portal.azure.com](https://aad.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="0129b-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="0129b-117">在左側瀏覽窗格中，按一下 **Azure Active Directory**。</span><span class="sxs-lookup"><span data-stu-id="0129b-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0129b-118">按一下 **外部身分識別**。</span><span class="sxs-lookup"><span data-stu-id="0129b-118">Click **External identities**.</span></span>
4. <span data-ttu-id="0129b-119">在左側瀏覽窗格的 **開始** 畫面中，按一下 **外部共同作業設定**。</span><span class="sxs-lookup"><span data-stu-id="0129b-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="0129b-120">請確保 **系統管理員和來賓邀請者角色中的使用者可邀請** 及 **成員可邀請** 都設定為 **是**。</span><span class="sxs-lookup"><span data-stu-id="0129b-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="0129b-121">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="0129b-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="0129b-122">記下 **共同作業限制** 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="0129b-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="0129b-123">請確定您想要共同作業之來賓的網域未封鎖。</span><span class="sxs-lookup"><span data-stu-id="0129b-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="0129b-124">如果您與多個組織的來賓合作，建議您限制他們存取目錄資料的能力。</span><span class="sxs-lookup"><span data-stu-id="0129b-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="0129b-125">這可防止他們查看目錄中還有誰是來賓。</span><span class="sxs-lookup"><span data-stu-id="0129b-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="0129b-126">若要執行這項操作，請在 **來賓使用者存取限制** 下，選取 **來賓使用者對屬性及目錄物件設定的成員資格存取受限** 或 **來賓使用者存取受限於他們自己的目錄物件的屬性及成員資格**。</span><span class="sxs-lookup"><span data-stu-id="0129b-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="0129b-127">Teams 來賓存取設定</span><span class="sxs-lookup"><span data-stu-id="0129b-127">Teams guest access settings</span></span>

<span data-ttu-id="0129b-128">Teams 具備來賓存取的主開啟/關閉開關，以及各種設定，可用於控制來賓可在團隊中執行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="0129b-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="0129b-129">主開關 **在 Teams 中允許來賓存取** 必須為 **開啟** ，來賓才有存取權在 Teams 中工作。</span><span class="sxs-lookup"><span data-stu-id="0129b-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="0129b-p107">檢查並確保 Teams 中已啟用來賓存取，並根據您的業務需求調整來賓設定。請記住，這些設定會影響所有團隊。</span><span class="sxs-lookup"><span data-stu-id="0129b-p107">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs. Keep in mind that these settings affect all teams.</span></span>

![Teams 來賓存取切換的螢幕擷取畫面](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="0129b-133">設定 Teams 來賓存取設定</span><span class="sxs-lookup"><span data-stu-id="0129b-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="0129b-134">登入 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="0129b-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="0129b-135">在左側瀏覽窗格中，按一下 **顯示全部**。</span><span class="sxs-lookup"><span data-stu-id="0129b-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="0129b-136">在 **系統管理中心** 下，按一下 **Teams**。</span><span class="sxs-lookup"><span data-stu-id="0129b-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="0129b-137">在 Teams 系統管理中心的左側瀏覽窗格中展開 **全組織設定**，然後按一下 **來賓存取**。</span><span class="sxs-lookup"><span data-stu-id="0129b-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="0129b-138">確定 [在 Teams 中允許來賓存取] 已設定為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="0129b-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="0129b-139">對其他來賓設定進行所需的變更，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0129b-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="0129b-140">開啟 Teams 來賓存取後，您可以選擇性地使用敏感度標籤，以控制個別團隊及其相關聯 SharePoint 網站的來賓存取。</span><span class="sxs-lookup"><span data-stu-id="0129b-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="0129b-141">如需詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="0129b-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0129b-142">Teams 來賓設定在開啟後，最慢可能需要 24 小時才會生效。</span><span class="sxs-lookup"><span data-stu-id="0129b-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="0129b-143">Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="0129b-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="0129b-p109">Teams 使用 Microsoft 365 群組作為團隊成員資格。必須開啟 Microsoft 365 群組來賓設定，才能使用 Teams 中的來賓存取。</span><span class="sxs-lookup"><span data-stu-id="0129b-p109">Teams uses Microsoft 365 Groups for team membership. The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 系統管理中心的 Microsoft 365 群組來賓設定螢幕擷取畫面](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="0129b-147">設定 Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="0129b-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="0129b-148">在 Microsoft 365 系統管理中心左側的瀏覽窗格中，展開 **設定**。</span><span class="sxs-lookup"><span data-stu-id="0129b-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="0129b-149">按一下 **組織設定**。</span><span class="sxs-lookup"><span data-stu-id="0129b-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="0129b-150">在清單中，按一下 **Microsoft 365 群組**。</span><span class="sxs-lookup"><span data-stu-id="0129b-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="0129b-151">請確認已核取 **讓群組擁有者將組織外部人員新增到 Microsoft 365 群組作為來賓** 及 **讓來賓群組成員存取群組內容** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0129b-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="0129b-152">如果您做了任何變更，請按一下 **儲存變更**。</span><span class="sxs-lookup"><span data-stu-id="0129b-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="0129b-153">SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0129b-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="0129b-154">Teams 內容 (例如檔案、資料夾和清單) 全部都儲存在 SharePoint 中。</span><span class="sxs-lookup"><span data-stu-id="0129b-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="0129b-155">為了讓來賓能夠存取 Teams 中的這些專案，SharePoint 組織層級共用設定必須允許與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="0129b-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="0129b-156">組織層級設定會決定個別網站可用的設定，包括與團隊相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="0129b-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="0129b-157">網站設定不能比組織層級設定更寬鬆。</span><span class="sxs-lookup"><span data-stu-id="0129b-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="0129b-158">如果您想要允許與未驗證人員共用檔案和資料夾，請選擇 **任何人**。</span><span class="sxs-lookup"><span data-stu-id="0129b-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="0129b-159">如果您想要確保所有來賓都經過驗證，請選擇 **新的及現有的來賓**。</span><span class="sxs-lookup"><span data-stu-id="0129b-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="0129b-160">選擇組織中任何網站所需的最寬鬆設定。</span><span class="sxs-lookup"><span data-stu-id="0129b-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="0129b-162">設定 SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0129b-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="0129b-163">在 Microsoft 365 系統管理中心的左側瀏覽窗格中，在 **系統管理中心** 下，按一下 **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="0129b-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="0129b-164">在 SharePoint 系統管理中心的左側瀏覽窗格中，展開 **原則** ，然後按一下 **共用**。</span><span class="sxs-lookup"><span data-stu-id="0129b-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="0129b-165">確定 SharePoint 的外部共用已設定為 **任何人** 或 **新的及現有的來賓**。</span><span class="sxs-lookup"><span data-stu-id="0129b-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="0129b-166">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="0129b-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="0129b-167">SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="0129b-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="0129b-168">預設檔案和資料夾連結設定會決定當使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。</span><span class="sxs-lookup"><span data-stu-id="0129b-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="0129b-169">如有需要，使用者可以在共用前，將連結類型變更為其中一個其他選項。</span><span class="sxs-lookup"><span data-stu-id="0129b-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="0129b-170">請記住，此設定會影響貴組織的所有團隊和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="0129b-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="0129b-171">選擇下列任一連結類型，使用者共用檔案和資料夾時，預設會加以選取：</span><span class="sxs-lookup"><span data-stu-id="0129b-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="0129b-172">**擁有連結的任何人** - 如果您預期要共用許多未經驗證的檔案和資料夾，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="0129b-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="0129b-173">如果您想要允許 *任何人* 連結，但擔心意外的未驗證共用，請考慮將其中一個其他選項設為預設值。</span><span class="sxs-lookup"><span data-stu-id="0129b-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="0129b-174">此連結類型只有在您已啟用 **任何人** 共用時才能使用。</span><span class="sxs-lookup"><span data-stu-id="0129b-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="0129b-175">**只有貴組織中的人員** - 如果您預期大部分檔案和資料夾共用都是與組織內部人員共用，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="0129b-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="0129b-176">**特定人員** - 如果您預期要與來賓共用許多檔案和資料夾，請考慮使用此選項。</span><span class="sxs-lookup"><span data-stu-id="0129b-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="0129b-177">這種類型的連結適用於來賓，且需要他們進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0129b-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="0129b-179">設定 SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="0129b-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="0129b-180">瀏覽至 SharePoint 系統管理中心的共用頁面。</span><span class="sxs-lookup"><span data-stu-id="0129b-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="0129b-181">在 **檔案與資料夾連結** 下，選取您想要使用的預設共用連結。</span><span class="sxs-lookup"><span data-stu-id="0129b-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="0129b-182">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="0129b-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="0129b-183">建立團隊</span><span class="sxs-lookup"><span data-stu-id="0129b-183">Create a team</span></span>

<span data-ttu-id="0129b-184">下一個步驟是建立您計畫用於與來賓共同作業的團隊。</span><span class="sxs-lookup"><span data-stu-id="0129b-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="0129b-185">建立團隊</span><span class="sxs-lookup"><span data-stu-id="0129b-185">To create a team</span></span>
1. <span data-ttu-id="0129b-186">在 Teams 中，於 **Teams** 索引標籤左窗格底部按一下 **加入或建立團隊**。</span><span class="sxs-lookup"><span data-stu-id="0129b-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="0129b-187">按一下 **建立團隊**。</span><span class="sxs-lookup"><span data-stu-id="0129b-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="0129b-188">按一下 **從頭建立團隊**。</span><span class="sxs-lookup"><span data-stu-id="0129b-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="0129b-189">選擇 **私人** 或 **公用**。</span><span class="sxs-lookup"><span data-stu-id="0129b-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="0129b-190">輸入團隊的名稱和描述，然後按一下 **建立**。</span><span class="sxs-lookup"><span data-stu-id="0129b-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="0129b-191">按一下 **略過**。</span><span class="sxs-lookup"><span data-stu-id="0129b-191">Click **Skip**.</span></span>

<span data-ttu-id="0129b-p116">我們稍後會邀請使用者。接下來，檢查與團隊相關聯之 SharePoint 網站的網站層級共用設定，這點非常重要。</span><span class="sxs-lookup"><span data-stu-id="0129b-p116">We'll invite users later. Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="0129b-194">SharePoint 網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0129b-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="0129b-195">檢查網站層級共用設定，確定它們允許你所要的此團隊存取類型。</span><span class="sxs-lookup"><span data-stu-id="0129b-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="0129b-196">例如，如果您將組織層級設定設為 **任何人**，但您希望所有來賓都為此團隊進行驗證，則請確定網站層級共用設定已設為 **新的及現有的來賓**。</span><span class="sxs-lookup"><span data-stu-id="0129b-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="0129b-198">設定網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0129b-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="0129b-199">在 SharePoint 管理中心中，在左側導覽窗格中展開 **網站**，然後按一下 **使用中網站**。</span><span class="sxs-lookup"><span data-stu-id="0129b-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="0129b-200">為您剛建立的團隊選取網站。</span><span class="sxs-lookup"><span data-stu-id="0129b-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="0129b-201">按一下 [...] 然後選擇 **共用**。</span><span class="sxs-lookup"><span data-stu-id="0129b-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="0129b-202">請確認共用設為 **任何人** 或 **新的及現有的來賓**。</span><span class="sxs-lookup"><span data-stu-id="0129b-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="0129b-203">如果您做了任何變更，請按一下 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="0129b-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="0129b-204">邀請使用者</span><span class="sxs-lookup"><span data-stu-id="0129b-204">Invite users</span></span>

<span data-ttu-id="0129b-205">來賓共用設定現已設定，因此您可以開始將內部使用者和來賓新增到您的團隊。</span><span class="sxs-lookup"><span data-stu-id="0129b-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="0129b-206">邀請內部使用者加入團隊</span><span class="sxs-lookup"><span data-stu-id="0129b-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="0129b-207">在該團隊中，按一下 **更多選項** (**\*\*\***)，然後按一下 **新增成員**。</span><span class="sxs-lookup"><span data-stu-id="0129b-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="0129b-208">輸入要邀請的人員名稱。</span><span class="sxs-lookup"><span data-stu-id="0129b-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="0129b-209">按一下 **新增**，然後按一下 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="0129b-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="0129b-210">邀請來賓加入團隊</span><span class="sxs-lookup"><span data-stu-id="0129b-210">To invite guests to a team</span></span>
1. <span data-ttu-id="0129b-211">在該團隊中，按一下 **更多選項** (**\*\*\***)，然後按一下 **新增成員**。</span><span class="sxs-lookup"><span data-stu-id="0129b-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="0129b-212">輸入要邀請之來賓的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0129b-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="0129b-213">按一下 **編輯來賓資訊**。</span><span class="sxs-lookup"><span data-stu-id="0129b-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="0129b-214">輸入來賓的全名，然後按一下核取方塊。</span><span class="sxs-lookup"><span data-stu-id="0129b-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="0129b-215">按一下 **新增**，然後按一下 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="0129b-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0129b-216">請參閱</span><span class="sxs-lookup"><span data-stu-id="0129b-216">See also</span></span>

[<span data-ttu-id="0129b-217">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="0129b-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="0129b-218">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="0129b-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="0129b-219">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="0129b-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="0129b-220">使用受管理來賓建立 B2B 外部網路</span><span class="sxs-lookup"><span data-stu-id="0129b-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="0129b-221">SharePoint 和 OneDrive 與 Azure AD B2B 整合</span><span class="sxs-lookup"><span data-stu-id="0129b-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="0129b-222">從 SharePoint 或 OneDrive 共用時，共用選項會以灰色顯示</span><span class="sxs-lookup"><span data-stu-id="0129b-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)