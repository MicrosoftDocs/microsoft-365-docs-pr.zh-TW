---
title: 一般身分識別與裝置存取原則-Microsoft 365 企業版 |Microsoft Docs
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
ms.openlocfilehash: 9912b05c07599c5ad0c0ed7fec91ae2572bd2ead
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289315"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="b1124-103">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="b1124-103">Common identity and device access policies</span></span>
<span data-ttu-id="b1124-104">本文說明的一般建議的原則保護存取雲端服務，包括內部部署應用程式與 Azure AD 應用程式 Proxy 一起發佈。</span><span class="sxs-lookup"><span data-stu-id="b1124-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="b1124-105">本指南將討論如何部署新佈建的環境中建議的原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-105">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment.</span></span> <span data-ttu-id="b1124-106">設定個別的實驗室環境中的這些原則可讓您了解和臨時推行至前期製作和生產環境之前進行評估建議的原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-106">Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments.</span></span> <span data-ttu-id="b1124-107">您新佈建的環境可能僅限雲端或混合式。</span><span class="sxs-lookup"><span data-stu-id="b1124-107">Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="b1124-108">原則設定</span><span class="sxs-lookup"><span data-stu-id="b1124-108">Policy set</span></span> 

<span data-ttu-id="b1124-109">下圖說明這組建議的原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-109">The following diagram illustrates the recommended set of policies.</span></span> <span data-ttu-id="b1124-110">它會顯示哪些層保護於一身的每個原則套用至，以及是否原則套用至電腦或手機和平板電腦裝置這兩個類別。</span><span class="sxs-lookup"><span data-stu-id="b1124-110">It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices.</span></span> <span data-ttu-id="b1124-111">它也會指出已這些原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-111">It also indicates where these policies are configured.</span></span>

