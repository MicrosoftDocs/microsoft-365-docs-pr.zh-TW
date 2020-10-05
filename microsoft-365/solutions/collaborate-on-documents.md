---
title: 在文件上與來賓共同作業
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: 在本文中，您將瞭解如何在 SharePoint 和 OneDrive 的檔中與客人共同作業。
ms.openlocfilehash: 1a7591915efa82f1995ce2789e181dc350cd3784
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357779"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="34c1d-103">在文件上與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="34c1d-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="34c1d-104">如果您需要與組織外部的人員共同作業 SharePoint 或 OneDrive 中的檔，您可以將檔的共用連結傳送給他們。</span><span class="sxs-lookup"><span data-stu-id="34c1d-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="34c1d-105">在本文中，我們將逐步完成設定 SharePoint 的共用連結，以及組織需求 OneDrive 所需的 Microsoft 365 設定步驟。</span><span class="sxs-lookup"><span data-stu-id="34c1d-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="34c1d-106">影片示範</span><span class="sxs-lookup"><span data-stu-id="34c1d-106">Video demonstration</span></span>

<span data-ttu-id="34c1d-107">這段影片顯示本檔所述的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="34c1d-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="34c1d-108">Azure 組織關聯性設定</span><span class="sxs-lookup"><span data-stu-id="34c1d-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="34c1d-109">Microsoft 365 中的共用可透過 [Azure Active Directory 中的組織關聯設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)受到最高層級的制約。</span><span class="sxs-lookup"><span data-stu-id="34c1d-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="34c1d-110">如果 Azure AD 中已停用來賓共用或已限制來賓共用，這會覆寫您在 Microsoft 365 中設定的任何共用設定。</span><span class="sxs-lookup"><span data-stu-id="34c1d-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="34c1d-111">檢查 [組織關聯] 設定，以確保未封鎖與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="34c1d-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory 組織關聯性設定頁面的螢幕擷取畫面](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="34c1d-113">設定組織關聯設定</span><span class="sxs-lookup"><span data-stu-id="34c1d-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="34c1d-114">登入 Microsoft Azure，網址為 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="34c1d-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="34c1d-115">在左側導覽中，按一下 [ **Azure Active Directory**]。</span><span class="sxs-lookup"><span data-stu-id="34c1d-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="34c1d-116">在 [ **一覽表** ] 窗格中，按一下 [ **組織關聯**性]。</span><span class="sxs-lookup"><span data-stu-id="34c1d-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="34c1d-117">在 [ **組織關聯** ] 窗格中，按一下 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="34c1d-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="34c1d-118">確定 **guest 和 guest inviter role 中的系統管理員和使用者都可以邀請** 和 **成員可以邀請** 皆設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="34c1d-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="34c1d-119">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34c1d-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="34c1d-120">請記下 [ **協同限制** ] 區段中的設定。</span><span class="sxs-lookup"><span data-stu-id="34c1d-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="34c1d-121">確定您要與之來賓進行共同作業的網域不會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="34c1d-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="34c1d-122">如果您與多個組織的客人合作，您可能想要限制其存取目錄資料的能力。</span><span class="sxs-lookup"><span data-stu-id="34c1d-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="34c1d-123">這可防止使用者看到目錄中的客人。</span><span class="sxs-lookup"><span data-stu-id="34c1d-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="34c1d-124">若要執行此動作，請在 [ **來賓使用者訪問限制**] 底下，選取 [來賓使用者對內容的 **存取權受到限制** ]，或 **[來賓使用者存取許可權制于自身目錄物件的屬性和成員資格]** 設定。</span><span class="sxs-lookup"><span data-stu-id="34c1d-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="34c1d-125">SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="34c1d-125">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="34c1d-126">為了讓組織外部人員能夠存取 SharePoint 或 OneDrive 中的檔，SharePoint 和 OneDrive 組織層級的共用設定必須允許與組織外部的人員共用。</span><span class="sxs-lookup"><span data-stu-id="34c1d-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="34c1d-127">SharePoint 的組織層級設定會決定個別 SharePoint 網站可使用的設定。</span><span class="sxs-lookup"><span data-stu-id="34c1d-127">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="34c1d-128">網站設定不能超過組織層級設定的許可。</span><span class="sxs-lookup"><span data-stu-id="34c1d-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="34c1d-129">OneDrive 的組織層級設定決定使用者 OneDrive 庫中可使用的共用層級。</span><span class="sxs-lookup"><span data-stu-id="34c1d-129">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="34c1d-130">若要 SharePoint 和 OneDrive，如果您想要允許未驗證的檔案和資料夾共用，請選擇 [ **任何人**]。</span><span class="sxs-lookup"><span data-stu-id="34c1d-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="34c1d-131">若要確定您組織外部的人員必須進行驗證，請選擇 [ **新增] 和 [現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="34c1d-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="34c1d-132">[*任何人*] 連結是最簡單的共用方式：您組織外部的人員可以在未驗證的情況下開啟連結，而且可以隨意將其傳遞給其他人。</span><span class="sxs-lookup"><span data-stu-id="34c1d-132">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="34c1d-133">若為 SharePoint，請選擇您組織中的任何網站所需的功能最寬鬆設定。</span><span class="sxs-lookup"><span data-stu-id="34c1d-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織層級共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="34c1d-135">設定 SharePoint 組織層級共用設定</span><span class="sxs-lookup"><span data-stu-id="34c1d-135">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="34c1d-136">在 Microsoft 365 系統管理中心的左側導覽中，按一下 [系統 **管理中心**] 底下的 [ **SharePoint**]。</span><span class="sxs-lookup"><span data-stu-id="34c1d-136">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="34c1d-137">在 SharePoint 管理中心中，按一下左側導覽窗格中的 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34c1d-137">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="34c1d-138">確定 SharePoint 或 OneDrive 的外部共用已設定為 **任何人** 或 **新的和現有的客人**。</span><span class="sxs-lookup"><span data-stu-id="34c1d-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="34c1d-139"> (請注意，OneDrive 設定不能超過 SharePoint 設定的容許數目。 ) </span><span class="sxs-lookup"><span data-stu-id="34c1d-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="34c1d-140">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34c1d-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="34c1d-141">SharePoint 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="34c1d-141">SharePoint organization level default link settings</span></span>

