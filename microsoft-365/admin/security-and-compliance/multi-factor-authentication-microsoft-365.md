---
title: Microsoft 365 的多重要素驗證
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 深入瞭解 Microsoft 365 中的多重要素驗證。
ms.openlocfilehash: e8ba304d145ca7227eea074556ff6efccd751ecf
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399143"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="f381c-103">Microsoft 365 的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="f381c-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="f381c-104">密碼是對電腦或線上服務驗證登入的最常見方法，但也是最容易受到攻擊的方法。</span><span class="sxs-lookup"><span data-stu-id="f381c-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="f381c-105">人員可以選擇輕鬆密碼，並對不同的電腦和服務使用多個登入的相同密碼。</span><span class="sxs-lookup"><span data-stu-id="f381c-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="f381c-106">若要為登入提供額外的安全性層級，您必須使用多重要素驗證（MFA），它會同時使用密碼（該密碼應該強），並以其他驗證方法為基礎：</span><span class="sxs-lookup"><span data-stu-id="f381c-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="f381c-107">您所擁有的專案不會輕易重複，例如智慧型電話。</span><span class="sxs-lookup"><span data-stu-id="f381c-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="f381c-108">您獨特且 biologically 的功能，例如您的指紋、字型或其他生物統計學屬性。</span><span class="sxs-lookup"><span data-stu-id="f381c-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="f381c-109">在驗證使用者密碼之後，才會採用其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="f381c-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="f381c-110">使用 MFA 時，即使強使用者密碼遭到損害，攻擊者也沒有您的智慧型電話或指紋，即可完成登入。</span><span class="sxs-lookup"><span data-stu-id="f381c-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="f381c-111">Microsoft 365 中的 MFA 支援</span><span class="sxs-lookup"><span data-stu-id="f381c-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="f381c-112">根據預設，Microsoft 365 和 Office 365 都支援使用下列使用者帳戶的 MFA：</span><span class="sxs-lookup"><span data-stu-id="f381c-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="f381c-113">傳送至電話的文字訊息，需要使用者輸入驗證碼。</span><span class="sxs-lookup"><span data-stu-id="f381c-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="f381c-114">通話。</span><span class="sxs-lookup"><span data-stu-id="f381c-114">A phone call.</span></span>
- <span data-ttu-id="f381c-115">Microsoft 驗證器智慧型電話應用程式。</span><span class="sxs-lookup"><span data-stu-id="f381c-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="f381c-116">在這兩種情況下，MFA 登入都使用「您具有的「您所擁有的專案」方法，以進行其他驗證。</span><span class="sxs-lookup"><span data-stu-id="f381c-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="f381c-117">您可以使用多種方式，為 Microsoft 365 和 Office 365 啟用 MFA：</span><span class="sxs-lookup"><span data-stu-id="f381c-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="f381c-118">使用安全性預設值</span><span class="sxs-lookup"><span data-stu-id="f381c-118">With security defaults</span></span>
- <span data-ttu-id="f381c-119">使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f381c-119">With Conditional Access policies</span></span>
- <span data-ttu-id="f381c-120">每個個別使用者帳戶（不建議）</span><span class="sxs-lookup"><span data-stu-id="f381c-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="f381c-121">這些方式是以您的 Microsoft 365 方案為基礎。</span><span class="sxs-lookup"><span data-stu-id="f381c-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="f381c-122">方案</span><span class="sxs-lookup"><span data-stu-id="f381c-122">Plan</span></span>  |<span data-ttu-id="f381c-123">建議</span><span class="sxs-lookup"><span data-stu-id="f381c-123">Recommendation</span></span>  | <span data-ttu-id="f381c-124">客戶類型</span><span class="sxs-lookup"><span data-stu-id="f381c-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="f381c-125">所有 Microsoft 365 方案</span><span class="sxs-lookup"><span data-stu-id="f381c-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="f381c-126">使用安全性預設值，這需要對所有使用者帳戶執行 MFA。</span><span class="sxs-lookup"><span data-stu-id="f381c-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="f381c-127">您也可以針對個別使用者帳戶要求 MFA，但不建議這麼做。</span><span class="sxs-lookup"><span data-stu-id="f381c-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="f381c-128">小型企業</span><span class="sxs-lookup"><span data-stu-id="f381c-128">Small business</span></span> |
| <span data-ttu-id="f381c-129">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="f381c-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="f381c-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="f381c-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="f381c-131">Azure Active Directory （Azure AD）高級 P1 授權</span><span class="sxs-lookup"><span data-stu-id="f381c-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="f381c-132">使用條件式存取原則，根據群組成員資格、應用程式或其他準則，針對使用者帳戶要求 MFA。</span><span class="sxs-lookup"><span data-stu-id="f381c-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="f381c-133">小型企業對企業</span><span class="sxs-lookup"><span data-stu-id="f381c-133">Small business to enterprise</span></span> |
| <span data-ttu-id="f381c-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f381c-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="f381c-135">Azure AD 高級 P2 授權</span><span class="sxs-lookup"><span data-stu-id="f381c-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="f381c-136">使用 Azure AD 身分識別保護，根據登入風險準則要求 MFA。</span><span class="sxs-lookup"><span data-stu-id="f381c-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="f381c-137">企業</span><span class="sxs-lookup"><span data-stu-id="f381c-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="f381c-138">安全性預設</span><span class="sxs-lookup"><span data-stu-id="f381c-138">Security defaults</span></span>

