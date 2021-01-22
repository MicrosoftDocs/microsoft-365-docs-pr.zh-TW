---
title: 允許來賓和外部使用者 B2B 存取的身分識別與裝置存取政策 - 適用于企業使用者的 Microsoft 365 |Microsoft Docs
description: 說明建議的條件式存取和相關策略，以保護來賓和外部使用者的存取。
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932607"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="c7afc-103">允許來賓存取和 B2B 外部使用者存取的策略</span><span class="sxs-lookup"><span data-stu-id="c7afc-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="c7afc-104">本文將討論調整建議的裝置和身分識別存取策略，以允許擁有 Azure Active Directory (Azure AD) 企業對企業 (B2B) 帳戶的來賓和外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="c7afc-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="c7afc-105">本指引以一 [般身分識別與裝置存取策略為根據](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c7afc-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="c7afc-106">這些建議是設計成 **適用于基礎保護** 層級。</span><span class="sxs-lookup"><span data-stu-id="c7afc-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="c7afc-107">但您也可以根據您的特定需求調整對敏感和高度受規範 **之保護的建議**。 </span><span class="sxs-lookup"><span data-stu-id="c7afc-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="c7afc-108">提供 B2B 帳戶與 Azure AD 租使用者進行驗證的路徑，不會讓這些帳戶存取整個環境。</span><span class="sxs-lookup"><span data-stu-id="c7afc-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="c7afc-109">B2B 使用者及其帳戶可以存取服務和資源，例如檔案，可條件式存取策略與使用者共用。</span><span class="sxs-lookup"><span data-stu-id="c7afc-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="c7afc-110">更新共同策略以允許及保護來賓與外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="c7afc-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="c7afc-111">此圖表顯示針對 B2B 來賓和外部使用者存取，在一般身分識別與裝置存取策略之間新增或更新哪些策略。</span><span class="sxs-lookup"><span data-stu-id="c7afc-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="c7afc-112">[![保護來賓存取之策略更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="c7afc-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="c7afc-113">查看此影像的較大版本</span><span class="sxs-lookup"><span data-stu-id="c7afc-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="c7afc-114">下表列出您需要建立及更新的策略。</span><span class="sxs-lookup"><span data-stu-id="c7afc-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="c7afc-115">共同策略會連結至共同身分識別與裝置存取策略文章中的相關 [組組](identity-access-policies.md) 指示。</span><span class="sxs-lookup"><span data-stu-id="c7afc-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="c7afc-116">保護層級</span><span class="sxs-lookup"><span data-stu-id="c7afc-116">Protection level</span></span>|<span data-ttu-id="c7afc-117">原則</span><span class="sxs-lookup"><span data-stu-id="c7afc-117">Policies</span></span>|<span data-ttu-id="c7afc-118">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="c7afc-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="c7afc-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="c7afc-119">**Baseline**</span></span>|[<span data-ttu-id="c7afc-120">一向要求來賓和外部使用者使用 MFA</span><span class="sxs-lookup"><span data-stu-id="c7afc-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c7afc-121">建立此新策略，並設定：</span><span class="sxs-lookup"><span data-stu-id="c7afc-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="c7afc-122">針對 **指派>** 包括使用者>群組，選擇選取使用者和群組，然後選取所有 **來賓和外部使用者**。</span><span class="sxs-lookup"><span data-stu-id="c7afc-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="c7afc-123">針對 **>與**>，請取消核>所有選項，以在 MFA 中一 (多重要素驗證) 。</span><span class="sxs-lookup"><span data-stu-id="c7afc-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="c7afc-124">當登錄風險中或高 *時需要* MFA</span><span class="sxs-lookup"><span data-stu-id="c7afc-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c7afc-125">修改此策略以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="c7afc-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="c7afc-126">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="c7afc-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="c7afc-127">修改此策略以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="c7afc-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="c7afc-128">若要在條件式存取策略中納入或排除來賓和外部使用者，請針對工作分派>使用者和群組>**包括** 或排除，請勾選所有 **來賓和外部使用者**。</span><span class="sxs-lookup"><span data-stu-id="c7afc-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![排除來賓和外部使用者之控制項的螢幕畫面](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="c7afc-130">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="c7afc-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="c7afc-131">使用 Microsoft Teams 的來賓和外部使用者存取權</span><span class="sxs-lookup"><span data-stu-id="c7afc-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="c7afc-132">Microsoft Teams 定義下列使用者：</span><span class="sxs-lookup"><span data-stu-id="c7afc-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="c7afc-133">**來賓存取** 會使用 Azure AD B2B 帳戶，可新增為團隊的成員，並存取團隊的通訊和資源。</span><span class="sxs-lookup"><span data-stu-id="c7afc-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="c7afc-134">**外部存取** 適用于沒有 B2B 帳戶的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="c7afc-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="c7afc-135">外部使用者存取包含邀請、通話、聊天和會議，但不包括團隊成員資格和團隊資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="c7afc-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="c7afc-136">有關詳細資訊，請參閱團隊 [的來賓與外部使用者存取權之間的比較](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="c7afc-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="c7afc-137">有關保護 Teams 的身分識別與裝置存取策略，請參閱保護 Teams 聊天、群組和檔案安全之政策 [建議](teams-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c7afc-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="c7afc-138">一向要求來賓和外部使用者使用 MFA</span><span class="sxs-lookup"><span data-stu-id="c7afc-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="c7afc-139">此政策會提示來賓在租使用者中註冊 MFA，不論他們是否已在家庭租使用者中註冊 MFA。</span><span class="sxs-lookup"><span data-stu-id="c7afc-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="c7afc-140">存取您租使用者中的資源時，來賓和外部使用者必須針對每個要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="c7afc-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="c7afc-141">將來賓和外部使用者排除在風險型 MFA 之外</span><span class="sxs-lookup"><span data-stu-id="c7afc-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="c7afc-142">雖然組織可以針對使用 Azure AD 身分識別保護的 B2B 使用者強制執行以風險為基礎的策略，但是針對 B2B 共同合作使用者在資原始目錄中的身分識別，而其 Azure AD 身分識別保護的執行有一些限制。</span><span class="sxs-lookup"><span data-stu-id="c7afc-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="c7afc-143">由於這些限制，Microsoft 建議您將來賓排除在以風險為基礎的 MFA 政策外，並要求這些使用者永遠使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="c7afc-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="c7afc-144">詳細資訊請參閱 [B2B 共同合作使用者身分識別保護的限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="c7afc-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="c7afc-145">從裝置管理中排除來賓和外部使用者</span><span class="sxs-lookup"><span data-stu-id="c7afc-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="c7afc-146">只有一個組織可以管理裝置。</span><span class="sxs-lookup"><span data-stu-id="c7afc-146">Only one organization can manage a device.</span></span> <span data-ttu-id="c7afc-147">如果您不將來賓和外部使用者排除在需要裝置合規性的政策外，則那些政策會封鎖這些使用者。</span><span class="sxs-lookup"><span data-stu-id="c7afc-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="c7afc-148">下一步</span><span class="sxs-lookup"><span data-stu-id="c7afc-148">Next step</span></span>

![步驟 4：Microsoft 365 雲端應用程式政策](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="c7afc-150">設定條件式存取策略：</span><span class="sxs-lookup"><span data-stu-id="c7afc-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="c7afc-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7afc-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="c7afc-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c7afc-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="c7afc-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c7afc-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
