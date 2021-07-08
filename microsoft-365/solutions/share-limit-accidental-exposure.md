---
title: 限制意外暴露
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
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 深入了解如何在與組織外的人員共用檔案時，限制資訊意外暴露。
ms.openlocfilehash: 1dffa40a0c21f5f611492d5a098a98f8aaa726a5
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326984"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="ac11f-103">在與組織外的人員共用檔案時，限制資訊意外暴露。</span><span class="sxs-lookup"><span data-stu-id="ac11f-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="ac11f-104">當與組織外的人員共用檔案和資料夾時，有許多選項可以降低意外共用敏感性資訊的機會。</span><span class="sxs-lookup"><span data-stu-id="ac11f-104">When sharing files and folders with people outside your organization, there are various options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="ac11f-105">您可以從本文中選擇最符合貴組織需求的選項。</span><span class="sxs-lookup"><span data-stu-id="ac11f-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="ac11f-106">使用適用於 [任何人] 連結的最佳做法</span><span class="sxs-lookup"><span data-stu-id="ac11f-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="ac11f-107">如果組織的人員需要進行未驗證共用，但是您擔心未驗證的人員修改內容，請參閱[未驗證共用的最佳做法](best-practices-anonymous-sharing.md)，以取得如何在組織中使用未驗證共用的指導方針。</span><span class="sxs-lookup"><span data-stu-id="ac11f-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="ac11f-108">關閉 [任何人] 連結</span><span class="sxs-lookup"><span data-stu-id="ac11f-108">Turn off Anyone links</span></span>

<span data-ttu-id="ac11f-109">我們建議針對適當的內容讓 [任何人] 連結啟用，因為這是最簡單的共用方式，而且可以協助減少使用者尋求您的 IT 部門掌握外其他解決方案的風險。</span><span class="sxs-lookup"><span data-stu-id="ac11f-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="ac11f-110">[任何人] 連結可以轉寄給其他人，但是檔案存取權僅限擁有連結的人員使用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="ac11f-111">如果您要組織外的人員一律在存取 SharePoint、群組或 Teams 中的內容時經過驗證，您可以關閉 [任何人] 共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="ac11f-112">這會防止使用者未經驗證而共用內容。</span><span class="sxs-lookup"><span data-stu-id="ac11f-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="ac11f-113">如果您停用 [任何人] 連結，使用者仍然可以使用 [特定人員] 連結，輕易地與來賓共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="ac11f-114">在此情況下，所有組織外的人員都必須先經過驗證，才能存取共用的內容。</span><span class="sxs-lookup"><span data-stu-id="ac11f-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="ac11f-115">視您的需求而定，您可以針對特定網站或整個組織停用 [任何人] 連結。</span><span class="sxs-lookup"><span data-stu-id="ac11f-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="ac11f-116">若要關閉貴組織的 [任何人] 連結</span><span class="sxs-lookup"><span data-stu-id="ac11f-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="ac11f-117">在 SharePoint 管理中心中，按一下左側導覽窗格中的 [共用]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="ac11f-118">將 SharePoint 外部共用設定設為 [新的及現有來賓]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![組織層級 SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="ac11f-120">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-120">Click **Save**.</span></span>