<span data-ttu-id="f381c-139">安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。</span><span class="sxs-lookup"><span data-stu-id="f381c-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="f381c-140">這些訂閱已開啟安全性預設值，其：</span><span class="sxs-lookup"><span data-stu-id="f381c-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="f381c-141">要求所有使用者都使用 MFA 與 Microsoft 驗證器應用程式。</span><span class="sxs-lookup"><span data-stu-id="f381c-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="f381c-142">封鎖舊版驗證。</span><span class="sxs-lookup"><span data-stu-id="f381c-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="f381c-143">使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。</span><span class="sxs-lookup"><span data-stu-id="f381c-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="f381c-144">14 天過後，使用者就無法登入，除非其完成 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="f381c-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="f381c-145">安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。</span><span class="sxs-lookup"><span data-stu-id="f381c-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="f381c-146">您可以使用條件式存取原則來停用安全性預設值，以取代 MFA。</span><span class="sxs-lookup"><span data-stu-id="f381c-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="f381c-147">您可以在 Azure 入口網站中，啟用或停用 Azure AD 的**屬性**窗格中的安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="f381c-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="f381c-148">您可以使用安全性預設值搭配任何 Microsoft 365 方案。</span><span class="sxs-lookup"><span data-stu-id="f381c-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="f381c-149">如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="f381c-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="f381c-150">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f381c-150">Conditional Access policies</span></span>

<span data-ttu-id="f381c-151">條件式存取原則是一組規則，可指定要在什麼條件下評估和允許登入。</span><span class="sxs-lookup"><span data-stu-id="f381c-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="f381c-152">例如，您可以建立敘述如下的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="f381c-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="f381c-153">如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。</span><span class="sxs-lookup"><span data-stu-id="f381c-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="f381c-154">此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f381c-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="f381c-155">您也可以使用條件式存取原則進行更高級的功能，例如，針對特定的應用程式要求 MFA，或登入是從相容的裝置（例如，您的可擕式電腦執行 Windows 10）進行。</span><span class="sxs-lookup"><span data-stu-id="f381c-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="f381c-156">您可以在 Azure 入口網站中，從 Azure AD 的**安全性**窗格中設定條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="f381c-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="f381c-157">您可以使用條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="f381c-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="f381c-158">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="f381c-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="f381c-159">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="f381c-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="f381c-160">Azure AD Premium P1 和 Azure AD Premium P2 授權</span><span class="sxs-lookup"><span data-stu-id="f381c-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="f381c-161">針對具有 Microsoft 365 商務版 Premium 的小型企業，您可以使用下列步驟輕鬆使用條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="f381c-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="f381c-162">建立群組，以包含需要 MFA 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f381c-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="f381c-163">啟用 [**需要對全域管理員的 MFA** ] 原則。</span><span class="sxs-lookup"><span data-stu-id="f381c-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="f381c-164">使用下列設定來建立以群組為基礎的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="f381c-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="f381c-165">> 使用者和群組的工作分派：上述步驟1的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f381c-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="f381c-166">工作分派 > Cloud app or 動作：所有雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="f381c-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="f381c-167">存取控制 > 授與存取權 > > 需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="f381c-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="f381c-168">啟用原則。</span><span class="sxs-lookup"><span data-stu-id="f381c-168">Enable the policy.</span></span>
5. <span data-ttu-id="f381c-169">將使用者帳戶新增至上述步驟1中建立的群組，然後進行測試。</span><span class="sxs-lookup"><span data-stu-id="f381c-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="f381c-170">若要對其他使用者帳戶要求 MFA，請將其新增至步驟1中建立的群組。</span><span class="sxs-lookup"><span data-stu-id="f381c-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="f381c-171">此條件式存取原則可讓您以您自己的節奏向您的使用者推廣 MFA 需求。</span><span class="sxs-lookup"><span data-stu-id="f381c-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="f381c-172">企業應該使用[通用的條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則：</span><span class="sxs-lookup"><span data-stu-id="f381c-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="f381c-173">要求系統管理員使用 MFA</span><span class="sxs-lookup"><span data-stu-id="f381c-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="f381c-174">要求所有使用者使用 MFA</span><span class="sxs-lookup"><span data-stu-id="f381c-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="f381c-175">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="f381c-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="f381c-176">如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="f381c-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="f381c-177">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="f381c-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="f381c-178">使用 Azure AD Identity Protection，您可以建立額外的條件式存取原則，以在登[入風險為中低或高時，要求進行 MFA](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)。</span><span class="sxs-lookup"><span data-stu-id="f381c-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="f381c-179">您可以使用 Azure AD 身分識別保護和以風險為基礎的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="f381c-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="f381c-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f381c-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="f381c-181">Azure AD 高級 P2 授權</span><span class="sxs-lookup"><span data-stu-id="f381c-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="f381c-182">如需詳細資訊，請參閱這個 [Azure AD Identity Protection 概觀](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="f381c-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="f381c-183">個別使用者帳戶的 MFA （不建議使用）</span><span class="sxs-lookup"><span data-stu-id="f381c-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="f381c-184">您應該使用安全性預設值或條件式存取原則，針對您的使用者帳戶登入要求 MFA。不過，如果上述任一項無法使用，Microsoft 強烈建議對具有系統管理員角色的使用者帳戶（特別是全域系統管理員角色）進行 MFA，以進行任何大小訂閱。</span><span class="sxs-lookup"><span data-stu-id="f381c-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="f381c-185">您可以從 Microsoft 365 系統管理中心的 [作用中**使用者**] 窗格中，為個別使用者帳戶啟用 MFA。</span><span class="sxs-lookup"><span data-stu-id="f381c-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="f381c-186">啟用之後，使用者下一次登入時，系統會提示他們註冊 MFA，並選擇及測試其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="f381c-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="f381c-187">共同使用這些方法</span><span class="sxs-lookup"><span data-stu-id="f381c-187">Using these methods together</span></span>

