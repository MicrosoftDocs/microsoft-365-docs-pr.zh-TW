---
title: 建議的團隊原則-Microsoft 365 for enterprise |Microsoft 檔
description: 說明有關如何保護小組通訊和檔案存取之 Microsoft 建議的原則。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 10/31/2019
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 41ead64a7a94dcd5afb22a311d7637326949fc7c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685651"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="361a5-103">保護小組聊天、群組和檔案的原則建議</span><span class="sxs-lookup"><span data-stu-id="361a5-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="361a5-104">本文說明如何執行建議的身分識別和裝置存取原則，以保護小組聊天、群組和內容，例如檔案和行事曆。</span><span class="sxs-lookup"><span data-stu-id="361a5-104">This article describes how to implement the recommended identity and device-access policies to protect Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="361a5-105">本指南以通用身分 [識別和裝置存取原則](identity-access-policies.md)為基礎，具有特定小組特有的額外資訊。</span><span class="sxs-lookup"><span data-stu-id="361a5-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="361a5-106">因為小組與我們的其他產品整合，另請參閱 [原則建議，以保護 SharePoint 網站和](sharepoint-file-access-policies.md) 檔案，以及 [保護電子郵件的原則建議](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="361a5-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="361a5-107">這些建議是以三種不同的安全性和保護層級為基礎，可根據您的需求細微性來套用這些小組：基準、機密和高管制。</span><span class="sxs-lookup"><span data-stu-id="361a5-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="361a5-108">您可以在身分 [識別和裝置存取](microsoft-365-policies-configurations.md)設定中深入瞭解這些安全層及這些建議所參照的建議原則。</span><span class="sxs-lookup"><span data-stu-id="361a5-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="361a5-109">本文中包含其他小組部署的相關建議，以涵蓋特定驗證的情況，包括組織外部的使用者。</span><span class="sxs-lookup"><span data-stu-id="361a5-109">Additional recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="361a5-110">您必須遵循此指導方針，才可取得完整的安全性體驗。</span><span class="sxs-lookup"><span data-stu-id="361a5-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="361a5-111">在其他相依服務之前快速開始使用團隊</span><span class="sxs-lookup"><span data-stu-id="361a5-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="361a5-112">您不需要啟用相依服務即可開始使用 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="361a5-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="361a5-113">這些都是「直接運作」。</span><span class="sxs-lookup"><span data-stu-id="361a5-113">These will all "just work."</span></span> <span data-ttu-id="361a5-114">不過，您必須準備好管理下列專案：</span><span class="sxs-lookup"><span data-stu-id="361a5-114">However, you do need to be prepared to manage the following:</span></span>

- <span data-ttu-id="361a5-115">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="361a5-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="361a5-116">SharePoint 小組網站</span><span class="sxs-lookup"><span data-stu-id="361a5-116">SharePoint team sites</span></span>
- <span data-ttu-id="361a5-117">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="361a5-117">OneDrive for Business</span></span>
- <span data-ttu-id="361a5-118">信箱</span><span class="sxs-lookup"><span data-stu-id="361a5-118">Mailboxes</span></span>
- <span data-ttu-id="361a5-119">Stream 影片和 Planner 方案 (若啟用這些服務) </span><span class="sxs-lookup"><span data-stu-id="361a5-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="361a5-120">將常見原則更新為包含小組</span><span class="sxs-lookup"><span data-stu-id="361a5-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="361a5-121">下圖說明在小組中保護聊天、群組和內容的建議原則集合。</span><span class="sxs-lookup"><span data-stu-id="361a5-121">The following diagram illustrates the set of recommended policies for protecting chat, groups and content in Teams.</span></span> <span data-ttu-id="361a5-122">鉛筆圖示會指出需要視的原則，以確保雲端應用程式的指派中包含小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-122">The pencil icon indicates which policies need to be revisited to be sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

![圖表顯示如何在各種裝置上使用 Microsoft 團隊。](../media/identity-access-ruleset-teams.png)

