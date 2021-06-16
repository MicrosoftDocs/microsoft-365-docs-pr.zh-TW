---
title: 保護您的 Microsoft 365 全域管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: 本文提供保護您 Microsoft 365 訂閱之全域管理員存取權的相關資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c929651f3e70a1aeef16cdf48d853d675820833
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926544"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="63493-103">保護您的 Microsoft 365 全域管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="63493-103">Protect your Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="63493-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="63493-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="63493-105">Microsoft 365 訂閱的安全性違規（包括資訊竊取和網路釣魚攻擊）通常是透過威脅 Microsoft 365 全域管理員帳戶的認證來完成。</span><span class="sxs-lookup"><span data-stu-id="63493-105">Security breaches of a Microsoft 365 subscription, including information harvesting and phishing attacks, are typically done by compromising the credentials of a Microsoft 365 global administrator account.</span></span> <span data-ttu-id="63493-106">雲端的安全性是您和 Microsoft 之間的合作關係：</span><span class="sxs-lookup"><span data-stu-id="63493-106">Security in the cloud is a partnership between you and Microsoft:</span></span>
  
- <span data-ttu-id="63493-107">Microsoft 雲端服務是以信任和安全性的基礎來建立的。</span><span class="sxs-lookup"><span data-stu-id="63493-107">Microsoft cloud services are built on a foundation of trust and security.</span></span> <span data-ttu-id="63493-108">Microsoft 提供的安全性控制和功能可協助您保護您的資料和應用程式。</span><span class="sxs-lookup"><span data-stu-id="63493-108">Microsoft provides you security controls and capabilities to help you protect your data and applications.</span></span>
    
- <span data-ttu-id="63493-109">您擁有資料和身分識別，以及保護它們的責任、內部部署資源的安全性，以及您所控制之雲端元件的安全性。</span><span class="sxs-lookup"><span data-stu-id="63493-109">You own your data and identities and the responsibility for protecting them, the security of your on-premises resources, and the security of cloud components you control.</span></span>
    
<span data-ttu-id="63493-110">Microsoft 提供的功能可協助保護您的組織，但只有在您使用這些功能時，才會有效。</span><span class="sxs-lookup"><span data-stu-id="63493-110">Microsoft provides capabilities to help protect your organization, but they are effective only if you use them.</span></span> <span data-ttu-id="63493-111">如果您不使用它們，可能會受到攻擊。</span><span class="sxs-lookup"><span data-stu-id="63493-111">If you do not use them, you may be vulnerable to attack.</span></span> <span data-ttu-id="63493-112">為了保護您的全域系統管理員帳戶，Microsoft 可在這裡協助您瞭解下列各專案的詳細指示：</span><span class="sxs-lookup"><span data-stu-id="63493-112">To protect your global administrator accounts, Microsoft is here to help you with detailed instructions to:</span></span>
  
1. <span data-ttu-id="63493-113">建立專屬的 Microsoft 365 全域管理員帳戶，並只在必要時使用。</span><span class="sxs-lookup"><span data-stu-id="63493-113">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary.</span></span>
    
2. <span data-ttu-id="63493-114">為專屬 Microsoft 365 全域管理員帳戶設定多重要素驗證，並使用最強形式的次要驗證。</span><span class="sxs-lookup"><span data-stu-id="63493-114">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts and use the strongest form of secondary authentication.</span></span>
    
> [!Note]
> <span data-ttu-id="63493-115">雖然本文著重于全域管理員帳戶，您還是應該考慮是否有其他具有廣域許可權的帳戶，以存取您訂閱中的資料，例如 eDiscovery 管理員或安全性或合規性管理員帳戶，都應該以相同的方式加以保護。</span><span class="sxs-lookup"><span data-stu-id="63493-115">Although this article is focused on global administrator accounts, you should consider whether additional accounts with wide-ranging permissions to access the data in your subscription, such as eDiscovery administrator or security or compliance administrator accounts, should be protected in the same way.</span></span> <br > <span data-ttu-id="63493-116">您可以建立全域管理員帳戶，而不需要新增任何授權。</span><span class="sxs-lookup"><span data-stu-id="63493-116">A global administrator account can be created without adding any licenses.</span></span>
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a><span data-ttu-id="63493-117">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="63493-117">Step 1.</span></span> <span data-ttu-id="63493-118">建立專用的 Microsoft 365 全域管理員帳戶，並只在必要時使用它們</span><span class="sxs-lookup"><span data-stu-id="63493-118">Create dedicated Microsoft 365 global administrator accounts and use them only when necessary</span></span>

