---
title: 在小組中與來賓共同作業
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
description: 深入瞭解為小組中的客人設定任務、交談及檔共同作業時，所需的 Microsoft 365 設定步驟。
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233071"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="0d4f9-103">在小組中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="0d4f9-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="0d4f9-104">如果您需要跨檔、工作和交談共同處理來賓，我們建議使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="0d4f9-105">小組會提供 Office 和 SharePoint 中的所有共同作業功能，以及持續聊天的功能，以及可自訂且可擴展的共同作業工具集合，以整合的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="0d4f9-106">在本文中，我們將逐步完成設定小組以與來賓共同作業時，所需的 Microsoft 365 設定步驟。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="0d4f9-107">設定來賓存取權之後，您可以依照在 [小組中新增客人](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)的步驟，邀請客人加入小組。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="0d4f9-108">影片示範</span><span class="sxs-lookup"><span data-stu-id="0d4f9-108">Video demonstration</span></span>

<span data-ttu-id="0d4f9-109">這段影片顯示本檔所述的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="0d4f9-110">Azure 外部協同作業設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-110">Azure External collaboration settings</span></span>

<span data-ttu-id="0d4f9-111">Microsoft 365 中的共用受 [Azure Active Directory 中的 B2B 外部](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)共同作業設定的最高層級。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="0d4f9-112">如果 Azure AD 中已停用或限制來賓共用，此設定會覆寫您在 Microsoft 365 中設定的任何共用設定。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="0d4f9-113">檢查 B2B 外部協同設定設定，以確保不會封鎖與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="0d4f9-115">設定外部協同作業設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="0d4f9-116">登入 Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="0d4f9-117">在左功能窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0d4f9-118">按一下 [ **外部** 身分識別]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-118">Click **External identities**.</span></span>
4. <span data-ttu-id="0d4f9-119">在 [ **快速入門** ] 畫面上，按一下左功能窗格中的 [ **外部協同作業設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="0d4f9-120">確定 **guest 和 guest inviter role 中的系統管理員和使用者都可以邀請** 和 **成員可以邀請** 皆設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="0d4f9-121">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="0d4f9-122">請記下 [ **協同限制** ] 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="0d4f9-123">確定您要與之來賓進行共同作業的網域不會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="0d4f9-124">如果您與多個組織的客人合作，您可能想要限制其存取目錄資料的能力。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="0d4f9-125">這可防止使用者看到目錄中的客人。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="0d4f9-126">若要執行此動作，請在 [ **來賓使用者訪問限制**] 底下，選取 [來賓使用者對內容的 **存取權受到限制** ]，或 **[來賓使用者存取許可權制于自身目錄物件的屬性和成員資格]** 設定。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="0d4f9-127">小組訪客存取設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-127">Teams guest access settings</span></span>

<span data-ttu-id="0d4f9-128">團隊具有來賓存取的主圖形參數和各種設定，可控制哪些來賓可以在小組中執行。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="0d4f9-129">主要參數 **允許小組中的來賓存取** 必須 **開啟** ，以供來賓存取在小組中運作。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="0d4f9-130">檢查以確保小組已啟用來賓存取，並根據您的業務需求對來賓設定進行任何調整。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="0d4f9-131">請記住，這些設定會影響所有小組。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-131">Keep in mind that these settings affect all teams.</span></span>

![Teams 來賓存取切換的螢幕擷取畫面](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="0d4f9-133">設定 Teams 來賓存取設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="0d4f9-134">登入 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="0d4f9-135">在左功能窗格中，按一下 [ **全部顯示**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="0d4f9-136">在 [系統管理中心] 底下，按一下 [Teams]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="0d4f9-137">在團隊系統管理中心的左功能窗格中，展開 [ **整個組織的設定** ]，然後按一下 [ **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="0d4f9-138">確定 [在 Teams 中允許來賓存取] 已設定為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="0d4f9-139">對其他來賓設定進行所需的變更，然後按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="0d4f9-140">一旦開啟團隊使用者存取，您可以選擇性地使用敏感度標籤控制個別小組及其相關聯 SharePoint 網站的 guest 存取。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="0d4f9-141">如需詳細資訊，請參閱 [[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容]](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="0d4f9-142">「小組訪客」設定在開啟後，可能需要長達24小時的時間才會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="0d4f9-143">Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="0d4f9-144">小組會使用 Microsoft 365 群組做為小組成員資格。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="0d4f9-145">為了讓小組中的來賓存取能夠運作，必須開啟 Microsoft 365 群組來賓設定。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 系統管理中心中 Microsoft 365 群組來賓設定的螢幕擷取畫面](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="0d4f9-147">設定 Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="0d4f9-148">在 Microsoft 365 系統管理中心的左功能窗格中，展開 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="0d4f9-149">按一下 [ **組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="0d4f9-150">在清單中，按一下 [ **Microsoft 365 群組**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="0d4f9-151">確定 **允許群組擁有者將組織外部的人員新增至 Microsoft 365 群組做為來賓** ，並 **讓 [允許來賓群組成員存取群組內容** ] 核取方塊皆已勾選。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="0d4f9-152">如果您進行變更，請按一下 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="0d4f9-153">SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="0d4f9-154">小組內容（如檔案、資料夾和清單）全都儲存在 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="0d4f9-155">為了讓來賓能夠存取小組中的這些專案，SharePoint 組織層級的共用設定必須允許與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="0d4f9-156">組織層級設定會決定個別網站可使用的設定，包括與小組相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="0d4f9-157">網站設定不能超過組織層級設定的許可。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="0d4f9-158">如果您想要允許檔案和資料夾與未驗證人員共用，請選擇 [ **任何人**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="0d4f9-159">如果您想要確保所有來賓都必須進行驗證，請選擇 [ **新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="0d4f9-160">選擇您的組織中的任何網站所需的功能最寬鬆設定。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="0d4f9-162">設定 SharePoint 組織層級的共用設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="0d4f9-163">在 Microsoft 365 系統管理中心的左功能窗格中，按一下 [系統 **管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="0d4f9-164">在 [SharePoint 系統管理中心] 的左功能窗格中，展開 [ **原則** ]，然後按一下 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="0d4f9-165">確定 SharePoint 的外部共用已設定為 **任何人** 或 **新的和現有的客人**。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="0d4f9-166">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="0d4f9-167">SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="0d4f9-168">預設的檔案和資料夾連結設定會決定在使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="0d4f9-169">如有需要，使用者可以在共用之前將連結類型變更為其他選項之一。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="0d4f9-170">請記住，此設定會影響組織中的所有小組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="0d4f9-171">選擇下列任一連結類型：使用者共用檔案和資料夾時預設會選取下列其中一種連結類型：</span><span class="sxs-lookup"><span data-stu-id="0d4f9-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="0d4f9-172">**任何具有連結的使用者** -如果您想要對檔案和資料夾進行許多未驗證的共用，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="0d4f9-173">如果您想要允許 *任何人* 的連結，但擔心意外的共用驗證，請將其中一個其他選項視為預設值。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="0d4f9-174">只有在您已啟用 **任何** 共用時，才可使用此連結類型。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="0d4f9-175">**僅限貴組織中的人員** -如果您預期大多數的檔案和資料夾共用與組織內的人員有關，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="0d4f9-176">**特定人員** -如果您想要對來賓執行大量檔案和資料夾共用，請考慮此選項。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="0d4f9-177">這種連結類型與來賓搭配使用，需要驗證。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="0d4f9-179">設定 SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="0d4f9-180">流覽至 SharePoint 系統管理中心的 [共用] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="0d4f9-181">在 [檔案 **和資料夾連結**] 底下，選取您要使用的預設共用連結。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="0d4f9-182">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="0d4f9-183">建立小組</span><span class="sxs-lookup"><span data-stu-id="0d4f9-183">Create a team</span></span>

<span data-ttu-id="0d4f9-184">下一步是建立您計畫用以與客人合作的小組。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="0d4f9-185">建立小組</span><span class="sxs-lookup"><span data-stu-id="0d4f9-185">To create a team</span></span>
1. <span data-ttu-id="0d4f9-186">在 [小組] 的 [ **小組** ] 索引標籤上，按一下 [ **加入] 或 [建立小組** ] （位於左窗格的底部）。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="0d4f9-187">按一下 [ **建立小組**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="0d4f9-188">按一下 [ **從頭開始建立小組**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="0d4f9-189">選擇 [ **私人** ] 或 [ **公用**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="0d4f9-190">輸入團隊的名稱和描述，然後按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="0d4f9-191">按一下 [ **略過**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-191">Click **Skip**.</span></span>

<span data-ttu-id="0d4f9-192">我們稍後會邀請使用者。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-192">We'll invite users later.</span></span> <span data-ttu-id="0d4f9-193">接下來，請務必檢查與小組相關聯之 SharePoint 網站的網站層級共用設定。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="0d4f9-194">SharePoint 網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="0d4f9-195">檢查網站層級的共用設定，確定其允許此小組的訪問類型。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="0d4f9-196">例如，如果您將組織層級設定設定為 [ **任何人**]，但您希望所有來賓都對此小組進行驗證，請確定網站層級共用設定已設定為 [ **新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="0d4f9-198">設定網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0d4f9-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="0d4f9-199">在 SharePoint 系統管理中心的左功能窗格中，展開 [ **網站** ]，然後按一下 [作用中的 **網站**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="0d4f9-200">為您剛建立的小組選取網站。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="0d4f9-201">點擊。。。，然後選擇 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="0d4f9-202">確定 [共用] 設定為 [ **任何人** ] 或 [ **現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="0d4f9-203">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="0d4f9-204">邀請使用者</span><span class="sxs-lookup"><span data-stu-id="0d4f9-204">Invite users</span></span>

<span data-ttu-id="0d4f9-205">現在已設定來賓共用設定，因此您可以開始將內部使用者和來賓新增至您的小組。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="0d4f9-206">邀請內部使用者加入小組</span><span class="sxs-lookup"><span data-stu-id="0d4f9-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="0d4f9-207">在團隊中，按一下 [ **更多選項** ] (**\*\*\***) ]，然後按一下 [ **新增成員**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="0d4f9-208">輸入您要邀請之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="0d4f9-209">Click **Add**, and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="0d4f9-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="0d4f9-210">邀請客人加入小組</span><span class="sxs-lookup"><span data-stu-id="0d4f9-210">To invite guests to a team</span></span>
1. <span data-ttu-id="0d4f9-211">在團隊中，按一下 [ **更多選項** ] (**\*\*\***) ]，然後按一下 [ **新增成員**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="0d4f9-212">輸入您要邀請之客人的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="0d4f9-213">按一下 [ **編輯來賓資訊**]。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="0d4f9-214">輸入來賓的完整名稱，然後按一下核取記號。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="0d4f9-215">Click **Add**, and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="0d4f9-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d4f9-216">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0d4f9-216">See also</span></span>

[<span data-ttu-id="0d4f9-217">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="0d4f9-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="0d4f9-218">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="0d4f9-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="0d4f9-219">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="0d4f9-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="0d4f9-220">使用受管理來賓建立 B2B 外部網路</span><span class="sxs-lookup"><span data-stu-id="0d4f9-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="0d4f9-221">SharePoint 和 OneDrive 與 Azure AD B2B 整合</span><span class="sxs-lookup"><span data-stu-id="0d4f9-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="0d4f9-222">當您從 SharePoint 或 OneDrive 共用時，共用選項會變灰。</span><span class="sxs-lookup"><span data-stu-id="0d4f9-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
