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
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898101"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="7c46e-103">允許來賓和外部 B2B 存取的原則</span><span class="sxs-lookup"><span data-stu-id="7c46e-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="7c46e-104">本文說明如何調整建議的常見身分識別和裝置存取原則，以允許 (來賓和外部使用者 B2B 帳戶存取權) 。</span><span class="sxs-lookup"><span data-stu-id="7c46e-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="7c46e-105">本指南是以 [通用身分識別和裝置存取原則](identity-access-policies.md)為基礎。</span><span class="sxs-lookup"><span data-stu-id="7c46e-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="7c46e-106">這些建議適用于保護的 **基準** 層。</span><span class="sxs-lookup"><span data-stu-id="7c46e-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="7c46e-107">不過，您可以根據您對 **機密** 和 **高管制** 保護的需求細微性來調整建議。</span><span class="sxs-lookup"><span data-stu-id="7c46e-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="7c46e-108">提供 B2B 使用者驗證您的 Azure AD 租使用者的路徑，不會讓這些使用者存取您的整個環境。</span><span class="sxs-lookup"><span data-stu-id="7c46e-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="7c46e-109">B2B 使用者只能存取與其共用的資源 (例如，在條件式存取原則中授與服務內) 的檔案。</span><span class="sxs-lookup"><span data-stu-id="7c46e-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="7c46e-110">更新共同原則以允許及保護來賓和外部存取</span><span class="sxs-lookup"><span data-stu-id="7c46e-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="7c46e-111">下圖說明一般身分識別和裝置存取原則，並指出 (包含鉛筆圖示) 要新增或更新以保護來賓和外部存取的原則。</span><span class="sxs-lookup"><span data-stu-id="7c46e-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![保護來賓存取的原則更新摘要](../media/identity-access-ruleset-guest.png)

<span data-ttu-id="7c46e-113">下表列出您必須更新或建立的原則。</span><span class="sxs-lookup"><span data-stu-id="7c46e-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="7c46e-114">通用身分 [識別與裝置存取原則](identity-access-policies.md) 文章中相關之設定指示的常見原則連結。</span><span class="sxs-lookup"><span data-stu-id="7c46e-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="7c46e-115">保護層級</span><span class="sxs-lookup"><span data-stu-id="7c46e-115">Protection level</span></span>|<span data-ttu-id="7c46e-116">原則</span><span class="sxs-lookup"><span data-stu-id="7c46e-116">Policies</span></span>|<span data-ttu-id="7c46e-117">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="7c46e-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="7c46e-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="7c46e-118">**Baseline**</span></span>|[<span data-ttu-id="7c46e-119">需要對來賓和外部使用者永遠進行 MFA</span><span class="sxs-lookup"><span data-stu-id="7c46e-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7c46e-120">建立此新規則，並將其套用至來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="7c46e-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="7c46e-121">在 [登入風險] 下，將所有選項保留未勾選狀態，永遠強制執行 MFA。</span><span class="sxs-lookup"><span data-stu-id="7c46e-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |[<span data-ttu-id="7c46e-122">當登入風險為*中*或*高*時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="7c46e-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="7c46e-123">修改此規則，以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="7c46e-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="7c46e-124">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="7c46e-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="7c46e-125">修改此規則，以排除來賓和外部使用者。</span><span class="sxs-lookup"><span data-stu-id="7c46e-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="7c46e-126">若要在條件式存取規則中包含或排除來賓和外部使用者，請按一下 [包含或排除] 索引標籤，並檢查 **所有來賓和外部使用者**。</span><span class="sxs-lookup"><span data-stu-id="7c46e-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![用於排除來賓之控制項的畫面捕獲](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="7c46e-128">其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="7c46e-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="7c46e-129">來賓與外部使用者</span><span class="sxs-lookup"><span data-stu-id="7c46e-129">Guests vs. external users</span></span>
<span data-ttu-id="7c46e-130">在 Azure AD 中，來賓和外部使用者皆相同。</span><span class="sxs-lookup"><span data-stu-id="7c46e-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="7c46e-131">這兩種皆為來賓的使用者類型。</span><span class="sxs-lookup"><span data-stu-id="7c46e-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="7c46e-132">來賓使用者 B2B 使用者。</span><span class="sxs-lookup"><span data-stu-id="7c46e-132">Guest users are B2B users.</span></span>

<span data-ttu-id="7c46e-133">Microsoft 小組會區別來賓使用者與應用程式中的外部使用者，但是在驗證時，這兩個使用者都 B2B 使用者。</span><span class="sxs-lookup"><span data-stu-id="7c46e-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="7c46e-134">如需小組來賓和外部使用者的詳細資訊，請參閱 [啟用使用者的來賓和外部存取](teams-access-policies.md#enabling-guest-and-external-access-for-teams)。</span><span class="sxs-lookup"><span data-stu-id="7c46e-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="7c46e-135">需要對來賓和外部使用者永遠進行 MFA</span><span class="sxs-lookup"><span data-stu-id="7c46e-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="7c46e-136">此規則會提示客人在您的租使用者中註冊 MFA，不論他們是否已在其主承租人中為 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="7c46e-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="7c46e-137">當存取您租使用者中的資源時，來賓和外部使用者必須針對每個要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="7c46e-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="7c46e-138">從風險型 MFA 排除來賓和外部使用者</span><span class="sxs-lookup"><span data-stu-id="7c46e-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="7c46e-139">雖然組織可以對使用 Identity Protection 的 B2B 使用者強制執行風險原則原則，但由於使用者在其主目錄中的身分識別，對資原始目錄中 B2B 共同作業使用者實施身分識別保護時，有一些限制。</span><span class="sxs-lookup"><span data-stu-id="7c46e-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="7c46e-140">由於這些限制，Microsoft 建議您從以風險為基礎的 MFA 原則中排除來賓使用者，並要求這些使用者永遠使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="7c46e-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="7c46e-141">如需詳細資訊，請參閱 [B2B 協同作業使用者的身分識別保護限制](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="7c46e-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="7c46e-142">從裝置管理排除來賓和外部使用者</span><span class="sxs-lookup"><span data-stu-id="7c46e-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="7c46e-143">只有一個組織可以管理裝置。</span><span class="sxs-lookup"><span data-stu-id="7c46e-143">Only one organization can manage a device.</span></span> <span data-ttu-id="7c46e-144">如果您未從需要裝置規範的原則中排除來賓和外部使用者，這些原則將會封鎖這些使用者。</span><span class="sxs-lookup"><span data-stu-id="7c46e-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7c46e-145">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7c46e-145">Next steps</span></span>

[<span data-ttu-id="7c46e-146">瞭解如何啟用小組條件式存取</span><span class="sxs-lookup"><span data-stu-id="7c46e-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)