<span data-ttu-id="361a5-124">以下是要納入小組的雲端應用程式指派中的相依服務：</span><span class="sxs-lookup"><span data-stu-id="361a5-124">These are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="361a5-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="361a5-125">Microsoft Teams</span></span>
- <span data-ttu-id="361a5-126">SharePoint Online 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="361a5-126">SharePoint Online and OneDrive for Business</span></span>
- <span data-ttu-id="361a5-127">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="361a5-127">Exchange Online</span></span>
- <span data-ttu-id="361a5-128">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="361a5-128">Skype for Business Online</span></span>
- <span data-ttu-id="361a5-129">Microsoft Stream (會議錄製) </span><span class="sxs-lookup"><span data-stu-id="361a5-129">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="361a5-130">Microsoft Planner (Planner 工作和規劃資料) </span><span class="sxs-lookup"><span data-stu-id="361a5-130">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="361a5-131">此表格列出必須針對 [一般身分識別和裝置存取原則](identity-access-policies.md)中的每個原則進行存取的原則，以及所有 Office 應用程式的較寬規則集的連結。</span><span class="sxs-lookup"><span data-stu-id="361a5-131">This table lists the policies that need to be revisited and links to each policy in [Common identity and device access policies](identity-access-policies.md), which has the wider rule-set for all Office applications.</span></span>