<span data-ttu-id="63493-119">需要全域管理員許可權的系統管理工作相對較少，例如指派角色給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-119">There are relatively few administrative tasks, such as assigning roles to user accounts, that require global administrator privileges.</span></span> <span data-ttu-id="63493-120">因此，請執行下列步驟，而不是使用已獲指派全域系統管理員角色的日常使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="63493-120">Therefore, instead of using everyday user accounts that have been assigned the global admin role, do these steps:</span></span>
  
1. <span data-ttu-id="63493-121">決定已指派全域系統管理員角色的使用者帳戶集。</span><span class="sxs-lookup"><span data-stu-id="63493-121">Determine the set of user accounts that have been assigned the global admin role.</span></span> <span data-ttu-id="63493-122">您可以在 Microsoft 365 系統管理中心或下列 azure Active (azure AD) 目錄 PowerShell 中執行這項作業，以 Graph 命令：</span><span class="sxs-lookup"><span data-stu-id="63493-122">You can do this in the Microsoft 365 admin center or with the following Azure Active (Azure AD) Directory PowerShell for Graph command:</span></span>
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. <span data-ttu-id="63493-123">使用已獲指派全域系統管理員角色的使用者帳戶，登入您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="63493-123">Sign into your Microsoft 365 subscription with a user account that has been assigned the global admin role.</span></span>
    
3. <span data-ttu-id="63493-124">建立最多四個專用全域系統管理員使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-124">Create up to a maximum of four dedicated global administrator user accounts.</span></span> <span data-ttu-id="63493-125">**使用強式密碼的長度至少12個字元。**</span><span class="sxs-lookup"><span data-stu-id="63493-125">**Use strong passwords at least 12 characters long.**</span></span> <span data-ttu-id="63493-126">請參閱 [建立強式密碼](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="63493-126">See [Create a strong password](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) for more information.</span></span> <span data-ttu-id="63493-127">將新帳戶的密碼儲存在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="63493-127">Store the passwords for the new accounts in a secure location.</span></span> 
    
4. <span data-ttu-id="63493-128">將全域管理員角色指派給每個新的專屬全域系統管理員使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-128">Assign the global admin role to each of the new dedicated global administrator user accounts.</span></span>
    
5. <span data-ttu-id="63493-129">登出 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="63493-129">Sign out of Microsoft 365.</span></span>
    
6. <span data-ttu-id="63493-130">使用其中一個新的專屬全域系統管理員使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="63493-130">Sign in with one of the new dedicated global administrator user accounts.</span></span>
    
7. <span data-ttu-id="63493-131">針對每個已指派步驟1之全域系統管理員角色的現有使用者帳戶：</span><span class="sxs-lookup"><span data-stu-id="63493-131">For each existing user account that had been assigned the global admin role from step 1:</span></span>
    
  - <span data-ttu-id="63493-132">移除全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="63493-132">Remove the global admin role.</span></span>
    
  - <span data-ttu-id="63493-133">將系統管理員角色指派給適當于該使用者工作職能和責任的帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-133">Assign admin roles to the account that are appropriate to that user's job function and responsibility.</span></span> <span data-ttu-id="63493-134">如需 Microsoft 365 中各種系統管理員角色的詳細資訊，請參閱[關於系統管理員角色](/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="63493-134">For more information about various admin roles in Microsoft 365, see [About admin roles](/office365/admin/add-users/about-admin-roles).</span></span>
    
8. <span data-ttu-id="63493-135">登出 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="63493-135">Sign out of Microsoft 365.</span></span>
    
<span data-ttu-id="63493-136">結果應該是：</span><span class="sxs-lookup"><span data-stu-id="63493-136">The results should be:</span></span>
  
- <span data-ttu-id="63493-137">您的訂閱中唯一擁有全域系統管理員角色的使用者帳戶，就是新建立的一組專用全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-137">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="63493-138">使用下列 PowerShell 命令進行驗證：</span><span class="sxs-lookup"><span data-stu-id="63493-138">Verify this with the following PowerShell command:</span></span>
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- <span data-ttu-id="63493-139">管理您訂閱的所有其他日常使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。</span><span class="sxs-lookup"><span data-stu-id="63493-139">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>
    
