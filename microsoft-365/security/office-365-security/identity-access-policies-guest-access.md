---
title: 身分識別和裝置存取原則，允許來賓和外部使用者 B2B 存取-Microsoft 365 for enterprise |Microsoft 檔
description: 描述建議的條件式存取和相關原則，以保護來賓和外部使用者的存取。
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
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203500"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="d7f1c-103">允許來賓存取和 B2B 外部使用者存取的原則</span><span class="sxs-lookup"><span data-stu-id="d7f1c-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="d7f1c-104">本文討論如何調整建議的裝置和身分識別存取原則，以允許具有 Azure Active Directory (Azure AD) 企業對企業 (B2B) 帳戶的來賓和外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="d7f1c-105">本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="d7f1c-106">這些建議適用于保護的 **基準** 層。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="d7f1c-107">不過，您也可以根據您對 **機密** 和 **高管制** 保護的特定需求來調整建議。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="d7f1c-108">提供 B2B 帳戶的路徑，以與您的 Azure AD 租使用者進行驗證，不會讓這些帳戶存取您的整個環境。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="d7f1c-109">B2B 使用者和其帳戶可以存取服務和資源（如檔案），並以條件式存取原則與其共用。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="d7f1c-110">更新共同原則以允許及保護來賓和外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="d7f1c-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="d7f1c-111">此圖顯示在通用身分識別和裝置存取原則中，為 B2B 來賓和外部使用者存取新增或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="d7f1c-112">[![保護來賓存取的原則更新摘要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="d7f1c-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="d7f1c-113">下表列出您需要建立和更新的原則。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="d7f1c-114">通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="d7f1c-115">保護層級</span><span class="sxs-lookup"><span data-stu-id="d7f1c-115">Protection level</span></span>|<span data-ttu-id="d7f1c-116">原則</span><span class="sxs-lookup"><span data-stu-id="d7f1c-116">Policies</span></span>|<span data-ttu-id="d7f1c-117">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d7f1c-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="d7f1c-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="d7f1c-118">**Baseline**</span></span>|[<span data-ttu-id="d7f1c-119">需要對來賓和外部使用者無條件進行 MFA</span><span class="sxs-lookup"><span data-stu-id="d7f1c-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="d7f1c-120">建立這個新原則，並設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="d7f1c-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="d7f1c-121">若為 **> 使用者和群組 > 包含的工作分派**，請選擇 [ **選取使用者和群組**]，然後選取 [ **所有來賓和外部使用者**]。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="d7f1c-122">**> 條件的工作分派 > 登入**，請將所有選項保留未勾選狀態，以永遠強制執行多重要素驗證 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="d7f1c-123">當登入風險為 *中* 或 *高* 時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="d7f1c-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="d7f1c-124">修改此原則，以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="d7f1c-125">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="d7f1c-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="d7f1c-126">修改此原則，以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="d7f1c-127">若要在條件式存取原則中包含或排除來賓和外部使用者，針對 **> 使用者和群組 > 包含** 或 **排除** 的工作分派，請檢查 **所有來賓和外部使用者**。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![用於排除來賓和外部使用者的控制項的畫面捕獲](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="d7f1c-129">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="d7f1c-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="d7f1c-130">來賓和 Microsoft 小組的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="d7f1c-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="d7f1c-131">Microsoft 小組定義下列使用者：</span><span class="sxs-lookup"><span data-stu-id="d7f1c-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="d7f1c-132">**來賓存取** 使用 Azure AD B2B 帳戶，可將其新增為小組成員，並可存取小組的通訊和資源。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="d7f1c-133">**外部存取** 適用于沒有 B2B 帳戶的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="d7f1c-134">外部使用者存取包括邀請、通話、聊天和會議，但不包括小組成員資格和對小組資源的存取。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="d7f1c-135">如需詳細資訊，請參閱 [來賓和團隊外部使用者存取之間的比較](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="d7f1c-136">如需安全小組之身分識別與裝置存取原則的詳細資訊，請參閱 [保護小組聊天、群組和檔案的原則建議](teams-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="d7f1c-137">需要對來賓和外部使用者永遠進行 MFA</span><span class="sxs-lookup"><span data-stu-id="d7f1c-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="d7f1c-138">此原則會提示客人在您的租使用者中註冊 MFA，不論他們是否已在其主承租人中為 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="d7f1c-139">當存取您租使用者中的資源時，來賓和外部使用者必須針對每個要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="d7f1c-140">從風險型 MFA 排除來賓和外部使用者</span><span class="sxs-lookup"><span data-stu-id="d7f1c-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="d7f1c-141">雖然組織可以對使用 Azure AD 身分識別保護的 B2B 使用者強制執行風險原則原則，但由於其內部目錄中的現有身分識別，對資原始目錄中 B2B 共同作業使用者執行 Azure AD 身分識別保護有一些限制。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="d7f1c-142">由於這些限制，Microsoft 建議您從風險型 MFA 原則中排除來賓，並要求這些使用者永遠使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="d7f1c-143">如需詳細資訊，請參閱 [B2B 協同作業使用者的身分識別保護限制](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="d7f1c-144">從裝置管理排除來賓和外部使用者</span><span class="sxs-lookup"><span data-stu-id="d7f1c-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="d7f1c-145">只有一個組織可以管理裝置。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-145">Only one organization can manage a device.</span></span> <span data-ttu-id="d7f1c-146">如果您未從需要裝置規範的原則中排除來賓和外部使用者，這些原則將會封鎖這些使用者。</span><span class="sxs-lookup"><span data-stu-id="d7f1c-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="d7f1c-147">下一步</span><span class="sxs-lookup"><span data-stu-id="d7f1c-147">Next step</span></span>

![步驟4： Microsoft 365 雲端應用程式的原則](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="d7f1c-149">為下列專案設定條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="d7f1c-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="d7f1c-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7f1c-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="d7f1c-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d7f1c-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="d7f1c-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d7f1c-152">SharePoint</span></span>](sharepoint-file-access-policies.md)