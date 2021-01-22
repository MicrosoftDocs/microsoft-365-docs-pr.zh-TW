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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 瞭解 Microsoft 365 中的多重要素驗證。
ms.openlocfilehash: 7d62d88acb5137bd0674de7a42b44103bc9fc5f0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926543"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="8ac9c-103">Microsoft 365 的多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="8ac9c-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="8ac9c-104">密碼是驗證電腦或線上服務之登錄的最常見方法，但也容易受到任何影響。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="8ac9c-105">使用者可以選擇簡易密碼，並針對不同電腦和服務的多個登錄使用相同的密碼。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="8ac9c-106">若要為 Sign-in 提供額外的安全性層級，您必須使用多重要素驗證 (MFA) ，它同時使用一個密碼 ，這個密碼應該很強，並且根據：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="8ac9c-107">您擁有無法輕易複製的手機，例如智慧型手機。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="8ac9c-108">您獨有的專案，例如指紋、臉部或其他指紋屬性。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="8ac9c-109">驗證使用者密碼之後，才能使用額外的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="8ac9c-110">使用 MFA 時，即使強使用者密碼遭到入侵，攻擊者並沒有您的智慧型手機或指紋才能完成該登錄。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="8ac9c-111">Microsoft 365 中的 MFA 支援</span><span class="sxs-lookup"><span data-stu-id="8ac9c-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="8ac9c-112">根據預設，Microsoft 365 和 Office 365 都支援使用：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="8ac9c-113">一則文字訊息，會送到需要使用者輸入驗證碼的電話。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="8ac9c-114">通話。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-114">A phone call.</span></span>
- <span data-ttu-id="8ac9c-115">Microsoft Authenticator 智慧型手機應用程式。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="8ac9c-116">在這兩種情況下，MFA 的登錄都是使用「您擁有、不容易複製」的方法進行額外驗證。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="8ac9c-117">啟用 Microsoft 365 和 Office 365 的 MFA 有多種方式：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="8ac9c-118">使用安全性預設值</span><span class="sxs-lookup"><span data-stu-id="8ac9c-118">With security defaults</span></span>
- <span data-ttu-id="8ac9c-119">使用條件式存取策略</span><span class="sxs-lookup"><span data-stu-id="8ac9c-119">With Conditional Access policies</span></span>
- <span data-ttu-id="8ac9c-120">針對每個個別使用者帳戶 (不建議) </span><span class="sxs-lookup"><span data-stu-id="8ac9c-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="8ac9c-121">這些方法是以您的 Microsoft 365 方案為基礎。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="8ac9c-122">方案</span><span class="sxs-lookup"><span data-stu-id="8ac9c-122">Plan</span></span>|<span data-ttu-id="8ac9c-123">建議</span><span class="sxs-lookup"><span data-stu-id="8ac9c-123">Recommendation</span></span>|<span data-ttu-id="8ac9c-124">客戶類型</span><span class="sxs-lookup"><span data-stu-id="8ac9c-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="8ac9c-125">所有 Microsoft 365 方案</span><span class="sxs-lookup"><span data-stu-id="8ac9c-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="8ac9c-126">使用安全性預設值，要求所有使用者帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="8ac9c-127">您也可以針對個別使用者帳戶設定每個使用者 MFA，但不建議您這樣做。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="8ac9c-128">小型企業</span><span class="sxs-lookup"><span data-stu-id="8ac9c-128">Small business</span></span>|
|<span data-ttu-id="8ac9c-129">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="8ac9c-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="8ac9c-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="8ac9c-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="8ac9c-131">Azure Active Directory (Azure AD) 進版 P1 授權</span><span class="sxs-lookup"><span data-stu-id="8ac9c-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="8ac9c-132">使用條件式存取策略，以根據群組成員資格、應用程式或其他準則要求使用者帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="8ac9c-133">小型企業對企業</span><span class="sxs-lookup"><span data-stu-id="8ac9c-133">Small business to enterprise</span></span>|
|<span data-ttu-id="8ac9c-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8ac9c-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="8ac9c-135">Azure AD Premium P2 授權</span><span class="sxs-lookup"><span data-stu-id="8ac9c-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="8ac9c-136">使用 Azure AD 身分識別保護來根據登錄風險準則要求 MFA。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="8ac9c-137">企業</span><span class="sxs-lookup"><span data-stu-id="8ac9c-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="8ac9c-138">安全性預設</span><span class="sxs-lookup"><span data-stu-id="8ac9c-138">Security defaults</span></span>

