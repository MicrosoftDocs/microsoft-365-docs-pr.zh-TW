<span data-ttu-id="42d39-101">若需身分識別基礎架構的其他建議，另請參閱「[先決條件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)」(機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="42d39-101">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-user-groups"></a>
### <a name="required-your-users-groups-and-group-memberships-have-been-created"></a><span data-ttu-id="42d39-102">必要：您的使用者、群組和群組成員資格均已建立</span><span class="sxs-lookup"><span data-stu-id="42d39-102">Required: All users, groups, and group memberships have been created</span></span>

<span data-ttu-id="42d39-103">您已建立使用者帳戶和群組，因此：</span><span class="sxs-lookup"><span data-stu-id="42d39-103">You've created user accounts and groups so that:</span></span>

- <span data-ttu-id="42d39-104">貴組織的員工和與貴組織合作的廠商、承包商及合作夥伴擁有在 Azure Active Directory (Azure AD) 中相對應的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-104">Employees in your organization and the vendors, contractors, and partners that work for or with your organization have a corresponding user account in Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="42d39-105">Azure AD 群組和其成員包含適用於各種目的使用者帳戶和其他群組 (例如 Microsoft 雲端服務的安全性設定佈建、自動授權，與其他使用)。</span><span class="sxs-lookup"><span data-stu-id="42d39-105">Azure AD groups and their members contain user accounts and other groups for various purposes, such as the provisioning of security settings for Microsoft cloud services, automatic licensing, and other uses.</span></span>

<span data-ttu-id="42d39-106">如有需要，[步驟 1](../identity-plan-users-groups.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="42d39-106">If needed, [Step 1](../identity-plan-users-groups.md) can help you meet this requirement.</span></span>

<a name="crit-identity-global-admin"></a>
### <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="42d39-107">必要：全域系統管理員帳戶會受到保護</span><span class="sxs-lookup"><span data-stu-id="42d39-107">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="42d39-108">您已[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)，以防止攻擊者所進行、可能導致違反您的 Microsoft 365 訂閱的認證洩露。</span><span class="sxs-lookup"><span data-stu-id="42d39-108">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="42d39-109">如果您略過這項要求，全域系統管理員帳戶可能會受到攻擊和洩露，讓攻擊者可以取得對您資料的系統範圍存取權，來進行蒐集、損毀，或要求贖金。</span><span class="sxs-lookup"><span data-stu-id="42d39-109">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="42d39-110">如有需要，[步驟 2](../identity-designate-protect-admin-accounts.md#identity-global-admin) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="42d39-110">If needed, [Step 2](../identity-designate-protect-admin-accounts.md#identity-global-admin) can help you meet this requirement.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-111">如何測試</span><span class="sxs-lookup"><span data-stu-id="42d39-111">How to test</span></span>

<span data-ttu-id="42d39-112">使用這些步驟來確認您已受保護全域系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="42d39-112">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="42d39-p101">在 PowerShell 命令提示字元執行下列 Azure Active Directory PowerShell for Graph 命令。您應該會看到僅專用全域系統管理員帳戶的清單。</span><span class="sxs-lookup"><span data-stu-id="42d39-p101">Run the following Azure AD V2 command at the PowerShell command prompt. You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="42d39-p102">使用步驟 1 中的每個帳戶登入Office 365。每個登入必須要求多重要素驗證和您組織中可用的最強型次要驗證。</span><span class="sxs-lookup"><span data-stu-id="42d39-p102">Sign in to Office 365 using each of the accounts from step 1. Each sign in must require multi-factor authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="42d39-117">請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)，以取得安裝 Azure Active Directory PowerShell for Graph 模組及登入 Office 365 的指示。</span><span class="sxs-lookup"><span data-stu-id="42d39-117">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
### <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="42d39-118">選用：您已設定特殊權限的身分識別管理來支援全域系統管理員角色的隨選指派</span><span class="sxs-lookup"><span data-stu-id="42d39-118">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="42d39-119">您已使用[設定 Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) 中的指示，啟用 Azure AD 租用戶中的 PIM 並將您的全域系統管理員帳戶設定為合格的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="42d39-119">You've used the instructions in [Configure Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="42d39-120">您也使用「[保護 Azure AD 中混合式和雲端部署的特殊存取權](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」中的建議，以開發可保護特殊存取權避免受到網路攻擊的藍圖。</span><span class="sxs-lookup"><span data-stu-id="42d39-120">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="42d39-121">如果您略過此選項時，全域系統管理員帳戶可能會受到持續線上攻擊，且機密資訊洩露時，可能會讓攻擊者蒐集、損毀，或保留您的機密資訊，以勒索贖金。</span><span class="sxs-lookup"><span data-stu-id="42d39-121">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="42d39-122">如有需要，[步驟 2](../identity-designate-protect-admin-accounts.md#identity-pim) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-122">If needed, [Step 2](../identity-designate-protect-admin-accounts.md#identity-pim) can help you with this option.</span></span>


<a name="crit-identity-sync"></a>
### <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="42d39-123">必要：使用者和群組會與 Azure AD 同步處理</span><span class="sxs-lookup"><span data-stu-id="42d39-123">Required: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="42d39-124">如果您有現有的內部部署 Active Directory Domain Services (AD DS)，表示您已使用 Azure AD Connect 將內部部署 AD DS 內的使用者帳戶和群組同步處理到 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-124">If you have an existing on-premises identity provider, such as Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises identity provider to your Azure AD tenant.</span></span>

<span data-ttu-id="42d39-125">隨著將目錄同步處理，使用者可以使用他們用來登入電腦和存取內部部署資源所用的相同認證來登入 Office 365 和其他 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="42d39-125">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="42d39-126">如有需要，[步驟 3](../identity-azure-ad-connect.md#identity-sync) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="42d39-126">If needed, [Step 3](../identity-azure-ad-connect.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="42d39-127">如果您略過這項要求，您將有兩組使用者帳戶和群組：</span><span class="sxs-lookup"><span data-stu-id="42d39-127">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="42d39-128">在您內部部署 AD DS 中存在的使用者帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="42d39-128">User accounts and groups that exist in your on-premises identity provider</span></span>
- <span data-ttu-id="42d39-129">Azure AD 租用戶中存在的使用者帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="42d39-129">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="42d39-p103">在此狀態中，IT 系統管理員和使用者都必須以手動方式維護這兩組使用者帳戶和群組。這難免會導致帳戶、密碼及群組不同步。</span><span class="sxs-lookup"><span data-stu-id="42d39-p103">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-132">如何測試</span><span class="sxs-lookup"><span data-stu-id="42d39-132">How to test</span></span>
<span data-ttu-id="42d39-133">若要確認與內部部署認證的驗證運作正常，使用您的內部部署認證登入 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="42d39-133">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="42d39-134">若要確認目錄同步處理是否正常運作，請執行以下動作：</span><span class="sxs-lookup"><span data-stu-id="42d39-134">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="42d39-135">在 AD DS 中建立新的測試群組。</span><span class="sxs-lookup"><span data-stu-id="42d39-135">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="42d39-136">等待同步處理的時間。</span><span class="sxs-lookup"><span data-stu-id="42d39-136">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="42d39-137">檢查您的 Azure AD 租用戶以確認新測試群組名稱是否出現。</span><span class="sxs-lookup"><span data-stu-id="42d39-137">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
### <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="42d39-138">選用：目錄同步處理已受到監控</span><span class="sxs-lookup"><span data-stu-id="42d39-138">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="42d39-139">您已使用 [Azure AD Connect Health 同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (適用於密碼同步處理) 或[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (適用於同盟驗證) 並已部署 Azure AD Connect Health，其中包括：</span><span class="sxs-lookup"><span data-stu-id="42d39-139">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="42d39-140">在每個內部部署身分識別伺服器上安裝 Azure AD Connect Health 代理程式。</span><span class="sxs-lookup"><span data-stu-id="42d39-140">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="42d39-141">使用 Azure AD Connect Health 入口網站來監控正在進行的同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="42d39-141">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="42d39-142">如果您略過此選項時，則可以更精確地評估以雲端為基礎的身分識別基礎結構之狀態。</span><span class="sxs-lookup"><span data-stu-id="42d39-142">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="42d39-143">如有需要，[步驟 3](../identity-azure-ad-connect.md#identity-sync-health) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-143">If needed, [Step 3](../identity-azure-ad-connect.md#identity-sync-health) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-144">如何測試</span><span class="sxs-lookup"><span data-stu-id="42d39-144">How to test</span></span>
<span data-ttu-id="42d39-145">Azure AD Connect Health 入口網站會顯示您內部部署網域控制站和進行中同步處理的目前和正確狀態。</span><span class="sxs-lookup"><span data-stu-id="42d39-145">The Azure AD Connect Health portal shows the current and correct state of your on-premises identity servers and the ongoing synchronization.</span></span>

<a name="crit-identity-mfa"></a>
### <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="42d39-146">選用：已為使用者啟用多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="42d39-146">Optional: Multi-factor authentication is enabled for your users</span></span>

<span data-ttu-id="42d39-147">您已使用[規劃多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)和[條件式存取原則](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)，為您的使用者帳戶啟用多重要素驗證 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="42d39-147">You used [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [conditional access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable multi-factor authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="42d39-p104">如果您略過此選項，使用者帳戶會容易遭到網路攻擊所引起的認證洩露。若使用者帳戶的密碼洩露時，帳戶的所有資源和功能 (例如系統管理員角色) 皆可供攻擊者使用。這可讓攻擊者複製、損毀，或保留內部文件和其他資料以勒索贖金。</span><span class="sxs-lookup"><span data-stu-id="42d39-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="42d39-151">如有需要，[步驟 4](../identity-multi-factor-authentication.md#identity-mfa) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-151">If needed, [Step 4](../identity-multi-factor-authentication.md#identity-mfa) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-152">如何測試</span><span class="sxs-lookup"><span data-stu-id="42d39-152">How to test</span></span>

1.  <span data-ttu-id="42d39-153">建立測試使用者帳戶，並為他們指派授權。</span><span class="sxs-lookup"><span data-stu-id="42d39-153">Create a test user account in the Office 365 Admin portal and assign them a license.</span></span> 
2.  <span data-ttu-id="42d39-154">使用您為實際使用者帳戶使用的其他驗證方法 (例如將簡訊傳送到您的電話)，來為測試使用者帳戶設定多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="42d39-154">Configure multi-factor authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a message to your phone.</span></span> 
3.  <span data-ttu-id="42d39-155">以測試使用者帳戶登入 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="42d39-155">Sign in to the Office 365 or Azure portal with the test user account.</span></span>
4.  <span data-ttu-id="42d39-156">請確認 MFA 會提示您輸入其他的驗證資訊，且結果為驗證成功。</span><span class="sxs-lookup"><span data-stu-id="42d39-156">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="42d39-157">刪除測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-157">Delete the test user account.</span></span>

<a name="crit-password-prot"></a>
### <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="42d39-158">選用：Azure AD 密碼保護禁止使用弱式密碼</span><span class="sxs-lookup"><span data-stu-id="42d39-158">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="42d39-159">您已[在雲端](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)啟用禁止使用錯誤密碼，以及為您的[內部部署 Active Directory 網域服務 (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) 啟用全域禁止密碼以及選用的自訂字詞。</span><span class="sxs-lookup"><span data-stu-id="42d39-159">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="42d39-160">如有需要，[步驟 4](../identity-multi-factor-authentication.md#identity-password-prot) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-160">If needed, [Step 4](../identity-multi-factor-authentication.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-ident-prot"></a>
### <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="42d39-161">選用：已啟用 Azure AD Identity Protection 來防止認證洩露 (僅限 Microsoft 365 企業版 E5)</span><span class="sxs-lookup"><span data-stu-id="42d39-161">Optional: Azure AD Identity Protection is enabled to protect against credential compromise</span></span>

<span data-ttu-id="42d39-162">您已啟用 Azure AD Identity Protection 來：</span><span class="sxs-lookup"><span data-stu-id="42d39-162">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="42d39-163">解決潛在的身分識別弱點。</span><span class="sxs-lookup"><span data-stu-id="42d39-163">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="42d39-164">偵測可能的認證洩露嘗試。</span><span class="sxs-lookup"><span data-stu-id="42d39-164">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="42d39-165">調查並解決持續的可疑身分識別事件。</span><span class="sxs-lookup"><span data-stu-id="42d39-165">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="42d39-p105">如果您略過此選項，您將無法偵測或自動抵禦認證洩露嘗試或調查與身分識別相關的安全性事件。這可能會使您的組織憑證洩露並對貴組織的機密資料產生威脅。</span><span class="sxs-lookup"><span data-stu-id="42d39-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="42d39-168">如有需要，[步驟 4](../identity-multi-factor-authentication.md#identity-ident-prot) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-168">If needed, [Step 4](../identity-multi-factor-authentication.md#identity-ident-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
### <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="42d39-169">選用：使用者可以重設自己的密碼</span><span class="sxs-lookup"><span data-stu-id="42d39-169">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="42d39-170">您已使用 [Azure AD 自助密碼重設快速部署](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)來為您的使用者設定密碼重設。</span><span class="sxs-lookup"><span data-stu-id="42d39-170">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="42d39-171">如果您不符合此條件，使用者將依賴使用者帳戶的系統管理員重設密碼，造成其他 IT 系統管理員的負擔。</span><span class="sxs-lookup"><span data-stu-id="42d39-171">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="42d39-172">如有需要，[步驟 5](../identity-password-reset.md#identity-pw-reset) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-172">If needed, [Step 5](../identity-password-reset.md#identity-pw-reset) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-173">測試方式</span><span class="sxs-lookup"><span data-stu-id="42d39-173">How to test</span></span>

1. <span data-ttu-id="42d39-174">使用初始密碼建立測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-174">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="42d39-175">使用「[讓使用者在 Office 365 中重設其自身密碼](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords)」中的步驟來重設對測試使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="42d39-175">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="42d39-176">登出，然後再使用重設密碼登入測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-176">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="42d39-177">刪除測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-177">Delete the test user account.</span></span>

<a name="crit-identity-pw-writeback"></a>
### <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="42d39-178">選用：已為您的使用者啟用密碼回寫</span><span class="sxs-lookup"><span data-stu-id="42d39-178">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="42d39-179">您已使用在「[具密碼回寫的 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」中的指示，為您 Microsoft 365 企業版訂閱的 Azure AD 租用戶啟用密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="42d39-179">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="42d39-180">如果您略過此選項，未連線到內部部署網路的使用者必須透過 IT 系統管理員，才能重設或解除鎖定 AD DS 密碼。</span><span class="sxs-lookup"><span data-stu-id="42d39-180">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="42d39-181">如有需要，[步驟 5](../identity-password-reset.md#identity-pw-writeback) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-181">If needed, [Step 5](../identity-password-reset.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="42d39-182">若要充分利用 Azure AD Identity Protection 功能 (例如當 Azure AD 已偵測到高風險的帳戶洩露時，要求使用者變更其內部部署密碼)，則需要密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="42d39-182">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-183">如何測試</span><span class="sxs-lookup"><span data-stu-id="42d39-183">How to test</span></span>

<span data-ttu-id="42d39-184">您可藉由在 Office 365 中變更您的密碼來測試密碼回寫。</span><span class="sxs-lookup"><span data-stu-id="42d39-184">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="42d39-185">您應該能夠使用自己的帳戶和新密碼來存取內部部署 AD DS 資源。</span><span class="sxs-lookup"><span data-stu-id="42d39-185">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="42d39-186">在內部部署 AD DS 中建立測試使用者帳戶、允許進行目錄同步處理，然後在 Microsoft 365 系統管理中心將 Microsoft 365 企業版授權授予該帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-186">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it an Office 365 license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="42d39-187">透過加入您內部部署 AD DS 網域的遠端電腦，使用測試使用者帳戶的認證來登入電腦與 Office 入口網站。</span><span class="sxs-lookup"><span data-stu-id="42d39-187">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="42d39-188">選取 [設定] > [Office 365 設定] > [密碼] > [變更密碼]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42d39-188">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="42d39-189">輸入目前的密碼並輸入新密碼，然後加以確認。</span><span class="sxs-lookup"><span data-stu-id="42d39-189">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="42d39-190">登出 Office 入口網站與遠端電腦，然後使用測試使用者帳戶與新密碼登入電腦。</span><span class="sxs-lookup"><span data-stu-id="42d39-190">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="42d39-191">這證明您可以使用 Azure AD 租用戶來變更內部部署 AD DS 使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="42d39-191">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

<a name="crit-identity-sso"></a>
### <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="42d39-192">選用：使用者可以使用 Azure AD 無縫單一登入來進行登入</span><span class="sxs-lookup"><span data-stu-id="42d39-192">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="42d39-193">您可以為您組織啟用 [Azure AD Connect：隨選即用單一登入](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)，以簡化使用者登入以雲端為基礎之應用程式 (例如 Office 365) 的方式。</span><span class="sxs-lookup"><span data-stu-id="42d39-193">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="42d39-194">如果您略過此選項，使用者在存取使用您 Azure AD 租用戶的其他應用程式時可能會收到提示，要求他們提供認證。</span><span class="sxs-lookup"><span data-stu-id="42d39-194">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use Azure AD.</span></span>

<span data-ttu-id="42d39-195">如有需要，[步驟 5](../identity-password-reset.md#identity-sso) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-195">If needed, [Step 5](../identity-password-reset.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
### <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="42d39-196">選用：已個人化您組織的 Office 365 登入畫面</span><span class="sxs-lookup"><span data-stu-id="42d39-196">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="42d39-197">您已使用「[將公司商標新增至登入及存取面板頁面](http://aka.ms/aadpaddbranding)」來將貴組織的商標新增至 Office 365 登入頁面。</span><span class="sxs-lookup"><span data-stu-id="42d39-197">You have used [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="42d39-198">如果您略過此選項，使用者會看到一般的 Office 365 登入畫面，並且可能無法確定它們登入的是貴組織的網站。</span><span class="sxs-lookup"><span data-stu-id="42d39-198">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="42d39-199">如有需要，[步驟 5](../identity-password-reset.md#identity-custom-sign-in) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-199">If needed, [Step 5](../identity-password-reset.md#identity-custom-sign-in) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-200">測試方式</span><span class="sxs-lookup"><span data-stu-id="42d39-200">How to test</span></span>

<span data-ttu-id="42d39-p108">透過使用者帳戶名稱與多重要素驗證登入 Office 365 入口網站。您應會在登入頁面上看到您自訂的商標元素。</span><span class="sxs-lookup"><span data-stu-id="42d39-p108">Sign in to the Office 365 portal with your user account name and multi-factor authentication. You should see your custom branding elements on the sign-in page.</span></span>

<a name="crit-identity-self-service-groups"></a>
### <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="42d39-203">選用：已啟用特定 Azure AD 的安全性和 Office 365 群組的自助群組管理</span><span class="sxs-lookup"><span data-stu-id="42d39-203">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="42d39-204">您已決定哪些群組適用於自助管理，指示其擁有者關於群組管理工作流程和責任，並為這些群組[設定 Azure AD 中的自助管理](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。</span><span class="sxs-lookup"><span data-stu-id="42d39-204">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="42d39-205">如果您略過此選項時，所有 Azure AD 群組管理工作必須由 IT 系統管理員執行。</span><span class="sxs-lookup"><span data-stu-id="42d39-205">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="42d39-206">如有需要，[步驟 6](../identity-self-service-group-management.md#identity-self-service-groups) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-206">If needed, [Step 6](../identity-self-service-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-207">測試方式</span><span class="sxs-lookup"><span data-stu-id="42d39-207">How to test</span></span>
1.  <span data-ttu-id="42d39-208">使用 Azure 入口網站在 Azure AD 中建立測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-208">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="42d39-209">使用測試使用者帳戶登入並建立測試 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="42d39-209">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="42d39-210">登出，然後使用您的 IT 系統管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="42d39-210">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="42d39-211">為測試使用者帳戶設定自助管理的測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="42d39-211">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="42d39-212">登出，然後使用您的測試使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="42d39-212">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="42d39-213">使用 Azure 入口網站以將成員新增至測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="42d39-213">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="42d39-214">刪除測試安全性群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-214">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
### <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="42d39-215">選用：動態群組成員資格設定會根據使用者帳戶屬性，自動將使用者帳戶新增至群組</span><span class="sxs-lookup"><span data-stu-id="42d39-215">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="42d39-216">您已決定一組 Azure AD 動態群組，並使用「[Azure Active Directory 中的以屬性為基礎的動態群組成員資格](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」中的指示來建立群組與規則，以便判斷適用於群組成員資格的一組使用者帳戶屬性和值。</span><span class="sxs-lookup"><span data-stu-id="42d39-216">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="42d39-p109">如果您略過此選項時，必須以手動方式完成群組成員資格，因為已新增數個帳戶或使用者帳戶屬性隨著時間而變更。比方說，如果有人從銷售部門調到會計部門時，您必須：</span><span class="sxs-lookup"><span data-stu-id="42d39-p109">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="42d39-219">更新該使用者帳戶的部門屬性值。</span><span class="sxs-lookup"><span data-stu-id="42d39-219">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="42d39-220">手動將它們從銷售群組中移除。</span><span class="sxs-lookup"><span data-stu-id="42d39-220">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="42d39-221">手動將它們新增至會計群組。</span><span class="sxs-lookup"><span data-stu-id="42d39-221">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="42d39-222">如果銷售和會計群組是動態的，您只需要變更使用者帳戶的部門值。</span><span class="sxs-lookup"><span data-stu-id="42d39-222">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="42d39-223">如有需要，[步驟 6](../identity-self-service-group-management.md#identity-dyn-groups) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-223">If needed, [Step 6](../identity-self-service-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-224">如何測試</span><span class="sxs-lookup"><span data-stu-id="42d39-224">How to test</span></span>

1. <span data-ttu-id="42d39-225">使用 Azure 入口網站在 Azure AD 中建立測試動態群組並設定部門等於「test1」的規則。</span><span class="sxs-lookup"><span data-stu-id="42d39-225">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="42d39-226">在 Azure AD 中建立測試使用者帳戶，並將部門屬性設定為「test1」。</span><span class="sxs-lookup"><span data-stu-id="42d39-226">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="42d39-227">檢查使用者帳戶的內容，以確定它成為測試動態群組的成員。</span><span class="sxs-lookup"><span data-stu-id="42d39-227">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="42d39-228">將測試使用者帳戶的部門屬性值變為「test2」。</span><span class="sxs-lookup"><span data-stu-id="42d39-228">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="42d39-229">檢查使用者帳戶的內容，以確定它不再是測試動態群組的成員。</span><span class="sxs-lookup"><span data-stu-id="42d39-229">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="42d39-230">刪除測試動態群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-230">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
### <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="42d39-231">選用：以群組為基礎的授權會根據群組成員資格，自動將授權指派至使用者帳戶和將其移除</span><span class="sxs-lookup"><span data-stu-id="42d39-231">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="42d39-232">您已為適當的 Azure AD 安全性群組[啟用以群組為基礎的授權](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)，因此系統會自動指派或取消指派您的 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="42d39-232">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that licenses for both Office 365 and EMS are automatically assigned or removed.</span></span>

<span data-ttu-id="42d39-233">若您略過此選項，您必須手動進行以下動作：</span><span class="sxs-lookup"><span data-stu-id="42d39-233">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="42d39-234">將授權指派給您想要提供存取權的新使用者。</span><span class="sxs-lookup"><span data-stu-id="42d39-234">Assign licenses to new users whom you intend to have access to Office 365 and EMS.</span></span>
- <span data-ttu-id="42d39-235">從已不在您組織內或不需要存取權的使用者取消指派授權。</span><span class="sxs-lookup"><span data-stu-id="42d39-235">Remove licenses from users who are no longer with your organization or do not have access to Office 365 and EMS.</span></span>

<span data-ttu-id="42d39-236">如有需要，[步驟 6](../identity-self-service-group-management.md#identity-group-license) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-236">If needed, [Step 6](../identity-self-service-group-management.md#identity-group-license) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="42d39-237">如何測試</span><span class="sxs-lookup"><span data-stu-id="42d39-237">How to test</span></span>

1. <span data-ttu-id="42d39-238">在 Azure AD 中使用 Azure 入口網站建立測試安全性群組，並設定以群組為基礎的授權，以指派 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="42d39-238">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Office 365 and EMS licenses.</span></span>
2. <span data-ttu-id="42d39-239">在 Azure AD 中建立測試使用者帳戶，並將它新增到測試安全性群組。</span><span class="sxs-lookup"><span data-stu-id="42d39-239">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="42d39-240">在 Microsoft 365 系統管理中心中檢查使用者帳戶的內容，以確定其已獲指派 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="42d39-240">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Office 365 and EMS licenses.</span></span>
4. <span data-ttu-id="42d39-241">將測試使用者帳戶從測試安全性群組中移除。</span><span class="sxs-lookup"><span data-stu-id="42d39-241">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="42d39-242">檢查使用者帳戶內容，以確定其不再獲指派 Microsoft 365 企業版授權。</span><span class="sxs-lookup"><span data-stu-id="42d39-242">Examine the properties of the user account to ensure that it no longer has the Office 365 and EMS licenses assigned.</span></span>
6. <span data-ttu-id="42d39-243">刪除測試安全性群組和測試使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d39-243">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-access-reviews"></a>
### <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="42d39-244">選用：已設定存取權檢閱並用來監控存取權</span><span class="sxs-lookup"><span data-stu-id="42d39-244">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="42d39-245">您已使用這些文章來設定不同類型的存取權檢閱，以監控群組成員資格、對企業應用程式的存取權及角色指派：</span><span class="sxs-lookup"><span data-stu-id="42d39-245">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="42d39-246">群組和應用程式</span><span class="sxs-lookup"><span data-stu-id="42d39-246">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="42d39-247">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="42d39-247">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="42d39-248">Azure 資源角色</span><span class="sxs-lookup"><span data-stu-id="42d39-248">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="42d39-249">如有需要，[步驟 7](../identity-governance.md#identity-access-reviews) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="42d39-249">If needed, [Step 5](../identity-governance.md#identity-access-reviews) can help you with this option.</span></span>
