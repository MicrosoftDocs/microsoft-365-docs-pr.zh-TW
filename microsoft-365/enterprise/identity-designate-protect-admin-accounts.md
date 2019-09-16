---
title: 步驟 2：保護您的特殊權限身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定您的系統管理員帳戶的保護上限。
ms.openlocfilehash: b9c645d597dfeb2bdc42e2b0b7615252dc1f5ecb
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981904"
---
# <a name="step-2-secure-your-privileged-identities"></a><span data-ttu-id="33fde-103">步驟 2：保護您的特殊權限身分識別</span><span class="sxs-lookup"><span data-stu-id="33fde-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a><span data-ttu-id="33fde-104">保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="33fde-104">Protect global administrator accounts</span></span>

<span data-ttu-id="33fde-105">*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="33fde-105">*This is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="33fde-106">在這一節中，您透過盡可能確保系統管理員帳戶的安全，來避免您組織遭受數位攻擊。</span><span class="sxs-lookup"><span data-stu-id="33fde-106">In this section, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="33fde-107">若要這麼做，您必須：</span><span class="sxs-lookup"><span data-stu-id="33fde-107">To do this, you must:</span></span>

- <span data-ttu-id="33fde-108">使用非常[強式密碼](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)來建立專用的全域系統管理員帳戶，並只在需要時使用它們。</span><span class="sxs-lookup"><span data-stu-id="33fde-108">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="33fde-109">有需要時，透過將特定系統管理員角色 (例如 Exchange 系統管理員或密碼系統管理員) 指派至 IT 人員的使用者帳戶來執行日常管理。</span><span class="sxs-lookup"><span data-stu-id="33fde-109">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="33fde-110">如需專用的全域系統管理員帳戶，您也必須：</span><span class="sxs-lookup"><span data-stu-id="33fde-110">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="33fde-p102">在測試使用者帳戶上測試根據使用者帳戶或條件式以存取為基礎的多重要素驗證 (MFA) 設定，以確保 MFA 正確且如預測般運作。MFA 需要第二種形式的驗證 (例如將驗證碼傳送給智慧型手機)。</span><span class="sxs-lookup"><span data-stu-id="33fde-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="33fde-113">為您的全域系統管理員帳戶啟用**基準原則：管理員需要進行 MFA** 條件式存取原則，並使用組織中可用的最嚴密次要驗證形式。</span><span class="sxs-lookup"><span data-stu-id="33fde-113">Enable the **Baseline policy: Require MFA for admins** conditional access policy for your global administrator accounts and use the strongest form of secondary authentication available in your organization.</span></span> <span data-ttu-id="33fde-114">如需詳細資訊，請參閱[多重要素驗證](identity-access-prerequisites.md#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="33fde-114">See [Multi-factor authentication](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>

<span data-ttu-id="33fde-115">如需進一步的保護，請參閱[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations)。</span><span class="sxs-lookup"><span data-stu-id="33fde-115">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="33fde-p104">組織應使用純雲端的身分識別來建立特殊權限的帳戶 (例如全域系統管理員)，以供緊急情況使用 (例如網路攻擊)。如需詳細資訊，請參閱[管理 Azure AD 中的緊急存取系統管理帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="33fde-p104">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="33fde-118">這一節的結果如下：</span><span class="sxs-lookup"><span data-stu-id="33fde-118">The results of this section are:</span></span>

- <span data-ttu-id="33fde-119">您的訂閱中唯一擁有全域系統管理員角色的使用者帳戶，就是專用全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="33fde-119">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts.</span></span> <span data-ttu-id="33fde-120">使用以下 Azure Active Directory PowerShell for Graph 命令驗證這點：</span><span class="sxs-lookup"><span data-stu-id="33fde-120">Verify this with the following Azure Active Directory PowerShell for Graph command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="33fde-121">管理您訂閱服務的所有其他使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。</span><span class="sxs-lookup"><span data-stu-id="33fde-121">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="33fde-122">請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)，以取得安裝 Azure Active Directory PowerShell for Graph 模組及登入的指示。</span><span class="sxs-lookup"><span data-stu-id="33fde-122">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="33fde-124">若要在測試實驗室環境中練習此組態，請參閱[保護全域系統管理員帳戶測試實驗室指南](protect-global-administrator-accounts-microsoft-365-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="33fde-124">To practice this configuration in a test lab environment, see the [Protect global administrator accounts Test Lab Guide](protect-global-administrator-accounts-microsoft-365-test-environment.md).</span></span> |
|||

<span data-ttu-id="33fde-125">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="33fde-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this section.</span></span>


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a><span data-ttu-id="33fde-126">設定隨選全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="33fde-126">Set up on-demand global administrators</span></span>

<span data-ttu-id="33fde-127">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="33fde-127">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="33fde-128">在這一節中，您會設定 Azure AD Privileged Identity Management (PIM) 來減少全域系統管理員帳戶容易受到惡意使用者攻擊的時間。</span><span class="sxs-lookup"><span data-stu-id="33fde-128">In this section, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users.</span></span> <span data-ttu-id="33fde-129">PIM 可在需要時提供隨需、即時的全域系統管理員角色指派。</span><span class="sxs-lookup"><span data-stu-id="33fde-129">PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="33fde-p107">全域系統管理員帳戶不再是永久管理員，而是變為合格的管理員。全域系統管理員角色在有人需要它之前為無作用狀態。您需要完成啟動程序，在一段特定時間內將全域系統管理員角色新增到全域系統管理員帳戶。時間到期後，PIM 會從全域系統管理員帳戶中移除此全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="33fde-p107">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="33fde-p108">Microsoft 365 企業版 E5 隨附 Azure Active Directory Premium P2，而 P2 便有 PIM 功能。或者，您可以為您的全域系統管理員帳戶購買單獨的 Azure Active Directory Premium P2 授權。</span><span class="sxs-lookup"><span data-stu-id="33fde-p108">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="33fde-136">若要為 Azure AD 租用戶和全域系統管理員帳戶啟用 Azure PIM，請參閱[什麼是 Azure AD Privileged Identity Management？](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</span><span class="sxs-lookup"><span data-stu-id="33fde-136">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="33fde-137">若要開發可保護特殊存取權避免受到網路攻擊的全面性藍圖，請參閱[在 Azure AD 中保護混合式部署和雲端部署的特殊權限存取](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="33fde-137">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="33fde-138">作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pim)。</span><span class="sxs-lookup"><span data-stu-id="33fde-138">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this section.</span></span>


## <a name="next-step"></a><span data-ttu-id="33fde-139">下一步</span><span class="sxs-lookup"><span data-stu-id="33fde-139">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="33fde-140">設定混合式身分識別</span><span class="sxs-lookup"><span data-stu-id="33fde-140">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |

