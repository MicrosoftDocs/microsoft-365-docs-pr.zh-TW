---
title: 步驟 2：保護全域管理員帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定您的系統管理員帳戶的保護上限。
ms.openlocfilehash: ccab7c8526817ee5140a5315c56f6f8a42f085d2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866756"
---
# <a name="step-2-protect-global-administrator-accounts"></a><span data-ttu-id="12e7c-103">步驟 2：保護全域管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="12e7c-103">Step 2: Protect global administrator accounts</span></span>

<span data-ttu-id="12e7c-104">*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="12e7c-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="12e7c-p101">在本步驟中，您透過盡可能確保系統管理員帳戶的安全，來避免您組織遭受數位攻擊。若要這麼做，您必須：</span><span class="sxs-lookup"><span data-stu-id="12e7c-p101">In Step 5, you'll help prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. To do this, you must:</span></span>

- <span data-ttu-id="12e7c-107">使用非常[強式密碼](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)來建立專用的全域系統管理員帳戶，並只在需要時使用它們。</span><span class="sxs-lookup"><span data-stu-id="12e7c-107">Create dedicated global administrator accounts with very [strong passwords](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password) and use them only when necessary.</span></span>
- <span data-ttu-id="12e7c-108">有需要時，透過將特定系統管理員角色 (例如 Exchange 系統管理員或密碼系統管理員) 指派至 IT 人員的使用者帳戶來執行日常管理。</span><span class="sxs-lookup"><span data-stu-id="12e7c-108">Perform day-to-day administration by assigning specific administrator roles—such as Exchange administrator or Password administrator—to user accounts of IT staff as needed.</span></span>

<span data-ttu-id="12e7c-109">如需專用的全域系統管理員帳戶，您也必須：</span><span class="sxs-lookup"><span data-stu-id="12e7c-109">For your dedicated global admin accounts, you must also:</span></span>

1. <span data-ttu-id="12e7c-p102">在測試使用者帳戶上測試根據使用者帳戶或條件式以存取為基礎的多重要素驗證 (MFA) 設定，以確保 MFA 正確且如預測般運作。MFA 需要第二種形式的驗證 (例如將驗證碼傳送給智慧型手機)。</span><span class="sxs-lookup"><span data-stu-id="12e7c-p102">Test per-user account or conditional access-based multi-factor authentication (MFA) settings on a test user account to ensure that MFA works correctly and predictably. MFA requires a secondary form of authentication, such as a verification code sent to a smart phone.</span></span>
2. <span data-ttu-id="12e7c-p103">為每一個專用的 Office 365 全域系統管理員帳戶設定 MFA ，並使用貴組織中可供使用的最強型次要驗證。如需詳細資訊，請參閱[多重要素驗證](identity-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="12e7c-p103">Configure MFA for each of the dedicated Office 365 global administrator accounts, and use the strongest form of secondary authentication available in your organization. See [Multi-factor authentication](identity-multi-factor-authentication.md) for more information.</span></span>
2. <span data-ttu-id="12e7c-p104">使用條件訪問策略來要求全域系統管理員帳戶的 MFA。如需詳細資訊，請參閱[保護系統管理員帳戶](identity-access-prerequisites.md#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="12e7c-p104">Use a conditional access policy to require MFA for global administrator accounts. See [Protecting administrator accounts](identity-access-prerequisites.md#protecting-administrator-accounts) for more information.</span></span>
4. <span data-ttu-id="12e7c-p105">使用 Office 365 雲端 App 安全性原則來監控全域系統管理員帳戶活動。如需詳細資訊，請參閱[設定增強的 Office 365 安全性](infoprotect-configure-increased-security-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="12e7c-p105">Use an Office 365 Cloud App Security policy to monitor global administrator account activity. See [Information protection for Microsoft 365 Enterprise](infoprotect-configure-increased-security-office-365.md) for more information.</span></span>

<span data-ttu-id="12e7c-118">請參閱[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)以了解設定的相關詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="12e7c-118">See [Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) for more information about configuration.</span></span>

> [!Note]
> <span data-ttu-id="12e7c-p106">組織應使用純雲端的身分識別來建立特殊權限的帳戶 (例如全域系統管理員)，以供緊急情況使用 (例如網路攻擊)。如需詳細資訊，請參閱[管理 Azure AD 中的緊急存取系統管理帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="12e7c-p106">Organizations should use cloud-only identities to create privileged accounts, such as global administrators, for break-glass scenarios in emergencies, such as a cyberattack. For more information, see [Manage emergency-access administrative accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span>

<span data-ttu-id="12e7c-121">此步驟的結果如下：</span><span class="sxs-lookup"><span data-stu-id="12e7c-121">The results of this step are:</span></span>

- <span data-ttu-id="12e7c-p107">在您訂閱中擁有全域系統管理員角色的唯一使用者帳戶，就是新一組專用全域系統管理員帳戶。請透過下列 Windows Azure AD V2 PowerShell 命令來進行確認：</span><span class="sxs-lookup"><span data-stu-id="12e7c-p107">The only user accounts in your subscription that have the global admin role are the new set of dedicated global administrator accounts. Verify this with the following Windows Azure AD V2 PowerShell command:</span></span> 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- <span data-ttu-id="12e7c-124">管理您訂閱的所有其他日常使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。</span><span class="sxs-lookup"><span data-stu-id="12e7c-124">All other everyday user accounts that manage your subscription have admin roles assigned that are associated with their job responsibilities.</span></span>

> [!Note]
> <span data-ttu-id="12e7c-125">請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) 以了解安裝 Azure AD V2 PowerShell 模組與登入的指示。</span><span class="sxs-lookup"><span data-stu-id="12e7c-125">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure AD V2 PowerShell module and signing in.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="12e7c-127">測試實驗室指南：保護全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="12e7c-127">Test Lab Guide: Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="12e7c-128">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="12e7c-128">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-global-admin) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="12e7c-129">下一步</span><span class="sxs-lookup"><span data-stu-id="12e7c-129">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="12e7c-130">設定隨選全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="12e7c-130">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |

