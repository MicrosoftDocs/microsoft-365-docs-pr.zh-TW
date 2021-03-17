---
title: 管理 Microsoft 365 群組、小組和 SharePoint 中的存取權
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 瞭解如何在 Microsoft 365 群組、小組和 SharePoint 中管理存取。
ms.openlocfilehash: 24a8a43f05206c9f1c0cd07aef480b330d968935
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838706"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a><span data-ttu-id="c6e53-103">管理 Microsoft 365 群組、小組和 SharePoint 中的存取權</span><span class="sxs-lookup"><span data-stu-id="c6e53-103">Governing access in Microsoft 365 groups, Teams, and SharePoint</span></span>

<span data-ttu-id="c6e53-104">有許多控制項可讓您控制人員在群組、小組和 SharePoint 中存取資源的方式。</span><span class="sxs-lookup"><span data-stu-id="c6e53-104">There are many controls that enable you to govern how people access resources in groups, teams, and SharePoint.</span></span> <span data-ttu-id="c6e53-105">請查看這些選項，並考慮其如何對應至您的業務需求、資料敏感度，以及您的使用者需要共同作業的人員範圍。</span><span class="sxs-lookup"><span data-stu-id="c6e53-105">Review these options and consider how they map to your business needs, the sensitivity of your data, and the scope of people that your users need to collaborate with.</span></span>

<span data-ttu-id="c6e53-106">下表提供 Microsoft 365 中可用之存取控制的快速參考。</span><span class="sxs-lookup"><span data-stu-id="c6e53-106">The following table provides a quick reference for the access controls available in Microsoft 365.</span></span> <span data-ttu-id="c6e53-107">以下各節提供進一步的資訊。</span><span class="sxs-lookup"><span data-stu-id="c6e53-107">Further information is provided in the following sections.</span></span>