<span data-ttu-id="63493-140">自現在起，您只需在需要全域系統管理員許可權的工作中登入專用全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-140">From this moment onward, you sign in with the dedicated global administrator accounts only for tasks that require global administrator privileges.</span></span> <span data-ttu-id="63493-141">您必須將其他管理角色指派給使用者帳戶，才能進行其他所有 Microsoft 365 管理。</span><span class="sxs-lookup"><span data-stu-id="63493-141">All other Microsoft 365 administration must be done by assigning other administration roles to user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63493-142">這需要其他步驟以您的日常使用者帳戶登出，並以專用全域管理員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="63493-142">This does require additional steps to sign out as your everyday user account and sign in with a dedicated global administrator account.</span></span> <span data-ttu-id="63493-143">但是這只需要偶爾進行全域管理員作業。</span><span class="sxs-lookup"><span data-stu-id="63493-143">But this only needs to be done occasionally for global administrator operations.</span></span> <span data-ttu-id="63493-144">請考慮在全域管理員帳戶遭到破壞之後復原您的 Microsoft 365 訂閱需要許多步驟。</span><span class="sxs-lookup"><span data-stu-id="63493-144">Consider that recovering your Microsoft 365 subscription after a global administrator account breach requires a lot more steps.</span></span>
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a><span data-ttu-id="63493-145">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="63493-145">Step 2.</span></span> <span data-ttu-id="63493-146">為專用 Microsoft 365 全域管理員帳戶設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="63493-146">Configure multi-factor authentication for your dedicated Microsoft 365 global administrator accounts</span></span>

<span data-ttu-id="63493-147">多重要素驗證 (MFA) 需要帳戶名稱和密碼以外的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="63493-147">Multi-factor authentication (MFA) requires additional information beyond the account name and password.</span></span> <span data-ttu-id="63493-148">Microsoft 365 支援下列其他驗證方法：</span><span class="sxs-lookup"><span data-stu-id="63493-148">Microsoft 365 supports these additional verification methods:</span></span>
  
- <span data-ttu-id="63493-149">Microsoft Authenticator 應用程式</span><span class="sxs-lookup"><span data-stu-id="63493-149">The Microsoft Authenticator app</span></span>

- <span data-ttu-id="63493-150">電話</span><span class="sxs-lookup"><span data-stu-id="63493-150">A phone call</span></span>
    
- <span data-ttu-id="63493-151">透過短信傳送的隨機產生的驗證程式代碼</span><span class="sxs-lookup"><span data-stu-id="63493-151">A randomly generated verification code sent through a text message</span></span>
    
- <span data-ttu-id="63493-152">智慧卡 (虛擬或實體)</span><span class="sxs-lookup"><span data-stu-id="63493-152">A smart card (virtual or physical)</span></span>
    
- <span data-ttu-id="63493-153">生物特徵辨識裝置</span><span class="sxs-lookup"><span data-stu-id="63493-153">A biometric device</span></span>
    
