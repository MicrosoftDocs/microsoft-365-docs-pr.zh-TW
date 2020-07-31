---
title: 使用受管理來賓建立 B2B 外部網路
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
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: 瞭解如何使用夥伴組織中的受管理來賓使用者建立 B2B 外部網路網站或小組。
ms.openlocfilehash: 4f8eb33ad9b41f552975d4158a61ec4cedcfa9cc
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526979"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="21fc2-103">使用受管理來賓建立 B2B 外部網路</span><span class="sxs-lookup"><span data-stu-id="21fc2-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="21fc2-104">您可以使用[Azure Active Directory 的權利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)建立 B2B 外部網路，以與使用 Azure Active Directory 的夥伴組織共同作業。</span><span class="sxs-lookup"><span data-stu-id="21fc2-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="21fc2-105">這可讓使用者在外部網路網站或小組中自我註冊，並透過核准工作流程接收存取權。</span><span class="sxs-lookup"><span data-stu-id="21fc2-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="21fc2-106">透過這種共用資源進行共同作業，合作夥伴組織可以協助使用者在其端維護和核准來賓使用者，減少 IT 部門的負擔，並讓您能夠熟悉共同作業合約，以管理使用者存取。</span><span class="sxs-lookup"><span data-stu-id="21fc2-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="21fc2-107">本文將逐步逐步建立可透過自助存取註冊模型與夥伴組織共用的資源套件（此案例中為網站或小組）。</span><span class="sxs-lookup"><span data-stu-id="21fc2-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="21fc2-108">開始之前，請先建立您想要與夥伴組織共用的網站或小組，並為其啟用來賓共用。</span><span class="sxs-lookup"><span data-stu-id="21fc2-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="21fc2-109">請參閱[與網站中的客人共同](collaborate-in-site.md)作業，或[與小組的客人共同合作](collaborate-as-team.md)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="21fc2-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="21fc2-110">我們也建議您複查[建立安全來賓共用環境](create-secure-guest-sharing-environment.md)，以取得安全性與合規性功能的相關資訊，以協助您在與來賓合作時維持您的管理原則。</span><span class="sxs-lookup"><span data-stu-id="21fc2-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="21fc2-111">影片示範</span><span class="sxs-lookup"><span data-stu-id="21fc2-111">Video demonstration</span></span>

<span data-ttu-id="21fc2-112">這段影片會示範本文所述的程式。</span><span class="sxs-lookup"><span data-stu-id="21fc2-112">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="21fc2-113">連接夥伴組織</span><span class="sxs-lookup"><span data-stu-id="21fc2-113">Connect the partner organization</span></span>