|<span data-ttu-id="c6e53-108">類別</span><span class="sxs-lookup"><span data-stu-id="c6e53-108">Category</span></span>|<span data-ttu-id="c6e53-109">描述</span><span class="sxs-lookup"><span data-stu-id="c6e53-109">Description</span></span>|<span data-ttu-id="c6e53-110">參考</span><span class="sxs-lookup"><span data-stu-id="c6e53-110">Reference</span></span>|
|:-------|:----------|:--------|
|<span data-ttu-id="c6e53-111">[成員資格]</span><span class="sxs-lookup"><span data-stu-id="c6e53-111">Membership</span></span>|||
||<span data-ttu-id="c6e53-112">個人小組探索</span><span class="sxs-lookup"><span data-stu-id="c6e53-112">Discovery of private teams</span></span>|[<span data-ttu-id="c6e53-113">管理 Microsoft 小組中的私營小組探索</span><span class="sxs-lookup"><span data-stu-id="c6e53-113">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||<span data-ttu-id="c6e53-114">根據規則的動態群組成員資格</span><span class="sxs-lookup"><span data-stu-id="c6e53-114">Dynamic group membership based on rules</span></span>|[<span data-ttu-id="c6e53-115">在 Azure Active Directory 中建立或更新動態群組</span><span class="sxs-lookup"><span data-stu-id="c6e53-115">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||<span data-ttu-id="c6e53-116">控制誰可以共用檔案、資料夾及網站。</span><span class="sxs-lookup"><span data-stu-id="c6e53-116">Control who can share files, folders, and sites.</span></span>|[<span data-ttu-id="c6e53-117">設定及管理存取要求</span><span class="sxs-lookup"><span data-stu-id="c6e53-117">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|<span data-ttu-id="c6e53-118">條件式存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-118">Conditional access</span></span>|||
||<span data-ttu-id="c6e53-119">Multi-Factor 驗證</span><span class="sxs-lookup"><span data-stu-id="c6e53-119">Multi-Factor Authentication</span></span>|[<span data-ttu-id="c6e53-120">Azure AD Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="c6e53-120">Azure AD Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||<span data-ttu-id="c6e53-121">根據群組、小組或網站敏感度來控制裝置存取。</span><span class="sxs-lookup"><span data-stu-id="c6e53-121">Control device access based on group, team, or site sensitivity.</span></span>|[<span data-ttu-id="c6e53-122">使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容</span><span class="sxs-lookup"><span data-stu-id="c6e53-122">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="c6e53-123">限制未受管理裝置的網站存取。</span><span class="sxs-lookup"><span data-stu-id="c6e53-123">Limit site access for unmanaged devices.</span></span>|[<span data-ttu-id="c6e53-124">控制從非管理裝置 SharePoint 存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-124">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||<span data-ttu-id="c6e53-125">根據位置控制網站存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-125">Control site access based on location</span></span>|[<span data-ttu-id="c6e53-126">根據網路位置控制對 SharePoint 和 OneDrive 資料的存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-126">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|<span data-ttu-id="c6e53-127">來賓存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-127">Guest access</span></span>|||
||<span data-ttu-id="c6e53-128">允許或封鎖 SharePoint 從指定的網域共用。</span><span class="sxs-lookup"><span data-stu-id="c6e53-128">Allow or block SharePoint sharing from specified domains.</span></span>|[<span data-ttu-id="c6e53-129">依網域限制 SharePoint 和 OneDrive 內容的共用</span><span class="sxs-lookup"><span data-stu-id="c6e53-129">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||<span data-ttu-id="c6e53-130">允許或封鎖來自指定網域的小組或群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="c6e53-130">Allow or block team or group membership from specified domains.</span></span>|[<span data-ttu-id="c6e53-131">允許或封鎖從特定組織 B2B 使用者的邀請</span><span class="sxs-lookup"><span data-stu-id="c6e53-131">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||<span data-ttu-id="c6e53-132">阻止匿名共用。</span><span class="sxs-lookup"><span data-stu-id="c6e53-132">Prevent anonymous sharing.</span></span>|<span data-ttu-id="c6e53-133">[關閉 [任何人] 連結](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="c6e53-133">[Turn off Anyone links](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span></span>|
||<span data-ttu-id="c6e53-134">控制匿名存取連結的許可權。</span><span class="sxs-lookup"><span data-stu-id="c6e53-134">Control the permissions for anonymous access links.</span></span>|[<span data-ttu-id="c6e53-135">設定任何人的連結許可權連結</span><span class="sxs-lookup"><span data-stu-id="c6e53-135">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||<span data-ttu-id="c6e53-136">控制匿名共用連結的到期。</span><span class="sxs-lookup"><span data-stu-id="c6e53-136">Control the expiration of anonymous sharing links.</span></span>|[<span data-ttu-id="c6e53-137">設定任何人連結的到期日</span><span class="sxs-lookup"><span data-stu-id="c6e53-137">Set an expiration date for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||<span data-ttu-id="c6e53-138">根據預設，控制使用者顯示的共用連結類型。</span><span class="sxs-lookup"><span data-stu-id="c6e53-138">Control the type of sharing link shown to users by default.</span></span>|[<span data-ttu-id="c6e53-139">變更網站的預設連結類型</span><span class="sxs-lookup"><span data-stu-id="c6e53-139">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||<span data-ttu-id="c6e53-140">限制對特定人員的外部共用。</span><span class="sxs-lookup"><span data-stu-id="c6e53-140">Limit external sharing to specific people.</span></span>|[<span data-ttu-id="c6e53-141">限制對指定安全性群組的外部共用</span><span class="sxs-lookup"><span data-stu-id="c6e53-141">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||<span data-ttu-id="c6e53-142">根據資訊敏感度，控制對群組、小組或網站的來賓存取。</span><span class="sxs-lookup"><span data-stu-id="c6e53-142">Control guest access to a group, team, or site based on information sensitivity.</span></span>|[<span data-ttu-id="c6e53-143">使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容</span><span class="sxs-lookup"><span data-stu-id="c6e53-143">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="c6e53-144">關閉 [共用選項]。</span><span class="sxs-lookup"><span data-stu-id="c6e53-144">Turn off sharing options.</span></span>|[<span data-ttu-id="c6e53-145">在 Microsoft 365 中限制共用</span><span class="sxs-lookup"><span data-stu-id="c6e53-145">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|<span data-ttu-id="c6e53-146">使用者管理</span><span class="sxs-lookup"><span data-stu-id="c6e53-146">User management</span></span>|||
||<span data-ttu-id="c6e53-147">定期查看小組和群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="c6e53-147">Review team and group membership on a regular basis.</span></span>|[<span data-ttu-id="c6e53-148">何謂 Azure AD access 評論？</span><span class="sxs-lookup"><span data-stu-id="c6e53-148">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||<span data-ttu-id="c6e53-149">將存取管理自動化至群組和團隊。</span><span class="sxs-lookup"><span data-stu-id="c6e53-149">Automate access management to groups and teams.</span></span>|[<span data-ttu-id="c6e53-150">何謂 Azure AD 的權利管理？</span><span class="sxs-lookup"><span data-stu-id="c6e53-150">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||<span data-ttu-id="c6e53-151">允許或封鎖人員在小組中建立專用通道。</span><span class="sxs-lookup"><span data-stu-id="c6e53-151">Allow or block people from creating private channels in Teams.</span></span>|[<span data-ttu-id="c6e53-152">在 Microsoft 小組中管理專用通道的生命週期</span><span class="sxs-lookup"><span data-stu-id="c6e53-152">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a><span data-ttu-id="c6e53-153">[成員資格]</span><span class="sxs-lookup"><span data-stu-id="c6e53-153">Membership</span></span>

<span data-ttu-id="c6e53-154">小組和群組的成員資格是由擁有者所控制。</span><span class="sxs-lookup"><span data-stu-id="c6e53-154">Membership of teams and groups is controlled by owners.</span></span> <span data-ttu-id="c6e53-155">成員可以邀請其他人，但邀請會傳送給擁有者以供核准。</span><span class="sxs-lookup"><span data-stu-id="c6e53-155">Members can invite others, but the invitations are sent to owners for approval.</span></span> <span data-ttu-id="c6e53-156">雖然組織中的任何人都會發現公用團隊和群組，但您可以控制是否可探索私人團隊和群組：</span><span class="sxs-lookup"><span data-stu-id="c6e53-156">While public teams and groups are discoverable by anyone in the organization, you can control whether private teams and groups are discoverable:</span></span>

- [<span data-ttu-id="c6e53-157">管理 Microsoft 小組中的私營小組探索</span><span class="sxs-lookup"><span data-stu-id="c6e53-157">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

<span data-ttu-id="c6e53-158">您可以根據某些準則（例如部門），以動態方式管理群組或小組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="c6e53-158">You can manage membership of a group or team dynamically based on some criteria, such as department.</span></span> <span data-ttu-id="c6e53-159">在此情況下，成員和擁有者無法邀請人員加入小組。</span><span class="sxs-lookup"><span data-stu-id="c6e53-159">In this case, members and owners cannot invite people to the team.</span></span> <span data-ttu-id="c6e53-160">動態群組會使用您在 Azure Active Directory 中定義的中繼資料來控制群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c6e53-160">Dynamic groups uses metadata that you define in Azure Active Directory to control who is a member of the group.</span></span> <span data-ttu-id="c6e53-161">請確定您使用的中繼資料是完整的，且最新的是不正確的中繼資料，可能會導致使用者無法使用群組或加入不正確的使用者。</span><span class="sxs-lookup"><span data-stu-id="c6e53-161">Be sure the metadata that you're using is complete and up to date as incorrect metadata can lead to users being left out of groups or incorrect users being added.</span></span>

- [<span data-ttu-id="c6e53-162">在 Azure Active Directory 中建立或更新動態群組</span><span class="sxs-lookup"><span data-stu-id="c6e53-162">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

<span data-ttu-id="c6e53-163">SharePoint 網站可讓您加入群組或小組成員資格以外的人員、成員及訪客之外的功能。</span><span class="sxs-lookup"><span data-stu-id="c6e53-163">SharePoint sites provide the ability to add owners, members, and visitors apart from group or team membership.</span></span> <span data-ttu-id="c6e53-164">視您的需求而定，您可能會想要限制誰可以邀請人員加入網站。</span><span class="sxs-lookup"><span data-stu-id="c6e53-164">Depending on your requirements, you may want to restrict who can invite people to the site.</span></span> <span data-ttu-id="c6e53-165">此外，根據特定網站中資訊的靈敏度，您可能想要限制誰可以共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="c6e53-165">Also, depending on the sensitivity of the information in a given site, you may want to restrict who can share files and folder.</span></span> <span data-ttu-id="c6e53-166">這些限制是由小組、群組或網站擁有者所設定：</span><span class="sxs-lookup"><span data-stu-id="c6e53-166">These restrictions are configured by the team, group, or site owner:</span></span>

- [<span data-ttu-id="c6e53-167">設定及管理存取要求</span><span class="sxs-lookup"><span data-stu-id="c6e53-167">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a><span data-ttu-id="c6e53-168">條件式存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-168">Conditional access</span></span>

<span data-ttu-id="c6e53-169">使用 Microsoft 365，您可以對組織內部和外部的人員要求多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="c6e53-169">With Microsoft 365, you can require multi-factor authentication for both people inside and outside your organization.</span></span> <span data-ttu-id="c6e53-170">有許多選項會提示使用者輸入第二個驗證因素的情況。</span><span class="sxs-lookup"><span data-stu-id="c6e53-170">There are many options for the circumstances when people are prompted for a second factor of authentication.</span></span> <span data-ttu-id="c6e53-171">強烈建議您為組織部署多重要素驗證：</span><span class="sxs-lookup"><span data-stu-id="c6e53-171">We highly recommend that you deploy multi-factor authentication for your organization:</span></span>

- [<span data-ttu-id="c6e53-172">Azure AD Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="c6e53-172">Azure AD Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

<span data-ttu-id="c6e53-173">如果您的某些群組和小組有機密資訊，您可以根據群組或小組的靈敏度標籤強制執行裝置管理原則。</span><span class="sxs-lookup"><span data-stu-id="c6e53-173">If you have sensitive information in some of your groups and teams, you can enforce device management policies based on a group or team's sensitivity label.</span></span> <span data-ttu-id="c6e53-174">您可以完全封鎖非受管理裝置的存取，或僅允許有限的 web 存取：</span><span class="sxs-lookup"><span data-stu-id="c6e53-174">You can block access entirely from unmanaged devices, or allow limited, web only access:</span></span>

- [<span data-ttu-id="c6e53-175">使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容</span><span class="sxs-lookup"><span data-stu-id="c6e53-175">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="c6e53-176">在 SharePoint 中，您可以限制特定網路位置的網站存取權。</span><span class="sxs-lookup"><span data-stu-id="c6e53-176">In SharePoint, you can restrict access to sites from specified network locations.</span></span>

- [<span data-ttu-id="c6e53-177">根據網路位置控制對 SharePoint 和 OneDrive 資料的存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-177">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


<span data-ttu-id="c6e53-178">其他資源：</span><span class="sxs-lookup"><span data-stu-id="c6e53-178">Additional resources:</span></span>

- [<span data-ttu-id="c6e53-179">規劃條件式存取部署</span><span class="sxs-lookup"><span data-stu-id="c6e53-179">Plan a Conditional Access deployment</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [<span data-ttu-id="c6e53-180">Microsoft Intune 概述</span><span class="sxs-lookup"><span data-stu-id="c6e53-180">Microsoft Intune overview</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [<span data-ttu-id="c6e53-181">控制從非管理裝置 SharePoint 存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-181">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a><span data-ttu-id="c6e53-182">來賓存取</span><span class="sxs-lookup"><span data-stu-id="c6e53-182">Guest access</span></span>

<span data-ttu-id="c6e53-183">您可以根據電子郵件地址的網域來限制來賓。</span><span class="sxs-lookup"><span data-stu-id="c6e53-183">You can restrict guests based on the domain of their email address.</span></span> <span data-ttu-id="c6e53-184">SharePoint 提供整個組織和網站特有的網域限制設定。</span><span class="sxs-lookup"><span data-stu-id="c6e53-184">SharePoint offers organization-wide and site-specific domain restriction settings.</span></span> <span data-ttu-id="c6e53-185">群組和團隊使用 Azure AD 中的網域允許和拒絕清單。</span><span class="sxs-lookup"><span data-stu-id="c6e53-185">Groups and Teams use the domain allow and deny lists in Azure AD.</span></span> <span data-ttu-id="c6e53-186">請務必設定這兩項設定，以避免不必要的共用，並確保一致的使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="c6e53-186">Be sure to configure both settings to avoid unwanted sharing and ensure a consistent user experience:</span></span>

- [<span data-ttu-id="c6e53-187">依網域限制 SharePoint 和 OneDrive 內容的共用</span><span class="sxs-lookup"><span data-stu-id="c6e53-187">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [<span data-ttu-id="c6e53-188">允許或封鎖從特定組織 B2B 使用者的邀請</span><span class="sxs-lookup"><span data-stu-id="c6e53-188">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

<span data-ttu-id="c6e53-189">Microsoft 365 允許以共用連結的 *任何人* 匿名共用檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="c6e53-189">Microsoft 365 allows anonymous sharing of files and folders by using *Anyone* sharing links.</span></span> <span data-ttu-id="c6e53-190">可以轉寄 *任何人* 的連結，且具有連結的任何人都可以存取共用專案。</span><span class="sxs-lookup"><span data-stu-id="c6e53-190">*Anyone* links can be forwarded and anyone with the link can access the shared item.</span></span> <span data-ttu-id="c6e53-191">視您的資料敏感度而定，請考慮如何使用 *任何使用任何* 連結的連結-包括完全關閉，將連結許可權限制為唯讀，或為其設定到期時間：</span><span class="sxs-lookup"><span data-stu-id="c6e53-191">Depending on the sensitivity of your data, consider governing how *Anyone* links are used - including turning them off entirely, restricting link permissions to read-only, or setting an expiration time for them:</span></span>

- <span data-ttu-id="c6e53-192">[關閉 [任何人] 連結](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="c6e53-192">[Turn off Anyone links](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span></span>

- [<span data-ttu-id="c6e53-193">設定任何人的連結許可權連結</span><span class="sxs-lookup"><span data-stu-id="c6e53-193">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [<span data-ttu-id="c6e53-194">設定任何人連結的到期日</span><span class="sxs-lookup"><span data-stu-id="c6e53-194">Set an expiration date for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

<span data-ttu-id="c6e53-195">共用檔案或資料夾時，使用者可以選擇數種連結類型。</span><span class="sxs-lookup"><span data-stu-id="c6e53-195">When sharing files or folders, users have several link types to choose from.</span></span> <span data-ttu-id="c6e53-196">若要降低意外共用不當的風險，您可以變更使用者共用時呈現給使用者的預設連結類型。</span><span class="sxs-lookup"><span data-stu-id="c6e53-196">To reduce the risk of accidental inappropriate sharing, you can change the default link type presented to users when they share.</span></span> <span data-ttu-id="c6e53-197">例如，從 [ *任何人* ] 連結（可讓 *您的組織連結中* 的「匿名存取人員」）變更預設值，可降低敏感資訊不需要的外部共用共用風險。</span><span class="sxs-lookup"><span data-stu-id="c6e53-197">For example, changing the default from *Anyone* links - which allow anonymous access - to *People in your organization* links can reduce the risk of unwanted external sharing of sensitive information:</span></span>

- [<span data-ttu-id="c6e53-198">變更網站的預設連結類型</span><span class="sxs-lookup"><span data-stu-id="c6e53-198">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

<span data-ttu-id="c6e53-199">如果您的組織有需要與來賓共用的機密資料，但您卻擔心不適當的共用，您可以將檔案和資料夾的外部共用限制于指定之安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c6e53-199">If your organization has sensitive data that you need to share with guests, but you're concerned about inappropriate sharing, you can limit external sharing of files and folders to the members of specified security groups.</span></span> <span data-ttu-id="c6e53-200">如此一來，您就可以限制外部與特定人員群組共用，或要求您的使用者在將其新增至安全性群組之前，先進行適當的外部共用訓練：</span><span class="sxs-lookup"><span data-stu-id="c6e53-200">In this way, you can restrict sharing externally to a specific group of people, or require your users to take training around appropriate external sharing before adding them to the security group:</span></span>

- [<span data-ttu-id="c6e53-201">限制對指定安全性群組的外部共用</span><span class="sxs-lookup"><span data-stu-id="c6e53-201">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

<span data-ttu-id="c6e53-202">群組和團隊具有允許或拒絕來賓存取的組織層級設定。</span><span class="sxs-lookup"><span data-stu-id="c6e53-202">Groups and Teams have organization-level settings that allow or deny guest access.</span></span> <span data-ttu-id="c6e53-203">雖然您可以 [使用 Microsoft PowerShell 限制對特定小組或群組的 guest 存取](per-group-guest-access.md)，但我們建議您透過敏感度標籤來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c6e53-203">While you can [restrict guest access to specific teams or groups by using Microsoft PowerShell](per-group-guest-access.md), we recommend doing this by means of a sensitivity label.</span></span> <span data-ttu-id="c6e53-204">使用靈敏度標籤，您可以根據所套用的標籤自動允許或拒絕來賓存取：</span><span class="sxs-lookup"><span data-stu-id="c6e53-204">With sensitivity labels you can automatically allow or deny guest access based on the label applied:</span></span>

- [<span data-ttu-id="c6e53-205">使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容</span><span class="sxs-lookup"><span data-stu-id="c6e53-205">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="c6e53-206">在您經常邀請客人加入群組和小組的環境中，請考慮設定定期進行的「來賓存取」複查。</span><span class="sxs-lookup"><span data-stu-id="c6e53-206">In an environment where you frequently invite guests to groups and teams, consider setting up regularly scheduled guest access reviews.</span></span> <span data-ttu-id="c6e53-207">系統會提示擁有者查看群組和小組中的客人，以及核准或拒絕存取權。</span><span class="sxs-lookup"><span data-stu-id="c6e53-207">Owners can be prompted to review guests in their groups and teams and approve or deny access.</span></span>

- [<span data-ttu-id="c6e53-208">設定來賓存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="c6e53-208">Set up guest access reviews</span></span>](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

<span data-ttu-id="c6e53-209">Microsoft 365 提供許多不同的共用資訊方法。</span><span class="sxs-lookup"><span data-stu-id="c6e53-209">Microsoft 365 offers many different methods of sharing information.</span></span> <span data-ttu-id="c6e53-210">如果您有機密資訊，而且想要限制共用的方式，請參閱限制共用的選項：</span><span class="sxs-lookup"><span data-stu-id="c6e53-210">If you have sensitive information and you want to restrict how it's shared, review the options for limiting sharing:</span></span>

- [<span data-ttu-id="c6e53-211">在 Microsoft 365 中限制共用</span><span class="sxs-lookup"><span data-stu-id="c6e53-211">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

<span data-ttu-id="c6e53-212">其他資源：</span><span class="sxs-lookup"><span data-stu-id="c6e53-212">Additional resources:</span></span>

- [<span data-ttu-id="c6e53-213">使用 Microsoft 365 設定安全的共同作業</span><span class="sxs-lookup"><span data-stu-id="c6e53-213">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [<span data-ttu-id="c6e53-214">與未驗證使用者共用檔案和資料夾的最佳做法</span><span class="sxs-lookup"><span data-stu-id="c6e53-214">Best practices for sharing files and folders with unauthenticated users</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [<span data-ttu-id="c6e53-215">在與組織外的人員共用檔案時，限制資訊意外暴露</span><span class="sxs-lookup"><span data-stu-id="c6e53-215">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [<span data-ttu-id="c6e53-216">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="c6e53-216">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [<span data-ttu-id="c6e53-217">啟用 B2B 外部共同作業，並管理誰可以邀請來賓</span><span class="sxs-lookup"><span data-stu-id="c6e53-217">Enable B2B external collaboration and manage who can invite guests</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a><span data-ttu-id="c6e53-218">使用者管理</span><span class="sxs-lookup"><span data-stu-id="c6e53-218">User management</span></span>

<span data-ttu-id="c6e53-219">當組織中的群組和團隊演變時，很好的作法是定期查看小組和群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="c6e53-219">As groups and teams evolve in your organization, a good practice is to review team and group membership on a regular basis.</span></span> <span data-ttu-id="c6e53-220">對於具有變更成員資格的小組和群組、包含機密資訊的小組和群組，或包含來賓的小組和群組，這可能特別有用。</span><span class="sxs-lookup"><span data-stu-id="c6e53-220">This may be particularly useful for teams and groups with a changing membership, those that contain sensitive information, or those that include guests.</span></span> <span data-ttu-id="c6e53-221">請考慮為這些小組和群組設定存取權檢查：</span><span class="sxs-lookup"><span data-stu-id="c6e53-221">Consider setting up access reviews for these teams and groups:</span></span>

- [<span data-ttu-id="c6e53-222">何謂 Azure AD access 評論？</span><span class="sxs-lookup"><span data-stu-id="c6e53-222">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

<span data-ttu-id="c6e53-223">許多組織都與其他組織或主要廠商合作，其深度共同合作。</span><span class="sxs-lookup"><span data-stu-id="c6e53-223">Many organizations have business partnerships with other organizations or key vendors with whom they collaborate in depth.</span></span> <span data-ttu-id="c6e53-224">在這些案例中管理使用者管理和存取資源的難度很困難。</span><span class="sxs-lookup"><span data-stu-id="c6e53-224">User management and access to resources can be challenging to manage in these scenarios.</span></span> <span data-ttu-id="c6e53-225">請考慮自動化部分使用者管理工作，甚至將部分轉移至夥伴組織：</span><span class="sxs-lookup"><span data-stu-id="c6e53-225">Consider automating some of the user management tasks and even transitioning some of them to your partner organization:</span></span>

- [<span data-ttu-id="c6e53-226">何謂 Azure AD 的權利管理？</span><span class="sxs-lookup"><span data-stu-id="c6e53-226">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

<span data-ttu-id="c6e53-227">小組中的私人通道允許範圍內的交談和小組成員的子集間的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="c6e53-227">Private channels in Teams allow for scoped conversations and file sharing between a subset of team members.</span></span> <span data-ttu-id="c6e53-228">視您的特定業務需求而定，您可能會想要允許或封鎖此功能。</span><span class="sxs-lookup"><span data-stu-id="c6e53-228">Depending on your specific business needs, you may want to allow or block this capability.</span></span>

- [<span data-ttu-id="c6e53-229">Microsoft 小組中的專用通道</span><span class="sxs-lookup"><span data-stu-id="c6e53-229">Private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [<span data-ttu-id="c6e53-230">在 Microsoft 小組中管理專用通道的生命週期</span><span class="sxs-lookup"><span data-stu-id="c6e53-230">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

<span data-ttu-id="c6e53-231">其他資源：</span><span class="sxs-lookup"><span data-stu-id="c6e53-231">Additional resources:</span></span>

- [<span data-ttu-id="c6e53-232">Azure Active Directory 身分識別管理</span><span class="sxs-lookup"><span data-stu-id="c6e53-232">Azure Active Directory Identity Governance</span></span>](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a><span data-ttu-id="c6e53-233">相關主題</span><span class="sxs-lookup"><span data-stu-id="c6e53-233">Related topics</span></span>

[<span data-ttu-id="c6e53-234">共同作業管理規劃逐步</span><span class="sxs-lookup"><span data-stu-id="c6e53-234">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="c6e53-235">建立共同作業管理計畫</span><span class="sxs-lookup"><span data-stu-id="c6e53-235">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="c6e53-236">Microsoft Teams 中的安全性與合規性</span><span class="sxs-lookup"><span data-stu-id="c6e53-236">Security and compliance in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[<span data-ttu-id="c6e53-237">在 SharePoint 中管理共用設定</span><span class="sxs-lookup"><span data-stu-id="c6e53-237">Manage sharing settings in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[<span data-ttu-id="c6e53-238">在 Yammer 中建立及管理外部網路</span><span class="sxs-lookup"><span data-stu-id="c6e53-238">Create and manage an external network in Yammer</span></span>](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[<span data-ttu-id="c6e53-239">為 Teams 設定三層保護</span><span class="sxs-lookup"><span data-stu-id="c6e53-239">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