>[!Note]
><span data-ttu-id="63493-154">針對必須遵守全國研究院標準及技術的組織 (NIST) 標準，會限制使用電話通話或以文字訊息為基礎的其他驗證方法。</span><span class="sxs-lookup"><span data-stu-id="63493-154">For organizations that must adhere to National Institute of Standards and Technology (NIST) standards, the use of a phone call or text message-based additional verification methods are restricted.</span></span> <span data-ttu-id="63493-155">如需詳細資訊，請按一下 [這裡](https://pages.nist.gov/800-63-FAQ/#q-b01) 。</span><span class="sxs-lookup"><span data-stu-id="63493-155">Click [here](https://pages.nist.gov/800-63-FAQ/#q-b01) for the details.</span></span>
>

<span data-ttu-id="63493-156">如果您是一位小型企業，使用僅儲存在雲端中的使用者帳戶 (僅限雲端身分識別模型) 中， [設定 mfa 以設定](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 使用電話的 mfa，或為每一個專用全域管理員帳戶傳送至 smart phone 的文字訊息驗證碼。</span><span class="sxs-lookup"><span data-stu-id="63493-156">If you are a small business that is using user accounts stored only in the cloud (the cloud-only identity model), [set up MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) to configure MFA using a phone call or a text message verification code sent to a smart phone for each dedicated global administrator account.</span></span>
    
<span data-ttu-id="63493-157">如果您是較大的組織，且使用 Microsoft 365 混合式身分識別模型，您會有更多驗證選項。</span><span class="sxs-lookup"><span data-stu-id="63493-157">If you are a larger organization that is using a Microsoft 365 hybrid identity model, you have more verification options.</span></span> <span data-ttu-id="63493-158">如果您已將安全性基礎結構放在適當的次要驗證方法中，請針對適當的驗證方法， [設定 MFA 並設定](../admin/security-and-compliance/set-up-multi-factor-authentication.md) 每一個專用全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-158">If you have the security infrastructure already in place for a stronger secondary authentication method, [set up MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) and configure each dedicated global administrator account for the appropriate verification method.</span></span>
  
<span data-ttu-id="63493-159">如果所需之強驗證方法的安全性基礎結構不存在，且無法在 Microsoft 365 MFA 中運作，強烈建議您使用 Microsoft Authenticator 應用程式、電話或將電子郵件驗證碼傳送給全域系統管理員帳戶，以作為過渡的安全性度量，設定具有 MFA 的專屬全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="63493-159">If the security infrastructure for the desired stronger verification method is not in place and functioning for Microsoft 365 MFA, we strongly recommend that you configure dedicated global administrator accounts with MFA using the Microsoft Authenticator app, a phone call, or a text message verification code sent to a smart phone for your global administrator accounts as an interim security measure.</span></span> <span data-ttu-id="63493-160">請勿留下專屬全域管理員帳戶，除非 MFA 提供額外的保護。</span><span class="sxs-lookup"><span data-stu-id="63493-160">Do not leave your dedicated global administrator accounts without the additional protection provided by MFA.</span></span>
  
<span data-ttu-id="63493-161">如需詳細資訊，請參閱[MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)。</span><span class="sxs-lookup"><span data-stu-id="63493-161">For more information, see [MFA for Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md).</span></span>
  
<span data-ttu-id="63493-162">若要使用 MFA 和 PowerShell 連接至 Microsoft 365 服務，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="63493-162">To connect to Microsoft 365 services with MFA and PowerShell, see these articles:</span></span>

- [<span data-ttu-id="63493-163">PowerShell 使用者帳戶、群組和授權的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63493-163">PowerShell for Microsoft 365 for user accounts, groups, and licenses</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="63493-164">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63493-164">Microsoft Teams</span></span>](/microsoftteams/teams-powershell-install)
- [<span data-ttu-id="63493-165">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="63493-165">Exchange Online</span></span>](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [<span data-ttu-id="63493-166">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="63493-166">SharePoint Online</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [<span data-ttu-id="63493-167">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="63493-167">Skype for Business Online</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a><span data-ttu-id="63493-168">企業組織的其他保護</span><span class="sxs-lookup"><span data-stu-id="63493-168">Additional protections for enterprise organizations</span></span>

<span data-ttu-id="63493-169">請使用這些額外的方法，以確保您的全域系統管理員帳戶和您使用它執行的設定盡可能安全。</span><span class="sxs-lookup"><span data-stu-id="63493-169">Use these additional methods to ensure that your global administrator account, and the configuration that you perform using it, are as secure as possible.</span></span>
  
### <a name="privileged-access-workstation"></a><span data-ttu-id="63493-170">許可權存取工作站</span><span class="sxs-lookup"><span data-stu-id="63493-170">Privileged access workstation</span></span>

<span data-ttu-id="63493-171">為了確保高特權工作的執行盡可能安全，請使用一種特殊許可權存取工作站 (PAW) 。</span><span class="sxs-lookup"><span data-stu-id="63493-171">To ensure that the execution of highly privileged tasks is as secure as possible, use a privileged access workstation (PAW).</span></span> <span data-ttu-id="63493-172">PAW 是一種專用的電腦，只用于機密設定工作，例如需要全域管理員帳戶的 Microsoft 365 設定。</span><span class="sxs-lookup"><span data-stu-id="63493-172">A PAW is a dedicated computer that is only used for sensitive configuration tasks, such as Microsoft 365 configuration that requires a global administrator account.</span></span> <span data-ttu-id="63493-173">由於這部電腦不會在每日使用網際網路流覽或傳送電子郵件，因此可從網際網路攻擊和威脅中獲得更好的保護。</span><span class="sxs-lookup"><span data-stu-id="63493-173">Because this computer is not used daily for Internet browsing or email, it is better protected from Internet attacks and threats.</span></span>
  
<span data-ttu-id="63493-174">如需如何設定 PAW 的指示，請參閱 [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) 。</span><span class="sxs-lookup"><span data-stu-id="63493-174">For instructions on how to set up a PAW, see [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices).</span></span>

<span data-ttu-id="63493-175">若要為 Azure AD 租用戶和系統管理員帳戶啟用 Azure PIM，請參閱[設定 PIM 步驟](/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="63493-175">To enable Azure PIM for your Azure AD tenant and administrator accounts, see the [steps to configure PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="63493-176">若要開發可保護特殊存取權避免受到網路攻擊的全面性藍圖，請參閱[在 Azure AD 中保護混合式部署和雲端部署的特殊權限存取](/azure/active-directory/admin-roles-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="63493-176">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](/azure/active-directory/admin-roles-best-practices).</span></span>

### <a name="azure-ad-privileged-identity-management"></a><span data-ttu-id="63493-177">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="63493-177">Azure AD Privileged Identity Management</span></span>

<span data-ttu-id="63493-178">您可以使用 Azure AD Privileged Identity Management (PIM) 為全域系統管理員角色在需要時，隨意指派全域管理員角色，而不是將全域系統管理員帳戶永久指派給全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="63493-178">Rather than having your global administrator accounts be permanently assigned the global administrator role, you can use Azure AD Privileged Identity Management (PIM) to enable on-demand, just-in-time assignment of the global administrator role when it is needed.</span></span>
  
<span data-ttu-id="63493-179">您的全域系統管理員帳戶會從「永久系統管理員」變為「具有資格的管理員」。</span><span class="sxs-lookup"><span data-stu-id="63493-179">Your global administrator accounts go from being permanent admins to eligible admins.</span></span> <span data-ttu-id="63493-180">全域系統管理員角色會停用，直到某人需要為止。</span><span class="sxs-lookup"><span data-stu-id="63493-180">The global administrator role is inactive until someone needs it.</span></span> <span data-ttu-id="63493-181">然後，您會完成啟用程式，將全域系統管理員角色新增到全域管理員帳戶中的預先決定的時間長度。</span><span class="sxs-lookup"><span data-stu-id="63493-181">You then complete an activation process to add the global administrator role to the global administrator account for a predetermined amount of time.</span></span> <span data-ttu-id="63493-182">當時間到期時，PIM 會從全域管理員帳戶移除全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="63493-182">When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>
  
<span data-ttu-id="63493-183">使用 PIM 和此程式可大幅減少全域管理員帳戶受到惡意使用者攻擊和使用的時間量。</span><span class="sxs-lookup"><span data-stu-id="63493-183">Using PIM and this process significantly reduces the amount of time that your global administrator accounts are vulnerable to attack and use by malicious users.</span></span>

<span data-ttu-id="63493-184">PIM 可與 Azure Active Directory Premium P2 搭配使用，隨附於 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="63493-184">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 E5.</span></span> <span data-ttu-id="63493-185">或者，您也可以為您的系統管理員帳戶購買個別 Azure Active Directory Premium P2 授權。</span><span class="sxs-lookup"><span data-stu-id="63493-185">Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your administrator accounts.</span></span>
  
<span data-ttu-id="63493-186">如需詳細資訊，請參閱[AZURE AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="63493-186">For more information, see [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>
  

### <a name="privileged-access-management"></a><span data-ttu-id="63493-187">特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="63493-187">Privileged access management</span></span>

<span data-ttu-id="63493-p121">特殊權限存取管理的啟用方法是透過設定原則，該原則會指定您的租用戶中工作型活動的 Just-In-Time 存取。其可協助保護貴組織免於受到使用現有特殊權限系統管理員帳戶與機密資料的常設存取權或關鍵組態設定之存取權的缺口。例如，您可能會設定特殊權限存取管理原則，該原則需要明確核准的存取權，並且會變更您的租用戶中的組織信箱設定。</span><span class="sxs-lookup"><span data-stu-id="63493-p121">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="63493-p122">在這個步驟中，您會在租用戶中啟用特殊權限存取管理，並且設定特殊權限存取原則，該原則為資料的工作型存取以及貴組織的組態設定，提供額外的安全性。在您的組織中開始使用特殊權限存取有三個基本步驟：</span><span class="sxs-lookup"><span data-stu-id="63493-p122">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization. There are three basic steps to get started with privileged access in your organization:</span></span>

- <span data-ttu-id="63493-193">建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="63493-193">Creating an approver's group</span></span>
- <span data-ttu-id="63493-194">啟用特殊權限存取</span><span class="sxs-lookup"><span data-stu-id="63493-194">Enabling privileged access</span></span>
- <span data-ttu-id="63493-195">建立核准原則</span><span class="sxs-lookup"><span data-stu-id="63493-195">Creating approval policies</span></span>

<span data-ttu-id="63493-196">「特權存取管理」可讓您的組織以零的許可權運作，並針對因這類系統管理存取而產生的漏洞提供一層防護。</span><span class="sxs-lookup"><span data-stu-id="63493-196">Privileged access management enables your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="63493-197">「特權存取」需要核准，以執行任何已定義相關核准原則的任務。</span><span class="sxs-lookup"><span data-stu-id="63493-197">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="63493-198">需要執行核准原則中所包含之工作的使用者，必須要求並授與「存取權核准」。</span><span class="sxs-lookup"><span data-stu-id="63493-198">Users needing to execute tasks included in the approval policy must request and be granted access approval.</span></span>

<span data-ttu-id="63493-199">若要啟用特殊許可權存取管理，請參閱設定特殊許可權 [存取管理](/office365/securitycompliance/privileged-access-management-configuration)。</span><span class="sxs-lookup"><span data-stu-id="63493-199">To enable privileged access management, see [Configure privileged access management](/office365/securitycompliance/privileged-access-management-configuration).</span></span>

<span data-ttu-id="63493-200">如需詳細資訊，請參閱「特殊許可權 [存取管理](/office365/securitycompliance/privileged-access-management-overview)」。</span><span class="sxs-lookup"><span data-stu-id="63493-200">For more information, see [Privileged access management](/office365/securitycompliance/privileged-access-management-overview).</span></span>

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a><span data-ttu-id="63493-201">Microsoft 365 記錄的安全性資訊和事件管理 (SIEM) 軟體</span><span class="sxs-lookup"><span data-stu-id="63493-201">Security information and event management (SIEM) software for Microsoft 365 logging</span></span>

<span data-ttu-id="63493-202">在伺服器上執行的 SIEM 軟體會即時分析應用程式和網路硬體所建立的安全性警示和事件。</span><span class="sxs-lookup"><span data-stu-id="63493-202">SIEM software run on a server performs real-time analysis of security alerts and events created by applications and network hardware.</span></span> <span data-ttu-id="63493-203">若要讓您的 SIEM 伺服器在其分析和報告功能中包含 Microsoft 365 的安全性警示和事件，請將 Azure AD 整合到您的 SEIM。</span><span class="sxs-lookup"><span data-stu-id="63493-203">To allow your SIEM server to include Microsoft 365 security alerts and events in its analysis and reporting functions, integrate Azure AD into you SEIM.</span></span> <span data-ttu-id="63493-204">請參閱[Azure 記錄整合簡介](/azure/security/security-azure-log-integration-overview)。</span><span class="sxs-lookup"><span data-stu-id="63493-204">See [Introduction to Azure Log Integration](/azure/security/security-azure-log-integration-overview).</span></span>

## <a name="next-step"></a><span data-ttu-id="63493-205">下一步</span><span class="sxs-lookup"><span data-stu-id="63493-205">Next step</span></span>

<span data-ttu-id="63493-206">如果您正在設定 Microsoft 365 訂閱的身分識別，請參閱：</span><span class="sxs-lookup"><span data-stu-id="63493-206">If you're setting up identity for your Microsoft 365 subscription, see:</span></span>

- <span data-ttu-id="63493-207">[僅限雲端](cloud-only-identities.md) 身分識別（如果您使用僅限雲端身分識別）</span><span class="sxs-lookup"><span data-stu-id="63493-207">[Cloud-only identities](cloud-only-identities.md) if you're using cloud-only identity</span></span>
- <span data-ttu-id="63493-208">如果您使用的是混合身分識別，[準備目錄同步](prepare-for-directory-synchronization.md)處理</span><span class="sxs-lookup"><span data-stu-id="63493-208">[Prepare for directory synchronization](prepare-for-directory-synchronization.md) if you're using hybrid identity</span></span>

  
## <a name="see-also"></a><span data-ttu-id="63493-209">另請參閱</span><span class="sxs-lookup"><span data-stu-id="63493-209">See also</span></span>

[<span data-ttu-id="63493-210">Microsoft 365 安全性藍圖</span><span class="sxs-lookup"><span data-stu-id="63493-210">Microsoft 365 security roadmap</span></span>](/office365/securitycompliance/security-roadmap)