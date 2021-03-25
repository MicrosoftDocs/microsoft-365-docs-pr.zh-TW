---
title: 建議的團隊原則-Microsoft 365 for enterprise |Microsoft 檔
description: 說明有關如何保護小組通訊和檔案存取之 Microsoft 建議的原則。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 51dec80c541cd77a1d4813505d82429487e8381c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204615"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="9ab6b-103">保護小組聊天、群組和檔案的原則建議</span><span class="sxs-lookup"><span data-stu-id="9ab6b-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="9ab6b-104">本文說明如何執行建議的身分識別和裝置存取原則，以保護 Microsoft 團隊聊天、群組和內容（如檔案和行事曆）。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="9ab6b-105">本指南以通用身分 [識別和裝置存取原則](identity-access-policies.md)為基礎，具有特定小組特有的額外資訊。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="9ab6b-106">因為小組與我們的其他產品整合，另請參閱 [原則建議，以保護 SharePoint 網站和](sharepoint-file-access-policies.md) 檔案，以及 [保護電子郵件的原則建議](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="9ab6b-107">這些建議是以三種不同的安全性和保護層級為基礎，可根據您的需求細微性來套用這些小組：基準、機密和高管制。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="9ab6b-108">您可以在身分 [識別和裝置存取](microsoft-365-policies-configurations.md)設定中深入瞭解這些安全層及這些建議所參照的建議原則。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="9ab6b-109">本文所含的團隊部署的相關建議如下所述，以涵蓋特定驗證的情況，包括組織外部的使用者。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-109">More recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="9ab6b-110">您必須遵循此指導方針，才可取得完整的安全性體驗。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="9ab6b-111">在其他相依服務之前快速開始使用團隊</span><span class="sxs-lookup"><span data-stu-id="9ab6b-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="9ab6b-112">您不需要啟用相依服務即可開始使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="9ab6b-113">這些服務全部都是「運作」。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-113">These services will all "just work."</span></span> <span data-ttu-id="9ab6b-114">不過，您必須準備好管理下列服務相關元素：</span><span class="sxs-lookup"><span data-stu-id="9ab6b-114">However, you do need to be prepared to manage the following service-related elements:</span></span>

- <span data-ttu-id="9ab6b-115">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="9ab6b-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="9ab6b-116">SharePoint 小組網站</span><span class="sxs-lookup"><span data-stu-id="9ab6b-116">SharePoint team sites</span></span>
- <span data-ttu-id="9ab6b-117">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="9ab6b-117">OneDrive for Business</span></span>
- <span data-ttu-id="9ab6b-118">Exchange 信箱</span><span class="sxs-lookup"><span data-stu-id="9ab6b-118">Exchange mailboxes</span></span>
- <span data-ttu-id="9ab6b-119">Stream 影片和 Planner 方案 (若啟用這些服務) </span><span class="sxs-lookup"><span data-stu-id="9ab6b-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="9ab6b-120">將常見原則更新為包含小組</span><span class="sxs-lookup"><span data-stu-id="9ab6b-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="9ab6b-121">為了保護「聊天」、群組及小組內容，下列圖表說明要從通用身分識別和裝置存取原則更新哪些原則。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="9ab6b-122">針對每個要更新的原則，請確定 cloud app 的指派中包含小組和相依的服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="9ab6b-123">[![保護對小組及其相依服務之存取的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="9ab6b-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

<span data-ttu-id="9ab6b-124">這些服務是可納入小組的雲端應用程式指派中的相依服務：</span><span class="sxs-lookup"><span data-stu-id="9ab6b-124">These services are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="9ab6b-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9ab6b-125">Microsoft Teams</span></span>
- <span data-ttu-id="9ab6b-126">SharePoint 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="9ab6b-126">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="9ab6b-127">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9ab6b-127">Exchange Online</span></span>
- <span data-ttu-id="9ab6b-128">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="9ab6b-128">Skype for Business Online</span></span>
- <span data-ttu-id="9ab6b-129">Microsoft Stream (會議錄製) </span><span class="sxs-lookup"><span data-stu-id="9ab6b-129">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="9ab6b-130">Microsoft Planner (Planner 工作和規劃資料) </span><span class="sxs-lookup"><span data-stu-id="9ab6b-130">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="9ab6b-131">此表格列出必須針對 [一般身分識別和裝置存取原則](identity-access-policies.md)中的每個原則所進行的原則，以及所有 Office 應用程式的更大原則設定的連結。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-131">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="9ab6b-132">保護層級</span><span class="sxs-lookup"><span data-stu-id="9ab6b-132">Protection level</span></span>|<span data-ttu-id="9ab6b-133">原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-133">Policies</span></span>|<span data-ttu-id="9ab6b-134">小組實施的進一步資訊</span><span class="sxs-lookup"><span data-stu-id="9ab6b-134">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="9ab6b-135">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="9ab6b-135">**Baseline**</span></span>|[<span data-ttu-id="9ab6b-136">當登入風險為 *中* 或 *高* 時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="9ab6b-136">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="9ab6b-137">請確定小組和相依服務均包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-137">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="9ab6b-138">小組也會考慮訪客存取和外部存取規則，您將在本文稍後深入瞭解這些規則。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-138">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span>|
||[<span data-ttu-id="9ab6b-139">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="9ab6b-139">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="9ab6b-140">在雲應用程式的指派中包含小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-140">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="9ab6b-141">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="9ab6b-141">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="9ab6b-142">強制小組使用者在登入時，在其帳戶中偵測到高風險活動時變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-142">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="9ab6b-143">請確定小組和相依服務均包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-143">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="9ab6b-144">套用應用程式資料保護原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-144">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="9ab6b-145">請確定小組和相依服務均包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-145">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="9ab6b-146">更新每個平臺 (iOS、Android、Windows) 的原則。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-146">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="9ab6b-147">定義裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-147">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="9ab6b-148">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-148">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="9ab6b-149">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="9ab6b-149">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="9ab6b-150">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-150">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="9ab6b-151">**敏感度**</span><span class="sxs-lookup"><span data-stu-id="9ab6b-151">**Sensitive**</span></span>|[<span data-ttu-id="9ab6b-152">當登入風險為 *低*、*中* 或 *高* 時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="9ab6b-152">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="9ab6b-153">小組也會考慮訪客存取和外部存取規則，您將在本文稍後深入瞭解這些規則。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-153">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span> <span data-ttu-id="9ab6b-154">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-154">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="9ab6b-155">需要相容 *的電腦和* 行動裝置</span><span class="sxs-lookup"><span data-stu-id="9ab6b-155">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="9ab6b-156">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-156">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="9ab6b-157">**高管制**</span><span class="sxs-lookup"><span data-stu-id="9ab6b-157">**Highly regulated**</span></span>|[<span data-ttu-id="9ab6b-158">*永遠* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="9ab6b-158">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="9ab6b-159">不論使用者身分識別，您的組織都會使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-159">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="9ab6b-160">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-160">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="9ab6b-161">小組相依服務架構</span><span class="sxs-lookup"><span data-stu-id="9ab6b-161">Teams dependent services architecture</span></span>

<span data-ttu-id="9ab6b-162">為了供參考，下圖說明服務小組所依賴的服務。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-162">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="9ab6b-163">如需詳細資訊和圖例，請參閱 microsoft [小組和 microsoft 365 的相關生產力服務，以供 IT 架構設計](../../solutions/productivity-illustrations.md)人員參考。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-163">For more information and illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="9ab6b-164">[![圖表顯示團隊對 SharePoint、商務 OneDrive 和 Exchange 的相依性依賴性](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="9ab6b-164">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="9ab6b-165">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="9ab6b-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="9ab6b-166">團隊的來賓和外部存取權</span><span class="sxs-lookup"><span data-stu-id="9ab6b-166">Guest and external access for Teams</span></span>

<span data-ttu-id="9ab6b-167">Microsoft 小組定義下列訪問類型：</span><span class="sxs-lookup"><span data-stu-id="9ab6b-167">Microsoft Teams defines the following access types:</span></span>

- <span data-ttu-id="9ab6b-168">**來賓存取** 針對來賓或外部使用者使用 Azure AD B2B 帳戶，可將其新增為小組成員，並擁有對該小組之通訊和資源的所有專屬許可權存取權。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-168">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="9ab6b-169">**外部存取** 適用于沒有 Azure AD B2B 帳戶的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-169">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="9ab6b-170">外部存取可以包含邀請，並參與通話、聊天和會議，但不包括小組成員資格和對小組資源的存取。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-170">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="9ab6b-171">條件式存取原則只適用于小組中的來賓存取，因為有對應的 Azure AD B2B 帳戶。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-171">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="9ab6b-172">如需允許使用 Azure AD B2B 帳戶存取來賓和外部使用者的建議原則，請參閱 [允許來賓和外部 B2B 帳戶存取的原則](identity-access-policies-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-172">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="9ab6b-173">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="9ab6b-173">Guest access in Teams</span></span>

<span data-ttu-id="9ab6b-174">除了您公司或組織內部的使用者原則之外，管理員還可以讓來賓存取允許以使用者為基礎的使用者，在您的公司或組織外部的人員存取小組資源，並與內部人員（例如群組交談、聊天和會議）進行互動。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-174">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="9ab6b-175">如需來賓存取及其實施方式的詳細資訊，請參閱  [小組訪客存取](/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-175">For more information about guest access and how to implement it, see  [Teams guest access](/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="9ab6b-176">小組中的外部存取</span><span class="sxs-lookup"><span data-stu-id="9ab6b-176">External access in Teams</span></span>

<span data-ttu-id="9ab6b-177">外部存取有時候會與來賓存取混淆，所以請務必明確這兩種非內部存取機制是不同的存取類型。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-177">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are different types of access.</span></span>

<span data-ttu-id="9ab6b-178">「外部存取」是一種方法，讓團隊使用者可以從整個外部網域尋找、呼叫、聊天及設定小組中的使用者的會議。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-178">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="9ab6b-179">小組管理員會設定組織層級的外部存取。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-179">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="9ab6b-180">如需詳細資訊，請參閱 [管理 Microsoft 團隊中的外部存取](/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-180">For more information, see [Manage external access in Microsoft Teams](/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="9ab6b-181">外部存取使用者與透過來賓存取新增的人員相比，具有較少的存取權和功能。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-181">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="9ab6b-182">例如，外部存取使用者可以與內部使用者聊天，但無法存取小組通道、檔案或其他資源。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-182">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="9ab6b-183">外部存取不使用 Azure AD B2B 使用者帳戶，因此不會使用條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-183">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="9ab6b-184">小組原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-184">Teams policies</span></span>

<span data-ttu-id="9ab6b-185">在上述一般原則之外，有一些小組特有的原則可和應設定，以管理各種小組功能。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-185">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="9ab6b-186">小組和管道原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-186">Teams and channels policies</span></span>

<span data-ttu-id="9ab6b-187">小組和頻道是 Microsoft 小組中的兩個常用元素，也有一些原則可供您用來控制使用者使用團隊和管道時可以執行和不能執行的動作。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-187">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="9ab6b-188">雖然您可以建立全域小組，但如果您的組織有5000位使用者或更少的使用者，您很可能會發現，使用小型小組和管道來滿足您的組織需求，以滿足特定目的。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-188">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="9ab6b-189">建議您變更預設原則或建立自訂原則，您也可以深入瞭解如何管理您在此連結上的原則： [管理 Microsoft 小組中的團隊原則](/microsoftteams/teams-policies)。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-189">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="9ab6b-190">郵件原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-190">Messaging policies</span></span>

<span data-ttu-id="9ab6b-191">您也可以透過預設全域原則或透過自訂原則來管理訊息或聊天，這可協助您的使用者以適合組織的方式與彼此進行通訊。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-191">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="9ab6b-192">您可以在 [管理小組的郵件原則](/microsoftteams/messaging-policies-in-teams)時查看這項資訊。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-192">This information can be reviewed at [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="9ab6b-193">會議原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-193">Meeting policies</span></span>

<span data-ttu-id="9ab6b-194">不需要在小組會議中規劃及實施原則，即可完成小組討論。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-194">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="9ab6b-195">會議是小組的基本元件，可讓使用者正式開會及呈現給許多使用者，以及共用會議相關的內容。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-195">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, and to share content relevant to the meeting.</span></span> <span data-ttu-id="9ab6b-196">在會議上為組織設定正確的原則是必要的。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-196">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="9ab6b-197">如需詳細資訊，請參閱 [管理小組中的會議原則](/microsoftteams/meeting-policies-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-197">For more information, review [Manage meeting policies in Teams](/microsoftteams/meeting-policies-in-teams).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="9ab6b-198">應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="9ab6b-198">App permission policies</span></span>

<span data-ttu-id="9ab6b-199">小組也可讓您在不同的地方使用應用程式，例如通道或個人聊天。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-199">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="9ab6b-200">針對可以新增及使用哪些應用程式，以及在維護內容豐富的環境（也是安全）上都有哪些原則。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-200">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="9ab6b-201">如需應用程式許可權原則的相關資訊，請參閱 [管理 Microsoft 小組中的應用程式許可權原則](/microsoftteams/teams-app-permission-policies)。</span><span class="sxs-lookup"><span data-stu-id="9ab6b-201">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ab6b-202">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9ab6b-202">Next steps</span></span>

![步驟4： Microsoft 365 雲端應用程式的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="9ab6b-204">為下列專案設定條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="9ab6b-204">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="9ab6b-205">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9ab6b-205">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="9ab6b-206">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ab6b-206">SharePoint</span></span>](sharepoint-file-access-policies.md)