<span data-ttu-id="34c1d-142">預設的檔案和資料夾連結設定會決定使用者在共用檔案或資料夾時，預設會向使用者顯示的連結選項。</span><span class="sxs-lookup"><span data-stu-id="34c1d-142">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="34c1d-143">如有需要，使用者可以在共用之前將連結類型變更為其他選項之一。</span><span class="sxs-lookup"><span data-stu-id="34c1d-143">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="34c1d-144">請記住，此設定會影響組織中 SharePoint 網站和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="34c1d-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="34c1d-145">選擇當使用者共用檔案和資料夾時，預設會選取的連結類型：</span><span class="sxs-lookup"><span data-stu-id="34c1d-145">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="34c1d-146">**任何具有連結的使用者** -如果您想要進行許多未驗證的檔案和資料夾共用，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="34c1d-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="34c1d-147">如果您想要允許 *任何人* 的連結，但擔心意外的共用驗證，請將其中一個其他選項視為預設值。</span><span class="sxs-lookup"><span data-stu-id="34c1d-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="34c1d-148">只有在您已啟用 **任何** 共用時，才可使用此連結類型。</span><span class="sxs-lookup"><span data-stu-id="34c1d-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="34c1d-149">**僅限貴組織中的人員** -如果您預期大多數的檔案和資料夾共用與組織內的人員有關，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="34c1d-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="34c1d-150">**特定人員** -如果您想要對來賓執行大量檔案和資料夾共用，請考慮此選項。</span><span class="sxs-lookup"><span data-stu-id="34c1d-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="34c1d-151">這種連結類型與來賓搭配使用，需要驗證。</span><span class="sxs-lookup"><span data-stu-id="34c1d-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![SharePoint 組織層級檔案和資料夾共用設定的螢幕擷取畫面](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="34c1d-153">設定 SharePoint 和 OneDrive 組織層級的預設連結設定</span><span class="sxs-lookup"><span data-stu-id="34c1d-153">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="34c1d-154">流覽至 SharePoint 系統管理中心的 [共用] 頁面。</span><span class="sxs-lookup"><span data-stu-id="34c1d-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="34c1d-155">在 [檔案 **和資料夾連結**] 底下，選取您要使用的預設共用連結。</span><span class="sxs-lookup"><span data-stu-id="34c1d-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="34c1d-156">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34c1d-156">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="34c1d-157">網站層級共用設定 SharePoint</span><span class="sxs-lookup"><span data-stu-id="34c1d-157">SharePoint site level sharing settings</span></span>

<span data-ttu-id="34c1d-158">如果您要共用 SharePoint 網站中的檔案與資料夾，您也需要檢查該網站的網站層級共用設定。</span><span class="sxs-lookup"><span data-stu-id="34c1d-158">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="34c1d-160">設定網站層級共用設定</span><span class="sxs-lookup"><span data-stu-id="34c1d-160">To set site-level sharing settings</span></span>
1. <span data-ttu-id="34c1d-161">在 SharePoint 管理中心中，在左側導覽窗格中展開 [網站]\*\*\*\*，然後按一下 [使用中網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34c1d-161">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="34c1d-162">選取您剛建立的網站。</span><span class="sxs-lookup"><span data-stu-id="34c1d-162">Select the site that you just created.</span></span>
3. <span data-ttu-id="34c1d-163">在功能區中，按一下 [共用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34c1d-163">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="34c1d-164">確定 [共用] 設定為 [ **任何人** ] 或 [ **現有來賓**]。</span><span class="sxs-lookup"><span data-stu-id="34c1d-164">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="34c1d-165">如果您做了任何變更，請按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34c1d-165">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="34c1d-166">邀請使用者</span><span class="sxs-lookup"><span data-stu-id="34c1d-166">Invite users</span></span>

<span data-ttu-id="34c1d-167">現在已設定來賓共用設定，因此使用者現在可以與組織外部的人員共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="34c1d-167">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="34c1d-168">如需詳細資訊，請參閱 [共用 OneDrive 檔案和資料夾](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) 及 [共用 SharePoint 檔案或資料夾](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) 。</span><span class="sxs-lookup"><span data-stu-id="34c1d-168">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="34c1d-169">另請參閱</span><span class="sxs-lookup"><span data-stu-id="34c1d-169">See Also</span></span>

[<span data-ttu-id="34c1d-170">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="34c1d-170">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="34c1d-171">與來賓共用時限制意外暴露檔案</span><span class="sxs-lookup"><span data-stu-id="34c1d-171">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="34c1d-172">與 Azure AD B2B 的 SharePoint 和 OneDrive 整合</span><span class="sxs-lookup"><span data-stu-id="34c1d-172">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)