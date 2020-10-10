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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 瞭解設定小組以與小組中的客人共同作業所需的 Microsoft 365 設定步驟。
ms.openlocfilehash: 7a2259358d6976184d393980b2b7c0320c3bb171
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409045"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="0c232-103">在小組中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="0c232-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="0c232-104">如果您需要跨檔、工作和交談共同處理來賓，我們建議使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="0c232-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="0c232-105">小組會提供 Office 和 SharePoint 中的所有共同作業功能，以及持續聊天的功能，以及可自訂且可擴展的共同作業工具集合，以整合的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="0c232-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="0c232-106">在本文中，我們將逐步完成設定小組以與來賓共同作業時，所需的 Microsoft 365 設定步驟。</span><span class="sxs-lookup"><span data-stu-id="0c232-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="0c232-107">影片示範</span><span class="sxs-lookup"><span data-stu-id="0c232-107">Video demonstration</span></span>

<span data-ttu-id="0c232-108">這段影片顯示本檔所述的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="0c232-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="0c232-109">Azure 組織關聯性設定</span><span class="sxs-lookup"><span data-stu-id="0c232-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="0c232-110">Microsoft 365 中的共用可透過 [Azure Active Directory 中的組織關聯設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)受到最高層級的制約。</span><span class="sxs-lookup"><span data-stu-id="0c232-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="0c232-111">如果 Azure AD 中已停用或限制來賓共用，此設定會覆寫您在 Microsoft 365 中設定的任何共用設定。</span><span class="sxs-lookup"><span data-stu-id="0c232-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="0c232-112">檢查 [組織關聯] 設定，以確保未封鎖與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="0c232-112">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="0c232-114">設定組織關聯設定</span><span class="sxs-lookup"><span data-stu-id="0c232-114">To set organizational relationship settings</span></span>