<span data-ttu-id="f381c-188">下表顯示啟用 MFA 與安全性預設、條件式存取原則和每一使用者帳戶設定的結果。</span><span class="sxs-lookup"><span data-stu-id="f381c-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="f381c-189">Enabled</span><span class="sxs-lookup"><span data-stu-id="f381c-189">Enabled</span></span> | <span data-ttu-id="f381c-190">停用</span><span class="sxs-lookup"><span data-stu-id="f381c-190">Disabled</span></span> | <span data-ttu-id="f381c-191">次要驗證方法</span><span class="sxs-lookup"><span data-stu-id="f381c-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="f381c-192">**安全性預設**</span><span class="sxs-lookup"><span data-stu-id="f381c-192">**Security defaults**</span></span> | <span data-ttu-id="f381c-193">無法使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f381c-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="f381c-194">可以使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f381c-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="f381c-195">Microsoft Authenticator 應用程式</span><span class="sxs-lookup"><span data-stu-id="f381c-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="f381c-196">**條件式存取原則**</span><span class="sxs-lookup"><span data-stu-id="f381c-196">**Conditional Access policies**</span></span> |<span data-ttu-id="f381c-197">如果已啟用任何原則，則無法啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="f381c-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="f381c-198">如果已停用所有原則，則可啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="f381c-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="f381c-199">在註冊 MFA 期間由使用者指定</span><span class="sxs-lookup"><span data-stu-id="f381c-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="f381c-200">**每個使用者帳戶設定（不建議使用）**</span><span class="sxs-lookup"><span data-stu-id="f381c-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="f381c-201">覆寫安全性預設值，以及在每次登入時要求 MFA 的條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f381c-201">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span> | <span data-ttu-id="f381c-202">由安全性預設值和條件式存取原則所取代</span><span class="sxs-lookup"><span data-stu-id="f381c-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="f381c-203">在註冊 MFA 期間由使用者指定</span><span class="sxs-lookup"><span data-stu-id="f381c-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="f381c-204">如果啟用安全性預設值，系統會提示所有新的使用者進行 MFA 註冊，並在下一個登入時使用 Microsoft 驗證應用程式。</span><span class="sxs-lookup"><span data-stu-id="f381c-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="f381c-205">管理 MFA 設定的方法</span><span class="sxs-lookup"><span data-stu-id="f381c-205">Ways to manage MFA settings</span></span>

<span data-ttu-id="f381c-206">有兩種方式可管理 MFA 設定。</span><span class="sxs-lookup"><span data-stu-id="f381c-206">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="f381c-207">在 Azure 入口網站中，您可以：</span><span class="sxs-lookup"><span data-stu-id="f381c-207">In the Azure portal, you can:</span></span>

- <span data-ttu-id="f381c-208">啟用及停用安全性預設值</span><span class="sxs-lookup"><span data-stu-id="f381c-208">Enable and disable security defaults</span></span>
- <span data-ttu-id="f381c-209">設定條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="f381c-209">Configure Conditional Access policies</span></span>

<span data-ttu-id="f381c-210">在 Microsoft 365 系統管理中心中，您可以設定每個使用者和服務 MFA 設定。</span><span class="sxs-lookup"><span data-stu-id="f381c-210">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="f381c-211">下一個步驟</span><span class="sxs-lookup"><span data-stu-id="f381c-211">Your next step</span></span>

[<span data-ttu-id="f381c-212">設定 Microsoft 365 的 MFA</span><span class="sxs-lookup"><span data-stu-id="f381c-212">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

