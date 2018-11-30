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
# <a name="step-2-protect-global-administrator-accounts"></a>步驟 2：保護全域管理員帳戶

*此為必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在本步驟中，您透過盡可能確保系統管理員帳戶的安全，來避免您組織遭受數位攻擊。若要這麼做，您必須：

- 使用非常[強式密碼](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)來建立專用的全域系統管理員帳戶，並只在需要時使用它們。
- 有需要時，透過將特定系統管理員角色 (例如 Exchange 系統管理員或密碼系統管理員) 指派至 IT 人員的使用者帳戶來執行日常管理。

如需專用的全域系統管理員帳戶，您也必須：

1. 在測試使用者帳戶上測試根據使用者帳戶或條件式以存取為基礎的多重要素驗證 (MFA) 設定，以確保 MFA 正確且如預測般運作。MFA 需要第二種形式的驗證 (例如將驗證碼傳送給智慧型手機)。
2. 為每一個專用的 Office 365 全域系統管理員帳戶設定 MFA ，並使用貴組織中可供使用的最強型次要驗證。如需詳細資訊，請參閱[多重要素驗證](identity-multi-factor-authentication.md)。
2. 使用條件訪問策略來要求全域系統管理員帳戶的 MFA。如需詳細資訊，請參閱[保護系統管理員帳戶](identity-access-prerequisites.md#protecting-administrator-accounts)。
4. 使用 Office 365 雲端 App 安全性原則來監控全域系統管理員帳戶活動。如需詳細資訊，請參閱[設定增強的 Office 365 安全性](infoprotect-configure-increased-security-office-365.md)。

請參閱[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)以了解設定的相關詳細資訊。

> [!Note]
> 組織應使用純雲端的身分識別來建立特殊權限的帳戶 (例如全域系統管理員)，以供緊急情況使用 (例如網路攻擊)。如需詳細資訊，請參閱[管理 Azure AD 中的緊急存取系統管理帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access)。

此步驟的結果如下：

- 在您訂閱中擁有全域系統管理員角色的唯一使用者帳戶，就是新一組專用全域系統管理員帳戶。請透過下列 Windows Azure AD V2 PowerShell 命令來進行確認： 
  ```
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 管理您訂閱的所有其他日常使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。

> [!Note]
> 請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) 以了解安裝 Azure AD V2 PowerShell 模組與登入的指示。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：保護全域系統管理員帳戶](protect-global-administrator-accounts-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-global-admin)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [設定隨選全域系統管理員](identity-privileged-identity-management.md) |

