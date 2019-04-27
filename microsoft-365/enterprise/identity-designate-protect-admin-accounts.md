---
title: 步驟 2：保護您的特殊權限身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定您的系統管理員帳戶的保護上限。
ms.openlocfilehash: 0be82fc6f431001c69e79a0a26007c54a87424c3
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353085"
---
# <a name="step-2-secure-your-privileged-identities"></a>步驟 2：保護您的特殊權限身分識別

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>保護全域系統管理員帳戶

*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您透過盡可能確保系統管理員帳戶的安全，來避免您組織遭受數位攻擊。 若要這麼做，您必須：

- 使用非常[強式密碼](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)來建立專用的全域系統管理員帳戶，並只在需要時使用它們。
- 有需要時，透過將特定系統管理員角色 (例如 Exchange 系統管理員或密碼系統管理員) 指派至 IT 人員的使用者帳戶來執行日常管理。

如需專用的全域系統管理員帳戶，您也必須：

1. 在測試使用者帳戶上測試根據使用者帳戶或條件式以存取為基礎的多重要素驗證 (MFA) 設定，以確保 MFA 正確且如預測般運作。MFA 需要第二種形式的驗證 (例如將驗證碼傳送給智慧型手機)。
2. 為每一個專用的 Office 365 全域系統管理員帳戶設定 MFA ，並使用貴組織中可供使用的最強型次要驗證。如需詳細資訊，請參閱[多重要素驗證](identity-multi-factor-authentication.md#identity-mfa)。
2. 使用條件訪問策略來要求全域系統管理員帳戶的 MFA。如需詳細資訊，請參閱[保護系統管理員帳戶](identity-access-prerequisites.md#protecting-administrator-accounts)。

請參閱[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)以了解設定的相關詳細資訊。

> [!Note]
> 組織應使用純雲端的身分識別來建立特殊權限的帳戶 (例如全域系統管理員)，以供緊急情況使用 (例如網路攻擊)。如需詳細資訊，請參閱[管理 Azure AD 中的緊急存取系統管理帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。

這一節的結果如下：

- 您的訂閱中唯一擁有全域系統管理員角色的使用者帳戶，就是新建立的一組專用全域系統管理員帳戶。 使用以下 Azure Active Directory PowerShell for Graph 命令驗證這點： 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 管理您訂閱的所有其他日常使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。

> [!Note]
> 請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)，以取得安裝 Azure Active Directory PowerShell for Graph 模組及登入的指示。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：保護全域系統管理員帳戶](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-global-admin)。


<a name="identity-pim"></a>
## <a name="set-up-on-demand-global-administrators"></a>設定隨選全域系統管理員

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*

在這一節中，您會設定 Azure AD Privileged Identity Management (PIM) 來減少全域系統管理員帳戶容易受到惡意使用者攻擊的時間。 PIM 可在需要時提供隨需、即時的全域系統管理員角色指派。  

全域系統管理員帳戶不再是永久管理員，而是變為合格的管理員。全域系統管理員角色在有人需要它之前為無作用狀態。您需要完成啟動程序，在一段特定時間內將全域系統管理員角色新增到全域系統管理員帳戶。時間到期後，PIM 會從全域系統管理員帳戶中移除此全域系統管理員角色。

Microsoft 365 企業版 E5 隨附 Azure Active Directory Premium P2，而 P2 便有 PIM 功能。或者，您可以為您的全域系統管理員帳戶購買單獨的 Azure Active Directory Premium P2 授權。

若要為 Azure AD 租用戶和全域系統管理員帳戶啟用 Azure PIM，請參閱[什麼是 Azure AD Privileged Identity Management？](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

若要開發可保護特殊存取權避免受到網路攻擊的全面性藍圖，請參閱[在 Azure AD 中保護混合式部署和雲端部署的特殊權限存取](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)。

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pim)。


## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [設定混合式身分識別](identity-azure-ad-connect.md) |