1. <span data-ttu-id="0c232-115">登入 Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="0c232-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="0c232-116">在左功能窗格中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="0c232-117">按一下 [ **外部**身分識別]。</span><span class="sxs-lookup"><span data-stu-id="0c232-117">Click **External identities**.</span></span>
4. <span data-ttu-id="0c232-118">在 [ **快速入門** ] 畫面上，按一下左功能窗格中的 [ **外部協同作業設定**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="0c232-119">確定 **guest 和 guest inviter role 中的系統管理員和使用者都可以邀請** 和 **成員可以邀請** 皆設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="0c232-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="0c232-120">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c232-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="0c232-121">請記下 [ **協同限制** ] 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="0c232-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="0c232-122">確定您要與之來賓進行共同作業的網域不會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="0c232-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="0c232-123">如果您與多個組織的客人合作，您可能想要限制其存取目錄資料的能力。</span><span class="sxs-lookup"><span data-stu-id="0c232-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="0c232-124">這可防止使用者看到目錄中的客人。</span><span class="sxs-lookup"><span data-stu-id="0c232-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="0c232-125">若要執行此動作，請在 [ **來賓使用者訪問限制**] 底下，選取 [來賓使用者對內容的 **存取權受到限制** ]，或 **[來賓使用者存取許可權制于自身目錄物件的屬性和成員資格]** 設定。</span><span class="sxs-lookup"><span data-stu-id="0c232-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="0c232-126">小組訪客存取設定</span><span class="sxs-lookup"><span data-stu-id="0c232-126">Teams guest access settings</span></span>

<span data-ttu-id="0c232-127">團隊具有來賓存取的主圖形參數和各種設定，可控制哪些來賓可以在小組中執行。</span><span class="sxs-lookup"><span data-stu-id="0c232-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="0c232-128">主要參數 **允許小組中的來賓存取** 必須 **開啟** ，以供來賓存取在小組中運作。</span><span class="sxs-lookup"><span data-stu-id="0c232-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="0c232-129">檢查以確保小組已啟用來賓存取，並根據您的業務需求對來賓設定進行任何調整。</span><span class="sxs-lookup"><span data-stu-id="0c232-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="0c232-130">請記住，這些設定會影響所有小組。</span><span class="sxs-lookup"><span data-stu-id="0c232-130">Keep in mind that these settings affect all teams.</span></span>

![Teams 來賓存取切換的螢幕擷取畫面](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="0c232-132">設定 Teams 來賓存取設定</span><span class="sxs-lookup"><span data-stu-id="0c232-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="0c232-133">登入 [https://admin.microsoft.com](https://admin.microsoft.com) 的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="0c232-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="0c232-134">在左功能窗格中，按一下 [ **全部顯示**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="0c232-135">在 [系統管理中心]\*\*\*\* 底下，按一下 [Teams]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c232-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="0c232-136">在團隊系統管理中心的左功能窗格中，展開 [ **整個組織的設定** ]，然後按一下 [ **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="0c232-137">確定 [在 Teams 中允許來賓存取]\*\*\*\* 已設定為 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c232-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="0c232-138">對其他來賓設定進行所需的變更，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c232-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c232-139">「小組訪客」設定在開啟後，可能需要長達24小時的時間才會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="0c232-139">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="0c232-140">Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="0c232-140">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="0c232-141">小組會使用 Microsoft 365 群組做為小組成員資格。</span><span class="sxs-lookup"><span data-stu-id="0c232-141">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="0c232-142">為了讓小組中的來賓存取能夠運作，必須開啟 Microsoft 365 群組來賓設定。</span><span class="sxs-lookup"><span data-stu-id="0c232-142">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Microsoft 365 系統管理中心中 Microsoft 365 群組來賓設定的螢幕擷取畫面](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="0c232-144">設定 Microsoft 365 群組來賓設定</span><span class="sxs-lookup"><span data-stu-id="0c232-144">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="0c232-145">在 Microsoft 365 系統管理中心的左功能窗格中，展開 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-145">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="0c232-146">按一下 [ **組織設定**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-146">Click **Org settings**.</span></span>
3. <span data-ttu-id="0c232-147">在清單中，按一下 [ **Microsoft 365 群組**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-147">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="0c232-148">確定 **允許群組擁有者將組織外部的人員新增至 Microsoft 365 群組做為來賓** ，並 **讓 [允許來賓群組成員存取群組內容** ] 核取方塊皆已勾選。</span><span class="sxs-lookup"><span data-stu-id="0c232-148">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="0c232-149">如果您進行變更，請按一下 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-149">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="0c232-150">SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0c232-150">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="0c232-151">小組內容（如檔案、資料夾和清單）全都儲存在 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0c232-151">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="0c232-152">為了讓來賓能夠存取小組中的這些專案，SharePoint 組織層級的共用設定必須允許與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="0c232-152">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="0c232-153">組織層級設定會決定個別網站可使用的設定，包括與小組相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="0c232-153">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="0c232-154">網站設定不能超過組織層級設定的許可。</span><span class="sxs-lookup"><span data-stu-id="0c232-154">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="0c232-155">如果您想要允許檔案和資料夾與未驗證人員共用，請選擇 [ **任何人**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-155">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="0c232-156">如果您想要確保所有來賓都必須進行驗證，請選擇 [ **新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-156">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="0c232-157">選擇您的組織中的任何網站所需的功能最寬鬆設定。</span><span class="sxs-lookup"><span data-stu-id="0c232-157">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="0c232-159">設定 SharePoint 組織層級的共用設定</span><span class="sxs-lookup"><span data-stu-id="0c232-159">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="0c232-160">在 Microsoft 365 系統管理中心的左功能窗格中，按一下 [系統 **管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-160">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="0c232-161">在 [SharePoint 系統管理中心] 的左功能窗格中，展開 [ **原則** ]，然後按一下 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-161">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="0c232-162">確定 SharePoint 的外部共用已設定為 **任何人** 或 **新的和現有的客人**。</span><span class="sxs-lookup"><span data-stu-id="0c232-162">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="0c232-163">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c232-163">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="0c232-164">SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="0c232-164">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="0c232-165">預設的檔案和資料夾連結設定會決定在使用者共用檔案或資料夾時，預設會向使用者顯示的連結選項。</span><span class="sxs-lookup"><span data-stu-id="0c232-165">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="0c232-166">如有需要，使用者可以在共用之前將連結類型變更為其他選項之一。</span><span class="sxs-lookup"><span data-stu-id="0c232-166">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="0c232-167">請記住，此設定會影響組織中的所有小組和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="0c232-167">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="0c232-168">選擇下列任一連結類型：使用者共用檔案和資料夾時預設會選取下列其中一種連結類型：</span><span class="sxs-lookup"><span data-stu-id="0c232-168">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="0c232-169">**任何具有連結的使用者** -如果您想要對檔案和資料夾進行許多未驗證的共用，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="0c232-169">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="0c232-170">如果您想要允許 *任何人* 的連結，但擔心意外的共用驗證，請將其中一個其他選項視為預設值。</span><span class="sxs-lookup"><span data-stu-id="0c232-170">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="0c232-171">只有在您已啟用 **任何** 共用時，才可使用此連結類型。</span><span class="sxs-lookup"><span data-stu-id="0c232-171">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="0c232-172">**僅限貴組織中的人員** -如果您預期大多數的檔案和資料夾共用與組織內的人員有關，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="0c232-172">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="0c232-173">**特定人員** -如果您想要對來賓執行大量檔案和資料夾共用，請考慮此選項。</span><span class="sxs-lookup"><span data-stu-id="0c232-173">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="0c232-174">這種連結類型與來賓搭配使用，需要驗證。</span><span class="sxs-lookup"><span data-stu-id="0c232-174">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="0c232-176">設定 SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="0c232-176">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="0c232-177">流覽至 SharePoint 系統管理中心的 [共用] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0c232-177">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="0c232-178">在 [檔案 **和資料夾連結**] 底下，選取您要使用的預設共用連結。</span><span class="sxs-lookup"><span data-stu-id="0c232-178">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="0c232-179">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c232-179">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="0c232-180">建立團隊</span><span class="sxs-lookup"><span data-stu-id="0c232-180">Create a team</span></span>

<span data-ttu-id="0c232-181">下一步是建立您計畫用以與客人合作的小組。</span><span class="sxs-lookup"><span data-stu-id="0c232-181">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="0c232-182">建立小組</span><span class="sxs-lookup"><span data-stu-id="0c232-182">To create a team</span></span>
1. <span data-ttu-id="0c232-183">在 [小組] 的 [ **小組** ] 索引標籤上，按一下 [ **加入] 或 [建立小組** ] （位於左窗格的底部）。</span><span class="sxs-lookup"><span data-stu-id="0c232-183">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="0c232-184">按一下 [ **建立小組**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-184">Click **Create a team**.</span></span>
3. <span data-ttu-id="0c232-185">按一下 [ **從頭開始建立小組**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-185">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="0c232-186">選擇 [ **私人** ] 或 [ **公用**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-186">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="0c232-187">輸入團隊的名稱和描述，然後按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-187">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="0c232-188">按一下 [ **略過**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-188">Click **Skip**.</span></span>

<span data-ttu-id="0c232-189">我們稍後會邀請使用者。</span><span class="sxs-lookup"><span data-stu-id="0c232-189">We'll invite users later.</span></span> <span data-ttu-id="0c232-190">接下來，請務必檢查與小組相關聯之 SharePoint 網站的網站層級共用設定。</span><span class="sxs-lookup"><span data-stu-id="0c232-190">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="0c232-191">SharePoint 網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0c232-191">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="0c232-192">檢查網站層級的共用設定，確定其允許此小組的訪問類型。</span><span class="sxs-lookup"><span data-stu-id="0c232-192">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="0c232-193">例如，如果您將組織層級設定設定為 [ **任何人**]，但您希望所有來賓都對此小組進行驗證，請確定網站層級共用設定已設定為 [ **新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-193">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)


<span data-ttu-id="0c232-195">設定網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="0c232-195">To set site-level sharing settings</span></span>
1. <span data-ttu-id="0c232-196">在 SharePoint 系統管理中心的左功能窗格中，展開 [ **網站** ]，然後按一下 [作用中的 **網站**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-196">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="0c232-197">為您剛建立的小組選取網站。</span><span class="sxs-lookup"><span data-stu-id="0c232-197">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="0c232-198">點擊。。。，然後選擇 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-198">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="0c232-199">確定 [共用] 設定為 [ **任何人** ] 或 [ **現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-199">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="0c232-200">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0c232-200">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="0c232-201">邀請使用者</span><span class="sxs-lookup"><span data-stu-id="0c232-201">Invite users</span></span>

<span data-ttu-id="0c232-202">現在已設定來賓共用設定，因此您可以開始將內部使用者和來賓新增至您的小組。</span><span class="sxs-lookup"><span data-stu-id="0c232-202">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="0c232-203">邀請內部使用者加入小組</span><span class="sxs-lookup"><span data-stu-id="0c232-203">To invite internal users to a team</span></span>
1. <span data-ttu-id="0c232-204">在團隊中，按一下 [ **更多選項** ] (**\*\*\***) ]，然後按一下 [ **新增成員**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-204">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="0c232-205">輸入您要邀請之人員的名稱。</span><span class="sxs-lookup"><span data-stu-id="0c232-205">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="0c232-206">Click **Add**, and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="0c232-206">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="0c232-207">邀請客人加入小組</span><span class="sxs-lookup"><span data-stu-id="0c232-207">To invite guests to a team</span></span>
1. <span data-ttu-id="0c232-208">在團隊中，按一下 [ **更多選項** ] (**\*\*\***) ]，然後按一下 [ **新增成員**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-208">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="0c232-209">輸入您要邀請之客人的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0c232-209">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="0c232-210">按一下 [ **編輯來賓資訊**]。</span><span class="sxs-lookup"><span data-stu-id="0c232-210">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="0c232-211">輸入來賓的完整名稱，然後按一下核取記號。</span><span class="sxs-lookup"><span data-stu-id="0c232-211">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="0c232-212">Click **Add**, and then click **Close**.</span><span class="sxs-lookup"><span data-stu-id="0c232-212">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c232-213">請參閱</span><span class="sxs-lookup"><span data-stu-id="0c232-213">See also</span></span>

[<span data-ttu-id="0c232-214">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="0c232-214">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="0c232-215">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="0c232-215">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="0c232-216">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="0c232-216">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="0c232-217">使用受管理來賓建立 B2B 外部網路</span><span class="sxs-lookup"><span data-stu-id="0c232-217">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="0c232-218">與 Azure AD B2B 的 SharePoint 和 OneDrive 整合</span><span class="sxs-lookup"><span data-stu-id="0c232-218">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
