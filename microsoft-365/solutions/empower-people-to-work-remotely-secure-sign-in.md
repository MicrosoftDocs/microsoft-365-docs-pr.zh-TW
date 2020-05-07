---
title: 步驟 1： 使用 MFA 提升遠端工作者的登入安全性
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 您的遠端工作者必須使用多重要素驗證 (MFA) 來登入。
ms.openlocfilehash: dfb4262c05399e1c5add9b151c42c143ac723a7d
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066124"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a><span data-ttu-id="aa1de-104">步驟 1：</span><span class="sxs-lookup"><span data-stu-id="aa1de-104">Step 1.</span></span> <span data-ttu-id="aa1de-105">使用 MFA 提升遠端工作者的登入安全性</span><span class="sxs-lookup"><span data-stu-id="aa1de-105">Increase sign-in security for remote workers with MFA</span></span>

<span data-ttu-id="aa1de-106">若要提升遠端工作者的登入安全性，請使用多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="aa1de-106">To increase the security of sign-ins of your remote workers, use multi-factor authentication (MFA).</span></span> <span data-ttu-id="aa1de-107">MFA 會要求使用者登入程序另外遵守使用者帳戶密碼以外的驗證規定。</span><span class="sxs-lookup"><span data-stu-id="aa1de-107">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="aa1de-108">惡意使用者即使確定了使用者帳戶的密碼，還必須能夠回應另外的驗證機制 (例如，傳送至智慧型手機的簡訊)，才能獲得存取權。</span><span class="sxs-lookup"><span data-stu-id="aa1de-108">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正確的密碼加上其他驗證則可導致順利登入](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="aa1de-110">Microsoft 強烈建議包括遠端工作者 (特別是系統管理員) 在內的所有使用者都使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="aa1de-110">For all users, including remote workers and especially admins, Microsoft strongly recommends MFA.</span></span>

<span data-ttu-id="aa1de-111">根據您的 Microsoft 365 方案，您有三種方法可以要求使用者使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="aa1de-111">There are three ways to require your users to use MFA based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="aa1de-112">方案</span><span class="sxs-lookup"><span data-stu-id="aa1de-112">Plan</span></span>  |<span data-ttu-id="aa1de-113">建議</span><span class="sxs-lookup"><span data-stu-id="aa1de-113">Recommendation</span></span>  |
|---------|---------|
|<span data-ttu-id="aa1de-114">Microsoft 365 方案 (不含 Azure AD Premium P1 或 P2)</span><span class="sxs-lookup"><span data-stu-id="aa1de-114">Microsoft 365 plans (without Azure AD Premium P1 or P2)</span></span>     |<span data-ttu-id="aa1de-115">[在 Azure AD 中啟用安全性預設](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="aa1de-115">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="aa1de-116">Azure AD 中的安全性預設包含了適用於使用者和系統管理員的 MFA。</span><span class="sxs-lookup"><span data-stu-id="aa1de-116">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="aa1de-117">Microsoft 365 E3 (含 Azure AD Premium P1)</span><span class="sxs-lookup"><span data-stu-id="aa1de-117">Microsoft 365 E3 (with Azure AD Premium P1)</span></span>     | <span data-ttu-id="aa1de-118">使用[常見的條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則：</span><span class="sxs-lookup"><span data-stu-id="aa1de-118">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="aa1de-119">- [要求系統管理員使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="aa1de-119">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="aa1de-120">- [要求所有使用者使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="aa1de-120">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="aa1de-121">- [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="aa1de-121">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="aa1de-122">Microsoft 365 E5 (含 Azure AD Premium P2)</span><span class="sxs-lookup"><span data-stu-id="aa1de-122">Microsoft 365 E5 (with Azure AD Premium P2)</span></span>     | <span data-ttu-id="aa1de-123">利用 Azure AD Identity Protection，藉由建立下列兩種原則來開始實作 Microsoft [建議的一組條件式存取和相關原則](../enterprise/identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="aa1de-123">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="aa1de-124">- [登入風險為中或高時，需要 MFA](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="aa1de-124">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="aa1de-125">- [封鎖不支援新式驗證的用戶端](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span><span class="sxs-lookup"><span data-stu-id="aa1de-125">- [Block clients that don't support modern authentication](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span></span><br><span data-ttu-id="aa1de-126">- [高風險使用者必須變更密碼](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="aa1de-126">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

## <a name="security-defaults"></a><span data-ttu-id="aa1de-127">安全性預設</span><span class="sxs-lookup"><span data-stu-id="aa1de-127">Security defaults</span></span>

<span data-ttu-id="aa1de-128">安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。</span><span class="sxs-lookup"><span data-stu-id="aa1de-128">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="aa1de-129">這些訂用帳戶會開啟安全性預設，而***要求所有使用者都必須使用 MFA 與 Microsoft Authenticator 應用程式***。</span><span class="sxs-lookup"><span data-stu-id="aa1de-129">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="aa1de-130">使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。</span><span class="sxs-lookup"><span data-stu-id="aa1de-130">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="aa1de-131">14 天過後，使用者就無法登入，除非其完成 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="aa1de-131">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="aa1de-132">安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。</span><span class="sxs-lookup"><span data-stu-id="aa1de-132">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="aa1de-133">您可以停用安全性預設，改為使用 MFA 與條件式存取原則或改為使用個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="aa1de-133">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="aa1de-134">如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="aa1de-134">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="aa1de-135">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="aa1de-135">Conditional Access policies</span></span>

<span data-ttu-id="aa1de-136">條件式存取原則是一組規則，可指定要在什麼條件下評估和允許登入。</span><span class="sxs-lookup"><span data-stu-id="aa1de-136">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="aa1de-137">例如，您可以建立敘述如下的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="aa1de-137">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="aa1de-138">如果使用者帳戶名稱適用於 Exchange、使用者、密碼、安全性、SharePoint 或全域系統管理員，則先要求 MFA 再允許存取。</span><span class="sxs-lookup"><span data-stu-id="aa1de-138">If the user account name is for a user that is an Exchange, user, password, security, SharePoint, or global administrator, require MFA before allowing access.</span></span>

<span data-ttu-id="aa1de-139">比起試著記得在這些系統管理員角色中新增或移除個別使用者帳戶時為其設定 MFA，此原則容易得多。</span><span class="sxs-lookup"><span data-stu-id="aa1de-139">This policy is easier than trying to remember to configure individual user accounts for MFA when they are added to or removed from these administrator roles.</span></span>

<span data-ttu-id="aa1de-140">您也可以使用條件式存取原則來執行更進階的功能，例如要求登入必須是來自符合規範的裝置 (例如執行 Windows 10 的膝上型電腦)。</span><span class="sxs-lookup"><span data-stu-id="aa1de-140">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="aa1de-141">條件式存取需要 Azure AD Premium P1，此方案隨附於 Microsoft 365 E3 和 E5。</span><span class="sxs-lookup"><span data-stu-id="aa1de-141">Conditional Access requires Azure AD Premium P1, which is included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="aa1de-142">如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="aa1de-142">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

## <a name="azure-ad-identity-protection-policies"></a><span data-ttu-id="aa1de-143">Azure AD Identity Protection 原則</span><span class="sxs-lookup"><span data-stu-id="aa1de-143">Azure AD Identity Protection policies</span></span>

<span data-ttu-id="aa1de-144">Azure AD Identity Protection 原則是可指定要在什麼條件下評估和允許登入的規則。</span><span class="sxs-lookup"><span data-stu-id="aa1de-144">Azure AD Identity Protection policies are rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="aa1de-145">例如，您可以建立敘述如下的 Azure AD Identity Protection 原則：</span><span class="sxs-lookup"><span data-stu-id="aa1de-145">For example, you can create an Azure AD Identity Protection policy that states:</span></span>

- <span data-ttu-id="aa1de-146">如果經判斷登入風險屬於中或高風險時，使用者必須使用 MFA 才能登入。</span><span class="sxs-lookup"><span data-stu-id="aa1de-146">If the risk of the sign-in is determined to be medium or high risk, the user must use MFA to sign in.</span></span>

<span data-ttu-id="aa1de-147">Azure AD Identity Protection 需要 Azure AD Premium P2，此方案隨附於 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="aa1de-147">Azure AD Identity Protection requires Azure AD Premium P2, which is included with Microsoft 365 E5.</span></span>

<span data-ttu-id="aa1de-148">如需詳細資訊，請參閱這個 [Azure AD Identity Protection 概觀](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="aa1de-148">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

## <a name="using-these-methods-together"></a><span data-ttu-id="aa1de-149">共同使用這些方法</span><span class="sxs-lookup"><span data-stu-id="aa1de-149">Using these methods together</span></span>

<span data-ttu-id="aa1de-150">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="aa1de-150">Keep in mind the following:</span></span>

- <span data-ttu-id="aa1de-151">如果您已啟用任何條件式存取原則，則無法啟用安全性預設。</span><span class="sxs-lookup"><span data-stu-id="aa1de-151">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="aa1de-152">如果您已啟用安全性預設，則無法啟用任何條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="aa1de-152">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="aa1de-153">如果已啟用安全性預設，系統會提示所有新使用者註冊 MFA 並使用 Microsoft Authenticator 應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa1de-153">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="aa1de-154">下表顯示啟用 MFA 與安全性預設、條件式存取原則和每一使用者帳戶設定的結果。</span><span class="sxs-lookup"><span data-stu-id="aa1de-154">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="aa1de-155">Enabled</span><span class="sxs-lookup"><span data-stu-id="aa1de-155">Enabled</span></span> | <span data-ttu-id="aa1de-156">停用</span><span class="sxs-lookup"><span data-stu-id="aa1de-156">Disabled</span></span> | <span data-ttu-id="aa1de-157">次要驗證方法</span><span class="sxs-lookup"><span data-stu-id="aa1de-157">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="aa1de-158">**安全性預設**</span><span class="sxs-lookup"><span data-stu-id="aa1de-158">**Security defaults**</span></span>  | <span data-ttu-id="aa1de-159">無法使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="aa1de-159">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="aa1de-160">可以使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="aa1de-160">Can use Conditional Access policies</span></span> | <span data-ttu-id="aa1de-161">Microsoft Authenticator 應用程式</span><span class="sxs-lookup"><span data-stu-id="aa1de-161">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="aa1de-162">**條件式存取原則**</span><span class="sxs-lookup"><span data-stu-id="aa1de-162">**Conditional Access policies**</span></span> | <span data-ttu-id="aa1de-163">如果已啟用任何原則，則無法啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="aa1de-163">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="aa1de-164">如果未啟用任何原則，則可以啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="aa1de-164">If all are not enabled, you can enable security defaults</span></span>  | <span data-ttu-id="aa1de-165">在註冊 MFA 期間由使用者指定</span><span class="sxs-lookup"><span data-stu-id="aa1de-165">User-specified during MFA registration</span></span>  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a><span data-ttu-id="aa1de-166">適用於 MFA 和身分識別的系統管理員訓練與技術資源</span><span class="sxs-lookup"><span data-stu-id="aa1de-166">Admin training and technical resources for MFA and identity</span></span>

- [<span data-ttu-id="aa1de-167">Microsoft 365 的 MFA 規劃</span><span class="sxs-lookup"><span data-stu-id="aa1de-167">MFA planning for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [<span data-ttu-id="aa1de-168">Azure AD 可協助您啟用遠端工作的五大方法</span><span class="sxs-lookup"><span data-stu-id="aa1de-168">Top 5 ways your Azure AD can help you enable remote work</span></span>](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [<span data-ttu-id="aa1de-169">規劃及部署 Microsoft 365 的身分識別基礎結構</span><span class="sxs-lookup"><span data-stu-id="aa1de-169">Plan and deploy your Microsoft 365 identity infrastructure</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [<span data-ttu-id="aa1de-170">Azure Academy Azure AD 訓練影片</span><span class="sxs-lookup"><span data-stu-id="aa1de-170">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="aa1de-171">設定 Azure Multi-Factor Authentication 註冊原則</span><span class="sxs-lookup"><span data-stu-id="aa1de-171">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a><span data-ttu-id="aa1de-172">步驟 1 的結果</span><span class="sxs-lookup"><span data-stu-id="aa1de-172">Results of Step 1</span></span>

<span data-ttu-id="aa1de-173">部署 MFA 之後，您的使用者：</span><span class="sxs-lookup"><span data-stu-id="aa1de-173">After deployment of MFA, your users:</span></span>

- <span data-ttu-id="aa1de-174">必須使用 MFA 來登入。</span><span class="sxs-lookup"><span data-stu-id="aa1de-174">Are required to use MFA for sign-ins.</span></span>
- <span data-ttu-id="aa1de-175">已完成 MFA 註冊程序，且會使用 MFA 來進行所有登入。</span><span class="sxs-lookup"><span data-stu-id="aa1de-175">Have completed the MFA registration process and is using MFA for all sign-ins.</span></span>

## <a name="next-step"></a><span data-ttu-id="aa1de-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="aa1de-176">Next step</span></span>

<span data-ttu-id="aa1de-177">繼續[步驟 2](empower-people-to-work-remotely-remote-access.md)，以為內部部署應用程式和服務提供遠端存取。</span><span class="sxs-lookup"><span data-stu-id="aa1de-177">Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.</span></span>
