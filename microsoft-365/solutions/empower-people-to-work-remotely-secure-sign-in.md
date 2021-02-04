---
title: 步驟 1： 使用 MFA 提升遠端工作者的登入安全性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 您的遠端工作者必須使用多重要素驗證 (MFA) 來登入。
ms.openlocfilehash: 7df6b1335c0ca45c06eee98eeff89f59b6365807
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097137"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a><span data-ttu-id="feece-104">步驟 1：</span><span class="sxs-lookup"><span data-stu-id="feece-104">Step 1.</span></span> <span data-ttu-id="feece-105">使用 MFA 提升遠端工作者的登入安全性</span><span class="sxs-lookup"><span data-stu-id="feece-105">Increase sign-in security for remote workers with MFA</span></span>

<span data-ttu-id="feece-106">若要提升遠端工作者的登入安全性，請使用多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="feece-106">To increase the security of sign-ins of your remote workers, use multi-factor authentication (MFA).</span></span> <span data-ttu-id="feece-107">MFA 會要求使用者登入程序另外遵守使用者帳戶密碼以外的驗證規定。</span><span class="sxs-lookup"><span data-stu-id="feece-107">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="feece-108">惡意使用者即使確定了使用者帳戶的密碼，還必須能夠回應另外的驗證機制 (例如，傳送至智慧型手機的簡訊)，才能獲得存取權。</span><span class="sxs-lookup"><span data-stu-id="feece-108">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正確的密碼加上其他驗證則可導致順利登入](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="feece-110">Microsoft 強烈建議包括遠端工作者 (特別是系統管理員) 在內的所有使用者都使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="feece-110">For all users, including remote workers and especially admins, Microsoft strongly recommends MFA.</span></span>

<span data-ttu-id="feece-111">根據您的 Microsoft 365 方案，您有三種方法可以要求使用者使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="feece-111">There are three ways to require your users to use MFA based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="feece-112">方案</span><span class="sxs-lookup"><span data-stu-id="feece-112">Plan</span></span>  |<span data-ttu-id="feece-113">建議</span><span class="sxs-lookup"><span data-stu-id="feece-113">Recommendation</span></span>  |
|---------|---------|
|<span data-ttu-id="feece-114">所有的 Microsoft 365 方案（不含 Azure AD Premium P1 或 P2 授權）</span><span class="sxs-lookup"><span data-stu-id="feece-114">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="feece-115">[在 Azure AD 中啟用安全性預設](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="feece-115">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="feece-116">Azure AD 中的安全性預設包含了適用於使用者和系統管理員的 MFA。</span><span class="sxs-lookup"><span data-stu-id="feece-116">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="feece-117">Microsoft 365 E3 （含 Azure AD Premium P1 授權）</span><span class="sxs-lookup"><span data-stu-id="feece-117">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="feece-118">使用[常見的條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則：</span><span class="sxs-lookup"><span data-stu-id="feece-118">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="feece-119">- [要求系統管理員使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="feece-119">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="feece-120">- [要求所有使用者使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="feece-120">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="feece-121">- [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="feece-121">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="feece-122">Microsoft 365 E5 （含 Azure AD Premium P2 授權）</span><span class="sxs-lookup"><span data-stu-id="feece-122">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="feece-123">利用 Azure AD Identity Protection，藉由建立下列原則來開始實作 Microsoft [建議的一組條件式存取和相關原則](../security/office-365-security/identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="feece-123">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of Conditional Access and related policies](../security/office-365-security/identity-access-policies.md) by creating these policies:</span></span><br> <span data-ttu-id="feece-124">- [登入風險為中或高時，需要 MFA](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="feece-124">- [Require MFA when sign-in risk is medium or high](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="feece-125">- [封鎖不支援新式驗證的用戶端](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)</span><span class="sxs-lookup"><span data-stu-id="feece-125">- [Block clients that don't support modern authentication](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-multi-factor)</span></span><br><span data-ttu-id="feece-126">- [高風險使用者必須變更密碼](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="feece-126">- [High risk users must change password](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

## <a name="security-defaults"></a><span data-ttu-id="feece-127">安全性預設</span><span class="sxs-lookup"><span data-stu-id="feece-127">Security defaults</span></span>

<span data-ttu-id="feece-128">安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。</span><span class="sxs-lookup"><span data-stu-id="feece-128">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="feece-129">這些訂用帳戶會開啟安全性預設，而 ***要求所有使用者都必須使用 MFA 與 Microsoft Authenticator 應用程式***。</span><span class="sxs-lookup"><span data-stu-id="feece-129">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="feece-130">使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。</span><span class="sxs-lookup"><span data-stu-id="feece-130">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="feece-131">14 天過後，使用者就無法登入，除非其完成 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="feece-131">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="feece-132">安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。</span><span class="sxs-lookup"><span data-stu-id="feece-132">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="feece-133">您可以停用安全性預設，改為使用 MFA 與條件式存取原則或改為使用個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="feece-133">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="feece-134">如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="feece-134">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="feece-135">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="feece-135">Conditional Access policies</span></span>

<span data-ttu-id="feece-136">條件式存取原則是一組規則，可指定要在什麼條件下評估和允許登入。</span><span class="sxs-lookup"><span data-stu-id="feece-136">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="feece-137">例如，您可以建立敘述如下的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="feece-137">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="feece-138">如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。</span><span class="sxs-lookup"><span data-stu-id="feece-138">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="feece-139">此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="feece-139">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="feece-140">您也可以使用條件式存取原則來執行更進階的功能，例如要求登入必須是來自符合規範的裝置 (例如執行 Windows 10 的膝上型電腦)。</span><span class="sxs-lookup"><span data-stu-id="feece-140">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="feece-141">[條件式存取] 需有 Azure AD Premium P1 授權，已附加在 Microsoft 365 E3 和 E5 套裝中。</span><span class="sxs-lookup"><span data-stu-id="feece-141">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="feece-142">如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="feece-142">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

## <a name="azure-ad-identity-protection-support"></a><span data-ttu-id="feece-143">Azure AD Identity Protection 支援</span><span class="sxs-lookup"><span data-stu-id="feece-143">Azure AD Identity Protection support</span></span>

<span data-ttu-id="feece-144">使用 Azure AD Identity Protection，您可建立敘述如下的額外條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="feece-144">With Azure AD Identity Protection, you can create an additional Conditional Access policy that states:</span></span>

- <span data-ttu-id="feece-145">如果經判斷登入風險屬於中或高風險，則要求 MFA。</span><span class="sxs-lookup"><span data-stu-id="feece-145">If the risk of the sign-in is determined to be medium or high, require MFA.</span></span>

<span data-ttu-id="feece-146">Azure AD Identity Protection 需有已附加在 Microsoft 365 E5 中的 Azure AD Premium P2 的授權資料。</span><span class="sxs-lookup"><span data-stu-id="feece-146">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>

<span data-ttu-id="feece-147">如需詳細資訊，請參閱[風險型條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)。</span><span class="sxs-lookup"><span data-stu-id="feece-147">For more information, see [Risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).</span></span>

<span data-ttu-id="feece-148">利用 Azure AD Identity Protection，您也可以建立原則，以要求您的使用者註冊使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="feece-148">With Azure AD Identity Protection, you can also create a policy to require your users to register for MFA.</span></span> <span data-ttu-id="feece-149">如需詳細資訊，請參閱[設定 Azure AD Multi-Factor Authentication 註冊原則](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)</span><span class="sxs-lookup"><span data-stu-id="feece-149">For more information, see [Configure the Azure AD Multi-Factor Authentication registration policy](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)</span></span>


## <a name="using-these-methods-together"></a><span data-ttu-id="feece-150">共同使用這些方法</span><span class="sxs-lookup"><span data-stu-id="feece-150">Using these methods together</span></span>

<span data-ttu-id="feece-151">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="feece-151">Keep the following in mind:</span></span>

- <span data-ttu-id="feece-152">如果您已啟用任何條件式存取原則，則無法啟用安全性預設。</span><span class="sxs-lookup"><span data-stu-id="feece-152">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="feece-153">如果您已啟用安全性預設，則無法啟用任何條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="feece-153">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="feece-154">如果已啟用安全性預設，系統會提示所有新使用者註冊 MFA 並使用 Microsoft Authenticator 應用程式。</span><span class="sxs-lookup"><span data-stu-id="feece-154">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="feece-155">下表顯示啟用 MFA 與安全性預設和條件式存取原則的結果。</span><span class="sxs-lookup"><span data-stu-id="feece-155">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="feece-156">Method</span><span class="sxs-lookup"><span data-stu-id="feece-156">Method</span></span> | <span data-ttu-id="feece-157">啟用</span><span class="sxs-lookup"><span data-stu-id="feece-157">Enabled</span></span> | <span data-ttu-id="feece-158">停用</span><span class="sxs-lookup"><span data-stu-id="feece-158">Disabled</span></span> | <span data-ttu-id="feece-159">額外驗證方法</span><span class="sxs-lookup"><span data-stu-id="feece-159">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="feece-160">**安全性預設**</span><span class="sxs-lookup"><span data-stu-id="feece-160">**Security defaults**</span></span>  | <span data-ttu-id="feece-161">無法使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="feece-161">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="feece-162">可以使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="feece-162">Can use Conditional Access policies</span></span> | <span data-ttu-id="feece-163">Microsoft Authenticator 應用程式</span><span class="sxs-lookup"><span data-stu-id="feece-163">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="feece-164">**條件式存取原則**</span><span class="sxs-lookup"><span data-stu-id="feece-164">**Conditional Access policies**</span></span> | <span data-ttu-id="feece-165">如果已啟用任何原則，則無法啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="feece-165">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="feece-166">如果已停用所有原則，則可啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="feece-166">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="feece-167">在 MFA 註冊期間由使用者指定</span><span class="sxs-lookup"><span data-stu-id="feece-167">User specifies during MFA registration</span></span>  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a><span data-ttu-id="feece-168">讓您的使用者重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="feece-168">Let your users reset their own passwords</span></span>

<span data-ttu-id="feece-169">自助式密碼重設（SSPR）可讓使用者自行重設自己的密碼，而不會影響到 IT 人員的工作。</span><span class="sxs-lookup"><span data-stu-id="feece-169">Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff.</span></span> <span data-ttu-id="feece-170">使用者可隨時隨地快速重設自己的密碼。</span><span class="sxs-lookup"><span data-stu-id="feece-170">Users can quickly reset their passwords at any time and from any place.</span></span> <span data-ttu-id="feece-171">如需詳細資訊，請參閱[規劃 Azure AD 自助式密碼重設部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)。</span><span class="sxs-lookup"><span data-stu-id="feece-171">For more information, see [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

## <a name="sign-in-to-saas-apps-with-azure-ad"></a><span data-ttu-id="feece-172">使用 Azure AD 登入 SaaS 應用程式</span><span class="sxs-lookup"><span data-stu-id="feece-172">Sign in to SaaS apps with Azure AD</span></span>

<span data-ttu-id="feece-173">除了為使用者提供雲端驗證之外，Azure AD 也可以是您保護所有應用程式 (無論是內部部署、位於 Microsoft 雲端或其他雲端) 的核心方式。</span><span class="sxs-lookup"><span data-stu-id="feece-173">In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud.</span></span> <span data-ttu-id="feece-174">透過[將您的應用程式整合到 Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration)，您可以輕鬆地讓遠端工作者探索所需的應用程式，並安全地登入這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="feece-174">By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for remote workers to discover the applications they need and sign into them securely.</span></span>

## <a name="admin-technical-resources-for-mfa-and-identity"></a><span data-ttu-id="feece-175">適用於 MFA 和身分識別的系統管理員技術資源</span><span class="sxs-lookup"><span data-stu-id="feece-175">Admin technical resources for MFA and identity</span></span>

- [<span data-ttu-id="feece-176">Azure AD 可協助您啟用遠端工作的五大方法</span><span class="sxs-lookup"><span data-stu-id="feece-176">Top 5 ways your Azure AD can help you enable remote work</span></span>](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [<span data-ttu-id="feece-177">Microsoft 365 的身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="feece-177">Identity roadmap for Microsoft 365</span></span>](../enterprise/identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="feece-178">Azure Academy Azure AD 訓練影片</span><span class="sxs-lookup"><span data-stu-id="feece-178">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a><span data-ttu-id="feece-179">步驟 1 的結果</span><span class="sxs-lookup"><span data-stu-id="feece-179">Results of Step 1</span></span>

<span data-ttu-id="feece-180">部署 MFA 之後，您的使用者：</span><span class="sxs-lookup"><span data-stu-id="feece-180">After deployment of MFA, your users:</span></span>

- <span data-ttu-id="feece-181">必須使用 MFA 來登入。</span><span class="sxs-lookup"><span data-stu-id="feece-181">Are required to use MFA for sign-ins.</span></span>
- <span data-ttu-id="feece-182">已完成 MFA 註冊程序，並使用 MFA 進行所有的登入動作。</span><span class="sxs-lookup"><span data-stu-id="feece-182">Have completed the MFA registration process and are using MFA for all sign-ins.</span></span>
- <span data-ttu-id="feece-183">可使用 SSPR 進行密碼重設。</span><span class="sxs-lookup"><span data-stu-id="feece-183">Can use SSPR to reset their own passwords.</span></span>

## <a name="next-step"></a><span data-ttu-id="feece-184">下一步</span><span class="sxs-lookup"><span data-stu-id="feece-184">Next step</span></span>

<span data-ttu-id="feece-185">[![步驟 2：可遠端存取內部部署應用程式和服務](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span><span class="sxs-lookup"><span data-stu-id="feece-185">[![Step 2: Provide remote access to on-premises apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span></span>

<span data-ttu-id="feece-186">繼續[步驟 2](empower-people-to-work-remotely-remote-access.md)，以為內部部署應用程式和服務提供遠端存取。</span><span class="sxs-lookup"><span data-stu-id="feece-186">Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.</span></span>
