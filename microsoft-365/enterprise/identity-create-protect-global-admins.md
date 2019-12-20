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
# <a name="step-1-create-and-protect-your-global-admin-accounts"></a>步驟 1：建立和保護您的全域系統管理員帳戶

![階段 2 - 身分識別](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-global-admin"></a>
## <a name="protect-global-administrator-accounts"></a>保護全域系統管理員帳戶

*這是必要步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

在這一節中，您透過盡可能確保系統管理員帳戶的安全，來避免您組織遭受數位攻擊。 若要這麼做，您必須：

- 使用[強式密碼](https://support.microsoft.com//help/4026406/microsoft-account-create-a-strong-password)來建立一個以上專用的全域系統管理員帳戶，並只在需要時使用它們。
- 有需要時，透過將特定系統管理員角色 (例如 Exchange 系統管理員或密碼系統管理員) 指派至這些角色的其他專用帳戶或 IT 人員的使用者帳戶來執行日常管理。

如需專用的全域系統管理員帳戶，您也必須：

1. 在測試使用者帳戶上測試根據使用者帳戶或條件式以存取為基礎的 Azure Multi-Factor Authentication (MFA) 設定，以確保 MFA 正確且如預測般運作。 MFA 需要第二種形式的驗證 (例如將驗證碼傳送給智慧型手機)。
2. 為您的全域系統管理員帳戶建立和啟用條件式存取原則，原則需要 MFA，並使用組織中可用的最嚴密次要驗證形式。 如需詳細資訊，請參閱 [Azure Multi-Factor Authentication](identity-access-prerequisites.md#protecting-administrator-accounts) (部分內容機器翻譯)。

如需進一步的保護，請參閱[保護您的 Office 365 全域系統管理員帳戶](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts#additional-protections-for-enterprise-organizations) (部分內容機器翻譯)。

> [!Note]
> 緊急狀況下的緊急帳戶 (例如網路攻擊) 應僅使用雲端帳戶。 您也可以擁有非雲端的全域系統管理員帳戶 (合格或永久)。 如需詳細資訊，請參閱[在 Azure AD 中管理緊急存取系統管理帳戶](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) (部分內容機器翻譯)。

這一節的結果如下：

- 您的訂閱中唯一擁有全域系統管理員角色的使用者帳戶，就是專用全域系統管理員帳戶。 使用以下 Azure Active Directory PowerShell for Graph 命令驗證這點： 
  ```powershell
  Get-AzureADDirectoryRole | Where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```
- 管理您訂閱服務的所有其他使用者帳戶擁有指派的系統管理員角色，這些角色會與他們的工作職責相關聯。

> [!Note]
> 請參閱[連線到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)，以取得安裝 Azure Active Directory PowerShell for Graph 模組及登入的指示。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  若要在測試實驗室環境中練習此組態，請參閱[保護全域系統管理員帳戶測試實驗室指南](protect-global-administrator-accounts-microsoft-365-test-environment.md)。 |
|||

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-global-admin)。


<a name="identity-pim"></a>
## <a name="set-up-on-demand-administrators"></a>設定隨選系統管理員

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*

在這一節中，您會設定 Azure AD Privileged Identity Management (PIM) 來減少系統管理員帳戶容易受到惡意使用者攻擊的時間。 PIM 可在需要時提供隨需、及時的系統管理員角色指派。  

系統管理員帳戶不是永久系統管理員，而只是符合資格的系統管理員。 系統管理員角色直到有人需要時才會啟用。 到時您將完成啟用程式，將系統管理員角色在特定時間內新增至系統管理員帳戶。 時間到期時，PIM 會從系統管理員帳戶中移除系統管理員角色。

PIM 可與 Azure Active Directory Premium P2 搭配使用，隨附於 Microsoft 365 E5。 或者，您也可以為您的系統管理員帳戶購買個別 Azure Active Directory Premium P2 授權。

若要為 Azure AD 租用戶和系統管理員帳戶啟用 Azure PIM，請參閱[設定 PIM 步驟](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

若要開發可保護特殊存取權避免受到網路攻擊的全面性藍圖，請參閱[在 Azure AD 中保護混合式部署和雲端部署的特殊權限存取](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)。

作為過渡期的檢查點，您可以看到這一節的[允出準則](identity-exit-criteria.md#crit-identity-pim)。


<a name="identity-pam"></a>
## <a name="privileged-access-management"></a>特許存取管理

特殊權限存取管理的啟用方法是透過設定原則，該原則會指定您的 Office 365 租用戶中工作型活動的 Just-In-Time 存取。它可以協助保護貴組織免於受到使用現有特殊權限系統管理員帳戶與機密資料的常設存取權或關鍵組態設定之存取權的缺口。例如，您可能會設定特殊權限存取管理原則，該原則需要明確核准的存取權，並且會變更您的 Office 365 租用戶中的組織信箱設定。

在這個步驟中，您會在 Office 365 租用戶中啟用特殊權限存取管理，並且設定特殊權限存取原則，該原則為 Office 365 資料的工作型存取以及貴組織的組態設定，提供額外的安全性。在您的 Office 365 組織中開始使用特殊權限存取有三個基本步驟：

- 建立核准者的群組
- 啟用特殊權限存取
- 建立核准原則

一旦設定，特殊權限存取管理就會讓貴組織以零常設特殊權限來運作，並且針對由於此類常設系統管理存取而引發的漏洞提供一層防護。特殊權限存取需要對執行具有已定義相關聯核准原則的工作進行核准。需要執行包含在核准原則內工作的使用者必須要求存取核准並且獲得授與，才能夠具有執行原則中定義工作的必要權限。

若要啟用 Office 365 特殊權限存取管理，請參閱[在 Office 365 中設定特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 主題。

如需詳細資訊，請參閱 [Office 365 中的特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 主題。


|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  若要在測試實驗室環境中練習此組態，請參閱[特許存取管理測試實驗室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md) (部分內容機器翻譯)。 |
|||

作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](identity-exit-criteria.md#crit-identity-pam)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 2](./media/stepnumbers/Step2.png)| [保護您的密碼](identity-secure-your-passwords.md) |

