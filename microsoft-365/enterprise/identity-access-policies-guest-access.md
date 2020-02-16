---
title: 身分識別與裝置存取原則允許來賓及外部網路 B2B 存取-Microsoft 365 企業版 |Microsoft Docs
description: 說明建議的條件式存取和保護來賓與外部使用者存取的相關的原則。
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8276dcf85f6c5fd61e01e67deee4fea35c1a15c4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067446"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="b1a6d-103">允許來賓及外部網路 B2B 存取原則</span><span class="sxs-lookup"><span data-stu-id="b1a6d-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="b1a6d-104">本文說明如何調整建議一般身分識別與裝置存取原則，以允許 B2B 帳戶存取權 （來賓和外部使用者）。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="b1a6d-105">本指南為基礎的[常見身分識別與裝置存取原則](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="b1a6d-106">這些建議被設計來套用保護的**基準**層。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="b1a6d-107">不過，您可以調整的建議，根據您所需要的保護**機密**和**高管制**的資料粒度。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="b1a6d-108">提供 B2B 使用者向您的 Azure AD 租用戶的路徑不會授與這些使用者存取整個環境。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="b1a6d-109">B2B 使用者只需要與他們共用 （例如檔案） 的資源的存取權授與條件式存取原則中的服務內。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="b1a6d-110">更新以允許與保護來賓與外部存取的一般原則</span><span class="sxs-lookup"><span data-stu-id="b1a6d-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="b1a6d-111">下圖說明常見的身分識別與裝置存取原則，並指出 （與 [鉛筆] 圖示） 來新增或更新來保護來賓與外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![保護來賓存取原則更新的摘要](../media/identity-access-ruleset-guest.png)

<span data-ttu-id="b1a6d-113">下表列出您需要更新或建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="b1a6d-114">一般原則連結至[常見的身分識別與裝置存取原則](identity-access-policies.md)> 一文中的關聯的設定指示。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="b1a6d-115">保護層級</span><span class="sxs-lookup"><span data-stu-id="b1a6d-115">Protection level</span></span>|<span data-ttu-id="b1a6d-116">原則</span><span class="sxs-lookup"><span data-stu-id="b1a6d-116">Policies</span></span>|<span data-ttu-id="b1a6d-117">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b1a6d-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="b1a6d-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="b1a6d-118">**Baseline**</span></span>|[<span data-ttu-id="b1a6d-119">來賓與外部使用者一律需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b1a6d-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="b1a6d-120">建立此新規則，它只適用於來賓與外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="b1a6d-121">[登入風險，保留所有選項已取消核取一律強制執行 MFA。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |<span data-ttu-id="b1a6d-122">[登入風險*中*] 或 [*高*時需要 MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="b1a6d-122">[Require MFA when sign-in risk is *medium* or *high*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span>|<span data-ttu-id="b1a6d-123">修改此規則，以排除來賓與外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="b1a6d-124">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="b1a6d-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="b1a6d-125">修改此規則，以排除來賓與外部使用者。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="b1a6d-126">若要包含或排除來賓和條件式存取規則中的外部使用者，按一下包含或排除] 索引標籤上，檢查**所有來賓和外部使用者。**</span><span class="sxs-lookup"><span data-stu-id="b1a6d-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![排除來賓的控制項的螢幕擷取畫面](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="b1a6d-128">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b1a6d-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="b1a6d-129">與外部使用者的來賓</span><span class="sxs-lookup"><span data-stu-id="b1a6d-129">Guests vs. external users</span></span>
<span data-ttu-id="b1a6d-130">在 Azure AD 中來賓和外部的使用者都相同。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="b1a6d-131">這兩種使用者輸入是來賓。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="b1a6d-132">來賓使用者是 B2B 使用者。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-132">Guest users are B2B users.</span></span>

<span data-ttu-id="b1a6d-133">Microsoft Teams 來賓使用者和應用程式內的外部使用者之間的差異，但以下是這兩個 B2B 使用者進行驗證時。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="b1a6d-134">如需 Teams 來賓與外部使用者的詳細資訊，請參閱[啟用來賓和 microsoft Teams 的外部存取](teams-access-policies.md#enabling-guest-and-external-access-for-teams)。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="b1a6d-135">來賓與外部使用者一律需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b1a6d-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="b1a6d-136">此規則會提示來賓在您的租用戶，不論是否他們正在註冊 MFA 其住家租用戶中註冊的 mfa 功能。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="b1a6d-137">存取您的租用戶中的資源時, 的來賓與外部使用者必須使用 MFA 每一個要求。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="b1a6d-138">從風險的 MFA 排除來賓與外部使用者</span><span class="sxs-lookup"><span data-stu-id="b1a6d-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="b1a6d-139">雖然組織可以強制執行風險型原則 B2B 使用者使用 Identity Protection，有 B2B 共同作業中的使用者由於其首頁中現有其身分識別的資源目錄 Identity Protection 的實作限制目錄。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="b1a6d-140">由於這些限制，Microsoft 建議您排除風險的 MFA 原則中的來賓使用者，且需要這些使用者一律使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="b1a6d-141">如需詳細資訊，請參閱[Identity Protection 的限制為 B2B 共同作業使用者](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="b1a6d-142">排除來賓與外部使用者從裝置管理</span><span class="sxs-lookup"><span data-stu-id="b1a6d-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="b1a6d-143">只有一個組織可以管理裝置。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-143">Only one organization can manage a device.</span></span> <span data-ttu-id="b1a6d-144">如果您不需要裝置相容性的原則排除來賓及外部使用者，這些原則會封鎖這些使用者。</span><span class="sxs-lookup"><span data-stu-id="b1a6d-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="b1a6d-145">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b1a6d-145">Next steps</span></span>

[<span data-ttu-id="b1a6d-146">了解如何啟用 Teams 條件式存取</span><span class="sxs-lookup"><span data-stu-id="b1a6d-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)

