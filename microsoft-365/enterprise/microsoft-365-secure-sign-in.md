---
title: 保護 Microsoft 365 租用戶的使用者登入
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 規定使用者以多重要素驗證 (MFA) 和其他功能安全登入。
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132236"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="8130e-103">保護 Microsoft 365 租用戶的使用者登入</span><span class="sxs-lookup"><span data-stu-id="8130e-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="8130e-104">若要加強使用者登入的安全性：</span><span class="sxs-lookup"><span data-stu-id="8130e-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="8130e-105">使用 Azure Active Directory (Azure AD) 密碼保護</span><span class="sxs-lookup"><span data-stu-id="8130e-105">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="8130e-106">使用多重要素驗證 (MFA)</span><span class="sxs-lookup"><span data-stu-id="8130e-106">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="8130e-107">部署身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="8130e-107">Deploy identity and device access policies</span></span>

## <a name="azure-ad-password-protection"></a><span data-ttu-id="8130e-108">Azure AD 密碼保護</span><span class="sxs-lookup"><span data-stu-id="8130e-108">Azure AD Password Protection</span></span>

<span data-ttu-id="8130e-109">Azure AD 密碼保護可偵測並封鎖已知的弱式密碼及其變體，也會封鎖貴組織特有的額外弱式詞彙。</span><span class="sxs-lookup"><span data-stu-id="8130e-109">Azure AD Password Protection detects and blocks known weak passwords and their variants, and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="8130e-110">預設全域禁用密碼清單會自動套用至 Azure AD 租用戶中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="8130e-110">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="8130e-111">您可以在自訂禁用密碼清單中定義其他條目。</span><span class="sxs-lookup"><span data-stu-id="8130e-111">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="8130e-112">使用者變更或重設密碼時，系統會檢查這些禁用密碼清單，以強制使用強式密碼。</span><span class="sxs-lookup"><span data-stu-id="8130e-112">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="8130e-113">如需詳細資訊，請參閱[設定 Azure AD 密碼保護](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)。</span><span class="sxs-lookup"><span data-stu-id="8130e-113">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="8130e-114">MFA</span><span class="sxs-lookup"><span data-stu-id="8130e-114">MFA</span></span>