|<span data-ttu-id="361a5-132">保護層級</span><span class="sxs-lookup"><span data-stu-id="361a5-132">Protection level</span></span>|<span data-ttu-id="361a5-133">原則</span><span class="sxs-lookup"><span data-stu-id="361a5-133">Policies</span></span>|<span data-ttu-id="361a5-134">小組實施的進一步資訊</span><span class="sxs-lookup"><span data-stu-id="361a5-134">Further information for Teams implementation</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="361a5-135">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="361a5-135">**Baseline**</span></span>|[<span data-ttu-id="361a5-136">當登入風險為*中*或*高*時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="361a5-136">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="361a5-137">請確定小組和相依服務均包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="361a5-137">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="361a5-138">小組也會考慮訪客存取和外部存取規則，您將在本文稍後深入瞭解這些規則。</span><span class="sxs-lookup"><span data-stu-id="361a5-138">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span>|
|        |[<span data-ttu-id="361a5-139">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="361a5-139">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="361a5-140">在雲應用程式的指派中包含小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-140">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
|        |[<span data-ttu-id="361a5-141">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="361a5-141">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="361a5-142">強制小組使用者在登入時，在其帳戶中偵測到高風險活動時變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="361a5-142">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="361a5-143">請確定小組和相依服務均包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="361a5-143">Be sure Teams and dependent services are included in the list of apps.</span></span>|
|        |[<span data-ttu-id="361a5-144">套用應用程式資料保護原則</span><span class="sxs-lookup"><span data-stu-id="361a5-144">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="361a5-145">請確定小組和相依服務均包含在應用程式清單中。</span><span class="sxs-lookup"><span data-stu-id="361a5-145">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="361a5-146">更新每個平臺 (iOS、Android、Windows) 的原則。</span><span class="sxs-lookup"><span data-stu-id="361a5-146">Update the policy for each platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="361a5-147">需要核准的應用程式和應用程式保護</span><span class="sxs-lookup"><span data-stu-id="361a5-147">Require approved apps and APP protection</span></span>](identity-access-policies.md#require-approved-apps-and-app-protection)|<span data-ttu-id="361a5-148">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-148">Include Teams and dependent services in this policy.</span></span>|
|        |[<span data-ttu-id="361a5-149">定義裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="361a5-149">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="361a5-150">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-150">Include Teams and dependent services in this policy.</span></span>|
|        |[<span data-ttu-id="361a5-151">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="361a5-151">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="361a5-152">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-152">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="361a5-153">**敏感度**</span><span class="sxs-lookup"><span data-stu-id="361a5-153">**Sensitive**</span></span>|[<span data-ttu-id="361a5-154">當登入風險為*低*、*中*或*高*時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="361a5-154">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="361a5-155">小組也會考慮訪客存取和外部存取規則，您將在本文稍後深入瞭解這些規則。</span><span class="sxs-lookup"><span data-stu-id="361a5-155">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span> <span data-ttu-id="361a5-156">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-156">Include Teams and dependent services in this policy.</span></span>|
|         |[<span data-ttu-id="361a5-157">需要相容 *的電腦和* 行動裝置</span><span class="sxs-lookup"><span data-stu-id="361a5-157">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="361a5-158">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-158">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="361a5-159">**高管制**</span><span class="sxs-lookup"><span data-stu-id="361a5-159">**Highly regulated**</span></span>|[<span data-ttu-id="361a5-160">*永遠* 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="361a5-160">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="361a5-161">不論使用者身分識別，您的組織都會使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="361a5-161">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="361a5-162">在此原則中包括小組和相依服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-162">Include Teams and dependent services in this policy.</span></span>
| | |

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="361a5-163">小組相依服務架構</span><span class="sxs-lookup"><span data-stu-id="361a5-163">Teams dependent services architecture</span></span>

<span data-ttu-id="361a5-164">為了供參考，下圖說明服務小組所依賴的服務。</span><span class="sxs-lookup"><span data-stu-id="361a5-164">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="361a5-165">如需詳細資訊及其他圖解，請參閱 microsoft [團隊和 microsoft 的相關生產力服務，請參閱 microsoft 365 FOR IT 架構設計](../solutions/productivity-illustrations.md)人員。</span><span class="sxs-lookup"><span data-stu-id="361a5-165">For more information and additional illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../solutions/productivity-illustrations.md).</span></span>

![此圖表顯示團隊對 SharePoint 線上、商務 OneDrive 和 Exchange 的相依性。](../media/identity-access-logical-architecture-teams.png)

## <a name="enabling-guest-and-external-access-for-teams"></a><span data-ttu-id="361a5-167">為小組啟用來賓和外部存取</span><span class="sxs-lookup"><span data-stu-id="361a5-167">Enabling guest and external access for Teams</span></span>

<span data-ttu-id="361a5-168">在 Azure AD 中，來賓和外部使用者皆相同。</span><span class="sxs-lookup"><span data-stu-id="361a5-168">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="361a5-169">這兩種皆為來賓的使用者類型。</span><span class="sxs-lookup"><span data-stu-id="361a5-169">The user type for both of these is Guest.</span></span> <span data-ttu-id="361a5-170">來賓使用者 B2B 使用者。</span><span class="sxs-lookup"><span data-stu-id="361a5-170">Guest users are B2B users.</span></span> <span data-ttu-id="361a5-171">Microsoft 小組區分來賓使用者和應用程式中的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="361a5-171">Microsoft Teams differentiates between guest users and external users in the app.</span></span> <span data-ttu-id="361a5-172">雖然瞭解各小組的各項處理方式很重要，但這兩種類型的使用者都是 Azure AD 中 B2B 使用者，而 B2B 使用者同時套用的建議原則，也是建議的原則。</span><span class="sxs-lookup"><span data-stu-id="361a5-172">While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.</span></span> <span data-ttu-id="361a5-173">如需允許來賓存取的建議原則，請參閱 [允許來賓和外部 B2B 存取的原則](identity-access-policies-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="361a5-173">For recommended policies to allow guest access, see [Policies for allowing guest and external B2B access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="361a5-174">小組中的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="361a5-174">Guest Access in Teams</span></span>

<span data-ttu-id="361a5-175">除了您公司或組織內部的使用者原則之外，管理員還可以讓來賓存取允許以使用者為基礎的使用者，在您的公司或組織外部的人員存取小組資源，並與內部人員（例如群組交談、聊天和會議）進行互動。</span><span class="sxs-lookup"><span data-stu-id="361a5-175">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span> <span data-ttu-id="361a5-176">您可以在下列連結中深入瞭解來賓存取： [小組訪客存取權](https://docs.microsoft.com/microsoftteams/guest-access)</span><span class="sxs-lookup"><span data-stu-id="361a5-176">You can learn more about Guest Access at the following link: [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access)</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="361a5-177">小組中的外部存取</span><span class="sxs-lookup"><span data-stu-id="361a5-177">External Access in Teams</span></span>

<span data-ttu-id="361a5-178">外部存取有時候會與來賓存取混淆，所以請務必明確這兩個非內部存取機制的實際差別很大。</span><span class="sxs-lookup"><span data-stu-id="361a5-178">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are actually quite different.</span></span> <span data-ttu-id="361a5-179">「來賓存取」是以每位使用者為基礎進行， (您一次新增一個使用者) ，當系統管理員啟用外部存取時，可讓您同時將外部網域的所有使用者新增至小組。</span><span class="sxs-lookup"><span data-stu-id="361a5-179">While guest access occurs on a per-user basis (you add one user at a time), when an administrator enables external access it allows you to add all the users of an external domain at the same time to Teams.</span></span> <span data-ttu-id="361a5-180">不過，這些外部使用者的存取權和功能，不如透過來賓存取新增的人員。</span><span class="sxs-lookup"><span data-stu-id="361a5-180">However those external users have less access and functionality than an individual who's been added via guest access would have.</span></span> <span data-ttu-id="361a5-181">外部存取使用者可以透過小組與您的內部使用者交談。</span><span class="sxs-lookup"><span data-stu-id="361a5-181">External access users can chat with your internal users via Teams.</span></span>

<span data-ttu-id="361a5-182">如需有關外部存取的詳細資訊，以及如何在需要時加以實施，請參閱 [管理 Microsoft 團隊中的外部存取](https://docs.microsoft.com/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="361a5-182">For more reading about external access, and how to implement it if you need to, please review [Manage external access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access)</span></span>

## <a name="teams-policies"></a><span data-ttu-id="361a5-183">小組原則</span><span class="sxs-lookup"><span data-stu-id="361a5-183">Teams Policies</span></span>

<span data-ttu-id="361a5-184">在上述一般原則之外，有一些小組特有的原則可和應設定，以管理各種小組功能。</span><span class="sxs-lookup"><span data-stu-id="361a5-184">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="361a5-185">小組和管道原則</span><span class="sxs-lookup"><span data-stu-id="361a5-185">Teams and Channels Policies</span></span>

<span data-ttu-id="361a5-186">小組和頻道是 Microsoft 小組中的兩個常用元素，也有一些原則可供您用來控制使用者使用團隊和管道時可以執行和不能執行的動作。</span><span class="sxs-lookup"><span data-stu-id="361a5-186">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="361a5-187">雖然您可以建立全域小組，但如果您的組織有5000位使用者或更少的使用者，您很可能會發現，使用小型小組和管道來滿足您的組織需求，以滿足特定目的。</span><span class="sxs-lookup"><span data-stu-id="361a5-187">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="361a5-188">建議您變更預設原則或建立自訂原則，您也可以深入瞭解如何管理您在此連結上的原則： [管理 Microsoft 小組中的團隊原則](https://docs.microsoft.com/microsoftteams/teams-policies)。</span><span class="sxs-lookup"><span data-stu-id="361a5-188">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="361a5-189">郵件原則</span><span class="sxs-lookup"><span data-stu-id="361a5-189">Messaging Policies</span></span>

<span data-ttu-id="361a5-190">您也可以透過預設全域原則或透過自訂原則來管理訊息或聊天，這可協助您的使用者以適合組織的方式與彼此進行通訊。</span><span class="sxs-lookup"><span data-stu-id="361a5-190">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="361a5-191">您可以在 [管理小組的郵件原則](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)時查看這項資訊。</span><span class="sxs-lookup"><span data-stu-id="361a5-191">This information can be reviewed at [Managing messaging policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="361a5-192">會議原則</span><span class="sxs-lookup"><span data-stu-id="361a5-192">Meeting Policies</span></span>

<span data-ttu-id="361a5-193">不需要在小組會議中規劃及實施原則，即可完成小組討論。</span><span class="sxs-lookup"><span data-stu-id="361a5-193">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="361a5-194">會議是小組的基本元件，可讓使用者正式開會及呈現給許多使用者，以及共用與會議相關的內容。</span><span class="sxs-lookup"><span data-stu-id="361a5-194">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, as well as share content relevant to the meeting.</span></span> <span data-ttu-id="361a5-195">在會議上為組織設定正確的原則是必要的。</span><span class="sxs-lookup"><span data-stu-id="361a5-195">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="361a5-196">如需詳細資訊，請參閱 [管理小組中的會議原則](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) 。</span><span class="sxs-lookup"><span data-stu-id="361a5-196">Please review [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) for more information.</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="361a5-197">應用程式許可權原則</span><span class="sxs-lookup"><span data-stu-id="361a5-197">App Permission Policies</span></span>

<span data-ttu-id="361a5-198">小組也可讓您在不同的地方使用應用程式，例如通道或個人聊天。</span><span class="sxs-lookup"><span data-stu-id="361a5-198">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="361a5-199">針對可以新增及使用哪些應用程式，以及在維護內容豐富的環境（也是安全）上都有哪些原則。</span><span class="sxs-lookup"><span data-stu-id="361a5-199">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="361a5-200">如需應用程式許可權原則的相關資訊，請參閱 [管理 Microsoft 小組中的應用程式許可權原則](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。</span><span class="sxs-lookup"><span data-stu-id="361a5-200">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="361a5-201">後續步驟</span><span class="sxs-lookup"><span data-stu-id="361a5-201">Next steps</span></span>

[<span data-ttu-id="361a5-202">瞭解如何為 Exchange Online 啟用條件式存取</span><span class="sxs-lookup"><span data-stu-id="361a5-202">Learn how to enable conditional access for Exchange Online</span></span>](secure-email-recommended-policies.md)