<span data-ttu-id="21fc2-114">為了從夥伴組織邀請來賓，您必須將該夥伴的網域新增為 Azure Active Directory 中的連線組織。</span><span class="sxs-lookup"><span data-stu-id="21fc2-114">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="21fc2-115">新增連線的組織</span><span class="sxs-lookup"><span data-stu-id="21fc2-115">To add a connected organization</span></span>
1. <span data-ttu-id="21fc2-116">在 [ [Azure Active Directory](https://aad.portal.azure.com)] 中，按一下 [身分**識別管理**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-116">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="21fc2-117">按一下 [**連線的組織**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-117">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="21fc2-118">按一下 [**新增連線的組織**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-118">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="21fc2-119">輸入組織的名稱和描述，然後按 **[下一步：目錄 + 網域]**。</span><span class="sxs-lookup"><span data-stu-id="21fc2-119">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="21fc2-120">按一下 [**新增目錄 + 網域**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-120">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="21fc2-121">輸入您要連線之組織的網域，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-121">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="21fc2-122">按一下 **[連線]**，然後按 **[下一步：主辦方**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-122">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="21fc2-123">從您的組織或您要連線的組織，新增您要用來核准來賓使用者存取權的組織或組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="21fc2-123">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="21fc2-124">按 **[下一步：審閱 + 建立**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-124">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="21fc2-125">檢查您所選擇的設定，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-125">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Azure Active Directory 中連線之組織頁面的螢幕擷取畫面](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="21fc2-127">選擇要共用的資源</span><span class="sxs-lookup"><span data-stu-id="21fc2-127">Choose the resources to share</span></span>

<span data-ttu-id="21fc2-128">選取要與夥伴組織共用之資源的第一個步驟是建立包含這些資源的目錄。</span><span class="sxs-lookup"><span data-stu-id="21fc2-128">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="21fc2-129">建立目錄</span><span class="sxs-lookup"><span data-stu-id="21fc2-129">To create a catalog</span></span>
1. <span data-ttu-id="21fc2-130">在 [ [Azure Active Directory](https://aad.portal.azure.com)] 中，按一下 [身分**識別管理**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-130">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="21fc2-131">按一下 [**目錄**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-131">Click **Catalogs**.</span></span>
3. <span data-ttu-id="21fc2-132">按一下 [**新增目錄**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-132">Click **New catalog**.</span></span>
4. <span data-ttu-id="21fc2-133">輸入目錄的名稱和描述，並確定**外部使用者**的**Enabled**及 enabled 皆已設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="21fc2-133">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="21fc2-134">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21fc2-134">Click **Create**.</span></span>

   ![Azure Active Directory 身分識別管理中目錄頁面的螢幕擷取畫面](../media/identity-governance-catalogs.png)

<span data-ttu-id="21fc2-136">建立目錄之後，您可以新增您要與夥伴組織共用的 SharePoint 網站或團隊。</span><span class="sxs-lookup"><span data-stu-id="21fc2-136">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="21fc2-137">將資源新增至目錄</span><span class="sxs-lookup"><span data-stu-id="21fc2-137">To add resources to a catalog</span></span>
1. <span data-ttu-id="21fc2-138">在 [Azure AD 身分識別管理] 中，按一下 [**目錄**]，然後按一下您要新增資源的目錄。</span><span class="sxs-lookup"><span data-stu-id="21fc2-138">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="21fc2-139">按一下 [**資源**]，然後按一下 [**新增資源**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-139">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="21fc2-140">選取您要包含在外部網路的小組或 SharePoint 網站，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-140">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Azure Active Directory 身分識別管理中目錄資源頁面的螢幕擷取畫面](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="21fc2-142">在您定義要共用的資源之後，下一步是建立訪問套件，該套件會定義授與夥伴使用者的存取類型，以及要求存取之新夥伴使用者的核准程式。</span><span class="sxs-lookup"><span data-stu-id="21fc2-142">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="21fc2-143">建立 access 套件</span><span class="sxs-lookup"><span data-stu-id="21fc2-143">To create an access package</span></span>
1. <span data-ttu-id="21fc2-144">在 [Azure AD 身分識別管理] 中，按一下 [**目錄**]，然後按一下您要建立訪問套件的目錄。</span><span class="sxs-lookup"><span data-stu-id="21fc2-144">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="21fc2-145">按一下 [ **Access 套裝**]，然後按一下 [**新的 access 套件**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-145">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="21fc2-146">輸入 access 套件的名稱和描述，然後按一下 **[下一步：資源角色]**。</span><span class="sxs-lookup"><span data-stu-id="21fc2-146">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="21fc2-147">選擇您要用於外部網路的目錄中的資源。</span><span class="sxs-lookup"><span data-stu-id="21fc2-147">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="21fc2-148">針對每個資源，在 [**角色**] 欄中，選擇您想要授與使用外部網路之來賓使用者的使用者角色。</span><span class="sxs-lookup"><span data-stu-id="21fc2-148">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="21fc2-149">按 **[下一步：要求]**。</span><span class="sxs-lookup"><span data-stu-id="21fc2-149">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="21fc2-150">在 [**可要求存取權的使用者**] 底下，選擇 [**不在您的目錄中的使用者**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-150">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="21fc2-151">確定已選取 [**特定連接的組織**] 選項，然後按一下 [**新增目錄**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-151">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="21fc2-152">選擇您先前新增的連線組織，然後按一下 [**選取**]</span><span class="sxs-lookup"><span data-stu-id="21fc2-152">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="21fc2-153">在 [**核准**] 底下，選擇 **[是]** 以 [**要求核准**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-153">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="21fc2-154">在 [**第一位核准者**] 底下，選擇您先前新增的其中一個主辦方，或選擇特定使用者。</span><span class="sxs-lookup"><span data-stu-id="21fc2-154">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="21fc2-155">按一下 [**新增回退**]，然後選取一個回退核准者。</span><span class="sxs-lookup"><span data-stu-id="21fc2-155">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="21fc2-156">在 [**啟用**] 下，選擇 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="21fc2-156">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="21fc2-157">按 **[下一步：生命週期]**。</span><span class="sxs-lookup"><span data-stu-id="21fc2-157">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="21fc2-158">選擇您要使用的 [到期] 和 [存取權複查] 設定，然後按 **[下一步]： [審閱 + 建立]**。</span><span class="sxs-lookup"><span data-stu-id="21fc2-158">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="21fc2-159">請複查您的設定，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-159">Review your settings, and then click **Create**.</span></span>

    ![Azure Active Directory 身分識別管理中 access 套件畫面的螢幕擷取畫面](../media/identity-governance-access-packages.png)

<span data-ttu-id="21fc2-161">如果您與大型組織合作，您可能想要隱藏存取套件。</span><span class="sxs-lookup"><span data-stu-id="21fc2-161">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="21fc2-162">如果已隱藏此套件，則夥伴組織中的使用者將不會在其「*我的存取*入口網站」上看到此套件。</span><span class="sxs-lookup"><span data-stu-id="21fc2-162">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="21fc2-163">相反地，必須傳送直接連結才能註冊套件。</span><span class="sxs-lookup"><span data-stu-id="21fc2-163">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="21fc2-164">隱藏存取封裝可以減少不適當的存取要求數目，也有助於保留夥伴組織入口網站中可用的訪問套件組織。</span><span class="sxs-lookup"><span data-stu-id="21fc2-164">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="21fc2-165">若要將訪問套件設定為隱藏</span><span class="sxs-lookup"><span data-stu-id="21fc2-165">To set an access package to hidden</span></span>
1. <span data-ttu-id="21fc2-166">在 [Azure AD 身分識別管理] 中，按一下 [ **access 套裝**]，然後按一下您的 Access 套件。</span><span class="sxs-lookup"><span data-stu-id="21fc2-166">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="21fc2-167">在 [**概覽**] 頁面上，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="21fc2-167">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="21fc2-168">在 [**屬性**] 底下，選擇 [**隱藏**]，然後按一下 [**儲存** **]** 。</span><span class="sxs-lookup"><span data-stu-id="21fc2-168">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![編輯 access 套件屬性畫面的螢幕擷取畫面](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="21fc2-170">邀請夥伴使用者</span><span class="sxs-lookup"><span data-stu-id="21fc2-170">Invite partner users</span></span>

<span data-ttu-id="21fc2-171">如果您將訪問套件設定為隱藏，您必須將直接連結傳送至夥伴組織，以便他們可以要求網站或小組的存取權。</span><span class="sxs-lookup"><span data-stu-id="21fc2-171">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="21fc2-172">尋找存取入口網站連結</span><span class="sxs-lookup"><span data-stu-id="21fc2-172">To find the access portal link</span></span>
1. <span data-ttu-id="21fc2-173">在 [Azure AD 身分識別管理] 中，按一下 [ **access 套裝**]，然後按一下您的 Access 套件。</span><span class="sxs-lookup"><span data-stu-id="21fc2-173">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="21fc2-174">在 [**概述**] 頁面上，按一下 [**我的 Access 入口網站] 連結**的 [**複製到剪貼簿**] 連結。</span><span class="sxs-lookup"><span data-stu-id="21fc2-174">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Access 入口網站連結的 access 套件屬性螢幕擷取畫面](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="21fc2-176">複製連結後，您就可以在夥伴組織中與連絡人共用，也可以將它傳送給其共同作業小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="21fc2-176">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="21fc2-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21fc2-177">See Also</span></span>

[<span data-ttu-id="21fc2-178">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="21fc2-178">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

