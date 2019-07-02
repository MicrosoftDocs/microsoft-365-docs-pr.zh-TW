---
title: 一般身分識別和裝置存取原則-Microsoft 365 企業版 |Microsoft 檔
description: 描述如何套用身分識別和裝置存取原則和設定之 Microsoft 建議的原則。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 322da1ccfbd0cf8b5070894580b06fb5b0283f40
ms.sourcegitcommit: 1d5fc181036b673c4f0b9e161e19395dbfe5a304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2019
ms.locfileid: "35411647"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="0bed9-103">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="0bed9-103">Common identity and device access policies</span></span>
<span data-ttu-id="0bed9-104">本文說明用於保護雲端服務存取的常見建議原則, 包括以 Azure AD 應用程式 Proxy 發佈的內部部署應用程式。</span><span class="sxs-lookup"><span data-stu-id="0bed9-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="0bed9-105">本指南討論如何在新布建的環境中部署建議的原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-105">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment.</span></span> <span data-ttu-id="0bed9-106">在個別的實驗室環境中設定這些原則, 可讓您瞭解並評估建議的原則, 然後再將推廣作業轉移至您的預製和實際執行環境。</span><span class="sxs-lookup"><span data-stu-id="0bed9-106">Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments.</span></span> <span data-ttu-id="0bed9-107">您剛布建的環境可能是僅限雲端或混合式。</span><span class="sxs-lookup"><span data-stu-id="0bed9-107">Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="0bed9-108">原則集</span><span class="sxs-lookup"><span data-stu-id="0bed9-108">Policy set</span></span> 

<span data-ttu-id="0bed9-109">下圖說明建議的原則集合。</span><span class="sxs-lookup"><span data-stu-id="0bed9-109">The following diagram illustrates the recommended set of policies.</span></span> <span data-ttu-id="0bed9-110">它會顯示每個原則適用的保護層, 以及這些原則是套用至電腦或電話和平板電腦, 或是這兩類裝置。</span><span class="sxs-lookup"><span data-stu-id="0bed9-110">It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices.</span></span> <span data-ttu-id="0bed9-111">它也會指出設定這些原則的位置。</span><span class="sxs-lookup"><span data-stu-id="0bed9-111">It also indicates where these policies are configured.</span></span>

