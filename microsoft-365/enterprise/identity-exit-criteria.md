---
title: 階段 2：識別基礎結構允出準則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 請確定您的設定符合 Microsoft 365 企業版準則，是否具備以識別為基礎的服務和基礎結構。
ms.openlocfilehash: 49ba7801b740b2a1cfd77955517646ee80174712
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866723"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a><span data-ttu-id="7a468-103">階段 2：識別基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="7a468-103">Phase 2: Identity infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="7a468-p101">在您進行階段 3 之前，請確認您的身分識別基礎結構符合這些條件。另請參閱[先決條件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)以了解對身分識別基礎結構的其他建議。</span><span class="sxs-lookup"><span data-stu-id="7a468-p101">Before you move on to Phase 3, make sure that your identity infrastructure meets these conditions. Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="7a468-106">必要：所有的使用者、群組和群組成員資格均已建立</span><span class="sxs-lookup"><span data-stu-id="7a468-106">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="7a468-107">您已建立使用者帳戶和群組，因此：</span><span class="sxs-lookup"><span data-stu-id="7a468-107">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="7a468-108">貴組織的員工和與貴組織合作的廠商、承包商及合作夥伴擁有在 Azure Active Directory (AD) 中相對應的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-108">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (AD).</span></span>
- <span data-ttu-id="7a468-109">Azure AD 群組和其成員包含適用於各種目的使用者帳戶和其他群組 (例如 Microsoft 雲端服務的安全性設定佈建、自動授權，與其他使用)。</span><span class="sxs-lookup"><span data-stu-id="7a468-109">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="7a468-110">如有需要，[步驟 1](identity-plan-users-groups.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="7a468-110">If needed, [Step 1](identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="7a468-111">必要：使用者和群組會與 Azure AD 同步處理</span><span class="sxs-lookup"><span data-stu-id="7a468-111">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="7a468-112">如果您有現有內部部署身分識別提供者 (例如 Windows Server Active Directory (AD))，您已使用 Azure AD Connect 以將從內部部署身分識別提供者的使用者帳戶和群組同步處理到 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-112">If you have an existing on-premises identity provider, such as Windows Server Active Directory (AD), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="7a468-113">隨著將目錄同步處理，使用者可以使用他們用來登入電腦和存取內部部署資源所用的相同認證來登入 Office 365 和其他 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="7a468-113">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="7a468-114">如有需要，[步驟 7](identity-azure-ad-connect.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="7a468-114">If needed, [Step 7](identity-azure-ad-connect.md) can help you meet this requirement.</span></span>

<span data-ttu-id="7a468-115">如果您略過這項要求，您將有兩組使用者帳戶和群組：</span><span class="sxs-lookup"><span data-stu-id="7a468-115">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="7a468-116">在您內部部署身分識別提供者中存在的使用者帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="7a468-116">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="7a468-117">Azure AD 租用戶中存在的使用者帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="7a468-117">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="7a468-p102">在此狀態中，IT 系統管理員和使用者都必須以手動方式維護這兩組使用者帳戶和群組。這難免會導致帳戶、密碼及群組不同步。</span><span class="sxs-lookup"><span data-stu-id="7a468-p102">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-120">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-120">How to test</span></span>
<span data-ttu-id="7a468-121">若要確認與內部部署認證的驗證運作正常，使用您的內部部署認證登入 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="7a468-121">To verify that authentication with on-premises credentials works correctly, sign in to the Office 365 portal with your on-premises credentials.</span></span>

<span data-ttu-id="7a468-122">若要確認目錄同步處理是否運作正常，請執行以下動作：</span><span class="sxs-lookup"><span data-stu-id="7a468-122">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="7a468-123">在 Windows Server AD 中建立新測試群組。</span><span class="sxs-lookup"><span data-stu-id="7a468-123">Create a new test group in Windows Server AD.</span></span>
2.  <span data-ttu-id="7a468-124">等待同步處理的時間。</span><span class="sxs-lookup"><span data-stu-id="7a468-124">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="7a468-125">檢查您的 Azure AD 租用戶以確認新測試群組名稱是否出現。</span><span class="sxs-lookup"><span data-stu-id="7a468-125">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="7a468-126">必要：全域系統管理員帳戶會受到保護</span><span class="sxs-lookup"><span data-stu-id="7a468-126">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="7a468-127">您已[保護 Office 365 全域系統管理員帳戶](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560)，以避免可能會導致違反 Office 365 訂閱規定的洩露認證。</span><span class="sxs-lookup"><span data-stu-id="7a468-127">You've [protected your Office 365 global administrator accounts](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) to avoid compromising credentials that can lead to breaches of an Office 365 subscription.</span></span>

<span data-ttu-id="7a468-128">如果您略過這項要求，全域系統管理員帳戶可能會受到攻擊和洩露，讓攻擊者可以取得對您資料的系統範圍存取權，來進行蒐集、損毀，或要求贖金。</span><span class="sxs-lookup"><span data-stu-id="7a468-128">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="7a468-129">如有需要，[步驟 2](identity-designate-protect-admin-accounts.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="7a468-129">If needed, [Step 2](identity-designate-protect-admin-accounts.md) can help you meet this requirement.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-130">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-130">How to test</span></span>

<span data-ttu-id="7a468-131">使用這些步驟來確認您已受保護全域系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="7a468-131">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="7a468-p103">在 PowerShell 命令提示字元執行下列 Azure AD V2 命令。您應該會看到僅專用全域系統管理員帳戶的清單。</span><span class="sxs-lookup"><span data-stu-id="7a468-p103">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="7a468-p104">使用步驟 1 中的每個帳戶登入Office 365。每個登入必須要求多重要素驗證和您組織中可用的最強型次要驗證。</span><span class="sxs-lookup"><span data-stu-id="7a468-p104">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="7a468-136">請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) 以了解安裝 Azure AD V2 PowerShell 模組與登入 Office 365 的指示。</span><span class="sxs-lookup"><span data-stu-id="7a468-136">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in to Office 365.</span></span>

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="7a468-137">選用：已個人化您組織的 Office 365 登入畫面</span><span class="sxs-lookup"><span data-stu-id="7a468-137">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="7a468-138">您已使用「[將公司商標新增至登入及存取面板頁面](http://aka.ms/aadpaddbranding)」來將貴組織的商標新增至 Office 365 登入頁面。</span><span class="sxs-lookup"><span data-stu-id="7a468-138">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="7a468-139">如果您略過此選項，使用者會看到一般的 Office 365 登入畫面，並且可能無法確定它們登入的是貴組織的網站。</span><span class="sxs-lookup"><span data-stu-id="7a468-139">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="7a468-140">如有需要，[步驟 11](identity-customize-office-365-sign-in.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-140">If needed, [Step 11](identity-customize-office-365-sign-in.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-141">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-141">How to test</span></span>

<span data-ttu-id="7a468-p105">透過使用者帳戶名稱與多重要素驗證登入 Office 365 入口網站。您應會在登入頁面上看到您自訂的商標元素。</span><span class="sxs-lookup"><span data-stu-id="7a468-p105">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="7a468-144">選用：已為使用者啟用多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="7a468-144">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="7a468-145">您已使用「[Office 365 部署多重要素驗證方案](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)」與「[為 Office 365 使用者設定多重要素驗證](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)」來啟用使用者帳戶的多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="7a468-145">You used [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) and [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) to enable multifactor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="7a468-p106">如果您略過此選項，使用者帳戶會容易遭到網路攻擊所引起的認證洩露。若使用者帳戶的密碼洩露時，帳戶的所有資源和功能 (例如系統管理員角色) 皆可供攻擊者使用。這可讓攻擊者複製、損毀，或保留內部文件和其他資料以勒索贖金。</span><span class="sxs-lookup"><span data-stu-id="7a468-p106">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="7a468-149">如有需要，[步驟 5](identity-multi-factor-authentication.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-149">If needed, [Step 5](identity-multi-factor-authentication.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-150">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-150">How to test</span></span>

1.  <span data-ttu-id="7a468-151">在 Office 365 系統管理員入口網站中建立測試使用者帳戶並為它們指派授權。</span><span class="sxs-lookup"><span data-stu-id="7a468-151">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="7a468-152">使用您為實際使用者帳戶使用的其他驗證方法 (例如將郵件傳送給您的電話)，來為測試使用者帳戶設定多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="7a468-152">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="7a468-153">以測試使用者帳戶登入 Office 365 或 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="7a468-153">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="7a468-154">請確認 MFA 會提示您輸入其他的驗證資訊，且結果為驗證成功。</span><span class="sxs-lookup"><span data-stu-id="7a468-154">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="7a468-155">刪除測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-155">Delete the test user account.</span></span>

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="7a468-156">選用：目錄同步處理已受到監控</span><span class="sxs-lookup"><span data-stu-id="7a468-156">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="7a468-157">您已使用 [Azure AD Connect Health 同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (適用於密碼同步處理) 或[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (適用於同盟驗證) 並已部署 Azure AD Connect Health，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7a468-157">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="7a468-158">在每個內部部署身分識別伺服器上安裝 Azure AD Connect Health 代理程式。</span><span class="sxs-lookup"><span data-stu-id="7a468-158">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="7a468-159">使用 Azure AD Connect Health 入口網站來監控正在進行的同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="7a468-159">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="7a468-160">如果您略過此選項時，則可以更精確地評估以雲端為基礎的身分識別基礎結構之狀態。</span><span class="sxs-lookup"><span data-stu-id="7a468-160">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="7a468-161">如有需要，[步驟 8](identity-azure-ad-connect-health.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-161">If needed, [Step 8](identity-azure-ad-connect-health.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-162">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-162">How to test</span></span>
<span data-ttu-id="7a468-163">Azure AD Connect Health 入口網站會顯示內部部署身分識別伺服器和進行中同步處理的目前和正確狀態。</span><span class="sxs-lookup"><span data-stu-id="7a468-163">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="7a468-164">選用：使用者可以重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="7a468-164">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="7a468-165">您已使用 [Azure AD 自助密碼重設快速部署](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)來為您的使用者設定密碼重設。</span><span class="sxs-lookup"><span data-stu-id="7a468-165">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="7a468-166">如果您不符合此條件，使用者將依賴使用者帳戶的系統管理員重設密碼，造成其他 IT 系統管理員的負擔。</span><span class="sxs-lookup"><span data-stu-id="7a468-166">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="7a468-167">如有需要，[步驟 4](identity-password-reset.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-167">If needed, [Step 4](identity-password-reset.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-168">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-168">How to test</span></span>

1. <span data-ttu-id="7a468-169">使用初始密碼建立測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-169">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="7a468-170">使用「[讓使用者在 Office 365 中重設其自身密碼](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a)」中的步驟來重設對測試使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="7a468-170">Use the steps in [Let users reset their own passwords in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="7a468-171">登出，然後再使用重設密碼登入測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-171">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="7a468-172">刪除測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-172">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="7a468-173">選用：已為您的使用者啟用密碼回寫</span><span class="sxs-lookup"><span data-stu-id="7a468-173">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="7a468-174">您已使用在「[具密碼回寫的 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」中的指示，為您 Microsoft 365 企業版訂閱的 Azure AD 租用戶啟用密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="7a468-174">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="7a468-175">如果您略過此選項，未連線到內部部署網路的使用者必須透過 IT 系統管理員重設或解除鎖定 Windows Server AD 密碼。</span><span class="sxs-lookup"><span data-stu-id="7a468-175">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their Windows Server AD passwords through an IT administrator.</span></span>

<span data-ttu-id="7a468-176">如有需要，[步驟 9](identity-password-writeback.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-176">If needed, [Step 9](identity-password-writeback.md) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="7a468-177">若要充分利用 Azure AD Identity Protection 功能 (例如當 Azure AD 已偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，則需要密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="7a468-177">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

### <a name="how-to-test"></a><span data-ttu-id="7a468-178">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-178">How to test</span></span>

<span data-ttu-id="7a468-p107">您可以藉由在 Office 365 中變更密碼以測試密碼回寫。您應可使用自己的帳戶與新密碼，以存取內部部署 Windows Server AD 資源。</span><span class="sxs-lookup"><span data-stu-id="7a468-p107">You test password writeback by changing your password in Office 365. You should be able to use your account and new password to access on-premises Windows Server AD resources.</span></span>

1. <span data-ttu-id="7a468-181">在內部部署 Windows Server AD 中建立測試使用者帳戶，允許發生目錄同步處理，然後在 Office 365 系統管理員入口網站中授與該帳戶 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="7a468-181">Create a test user account in your on-premises Windows Server AD, allow directory synchronization to occur, and then grant it an Office 365 license in the Office 365 admin portal.</span></span>
2. <span data-ttu-id="7a468-182">透過加入您內部部署 Windows 伺服器 AD 網域的遠端電腦，使用測試使用者帳戶的認證來登入電腦與 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="7a468-182">From a remote computer that is joined to your on-premises Windows Server AD domain, sign in to the computer and the Office 365 portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="7a468-183">選取 [設定] > [Office 365 設定] > [密碼] > [變更密碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7a468-183">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="7a468-184">輸入目前的密碼並輸入新密碼，然後加以確認。</span><span class="sxs-lookup"><span data-stu-id="7a468-184">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="7a468-p108">登出 Office 365 入口網站與遠端電腦，然後以測試使用者帳戶與新密碼登入電腦。這證明您可以使用 Azure AD 租用戶變更內部部署 Windows 伺服器 AD 使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="7a468-p108">Sign out of the Office 365 portal and the remote computer and then sign in to the computer using the test user account and its new password. This proves that you were able to change the password of an on-premises Windows Server AD user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-single-sign-on"></a><span data-ttu-id="7a468-187">選用：使用者可以使用單一登入來進行登入</span><span class="sxs-lookup"><span data-stu-id="7a468-187">Optional: Users can sign in using single sign-on</span></span>

<span data-ttu-id="7a468-188">您可以為您組織啟用 [Azure AD Connect：隨選即用單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)，以簡化使用者登入以雲端為基礎之應用程式 (例如 Office 365) 的方式。</span><span class="sxs-lookup"><span data-stu-id="7a468-188">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="7a468-189">如果您略過此選項時，使用者存取其他使用 Azure AD 的應用程式時可能會收到提示，要求他們提供認證。</span><span class="sxs-lookup"><span data-stu-id="7a468-189">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="7a468-190">如有需要，[步驟 10](identity-single-sign-on.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-190">If needed, [Step 10](identity-single-sign-on.md) can help you with this option.</span></span>


<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="7a468-191">選用：以群組為基礎的授權會根據群組成員資格，自動將授權指派至使用者帳戶和將其移除</span><span class="sxs-lookup"><span data-stu-id="7a468-191">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="7a468-192">您已為適當的 Azure AD 的安全性群組[啟用以群組為基礎的授權](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)，以便自動指派或移除 Office 365 和 EMS 的授權。</span><span class="sxs-lookup"><span data-stu-id="7a468-192">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="7a468-193">若您略過此選項，您必須手動進行以下動作：</span><span class="sxs-lookup"><span data-stu-id="7a468-193">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="7a468-194">將授權指派給您想要將 Office 365 和 EMS 存取權提供給其中的新使用者。</span><span class="sxs-lookup"><span data-stu-id="7a468-194">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="7a468-195">將授權從不再存在於您組織中或不需要存取 Office 365 和 EMS 的使用者中移除。</span><span class="sxs-lookup"><span data-stu-id="7a468-195">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="7a468-196">如有需要，[步驟 12](identity-group-based-licensing.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-196">If needed, [Step 12](identity-group-based-licensing.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-197">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-197">How to test</span></span>

1. <span data-ttu-id="7a468-198">在 Azure AD 中使用 Azure 入口網站建立測試安全性群組，並將以群組為基礎的授權設定為指派 Office 365 和 EMS 授權。</span><span class="sxs-lookup"><span data-stu-id="7a468-198">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="7a468-199">在 Azure AD 中建立測試使用者帳戶，並將它新增到測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7a468-199">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="7a468-200">檢查 Office 365 系統管理員入口網站中的使用者帳戶內容，以確保其已指派至 Office 365 和 EMS 授權。</span><span class="sxs-lookup"><span data-stu-id="7a468-200">Examine the properties of the user account in the Office 365 admin portal to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="7a468-201">從測試安全性群組移除測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-201">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="7a468-202">檢查使用者帳戶內容，以確保其不再指派至 Office 365 和 EMS 授權。</span><span class="sxs-lookup"><span data-stu-id="7a468-202">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="7a468-203">刪除測試安全性群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-203">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="7a468-204">選用：動態群組成員資格設定會根據使用者帳戶屬性，自動將使用者帳戶新增至群組</span><span class="sxs-lookup"><span data-stu-id="7a468-204">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="7a468-205">您已決定一組 Azure AD 動態群組，並使用「[Azure Active Directory 中的以屬性為基礎的動態群組成員資格](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」中的指示來建立群組與規則，以便判斷適用於群組成員資格的一組使用者帳戶屬性和值。</span><span class="sxs-lookup"><span data-stu-id="7a468-205">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="7a468-p109">如果您略過此選項時，必須以手動方式完成群組成員資格，因為已新增數個帳戶或使用者帳戶屬性隨著時間而變更。比方說，如果有人從銷售部門調到會計部門時，您必須：</span><span class="sxs-lookup"><span data-stu-id="7a468-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="7a468-208">更新該使用者帳戶的部門屬性值。</span><span class="sxs-lookup"><span data-stu-id="7a468-208">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="7a468-209">手動將它們從銷售群組中移除。</span><span class="sxs-lookup"><span data-stu-id="7a468-209">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="7a468-210">手動將它們新增至會計群組。</span><span class="sxs-lookup"><span data-stu-id="7a468-210">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="7a468-211">如果銷售和會計群組是動態的，您只需要變更使用者帳戶的部門值。</span><span class="sxs-lookup"><span data-stu-id="7a468-211">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="7a468-212">如有需要，[步驟 15](identity-automatic-group-membership.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-212">If needed, [Step 15](identity-automatic-group-membership.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-213">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-213">How to test</span></span>

1. <span data-ttu-id="7a468-214">使用 Azure 入口網站在 Azure AD 中建立測試動態群組並設定部門等於「test1」的規則。</span><span class="sxs-lookup"><span data-stu-id="7a468-214">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="7a468-215">在 Azure AD 中建立測試使用者帳戶，並將部門屬性設定為「test1」。</span><span class="sxs-lookup"><span data-stu-id="7a468-215">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="7a468-216">檢查使用者帳戶的內容，以確定它成為測試動態群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7a468-216">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="7a468-217">將測試使用者帳戶的部門屬性值變為「test2」。</span><span class="sxs-lookup"><span data-stu-id="7a468-217">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="7a468-218">檢查使用者帳戶的內容，以確定它不再是測試動態群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7a468-218">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="7a468-219">刪除測試動態群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-219">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="7a468-220">選用：已啟用特定 Azure AD 的安全性和 Office 365 群組的自助群組管理</span><span class="sxs-lookup"><span data-stu-id="7a468-220">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="7a468-221">您已決定哪些群組適用於自助管理，指示其擁有者關於群組管理工作流程和責任，並為這些群組[設定 Azure AD 中的自助管理](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="7a468-221">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="7a468-222">如果您略過此選項時，所有 Azure AD 群組管理工作必須由 IT 系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="7a468-222">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="7a468-223">如有需要，[步驟 14](identity-self-service-group-management.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-223">If needed, [Step 14](identity-self-service-group-management.md) can help you with this option.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="7a468-224">如何測試</span><span class="sxs-lookup"><span data-stu-id="7a468-224">How to test</span></span>
1.  <span data-ttu-id="7a468-225">使用 Azure 入口網站在 Azure AD 中建立測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-225">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="7a468-226">使用測試使用者帳戶登入並建立測試 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7a468-226">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="7a468-227">登出，然後使用您的 IT 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="7a468-227">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="7a468-228">為測試使用者帳戶設定自助管理的測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7a468-228">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="7a468-229">登出，然後使用您的測試使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="7a468-229">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="7a468-230">使用 Azure 入口網站以將成員新增至測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7a468-230">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="7a468-231">刪除測試安全性群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7a468-231">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a><span data-ttu-id="7a468-232">選用：已啟用 Azure AD Identity Protection 來防護認證洩露</span><span class="sxs-lookup"><span data-stu-id="7a468-232">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="7a468-233">您已啟用 Azure AD Identity Protection 來：</span><span class="sxs-lookup"><span data-stu-id="7a468-233">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="7a468-234">解決潛在的身分識別弱點。</span><span class="sxs-lookup"><span data-stu-id="7a468-234">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="7a468-235">偵測可能的認證洩露嘗試。</span><span class="sxs-lookup"><span data-stu-id="7a468-235">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="7a468-236">調查並解決持續的可疑身分識別事件。</span><span class="sxs-lookup"><span data-stu-id="7a468-236">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="7a468-p110">如果您略過此選項，您將無法偵測或自動抵禦認證洩露嘗試或調查與身分識別相關的安全性事件。這可能會使您的組織憑證洩露並對貴組織的機密資料產生威脅。</span><span class="sxs-lookup"><span data-stu-id="7a468-p110">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="7a468-239">如有需要，[步驟 6](identity-azure-ad-identity-protection.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-239">If needed, [Step 6](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="7a468-240">選用：您已設定特殊權限的身分識別管理來支援全域系統管理員角色的隨選指派</span><span class="sxs-lookup"><span data-stu-id="7a468-240">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="7a468-241">您已使用「[設定 Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」中的指示，以啟用 Azure AD 租用戶中的 PIM 並將您的全域系統管理員帳戶設定為合格的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="7a468-241">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="7a468-242">您也使用「[保護 Azure AD 中混合式和雲端部署的特殊存取權](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」中的建議，以開發可保護特殊存取權避免受到網路攻擊的藍圖。</span><span class="sxs-lookup"><span data-stu-id="7a468-242">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="7a468-243">如果您略過此選項時，全域系統管理員帳戶可能會受到持續線上攻擊，且機密資訊洩露時，可能會讓攻擊者蒐集、損毀，或保留您的機密資訊，以勒索贖金。</span><span class="sxs-lookup"><span data-stu-id="7a468-243">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="7a468-244">如有需要，[步驟 3](identity-azure-ad-identity-protection.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7a468-244">If needed, [Step 3](identity-azure-ad-identity-protection.md) can help you with this option.</span></span>


## <a name="next-phase"></a><span data-ttu-id="7a468-245">下一個階段</span><span class="sxs-lookup"><span data-stu-id="7a468-245">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| <span data-ttu-id="7a468-246">Microsoft 365 企業版 端對端部署程序的下一個階段是 [Windows 10 企業版](windows10-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="7a468-246">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [Windows 10 Enterprise](windows10-infrastructure.md).</span></span> |

