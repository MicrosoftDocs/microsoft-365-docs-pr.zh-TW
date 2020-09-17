---
title: 允許來賓和外部 B2B 存取的身分識別和裝置存取原則-Microsoft 365 for enterprise |Microsoft 檔
description: 描述建議的條件式存取和相關原則，以保護來賓和外部使用者的存取。
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c61526139111885ec345bc4a4dd3cd6b147370e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950805"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="b989e-103">允許來賓和外部 B2B 存取的原則</span><span class="sxs-lookup"><span data-stu-id="b989e-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="b989e-104">本文說明如何調整建議的常見身分識別和裝置存取原則，以允許商務對企業 (B2B) 帳戶存取 (來賓和外部使用者) 。</span><span class="sxs-lookup"><span data-stu-id="b989e-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="b989e-105">本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。</span><span class="sxs-lookup"><span data-stu-id="b989e-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="b989e-106">這些建議適用于保護的 **基準** 層。</span><span class="sxs-lookup"><span data-stu-id="b989e-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="b989e-107">不過，您也可以依據 **敏感** 和 **高管制** 保護的需求細微性來調整建議。</span><span class="sxs-lookup"><span data-stu-id="b989e-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="b989e-108">提供路徑供 B2B 使用者向您的 Azure Active Directory (Azure AD) 承租人進行驗證時，不會讓這些使用者存取您的整個環境。</span><span class="sxs-lookup"><span data-stu-id="b989e-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="b989e-109">B2B 使用者只能存取與其共用的資源 (例如，在條件式存取原則中授與服務內) 的檔案。</span><span class="sxs-lookup"><span data-stu-id="b989e-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="b989e-110">更新共同原則以允許及保護來賓和外部存取</span><span class="sxs-lookup"><span data-stu-id="b989e-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="b989e-111">為了保護來賓和外部存取，下列圖表說明要從通用身分識別和裝置存取原則中新增或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="b989e-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="b989e-112">[![保護來賓存取的原則更新摘要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="b989e-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="b989e-113">查看較大版本的此影像</span><span class="sxs-lookup"><span data-stu-id="b989e-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="b989e-114">下表列出您必須更新或建立的原則。</span><span class="sxs-lookup"><span data-stu-id="b989e-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="b989e-115">通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。</span><span class="sxs-lookup"><span data-stu-id="b989e-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="b989e-116">保護層級</span><span class="sxs-lookup"><span data-stu-id="b989e-116">Protection level</span></span>|<span data-ttu-id="b989e-117">原則</span><span class="sxs-lookup"><span data-stu-id="b989e-117">Policies</span></span>|<span data-ttu-id="b989e-118">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b989e-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="b989e-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="b989e-119">**Baseline**</span></span>|[<span data-ttu-id="b989e-120">需要對來賓和外部使用者永遠進行 MFA</span><span class="sxs-lookup"><span data-stu-id="b989e-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="b989e-121">建立此新原則，並將其套用至來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b989e-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="b989e-122">在 [登 **入風險**] 下，將所有選項保留未勾選狀態，以永遠強制執行多重要素驗證 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="b989e-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="b989e-123">當登入風險為*中*或*高*時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b989e-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="b989e-124">修改此原則，以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b989e-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="b989e-125">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="b989e-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="b989e-126">修改此原則，以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b989e-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="b989e-127">若要在條件式存取原則中包含或排除來賓和外部使用者，請按一下 [ **包含** 或 **排除** ] 索引標籤，並檢查 **所有來賓和外部使用者**。</span><span class="sxs-lookup"><span data-stu-id="b989e-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![用於排除來賓之控制項的畫面捕獲](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="b989e-129">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b989e-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="b989e-130">來賓與外部使用者</span><span class="sxs-lookup"><span data-stu-id="b989e-130">Guests vs. external users</span></span>
<span data-ttu-id="b989e-131">在 Azure AD 中，來賓和外部使用者皆相同。</span><span class="sxs-lookup"><span data-stu-id="b989e-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="b989e-132">這兩種皆為來賓的使用者類型。</span><span class="sxs-lookup"><span data-stu-id="b989e-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="b989e-133">來賓使用者 B2B 使用者。</span><span class="sxs-lookup"><span data-stu-id="b989e-133">Guest users are B2B users.</span></span>

<span data-ttu-id="b989e-134">Microsoft 小組區分來賓使用者和應用程式內的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b989e-134">Microsoft Teams differentiates between guest users and external users within the app.</span></span> <span data-ttu-id="b989e-135">來賓使用者已有 Azure AD B2B 帳戶，而且可以新增至小組。</span><span class="sxs-lookup"><span data-stu-id="b989e-135">Guest users have Azure AD B2B accounts and can be added to teams.</span></span> <span data-ttu-id="b989e-136">外部使用者只能參與通話、聊天和會議。</span><span class="sxs-lookup"><span data-stu-id="b989e-136">External users can only participate in calls, chats, and meetings.</span></span> <span data-ttu-id="b989e-137">如需詳細資訊，請參閱 [這兩種來賓和外部使用者對團隊的比較](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="b989e-137">For more information, see [this comparison between guest and external users for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="b989e-138">請參閱 [保護小組聊天、群組和檔案的原則建議](teams-access-policies.md) ，以取得安全身分識別與裝置存取的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b989e-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access for Teams</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="b989e-139">需要對來賓和外部使用者永遠進行 MFA</span><span class="sxs-lookup"><span data-stu-id="b989e-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="b989e-140">此原則會提示客人在您的租使用者中註冊 MFA，不論他們是否已在其主承租人中為 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="b989e-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="b989e-141">當存取您租使用者中的資源時，來賓和外部使用者必須針對每個要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="b989e-141">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="b989e-142">從風險型 MFA 排除來賓和外部使用者</span><span class="sxs-lookup"><span data-stu-id="b989e-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="b989e-143">雖然組織可以對使用 Azure AD 身分識別保護的 B2B 使用者強制執行風險原則原則，但由於其內部目錄中的現有身分識別，對資原始目錄中 B2B 共同作業使用者執行 Azure AD 身分識別保護有一些限制。</span><span class="sxs-lookup"><span data-stu-id="b989e-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="b989e-144">由於這些限制，Microsoft 建議您從以風險為基礎的 MFA 原則中排除來賓使用者，並要求這些使用者永遠使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="b989e-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="b989e-145">如需詳細資訊，請參閱 [B2B 協同作業使用者的身分識別保護限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="b989e-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="b989e-146">從裝置管理排除來賓和外部使用者</span><span class="sxs-lookup"><span data-stu-id="b989e-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="b989e-147">只有一個組織可以管理裝置。</span><span class="sxs-lookup"><span data-stu-id="b989e-147">Only one organization can manage a device.</span></span> <span data-ttu-id="b989e-148">如果您未從需要裝置規範的原則中排除來賓和外部使用者，這些原則將會封鎖這些使用者。</span><span class="sxs-lookup"><span data-stu-id="b989e-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b989e-149">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b989e-149">Next step</span></span>

![步驟4： Microsoft 365 雲端應用程式的原則](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="b989e-151">為下列專案設定條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="b989e-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="b989e-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b989e-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="b989e-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b989e-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="b989e-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="b989e-154">SharePoint</span></span>](secure-email-recommended-policies.md)

