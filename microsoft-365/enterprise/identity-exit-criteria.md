---
title: 階段 2：識別基礎結構允出準則
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
description: 請確定您的設定符合 Microsoft 365 企業版準則，是否具備以識別為基礎的服務和基礎結構。
ms.openlocfilehash: 94343400482083b2e793ff218816f06cb982187e
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627389"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="bb01c-103">階段 2：識別基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="bb01c-103">Phase 2: Identity infrastructure exit criteria</span></span>

![階段 2 - 身分識別](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="bb01c-105">請確定您的身分識別基礎結構符合下列必要準則，而且您已將這些視為選擇性準則。</span><span class="sxs-lookup"><span data-stu-id="bb01c-105">Make sure your identity infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<span data-ttu-id="bb01c-106">若需身分識別基礎架構的其他建議，另請參閱「[先決條件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)」。</span><span class="sxs-lookup"><span data-stu-id="bb01c-106">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="bb01c-107">必要：全域系統管理員帳戶會受到保護</span><span class="sxs-lookup"><span data-stu-id="bb01c-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="bb01c-108">您已[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)，以防止攻擊者所進行、可能導致違反您的 Microsoft 365 訂閱的認證洩露。</span><span class="sxs-lookup"><span data-stu-id="bb01c-108">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="bb01c-109">如果您略過這項要求，全域系統管理員帳戶可能會受到攻擊和洩露，讓攻擊者可以取得對您資料的系統範圍存取權，來進行蒐集、損毀，或要求贖金。</span><span class="sxs-lookup"><span data-stu-id="bb01c-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="bb01c-110">如有需要，[步驟 1](identity-create-protect-global-admins.md#identity-global-admin) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="bb01c-110">If needed, [Step 1](identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-111">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-111">How to test</span></span>

<span data-ttu-id="bb01c-112">使用這些步驟來確認您已受保護全域系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="bb01c-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="bb01c-113">在 PowerShell 命令提示字元執行以下 Azure Active Directory PowerShell 的圖表。</span><span class="sxs-lookup"><span data-stu-id="bb01c-113">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="bb01c-114">您應該只會看到專用全域系統管理員帳戶清單。</span><span class="sxs-lookup"><span data-stu-id="bb01c-114">You should see only the list of dedicated global administrator accounts.</span></span>
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="bb01c-115">使用步驟 1 中的每個帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bb01c-115">Sign in to Office 365 using each of the accounts from step 1.</span></span> <span data-ttu-id="bb01c-116">每個登入必須要求 Azure Multi-Factor Authentication 和您組織中可用的最強型次要驗證。</span><span class="sxs-lookup"><span data-stu-id="bb01c-116">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="bb01c-117">請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)，以取得安裝 Azure Active Directory PowerShell for Graph 模組及登入 Office 365 的指示。</span><span class="sxs-lookup"><span data-stu-id="bb01c-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="bb01c-118">選用：您已設定特殊權限的身分識別管理來支援全域系統管理員角色的隨選指派</span><span class="sxs-lookup"><span data-stu-id="bb01c-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="bb01c-119">您已使用[設定 Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) 中的指示，啟用 Azure AD 租用戶中的 PIM 並將您的全域系統管理員帳戶設定為合格的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="bb01c-119">You've used the instructions in [Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="bb01c-120">您也使用「[保護 Azure AD 中混合式和雲端部署的特殊存取權](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」中的建議，以開發可保護特殊存取權避免受到網路攻擊的藍圖。</span><span class="sxs-lookup"><span data-stu-id="bb01c-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="bb01c-121">如果您略過此選項時，全域系統管理員帳戶可能會受到持續線上攻擊，且機密資訊洩露時，可能會讓攻擊者蒐集、損毀，或保留您的機密資訊，以勒索贖金。</span><span class="sxs-lookup"><span data-stu-id="bb01c-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="bb01c-122">如有需要，[步驟 1](identity-create-protect-global-admins.md#identity-pim) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-122">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="bb01c-123">選用：您擁有在 Office 365 中設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="bb01c-123">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="bb01c-124">您已使用[在 Office 365 中設定特殊存取權限管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主題中的資訊來啟用特殊存取權限，並在組織中建立一個或多個特殊存取權限原則。</span><span class="sxs-lookup"><span data-stu-id="bb01c-124">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="bb01c-125">您已設定這些原則，並且啟用了即時存取，以存取敏感資料或存取關鍵配置設定。</span><span class="sxs-lookup"><span data-stu-id="bb01c-125">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="bb01c-126">如有需要，[步驟 1](identity-create-protect-global-admins.md#identity-pam) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="bb01c-126">If needed, [Step 1](identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="bb01c-127">選用：Azure AD 密碼保護禁止使用弱式密碼</span><span class="sxs-lookup"><span data-stu-id="bb01c-127">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="bb01c-128">您已[在雲端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)啟用禁止使用錯誤密碼，以及為您的[內部部署 Active Directory 網域服務 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) 啟用全域禁止密碼以及選用的自訂字詞。</span><span class="sxs-lookup"><span data-stu-id="bb01c-128">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="bb01c-129">如有需要，[步驟 2](identity-secure-your-passwords.md#identity-password-prot) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-129">If needed, [Step 2](identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="bb01c-130">選用：使用者可以重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="bb01c-130">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="bb01c-131">您已使用 [Azure AD 自助密碼重設快速部署](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)來為您的使用者設定密碼重設。</span><span class="sxs-lookup"><span data-stu-id="bb01c-131">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="bb01c-132">如果您不符合此條件，使用者將依賴使用者帳戶的系統管理員重設密碼，造成其他 IT 系統管理員的負擔。</span><span class="sxs-lookup"><span data-stu-id="bb01c-132">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="bb01c-133">如有需要，[步驟 2](identity-secure-your-passwords.md#identity-pw-reset) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-133">If needed, [Step 2](identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="bb01c-134">選用：使用者可以使用 Azure AD 無縫單一登入來進行登入</span><span class="sxs-lookup"><span data-stu-id="bb01c-134">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="bb01c-135">您可以為您組織啟用 [Azure AD Connect：隨選即用單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)，以簡化使用者登入以雲端為基礎之應用程式 (例如 Office 365) 的方式。</span><span class="sxs-lookup"><span data-stu-id="bb01c-135">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="bb01c-136">如果您略過此選項，使用者在存取使用您 Azure AD 租用戶的其他應用程式時可能會收到提示，要求他們提供認證。</span><span class="sxs-lookup"><span data-stu-id="bb01c-136">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use you Azure AD tenant.</span></span>

<span data-ttu-id="bb01c-137">如有需要，[步驟 2](identity-secure-your-passwords.md#identity-sso) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-137">If needed, [Step 2](identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="bb01c-138">選用：已個人化您組織的 Office 365 登入畫面</span><span class="sxs-lookup"><span data-stu-id="bb01c-138">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="bb01c-139">您已使用「[將公司商標新增至登入及存取面板頁面](https://aka.ms/aadpaddbranding)」來將貴組織的商標新增至 Office 365 登入頁面。</span><span class="sxs-lookup"><span data-stu-id="bb01c-139">You have used [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="bb01c-140">如果您略過此選項，使用者會看到一般的 Office 365 登入畫面，並且可能無法確定它們登入的是貴組織的網站。</span><span class="sxs-lookup"><span data-stu-id="bb01c-140">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="bb01c-141">如有需要，[步驟 2](identity-secure-your-passwords.md#identity-custom-sign-in) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-141">If needed, [Step 2](identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="bb01c-142">選用：已為使用者啟用 Azure Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="bb01c-142">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="bb01c-143">您已使用[規劃 Azure Multi-Factor Authentication ](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)和[條件式存取原則](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)，為您的使用者帳戶啟用 Azure Multi-Factor Authentication (MFA)。</span><span class="sxs-lookup"><span data-stu-id="bb01c-143">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="bb01c-p104">如果您略過此選項，使用者帳戶會容易遭到網路攻擊所引起的認證洩露。若使用者帳戶的密碼洩露時，帳戶的所有資源和功能 (例如系統管理員角色) 皆可供攻擊者使用。這可讓攻擊者複製、損毀，或保留內部文件和其他資料以勒索贖金。</span><span class="sxs-lookup"><span data-stu-id="bb01c-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="bb01c-147">如有需要，[步驟 3](identity-secure-user-sign-ins.md#identity-mfa) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-147">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-148">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-148">How to test</span></span>

1.  <span data-ttu-id="bb01c-149">建立測試使用者帳戶，並為他們指派授權。</span><span class="sxs-lookup"><span data-stu-id="bb01c-149">Create a test user account and assign them a license.</span></span> 
2.  <span data-ttu-id="bb01c-150">使用您為實際使用者帳戶使用的其他驗證方法 (例如將簡訊傳送到您的電話)，來為測試使用者帳戶設定 Azure Multi-Factor Authentication。</span><span class="sxs-lookup"><span data-stu-id="bb01c-150">Configure Azure Multi-Factor Authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a text message to your phone.</span></span> 
3.  <span data-ttu-id="bb01c-151">以測試使用者帳戶登入 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="bb01c-151">Sign in to the Office 36 portal with the test user account.</span></span>
4.  <span data-ttu-id="bb01c-152">請確認 MFA 會提示您輸入其他的驗證資訊，且結果為驗證成功。</span><span class="sxs-lookup"><span data-stu-id="bb01c-152">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="bb01c-153">刪除測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-153">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="bb01c-154">選用：已啟用 Azure AD Identity Protection 來防止認證洩露 (僅限 Microsoft 365 企業版 E5)</span><span class="sxs-lookup"><span data-stu-id="bb01c-154">Optional: Azure AD Identity Protection is enabled to protect against credential compromise (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="bb01c-155">您已啟用 Azure AD Identity Protection 來：</span><span class="sxs-lookup"><span data-stu-id="bb01c-155">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="bb01c-156">解決潛在的身分識別弱點。</span><span class="sxs-lookup"><span data-stu-id="bb01c-156">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="bb01c-157">偵測可能的認證洩露嘗試。</span><span class="sxs-lookup"><span data-stu-id="bb01c-157">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="bb01c-158">調查並解決持續的可疑身分識別事件。</span><span class="sxs-lookup"><span data-stu-id="bb01c-158">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="bb01c-p105">如果您略過此選項，您將無法偵測或自動抵禦認證洩露嘗試或調查與身分識別相關的安全性事件。這可能會使您的組織憑證洩露並對貴組織的機密資料產生威脅。</span><span class="sxs-lookup"><span data-stu-id="bb01c-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="bb01c-161">如有需要，[步驟 3](identity-secure-user-sign-ins.md#identity-ident-prot) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-161">If needed, [Step 3](identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="bb01c-162">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-162">How to test</span></span>

1. <span data-ttu-id="bb01c-163">使用初始密碼建立測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-163">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="bb01c-164">使用「[讓使用者在 Office 365 中重設其自身密碼](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords)」中的步驟來重設對測試使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="bb01c-164">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="bb01c-165">登出，然後再使用重設密碼登入測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-165">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="bb01c-166">刪除測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-166">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="bb01c-167">混合式身分識別的必要：使用者和群組會與 Azure AD 同步處理</span><span class="sxs-lookup"><span data-stu-id="bb01c-167">Required for hybrid identity: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="bb01c-168">如果您有現有的內部部署 Active Directory Domain Services (AD DS)，表示您已使用 Azure AD Connect 將內部部署 AD DS 內的使用者帳戶和群組同步處理到 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-168">If you have an existing on-premises Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises AD DS to your Azure AD tenant.</span></span>

<span data-ttu-id="bb01c-169">隨著將目錄同步處理，使用者可以使用他們用來登入電腦和存取內部部署資源所用的相同認證來登入 Office 365 和其他 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="bb01c-169">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="bb01c-170">如有需要，[步驟 4](identity-add-user-accounts.md#identity-sync) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="bb01c-170">If needed, [Step 4](identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="bb01c-171">如果您略過這項要求，您將有兩組使用者帳戶和群組：</span><span class="sxs-lookup"><span data-stu-id="bb01c-171">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="bb01c-172">在您內部部署 AD DS 中存在的使用者帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="bb01c-172">User accounts and groups that exist in your on-premises AD DS</span></span>
- <span data-ttu-id="bb01c-173">Azure AD 租用戶中存在的使用者帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="bb01c-173">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="bb01c-p106">在此狀態中，IT 系統管理員和使用者都必須以手動方式維護這兩組使用者帳戶和群組。這難免會導致帳戶、密碼及群組不同步。</span><span class="sxs-lookup"><span data-stu-id="bb01c-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-176">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-176">How to test</span></span>
<span data-ttu-id="bb01c-177">若要確認與內部部署認證的驗證運作正常，使用您的內部部署認證登入 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="bb01c-177">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="bb01c-178">若要確認目錄同步處理是否正常運作，請執行以下動作：</span><span class="sxs-lookup"><span data-stu-id="bb01c-178">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="bb01c-179">在 AD DS 中建立新的測試群組。</span><span class="sxs-lookup"><span data-stu-id="bb01c-179">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="bb01c-180">等待同步處理的時間。</span><span class="sxs-lookup"><span data-stu-id="bb01c-180">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="bb01c-181">檢查您的 Azure AD 租用戶以確認新測試群組名稱是否出現。</span><span class="sxs-lookup"><span data-stu-id="bb01c-181">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="bb01c-182">選用：目錄同步處理已受到監控</span><span class="sxs-lookup"><span data-stu-id="bb01c-182">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="bb01c-183">您已使用 [Azure AD Connect Health 同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (適用於密碼同步處理) 或[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (適用於同盟驗證) 並已部署 Azure AD Connect Health，其中包括：</span><span class="sxs-lookup"><span data-stu-id="bb01c-183">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="bb01c-184">在每個內部部署身分識別伺服器上安裝 Azure AD Connect Health 代理程式。</span><span class="sxs-lookup"><span data-stu-id="bb01c-184">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="bb01c-185">使用 Azure AD Connect Health 入口網站來監控正在進行的同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="bb01c-185">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="bb01c-186">如果您略過此選項時，則可以更精確地評估以雲端為基礎的身分識別基礎結構之狀態。</span><span class="sxs-lookup"><span data-stu-id="bb01c-186">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="bb01c-187">如有需要，[步驟 4](identity-add-user-accounts.md#identity-sync-health) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-187">If needed, [Step 4](identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-188">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-188">How to test</span></span>
<span data-ttu-id="bb01c-189">Azure AD Connect Health 入口網站會顯示您內部部署網域控制站和進行中同步處理的目前和正確狀態。</span><span class="sxs-lookup"><span data-stu-id="bb01c-189">The Azure AD Connect Health portal shows the current and correct state of your on-premises domain controllers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="bb01c-190">選用：已為您的使用者啟用密碼回寫</span><span class="sxs-lookup"><span data-stu-id="bb01c-190">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="bb01c-191">您已使用在「[具密碼回寫的 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」中的指示，為您 Microsoft 365 企業版訂閱的 Azure AD 租用戶啟用密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="bb01c-191">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="bb01c-192">如果您略過此選項，未連線到內部部署網路的使用者必須透過 IT 系統管理員，才能重設或解除鎖定 AD DS 密碼。</span><span class="sxs-lookup"><span data-stu-id="bb01c-192">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="bb01c-193">如有需要，[步驟 4](identity-add-user-accounts.md#identity-pw-writeback) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-193">If needed, [Step 4](identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="bb01c-194">若要充分利用 Azure AD Identity Protection 功能 (例如當 Azure AD 已偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，則需要密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="bb01c-194">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-195">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-195">How to test</span></span>

<span data-ttu-id="bb01c-196">您可藉由在 Office 365 中變更您的密碼來測試密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="bb01c-196">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="bb01c-197">您應該能夠使用自己的帳戶和新密碼來存取內部部署 AD DS 資源。</span><span class="sxs-lookup"><span data-stu-id="bb01c-197">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="bb01c-198">在內部部署 AD DS 中建立測試使用者帳戶、允許進行目錄同步處理，然後在 Microsoft 365 系統管理中心將 Microsoft 365 企業版授權授予該帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-198">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it a Microsoft 365 Enterprise license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="bb01c-199">透過加入您內部部署 AD DS 網域的遠端電腦，使用測試使用者帳戶的認證來登入電腦與 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="bb01c-199">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="bb01c-200">選取 [設定] > [Office 365 設定] > [密碼] > [變更密碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb01c-200">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="bb01c-201">輸入目前的密碼並輸入新密碼，然後加以確認。</span><span class="sxs-lookup"><span data-stu-id="bb01c-201">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="bb01c-202">登出 Office 入口網站與遠端電腦，然後使用測試使用者帳戶與新密碼登入電腦。</span><span class="sxs-lookup"><span data-stu-id="bb01c-202">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="bb01c-203">這證明您可以使用 Azure AD 租用戶來變更內部部署 AD DS 使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="bb01c-203">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-204">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-204">How to test</span></span>

<span data-ttu-id="bb01c-205">使用您的使用者帳戶名稱和 Azure Multi-Factor Authentication.登入 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="bb01c-205">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="bb01c-206">您應該會在登入頁面上看到您的自訂商標元素。</span><span class="sxs-lookup"><span data-stu-id="bb01c-206">You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="bb01c-207">選用：已啟用特定 Azure AD 的安全性和 Office 365 群組的自助群組管理</span><span class="sxs-lookup"><span data-stu-id="bb01c-207">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="bb01c-208">您已決定哪些群組適用於自助管理，指示其擁有者關於群組管理工作流程和責任，並為這些群組[設定 Azure AD 中的自助管理](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="bb01c-208">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="bb01c-209">如果您略過此選項時，所有 Azure AD 群組管理工作必須由 IT 系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="bb01c-209">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="bb01c-210">如有需要，[步驟 5](identity-use-group-management.md#identity-self-service-groups) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-210">If needed, [Step 5](identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-211">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-211">How to test</span></span>
1.  <span data-ttu-id="bb01c-212">使用 Azure 入口網站在 Azure AD 中建立測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-212">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="bb01c-213">使用測試使用者帳戶登入並建立測試 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="bb01c-213">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="bb01c-214">登出，然後使用您的 IT 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="bb01c-214">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="bb01c-215">為測試使用者帳戶設定自助管理的測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="bb01c-215">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="bb01c-216">登出，然後使用您的測試使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="bb01c-216">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="bb01c-217">使用 Azure 入口網站以將成員新增至測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="bb01c-217">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="bb01c-218">刪除測試安全性群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-218">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="bb01c-219">選用：動態群組成員資格設定會根據使用者帳戶屬性，自動將使用者帳戶新增至群組</span><span class="sxs-lookup"><span data-stu-id="bb01c-219">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="bb01c-220">您已決定一組 Azure AD 動態群組，並使用「[Azure Active Directory 中的以屬性為基礎的動態群組成員資格](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」中的指示來建立群組與規則，以便判斷適用於群組成員資格的一組使用者帳戶屬性和值。</span><span class="sxs-lookup"><span data-stu-id="bb01c-220">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="bb01c-p110">如果您略過此選項時，必須以手動方式完成群組成員資格，因為已新增數個帳戶或使用者帳戶屬性隨著時間而變更。比方說，如果有人從銷售部門調到會計部門時，您必須：</span><span class="sxs-lookup"><span data-stu-id="bb01c-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="bb01c-223">更新該使用者帳戶的部門屬性值。</span><span class="sxs-lookup"><span data-stu-id="bb01c-223">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="bb01c-224">手動將它們從銷售群組中移除。</span><span class="sxs-lookup"><span data-stu-id="bb01c-224">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="bb01c-225">手動將它們新增至會計群組。</span><span class="sxs-lookup"><span data-stu-id="bb01c-225">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="bb01c-226">如果銷售和會計群組是動態的，您只需要變更使用者帳戶的部門值。</span><span class="sxs-lookup"><span data-stu-id="bb01c-226">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="bb01c-227">如有需要，[步驟 5](identity-use-group-management.md#identity-dyn-groups) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-227">If needed, [Step 5](identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-228">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-228">How to test</span></span>

1. <span data-ttu-id="bb01c-229">使用 Azure 入口網站在 Azure AD 中建立測試動態群組並設定部門等於「test1」的規則。</span><span class="sxs-lookup"><span data-stu-id="bb01c-229">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="bb01c-230">在 Azure AD 中建立測試使用者帳戶，並將部門屬性設定為「test1」。</span><span class="sxs-lookup"><span data-stu-id="bb01c-230">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="bb01c-231">檢查使用者帳戶的內容，以確定它成為測試動態群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bb01c-231">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="bb01c-232">將測試使用者帳戶的部門屬性值變為「test2」。</span><span class="sxs-lookup"><span data-stu-id="bb01c-232">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="bb01c-233">檢查使用者帳戶的內容，以確定它不再是測試動態群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bb01c-233">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="bb01c-234">刪除測試動態群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-234">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="bb01c-235">選用：以群組為基礎的授權會根據群組成員資格，自動將授權指派至使用者帳戶和將其移除</span><span class="sxs-lookup"><span data-stu-id="bb01c-235">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="bb01c-236">您已為適當的 Azure AD 安全性群組[啟用以群組為基礎的授權](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)，因此系統會自動指派或取消指派您的 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="bb01c-236">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that your Microsoft 365 Enterprise licenses are automatically assigned or unassigned.</span></span>

<span data-ttu-id="bb01c-237">若您略過此選項，您必須手動進行以下動作：</span><span class="sxs-lookup"><span data-stu-id="bb01c-237">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="bb01c-238">將授權指派給您想要提供存取權的新使用者。</span><span class="sxs-lookup"><span data-stu-id="bb01c-238">Assign licenses to new users whom you intend to have access.</span></span>
- <span data-ttu-id="bb01c-239">從已不在您組織內或不需要存取權的使用者取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="bb01c-239">Unassign licenses from users who are no longer with your organization or do not have access.</span></span>

<span data-ttu-id="bb01c-240">如有需要，[步驟 5](identity-use-group-management.md#identity-group-license) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-240">If needed, [Step 5](identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="bb01c-241">如何測試</span><span class="sxs-lookup"><span data-stu-id="bb01c-241">How to test</span></span>

1. <span data-ttu-id="bb01c-242">在 Azure AD 中使用 Azure 入口網站建立測試安全性群組，並設定以群組為基礎的授權，以指派 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="bb01c-242">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Microsoft 365 Enterprise license.</span></span>
2. <span data-ttu-id="bb01c-243">在 Azure AD 中建立測試使用者帳戶，並將它新增到測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="bb01c-243">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="bb01c-244">在 Microsoft 365 系統管理中心中檢查使用者帳戶的內容，以確定其已獲指派 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="bb01c-244">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Microsoft 365 Enterprise license.</span></span>
4. <span data-ttu-id="bb01c-245">將測試使用者帳戶從測試安全性群組中移除。</span><span class="sxs-lookup"><span data-stu-id="bb01c-245">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="bb01c-246">檢查使用者帳戶內容，以確定其不再獲指派 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="bb01c-246">Examine the properties of the user account to ensure that it no longer has the Microsoft 365 Enterprise license assigned.</span></span>
6. <span data-ttu-id="bb01c-247">刪除測試安全性群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bb01c-247">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="bb01c-248">選用：已設定存取權檢閱並用來監控存取權</span><span class="sxs-lookup"><span data-stu-id="bb01c-248">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="bb01c-249">您已使用這些文章來設定不同類型的存取權檢閱，以監控群組成員資格、對企業應用程式的存取權及角色指派：</span><span class="sxs-lookup"><span data-stu-id="bb01c-249">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="bb01c-250">群組和應用程式</span><span class="sxs-lookup"><span data-stu-id="bb01c-250">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="bb01c-251">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="bb01c-251">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="bb01c-252">Azure 資源角色</span><span class="sxs-lookup"><span data-stu-id="bb01c-252">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="bb01c-253">如有需要，[步驟 6](identity-configure-identity-governance.md#identity-access-reviews) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="bb01c-253">If needed, [Step 6](identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>


## <a name="results-and-next-steps"></a><span data-ttu-id="bb01c-254">結果和後續步驟</span><span class="sxs-lookup"><span data-stu-id="bb01c-254">Results and next steps</span></span>

<span data-ttu-id="bb01c-255">您在 Microsoft 365 雲端的身分識別基礎結構會使用強大的驗證、受保護的系統管理員帳戶，以及簡化的使用者存取和管理。</span><span class="sxs-lookup"><span data-stu-id="bb01c-255">Your identity infrastructure in the Microsoft 365 cloud uses strong authentication, protected administrator accounts, and simplified user access and management.</span></span>

|||
|:-------|:-----|
|![階段 3：Windows 10 企業版](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="bb01c-257">如果您會遵循 Microsoft 365 企業版的端對端部署階段，則下一個階段是 [Windows 10 企業版](windows10-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="bb01c-257">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