![設定身分識別與裝置存取的一般原則](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="0bed9-113">本文的其餘部分將說明如何設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="0bed9-114">在將裝置註冊到 Intune 之前, 建議使用多重要素驗證, 以確保裝置屬於預定的使用者。</span><span class="sxs-lookup"><span data-stu-id="0bed9-114">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> <span data-ttu-id="0bed9-115">您也必須在強制裝置規範原則之前, 將裝置註冊至 Intune。</span><span class="sxs-lookup"><span data-stu-id="0bed9-115">You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="0bed9-116">為讓您完成這些工作的時間, 建議您依下表所列的順序來執行基準原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-116">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table.</span></span> <span data-ttu-id="0bed9-117">不過, 機密和高度管制保護的 MFA 原則可以在任何時候執行。</span><span class="sxs-lookup"><span data-stu-id="0bed9-117">However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="0bed9-118">保護層級</span><span class="sxs-lookup"><span data-stu-id="0bed9-118">Protection level</span></span>|<span data-ttu-id="0bed9-119">規則</span><span class="sxs-lookup"><span data-stu-id="0bed9-119">Policies</span></span>|<span data-ttu-id="0bed9-120">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="0bed9-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="0bed9-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="0bed9-121">**Baseline**</span></span>|[<span data-ttu-id="0bed9-122">當登入風險為*中等*或*高*時, 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="0bed9-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="0bed9-123">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="0bed9-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="0bed9-124">未使用新式驗證的用戶端可以略過條件式存取規則, 因此請務必封鎖這些規則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="0bed9-125">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="0bed9-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="0bed9-126">在為其帳戶偵測到高風險活動時, 強制使用者變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="0bed9-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="0bed9-127">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="0bed9-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="0bed9-128">每個平臺有一個原則 (iOS、Android、Windows)。</span><span class="sxs-lookup"><span data-stu-id="0bed9-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="0bed9-129">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="0bed9-130">強制執行手機和平板電腦的行動裝置應用程式保護</span><span class="sxs-lookup"><span data-stu-id="0bed9-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="0bed9-131">定義裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="0bed9-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="0bed9-132">每個平臺的一個原則</span><span class="sxs-lookup"><span data-stu-id="0bed9-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="0bed9-133">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="0bed9-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="0bed9-134">強制執行電腦的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="0bed9-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="0bed9-135">**敏感性**</span><span class="sxs-lookup"><span data-stu-id="0bed9-135">**Sensitive**</span></span>|[<span data-ttu-id="0bed9-136">當登入風險為*低*、*中*或*高*時, 需要 MFA</span><span class="sxs-lookup"><span data-stu-id="0bed9-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="0bed9-137">需要相容*的電腦和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="0bed9-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="0bed9-138">強制執行電腦和電話/平板電腦的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="0bed9-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="0bed9-139">**高管制**</span><span class="sxs-lookup"><span data-stu-id="0bed9-139">**Highly regulated**</span></span>|[<span data-ttu-id="0bed9-140">*永遠*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="0bed9-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="0bed9-141">指派原則給使用者</span><span class="sxs-lookup"><span data-stu-id="0bed9-141">Assigning policies to users</span></span>
<span data-ttu-id="0bed9-142">設定原則之前, 請先識別您對每個保護層所使用的 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="0bed9-142">Before configuring policies, identify the Azure AD groups you are using for each tier of protection.</span></span> <span data-ttu-id="0bed9-143">一般來說, 基準保護會套用至組織中的每個人。</span><span class="sxs-lookup"><span data-stu-id="0bed9-143">Typically, baseline protection applies to everybody in the organization.</span></span> <span data-ttu-id="0bed9-144">包含在基線和敏感保護中的使用者, 將套用所有的基準原則加上敏感原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-144">A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies.</span></span> <span data-ttu-id="0bed9-145">保護是累計的, 而且會強制執行最具限制性的原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-145">Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="0bed9-146">建議的作法是建立 Azure AD 群組以設定條件式存取排除。</span><span class="sxs-lookup"><span data-stu-id="0bed9-146">A recommended practice is to create an Azure AD group for conditional access exclusion.</span></span> <span data-ttu-id="0bed9-147">將此群組新增至 [Exclude] 底下的所有條件式存取規則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-147">Add this group to all of your conditional access rules under "Exclude".</span></span> <span data-ttu-id="0bed9-148">這可讓您在對存取問題進行疑難排解時提供存取權給使用者的方法。</span><span class="sxs-lookup"><span data-stu-id="0bed9-148">This gives you a method to provide access to a user while you troubleshoot access issues.</span></span> <span data-ttu-id="0bed9-149">建議做為暫時的解決方案。</span><span class="sxs-lookup"><span data-stu-id="0bed9-149">This is recommended as a temporary solution only.</span></span> <span data-ttu-id="0bed9-150">監視此群組的變更, 並確定排除群組的使用方式只是預期。</span><span class="sxs-lookup"><span data-stu-id="0bed9-150">Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="0bed9-151">下圖提供使用者指派和排除的範例。</span><span class="sxs-lookup"><span data-stu-id="0bed9-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![MFA 規則的使用者指派和排除的範例](../images/identity-access-policies-assignment.png)

<span data-ttu-id="0bed9-153">在圖中, 會將需要*一定*的條件式存取原則指派給「主要機密專案 X 小組」。</span><span class="sxs-lookup"><span data-stu-id="0bed9-153">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*.</span></span> <span data-ttu-id="0bed9-154">將較高的保護等級套用至使用者時, 請務必合理。</span><span class="sxs-lookup"><span data-stu-id="0bed9-154">Be judicious when applying higher levels of protection to users.</span></span> <span data-ttu-id="0bed9-155">此專案小組的成員必須在每次登入時都提供兩種形式的驗證, 即使他們沒有查看高度規範的內容也是一樣。</span><span class="sxs-lookup"><span data-stu-id="0bed9-155">Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="0bed9-156">在這些建議中建立的所有 Azure AD 群組, 都必須建立為 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="0bed9-156">All Azure AD groups created as part of these recommendations must be created as Office 365 groups.</span></span> <span data-ttu-id="0bed9-157">在 SharePoint Online 中保護文件時，這對於部署 Azure 資訊保護 (AIP) 特別重要。</span><span class="sxs-lookup"><span data-stu-id="0bed9-157">This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![建立 Office 365 群組的螢幕擷取畫面](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="0bed9-159">需要根據登入風險的 MFA</span><span class="sxs-lookup"><span data-stu-id="0bed9-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="0bed9-160">在要求 MFA 之前, 請先使用身分識別保護 MFA 註冊原則, 為 MFA 註冊使用者。</span><span class="sxs-lookup"><span data-stu-id="0bed9-160">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA.</span></span> <span data-ttu-id="0bed9-161">註冊使用者後, 您可以強制進行 MFA 以進行登入。</span><span class="sxs-lookup"><span data-stu-id="0bed9-161">After users are registered you can enforce MFA for sign-in.</span></span> <span data-ttu-id="0bed9-162">必要條件[工作](identity-access-prerequisites.md)包括向 MFA 註冊所有使用者。</span><span class="sxs-lookup"><span data-stu-id="0bed9-162">The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="0bed9-163">若要建立新的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="0bed9-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="0bed9-164">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0bed9-164">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="0bed9-165">在您成功登入之後, 您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="0bed9-165">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="0bed9-166">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="0bed9-167">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="0bed9-168">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-168">Choose **New policy**.</span></span>

![基準 CA 原則](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="0bed9-170">下表說明要為此原則執行的條件式存取原則設定。</span><span class="sxs-lookup"><span data-stu-id="0bed9-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="0bed9-171">**指派**</span><span class="sxs-lookup"><span data-stu-id="0bed9-171">**Assignments**</span></span>

|<span data-ttu-id="0bed9-172">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-172">Type</span></span>|<span data-ttu-id="0bed9-173">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-173">Properties</span></span>|<span data-ttu-id="0bed9-174">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-174">Values</span></span>|<span data-ttu-id="0bed9-175">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-176">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="0bed9-176">Users and groups</span></span>|<span data-ttu-id="0bed9-177">Include</span><span class="sxs-lookup"><span data-stu-id="0bed9-177">Include</span></span>|<span data-ttu-id="0bed9-178">選取使用者和群組 - 選取包含目標使用者的特定安全性群組</span><span class="sxs-lookup"><span data-stu-id="0bed9-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="0bed9-179">從包含試驗使用者的安全性群組開始</span><span class="sxs-lookup"><span data-stu-id="0bed9-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="0bed9-180">排除</span><span class="sxs-lookup"><span data-stu-id="0bed9-180">Exclude</span></span>|<span data-ttu-id="0bed9-181">例外狀況安全性群組；服務帳戶 (應用程式身分識別)</span><span class="sxs-lookup"><span data-stu-id="0bed9-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="0bed9-182">在需要的暫存基礎上修改成員資格</span><span class="sxs-lookup"><span data-stu-id="0bed9-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="0bed9-183">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-183">Cloud apps</span></span>|<span data-ttu-id="0bed9-184">Include</span><span class="sxs-lookup"><span data-stu-id="0bed9-184">Include</span></span>|<span data-ttu-id="0bed9-185">選取您要套用此規則的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0bed9-185">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="0bed9-186">例如, 選取 [Office 365 Exchange Online]</span><span class="sxs-lookup"><span data-stu-id="0bed9-186">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="0bed9-187">條件</span><span class="sxs-lookup"><span data-stu-id="0bed9-187">Conditions</span></span>|<span data-ttu-id="0bed9-188">已設定</span><span class="sxs-lookup"><span data-stu-id="0bed9-188">Configured</span></span>|<span data-ttu-id="0bed9-189">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-189">Yes</span></span>|<span data-ttu-id="0bed9-190">進行您環境和需求的特定設定</span><span class="sxs-lookup"><span data-stu-id="0bed9-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="0bed9-191">登入風險</span><span class="sxs-lookup"><span data-stu-id="0bed9-191">Sign-in risk</span></span>|<span data-ttu-id="0bed9-192">風險層級</span><span class="sxs-lookup"><span data-stu-id="0bed9-192">Risk level</span></span>||<span data-ttu-id="0bed9-193">請參閱下表中的指導方針</span><span class="sxs-lookup"><span data-stu-id="0bed9-193">See the guidance in the following table</span></span>|

<span data-ttu-id="0bed9-194">**登入風險**</span><span class="sxs-lookup"><span data-stu-id="0bed9-194">**Sign-in risk**</span></span>

<span data-ttu-id="0bed9-195">根據目標的保護層級套用設定。</span><span class="sxs-lookup"><span data-stu-id="0bed9-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="0bed9-196">屬性	</span><span class="sxs-lookup"><span data-stu-id="0bed9-196">Property</span></span>|<span data-ttu-id="0bed9-197">保護層級</span><span class="sxs-lookup"><span data-stu-id="0bed9-197">Level of protection</span></span>|<span data-ttu-id="0bed9-198">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-198">Values</span></span>|<span data-ttu-id="0bed9-199">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-200">風險層級</span><span class="sxs-lookup"><span data-stu-id="0bed9-200">Risk level</span></span>|<span data-ttu-id="0bed9-201">基準</span><span class="sxs-lookup"><span data-stu-id="0bed9-201">Baseline</span></span>|<span data-ttu-id="0bed9-202">高、中</span><span class="sxs-lookup"><span data-stu-id="0bed9-202">High, medium</span></span>|<span data-ttu-id="0bed9-203">檢查兩者</span><span class="sxs-lookup"><span data-stu-id="0bed9-203">Check both</span></span>|
| |<span data-ttu-id="0bed9-204">敏感性</span><span class="sxs-lookup"><span data-stu-id="0bed9-204">Sensitive</span></span>|<span data-ttu-id="0bed9-205">高、中、低</span><span class="sxs-lookup"><span data-stu-id="0bed9-205">High, medium, low</span></span>|<span data-ttu-id="0bed9-206">三個全選</span><span class="sxs-lookup"><span data-stu-id="0bed9-206">Check all three</span></span>|
| |<span data-ttu-id="0bed9-207">高管制</span><span class="sxs-lookup"><span data-stu-id="0bed9-207">Highly regulated</span></span>| |<span data-ttu-id="0bed9-208">將所有選項保留為未選取狀態, 以永遠強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="0bed9-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="0bed9-209">**存取控制**</span><span class="sxs-lookup"><span data-stu-id="0bed9-209">**Access controls**</span></span>

|<span data-ttu-id="0bed9-210">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-210">Type</span></span>|<span data-ttu-id="0bed9-211">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-211">Properties</span></span>|<span data-ttu-id="0bed9-212">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-212">Values</span></span>|<span data-ttu-id="0bed9-213">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-214">授與</span><span class="sxs-lookup"><span data-stu-id="0bed9-214">Grant</span></span>|<span data-ttu-id="0bed9-215">授予存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-215">Grant access</span></span>|<span data-ttu-id="0bed9-216">True</span><span class="sxs-lookup"><span data-stu-id="0bed9-216">True</span></span>|<span data-ttu-id="0bed9-217">已選取</span><span class="sxs-lookup"><span data-stu-id="0bed9-217">Selected</span></span>|
||<span data-ttu-id="0bed9-218">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="0bed9-218">Require MFA</span></span>|<span data-ttu-id="0bed9-219">True</span><span class="sxs-lookup"><span data-stu-id="0bed9-219">True</span></span>|<span data-ttu-id="0bed9-220">Check</span><span class="sxs-lookup"><span data-stu-id="0bed9-220">Check</span></span>|
||<span data-ttu-id="0bed9-221">需要將裝置標示為合規性</span><span class="sxs-lookup"><span data-stu-id="0bed9-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="0bed9-222">False</span><span class="sxs-lookup"><span data-stu-id="0bed9-222">False</span></span>||
||<span data-ttu-id="0bed9-223">需要混合式 Azure AD 加入的裝置</span><span class="sxs-lookup"><span data-stu-id="0bed9-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="0bed9-224">False</span><span class="sxs-lookup"><span data-stu-id="0bed9-224">False</span></span>||
||<span data-ttu-id="0bed9-225">需要核准的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-225">Require approved client app</span></span>|<span data-ttu-id="0bed9-226">False</span><span class="sxs-lookup"><span data-stu-id="0bed9-226">False</span></span>||
||<span data-ttu-id="0bed9-227">需要所有選取的控制項</span><span class="sxs-lookup"><span data-stu-id="0bed9-227">Require all the selected controls</span></span>|<span data-ttu-id="0bed9-228">True</span><span class="sxs-lookup"><span data-stu-id="0bed9-228">True</span></span>|<span data-ttu-id="0bed9-229">已選取</span><span class="sxs-lookup"><span data-stu-id="0bed9-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="0bed9-230">請選擇 [啟用], 以確定啟用\*\*\*\* 此原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-230">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="0bed9-231">此外, 請考慮使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-231">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="0bed9-232">封鎖不支援新式驗證的用戶端</span><span class="sxs-lookup"><span data-stu-id="0bed9-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="0bed9-233">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0bed9-233">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="0bed9-234">在您成功登入之後, 您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="0bed9-234">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="0bed9-235">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="0bed9-236">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="0bed9-237">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-237">Choose **New policy**.</span></span>

<span data-ttu-id="0bed9-238">下表說明要為此原則執行的條件式存取原則設定。</span><span class="sxs-lookup"><span data-stu-id="0bed9-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="0bed9-239">**指派**</span><span class="sxs-lookup"><span data-stu-id="0bed9-239">**Assignments**</span></span>

|<span data-ttu-id="0bed9-240">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-240">Type</span></span>|<span data-ttu-id="0bed9-241">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-241">Properties</span></span>|<span data-ttu-id="0bed9-242">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-242">Values</span></span>|<span data-ttu-id="0bed9-243">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-244">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="0bed9-244">Users and groups</span></span>|<span data-ttu-id="0bed9-245">Include</span><span class="sxs-lookup"><span data-stu-id="0bed9-245">Include</span></span>|<span data-ttu-id="0bed9-246">選取使用者和群組 - 選取包含目標使用者的特定安全性群組</span><span class="sxs-lookup"><span data-stu-id="0bed9-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="0bed9-247">從包含試驗使用者的安全性群組開始</span><span class="sxs-lookup"><span data-stu-id="0bed9-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="0bed9-248">排除</span><span class="sxs-lookup"><span data-stu-id="0bed9-248">Exclude</span></span>|<span data-ttu-id="0bed9-249">例外狀況安全性群組；服務帳戶 (應用程式身分識別)</span><span class="sxs-lookup"><span data-stu-id="0bed9-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="0bed9-250">視需要暫時修改成員資格</span><span class="sxs-lookup"><span data-stu-id="0bed9-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="0bed9-251">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-251">Cloud apps</span></span>|<span data-ttu-id="0bed9-252">Include</span><span class="sxs-lookup"><span data-stu-id="0bed9-252">Include</span></span>|<span data-ttu-id="0bed9-253">選取您要套用此規則的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0bed9-253">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="0bed9-254">例如, 選取 [Office 365 Exchange Online]</span><span class="sxs-lookup"><span data-stu-id="0bed9-254">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="0bed9-255">條件</span><span class="sxs-lookup"><span data-stu-id="0bed9-255">Conditions</span></span>|<span data-ttu-id="0bed9-256">已設定</span><span class="sxs-lookup"><span data-stu-id="0bed9-256">Configured</span></span>|<span data-ttu-id="0bed9-257">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-257">Yes</span></span>|<span data-ttu-id="0bed9-258">設定用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-258">Configure Client apps</span></span>|
|<span data-ttu-id="0bed9-259">用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-259">Client apps</span></span>|<span data-ttu-id="0bed9-260">已設定</span><span class="sxs-lookup"><span data-stu-id="0bed9-260">Configured</span></span>|<span data-ttu-id="0bed9-261">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-261">Yes</span></span>|<span data-ttu-id="0bed9-262">行動裝置應用程式和桌面用戶端, 其他用戶端 (選取兩者)</span><span class="sxs-lookup"><span data-stu-id="0bed9-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="0bed9-263">**存取控制**</span><span class="sxs-lookup"><span data-stu-id="0bed9-263">**Access controls**</span></span>

|<span data-ttu-id="0bed9-264">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-264">Type</span></span>|<span data-ttu-id="0bed9-265">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-265">Properties</span></span>|<span data-ttu-id="0bed9-266">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-266">Values</span></span>|<span data-ttu-id="0bed9-267">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-268">授與</span><span class="sxs-lookup"><span data-stu-id="0bed9-268">Grant</span></span>|<span data-ttu-id="0bed9-269">封鎖存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-269">Block access</span></span>|<span data-ttu-id="0bed9-270">True</span><span class="sxs-lookup"><span data-stu-id="0bed9-270">True</span></span>|<span data-ttu-id="0bed9-271">已選取</span><span class="sxs-lookup"><span data-stu-id="0bed9-271">Selected</span></span>|
||<span data-ttu-id="0bed9-272">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="0bed9-272">Require MFA</span></span>|<span data-ttu-id="0bed9-273">False</span><span class="sxs-lookup"><span data-stu-id="0bed9-273">False</span></span>||
||<span data-ttu-id="0bed9-274">需要將裝置標示為合規性</span><span class="sxs-lookup"><span data-stu-id="0bed9-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="0bed9-275">False</span><span class="sxs-lookup"><span data-stu-id="0bed9-275">False</span></span>||
||<span data-ttu-id="0bed9-276">需要混合式 Azure AD 加入的裝置</span><span class="sxs-lookup"><span data-stu-id="0bed9-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="0bed9-277">False</span><span class="sxs-lookup"><span data-stu-id="0bed9-277">False</span></span>||
||<span data-ttu-id="0bed9-278">需要核准的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-278">Require approved client app</span></span>|<span data-ttu-id="0bed9-279">False</span><span class="sxs-lookup"><span data-stu-id="0bed9-279">False</span></span>||
||<span data-ttu-id="0bed9-280">需要所有選取的控制項</span><span class="sxs-lookup"><span data-stu-id="0bed9-280">Require all the selected controls</span></span>|<span data-ttu-id="0bed9-281">True</span><span class="sxs-lookup"><span data-stu-id="0bed9-281">True</span></span>|<span data-ttu-id="0bed9-282">已選取</span><span class="sxs-lookup"><span data-stu-id="0bed9-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="0bed9-283">請選擇 [啟用], 以確定啟用\*\*\*\* 此原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-283">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="0bed9-284">此外, 請考慮使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-284">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="0bed9-285">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="0bed9-285">High risk users must change password</span></span>
<span data-ttu-id="0bed9-286">若要確保所有高風險使用者遭到破壞的帳戶強制在登入時執行密碼變更, 您必須套用下列原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="0bed9-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span><span class="sxs-lookup"><span data-stu-id="0bed9-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="0bed9-288">**指派**</span><span class="sxs-lookup"><span data-stu-id="0bed9-288">**Assignments**</span></span>

|<span data-ttu-id="0bed9-289">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-289">Type</span></span>|<span data-ttu-id="0bed9-290">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-290">Properties</span></span>|<span data-ttu-id="0bed9-291">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-291">Values</span></span>|<span data-ttu-id="0bed9-292">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-293">使用者</span><span class="sxs-lookup"><span data-stu-id="0bed9-293">Users</span></span>|<span data-ttu-id="0bed9-294">Include</span><span class="sxs-lookup"><span data-stu-id="0bed9-294">Include</span></span>|<span data-ttu-id="0bed9-295">所有使用者</span><span class="sxs-lookup"><span data-stu-id="0bed9-295">All users</span></span>|<span data-ttu-id="0bed9-296">已選取</span><span class="sxs-lookup"><span data-stu-id="0bed9-296">Selected</span></span>|
||<span data-ttu-id="0bed9-297">排除</span><span class="sxs-lookup"><span data-stu-id="0bed9-297">Exclude</span></span>|<span data-ttu-id="0bed9-298">無</span><span class="sxs-lookup"><span data-stu-id="0bed9-298">None</span></span>||
|<span data-ttu-id="0bed9-299">條件</span><span class="sxs-lookup"><span data-stu-id="0bed9-299">Conditions</span></span>|<span data-ttu-id="0bed9-300">使用者風險</span><span class="sxs-lookup"><span data-stu-id="0bed9-300">User risk</span></span>|<span data-ttu-id="0bed9-301">高</span><span class="sxs-lookup"><span data-stu-id="0bed9-301">High</span></span>|<span data-ttu-id="0bed9-302">已選取</span><span class="sxs-lookup"><span data-stu-id="0bed9-302">Selected</span></span>|

<span data-ttu-id="0bed9-303">**控制項**</span><span class="sxs-lookup"><span data-stu-id="0bed9-303">**Controls**</span></span>

| <span data-ttu-id="0bed9-304">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-304">Type</span></span> | <span data-ttu-id="0bed9-305">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-305">Properties</span></span> | <span data-ttu-id="0bed9-306">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-306">Values</span></span>                  | <span data-ttu-id="0bed9-307">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="0bed9-308">存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-308">Access</span></span>     | <span data-ttu-id="0bed9-309">允許存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-309">Allow access</span></span>            | <span data-ttu-id="0bed9-310">True</span><span class="sxs-lookup"><span data-stu-id="0bed9-310">True</span></span>  |
|      | <span data-ttu-id="0bed9-311">存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-311">Access</span></span>     | <span data-ttu-id="0bed9-312">需要密碼變更</span><span class="sxs-lookup"><span data-stu-id="0bed9-312">Require password change</span></span> | <span data-ttu-id="0bed9-313">True</span><span class="sxs-lookup"><span data-stu-id="0bed9-313">True</span></span>  |

<span data-ttu-id="0bed9-314">**回顧:** 不適用</span><span class="sxs-lookup"><span data-stu-id="0bed9-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="0bed9-315">請選擇 [啟用], 以確定啟用\*\*\*\* 此原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-315">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="0bed9-316">此外, 請考慮使用[if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則</span><span class="sxs-lookup"><span data-stu-id="0bed9-316">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="0bed9-317">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="0bed9-317">Define app protection policies</span></span>
<span data-ttu-id="0bed9-318">應用程式保護原則會定義所允許的應用程式, 以及可對您組織的資料採取的動作。</span><span class="sxs-lookup"><span data-stu-id="0bed9-318">App protection policies define which apps are allowed and the actions they can take with your organization's data.</span></span> <span data-ttu-id="0bed9-319">從 Azure 入口網站中建立 Intune 應用程式保護原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-319">Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="0bed9-320">建立每個平臺的原則:</span><span class="sxs-lookup"><span data-stu-id="0bed9-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="0bed9-321">適用</span><span class="sxs-lookup"><span data-stu-id="0bed9-321">iOS</span></span>
- <span data-ttu-id="0bed9-322">Android</span><span class="sxs-lookup"><span data-stu-id="0bed9-322">Android</span></span>
- <span data-ttu-id="0bed9-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0bed9-323">Windows 10</span></span>

<span data-ttu-id="0bed9-324">若要建立新的應用程式保護原則, 請使用您的管理員認證登入 Microsoft Azure 入口網站, 然後流覽至行動**應用程式 > 應用程式保護原則**。</span><span class="sxs-lookup"><span data-stu-id="0bed9-324">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**.</span></span> <span data-ttu-id="0bed9-325">選擇 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-325">Choose **Add a policy**.</span></span>

<span data-ttu-id="0bed9-326">iOS 與 Android 的應用程式防護原則選項有些許差異。</span><span class="sxs-lookup"><span data-stu-id="0bed9-326">There are slight differences in the app protection policy options between iOS and Android.</span></span> <span data-ttu-id="0bed9-327">下列原則專用於 Android。</span><span class="sxs-lookup"><span data-stu-id="0bed9-327">The below policy is specifically for Android.</span></span> <span data-ttu-id="0bed9-328">請以此做為其他原則的指南。</span><span class="sxs-lookup"><span data-stu-id="0bed9-328">Use this as a guide for your other policies.</span></span>

<span data-ttu-id="0bed9-329">建議的應用程式清單包括下列專案:</span><span class="sxs-lookup"><span data-stu-id="0bed9-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="0bed9-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0bed9-330">PowerPoint</span></span>
- <span data-ttu-id="0bed9-331">Excel</span><span class="sxs-lookup"><span data-stu-id="0bed9-331">Excel</span></span>
- <span data-ttu-id="0bed9-332">Word</span><span class="sxs-lookup"><span data-stu-id="0bed9-332">Word</span></span>
- <span data-ttu-id="0bed9-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0bed9-333">Microsoft Teams</span></span>
- <span data-ttu-id="0bed9-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="0bed9-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="0bed9-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="0bed9-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="0bed9-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0bed9-336">OneDrive</span></span>
- <span data-ttu-id="0bed9-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="0bed9-337">OneNote</span></span>
- <span data-ttu-id="0bed9-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="0bed9-338">Outlook</span></span>

<span data-ttu-id="0bed9-339">下表說明建議的設定:</span><span class="sxs-lookup"><span data-stu-id="0bed9-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="0bed9-340">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-340">Type</span></span>|<span data-ttu-id="0bed9-341">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-341">Properties</span></span>|<span data-ttu-id="0bed9-342">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-342">Values</span></span>|<span data-ttu-id="0bed9-343">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-344">資料重新配置</span><span class="sxs-lookup"><span data-stu-id="0bed9-344">Data relocation</span></span>|<span data-ttu-id="0bed9-345">禁止 Android 備份</span><span class="sxs-lookup"><span data-stu-id="0bed9-345">Prevent Android backup</span></span>|<span data-ttu-id="0bed9-346">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-346">Yes</span></span>|<span data-ttu-id="0bed9-347">在 iOS 上，這會特別呼叫 iTunes 和 iCloud</span><span class="sxs-lookup"><span data-stu-id="0bed9-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="0bed9-348">允許應用程式將資料傳送到其他應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="0bed9-349">受原則管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-349">Policy managed apps</span></span>||
||<span data-ttu-id="0bed9-350">[允許應用程式接收其他應用程式的資料]</span><span class="sxs-lookup"><span data-stu-id="0bed9-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="0bed9-351">受原則管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-351">Policy managed apps</span></span>||
||<span data-ttu-id="0bed9-352">禁止執行 [另存新檔]</span><span class="sxs-lookup"><span data-stu-id="0bed9-352">Prevent "Save As"</span></span>|<span data-ttu-id="0bed9-353">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-353">Yes</span></span>||
||<span data-ttu-id="0bed9-354">選取可儲存公司資料的儲存體服務</span><span class="sxs-lookup"><span data-stu-id="0bed9-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="0bed9-355">商務用 OneDrive、SharePoint</span><span class="sxs-lookup"><span data-stu-id="0bed9-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="0bed9-356">限制利用其他應用程式剪下、複製及貼上</span><span class="sxs-lookup"><span data-stu-id="0bed9-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="0bed9-357">使用貼上的原則管理應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="0bed9-358">限制 Web 內容以顯示於受管理的瀏覽器中</span><span class="sxs-lookup"><span data-stu-id="0bed9-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="0bed9-359">否</span><span class="sxs-lookup"><span data-stu-id="0bed9-359">No</span></span>||
||<span data-ttu-id="0bed9-360">加密應用程式資料</span><span class="sxs-lookup"><span data-stu-id="0bed9-360">Encrypt app data</span></span>|<span data-ttu-id="0bed9-361">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-361">Yes</span></span>|<span data-ttu-id="0bed9-362">在 iOS 上，選取選項：當裝置鎖定時</span><span class="sxs-lookup"><span data-stu-id="0bed9-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="0bed9-363">啟用裝置時停用應用程式加密</span><span class="sxs-lookup"><span data-stu-id="0bed9-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="0bed9-364">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-364">Yes</span></span>|<span data-ttu-id="0bed9-365">停用此設定以避免雙加密</span><span class="sxs-lookup"><span data-stu-id="0bed9-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="0bed9-366">停用聯絡人同步</span><span class="sxs-lookup"><span data-stu-id="0bed9-366">Disable contacts sync</span></span>|<span data-ttu-id="0bed9-367">否</span><span class="sxs-lookup"><span data-stu-id="0bed9-367">No</span></span>||
||<span data-ttu-id="0bed9-368">停用列印</span><span class="sxs-lookup"><span data-stu-id="0bed9-368">Disable printing</span></span>|<span data-ttu-id="0bed9-369">否</span><span class="sxs-lookup"><span data-stu-id="0bed9-369">No</span></span>||
|<span data-ttu-id="0bed9-370">存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-370">Access</span></span>|<span data-ttu-id="0bed9-371">需要 PIN 碼才可存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-371">Require PIN for access</span></span>|<span data-ttu-id="0bed9-372">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-372">Yes</span></span>||
||<span data-ttu-id="0bed9-373">選取類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-373">Select Type</span></span>|<span data-ttu-id="0bed9-374">數值</span><span class="sxs-lookup"><span data-stu-id="0bed9-374">Numeric</span></span>||
||<span data-ttu-id="0bed9-375">允許簡單的 PIN</span><span class="sxs-lookup"><span data-stu-id="0bed9-375">Allow simple PIN</span></span>|<span data-ttu-id="0bed9-376">否</span><span class="sxs-lookup"><span data-stu-id="0bed9-376">No</span></span>||
||<span data-ttu-id="0bed9-377">PIN 長度</span><span class="sxs-lookup"><span data-stu-id="0bed9-377">PIN length</span></span>|<span data-ttu-id="0bed9-378">第</span><span class="sxs-lookup"><span data-stu-id="0bed9-378">6</span></span>||
||<span data-ttu-id="0bed9-379">允許指紋而非 PIN</span><span class="sxs-lookup"><span data-stu-id="0bed9-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="0bed9-380">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-380">Yes</span></span>||
||<span data-ttu-id="0bed9-381">管理裝置 PIN 碼時停用應用程式 PIN 碼</span><span class="sxs-lookup"><span data-stu-id="0bed9-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="0bed9-382">是</span><span class="sxs-lookup"><span data-stu-id="0bed9-382">Yes</span></span>||
||<span data-ttu-id="0bed9-383">需要公司認證才能存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-383">Require corporate credentials for access</span></span>|<span data-ttu-id="0bed9-384">否</span><span class="sxs-lookup"><span data-stu-id="0bed9-384">No</span></span>||
||<span data-ttu-id="0bed9-385">重新檢查存取需求前等候時間 (分鐘)</span><span class="sxs-lookup"><span data-stu-id="0bed9-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="0bed9-386">30</span><span class="sxs-lookup"><span data-stu-id="0bed9-386">30</span></span>||
||<span data-ttu-id="0bed9-387">封鎖螢幕擷取及 Android 助手</span><span class="sxs-lookup"><span data-stu-id="0bed9-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="0bed9-388">否</span><span class="sxs-lookup"><span data-stu-id="0bed9-388">No</span></span>|<span data-ttu-id="0bed9-389">在 iOS 上，這不是可用的選項</span><span class="sxs-lookup"><span data-stu-id="0bed9-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="0bed9-390">登入安全性需求</span><span class="sxs-lookup"><span data-stu-id="0bed9-390">Sign-in security requirements</span></span>|<span data-ttu-id="0bed9-391">最大 PIN 嘗試次數</span><span class="sxs-lookup"><span data-stu-id="0bed9-391">Max PIN attempts</span></span>|<span data-ttu-id="0bed9-392">分</span><span class="sxs-lookup"><span data-stu-id="0bed9-392">5</span></span>|<span data-ttu-id="0bed9-393">重設 Pin 碼</span><span class="sxs-lookup"><span data-stu-id="0bed9-393">Reset Pin</span></span>|
||<span data-ttu-id="0bed9-394">離線寬限期</span><span class="sxs-lookup"><span data-stu-id="0bed9-394">Offline grace period</span></span>|<span data-ttu-id="0bed9-395">720</span><span class="sxs-lookup"><span data-stu-id="0bed9-395">720</span></span>|<span data-ttu-id="0bed9-396">封鎖存取</span><span class="sxs-lookup"><span data-stu-id="0bed9-396">Block access</span></span>|
||<span data-ttu-id="0bed9-397">離線間隔幾天後抹除 App 資料</span><span class="sxs-lookup"><span data-stu-id="0bed9-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="0bed9-398">90</span><span class="sxs-lookup"><span data-stu-id="0bed9-398">90</span></span>|<span data-ttu-id="0bed9-399">清除資料</span><span class="sxs-lookup"><span data-stu-id="0bed9-399">Wipe data</span></span>|
||<span data-ttu-id="0bed9-400">已越獄/根的裝置</span><span class="sxs-lookup"><span data-stu-id="0bed9-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="0bed9-401">清除資料</span><span class="sxs-lookup"><span data-stu-id="0bed9-401">Wipe data</span></span>|

<span data-ttu-id="0bed9-402">完成時, 請記得選取 [建立]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-402">When complete, remember to select "Create".</span></span> <span data-ttu-id="0bed9-403">重複上述步驟，並將選取的平台 (下拉式清單) 取代為 iOS。</span><span class="sxs-lookup"><span data-stu-id="0bed9-403">Repeat the above steps and replace the selected platform (dropdown) with iOS.</span></span> <span data-ttu-id="0bed9-404">這會建立兩個應用程式原則，因此在您建立原則之後，請將群組指派給原則，並進行部署。</span><span class="sxs-lookup"><span data-stu-id="0bed9-404">This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="0bed9-405">若要編輯原則並將這些原則指派給使用者, 請參閱[如何建立及指派應用程式保護原則](https://docs.microsoft.com/intune/app-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="0bed9-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="0bed9-406">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="0bed9-406">Require approved apps</span></span>
<span data-ttu-id="0bed9-407">若要要求核准的應用程式:</span><span class="sxs-lookup"><span data-stu-id="0bed9-407">To require approved apps:</span></span>

1. <span data-ttu-id="0bed9-408">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0bed9-408">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="0bed9-409">在您成功登入之後, 您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="0bed9-409">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="0bed9-410">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="0bed9-411">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="0bed9-412">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="0bed9-413">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="0bed9-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="0bed9-414">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="0bed9-415">選擇 [**選取應用程式**], 從 [**雲端應用程式**] 清單中選取所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0bed9-415">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="0bed9-416">例如, 選取 [Office 365 Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-416">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="0bed9-417">選擇 [**選取**並**完成**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-417">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="0bed9-418">選擇 [**條件**], 選取 [**裝置平臺**], 然後選擇 [**設定**]</span><span class="sxs-lookup"><span data-stu-id="0bed9-418">Choose **Conditions**, select **Device platforms**, then choose **Configure**</span></span>

9. <span data-ttu-id="0bed9-419">在 [**包含**] 下, 選擇 [**選取裝置平臺**], 選取 [ **Android**和**iOS**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-419">Under **Include**, choose **Select device platforms**, select **Android** and **iOS**.</span></span> <span data-ttu-id="0bed9-420">按一下 [**完成**] 並重新**執行**</span><span class="sxs-lookup"><span data-stu-id="0bed9-420">Click **Done** and **Done** again</span></span>

10. <span data-ttu-id="0bed9-421">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-421">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="0bed9-422">選擇 **[授與存取**], 選取 [**要求核准的用戶端 app**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-422">Choose **Grant access**, select **Require approved client app**.</span></span> <span data-ttu-id="0bed9-423">如果是多個控制項, 請選取 **[需要選取的控制項**], 然後選擇 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-423">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

12. <span data-ttu-id="0bed9-424">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="0bed9-424">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="0bed9-425">定義裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="0bed9-425">Define device-compliance policies</span></span>

<span data-ttu-id="0bed9-426">裝置合規性原則定義裝置必須遵守的需求, 才能標示為合規性。</span><span class="sxs-lookup"><span data-stu-id="0bed9-426">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant.</span></span> <span data-ttu-id="0bed9-427">從 Azure 入口網站建立 Intune 裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="0bed9-427">Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="0bed9-428">建立每個平臺的原則:</span><span class="sxs-lookup"><span data-stu-id="0bed9-428">Create a policy for each platform:</span></span>
- <span data-ttu-id="0bed9-429">Android</span><span class="sxs-lookup"><span data-stu-id="0bed9-429">Android</span></span>
- <span data-ttu-id="0bed9-430">Android 企業版</span><span class="sxs-lookup"><span data-stu-id="0bed9-430">Android enterprise</span></span>
- <span data-ttu-id="0bed9-431">適用</span><span class="sxs-lookup"><span data-stu-id="0bed9-431">iOS</span></span>
- <span data-ttu-id="0bed9-432">macOS</span><span class="sxs-lookup"><span data-stu-id="0bed9-432">macOS</span></span>
- <span data-ttu-id="0bed9-433">此設定適用於下列類型的裝置：</span><span class="sxs-lookup"><span data-stu-id="0bed9-433">Windows Phone 8.1</span></span>
- <span data-ttu-id="0bed9-434">Windows 8.1 和更新版本</span><span class="sxs-lookup"><span data-stu-id="0bed9-434">Windows 8.1 and later</span></span>
- <span data-ttu-id="0bed9-435">Windows 10 及更新版本</span><span class="sxs-lookup"><span data-stu-id="0bed9-435">Windows 10 and later</span></span>

<span data-ttu-id="0bed9-436">若要建立裝置合規性原則, 請使用您的管理員認證登入 Microsoft Azure 入口網站, 然後流覽至**Intune > 裝置合規性**。</span><span class="sxs-lookup"><span data-stu-id="0bed9-436">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**.</span></span> <span data-ttu-id="0bed9-437">選取 [**建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-437">Select **Create policy**.</span></span>

<span data-ttu-id="0bed9-438">Windows 10 建議使用下列設定。</span><span class="sxs-lookup"><span data-stu-id="0bed9-438">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="0bed9-439">**裝置健康情況: Windows 健康認證服務評估規則**</span><span class="sxs-lookup"><span data-stu-id="0bed9-439">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="0bed9-440">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-440">Properties</span></span>|<span data-ttu-id="0bed9-441">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-441">Values</span></span>|<span data-ttu-id="0bed9-442">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-442">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="0bed9-443">需要 BitLocker</span><span class="sxs-lookup"><span data-stu-id="0bed9-443">Require BitLocker</span></span>|<span data-ttu-id="0bed9-444">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-444">Require</span></span>||
|<span data-ttu-id="0bed9-445">需要在裝置上啟用安全啟動</span><span class="sxs-lookup"><span data-stu-id="0bed9-445">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="0bed9-446">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-446">Require</span></span>||
|<span data-ttu-id="0bed9-447">需要程式碼完整性</span><span class="sxs-lookup"><span data-stu-id="0bed9-447">Require code integrity</span></span>|<span data-ttu-id="0bed9-448">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-448">Require</span></span>||


<span data-ttu-id="0bed9-449">**裝置內容**</span><span class="sxs-lookup"><span data-stu-id="0bed9-449">**Device properties**</span></span>

|<span data-ttu-id="0bed9-450">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-450">Type</span></span>|<span data-ttu-id="0bed9-451">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-451">Properties</span></span>|<span data-ttu-id="0bed9-452">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-452">Values</span></span>|<span data-ttu-id="0bed9-453">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-453">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-454">作業系統版本</span><span class="sxs-lookup"><span data-stu-id="0bed9-454">Operating system version</span></span>|<span data-ttu-id="0bed9-455">全部</span><span class="sxs-lookup"><span data-stu-id="0bed9-455">All</span></span>|<span data-ttu-id="0bed9-456">尚未設定</span><span class="sxs-lookup"><span data-stu-id="0bed9-456">Not configured</span></span>||

<span data-ttu-id="0bed9-457">針對所有要視為已部署的上述原則，必須將它們的目標設為使用者群組。</span><span class="sxs-lookup"><span data-stu-id="0bed9-457">For all the above policies to be considered deployed, they must be targeted at user groups.</span></span> <span data-ttu-id="0bed9-458">若要執行此作業, 您可以在 [**原則**] 區段中選取 [**管理部署**] (與 [新增] 層級), 以建立原則 (在儲存時) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="0bed9-458">You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="0bed9-459">**系統安全性**</span><span class="sxs-lookup"><span data-stu-id="0bed9-459">**System security**</span></span>

|<span data-ttu-id="0bed9-460">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-460">Type</span></span>|<span data-ttu-id="0bed9-461">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-461">Properties</span></span>|<span data-ttu-id="0bed9-462">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-462">Values</span></span>|<span data-ttu-id="0bed9-463">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-463">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-464">密碼</span><span class="sxs-lookup"><span data-stu-id="0bed9-464">Password</span></span>|<span data-ttu-id="0bed9-465">需要密碼才能解除鎖定行動裝置</span><span class="sxs-lookup"><span data-stu-id="0bed9-465">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="0bed9-466">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-466">Require</span></span>||
||<span data-ttu-id="0bed9-467">簡單密碼</span><span class="sxs-lookup"><span data-stu-id="0bed9-467">Simple passwords</span></span>|<span data-ttu-id="0bed9-468">批</span><span class="sxs-lookup"><span data-stu-id="0bed9-468">Block</span></span>||
||<span data-ttu-id="0bed9-469">密碼類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-469">Password type</span></span>|<span data-ttu-id="0bed9-470">裝置預設值</span><span class="sxs-lookup"><span data-stu-id="0bed9-470">Device default</span></span>||
||<span data-ttu-id="0bed9-471">密碼最小長度</span><span class="sxs-lookup"><span data-stu-id="0bed9-471">Minimum password length</span></span>|<span data-ttu-id="0bed9-472">第</span><span class="sxs-lookup"><span data-stu-id="0bed9-472">6</span></span>||
||<span data-ttu-id="0bed9-473">要求密碼之前的最長閒置時間 (以分鐘為單位)</span><span class="sxs-lookup"><span data-stu-id="0bed9-473">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="0bed9-474">15 </span><span class="sxs-lookup"><span data-stu-id="0bed9-474">15</span></span>|<span data-ttu-id="0bed9-475">此設定支援 Android 版本4.0 及更新版本, 或在 KNOX 4.0 和更新版本。</span><span class="sxs-lookup"><span data-stu-id="0bed9-475">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above.</span></span> <span data-ttu-id="0bed9-476">對於 iOS 裝置, 支援 iOS 8.0 和更新版本</span><span class="sxs-lookup"><span data-stu-id="0bed9-476">For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="0bed9-477">密碼到期 (天)</span><span class="sxs-lookup"><span data-stu-id="0bed9-477">Password expiration (days)</span></span>|<span data-ttu-id="0bed9-478">41</span><span class="sxs-lookup"><span data-stu-id="0bed9-478">41</span></span>||
||<span data-ttu-id="0bed9-479">要防止重複使用的先前密碼數目</span><span class="sxs-lookup"><span data-stu-id="0bed9-479">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="0bed9-480">分</span><span class="sxs-lookup"><span data-stu-id="0bed9-480">5</span></span>||
||<span data-ttu-id="0bed9-481">當裝置從空閒狀態 (Mobile 和全息) 傳回時, 需要密碼</span><span class="sxs-lookup"><span data-stu-id="0bed9-481">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="0bed9-482">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-482">Require</span></span>|<span data-ttu-id="0bed9-483">適用于 Windows 10 及更新版本</span><span class="sxs-lookup"><span data-stu-id="0bed9-483">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="0bed9-484">加密</span><span class="sxs-lookup"><span data-stu-id="0bed9-484">Encryption</span></span>|<span data-ttu-id="0bed9-485">裝置上資料儲存區的加密</span><span class="sxs-lookup"><span data-stu-id="0bed9-485">Encryption of data storage on device</span></span>|<span data-ttu-id="0bed9-486">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-486">Require</span></span>||
|<span data-ttu-id="0bed9-487">裝置安全性</span><span class="sxs-lookup"><span data-stu-id="0bed9-487">Device Security</span></span>|<span data-ttu-id="0bed9-488">防火牆</span><span class="sxs-lookup"><span data-stu-id="0bed9-488">Firewall</span></span>|<span data-ttu-id="0bed9-489">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-489">Require</span></span>||
||<span data-ttu-id="0bed9-490">防毒</span><span class="sxs-lookup"><span data-stu-id="0bed9-490">Antivirus</span></span>|<span data-ttu-id="0bed9-491">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-491">Require</span></span>||
||<span data-ttu-id="0bed9-492">防</span><span class="sxs-lookup"><span data-stu-id="0bed9-492">Antispyware</span></span>|<span data-ttu-id="0bed9-493">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-493">Require</span></span>|<span data-ttu-id="0bed9-494">此設定需要使用 Windows 安全中心註冊的反間諜軟體解決方案</span><span class="sxs-lookup"><span data-stu-id="0bed9-494">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="0bed9-495">Defender</span><span class="sxs-lookup"><span data-stu-id="0bed9-495">Defender</span></span>|<span data-ttu-id="0bed9-496">Windows Defender 反惡意軟體</span><span class="sxs-lookup"><span data-stu-id="0bed9-496">Windows Defender Antimalware</span></span>|<span data-ttu-id="0bed9-497">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-497">Require</span></span>||
||<span data-ttu-id="0bed9-498">Windows Defender 反惡意軟體的最低版本</span><span class="sxs-lookup"><span data-stu-id="0bed9-498">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="0bed9-499">僅支援 Windows 10 桌上出版。</span><span class="sxs-lookup"><span data-stu-id="0bed9-499">Only supported for Windows 10 desktop.</span></span> <span data-ttu-id="0bed9-500">Microsoft 建議版本不超過最新版本五個</span><span class="sxs-lookup"><span data-stu-id="0bed9-500">Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="0bed9-501">Windows Defender 反惡意程式碼簽章為最新狀態</span><span class="sxs-lookup"><span data-stu-id="0bed9-501">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="0bed9-502">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-502">Require</span></span>||
||<span data-ttu-id="0bed9-503">即時保護</span><span class="sxs-lookup"><span data-stu-id="0bed9-503">Real-time protection</span></span>|<span data-ttu-id="0bed9-504">必要</span><span class="sxs-lookup"><span data-stu-id="0bed9-504">Require</span></span>|<span data-ttu-id="0bed9-505">僅支援 Windows 10 桌上出版</span><span class="sxs-lookup"><span data-stu-id="0bed9-505">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="0bed9-506">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="0bed9-506">**Windows Defender ATP**</span></span>

|<span data-ttu-id="0bed9-507">類型</span><span class="sxs-lookup"><span data-stu-id="0bed9-507">Type</span></span>|<span data-ttu-id="0bed9-508">屬性</span><span class="sxs-lookup"><span data-stu-id="0bed9-508">Properties</span></span>|<span data-ttu-id="0bed9-509">值</span><span class="sxs-lookup"><span data-stu-id="0bed9-509">Values</span></span>|<span data-ttu-id="0bed9-510">附註</span><span class="sxs-lookup"><span data-stu-id="0bed9-510">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="0bed9-511">Windows Defender Advanced 威脅防護規則</span><span class="sxs-lookup"><span data-stu-id="0bed9-511">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="0bed9-512">要求裝置位於或低於機器風險分數</span><span class="sxs-lookup"><span data-stu-id="0bed9-512">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="0bed9-513">中</span><span class="sxs-lookup"><span data-stu-id="0bed9-513">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="0bed9-514">需要相容的電腦 (但不相容的電話和平板電腦)</span><span class="sxs-lookup"><span data-stu-id="0bed9-514">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="0bed9-515">將原則新增至需要相容的電腦之前, 請務必在 Intune 中註冊裝置進行管理。</span><span class="sxs-lookup"><span data-stu-id="0bed9-515">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune.</span></span> <span data-ttu-id="0bed9-516">在將裝置註冊到 Intune 之前, 建議使用多重要素驗證, 以確保裝置屬於預定的使用者。</span><span class="sxs-lookup"><span data-stu-id="0bed9-516">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="0bed9-517">若要需要相容的電腦:</span><span class="sxs-lookup"><span data-stu-id="0bed9-517">To require compliant PCs:</span></span>

1. <span data-ttu-id="0bed9-518">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0bed9-518">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="0bed9-519">在您成功登入之後, 您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="0bed9-519">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="0bed9-520">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-520">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="0bed9-521">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-521">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="0bed9-522">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-522">Choose **New policy**.</span></span>

5. <span data-ttu-id="0bed9-523">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="0bed9-523">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="0bed9-524">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-524">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="0bed9-525">選擇 [**選取應用程式**], 從 [**雲端應用程式**] 清單中選取所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0bed9-525">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="0bed9-526">例如, 選取 [Office 365 Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-526">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="0bed9-527">選擇 [**選取**並**完成**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-527">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="0bed9-528">若要需要相容的電腦, 但不相容的電話和平板電腦, 請選擇 [**條件**] 和 [**裝置平臺**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-528">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**.</span></span> <span data-ttu-id="0bed9-529">選擇 [**選取裝置平臺**], 然後選取 [ **Windows** ] 和 [ **macOS**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-529">Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="0bed9-530">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-530">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="0bed9-531">選擇 **[授與存取**], 選取 [**要求裝置被標示為合規性**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-531">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="0bed9-532">如果是多個控制項, 請選取 **[需要所有選取的控制項**], 然後選擇 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-532">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="0bed9-533">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="0bed9-533">Choose **Create**.</span></span>

<span data-ttu-id="0bed9-534">如果您的目標是需要相容*的電腦和*行動裝置, 請勿選取 [平臺]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-534">If your objective is to require compliant PCs *and* mobile devices, do not select platforms.</span></span> <span data-ttu-id="0bed9-535">這會強制執行所有裝置的相容性。</span><span class="sxs-lookup"><span data-stu-id="0bed9-535">This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="0bed9-536">需要相容*的電腦和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="0bed9-536">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="0bed9-537">若要要求所有裝置符合性:</span><span class="sxs-lookup"><span data-stu-id="0bed9-537">To require compliance for all devices:</span></span>

1. <span data-ttu-id="0bed9-538">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="0bed9-538">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="0bed9-539">在您成功登入之後, 您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="0bed9-539">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="0bed9-540">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-540">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="0bed9-541">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-541">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="0bed9-542">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-542">Choose **New policy**.</span></span>

5. <span data-ttu-id="0bed9-543">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="0bed9-543">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="0bed9-544">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-544">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="0bed9-545">選擇 [**選取應用程式**], 從 [**雲端應用程式**] 清單中選取所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0bed9-545">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="0bed9-546">例如, 選取 [Office 365 Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-546">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="0bed9-547">選擇 [**選取**並**完成**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-547">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="0bed9-548">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-548">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="0bed9-549">選擇 **[授與存取**], 選取 [**要求裝置被標示為合規性**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-549">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="0bed9-550">如果是多個控制項, 請選取 **[需要所有選取的控制項**], 然後選擇 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-550">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="0bed9-551">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="0bed9-551">Choose **Create**.</span></span>

<span data-ttu-id="0bed9-552">建立此原則時, 請勿選取 [平臺]。</span><span class="sxs-lookup"><span data-stu-id="0bed9-552">When creating this policy, do not select platforms.</span></span> <span data-ttu-id="0bed9-553">這會強制執行相容的裝置。</span><span class="sxs-lookup"><span data-stu-id="0bed9-553">This enforces compliant devices.</span></span>


## <a name="next-steps"></a><span data-ttu-id="0bed9-554">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0bed9-554">Next steps</span></span>

[<span data-ttu-id="0bed9-555">了解保護電子郵件的原則建議</span><span class="sxs-lookup"><span data-stu-id="0bed9-555">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
