---
title: 步驟 3：保護和管理您的使用者登入
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 您可以將使用者登入 Windows 裝置和 Microsoft 365 變得更安全。
ms.openlocfilehash: c541f5b74fe3ea6e94b002212f21ec8645e8e87e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633511"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a><span data-ttu-id="a30b5-103">步驟 3：保護和管理您的使用者登入</span><span class="sxs-lookup"><span data-stu-id="a30b5-103">Step 3: Secure and manage your user sign-ins</span></span>

![階段 2 - 身分識別](../media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a><span data-ttu-id="a30b5-105">使用 Windows Hello 企業版</span><span class="sxs-lookup"><span data-stu-id="a30b5-105">Use Windows Hello for Business</span></span>

<span data-ttu-id="a30b5-106">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a30b5-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="a30b5-107">Windows 10 企業版的 Windows Hello 企業版在登入 Windows 裝置時，會使用加強雙因素驗證取代密碼。</span><span class="sxs-lookup"><span data-stu-id="a30b5-107">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="a30b5-108">雙因素是一種新的使用者認證類型，可與裝置和生物特徵或 PIN 相繫結。</span><span class="sxs-lookup"><span data-stu-id="a30b5-108">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="a30b5-109">如需詳細資訊，請參閱 [ Windows Hello 企業版概觀](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-109">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a><span data-ttu-id="a30b5-110">設定 Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="a30b5-110">Set up Azure Multi-Factor Authentication</span></span>

<span data-ttu-id="a30b5-111">*此為選用步驟，且同時適用於 Microsoft 365 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a30b5-111">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="a30b5-112">在這個步驟，您將設定 Azure Multi-Factor Authentication (MFA)，為使用者登入和交易添加第二層安全性。</span><span class="sxs-lookup"><span data-stu-id="a30b5-112">In this step, you'll set up Azure Multi-Factor Authentication (MFA) to add a second layer of security to user sign-ins and transactions.</span></span> <span data-ttu-id="a30b5-113">MFA 在使用者正確輸入其密碼之後，還會需要其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="a30b5-113">MFA requires an additional verification method after users have correctly entered their password.</span></span> <span data-ttu-id="a30b5-114">沒有 MFA，密碼就是唯一的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="a30b5-114">Without MFA, the password is the only verification method.</span></span> <span data-ttu-id="a30b5-115">但密碼的問題在於，許多密碼很容易被攻擊者猜測，或在不知情的情況下分享給不受信任的一方。</span><span class="sxs-lookup"><span data-stu-id="a30b5-115">The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="a30b5-116">透過 MFA，第二層安全性可以是：</span><span class="sxs-lookup"><span data-stu-id="a30b5-116">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="a30b5-117">不容易遭到偽造或重複的個人和受信任裝置 (例如智慧型手機)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-117">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="a30b5-118">生物識別屬性 (例如指紋)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-118">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="a30b5-119">您將啟用 MFA 並使用[條件式存取原則](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)來設定次要驗證方法，這會允許您使用 Azure Active Directory (Azure AD) 群組來將 MFA 向指定的一組使用者 (例如試驗使用者、地理位置或部門) 推出。</span><span class="sxs-lookup"><span data-stu-id="a30b5-119">You'll enable MFA and configure the secondary authentication method with [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), which allow you to use Azure Active Directory (Azure AD) groups to roll out MFA to specified sets of users, such as pilot users, geographical regions, or departments.</span></span> <span data-ttu-id="a30b5-120">請務必讓使用者知道即將啟用 MFA，使得他們了解需求 (例如強制使用智慧型手機登入) 並能順利登入。</span><span class="sxs-lookup"><span data-stu-id="a30b5-120">Make sure to let your users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span> 

<span data-ttu-id="a30b5-121">如需更多資訊，請參閱 [規劃雲端式 Azure Multi-Factor Authentication 部署](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-121">For more information, see [Planning a cloud-based Azure Multi-Factor Authentication deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a30b5-123">測試實驗室指南：Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="a30b5-123">Test Lab Guide: Azure Multi-Factor Authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="a30b5-124">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-mfa)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="a30b5-125">防護認證洩露</span><span class="sxs-lookup"><span data-stu-id="a30b5-125">Protect against credential compromise</span></span>

<span data-ttu-id="a30b5-126">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="a30b5-126">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="a30b5-127">在這一節中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。</span><span class="sxs-lookup"><span data-stu-id="a30b5-127">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="a30b5-128">Azure AD 身分識別保護提供多種方法，可協助防止攻擊者危及使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="a30b5-128">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="a30b5-129">使用 Azure AD Identity Protection，您可以：</span><span class="sxs-lookup"><span data-stu-id="a30b5-129">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="a30b5-130">判斷並處理組織身分識別中潛在的弱點</span><span class="sxs-lookup"><span data-stu-id="a30b5-130">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="a30b5-131">Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。</span><span class="sxs-lookup"><span data-stu-id="a30b5-131">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="a30b5-132">Azure AD Identity Protection 可使用此資料來產生報告和警示，協助您評估問題及採取行動。</span><span class="sxs-lookup"><span data-stu-id="a30b5-132">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="a30b5-133">偵測與組織身分識別相關的可疑活動，並自動進行回應處理</span><span class="sxs-lookup"><span data-stu-id="a30b5-133">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="a30b5-134">您可以設定以風險為基礎的原則，當達到指定風險層級時自動回應偵測到的問題。</span><span class="sxs-lookup"><span data-stu-id="a30b5-134">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="a30b5-135">除了由 Azure AD 和 Microsoft Intune 提供的其他條件式存取控制項之外，這些原則還可以自動封鎖存取權，或採取更正動作，包括密碼重設以及對後續登入要求 Azure Multi-Factor Authentication。</span><span class="sxs-lookup"><span data-stu-id="a30b5-135">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="a30b5-136">調查可疑事件，並使用系統管理動作加以解決</span><span class="sxs-lookup"><span data-stu-id="a30b5-136">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="a30b5-p107">您可以使用安全性事件的相關資訊來調查風險事件。基本工作流程可用於追蹤調查及啟動修復動作，例如密碼重設。</span><span class="sxs-lookup"><span data-stu-id="a30b5-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="a30b5-139">請參閱 [Azure AD Identity Protection 的相關詳細資訊](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-139">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="a30b5-140">請參閱[啟用 Azure AD Identity Protection 的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-140">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="a30b5-141">此步驟的結果會是您已啟用 Azure AD Identity Protection，並將其用於：</span><span class="sxs-lookup"><span data-stu-id="a30b5-141">The results of this step are that you've enabled Azure AD Identity Protection and you are using it to:</span></span>

- <span data-ttu-id="a30b5-142">解決潛在的身分識別弱點。</span><span class="sxs-lookup"><span data-stu-id="a30b5-142">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="a30b5-143">偵測可能的認證洩露嘗試。</span><span class="sxs-lookup"><span data-stu-id="a30b5-143">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="a30b5-144">調查並解決持續的可疑身分識別事件。</span><span class="sxs-lookup"><span data-stu-id="a30b5-144">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a30b5-146">測試實驗室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="a30b5-146">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="a30b5-147">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="a30b5-147">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

|||
|:-------|:-----|
|![步驟 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="a30b5-149">新增使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="a30b5-149">Add your user accounts</span></span>](identity-add-user-accounts.md) |
