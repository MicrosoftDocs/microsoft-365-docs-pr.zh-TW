---
title: 步驟 1：建立和保護您的全域系統管理員帳戶
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
description: 您的全域系統管理員帳戶需要特別處理，以確保認證免受洩漏的危險。
ms.openlocfilehash: 1a0274967798e6c2ba6048e5a2cfd70e73cb0671
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801828"
---
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a><span data-ttu-id="50c2c-103">步驟 1：建立和保護您的全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="50c2c-103">Step 1: Create and protect your global admin accounts</span></span>

![階段 2 - 身分識別](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="50c2c-105">保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="50c2c-105">Protect global administrator accounts</span></span>

<span data-ttu-id="50c2c-106">*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="50c2c-106">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="50c2c-107">在這一節中，您透過盡可能確保系統管理員帳戶的安全，來避免您組織遭受數位攻擊。</span><span class="sxs-lookup"><span data-stu-id="50c2c-107">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="50c2c-108">若要這麼做，您必須：</span><span class="sxs-lookup"><span data-stu-id="50c2c-108">To do this, you must:</span></span>

- <span data-ttu-id="50c2c-109">使用[強式密碼](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)來建立一個以上專用的全域系統管理員帳戶，並只在需要時使用它們。</span><span class="sxs-lookup"><span data-stu-id="50c2c-109">Create more than one dedicated global administrator accounts with [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="50c2c-110">有需要時，透過將特定系統管理員角色 (例如 Exchange 系統管理員或密碼系統管理員) 指派至這些角色的其他專用帳戶或 IT 人員的使用者帳戶來執行日常管理。</span><span class="sxs-lookup"><span data-stu-id="50c2c-110">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to other dedicated accounts for those roles or user accounts of IT staff as needed.</span></span>

<span data-ttu-id="50c2c-111">如需專用的全域系統管理員帳戶，您也必須：</span><span class="sxs-lookup"><span data-stu-id="50c2c-111">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="50c2c-112">在測試使用者帳戶上測試根據使用者帳戶或條件式以存取為基礎的 Azure Multi-Factor Authentication (MFA) 設定，以確保 MFA 正確且如預測般運作。</span><span class="sxs-lookup"><span data-stu-id="50c2c-112">Test per-user account or Conditional Access-based Azure Multi-Factor Authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably.</span></span> <span data-ttu-id="50c2c-113">MFA 需要第二種形式的驗證 (例如將驗證碼傳送給智慧型手機)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-113">MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="50c2c-114">為您的全域系統管理員帳戶建立和啟用條件式存取原則，原則需要 MFA，並使用組織中可用的最嚴密次要驗證形式。</span><span class="sxs-lookup"><span data-stu-id="50c2c-114">Create and enable a Conditional Access policy for your global administrator accounts that requires MFA and uses the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="50c2c-115">如需詳細資訊，請參閱 [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) (部分內容機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-115">See [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="50c2c-116">如需進一步的保護，請參閱[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) (部分內容機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-116">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for additional protections.</span></span>

> [!Note]
> <span data-ttu-id="50c2c-117">緊急狀況下的緊急帳戶 (例如網路攻擊) 應僅使用雲端帳戶。</span><span class="sxs-lookup"><span data-stu-id="50c2c-117">Emergency accounts for break-glass scenarios in emergencies such as a cyberattack should be cloud-only accounts.</span></span> <span data-ttu-id="50c2c-118">您也可以擁有非雲端的全域系統管理員帳戶 (合格或永久)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-118">You may also have global administrator accounts (eligible or permanent) that are not cloud-only.</span></span> <span data-ttu-id="50c2c-119">如需詳細資訊，請參閱[在 Azure AD 中管理緊急存取系統管理帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) (部分內容機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-119">For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="50c2c-120">這一節的結果如下：</span><span class="sxs-lookup"><span data-stu-id="50c2c-120">The results of this section are:</span></span>

- <span data-ttu-id="50c2c-121">您的訂閱中唯一擁有全域系統管理員角色的使用者帳戶，就是專用全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="50c2c-121">The only user accounts in your subscription that have the global admin role are the dedicated global administrator accounts.</span></span> <span data-ttu-id="50c2c-122">使用以下 Azure Active Directory PowerShell for Graph 命令驗證這點：</span><span class="sxs-lookup"><span data-stu-id="50c2c-122">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="50c2c-123">管理您訂閱服務的所有其他使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。</span><span class="sxs-lookup"><span data-stu-id="50c2c-123">All other user accounts that manage your subscription services have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="50c2c-124">請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)，以取得安裝 Azure Active Directory PowerShell for Graph 模組及登入的指示。</span><span class="sxs-lookup"><span data-stu-id="50c2c-124">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="50c2c-126">若要在測試實驗室環境中練習此組態，請參閱[保護全域系統管理員帳戶測試實驗室指南](protect-global-administrator-accounts-microsoft-365-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-126">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="50c2c-127">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-127">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a><span data-ttu-id="50c2c-128">設定隨選系統管理員</span><span class="sxs-lookup"><span data-stu-id="50c2c-128">Set up on-demand administrators</span></span>

<span data-ttu-id="50c2c-129">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="50c2c-129">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="50c2c-130">在這一節中，您會設定 Azure AD Privileged Identity Management (PIM) 來減少系統管理員帳戶容易受到惡意使用者攻擊的時間。</span><span class="sxs-lookup"><span data-stu-id="50c2c-130">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="50c2c-131">PIM 可在需要時提供隨需、及時的系統管理員角色指派。</span><span class="sxs-lookup"><span data-stu-id="50c2c-131">PIM provides on-demand, just-in-time assignment of the administrator roles when needed.</span></span>  

<span data-ttu-id="50c2c-132">系統管理員帳戶不是永久系統管理員，而只是符合資格的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="50c2c-132">Instead of your administrator accounts being permanent admins, they become eligible admins.</span></span> <span data-ttu-id="50c2c-133">系統管理員角色直到有人需要時才會啟用。</span><span class="sxs-lookup"><span data-stu-id="50c2c-133">The administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="50c2c-134">到時您將完成啟用程式，將系統管理員角色在特定時間內新增至系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="50c2c-134">You'll then complete an activation process to add the administrator role to the administrator account for a specific amount of time.</span></span> <span data-ttu-id="50c2c-135">時間到期時，PIM 會從系統管理員帳戶中移除系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="50c2c-135">When the time expires, PIM removes the administrator role from the administrator account.</span></span>

<span data-ttu-id="50c2c-136">PIM 可與 Azure Active Directory Premium P2 搭配使用，隨附於 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="50c2c-136">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5.</span></span> <span data-ttu-id="50c2c-137">或者，您也可以為您的系統管理員帳戶購買個別 Azure Active Directory Premium P2 授權。</span><span class="sxs-lookup"><span data-stu-id="50c2c-137">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>

<span data-ttu-id="50c2c-138">若要為 Azure AD 租用戶和系統管理員帳戶啟用 Azure PIM，請參閱[設定 PIM 步驟](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-138">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="50c2c-139">若要開發可保護特殊存取權避免受到網路攻擊的全面性藍圖，請參閱[在 Azure AD 中保護混合式部署和雲端部署的特殊權限存取](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-139">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="50c2c-140">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pim)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a><span data-ttu-id="50c2c-141">特許存取管理</span><span class="sxs-lookup"><span data-stu-id="50c2c-141">Privileged access management</span></span>

<span data-ttu-id="50c2c-p109">特殊權限存取管理的啟用方法是透過設定原則，該原則會指定您的 Office 365 租用戶中工作型活動的 Just-In-Time 存取。它可以協助保護貴組織免於受到使用現有特殊權限系統管理員帳戶與機密資料的常設存取權或關鍵組態設定之存取權的缺口。例如，您可能會設定特殊權限存取管理原則，該原則需要明確核准的存取權，並且會變更您的 Office 365 租用戶中的組織信箱設定。</span><span class="sxs-lookup"><span data-stu-id="50c2c-p109">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="50c2c-p110">在這個步驟中，您會在 Office 365 租用戶中啟用特殊權限存取管理，並且設定特殊權限存取原則，該原則為 Office 365 資料的工作型存取以及貴組織的組態設定，提供額外的安全性。在您的 Office 365 組織中開始使用特殊權限存取有三個基本步驟：</span><span class="sxs-lookup"><span data-stu-id="50c2c-p110">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>

- <span data-ttu-id="50c2c-147">建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="50c2c-147">Creating an approver's group</span></span>
- <span data-ttu-id="50c2c-148">啟用特殊權限存取</span><span class="sxs-lookup"><span data-stu-id="50c2c-148">Enabling privileged access</span></span>
- <span data-ttu-id="50c2c-149">建立核准原則</span><span class="sxs-lookup"><span data-stu-id="50c2c-149">Creating approval policies</span></span>

<span data-ttu-id="50c2c-p111">一旦設定，特殊權限存取管理就會讓貴組織以零常設特殊權限來運作，並且針對由於此類常設系統管理存取而引發的漏洞提供一層防護。特殊權限存取需要對執行具有已定義相關聯核准原則的工作進行核准。需要執行包含在核准原則內工作的使用者必須要求存取核准並且獲得授與，才能夠具有執行原則中定義工作的必要權限。</span><span class="sxs-lookup"><span data-stu-id="50c2c-p111">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="50c2c-153">若要啟用 Office 365 特殊權限存取管理，請參閱[在 Office 365 中設定特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 主題。</span><span class="sxs-lookup"><span data-stu-id="50c2c-153">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="50c2c-154">如需詳細資訊，請參閱 [Office 365 中的特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 主題。</span><span class="sxs-lookup"><span data-stu-id="50c2c-154">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="50c2c-156">若要在測試實驗室環境中練習此組態，請參閱[特許存取管理測試實驗室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md) (部分內容機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-156">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="50c2c-157">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](identity-exit-criteria.md#crit-identity-pam)。</span><span class="sxs-lookup"><span data-stu-id="50c2c-157">As an interim checkpoint, see the [exit criteria](identity-exit-criteria.md#crit-identity-pam) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="50c2c-158">下一步</span><span class="sxs-lookup"><span data-stu-id="50c2c-158">Next step</span></span>

|||
|:-------|:-----|
|![步驟 2](./media/stepnumbers/Step2.png)| [<span data-ttu-id="50c2c-160">保護您的密碼</span><span class="sxs-lookup"><span data-stu-id="50c2c-160">Secure your passwords</span></span>](identity-secure-your-passwords.md) |