![常見的設定身分識別與裝置存取原則](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="b1124-113">本文的其餘部分說明如何設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="b1124-114">建議使用多重要素驗證之前到 Intune 註冊裝置的裝置是在所預期的使用者所持有的保證。</span><span class="sxs-lookup"><span data-stu-id="b1124-114">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> <span data-ttu-id="b1124-115">您也必須到 Intune 註冊裝置，先強制執行裝置合規性原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-115">You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="b1124-116">若要授與您有時間來完成這些工作，我們建議此表格中的比較基準原則實作的順序列出。</span><span class="sxs-lookup"><span data-stu-id="b1124-116">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table.</span></span> <span data-ttu-id="b1124-117">但是，保護機密和高管制的 MFA 原則可實作任何時候。</span><span class="sxs-lookup"><span data-stu-id="b1124-117">However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="b1124-118">保護層級</span><span class="sxs-lookup"><span data-stu-id="b1124-118">Protection level</span></span>|<span data-ttu-id="b1124-119">原則</span><span class="sxs-lookup"><span data-stu-id="b1124-119">Policies</span></span>|<span data-ttu-id="b1124-120">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b1124-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="b1124-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="b1124-121">**Baseline**</span></span>|<span data-ttu-id="b1124-122">[登入風險*中*] 或 [*高*時需要 MFA](#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="b1124-122">[Require MFA when sign-in risk is *medium* or *high*](#require-mfa-based-on-sign-in-risk)</span></span>| |
|        |[<span data-ttu-id="b1124-123">封鎖用戶端不支援新式驗證</span><span class="sxs-lookup"><span data-stu-id="b1124-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="b1124-124">請勿使用新式驗證的用戶端可以略過條件式存取規則，因此請務必封鎖這些</span><span class="sxs-lookup"><span data-stu-id="b1124-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="b1124-125">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="b1124-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="b1124-126">強制使用者變更其密碼，當偵測到高風險的活動時為其帳戶登入</span><span class="sxs-lookup"><span data-stu-id="b1124-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="b1124-127">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="b1124-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="b1124-128">每個平台 (iOS、 Android、 Windows) 的一項原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="b1124-129">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="b1124-130">強制執行手機和平板電腦行動應用程式的保護</span><span class="sxs-lookup"><span data-stu-id="b1124-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="b1124-131">定義裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="b1124-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="b1124-132">每個平台的一個原則</span><span class="sxs-lookup"><span data-stu-id="b1124-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="b1124-133">需要相容的電腦</span><span class="sxs-lookup"><span data-stu-id="b1124-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="b1124-134">強制執行 Intune 管理的電腦</span><span class="sxs-lookup"><span data-stu-id="b1124-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="b1124-135">**敏感性**</span><span class="sxs-lookup"><span data-stu-id="b1124-135">**Sensitive**</span></span>|[<span data-ttu-id="b1124-136">*低*、*中*或*高*登入風險時，需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b1124-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="b1124-137">需要相容電腦*和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="b1124-138">強制執行 Intune 管理的電腦和手機/平板電腦</span><span class="sxs-lookup"><span data-stu-id="b1124-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="b1124-139">**高管制**</span><span class="sxs-lookup"><span data-stu-id="b1124-139">**Highly regulated**</span></span>|[<span data-ttu-id="b1124-140">*永遠*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b1124-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="b1124-141">將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="b1124-141">Assigning policies to users</span></span>
<span data-ttu-id="b1124-142">設定原則之前, 找出您所使用的每一層的保護 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="b1124-142">Before configuring policies, identify the Azure AD groups you are using for each tier of protection.</span></span> <span data-ttu-id="b1124-143">一般而言，基準保護套用至組織中每個人。</span><span class="sxs-lookup"><span data-stu-id="b1124-143">Typically, baseline protection applies to everybody in the organization.</span></span> <span data-ttu-id="b1124-144">包含的比較基準，並且機密保護的使用者必須套用的所有比較基準原則加上的敏感的原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-144">A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies.</span></span> <span data-ttu-id="b1124-145">防護是累計及強制使用最嚴格的原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-145">Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="b1124-146">建議的作法是建立 Azure AD 群組的條件式存取排除項目。</span><span class="sxs-lookup"><span data-stu-id="b1124-146">A recommended practice is to create an Azure AD group for conditional access exclusion.</span></span> <span data-ttu-id="b1124-147">將此群組新增至您的所有條件式存取規則下 」 排除 」。</span><span class="sxs-lookup"><span data-stu-id="b1124-147">Add this group to all of your conditional access rules under "Exclude".</span></span> <span data-ttu-id="b1124-148">這可以讓您存取提供給使用者，而您疑難排解存取問題的方法。</span><span class="sxs-lookup"><span data-stu-id="b1124-148">This gives you a method to provide access to a user while you troubleshoot access issues.</span></span> <span data-ttu-id="b1124-149">這被建議作為暫時解決方案。</span><span class="sxs-lookup"><span data-stu-id="b1124-149">This is recommended as a temporary solution only.</span></span> <span data-ttu-id="b1124-150">監視此群組的變更，並確定只有如預期般正在使用排除群組。</span><span class="sxs-lookup"><span data-stu-id="b1124-150">Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="b1124-151">下圖提供使用者工作分派以及排除項目範例。</span><span class="sxs-lookup"><span data-stu-id="b1124-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![範例使用者指派和 MFA 規則排除](../images/identity-access-policies-assignment.png)

<span data-ttu-id="b1124-153">在圖例中 「 上方秘密專案 X 小組 」 會指派 MFA*一律*需要條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-153">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*.</span></span> <span data-ttu-id="b1124-154">當套用至使用者的高層級的保護，則會明智。</span><span class="sxs-lookup"><span data-stu-id="b1124-154">Be judicious when applying higher levels of protection to users.</span></span> <span data-ttu-id="b1124-155">此專案小組成員都必須提供兩種形式的驗證，每次登入時，即使他們沒有檢視高管制的內容。</span><span class="sxs-lookup"><span data-stu-id="b1124-155">Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="b1124-156">建立這些建議的一部分的所有 Azure AD 群組必須為 Office 365 群組建立。</span><span class="sxs-lookup"><span data-stu-id="b1124-156">All Azure AD groups created as part of these recommendations must be created as Office 365 groups.</span></span> <span data-ttu-id="b1124-157">在 SharePoint Online 中保護文件時，這對於部署 Azure 資訊保護 (AIP) 特別重要。</span><span class="sxs-lookup"><span data-stu-id="b1124-157">This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![建立 Office 365 群組的螢幕擷取](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="b1124-159">需要根據登入風險的 MFA</span><span class="sxs-lookup"><span data-stu-id="b1124-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="b1124-160">之前需要 MFA，第一次使用 Identity Protection MFA 註冊原則來註冊使用者的 mfa 功能。</span><span class="sxs-lookup"><span data-stu-id="b1124-160">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA.</span></span> <span data-ttu-id="b1124-161">登錄使用者之後，您可以強制 MFA 登入。</span><span class="sxs-lookup"><span data-stu-id="b1124-161">After users are registered you can enforce MFA for sign-in.</span></span> <span data-ttu-id="b1124-162">[必要工作](identity-access-prerequisites.md)包括將所有使用者都註冊使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="b1124-162">The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="b1124-163">若要建立新的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="b1124-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="b1124-164">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="b1124-164">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="b1124-165">您已成功登入之後，您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="b1124-165">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="b1124-166">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="b1124-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b1124-167">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="b1124-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b1124-168">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="b1124-168">Choose **New policy**.</span></span>

![基準 CA 原則](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="b1124-170">下表描述要針對這個原則實作的條件式存取原則設定。</span><span class="sxs-lookup"><span data-stu-id="b1124-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="b1124-171">**指派**</span><span class="sxs-lookup"><span data-stu-id="b1124-171">**Assignments**</span></span>

|<span data-ttu-id="b1124-172">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-172">Type</span></span>|<span data-ttu-id="b1124-173">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-173">Properties</span></span>|<span data-ttu-id="b1124-174">值</span><span class="sxs-lookup"><span data-stu-id="b1124-174">Values</span></span>|<span data-ttu-id="b1124-175">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-176">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="b1124-176">Users and groups</span></span>|<span data-ttu-id="b1124-177">Include</span><span class="sxs-lookup"><span data-stu-id="b1124-177">Include</span></span>|<span data-ttu-id="b1124-178">選取使用者和群組 - 選取包含目標使用者的特定安全性群組</span><span class="sxs-lookup"><span data-stu-id="b1124-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="b1124-179">從包含試驗使用者的安全性群組開始</span><span class="sxs-lookup"><span data-stu-id="b1124-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="b1124-180">排除</span><span class="sxs-lookup"><span data-stu-id="b1124-180">Exclude</span></span>|<span data-ttu-id="b1124-181">例外狀況安全性群組；服務帳戶 (應用程式身分識別)</span><span class="sxs-lookup"><span data-stu-id="b1124-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="b1124-182">根據視需要暫時修改成員資格</span><span class="sxs-lookup"><span data-stu-id="b1124-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="b1124-183">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-183">Cloud apps</span></span>|<span data-ttu-id="b1124-184">Include</span><span class="sxs-lookup"><span data-stu-id="b1124-184">Include</span></span>|<span data-ttu-id="b1124-185">選取您想要此規則套用至應用的程式。</span><span class="sxs-lookup"><span data-stu-id="b1124-185">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="b1124-186">例如，選取 [Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1124-186">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="b1124-187">條件</span><span class="sxs-lookup"><span data-stu-id="b1124-187">Conditions</span></span>|<span data-ttu-id="b1124-188">已設定</span><span class="sxs-lookup"><span data-stu-id="b1124-188">Configured</span></span>|<span data-ttu-id="b1124-189">是</span><span class="sxs-lookup"><span data-stu-id="b1124-189">Yes</span></span>|<span data-ttu-id="b1124-190">進行您環境和需求的特定設定</span><span class="sxs-lookup"><span data-stu-id="b1124-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="b1124-191">登入風險</span><span class="sxs-lookup"><span data-stu-id="b1124-191">Sign-in risk</span></span>|<span data-ttu-id="b1124-192">風險層級</span><span class="sxs-lookup"><span data-stu-id="b1124-192">Risk level</span></span>||<span data-ttu-id="b1124-193">請參閱下表中的指引</span><span class="sxs-lookup"><span data-stu-id="b1124-193">See the guidance in the following table</span></span>|

<span data-ttu-id="b1124-194">**登入風險**</span><span class="sxs-lookup"><span data-stu-id="b1124-194">**Sign-in risk**</span></span>

<span data-ttu-id="b1124-195">適用於根據您的目標的保護層級的設定。</span><span class="sxs-lookup"><span data-stu-id="b1124-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="b1124-196">屬性	</span><span class="sxs-lookup"><span data-stu-id="b1124-196">Property</span></span>|<span data-ttu-id="b1124-197">保護層級</span><span class="sxs-lookup"><span data-stu-id="b1124-197">Level of protection</span></span>|<span data-ttu-id="b1124-198">值</span><span class="sxs-lookup"><span data-stu-id="b1124-198">Values</span></span>|<span data-ttu-id="b1124-199">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-200">風險層級</span><span class="sxs-lookup"><span data-stu-id="b1124-200">Risk level</span></span>|<span data-ttu-id="b1124-201">基準</span><span class="sxs-lookup"><span data-stu-id="b1124-201">Baseline</span></span>|<span data-ttu-id="b1124-202">高、中</span><span class="sxs-lookup"><span data-stu-id="b1124-202">High, medium</span></span>|<span data-ttu-id="b1124-203">檢查兩者</span><span class="sxs-lookup"><span data-stu-id="b1124-203">Check both</span></span>|
| |<span data-ttu-id="b1124-204">敏感性</span><span class="sxs-lookup"><span data-stu-id="b1124-204">Sensitive</span></span>|<span data-ttu-id="b1124-205">高、 中、 低</span><span class="sxs-lookup"><span data-stu-id="b1124-205">High, medium, low</span></span>|<span data-ttu-id="b1124-206">三個全選</span><span class="sxs-lookup"><span data-stu-id="b1124-206">Check all three</span></span>|
| |<span data-ttu-id="b1124-207">高管制</span><span class="sxs-lookup"><span data-stu-id="b1124-207">Highly regulated</span></span>| |<span data-ttu-id="b1124-208">保留所有選項已取消核取一律強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="b1124-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="b1124-209">**存取控制**</span><span class="sxs-lookup"><span data-stu-id="b1124-209">**Access controls**</span></span>

|<span data-ttu-id="b1124-210">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-210">Type</span></span>|<span data-ttu-id="b1124-211">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-211">Properties</span></span>|<span data-ttu-id="b1124-212">值</span><span class="sxs-lookup"><span data-stu-id="b1124-212">Values</span></span>|<span data-ttu-id="b1124-213">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-214">授與</span><span class="sxs-lookup"><span data-stu-id="b1124-214">Grant</span></span>|<span data-ttu-id="b1124-215">授予存取</span><span class="sxs-lookup"><span data-stu-id="b1124-215">Grant access</span></span>|<span data-ttu-id="b1124-216">True</span><span class="sxs-lookup"><span data-stu-id="b1124-216">True</span></span>|<span data-ttu-id="b1124-217">已選取</span><span class="sxs-lookup"><span data-stu-id="b1124-217">Selected</span></span>|
||<span data-ttu-id="b1124-218">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b1124-218">Require MFA</span></span>|<span data-ttu-id="b1124-219">True</span><span class="sxs-lookup"><span data-stu-id="b1124-219">True</span></span>|<span data-ttu-id="b1124-220">Check</span><span class="sxs-lookup"><span data-stu-id="b1124-220">Check</span></span>|
||<span data-ttu-id="b1124-221">需要裝置標記為相容</span><span class="sxs-lookup"><span data-stu-id="b1124-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="b1124-222">False</span><span class="sxs-lookup"><span data-stu-id="b1124-222">False</span></span>||
||<span data-ttu-id="b1124-223">需要混合式 Azure AD 加入的裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="b1124-224">False</span><span class="sxs-lookup"><span data-stu-id="b1124-224">False</span></span>||
||<span data-ttu-id="b1124-225">需要核准的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-225">Require approved client app</span></span>|<span data-ttu-id="b1124-226">False</span><span class="sxs-lookup"><span data-stu-id="b1124-226">False</span></span>||
||<span data-ttu-id="b1124-227">需要所有選取的控制項</span><span class="sxs-lookup"><span data-stu-id="b1124-227">Require all the selected controls</span></span>|<span data-ttu-id="b1124-228">True</span><span class="sxs-lookup"><span data-stu-id="b1124-228">True</span></span>|<span data-ttu-id="b1124-229">已選取</span><span class="sxs-lookup"><span data-stu-id="b1124-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="b1124-230">請務必啟用此原則中，選擇 [**上**。</span><span class="sxs-lookup"><span data-stu-id="b1124-230">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="b1124-231">也請考慮使用[怎麼](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-231">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="b1124-232">封鎖用戶端不支援新式驗證</span><span class="sxs-lookup"><span data-stu-id="b1124-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="b1124-233">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="b1124-233">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="b1124-234">您已成功登入之後，您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="b1124-234">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="b1124-235">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="b1124-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b1124-236">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="b1124-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b1124-237">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="b1124-237">Choose **New policy**.</span></span>

<span data-ttu-id="b1124-238">下表描述要針對這個原則實作的條件式存取原則設定。</span><span class="sxs-lookup"><span data-stu-id="b1124-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="b1124-239">**指派**</span><span class="sxs-lookup"><span data-stu-id="b1124-239">**Assignments**</span></span>

|<span data-ttu-id="b1124-240">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-240">Type</span></span>|<span data-ttu-id="b1124-241">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-241">Properties</span></span>|<span data-ttu-id="b1124-242">值</span><span class="sxs-lookup"><span data-stu-id="b1124-242">Values</span></span>|<span data-ttu-id="b1124-243">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-244">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="b1124-244">Users and groups</span></span>|<span data-ttu-id="b1124-245">Include</span><span class="sxs-lookup"><span data-stu-id="b1124-245">Include</span></span>|<span data-ttu-id="b1124-246">選取使用者和群組 - 選取包含目標使用者的特定安全性群組</span><span class="sxs-lookup"><span data-stu-id="b1124-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="b1124-247">從包含試驗使用者的安全性群組開始</span><span class="sxs-lookup"><span data-stu-id="b1124-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="b1124-248">排除</span><span class="sxs-lookup"><span data-stu-id="b1124-248">Exclude</span></span>|<span data-ttu-id="b1124-249">例外狀況安全性群組；服務帳戶 (應用程式身分識別)</span><span class="sxs-lookup"><span data-stu-id="b1124-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="b1124-250">視需要暫時修改成員資格</span><span class="sxs-lookup"><span data-stu-id="b1124-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="b1124-251">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-251">Cloud apps</span></span>|<span data-ttu-id="b1124-252">Include</span><span class="sxs-lookup"><span data-stu-id="b1124-252">Include</span></span>|<span data-ttu-id="b1124-253">選取您想要此規則套用至應用的程式。</span><span class="sxs-lookup"><span data-stu-id="b1124-253">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="b1124-254">例如，選取 [Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1124-254">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="b1124-255">條件</span><span class="sxs-lookup"><span data-stu-id="b1124-255">Conditions</span></span>|<span data-ttu-id="b1124-256">已設定</span><span class="sxs-lookup"><span data-stu-id="b1124-256">Configured</span></span>|<span data-ttu-id="b1124-257">是</span><span class="sxs-lookup"><span data-stu-id="b1124-257">Yes</span></span>|<span data-ttu-id="b1124-258">設定用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-258">Configure Client apps</span></span>|
|<span data-ttu-id="b1124-259">用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-259">Client apps</span></span>|<span data-ttu-id="b1124-260">已設定</span><span class="sxs-lookup"><span data-stu-id="b1124-260">Configured</span></span>|<span data-ttu-id="b1124-261">是</span><span class="sxs-lookup"><span data-stu-id="b1124-261">Yes</span></span>|<span data-ttu-id="b1124-262">桌面用戶端，（選取兩者） 其他用戶端和行動應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="b1124-263">**存取控制**</span><span class="sxs-lookup"><span data-stu-id="b1124-263">**Access controls**</span></span>

|<span data-ttu-id="b1124-264">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-264">Type</span></span>|<span data-ttu-id="b1124-265">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-265">Properties</span></span>|<span data-ttu-id="b1124-266">值</span><span class="sxs-lookup"><span data-stu-id="b1124-266">Values</span></span>|<span data-ttu-id="b1124-267">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-268">授與</span><span class="sxs-lookup"><span data-stu-id="b1124-268">Grant</span></span>|<span data-ttu-id="b1124-269">封鎖存取</span><span class="sxs-lookup"><span data-stu-id="b1124-269">Block access</span></span>|<span data-ttu-id="b1124-270">True</span><span class="sxs-lookup"><span data-stu-id="b1124-270">True</span></span>|<span data-ttu-id="b1124-271">已選取</span><span class="sxs-lookup"><span data-stu-id="b1124-271">Selected</span></span>|
||<span data-ttu-id="b1124-272">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="b1124-272">Require MFA</span></span>|<span data-ttu-id="b1124-273">False</span><span class="sxs-lookup"><span data-stu-id="b1124-273">False</span></span>||
||<span data-ttu-id="b1124-274">需要裝置標記為相容</span><span class="sxs-lookup"><span data-stu-id="b1124-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="b1124-275">False</span><span class="sxs-lookup"><span data-stu-id="b1124-275">False</span></span>||
||<span data-ttu-id="b1124-276">需要混合式 Azure AD 加入的裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="b1124-277">False</span><span class="sxs-lookup"><span data-stu-id="b1124-277">False</span></span>||
||<span data-ttu-id="b1124-278">需要核准的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-278">Require approved client app</span></span>|<span data-ttu-id="b1124-279">False</span><span class="sxs-lookup"><span data-stu-id="b1124-279">False</span></span>||
||<span data-ttu-id="b1124-280">需要所有選取的控制項</span><span class="sxs-lookup"><span data-stu-id="b1124-280">Require all the selected controls</span></span>|<span data-ttu-id="b1124-281">True</span><span class="sxs-lookup"><span data-stu-id="b1124-281">True</span></span>|<span data-ttu-id="b1124-282">已選取</span><span class="sxs-lookup"><span data-stu-id="b1124-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="b1124-283">請務必啟用此原則中，選擇 [**上**。</span><span class="sxs-lookup"><span data-stu-id="b1124-283">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="b1124-284">也請考慮使用[怎麼](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-284">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="b1124-285">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="b1124-285">High risk users must change password</span></span>
<span data-ttu-id="b1124-286">若要確保所有高風險使用者遭入侵的帳戶強制執行密碼變更登入時，您必須套用下列原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="b1124-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span><span class="sxs-lookup"><span data-stu-id="b1124-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="b1124-288">**指派**</span><span class="sxs-lookup"><span data-stu-id="b1124-288">**Assignments**</span></span>

|<span data-ttu-id="b1124-289">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-289">Type</span></span>|<span data-ttu-id="b1124-290">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-290">Properties</span></span>|<span data-ttu-id="b1124-291">值</span><span class="sxs-lookup"><span data-stu-id="b1124-291">Values</span></span>|<span data-ttu-id="b1124-292">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-293">使用者</span><span class="sxs-lookup"><span data-stu-id="b1124-293">Users</span></span>|<span data-ttu-id="b1124-294">Include</span><span class="sxs-lookup"><span data-stu-id="b1124-294">Include</span></span>|<span data-ttu-id="b1124-295">所有使用者</span><span class="sxs-lookup"><span data-stu-id="b1124-295">All users</span></span>|<span data-ttu-id="b1124-296">已選取</span><span class="sxs-lookup"><span data-stu-id="b1124-296">Selected</span></span>|
||<span data-ttu-id="b1124-297">排除</span><span class="sxs-lookup"><span data-stu-id="b1124-297">Exclude</span></span>|<span data-ttu-id="b1124-298">無</span><span class="sxs-lookup"><span data-stu-id="b1124-298">None</span></span>||
|<span data-ttu-id="b1124-299">條件</span><span class="sxs-lookup"><span data-stu-id="b1124-299">Conditions</span></span>|<span data-ttu-id="b1124-300">使用者風險</span><span class="sxs-lookup"><span data-stu-id="b1124-300">User risk</span></span>|<span data-ttu-id="b1124-301">高</span><span class="sxs-lookup"><span data-stu-id="b1124-301">High</span></span>|<span data-ttu-id="b1124-302">已選取</span><span class="sxs-lookup"><span data-stu-id="b1124-302">Selected</span></span>|

<span data-ttu-id="b1124-303">**控制項**</span><span class="sxs-lookup"><span data-stu-id="b1124-303">**Controls**</span></span>

| <span data-ttu-id="b1124-304">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-304">Type</span></span> | <span data-ttu-id="b1124-305">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-305">Properties</span></span> | <span data-ttu-id="b1124-306">值</span><span class="sxs-lookup"><span data-stu-id="b1124-306">Values</span></span>                  | <span data-ttu-id="b1124-307">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="b1124-308">Access</span><span class="sxs-lookup"><span data-stu-id="b1124-308">Access</span></span>     | <span data-ttu-id="b1124-309">允許存取</span><span class="sxs-lookup"><span data-stu-id="b1124-309">Allow access</span></span>            | <span data-ttu-id="b1124-310">True</span><span class="sxs-lookup"><span data-stu-id="b1124-310">True</span></span>  |
|      | <span data-ttu-id="b1124-311">Access</span><span class="sxs-lookup"><span data-stu-id="b1124-311">Access</span></span>     | <span data-ttu-id="b1124-312">需要密碼變更</span><span class="sxs-lookup"><span data-stu-id="b1124-312">Require password change</span></span> | <span data-ttu-id="b1124-313">True</span><span class="sxs-lookup"><span data-stu-id="b1124-313">True</span></span>  |

<span data-ttu-id="b1124-314">**檢閱：** 不適用</span><span class="sxs-lookup"><span data-stu-id="b1124-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="b1124-315">請務必啟用此原則中，選擇 [**上**。</span><span class="sxs-lookup"><span data-stu-id="b1124-315">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="b1124-316">也請考慮使用 「[如果](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)」 工具來測試原則</span><span class="sxs-lookup"><span data-stu-id="b1124-316">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="b1124-317">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="b1124-317">Define app protection policies</span></span>
<span data-ttu-id="b1124-318">應用程式保護原則定義允許哪些應用程式和與貴組織的資料可採取的動作。</span><span class="sxs-lookup"><span data-stu-id="b1124-318">App protection policies define which apps are allowed and the actions they can take with your organization's data.</span></span> <span data-ttu-id="b1124-319">建立 Intune 應用程式保護原則從 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="b1124-319">Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="b1124-320">建立每個平台的原則：</span><span class="sxs-lookup"><span data-stu-id="b1124-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="b1124-321">iOS</span><span class="sxs-lookup"><span data-stu-id="b1124-321">iOS</span></span>
- <span data-ttu-id="b1124-322">Android</span><span class="sxs-lookup"><span data-stu-id="b1124-322">Android</span></span>
- <span data-ttu-id="b1124-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b1124-323">Windows 10</span></span>

<span data-ttu-id="b1124-324">若要建立新的應用程式保護原則，請登入與您的系統管理員認證，在 Microsoft Azure 入口網站，然後瀏覽至 [**行動裝置 app > 應用程式保護原則**。</span><span class="sxs-lookup"><span data-stu-id="b1124-324">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**.</span></span> <span data-ttu-id="b1124-325">選擇 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="b1124-325">Choose **Add a policy**.</span></span>

<span data-ttu-id="b1124-326">iOS 與 Android 的應用程式防護原則選項有些許差異。</span><span class="sxs-lookup"><span data-stu-id="b1124-326">There are slight differences in the app protection policy options between iOS and Android.</span></span> <span data-ttu-id="b1124-327">下列原則專用於 Android。</span><span class="sxs-lookup"><span data-stu-id="b1124-327">The below policy is specifically for Android.</span></span> <span data-ttu-id="b1124-328">使用此做為指南的其他原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-328">Use this as a guide for your other policies.</span></span>

<span data-ttu-id="b1124-329">建議的應用程式清單包含下列特性：</span><span class="sxs-lookup"><span data-stu-id="b1124-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="b1124-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b1124-330">PowerPoint</span></span>
- <span data-ttu-id="b1124-331">Excel</span><span class="sxs-lookup"><span data-stu-id="b1124-331">Excel</span></span>
- <span data-ttu-id="b1124-332">Word</span><span class="sxs-lookup"><span data-stu-id="b1124-332">Word</span></span>
- <span data-ttu-id="b1124-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1124-333">Microsoft Teams</span></span>
- <span data-ttu-id="b1124-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="b1124-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="b1124-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="b1124-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="b1124-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b1124-336">OneDrive</span></span>
- <span data-ttu-id="b1124-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="b1124-337">OneNote</span></span>
- <span data-ttu-id="b1124-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="b1124-338">Outlook</span></span>

<span data-ttu-id="b1124-339">下表說明建議的設定：</span><span class="sxs-lookup"><span data-stu-id="b1124-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="b1124-340">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-340">Type</span></span>|<span data-ttu-id="b1124-341">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-341">Properties</span></span>|<span data-ttu-id="b1124-342">值</span><span class="sxs-lookup"><span data-stu-id="b1124-342">Values</span></span>|<span data-ttu-id="b1124-343">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-344">資料重新配置</span><span class="sxs-lookup"><span data-stu-id="b1124-344">Data relocation</span></span>|<span data-ttu-id="b1124-345">禁止 Android 備份</span><span class="sxs-lookup"><span data-stu-id="b1124-345">Prevent Android backup</span></span>|<span data-ttu-id="b1124-346">是</span><span class="sxs-lookup"><span data-stu-id="b1124-346">Yes</span></span>|<span data-ttu-id="b1124-347">在 iOS 上，這會特別呼叫 iTunes 和 iCloud</span><span class="sxs-lookup"><span data-stu-id="b1124-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="b1124-348">允許應用程式將資料傳送到其他應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="b1124-349">受原則管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-349">Policy managed apps</span></span>||
||<span data-ttu-id="b1124-350">[允許應用程式接收其他應用程式的資料]</span><span class="sxs-lookup"><span data-stu-id="b1124-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="b1124-351">受原則管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-351">Policy managed apps</span></span>||
||<span data-ttu-id="b1124-352">禁止執行 [另存新檔]</span><span class="sxs-lookup"><span data-stu-id="b1124-352">Prevent "Save As"</span></span>|<span data-ttu-id="b1124-353">是</span><span class="sxs-lookup"><span data-stu-id="b1124-353">Yes</span></span>||
||<span data-ttu-id="b1124-354">選取可儲存公司資料的儲存體服務</span><span class="sxs-lookup"><span data-stu-id="b1124-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="b1124-355">OneDrive for Business，SharePoint</span><span class="sxs-lookup"><span data-stu-id="b1124-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="b1124-356">限制利用其他應用程式剪下、複製及貼上</span><span class="sxs-lookup"><span data-stu-id="b1124-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="b1124-357">使用貼上的受原則管理應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="b1124-358">限制 Web 內容以顯示於受管理的瀏覽器中</span><span class="sxs-lookup"><span data-stu-id="b1124-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="b1124-359">否</span><span class="sxs-lookup"><span data-stu-id="b1124-359">No</span></span>||
||<span data-ttu-id="b1124-360">加密應用程式資料</span><span class="sxs-lookup"><span data-stu-id="b1124-360">Encrypt app data</span></span>|<span data-ttu-id="b1124-361">是</span><span class="sxs-lookup"><span data-stu-id="b1124-361">Yes</span></span>|<span data-ttu-id="b1124-362">在 iOS 上，選取選項：當裝置鎖定時</span><span class="sxs-lookup"><span data-stu-id="b1124-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="b1124-363">停用應用程式加密，當已啟用裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="b1124-364">是</span><span class="sxs-lookup"><span data-stu-id="b1124-364">Yes</span></span>|<span data-ttu-id="b1124-365">停用此設定，以避免雙加密</span><span class="sxs-lookup"><span data-stu-id="b1124-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="b1124-366">停用聯絡人同步</span><span class="sxs-lookup"><span data-stu-id="b1124-366">Disable contacts sync</span></span>|<span data-ttu-id="b1124-367">否</span><span class="sxs-lookup"><span data-stu-id="b1124-367">No</span></span>||
||<span data-ttu-id="b1124-368">停用列印</span><span class="sxs-lookup"><span data-stu-id="b1124-368">Disable printing</span></span>|<span data-ttu-id="b1124-369">否</span><span class="sxs-lookup"><span data-stu-id="b1124-369">No</span></span>||
|<span data-ttu-id="b1124-370">存取</span><span class="sxs-lookup"><span data-stu-id="b1124-370">Access</span></span>|<span data-ttu-id="b1124-371">需要 PIN 碼才可存取</span><span class="sxs-lookup"><span data-stu-id="b1124-371">Require PIN for access</span></span>|<span data-ttu-id="b1124-372">是</span><span class="sxs-lookup"><span data-stu-id="b1124-372">Yes</span></span>||
||<span data-ttu-id="b1124-373">選取類型</span><span class="sxs-lookup"><span data-stu-id="b1124-373">Select Type</span></span>|<span data-ttu-id="b1124-374">數值</span><span class="sxs-lookup"><span data-stu-id="b1124-374">Numeric</span></span>||
||<span data-ttu-id="b1124-375">允許簡單的 PIN</span><span class="sxs-lookup"><span data-stu-id="b1124-375">Allow simple PIN</span></span>|<span data-ttu-id="b1124-376">否</span><span class="sxs-lookup"><span data-stu-id="b1124-376">No</span></span>||
||<span data-ttu-id="b1124-377">PIN 長度</span><span class="sxs-lookup"><span data-stu-id="b1124-377">PIN length</span></span>|<span data-ttu-id="b1124-378">6</span><span class="sxs-lookup"><span data-stu-id="b1124-378">6</span></span>||
||<span data-ttu-id="b1124-379">允許指紋而非 PIN</span><span class="sxs-lookup"><span data-stu-id="b1124-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="b1124-380">是</span><span class="sxs-lookup"><span data-stu-id="b1124-380">Yes</span></span>||
||<span data-ttu-id="b1124-381">管理裝置的 pin 碼時，停用應用程式的 pin 碼</span><span class="sxs-lookup"><span data-stu-id="b1124-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="b1124-382">是</span><span class="sxs-lookup"><span data-stu-id="b1124-382">Yes</span></span>||
||<span data-ttu-id="b1124-383">需要公司認證才能存取</span><span class="sxs-lookup"><span data-stu-id="b1124-383">Require corporate credentials for access</span></span>|<span data-ttu-id="b1124-384">否</span><span class="sxs-lookup"><span data-stu-id="b1124-384">No</span></span>||
||<span data-ttu-id="b1124-385">重新檢查存取需求前等候時間 (分鐘)</span><span class="sxs-lookup"><span data-stu-id="b1124-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="b1124-386">30</span><span class="sxs-lookup"><span data-stu-id="b1124-386">30</span></span>||
||<span data-ttu-id="b1124-387">封鎖螢幕擷取及 Android 助手</span><span class="sxs-lookup"><span data-stu-id="b1124-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="b1124-388">否</span><span class="sxs-lookup"><span data-stu-id="b1124-388">No</span></span>|<span data-ttu-id="b1124-389">在 iOS 上，這不是可用的選項</span><span class="sxs-lookup"><span data-stu-id="b1124-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="b1124-390">登入安全性需求</span><span class="sxs-lookup"><span data-stu-id="b1124-390">Sign-in security requirements</span></span>|<span data-ttu-id="b1124-391">最大 PIN 嘗試次數</span><span class="sxs-lookup"><span data-stu-id="b1124-391">Max PIN attempts</span></span>|<span data-ttu-id="b1124-392">5</span><span class="sxs-lookup"><span data-stu-id="b1124-392">5</span></span>|<span data-ttu-id="b1124-393">重設 pin 碼</span><span class="sxs-lookup"><span data-stu-id="b1124-393">Reset Pin</span></span>|
||<span data-ttu-id="b1124-394">離線寬限期</span><span class="sxs-lookup"><span data-stu-id="b1124-394">Offline grace period</span></span>|<span data-ttu-id="b1124-395">720</span><span class="sxs-lookup"><span data-stu-id="b1124-395">720</span></span>|<span data-ttu-id="b1124-396">封鎖存取</span><span class="sxs-lookup"><span data-stu-id="b1124-396">Block access</span></span>|
||<span data-ttu-id="b1124-397">離線間隔幾天後抹除 App 資料</span><span class="sxs-lookup"><span data-stu-id="b1124-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="b1124-398">90</span><span class="sxs-lookup"><span data-stu-id="b1124-398">90</span></span>|<span data-ttu-id="b1124-399">清除資料</span><span class="sxs-lookup"><span data-stu-id="b1124-399">Wipe data</span></span>|
||<span data-ttu-id="b1124-400">已進行 Jb/root 破解的裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="b1124-401">清除資料</span><span class="sxs-lookup"><span data-stu-id="b1124-401">Wipe data</span></span>|

<span data-ttu-id="b1124-402">完成後，請記住，選取 「 建立 」。</span><span class="sxs-lookup"><span data-stu-id="b1124-402">When complete, remember to select "Create".</span></span> <span data-ttu-id="b1124-403">重複上述步驟，並將選取的平台 (下拉式清單) 取代為 iOS。</span><span class="sxs-lookup"><span data-stu-id="b1124-403">Repeat the above steps and replace the selected platform (dropdown) with iOS.</span></span> <span data-ttu-id="b1124-404">這會建立兩個應用程式原則，因此在您建立原則之後，請將群組指派給原則，並進行部署。</span><span class="sxs-lookup"><span data-stu-id="b1124-404">This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="b1124-405">若要編輯原則，並將這些原則指派給使用者，請參閱 <<c0>如何建立及指派應用程式保護原則。</span><span class="sxs-lookup"><span data-stu-id="b1124-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="b1124-406">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="b1124-406">Require approved apps</span></span>
<span data-ttu-id="b1124-407">若要需要核准的應用程式：</span><span class="sxs-lookup"><span data-stu-id="b1124-407">To require approved apps:</span></span>

1. <span data-ttu-id="b1124-408">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="b1124-408">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="b1124-409">您已成功登入之後，您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="b1124-409">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="b1124-410">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="b1124-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b1124-411">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="b1124-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b1124-412">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="b1124-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="b1124-413">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="b1124-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="b1124-414">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="b1124-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="b1124-415">選擇 [**選取應用程式**，從**雲端應用程式**清單中選取所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b1124-415">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="b1124-416">例如，選取 [Office 365 Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="b1124-416">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="b1124-417">選擇 [**選取**和**完成**]。</span><span class="sxs-lookup"><span data-stu-id="b1124-417">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="b1124-418">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="b1124-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="b1124-419">選擇 [**授與存取權**，請選取 [**需要核准用戶端應用程式**。</span><span class="sxs-lookup"><span data-stu-id="b1124-419">Choose **Grant access**, select **Require approved client app**.</span></span> <span data-ttu-id="b1124-420">對於多個控制項，請選取 [**需要選取的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="b1124-420">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="b1124-421">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="b1124-421">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="b1124-422">定義裝置合規性原則</span><span class="sxs-lookup"><span data-stu-id="b1124-422">Define device-compliance policies</span></span>

<span data-ttu-id="b1124-423">裝置合規性原則定義的裝置必須遵守才能標記為相容的需求。</span><span class="sxs-lookup"><span data-stu-id="b1124-423">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant.</span></span> <span data-ttu-id="b1124-424">建立 Intune 裝置合規性原則從 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="b1124-424">Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="b1124-425">建立每個平台的原則：</span><span class="sxs-lookup"><span data-stu-id="b1124-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="b1124-426">Android</span><span class="sxs-lookup"><span data-stu-id="b1124-426">Android</span></span>
- <span data-ttu-id="b1124-427">Android 的企業</span><span class="sxs-lookup"><span data-stu-id="b1124-427">Android enterprise</span></span>
- <span data-ttu-id="b1124-428">iOS</span><span class="sxs-lookup"><span data-stu-id="b1124-428">iOS</span></span>
- <span data-ttu-id="b1124-429">macOS</span><span class="sxs-lookup"><span data-stu-id="b1124-429">macOS</span></span>
- <span data-ttu-id="b1124-430">此設定適用於下列類型的裝置：</span><span class="sxs-lookup"><span data-stu-id="b1124-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="b1124-431">Windows 8.1 和更新版本</span><span class="sxs-lookup"><span data-stu-id="b1124-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="b1124-432">Windows 10 和更新版本</span><span class="sxs-lookup"><span data-stu-id="b1124-432">Windows 10 and later</span></span>

<span data-ttu-id="b1124-433">若要建立裝置合規性原則，登入與您的系統管理員認證，在 Microsoft Azure 入口網站，然後瀏覽至 [ **Intune > 裝置相容性**。</span><span class="sxs-lookup"><span data-stu-id="b1124-433">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**.</span></span> <span data-ttu-id="b1124-434">選取 [**建立原則**。</span><span class="sxs-lookup"><span data-stu-id="b1124-434">Select **Create policy**.</span></span>

<span data-ttu-id="b1124-435">適用於 Windows 10 建議使用下列設定值。</span><span class="sxs-lookup"><span data-stu-id="b1124-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="b1124-436">**裝置健全狀況： Windows 健全狀況證明服務評估規則**</span><span class="sxs-lookup"><span data-stu-id="b1124-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="b1124-437">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-437">Properties</span></span>|<span data-ttu-id="b1124-438">值</span><span class="sxs-lookup"><span data-stu-id="b1124-438">Values</span></span>|<span data-ttu-id="b1124-439">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="b1124-440">需要 BitLocker</span><span class="sxs-lookup"><span data-stu-id="b1124-440">Require BitLocker</span></span>|<span data-ttu-id="b1124-441">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-441">Require</span></span>||
|<span data-ttu-id="b1124-442">需要安全開機，以在裝置上啟用</span><span class="sxs-lookup"><span data-stu-id="b1124-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="b1124-443">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-443">Require</span></span>||
|<span data-ttu-id="b1124-444">需要的程式碼完整性</span><span class="sxs-lookup"><span data-stu-id="b1124-444">Require code integrity</span></span>|<span data-ttu-id="b1124-445">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-445">Require</span></span>||


<span data-ttu-id="b1124-446">**裝置內容**</span><span class="sxs-lookup"><span data-stu-id="b1124-446">**Device properties**</span></span>

|<span data-ttu-id="b1124-447">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-447">Type</span></span>|<span data-ttu-id="b1124-448">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-448">Properties</span></span>|<span data-ttu-id="b1124-449">值</span><span class="sxs-lookup"><span data-stu-id="b1124-449">Values</span></span>|<span data-ttu-id="b1124-450">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-451">作業系統版本</span><span class="sxs-lookup"><span data-stu-id="b1124-451">Operating system version</span></span>|<span data-ttu-id="b1124-452">全部</span><span class="sxs-lookup"><span data-stu-id="b1124-452">All</span></span>|<span data-ttu-id="b1124-453">尚未設定</span><span class="sxs-lookup"><span data-stu-id="b1124-453">Not configured</span></span>||

<span data-ttu-id="b1124-454">針對所有要視為已部署的上述原則，必須將它們的目標設為使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b1124-454">For all the above policies to be considered deployed, they must be targeted at user groups.</span></span> <span data-ttu-id="b1124-455">您可以藉由建立原則 （儲存） 或更新版本所選取 （相同層級新增） 上的 [**原則**] 區段中的 [**管理部署**。</span><span class="sxs-lookup"><span data-stu-id="b1124-455">You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="b1124-456">**系統安全性**</span><span class="sxs-lookup"><span data-stu-id="b1124-456">**System security**</span></span>

|<span data-ttu-id="b1124-457">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-457">Type</span></span>|<span data-ttu-id="b1124-458">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-458">Properties</span></span>|<span data-ttu-id="b1124-459">值</span><span class="sxs-lookup"><span data-stu-id="b1124-459">Values</span></span>|<span data-ttu-id="b1124-460">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-461">密碼</span><span class="sxs-lookup"><span data-stu-id="b1124-461">Password</span></span>|<span data-ttu-id="b1124-462">需要密碼才可解除鎖定行動裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="b1124-463">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-463">Require</span></span>||
||<span data-ttu-id="b1124-464">簡單密碼</span><span class="sxs-lookup"><span data-stu-id="b1124-464">Simple passwords</span></span>|<span data-ttu-id="b1124-465">封鎖</span><span class="sxs-lookup"><span data-stu-id="b1124-465">Block</span></span>||
||<span data-ttu-id="b1124-466">密碼類型</span><span class="sxs-lookup"><span data-stu-id="b1124-466">Password type</span></span>|<span data-ttu-id="b1124-467">裝置預設值</span><span class="sxs-lookup"><span data-stu-id="b1124-467">Device default</span></span>||
||<span data-ttu-id="b1124-468">密碼最小長度</span><span class="sxs-lookup"><span data-stu-id="b1124-468">Minimum password length</span></span>|<span data-ttu-id="b1124-469">6</span><span class="sxs-lookup"><span data-stu-id="b1124-469">6</span></span>||
||<span data-ttu-id="b1124-470">最大之前都需要 password 的閒置分鐘</span><span class="sxs-lookup"><span data-stu-id="b1124-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="b1124-471">15 </span><span class="sxs-lookup"><span data-stu-id="b1124-471">15</span></span>|<span data-ttu-id="b1124-472">此設定為支援版 Android 4.0 及上方或 KNOX 4.0 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="b1124-472">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above.</span></span> <span data-ttu-id="b1124-473">適用於 iOS 裝置，它是適用於 iOS 8.0 及支援上方</span><span class="sxs-lookup"><span data-stu-id="b1124-473">For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="b1124-474">密碼到期 （天數）</span><span class="sxs-lookup"><span data-stu-id="b1124-474">Password expiration (days)</span></span>|<span data-ttu-id="b1124-475">41</span><span class="sxs-lookup"><span data-stu-id="b1124-475">41</span></span>||
||<span data-ttu-id="b1124-476">若要防止重複使用舊密碼數目</span><span class="sxs-lookup"><span data-stu-id="b1124-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="b1124-477">5</span><span class="sxs-lookup"><span data-stu-id="b1124-477">5</span></span>||
||<span data-ttu-id="b1124-478">需要密碼，當裝置會傳回從閒置狀態 （行動電話和 Holographic）</span><span class="sxs-lookup"><span data-stu-id="b1124-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="b1124-479">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-479">Require</span></span>|<span data-ttu-id="b1124-480">適用於 Windows 10 和更新版本</span><span class="sxs-lookup"><span data-stu-id="b1124-480">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="b1124-481">加密</span><span class="sxs-lookup"><span data-stu-id="b1124-481">Encryption</span></span>|<span data-ttu-id="b1124-482">在裝置上的資料存放區的加密</span><span class="sxs-lookup"><span data-stu-id="b1124-482">Encryption of data storage on device</span></span>|<span data-ttu-id="b1124-483">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-483">Require</span></span>||
|<span data-ttu-id="b1124-484">裝置安全性</span><span class="sxs-lookup"><span data-stu-id="b1124-484">Device Security</span></span>|<span data-ttu-id="b1124-485">防火牆</span><span class="sxs-lookup"><span data-stu-id="b1124-485">Firewall</span></span>|<span data-ttu-id="b1124-486">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-486">Require</span></span>||
||<span data-ttu-id="b1124-487">防毒</span><span class="sxs-lookup"><span data-stu-id="b1124-487">Antivirus</span></span>|<span data-ttu-id="b1124-488">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-488">Require</span></span>||
||<span data-ttu-id="b1124-489">反間諜軟體</span><span class="sxs-lookup"><span data-stu-id="b1124-489">Antispyware</span></span>|<span data-ttu-id="b1124-490">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-490">Require</span></span>|<span data-ttu-id="b1124-491">此設定需要註冊 Windows 資訊安全中心反間諜軟體解決方案</span><span class="sxs-lookup"><span data-stu-id="b1124-491">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="b1124-492">Defender</span><span class="sxs-lookup"><span data-stu-id="b1124-492">Defender</span></span>|<span data-ttu-id="b1124-493">Windows Defender 反惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="b1124-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="b1124-494">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-494">Require</span></span>||
||<span data-ttu-id="b1124-495">Windows Defender 反惡意程式碼最小版本</span><span class="sxs-lookup"><span data-stu-id="b1124-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="b1124-496">只有支援 Windows 10 桌面。</span><span class="sxs-lookup"><span data-stu-id="b1124-496">Only supported for Windows 10 desktop.</span></span> <span data-ttu-id="b1124-497">Microsoft 建議的版本不超過五背後從最新版本</span><span class="sxs-lookup"><span data-stu-id="b1124-497">Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="b1124-498">最新的 Windows Defender 反惡意程式碼簽章</span><span class="sxs-lookup"><span data-stu-id="b1124-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="b1124-499">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-499">Require</span></span>||
||<span data-ttu-id="b1124-500">即時防護</span><span class="sxs-lookup"><span data-stu-id="b1124-500">Real-time protection</span></span>|<span data-ttu-id="b1124-501">需要</span><span class="sxs-lookup"><span data-stu-id="b1124-501">Require</span></span>|<span data-ttu-id="b1124-502">僅有 Windows 10 桌面版支援</span><span class="sxs-lookup"><span data-stu-id="b1124-502">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="b1124-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="b1124-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="b1124-504">類型</span><span class="sxs-lookup"><span data-stu-id="b1124-504">Type</span></span>|<span data-ttu-id="b1124-505">屬性</span><span class="sxs-lookup"><span data-stu-id="b1124-505">Properties</span></span>|<span data-ttu-id="b1124-506">值</span><span class="sxs-lookup"><span data-stu-id="b1124-506">Values</span></span>|<span data-ttu-id="b1124-507">附註</span><span class="sxs-lookup"><span data-stu-id="b1124-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="b1124-508">Windows Defender 進階威脅防護規則</span><span class="sxs-lookup"><span data-stu-id="b1124-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="b1124-509">需要為或機器風險分數下裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-509">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="b1124-510">中</span><span class="sxs-lookup"><span data-stu-id="b1124-510">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="b1124-511">需要相容的電腦 （但不是相容的手機和平板電腦）</span><span class="sxs-lookup"><span data-stu-id="b1124-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="b1124-512">之前新增一項原則需要相容的電腦，請確定已註冊到 Intune 管理裝置。</span><span class="sxs-lookup"><span data-stu-id="b1124-512">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune.</span></span> <span data-ttu-id="b1124-513">建議使用多重要素驗證之前到 Intune 註冊裝置的裝置是在所預期的使用者所持有的保證。</span><span class="sxs-lookup"><span data-stu-id="b1124-513">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="b1124-514">需要相容的電腦：</span><span class="sxs-lookup"><span data-stu-id="b1124-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="b1124-515">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="b1124-515">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="b1124-516">您已成功登入之後，您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="b1124-516">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="b1124-517">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="b1124-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b1124-518">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="b1124-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b1124-519">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="b1124-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="b1124-520">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="b1124-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="b1124-521">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="b1124-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="b1124-522">選擇 [**選取應用程式**，從**雲端應用程式**清單中選取所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b1124-522">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="b1124-523">例如，選取 [Office 365 Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="b1124-523">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="b1124-524">選擇 [**選取**和**完成**]。</span><span class="sxs-lookup"><span data-stu-id="b1124-524">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="b1124-525">若需要相容的電腦，但不是相容的手機和平板電腦，請選擇 [**條件**和**裝置平台**]。</span><span class="sxs-lookup"><span data-stu-id="b1124-525">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**.</span></span> <span data-ttu-id="b1124-526">選擇 [**選取裝置平台**]，然後選取 [ **Windows**和**macOS**。</span><span class="sxs-lookup"><span data-stu-id="b1124-526">Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="b1124-527">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="b1124-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="b1124-528">選擇 [**授與存取權**，請選取 [**需要裝置標記為相容**。</span><span class="sxs-lookup"><span data-stu-id="b1124-528">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="b1124-529">對於多個控制項，請選取 [**需要所有選取的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="b1124-529">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="b1124-530">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="b1124-530">Choose **Create**.</span></span>

<span data-ttu-id="b1124-531">如果您的目標是要需要相容電腦*和*行動裝置，請勿選取 [平台。</span><span class="sxs-lookup"><span data-stu-id="b1124-531">If your objective is to require compliant PCs *and* mobile devices, do not select platforms.</span></span> <span data-ttu-id="b1124-532">這會強制執行所有裝置合規性。</span><span class="sxs-lookup"><span data-stu-id="b1124-532">This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="b1124-533">需要相容電腦*和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="b1124-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="b1124-534">需要所有裝置合規性：</span><span class="sxs-lookup"><span data-stu-id="b1124-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="b1124-535">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。</span><span class="sxs-lookup"><span data-stu-id="b1124-535">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="b1124-536">您已成功登入之後，您會看到 Azure 儀表板。</span><span class="sxs-lookup"><span data-stu-id="b1124-536">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="b1124-537">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="b1124-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="b1124-538">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="b1124-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="b1124-539">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="b1124-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="b1124-540">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="b1124-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="b1124-541">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="b1124-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="b1124-542">選擇 [**選取應用程式**，從**雲端應用程式**清單中選取所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b1124-542">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="b1124-543">例如，選取 [Office 365 Exchange Online]。</span><span class="sxs-lookup"><span data-stu-id="b1124-543">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="b1124-544">選擇 [**選取**和**完成**]。</span><span class="sxs-lookup"><span data-stu-id="b1124-544">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="b1124-545">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="b1124-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="b1124-546">選擇 [**授與存取權**，請選取 [**需要裝置標記為相容**。</span><span class="sxs-lookup"><span data-stu-id="b1124-546">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="b1124-547">對於多個控制項，請選取 [**需要所有選取的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="b1124-547">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="b1124-548">	選擇 *\*[建立]*\*。</span><span class="sxs-lookup"><span data-stu-id="b1124-548">Choose **Create**.</span></span>

<span data-ttu-id="b1124-549">建立此原則時，請勿選取 [平台。</span><span class="sxs-lookup"><span data-stu-id="b1124-549">When creating this policy, do not select platforms.</span></span> <span data-ttu-id="b1124-550">這會強制執行相容的裝置。</span><span class="sxs-lookup"><span data-stu-id="b1124-550">This enforces compliant devices.</span></span>


## <a name="next-steps"></a><span data-ttu-id="b1124-551">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b1124-551">Next steps</span></span>

[<span data-ttu-id="b1124-552">了解保護電子郵件的原則建議</span><span class="sxs-lookup"><span data-stu-id="b1124-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