<span data-ttu-id="8130e-115">MFA 會要求使用者登入程序另外遵守使用者帳戶密碼以外的驗證規定。</span><span class="sxs-lookup"><span data-stu-id="8130e-115">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="8130e-116">惡意使用者即使確定了使用者帳戶的密碼，還必須能夠回應另外的驗證機制 (例如，傳送至智慧型手機的簡訊)，才能獲得存取權。</span><span class="sxs-lookup"><span data-stu-id="8130e-116">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正確的密碼加上其他驗證則可導致順利登入](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="8130e-118">使用 MFA 的第一步是***要求所有系統管理員帳戶 (亦即授權帳戶) 都使用 MFA***。</span><span class="sxs-lookup"><span data-stu-id="8130e-118">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="8130e-119">除了這個第一步，Microsoft 強烈建議要求所有使用者都使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="8130e-119">Beyond this first step, Microsoft strongly recommends MFA For all users.</span></span>

<span data-ttu-id="8130e-120">根據您的 Microsoft 365 方案，有三種方法可以要求系統管理員或使用者使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="8130e-120">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="8130e-121">方案</span><span class="sxs-lookup"><span data-stu-id="8130e-121">Plan</span></span> | <span data-ttu-id="8130e-122">建議</span><span class="sxs-lookup"><span data-stu-id="8130e-122">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="8130e-123">所有的 Microsoft 365 方案（不含 Azure AD Premium P1 或 P2 授權）</span><span class="sxs-lookup"><span data-stu-id="8130e-123">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="8130e-124">[在 Azure AD 中啟用安全性預設](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="8130e-124">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="8130e-125">Azure AD 中的安全性預設包含了適用於使用者和系統管理員的 MFA。</span><span class="sxs-lookup"><span data-stu-id="8130e-125">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="8130e-126">Microsoft 365 E3 （含 Azure AD Premium P1 授權）</span><span class="sxs-lookup"><span data-stu-id="8130e-126">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="8130e-127">使用[常見的條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)來設定下列原則：</span><span class="sxs-lookup"><span data-stu-id="8130e-127">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="8130e-128">- [要求系統管理員使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="8130e-128">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="8130e-129">- [要求所有使用者使用 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="8130e-129">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="8130e-130">- [封鎖舊版驗證](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="8130e-130">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="8130e-131">Microsoft 365 E5 （含 Azure AD Premium P2 授權）</span><span class="sxs-lookup"><span data-stu-id="8130e-131">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="8130e-132">利用 Azure AD Identity Protection，藉由建立下列兩種原則來開始實作 Microsoft [建議的一組條件式存取和相關原則](../enterprise/identity-access-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="8130e-132">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="8130e-133">- [登入風險為中或高時，需要 MFA](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="8130e-133">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="8130e-134">- [高風險使用者必須變更密碼](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="8130e-134">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="8130e-135">安全性預設</span><span class="sxs-lookup"><span data-stu-id="8130e-135">Security defaults</span></span>

<span data-ttu-id="8130e-136">安全性預設是 2019 年 10 月 21 日之後所建立 Microsoft 365 和 Office 365 付費或試用版訂用帳戶的新功能。</span><span class="sxs-lookup"><span data-stu-id="8130e-136">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="8130e-137">這些訂用帳戶會開啟安全性預設，而***要求所有使用者都必須使用 MFA 與 Microsoft Authenticator 應用程式***。</span><span class="sxs-lookup"><span data-stu-id="8130e-137">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="8130e-138">使用者有 14 天的時間可以從其智慧型手機向 Microsoft Authenticator 應用程式註冊 MFA，時間從啟用安全性預設後使用者首次登入時起算。</span><span class="sxs-lookup"><span data-stu-id="8130e-138">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="8130e-139">14 天過後，使用者就無法登入，除非其完成 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="8130e-139">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="8130e-140">安全性預設可確保所有組織都具備預設啟用的使用者登入基本層級安全性。</span><span class="sxs-lookup"><span data-stu-id="8130e-140">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="8130e-141">您可以停用安全性預設，改為使用 MFA 與條件式存取原則或改為使用個別帳戶。</span><span class="sxs-lookup"><span data-stu-id="8130e-141">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="8130e-142">如需詳細資訊，請參閱這個[安全性預設概觀](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="8130e-142">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="8130e-143">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8130e-143">Conditional Access policies</span></span>

<span data-ttu-id="8130e-144">條件式存取原則是一組規則，可指定要在什麼條件下評估登入以及授予存取權。</span><span class="sxs-lookup"><span data-stu-id="8130e-144">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="8130e-145">例如，您可以建立敘述如下的條件式存取原則：</span><span class="sxs-lookup"><span data-stu-id="8130e-145">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="8130e-146">如果使用者帳戶名稱是獲派 Exchange、使用者、密碼、安全性、SharePoint 或全域管理員角色的使用者群組成員，則先要求 MFA 再允許存取。</span><span class="sxs-lookup"><span data-stu-id="8130e-146">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="8130e-147">此原則可讓您根據群組成員資格要求 MFA，而不是在指派或取消指派這些管理員角色時，嘗試針對 MFA 設定個別使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8130e-147">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="8130e-148">您也可以使用條件式存取原則來執行更進階的功能，例如要求登入必須是來自符合規範的裝置 (例如執行 Windows 10 的膝上型電腦)。</span><span class="sxs-lookup"><span data-stu-id="8130e-148">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="8130e-149">[條件式存取] 需有 Azure AD Premium P1 授權，已附加在 Microsoft 365 E3 和 E5 套裝中。</span><span class="sxs-lookup"><span data-stu-id="8130e-149">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="8130e-150">如需詳細資訊，請參閱這個[條件式存取概觀](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="8130e-150">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="8130e-151">共同使用這些方法</span><span class="sxs-lookup"><span data-stu-id="8130e-151">Using these methods together</span></span>

<span data-ttu-id="8130e-152">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="8130e-152">Keep the following in mind:</span></span>

- <span data-ttu-id="8130e-153">如果您已啟用任何條件式存取原則，則無法啟用安全性預設。</span><span class="sxs-lookup"><span data-stu-id="8130e-153">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="8130e-154">如果您已啟用安全性預設，則無法啟用任何條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="8130e-154">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="8130e-155">如果已啟用安全性預設，系統會提示所有新使用者註冊 MFA 並使用 Microsoft Authenticator 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8130e-155">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="8130e-156">下表顯示啟用 MFA 與安全性預設和條件式存取原則的結果。</span><span class="sxs-lookup"><span data-stu-id="8130e-156">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="8130e-157">Method</span><span class="sxs-lookup"><span data-stu-id="8130e-157">Method</span></span> | <span data-ttu-id="8130e-158">啟用</span><span class="sxs-lookup"><span data-stu-id="8130e-158">Enabled</span></span> | <span data-ttu-id="8130e-159">停用</span><span class="sxs-lookup"><span data-stu-id="8130e-159">Disabled</span></span> | <span data-ttu-id="8130e-160">額外驗證方法</span><span class="sxs-lookup"><span data-stu-id="8130e-160">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="8130e-161">**安全性預設**</span><span class="sxs-lookup"><span data-stu-id="8130e-161">**Security defaults**</span></span>  | <span data-ttu-id="8130e-162">無法使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8130e-162">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="8130e-163">可以使用條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="8130e-163">Can use Conditional Access policies</span></span> | <span data-ttu-id="8130e-164">Microsoft Authenticator 應用程式</span><span class="sxs-lookup"><span data-stu-id="8130e-164">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="8130e-165">**條件式存取原則**</span><span class="sxs-lookup"><span data-stu-id="8130e-165">**Conditional Access policies**</span></span> | <span data-ttu-id="8130e-166">如果已啟用任何原則，則無法啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="8130e-166">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="8130e-167">如果已停用所有原則，則可啟用安全性預設</span><span class="sxs-lookup"><span data-stu-id="8130e-167">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="8130e-168">在 MFA 註冊期間由使用者指定</span><span class="sxs-lookup"><span data-stu-id="8130e-168">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-policies"></a><span data-ttu-id="8130e-169">身分識別與裝置存取原則</span><span class="sxs-lookup"><span data-stu-id="8130e-169">Identity and device access policies</span></span>

<span data-ttu-id="8130e-170">建議採用身分識別和裝置存取設定和原則這類先決條件功能，其設定結合了條件式存取、Intune 和 Azure Active Directory Identity Protection 原則，決定是否應授予特定存取權要求及其授予條件。</span><span class="sxs-lookup"><span data-stu-id="8130e-170">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="8130e-171">這項決定的依據是登入的使用者帳戶、使用的裝置、使用者存取時使用的應用程式、建立存取要求的位置，以及對要求的風險評估。</span><span class="sxs-lookup"><span data-stu-id="8130e-171">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="8130e-172">這項功能有助於確保，只有經核准的使用者與裝置才可存取重要的資源。</span><span class="sxs-lookup"><span data-stu-id="8130e-172">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="8130e-173">Azure AD Identity Protection 需要 Microsoft 365 E5 隨附的 Azure AD Premium P2 授權。</span><span class="sxs-lookup"><span data-stu-id="8130e-173">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="8130e-174">身分識別與裝置存取原則的定義為分三層使用：</span><span class="sxs-lookup"><span data-stu-id="8130e-174">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="8130e-175">對於存取您的應用程式和資料的身分識別和裝置，基準保護是安全性等級下限。</span><span class="sxs-lookup"><span data-stu-id="8130e-175">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="8130e-176">敏感性保護可為特定資料提供額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="8130e-176">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="8130e-177">身分識別和裝置的安全性層級與裝置健康情況需求較高。</span><span class="sxs-lookup"><span data-stu-id="8130e-177">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="8130e-178">包含高度管制或保密資料環境的防護，適合通常屬於高度保密、包含營業，或是受資料法規約束的少量資料。</span><span class="sxs-lookup"><span data-stu-id="8130e-178">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="8130e-179">身分識別和裝置的安全性層級與裝置健康情況需求高出許多。</span><span class="sxs-lookup"><span data-stu-id="8130e-179">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="8130e-180">這些層級及其對應的設定，可針對所有資料、身分識別和裝置，提供一致的保護層級。</span><span class="sxs-lookup"><span data-stu-id="8130e-180">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="8130e-181">Microsoft 強烈建議您在組織設定並推出身分識別和裝置存取原則，包括 Microsoft Teams、Exchange Online 和 SharePoint 專有的設定。</span><span class="sxs-lookup"><span data-stu-id="8130e-181">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="8130e-182">如需詳細資訊，請參閱[身分識別與裝置存取設定](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="8130e-182">For more information, see [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="8130e-183">適用於 MFA 和身分識別登入的系統管理員技術資源</span><span class="sxs-lookup"><span data-stu-id="8130e-183">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="8130e-184">Microsoft 365 適用的 MFA</span><span class="sxs-lookup"><span data-stu-id="8130e-184">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="8130e-185">Microsoft 365 的身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="8130e-185">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="8130e-186">Azure Academy Azure AD 訓練影片</span><span class="sxs-lookup"><span data-stu-id="8130e-186">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="8130e-187">設定 Azure Multi-Factor Authentication 註冊原則</span><span class="sxs-lookup"><span data-stu-id="8130e-187">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="8130e-188">身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="8130e-188">Identity and device access configurations</span></span>](microsoft-365-policies-configurations.md)

