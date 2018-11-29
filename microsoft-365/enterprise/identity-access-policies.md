---
title: 一般身分識別與裝置存取原則-Microsoft 365 企業版 |Microsoft 文件
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
ms.openlocfilehash: 72a957222ed3bba449e1576873bfc87a614c075b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866754"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="45de7-103">一般身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="45de7-103">Common identity and device access policies</span></span>
<span data-ttu-id="45de7-104">本文說明建議的原則保護存取雲端服務的一般包括內部應用程式發佈與 Azure AD 應用程式 Proxy。</span><span class="sxs-lookup"><span data-stu-id="45de7-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="45de7-p101">本指南討論如何部署新佈建環境中的建議原則。 在個別實驗室環境中設定這些原則可讓您先了解和評估建議原則，再讓首度發行進入生產階段前和生產環境。 您新佈建的環境可能僅限雲端或混合式。</span><span class="sxs-lookup"><span data-stu-id="45de7-p101">This guidance discusses how to deploy the recommended policies in a newly provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your pre-production and production environments. Your newly provisioned environment may be cloud-only or Hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="45de7-108">原則設定</span><span class="sxs-lookup"><span data-stu-id="45de7-108">Policy set</span></span> 

<span data-ttu-id="45de7-p102">下圖說明建議的設定的原則。該顯示哪個層保護於一身的每個原則套用至和原則是否套用至 Pc、 手機與平板電腦或裝置這兩種類別。它也會指出所設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs, phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![設定身分識別與裝置的存取權的一般原則](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="45de7-113">本文的其餘部分說明如何設定這些原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="45de7-p103">之前將 Intune 註冊裝置的裝置在預定使用者所持有的保證建議您不要使用多重要素驗證。與您必須將 Intune 註冊裝置之前強制執行裝置規範遵守原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. And you must enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="45de7-p104">若要授與您若要完成這些工作的時間、 建議的基準原則實作的順序列出此表格中。不過，保護機密和高度規範 MFA 原則可實作任何時候。</span><span class="sxs-lookup"><span data-stu-id="45de7-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="45de7-118">保護層級</span><span class="sxs-lookup"><span data-stu-id="45de7-118">Protection level</span></span>|<span data-ttu-id="45de7-119">Policies</span><span class="sxs-lookup"><span data-stu-id="45de7-119">Policies</span></span>|<span data-ttu-id="45de7-120">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="45de7-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="45de7-121">**基準**</span><span class="sxs-lookup"><span data-stu-id="45de7-121">**Baseline**</span></span>|[<span data-ttu-id="45de7-122">登入風險為*medium*或*high*時需要 MFA</span><span class="sxs-lookup"><span data-stu-id="45de7-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="45de7-123">不支援經過驗證的封鎖用戶端</span><span class="sxs-lookup"><span data-stu-id="45de7-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="45de7-124">不使用經過驗證的用戶端可略過條件式存取規則，因此請務必封鎖這些。</span><span class="sxs-lookup"><span data-stu-id="45de7-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these.</span></span>|
|        |[<span data-ttu-id="45de7-125">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="45de7-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="45de7-126">強制使用者在登入其帳戶偵測到高風險活動時時變更其密碼。</span><span class="sxs-lookup"><span data-stu-id="45de7-126">Forces users to change their password when signing in if high risk activity is detected for their account.</span></span>|
|        |[<span data-ttu-id="45de7-127">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="45de7-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="45de7-128">每個平台 (iOS、 Android、 Windows) 的一個原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="45de7-129">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="45de7-130">強制執行電話與平板電腦的行動裝置應用程式保護</span><span class="sxs-lookup"><span data-stu-id="45de7-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="45de7-131">定義裝置規範遵守原則</span><span class="sxs-lookup"><span data-stu-id="45de7-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="45de7-132">針對每個平台的一個原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-132">One policy for each platform.</span></span>|
|        |[<span data-ttu-id="45de7-133">需要相容的 Pc</span><span class="sxs-lookup"><span data-stu-id="45de7-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="45de7-134">強制執行 Pc Intune 的管理</span><span class="sxs-lookup"><span data-stu-id="45de7-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="45de7-135">**敏感性**</span><span class="sxs-lookup"><span data-stu-id="45de7-135">**Sensitive**</span></span>|[<span data-ttu-id="45de7-136">登入風險為*低*、 *medium*或*high*時需要 MFA</span><span class="sxs-lookup"><span data-stu-id="45de7-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="45de7-137">需要相容的 Pc*和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="45de7-138">強制執行 Pc 與電話/平板電腦 Intune 的管理。</span><span class="sxs-lookup"><span data-stu-id="45de7-138">Enforces Intune management for PCs and phone/tablets.</span></span>|
|<span data-ttu-id="45de7-139">**高管制**</span><span class="sxs-lookup"><span data-stu-id="45de7-139">**Highly regulated**</span></span>|[<span data-ttu-id="45de7-140">*永遠*需要 MFA</span><span class="sxs-lookup"><span data-stu-id="45de7-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="45de7-141">將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="45de7-141">Assigning policies to users</span></span>
<span data-ttu-id="45de7-p105">設定原則之前, 識別 Azure AD 群組所使用的每一層的保護。通常比較基準保護套用至組織中的每一個人。比較基準和機密保護包含使用者必須套用的所有比較基準原則加上機密的原則。保護累計且最嚴格的原則會強制執行。</span><span class="sxs-lookup"><span data-stu-id="45de7-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="45de7-p106">建議的做法是建立的設定格式化的條件存取排除 Azure AD 群組。將這個群組新增至所有"排除"下您設定格式化的條件存取規則。這可讓您提供給使用者的存取時疑難排解存取問題的方法。這被建議為暫時方案。監視變更這個群組並確定排除群組已採用僅如預期。</span><span class="sxs-lookup"><span data-stu-id="45de7-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="45de7-151">下圖提供使用者工作分派及排除的範例。</span><span class="sxs-lookup"><span data-stu-id="45de7-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![範例使用者工作分派及排除 MFA 規則](../images/identity-access-policies-assignment.png)

<span data-ttu-id="45de7-p107">圖中 「 上方秘密 project X 小組 」 被指派 MFA*一律*需要的設定格式化的條件存取原則。套用至使用者的較高等級時則是保護的審慎。需要此專案小組成員將提供兩種形式的驗證每次登入，即使這些沒有檢視高度規範的內容。</span><span class="sxs-lookup"><span data-stu-id="45de7-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly regulated content.</span></span>  

 <span data-ttu-id="45de7-p108">所有這些建議的過程中建立的 Azure AD 群組必須建立為 Office 365 群組。這是特別重要的部署 Azure 資訊保護 (AIP) 時保護文件中的 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="45de7-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![建立 Office 365 群組的螢幕擷取畫面](../images/identity-device-AAD-groups.png)




## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="45de7-159">需要 MFA 根據登入風險</span><span class="sxs-lookup"><span data-stu-id="45de7-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="45de7-p109">要求 MFA、 之前先使用身分識別保護 MFA 註冊原則 MFA 註冊的使用者。使用者註冊後您可以強制 MFA 登入。[必要的工作](identity-access-prerequisites.md)包括 MFA 登錄的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="45de7-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="45de7-163">若要建立新的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="45de7-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="45de7-p110">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="45de7-166">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="45de7-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="45de7-167">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="45de7-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="45de7-168">選擇**新的原則**如下列螢幕擷取畫面所示：</span><span class="sxs-lookup"><span data-stu-id="45de7-168">Choose **New policy** as shown in the screenshot below:</span></span>

![基準 CA 原則](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="45de7-170">下表說明實作此原則的設定格式化的條件存取原則設定。</span><span class="sxs-lookup"><span data-stu-id="45de7-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="45de7-171">**指派**</span><span class="sxs-lookup"><span data-stu-id="45de7-171">**Assignments**</span></span>

|<span data-ttu-id="45de7-172">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-172">Type</span></span>|<span data-ttu-id="45de7-173">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-173">Properties</span></span>|<span data-ttu-id="45de7-174">值</span><span class="sxs-lookup"><span data-stu-id="45de7-174">Values</span></span>|<span data-ttu-id="45de7-175">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-176">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="45de7-176">Users and groups</span></span>|<span data-ttu-id="45de7-177">Include</span><span class="sxs-lookup"><span data-stu-id="45de7-177">Include</span></span>|<span data-ttu-id="45de7-178">選取使用者和群組 - 選取包含目標使用者的特定安全性群組</span><span class="sxs-lookup"><span data-stu-id="45de7-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="45de7-179">從包含試驗使用者的安全性群組開始。</span><span class="sxs-lookup"><span data-stu-id="45de7-179">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="45de7-180">排除</span><span class="sxs-lookup"><span data-stu-id="45de7-180">Exclude</span></span>|<span data-ttu-id="45de7-181">例外狀況安全性群組；服務帳戶 (應用程式身分識別)</span><span class="sxs-lookup"><span data-stu-id="45de7-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="45de7-182">視需要暫時修改成員資格</span><span class="sxs-lookup"><span data-stu-id="45de7-182">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="45de7-183">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-183">Cloud apps</span></span>|<span data-ttu-id="45de7-184">Include</span><span class="sxs-lookup"><span data-stu-id="45de7-184">Include</span></span>|<span data-ttu-id="45de7-p111">選取您想要套用到此規則的應用程式。例如，選取 [Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="45de7-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="45de7-187">條件</span><span class="sxs-lookup"><span data-stu-id="45de7-187">Conditions</span></span>|<span data-ttu-id="45de7-188">已設定</span><span class="sxs-lookup"><span data-stu-id="45de7-188">Configured</span></span>|<span data-ttu-id="45de7-189">是</span><span class="sxs-lookup"><span data-stu-id="45de7-189">Yes</span></span>|<span data-ttu-id="45de7-190">進行您環境和需求的特定設定</span><span class="sxs-lookup"><span data-stu-id="45de7-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="45de7-191">登入風險</span><span class="sxs-lookup"><span data-stu-id="45de7-191">Sign-in risk</span></span>|<span data-ttu-id="45de7-192">風險層級</span><span class="sxs-lookup"><span data-stu-id="45de7-192">Risk level</span></span>||<span data-ttu-id="45de7-193">請參閱下表中的指引</span><span class="sxs-lookup"><span data-stu-id="45de7-193">See the guidance in the following table</span></span>|

<span data-ttu-id="45de7-194">**登入風險**</span><span class="sxs-lookup"><span data-stu-id="45de7-194">**Sign-in risk**</span></span>

<span data-ttu-id="45de7-195">適用於根據您所採用的保護層級的設定。</span><span class="sxs-lookup"><span data-stu-id="45de7-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="45de7-196">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-196">Property</span></span>|<span data-ttu-id="45de7-197">保護層級</span><span class="sxs-lookup"><span data-stu-id="45de7-197">Level of protection</span></span>|<span data-ttu-id="45de7-198">值</span><span class="sxs-lookup"><span data-stu-id="45de7-198">Values</span></span>|<span data-ttu-id="45de7-199">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-200">風險層級</span><span class="sxs-lookup"><span data-stu-id="45de7-200">Risk level</span></span>|<span data-ttu-id="45de7-201">基準</span><span class="sxs-lookup"><span data-stu-id="45de7-201">Baseline</span></span>|<span data-ttu-id="45de7-202">高、中</span><span class="sxs-lookup"><span data-stu-id="45de7-202">High, medium</span></span>|<span data-ttu-id="45de7-203">檢查兩者</span><span class="sxs-lookup"><span data-stu-id="45de7-203">Check both</span></span>|
| |<span data-ttu-id="45de7-204">敏感性</span><span class="sxs-lookup"><span data-stu-id="45de7-204">Sensitive</span></span>|<span data-ttu-id="45de7-205">高、 中、 低</span><span class="sxs-lookup"><span data-stu-id="45de7-205">High, medium, low</span></span>|<span data-ttu-id="45de7-206">三個全選</span><span class="sxs-lookup"><span data-stu-id="45de7-206">Check all three</span></span>|
| |<span data-ttu-id="45de7-207">高管制</span><span class="sxs-lookup"><span data-stu-id="45de7-207">Highly regulated</span></span>| |<span data-ttu-id="45de7-208">保留所有選項未核取一律強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="45de7-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="45de7-209">**存取控制**</span><span class="sxs-lookup"><span data-stu-id="45de7-209">**Access controls**</span></span>

|<span data-ttu-id="45de7-210">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-210">Type</span></span>|<span data-ttu-id="45de7-211">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-211">Properties</span></span>|<span data-ttu-id="45de7-212">值</span><span class="sxs-lookup"><span data-stu-id="45de7-212">Values</span></span>|<span data-ttu-id="45de7-213">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-214">授與</span><span class="sxs-lookup"><span data-stu-id="45de7-214">Grant</span></span>|<span data-ttu-id="45de7-215">授予存取</span><span class="sxs-lookup"><span data-stu-id="45de7-215">Grant access</span></span>|<span data-ttu-id="45de7-216">True</span><span class="sxs-lookup"><span data-stu-id="45de7-216">True</span></span>|<span data-ttu-id="45de7-217">已選取</span><span class="sxs-lookup"><span data-stu-id="45de7-217">Selected</span></span>|
||<span data-ttu-id="45de7-218">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="45de7-218">Require MFA</span></span>|<span data-ttu-id="45de7-219">True</span><span class="sxs-lookup"><span data-stu-id="45de7-219">True</span></span>|<span data-ttu-id="45de7-220">Check</span><span class="sxs-lookup"><span data-stu-id="45de7-220">Check</span></span>|
||<span data-ttu-id="45de7-221">需要要標示為相容的裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="45de7-222">False</span><span class="sxs-lookup"><span data-stu-id="45de7-222">False</span></span>||
||<span data-ttu-id="45de7-223">需要混合 Azure AD 加入的裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-223">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="45de7-224">False</span><span class="sxs-lookup"><span data-stu-id="45de7-224">False</span></span>||
||<span data-ttu-id="45de7-225">需要核准的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-225">Require approved client app</span></span>|<span data-ttu-id="45de7-226">False</span><span class="sxs-lookup"><span data-stu-id="45de7-226">False</span></span>||
||<span data-ttu-id="45de7-227">需要所有選取的控制項</span><span class="sxs-lookup"><span data-stu-id="45de7-227">Require all the selected controls</span></span>|<span data-ttu-id="45de7-228">True</span><span class="sxs-lookup"><span data-stu-id="45de7-228">True</span></span>|<span data-ttu-id="45de7-229">已選取</span><span class="sxs-lookup"><span data-stu-id="45de7-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="45de7-p112">請務必按一下**上**的 [啟用此原則。也請考慮使用[怎麼辦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則</span><span class="sxs-lookup"><span data-stu-id="45de7-p112">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="45de7-232">不支援經過驗證的封鎖用戶端</span><span class="sxs-lookup"><span data-stu-id="45de7-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="45de7-p113">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="45de7-235">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="45de7-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="45de7-236">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="45de7-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="45de7-237">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="45de7-237">Choose **New policy**.</span></span>

<span data-ttu-id="45de7-238">下表說明實作此原則的設定格式化的條件存取原則設定。</span><span class="sxs-lookup"><span data-stu-id="45de7-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="45de7-239">**指派**</span><span class="sxs-lookup"><span data-stu-id="45de7-239">**Assignments**</span></span>

|<span data-ttu-id="45de7-240">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-240">Type</span></span>|<span data-ttu-id="45de7-241">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-241">Properties</span></span>|<span data-ttu-id="45de7-242">值</span><span class="sxs-lookup"><span data-stu-id="45de7-242">Values</span></span>|<span data-ttu-id="45de7-243">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-244">使用者和群組</span><span class="sxs-lookup"><span data-stu-id="45de7-244">Users and groups</span></span>|<span data-ttu-id="45de7-245">Include</span><span class="sxs-lookup"><span data-stu-id="45de7-245">Include</span></span>|<span data-ttu-id="45de7-246">選取使用者和群組 - 選取包含目標使用者的特定安全性群組</span><span class="sxs-lookup"><span data-stu-id="45de7-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="45de7-247">從包含試驗使用者的安全性群組開始。</span><span class="sxs-lookup"><span data-stu-id="45de7-247">Start with security group including pilot users.</span></span>|
||<span data-ttu-id="45de7-248">排除</span><span class="sxs-lookup"><span data-stu-id="45de7-248">Exclude</span></span>|<span data-ttu-id="45de7-249">例外狀況安全性群組；服務帳戶 (應用程式身分識別)</span><span class="sxs-lookup"><span data-stu-id="45de7-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="45de7-250">視需要暫時修改成員資格</span><span class="sxs-lookup"><span data-stu-id="45de7-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="45de7-251">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-251">Cloud apps</span></span>|<span data-ttu-id="45de7-252">Include</span><span class="sxs-lookup"><span data-stu-id="45de7-252">Include</span></span>|<span data-ttu-id="45de7-p114">選取您想要套用到此規則的應用程式。例如，選取 [Office 365 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="45de7-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="45de7-255">條件</span><span class="sxs-lookup"><span data-stu-id="45de7-255">Conditions</span></span>|<span data-ttu-id="45de7-256">已設定</span><span class="sxs-lookup"><span data-stu-id="45de7-256">Configured</span></span>|<span data-ttu-id="45de7-257">是</span><span class="sxs-lookup"><span data-stu-id="45de7-257">Yes</span></span>|<span data-ttu-id="45de7-258">設定用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-258">Configure Client apps</span></span>|
|<span data-ttu-id="45de7-259">用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-259">Client apps</span></span>|<span data-ttu-id="45de7-260">已設定</span><span class="sxs-lookup"><span data-stu-id="45de7-260">Configured</span></span>|<span data-ttu-id="45de7-261">是</span><span class="sxs-lookup"><span data-stu-id="45de7-261">Yes</span></span>|<span data-ttu-id="45de7-262">行動應用程式和桌面用戶端 (選取 [兩者) 其他用戶端</span><span class="sxs-lookup"><span data-stu-id="45de7-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="45de7-263">**存取控制**</span><span class="sxs-lookup"><span data-stu-id="45de7-263">**Access controls**</span></span>

|<span data-ttu-id="45de7-264">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-264">Type</span></span>|<span data-ttu-id="45de7-265">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-265">Properties</span></span>|<span data-ttu-id="45de7-266">值</span><span class="sxs-lookup"><span data-stu-id="45de7-266">Values</span></span>|<span data-ttu-id="45de7-267">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-268">授與</span><span class="sxs-lookup"><span data-stu-id="45de7-268">Grant</span></span>|<span data-ttu-id="45de7-269">封鎖存取</span><span class="sxs-lookup"><span data-stu-id="45de7-269">Block access</span></span>|<span data-ttu-id="45de7-270">True</span><span class="sxs-lookup"><span data-stu-id="45de7-270">True</span></span>|<span data-ttu-id="45de7-271">已選取</span><span class="sxs-lookup"><span data-stu-id="45de7-271">Selected</span></span>|
||<span data-ttu-id="45de7-272">需要 MFA</span><span class="sxs-lookup"><span data-stu-id="45de7-272">Require MFA</span></span>|<span data-ttu-id="45de7-273">False</span><span class="sxs-lookup"><span data-stu-id="45de7-273">False</span></span>||
||<span data-ttu-id="45de7-274">需要要標示為相容的裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="45de7-275">False</span><span class="sxs-lookup"><span data-stu-id="45de7-275">False</span></span>||
||<span data-ttu-id="45de7-276">需要混合 Azure AD 加入的裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-276">Require Hybrid Azure AD joined device</span></span>|<span data-ttu-id="45de7-277">False</span><span class="sxs-lookup"><span data-stu-id="45de7-277">False</span></span>||
||<span data-ttu-id="45de7-278">需要核准的用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-278">Require approved client app</span></span>|<span data-ttu-id="45de7-279">False</span><span class="sxs-lookup"><span data-stu-id="45de7-279">False</span></span>||
||<span data-ttu-id="45de7-280">需要所有選取的控制項</span><span class="sxs-lookup"><span data-stu-id="45de7-280">Require all the selected controls</span></span>|<span data-ttu-id="45de7-281">True</span><span class="sxs-lookup"><span data-stu-id="45de7-281">True</span></span>|<span data-ttu-id="45de7-282">已選取</span><span class="sxs-lookup"><span data-stu-id="45de7-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="45de7-p115">請務必按一下**上**的 [啟用此原則。也請考慮使用[怎麼辦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則</span><span class="sxs-lookup"><span data-stu-id="45de7-p115">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="45de7-285">高風險使用者必須變更密碼</span><span class="sxs-lookup"><span data-stu-id="45de7-285">High risk users must change password</span></span>
<span data-ttu-id="45de7-286">若要確保強制執行所有高風險使用者遭盜用的帳戶在登入時變更密碼，您必須套用下列原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-286">To ensure that all high-risk users compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="45de7-287">登入[Microsoft Azure 入口網站 (http://portal.azure.com)](http://portal.azure.com/)使用您的系統管理員認證，然後瀏覽至**Azure AD 身分識別保護 > 使用者風險原則**。</span><span class="sxs-lookup"><span data-stu-id="45de7-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="45de7-288">**指派**</span><span class="sxs-lookup"><span data-stu-id="45de7-288">**Assignments**</span></span>

|<span data-ttu-id="45de7-289">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-289">Type</span></span>|<span data-ttu-id="45de7-290">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-290">Properties</span></span>|<span data-ttu-id="45de7-291">值</span><span class="sxs-lookup"><span data-stu-id="45de7-291">Values</span></span>|<span data-ttu-id="45de7-292">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-293">使用者</span><span class="sxs-lookup"><span data-stu-id="45de7-293">Users</span></span>|<span data-ttu-id="45de7-294">Include</span><span class="sxs-lookup"><span data-stu-id="45de7-294">Include</span></span>|<span data-ttu-id="45de7-295">所有使用者</span><span class="sxs-lookup"><span data-stu-id="45de7-295">All users</span></span>|<span data-ttu-id="45de7-296">已選取</span><span class="sxs-lookup"><span data-stu-id="45de7-296">Selected</span></span>|
||<span data-ttu-id="45de7-297">排除</span><span class="sxs-lookup"><span data-stu-id="45de7-297">Exclude</span></span>|<span data-ttu-id="45de7-298">無</span><span class="sxs-lookup"><span data-stu-id="45de7-298">None</span></span>||
|<span data-ttu-id="45de7-299">條件</span><span class="sxs-lookup"><span data-stu-id="45de7-299">Conditions</span></span>|<span data-ttu-id="45de7-300">使用者風險</span><span class="sxs-lookup"><span data-stu-id="45de7-300">User risk</span></span>|<span data-ttu-id="45de7-301">高</span><span class="sxs-lookup"><span data-stu-id="45de7-301">High</span></span>|<span data-ttu-id="45de7-302">已選取</span><span class="sxs-lookup"><span data-stu-id="45de7-302">Selected</span></span>|

<span data-ttu-id="45de7-303">**控制項**</span><span class="sxs-lookup"><span data-stu-id="45de7-303">**Controls**</span></span>

| <span data-ttu-id="45de7-304">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-304">Type</span></span> | <span data-ttu-id="45de7-305">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-305">Properties</span></span> | <span data-ttu-id="45de7-306">值</span><span class="sxs-lookup"><span data-stu-id="45de7-306">Values</span></span>                  | <span data-ttu-id="45de7-307">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="45de7-308">存取</span><span class="sxs-lookup"><span data-stu-id="45de7-308">Access</span></span>     | <span data-ttu-id="45de7-309">允許存取</span><span class="sxs-lookup"><span data-stu-id="45de7-309">Allow access</span></span>            | <span data-ttu-id="45de7-310">True</span><span class="sxs-lookup"><span data-stu-id="45de7-310">True</span></span>  |
|      | <span data-ttu-id="45de7-311">存取</span><span class="sxs-lookup"><span data-stu-id="45de7-311">Access</span></span>     | <span data-ttu-id="45de7-312">需要密碼變更</span><span class="sxs-lookup"><span data-stu-id="45de7-312">Require password change</span></span> | <span data-ttu-id="45de7-313">True</span><span class="sxs-lookup"><span data-stu-id="45de7-313">True</span></span>  |

<span data-ttu-id="45de7-314">**檢閱：** 不適用</span><span class="sxs-lookup"><span data-stu-id="45de7-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="45de7-p116">請務必按一下**上**的 [啟用此原則。也請考慮使用[怎麼辦](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)工具來測試原則</span><span class="sxs-lookup"><span data-stu-id="45de7-p116">Be sure to enable this policy, by clicking **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="45de7-317">定義應用程式保護原則</span><span class="sxs-lookup"><span data-stu-id="45de7-317">Define app protection policies</span></span>
<span data-ttu-id="45de7-p117">應用程式保護原則定義允許哪些應用程式和其可採取的動作與您組織的資料。保護原則與 Azure 入口網站內建立 Intune 應用程式。</span><span class="sxs-lookup"><span data-stu-id="45de7-p117">App protection policies define which apps are allowed and the actions they can take with your organization data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="45de7-320">建立每個平台的原則：</span><span class="sxs-lookup"><span data-stu-id="45de7-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="45de7-321">iOS</span><span class="sxs-lookup"><span data-stu-id="45de7-321">iOS</span></span>
- <span data-ttu-id="45de7-322">Android</span><span class="sxs-lookup"><span data-stu-id="45de7-322">Android</span></span>
- <span data-ttu-id="45de7-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="45de7-323">Windows 10</span></span>

<span data-ttu-id="45de7-p118">若要建立新的應用程式保護原則，Microsoft Azure 入口網站與 administer 認證，登入及瀏覽至 [**行動應用程式 > 應用程式保護原則**。按一下 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="45de7-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Click **Add a policy**.</span></span>

<span data-ttu-id="45de7-p119">有稍微之間的差異的應用程式保護 iOS 及 android （英文） 之間的原則選項。下列原則是特別為 android （英文）。使用此做為指南的其他原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="45de7-329">應用程式的建議的清單會包含下列：</span><span class="sxs-lookup"><span data-stu-id="45de7-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="45de7-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="45de7-330">PowerPoint</span></span>
- <span data-ttu-id="45de7-331">Excel</span><span class="sxs-lookup"><span data-stu-id="45de7-331">Excel</span></span>
- <span data-ttu-id="45de7-332">Word</span><span class="sxs-lookup"><span data-stu-id="45de7-332">Word</span></span>
- <span data-ttu-id="45de7-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45de7-333">Microsoft Teams</span></span>
- <span data-ttu-id="45de7-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="45de7-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="45de7-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="45de7-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="45de7-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="45de7-336">OneDrive</span></span>
- <span data-ttu-id="45de7-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="45de7-337">OneNote</span></span>
- <span data-ttu-id="45de7-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="45de7-338">Outlook</span></span>

<span data-ttu-id="45de7-339">下表說明建議的設定：</span><span class="sxs-lookup"><span data-stu-id="45de7-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="45de7-340">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-340">Type</span></span>|<span data-ttu-id="45de7-341">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-341">Properties</span></span>|<span data-ttu-id="45de7-342">值</span><span class="sxs-lookup"><span data-stu-id="45de7-342">Values</span></span>|<span data-ttu-id="45de7-343">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-344">資料重新配置</span><span class="sxs-lookup"><span data-stu-id="45de7-344">Data relocation</span></span>|<span data-ttu-id="45de7-345">禁止 Android 備份</span><span class="sxs-lookup"><span data-stu-id="45de7-345">Prevent Android backup</span></span>|<span data-ttu-id="45de7-346">是</span><span class="sxs-lookup"><span data-stu-id="45de7-346">Yes</span></span>|<span data-ttu-id="45de7-347">在 iOS 上，這會特別呼叫 iTunes 和 iCloud</span><span class="sxs-lookup"><span data-stu-id="45de7-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="45de7-348">允許應用程式將資料傳送到其他應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="45de7-349">受原則管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-349">Policy managed apps</span></span>||
||<span data-ttu-id="45de7-350">[允許應用程式接收其他應用程式的資料]</span><span class="sxs-lookup"><span data-stu-id="45de7-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="45de7-351">受原則管理的應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-351">Policy managed apps</span></span>||
||<span data-ttu-id="45de7-352">禁止執行 [另存新檔]</span><span class="sxs-lookup"><span data-stu-id="45de7-352">Prevent "Save As"</span></span>|<span data-ttu-id="45de7-353">是</span><span class="sxs-lookup"><span data-stu-id="45de7-353">Yes</span></span>||
||<span data-ttu-id="45de7-354">選取可儲存公司資料的儲存體服務</span><span class="sxs-lookup"><span data-stu-id="45de7-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="45de7-355">OneDrive for Business，SharePoint</span><span class="sxs-lookup"><span data-stu-id="45de7-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="45de7-356">[限制利用其他應用程式剪下、複製及貼上]</span><span class="sxs-lookup"><span data-stu-id="45de7-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="45de7-357">使用中的貼上的受管理的原則應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="45de7-358">限制 Web 內容以顯示於受管理的瀏覽器中</span><span class="sxs-lookup"><span data-stu-id="45de7-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="45de7-359">否</span><span class="sxs-lookup"><span data-stu-id="45de7-359">No</span></span>||
||<span data-ttu-id="45de7-360">加密應用程式資料</span><span class="sxs-lookup"><span data-stu-id="45de7-360">Encrypt app data</span></span>|<span data-ttu-id="45de7-361">是</span><span class="sxs-lookup"><span data-stu-id="45de7-361">Yes</span></span>|<span data-ttu-id="45de7-362">在 iOS 上，選取選項：當裝置鎖定時</span><span class="sxs-lookup"><span data-stu-id="45de7-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="45de7-363">啟用裝置時停用應用程式的加密</span><span class="sxs-lookup"><span data-stu-id="45de7-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="45de7-364">是</span><span class="sxs-lookup"><span data-stu-id="45de7-364">Yes</span></span>|<span data-ttu-id="45de7-365">停用此設定可避免雙重加密</span><span class="sxs-lookup"><span data-stu-id="45de7-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="45de7-366">停用聯絡人同步</span><span class="sxs-lookup"><span data-stu-id="45de7-366">Disable contacts sync</span></span>|<span data-ttu-id="45de7-367">否</span><span class="sxs-lookup"><span data-stu-id="45de7-367">No</span></span>||
||<span data-ttu-id="45de7-368">停用列印</span><span class="sxs-lookup"><span data-stu-id="45de7-368">Disable printing</span></span>|<span data-ttu-id="45de7-369">否</span><span class="sxs-lookup"><span data-stu-id="45de7-369">No</span></span>||
|<span data-ttu-id="45de7-370">存取</span><span class="sxs-lookup"><span data-stu-id="45de7-370">Access</span></span>|<span data-ttu-id="45de7-371">需要 PIN 碼才可存取</span><span class="sxs-lookup"><span data-stu-id="45de7-371">Require PIN for access</span></span>|<span data-ttu-id="45de7-372">是</span><span class="sxs-lookup"><span data-stu-id="45de7-372">Yes</span></span>||
||<span data-ttu-id="45de7-373">選取類型</span><span class="sxs-lookup"><span data-stu-id="45de7-373">Select Type</span></span>|<span data-ttu-id="45de7-374">數字</span><span class="sxs-lookup"><span data-stu-id="45de7-374">Numeric</span></span>||
||<span data-ttu-id="45de7-375">允許簡單的 PIN</span><span class="sxs-lookup"><span data-stu-id="45de7-375">Allow simple PIN</span></span>|<span data-ttu-id="45de7-376">否</span><span class="sxs-lookup"><span data-stu-id="45de7-376">No</span></span>||
||<span data-ttu-id="45de7-377">PIN 長度</span><span class="sxs-lookup"><span data-stu-id="45de7-377">PIN length</span></span>|<span data-ttu-id="45de7-378">6</span><span class="sxs-lookup"><span data-stu-id="45de7-378">6</span></span>||
||<span data-ttu-id="45de7-379">允許指紋而非 PIN</span><span class="sxs-lookup"><span data-stu-id="45de7-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="45de7-380">是</span><span class="sxs-lookup"><span data-stu-id="45de7-380">Yes</span></span>||
||<span data-ttu-id="45de7-381">受管理的裝置 PIN 時停用應用程式 PIN</span><span class="sxs-lookup"><span data-stu-id="45de7-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="45de7-382">是</span><span class="sxs-lookup"><span data-stu-id="45de7-382">Yes</span></span>||
||<span data-ttu-id="45de7-383">需要存取公司認證</span><span class="sxs-lookup"><span data-stu-id="45de7-383">Require corporate credentials for access</span></span>|<span data-ttu-id="45de7-384">否</span><span class="sxs-lookup"><span data-stu-id="45de7-384">No</span></span>||
||<span data-ttu-id="45de7-385">重新檢查存取需求前等候時間 (分鐘)</span><span class="sxs-lookup"><span data-stu-id="45de7-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="45de7-386">30</span><span class="sxs-lookup"><span data-stu-id="45de7-386">30</span></span>||
||<span data-ttu-id="45de7-387">封鎖螢幕擷取及 Android 助手</span><span class="sxs-lookup"><span data-stu-id="45de7-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="45de7-388">否</span><span class="sxs-lookup"><span data-stu-id="45de7-388">No</span></span>|<span data-ttu-id="45de7-389">在 iOS 上，這不是可用的選項</span><span class="sxs-lookup"><span data-stu-id="45de7-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="45de7-390">登入安全性需求</span><span class="sxs-lookup"><span data-stu-id="45de7-390">Sign-in security requirements</span></span>|<span data-ttu-id="45de7-391">最大 PIN 嘗試次數</span><span class="sxs-lookup"><span data-stu-id="45de7-391">Max PIN attempts</span></span>|<span data-ttu-id="45de7-392">5</span><span class="sxs-lookup"><span data-stu-id="45de7-392">5</span></span>|<span data-ttu-id="45de7-393">重設 Pin</span><span class="sxs-lookup"><span data-stu-id="45de7-393">Reset Pin</span></span>|
||<span data-ttu-id="45de7-394">離線寬限期</span><span class="sxs-lookup"><span data-stu-id="45de7-394">Offline grace period</span></span>|<span data-ttu-id="45de7-395">720</span><span class="sxs-lookup"><span data-stu-id="45de7-395">720</span></span>|<span data-ttu-id="45de7-396">封鎖存取</span><span class="sxs-lookup"><span data-stu-id="45de7-396">Block access</span></span>|
||<span data-ttu-id="45de7-397">離線間隔幾天後抹除 App 資料</span><span class="sxs-lookup"><span data-stu-id="45de7-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="45de7-398">90</span><span class="sxs-lookup"><span data-stu-id="45de7-398">90</span></span>|<span data-ttu-id="45de7-399">清除資料</span><span class="sxs-lookup"><span data-stu-id="45de7-399">Wipe data</span></span>|
||<span data-ttu-id="45de7-400">根目錄 Jailbroken/裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="45de7-401">清除資料</span><span class="sxs-lookup"><span data-stu-id="45de7-401">Wipe data</span></span>|

<span data-ttu-id="45de7-p120">完成時，請記得按一下 [建立]。 重複上述步驟，並將選取的平台 (下拉式清單) 取代為 iOS。 這會建立兩個應用程式原則，因此在您建立原則之後，請將群組指派給原則，並進行部署。</span><span class="sxs-lookup"><span data-stu-id="45de7-p120">When complete, remember to click "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="45de7-405">若要編輯原則並將這些原則指派給使用者，請參閱 ＜[如何建立和指派應用程式保護原則](https://docs.microsoft.com/intune/app-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="45de7-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="45de7-406">需要核准的應用程式</span><span class="sxs-lookup"><span data-stu-id="45de7-406">Require approved apps</span></span>
<span data-ttu-id="45de7-407">若要要求核准的應用程式：</span><span class="sxs-lookup"><span data-stu-id="45de7-407">To require approved apps:</span></span>

1. <span data-ttu-id="45de7-p121">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="45de7-410">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="45de7-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="45de7-411">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="45de7-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="45de7-412">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="45de7-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="45de7-413">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="45de7-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="45de7-414">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="45de7-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="45de7-p122">選擇 [**選取應用程式**、 從**雲端應用程式**清單中選取所需的應用程式。例如，選取 [Office 365 Exchange Online。按一下 [**選取 [** **完成**]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="45de7-418">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="45de7-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="45de7-p123">選擇 [**授與存取權**，請選取 [**需要核准用戶端應用程式**。 多個控制項，選取 [**需要在選定的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="45de7-p123">Choose **Grant access**, select **Require approved client app**.  For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="45de7-421">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-421">Click **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="45de7-422">定義裝置規範遵守原則</span><span class="sxs-lookup"><span data-stu-id="45de7-422">Define device compliance policies</span></span>

<span data-ttu-id="45de7-p124">裝置規範遵守原則定義的裝置必須遵守才能加以標示為相容的需求。建立 Intune 裝置 Azure 入口網站內的規範原則。</span><span class="sxs-lookup"><span data-stu-id="45de7-p124">Device compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="45de7-425">建立每個平台的原則：</span><span class="sxs-lookup"><span data-stu-id="45de7-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="45de7-426">Android</span><span class="sxs-lookup"><span data-stu-id="45de7-426">Android</span></span>
- <span data-ttu-id="45de7-427">Android 企業</span><span class="sxs-lookup"><span data-stu-id="45de7-427">Android enterprise</span></span>
- <span data-ttu-id="45de7-428">iOS</span><span class="sxs-lookup"><span data-stu-id="45de7-428">iOS</span></span>
- <span data-ttu-id="45de7-429">macOS</span><span class="sxs-lookup"><span data-stu-id="45de7-429">macOS</span></span>
- <span data-ttu-id="45de7-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="45de7-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="45de7-431">Windows 8.1 及更新版本</span><span class="sxs-lookup"><span data-stu-id="45de7-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="45de7-432">Windows 10 及更新版本</span><span class="sxs-lookup"><span data-stu-id="45de7-432">Windows 10 and later</span></span>

<span data-ttu-id="45de7-p125">若要建立裝置規範遵守原則，Microsoft Azure 入口網站與 administer 認證，登入及瀏覽至 [ **Intune > 裝置規範**。按一下 [**建立原則**。</span><span class="sxs-lookup"><span data-stu-id="45de7-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Click **Create policy**.</span></span>

<span data-ttu-id="45de7-435">Windows 10 會建議使用下列設定值。</span><span class="sxs-lookup"><span data-stu-id="45de7-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="45de7-436">**裝置狀況： Windows 狀況審查服務評估規則**</span><span class="sxs-lookup"><span data-stu-id="45de7-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="45de7-437">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-437">Properties</span></span>|<span data-ttu-id="45de7-438">值</span><span class="sxs-lookup"><span data-stu-id="45de7-438">Values</span></span>|<span data-ttu-id="45de7-439">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="45de7-440">需要 BitLocker</span><span class="sxs-lookup"><span data-stu-id="45de7-440">Require BitLocker</span></span>|<span data-ttu-id="45de7-441">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-441">Require</span></span>||
|<span data-ttu-id="45de7-442">需要在裝置上啟用安全開機</span><span class="sxs-lookup"><span data-stu-id="45de7-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="45de7-443">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-443">Require</span></span>||
|<span data-ttu-id="45de7-444">需要的程式碼完整性</span><span class="sxs-lookup"><span data-stu-id="45de7-444">Require code integrity</span></span>|<span data-ttu-id="45de7-445">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-445">Require</span></span>||


<span data-ttu-id="45de7-446">**裝置內容**</span><span class="sxs-lookup"><span data-stu-id="45de7-446">**Device properties**</span></span>

|<span data-ttu-id="45de7-447">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-447">Type</span></span>|<span data-ttu-id="45de7-448">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-448">Properties</span></span>|<span data-ttu-id="45de7-449">值</span><span class="sxs-lookup"><span data-stu-id="45de7-449">Values</span></span>|<span data-ttu-id="45de7-450">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-451">作業系統版本</span><span class="sxs-lookup"><span data-stu-id="45de7-451">Operating system version</span></span>|<span data-ttu-id="45de7-452">全部</span><span class="sxs-lookup"><span data-stu-id="45de7-452">All</span></span>|<span data-ttu-id="45de7-453">尚未設定</span><span class="sxs-lookup"><span data-stu-id="45de7-453">Not configured</span></span>||

<span data-ttu-id="45de7-p126">針對所有要視為已部署的上述原則，必須將它們的目標設為使用者群組。 做法是建立此原則 (在儲存時)，或稍後選取 [原則] 區段中的 [管理部署] (層級與 [新增] 相同)。</span><span class="sxs-lookup"><span data-stu-id="45de7-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting Manage Deployment in the Policy section (same level as Add).</span></span>

<span data-ttu-id="45de7-456">**系統安全性**</span><span class="sxs-lookup"><span data-stu-id="45de7-456">**System security**</span></span>

|<span data-ttu-id="45de7-457">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-457">Type</span></span>|<span data-ttu-id="45de7-458">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-458">Properties</span></span>|<span data-ttu-id="45de7-459">值</span><span class="sxs-lookup"><span data-stu-id="45de7-459">Values</span></span>|<span data-ttu-id="45de7-460">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-461">Password</span><span class="sxs-lookup"><span data-stu-id="45de7-461">Password</span></span>|<span data-ttu-id="45de7-462">需要密碼來解除鎖定行動裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="45de7-463">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-463">Require</span></span>||
||<span data-ttu-id="45de7-464">簡單密碼</span><span class="sxs-lookup"><span data-stu-id="45de7-464">Simple passwords</span></span>|<span data-ttu-id="45de7-465">封鎖</span><span class="sxs-lookup"><span data-stu-id="45de7-465">Block</span></span>||
||<span data-ttu-id="45de7-466">密碼類型</span><span class="sxs-lookup"><span data-stu-id="45de7-466">Password type</span></span>|<span data-ttu-id="45de7-467">裝置預設值</span><span class="sxs-lookup"><span data-stu-id="45de7-467">Device default</span></span>||
||<span data-ttu-id="45de7-468">密碼最小長度</span><span class="sxs-lookup"><span data-stu-id="45de7-468">Minimum password length</span></span>|<span data-ttu-id="45de7-469">6</span><span class="sxs-lookup"><span data-stu-id="45de7-469">6</span></span>||
||<span data-ttu-id="45de7-470">最大分鐘的閒置時間前都需要 password</span><span class="sxs-lookup"><span data-stu-id="45de7-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="45de7-471">15 </span><span class="sxs-lookup"><span data-stu-id="45de7-471">15</span></span>|<span data-ttu-id="45de7-p127">此設定為支援 Android 版本 4.0 及上方或 KNOX 4.0 及以上。IOS 裝置已支援 iOS 8.0 及上方。</span><span class="sxs-lookup"><span data-stu-id="45de7-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above.</span></span>|
||<span data-ttu-id="45de7-474">密碼到期 (天數)</span><span class="sxs-lookup"><span data-stu-id="45de7-474">Password expiration (days)</span></span>|<span data-ttu-id="45de7-475">41</span><span class="sxs-lookup"><span data-stu-id="45de7-475">41</span></span>||
||<span data-ttu-id="45de7-476">若要防止重複使用舊密碼數目</span><span class="sxs-lookup"><span data-stu-id="45de7-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="45de7-477">5</span><span class="sxs-lookup"><span data-stu-id="45de7-477">5</span></span>||
||<span data-ttu-id="45de7-478">裝置會傳回從閒置狀態 （行動電話和 Holographic） 時需要密碼</span><span class="sxs-lookup"><span data-stu-id="45de7-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="45de7-479">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-479">Require</span></span>|<span data-ttu-id="45de7-480">供 Windows 10 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="45de7-480">Available for Windows 10 and later.</span></span>|
|<span data-ttu-id="45de7-481">加密</span><span class="sxs-lookup"><span data-stu-id="45de7-481">Encryption</span></span>|<span data-ttu-id="45de7-482">在裝置上的資料存放區的加密</span><span class="sxs-lookup"><span data-stu-id="45de7-482">Encryption of data storage on device</span></span>|<span data-ttu-id="45de7-483">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-483">Require</span></span>||
|<span data-ttu-id="45de7-484">裝置安全性</span><span class="sxs-lookup"><span data-stu-id="45de7-484">Device Security</span></span>|<span data-ttu-id="45de7-485">防火牆</span><span class="sxs-lookup"><span data-stu-id="45de7-485">Firewall</span></span>|<span data-ttu-id="45de7-486">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-486">Require</span></span>||
||<span data-ttu-id="45de7-487">防毒</span><span class="sxs-lookup"><span data-stu-id="45de7-487">Antivirus</span></span>|<span data-ttu-id="45de7-488">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-488">Require</span></span>||
||<span data-ttu-id="45de7-489">反間諜軟體</span><span class="sxs-lookup"><span data-stu-id="45de7-489">Antispyware</span></span>|<span data-ttu-id="45de7-490">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-490">Require</span></span>|<span data-ttu-id="45de7-491">此設定需要登錄於 Windows 安全性中心反間諜軟體解決方案。</span><span class="sxs-lookup"><span data-stu-id="45de7-491">This setting requires an Anti-Spyware solution registered with Windows Security Center.</span></span>|
|<span data-ttu-id="45de7-492">防禦者</span><span class="sxs-lookup"><span data-stu-id="45de7-492">Defender</span></span>|<span data-ttu-id="45de7-493">Windows 防禦者反惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="45de7-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="45de7-494">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-494">Require</span></span>||
||<span data-ttu-id="45de7-495">Windows 防禦者反惡意程式碼的最小版本</span><span class="sxs-lookup"><span data-stu-id="45de7-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="45de7-p128">僅支援 Windows 10 桌面。Microsoft 建議版本不超過五後方從最新版本。</span><span class="sxs-lookup"><span data-stu-id="45de7-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version.</span></span>|
||<span data-ttu-id="45de7-498">最新的 Windows 防禦者反惡意程式碼簽章</span><span class="sxs-lookup"><span data-stu-id="45de7-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="45de7-499">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-499">Require</span></span>||
||<span data-ttu-id="45de7-500">[即時保護]</span><span class="sxs-lookup"><span data-stu-id="45de7-500">Real-time protection</span></span>|<span data-ttu-id="45de7-501">需要</span><span class="sxs-lookup"><span data-stu-id="45de7-501">Require</span></span>|<span data-ttu-id="45de7-502">僅支援 Windows 10 桌面。</span><span class="sxs-lookup"><span data-stu-id="45de7-502">Only supported for Windows 10 desktop.</span></span>|

<span data-ttu-id="45de7-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="45de7-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="45de7-504">類型</span><span class="sxs-lookup"><span data-stu-id="45de7-504">Type</span></span>|<span data-ttu-id="45de7-505">屬性</span><span class="sxs-lookup"><span data-stu-id="45de7-505">Properties</span></span>|<span data-ttu-id="45de7-506">值</span><span class="sxs-lookup"><span data-stu-id="45de7-506">Values</span></span>|<span data-ttu-id="45de7-507">附註</span><span class="sxs-lookup"><span data-stu-id="45de7-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="45de7-508">Windows 防禦者進階威脅保護規則</span><span class="sxs-lookup"><span data-stu-id="45de7-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="45de7-509">需要裝置是在或下機器風險分數</span><span class="sxs-lookup"><span data-stu-id="45de7-509">Require the device to be at or under the machine risk score</span></span>|<span data-ttu-id="45de7-510">中</span><span class="sxs-lookup"><span data-stu-id="45de7-510">Medium</span></span>||





## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="45de7-511">需要相容的 Pc （但不是相容的電話與平板電腦）</span><span class="sxs-lookup"><span data-stu-id="45de7-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="45de7-p129">之前加入至需要相容的 Pc 的原則，請務必註冊管理到 Intune 的裝置。之前將 Intune 註冊裝置的裝置在預定使用者所持有的保證建議您不要使用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="45de7-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="45de7-514">若要要求相容的 Pc：</span><span class="sxs-lookup"><span data-stu-id="45de7-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="45de7-p130">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="45de7-517">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="45de7-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="45de7-518">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="45de7-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="45de7-519">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="45de7-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="45de7-520">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="45de7-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="45de7-521">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="45de7-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="45de7-p131">選擇 [**選取應用程式**、 從**雲端應用程式**清單中選取所需的應用程式。例如，選取 [Office 365 Exchange Online。按一下 [**選取 [** **完成**]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="45de7-p132">若要要求相容的 Pc，但不是相容的電話與平板電腦，請選擇 [**條件**和**裝置平台**。選擇 「 選取裝置平台 」，並選取 [ **Windows**和**macOS**。</span><span class="sxs-lookup"><span data-stu-id="45de7-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose "Select device platforms" and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="45de7-527">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="45de7-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="45de7-p133">選擇 [**授與存取權**，請選取 [**需要標示為相容的裝置**。 多個控制項，選取 [**需要所有選取的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="45de7-p133">Choose **Grant access**, select **Require device to be marked as compliant**.  For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="45de7-530">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-530">Click **Create**.</span></span>

<span data-ttu-id="45de7-p134">如果您的目標為何需要相容的 Pc*和*行動裝置，請勿選取平台。這會強制執行的所有裝置相容。</span><span class="sxs-lookup"><span data-stu-id="45de7-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliant for all devices.</span></span> 




## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="45de7-533">需要相容的 Pc*和*行動裝置</span><span class="sxs-lookup"><span data-stu-id="45de7-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="45de7-534">若要要求規範的所有裝置：</span><span class="sxs-lookup"><span data-stu-id="45de7-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="45de7-p135">前往[ Azure 入口網站](https://portal.azure.com)，並使用您的認證登入。 成功登入之後，您會看到 [Azure 儀表板]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure Dashboard.</span></span>

2. <span data-ttu-id="45de7-537">從左功能表選擇 [Azure Active Directory]。</span><span class="sxs-lookup"><span data-stu-id="45de7-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="45de7-538">在 [安全性] 區段下，選擇 [條件式存取]。</span><span class="sxs-lookup"><span data-stu-id="45de7-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="45de7-539">選擇 [新增原則]。</span><span class="sxs-lookup"><span data-stu-id="45de7-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="45de7-540">輸入原則名稱，然後選擇您想要套用原則的**使用者與群組**。</span><span class="sxs-lookup"><span data-stu-id="45de7-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="45de7-541">選擇 [雲端應用程式]。</span><span class="sxs-lookup"><span data-stu-id="45de7-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="45de7-p136">選擇 [**選取應用程式**、 從**雲端應用程式**清單中選取所需的應用程式。例如，選取 [Office 365 Exchange Online。按一下 [**選取 [** **完成**]。</span><span class="sxs-lookup"><span data-stu-id="45de7-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Click **Select** and **Done**.</span></span>

8. <span data-ttu-id="45de7-545">選擇 [存取控制] 區段中的 [授與]。</span><span class="sxs-lookup"><span data-stu-id="45de7-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="45de7-p137">選擇 [**授與存取權**，請選取 [**需要標示為相容的裝置**。多個控制項，選取 [**需要所有選取的控制項**，然後選擇 [**選取**。</span><span class="sxs-lookup"><span data-stu-id="45de7-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="45de7-548">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-548">Click **Create**.</span></span>

<span data-ttu-id="45de7-p138">建立此原則，請勿選取平台。這會強制執行相容的裝置。</span><span class="sxs-lookup"><span data-stu-id="45de7-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>















<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="45de7-551">接下來的步驟</span><span class="sxs-lookup"><span data-stu-id="45de7-551">Next steps</span></span>

[<span data-ttu-id="45de7-552">了解保護電子郵件的原則建議</span><span class="sxs-lookup"><span data-stu-id="45de7-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