<span data-ttu-id="ac11f-121">若要關閉網站的 [任何人] 連結</span><span class="sxs-lookup"><span data-stu-id="ac11f-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="ac11f-122">在 SharePoint 管理中心中，在左側導覽窗格中展開 [網站]，然後按一下 [使用中網站]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="ac11f-123">選取您要設定的網站。</span><span class="sxs-lookup"><span data-stu-id="ac11f-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="ac11f-124">在功能區中，按一下 [共用]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="ac11f-125">請確認共用設為 [新的及現有來賓]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![網站層級 SharePoint 網站外部共用設定的螢幕擷取畫面](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="ac11f-127">如果您做了任何變更，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="ac11f-128">網域篩選</span><span class="sxs-lookup"><span data-stu-id="ac11f-128">Domain filtering</span></span>

<span data-ttu-id="ac11f-129">您可以使用網域來允許或拒絕清單，以指定您的使用者在與組織外的人員共用時，可以使用哪些網域。</span><span class="sxs-lookup"><span data-stu-id="ac11f-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="ac11f-130">使用允許清單，您可以指定網域清單，而該網域內的組織使用者可以與組織外的人員共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="ac11f-131">已封鎖與其他網域共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-131">Sharing with other domains is blocked.</span></span> <span data-ttu-id="ac11f-132">如貴組織只會與來自特定網域清單的人員共同作業，您可以使用此功能來防止與其他網域共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="ac11f-133">使用拒絕清單，您可以指定網域清單，而該網域內的組織使用者不能與組織外的人員共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="ac11f-134">已封鎖與清單中的網域共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="ac11f-135">如果您有競爭對手，例如您想要避免某人存取組織中的內容，這個功能很有用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="ac11f-136">允許和拒絕清單只會影響與來賓的共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="ac11f-137">如果您未停用 [任何人] 連結，使用者仍然可以使用這個連結，與來自禁止網域的人員共用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="ac11f-138">若要達到使用網域允許和拒絕清單的最佳結果，請考量停用 [任何人] 連結，如上所述。</span><span class="sxs-lookup"><span data-stu-id="ac11f-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="ac11f-139">若要設定網域允許或拒絕清單</span><span class="sxs-lookup"><span data-stu-id="ac11f-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="ac11f-140">在 SharePoint 管理中心中，按一下左側導覽窗格中的 [共用]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="ac11f-141">在 [外部共用的進階設定]底下，選取 [依網域限制外部共用] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ac11f-141">Under **Advanced settings for external sharing**, select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="ac11f-142">按一下 [新增網域]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="ac11f-143">選取您是否想要封鎖網域，輸入網域，然後按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![依網域的 SharePoint 限制外部共用設定的螢幕擷取畫面](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="ac11f-145">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ac11f-145">Click **Save**.</span></span>

<span data-ttu-id="ac11f-146">如果您想要依據比 SharePoint 和 OneDrive 還要高層級的網域限制共用，您可以在 Azure Active Directory 中[允許或封鎖對特定組織的 B2B 使用者的邀請](/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="ac11f-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="ac11f-147">(您必須設定 [SharePoint 和 OneDrive 與 Azure AD B2B 整合 (預覽版)](/sharepoint/sharepoint-azureb2b-integration-preview)，讓這些設定影響 SharePoint 和 OneDrive。)</span><span class="sxs-lookup"><span data-stu-id="ac11f-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="ac11f-148">將與組織外的人員共用的檔案、資料夾和網站限制為指定的安全性群組</span><span class="sxs-lookup"><span data-stu-id="ac11f-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="ac11f-149">您可以將與組織外的人員共用的檔案、資料夾和網站限制為指定的安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ac11f-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="ac11f-150">如果您想要啟用外部共用，但是有核准工作流程或要求程序，這個選項相當有用。</span><span class="sxs-lookup"><span data-stu-id="ac11f-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="ac11f-151">或者，您可能會要求您的使用者在加入安全性群組並允許外部人員共用之前，先完成訓練課程。</span><span class="sxs-lookup"><span data-stu-id="ac11f-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="ac11f-152">將外部共用限制為安全性群組的成員</span><span class="sxs-lookup"><span data-stu-id="ac11f-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="ac11f-153">在 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint) 中，在左側導覽窗格中， **[政策]** 的下方，按一下 **[共用]**。</span><span class="sxs-lookup"><span data-stu-id="ac11f-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="ac11f-154">在 **[外部共用]** 底下，展開 **更多外部共用設定**。</span><span class="sxs-lookup"><span data-stu-id="ac11f-154">Under **External sharing**, expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="ac11f-155">選取 **[只允許特定安全性群組中的使用者對外共用]**，然後選取 **[管理安全性群組]**。</span><span class="sxs-lookup"><span data-stu-id="ac11f-155">Select **Allow only users in specific security groups to share externally**, and then select **Manage security groups**.</span></span>

    ![管理安全性群組窗格的螢幕擷取畫面](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="ac11f-157">在 **[新增安全性群組]** 方塊中，輸入安全性群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="ac11f-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="ac11f-158">[安全性群組] 方塊會隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="ac11f-158">The security group box appears.</span></span>

5. <span data-ttu-id="ac11f-159">在安全性群組名稱旁邊，自 **[可以共用的對象]** 下拉式功能表，請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ac11f-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="ac11f-160">**僅限已驗證的來賓**(預設)</span><span class="sxs-lookup"><span data-stu-id="ac11f-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="ac11f-161">**任何人**</span><span class="sxs-lookup"><span data-stu-id="ac11f-161">**Anyone**</span></span>

6. <span data-ttu-id="ac11f-162">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="ac11f-162">Select **Save**.</span></span>

<span data-ttu-id="ac11f-163">請注意，這會影響檔案、資料夾和網站，但是不會影響 Microsoft 365 群組或 Teams。</span><span class="sxs-lookup"><span data-stu-id="ac11f-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="ac11f-164">當成員邀請來賓加入私人 Microsoft 365 群組或 Microsoft Teams 中的私人小組時，邀請會傳送給群組或小組擁有者進行核准。</span><span class="sxs-lookup"><span data-stu-id="ac11f-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac11f-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ac11f-165">See Also</span></span>

[<span data-ttu-id="ac11f-166">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="ac11f-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="ac11f-167">與匿名使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="ac11f-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)