<span data-ttu-id="8ac9c-139">安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="8ac9c-140">這些訂閱會開啟安全性預設值，其中：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="8ac9c-141">需要所有使用者將 MFA 與 Microsoft Authenticator App 一同使用。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="8ac9c-142">區塊舊版驗證。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="8ac9c-143">使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="8ac9c-144">14 天過後，使用者就無法登入，除非其完成 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="8ac9c-145">安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="8ac9c-146">您可以使用條件式存取策略來停用安全性預設值，以 MFA 為根據。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="8ac9c-147">從 Azure 入口網站中 Azure  AD 的屬性窗格啟用或停用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![目錄屬性頁面的圖片。](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="8ac9c-149">您可以在任何 Microsoft 365 方案使用安全性預設值。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="8ac9c-150">如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="8ac9c-151">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8ac9c-151">Conditional Access policies</span></span>

<span data-ttu-id="8ac9c-152">條件式存取原則是一組規則，可指定要在什麼條件下評估和允許登入。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="8ac9c-153">例如，您可以建立敘述如下的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="8ac9c-154">如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="8ac9c-155">此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="8ac9c-156">您也可以使用條件式存取策略來使用進一步功能，例如要求特定 App 使用 MFA，或是在符合規範的裝置上完成該登錄，例如執行 Windows 10 的膝上型電腦。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="8ac9c-157">您從 Azure 入口網站中的 Azure AD 安全性窗格設定條件式存取策略。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![條件式存取功能表選項的圖片](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="8ac9c-159">您可以將條件式存取策略用於：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="8ac9c-160">Microsoft 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="8ac9c-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="8ac9c-161">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="8ac9c-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="8ac9c-162">Azure AD Premium P1 和 Azure AD Premium P2 授權</span><span class="sxs-lookup"><span data-stu-id="8ac9c-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="8ac9c-163">對於使用 Microsoft 365 商務進版小型企業，您可以利用下列步驟輕鬆使用條件式存取政策：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="8ac9c-164">建立群組以包含需要 MFA 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="8ac9c-165">啟用 **全域系統管理員的需要 MFA** 政策。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="8ac9c-166">使用這些設定建立以群組為基礎的條件式存取政策：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="8ac9c-167">指派>使用者和群組：上述步驟 1 的組名。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="8ac9c-168">指派>雲端 App 或動作：所有雲端 App。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="8ac9c-169">存取控制專案>授予>存取>需要多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="8ac9c-170">啟用該政策。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-170">Enable the policy.</span></span>
5. <span data-ttu-id="8ac9c-171">將使用者帳戶新增到上述步驟 1 中建立並測試的群組。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="8ac9c-172">若要要求其他使用者帳戶使用 MFA，請將其新增到步驟 1 中建立群組。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="8ac9c-173">此條件式存取政策可讓您以自己的步調將 MFA 需求推出給使用者。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="8ac9c-174">企業應該使用 [一般條件式存取策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) 來設定下列策略：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="8ac9c-175">要求系統管理員使用 MFA</span><span class="sxs-lookup"><span data-stu-id="8ac9c-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="8ac9c-176">要求所有使用者使用 MFA</span><span class="sxs-lookup"><span data-stu-id="8ac9c-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="8ac9c-177">封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="8ac9c-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="8ac9c-178">如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="8ac9c-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="8ac9c-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="8ac9c-180">使用 Azure AD 身分識別保護，您可以建立額外的條件式存取策略，在有中或高之登錄風險時要求[MFA。](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="8ac9c-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="8ac9c-181">您可以使用 Azure AD 身分識別保護與以風險為基礎的條件式存取策略，以執行：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="8ac9c-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8ac9c-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="8ac9c-183">Azure AD Premium P2 授權</span><span class="sxs-lookup"><span data-stu-id="8ac9c-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="8ac9c-184">如需詳細資訊，請參閱這個 [Azure AD Identity Protection 概觀](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="8ac9c-185">不建議使用舊版每個使用者 MFA (MFA) </span><span class="sxs-lookup"><span data-stu-id="8ac9c-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="8ac9c-186">您應該使用安全性預設值或條件式存取策略，要求使用者帳戶的登錄使用 MFA。不過，如果無法使用上述任一項，Microsoft 強烈建議擁有系統管理員角色的使用者帳戶使用 MFA，尤其是任何大小訂閱的全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="8ac9c-187">您從 Microsoft 365系統管理中心的使用中使用者窗格啟用個別使用者帳戶的 MFA。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![作用中使用者頁面上多重要素驗證選項的圖片](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="8ac9c-189">啟用後，下次使用者進行登錄時，系統會提示他們註冊 MFA，以及選擇並測試其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="8ac9c-190">共同使用這些方法</span><span class="sxs-lookup"><span data-stu-id="8ac9c-190">Using these methods together</span></span>

<span data-ttu-id="8ac9c-191">下表顯示啟用 MFA 與安全性預設、條件式存取原則和每一使用者帳戶設定的結果。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="8ac9c-192">Enabled</span><span class="sxs-lookup"><span data-stu-id="8ac9c-192">Enabled</span></span>|<span data-ttu-id="8ac9c-193">停用</span><span class="sxs-lookup"><span data-stu-id="8ac9c-193">Disabled</span></span>|<span data-ttu-id="8ac9c-194">次要驗證方法</span><span class="sxs-lookup"><span data-stu-id="8ac9c-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="8ac9c-195">**安全性預設**</span><span class="sxs-lookup"><span data-stu-id="8ac9c-195">**Security defaults**</span></span>|<span data-ttu-id="8ac9c-196">無法使用條件式存取策略</span><span class="sxs-lookup"><span data-stu-id="8ac9c-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="8ac9c-197">可以使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8ac9c-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="8ac9c-198">Microsoft Authenticator 應用程式</span><span class="sxs-lookup"><span data-stu-id="8ac9c-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="8ac9c-199">**條件式存取原則**</span><span class="sxs-lookup"><span data-stu-id="8ac9c-199">**Conditional Access policies**</span></span>|<span data-ttu-id="8ac9c-200">如果有任何啟用，您則無法啟用安全性預設值</span><span class="sxs-lookup"><span data-stu-id="8ac9c-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="8ac9c-201">如果已停用所有原則，則可啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="8ac9c-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="8ac9c-202">在註冊 MFA 期間由使用者指定</span><span class="sxs-lookup"><span data-stu-id="8ac9c-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="8ac9c-203">**不建議使用舊版每個使用者 MFA (MFA)**</span><span class="sxs-lookup"><span data-stu-id="8ac9c-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="8ac9c-204">會優先于安全性預設值和條件式存取策略，要求每一個登錄都使用 MFA</span><span class="sxs-lookup"><span data-stu-id="8ac9c-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="8ac9c-205">安全性預設值和條件式存取政策所覆蓋</span><span class="sxs-lookup"><span data-stu-id="8ac9c-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="8ac9c-206">在註冊 MFA 期間由使用者指定</span><span class="sxs-lookup"><span data-stu-id="8ac9c-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="8ac9c-207">如果已啟用安全性預設值，系統會提示所有新使用者進行 MFA 註冊，以及下一次使用 Microsoft Authenticator App。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="8ac9c-208">管理 MFA 設定的方法</span><span class="sxs-lookup"><span data-stu-id="8ac9c-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="8ac9c-209">管理 MFA 設定的方法有兩種。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="8ac9c-210">在 Azure 入口網站中，您可以：</span><span class="sxs-lookup"><span data-stu-id="8ac9c-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="8ac9c-211">啟用和停用安全性預設值</span><span class="sxs-lookup"><span data-stu-id="8ac9c-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="8ac9c-212">設定條件式存取策略</span><span class="sxs-lookup"><span data-stu-id="8ac9c-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="8ac9c-213">在 Microsoft 365 系統管理中心，您可以設定每個使用者和服務 MFA 設定。</span><span class="sxs-lookup"><span data-stu-id="8ac9c-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="8ac9c-214">您的下一個步驟</span><span class="sxs-lookup"><span data-stu-id="8ac9c-214">Your next step</span></span>

[<span data-ttu-id="8ac9c-215">設定 Microsoft 365 的 MFA</span><span class="sxs-lookup"><span data-stu-id="8ac9c-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)
