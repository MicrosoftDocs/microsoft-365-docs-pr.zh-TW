---
title: 資訊保護基礎結構的允出準則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 檢查資訊保護型服務和基礎結構的準則，確定您的設定符合 Microsoft 365 企業版的需求。
ms.openlocfilehash: 02e972a80d4b42ae66193bbbc55d0f1e63be5ba6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047236"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>資訊保護基礎結構的允出準則

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

請確定您的資訊保護基礎結構符合下列必要準則，而且您已將這些視為選擇性準則。

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必要：定義組織的安全性和資訊保護層級

您已規劃並決定組織需要的安全性層級。這些層級定義了最低層級的安全性和資訊機密性增加的其他層級及其所需的資料安全性。

您至少要使用三種安全性層級：

- 基準
- 敏感性
- 高管制

如有需要，[步驟 1](infoprotect-define-sec-infoprotect-levels.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>必要：設定增強的 Microsoft 365 安全性

您已為 [Office 365 增強的安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)設定下列設定：

- Microsoft 365 安全性中心的威脅管理原則
- Exchange Online 的其他全租用戶設定
- SharePoint Online 系統管理中心中的全租用戶共用原則
- Azure Active Directory (Azure AD) 中的設定

您已經[為 SharePoint、OneDrive 和 Microsoft Teams 啟用了 Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。

如有需要，[步驟 3](infoprotect-configure-increased-security-office-365.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>選用：設定環境的分類

您已與您的法務和法規遵循小組合作，為組織的資料監管和安全性原則開發出適當的分類和標籤配置。 

這些原則對應以下設定及部署：

- 敏感資料類型
- 保留標籤
- 敏感度標籤
- Azure 資訊保護標籤

如有需要，[步驟 2](infoprotect-configure-classification.md) 可協助您符合這項要求。 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>選用：在您的環境之間部署 Windows 資訊保護

您已註冊 Windows 10 企業版裝置，該裝置已部署並套用 Intune 原則，定義了：

- 要保護的應用程式。
- 保護的層級。
- 保護延伸的位置。

如有需要，[步驟 4](infoprotect-deploy-windows-information-protection.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>選用：部署 Office 365 資料外洩防護 (DLP)

您已分析、測試然後推出一組 DLP 原則 (具有位置和規則與條件和動作)，貴組織需要保護客戶和其他類型的私密資料，並且遵循產業和地區法規及需求。

您的資料合規性和安全性人員使用 Office 365 安全性與合規性中心儀表板來監視 DLP 事件。

如有需要，[步驟 5](infoprotect-data-loss-prevention.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a>選用：已設定電子郵件加密

您已視需要設定組織的以下電子郵件加密：

|||
|:-------|:-----|
| **加密方法** | **針對傳送的電子郵件** |
| [Office 365 郵件加密 (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | 在組織外部使用加密 |
| [資訊版權管理 (IRM)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | 具有加密和權限 |
| [安全多用途網際網路郵件延伸 (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | 使用公開金鑰加密同時使用加密和數位簽章 |
|||

如有需要，[步驟 6](infoprotect-email-encryption.md) 可協助您符合這項要求。

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>選用：在 Office 365 中設定特殊權限存取管理

您已使用[在 Office 365 中設定特殊存取權限管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主題中的資訊來啟用特殊存取權限，並在組織中建立一個或多個特殊存取權限原則。 您已設定這些原則，並且啟用了即時存取，以存取敏感資料或存取關鍵配置設定。

如有需要，[步驟 7](infoprotect-configure-privileged-access-management.md) 可協助您符合這項要求。 

## <a name="results-and-next-steps"></a>結果和後續步驟

Microsoft 365 企業版的資訊保護基礎架構使用已定義的安全性層級、Office 365 的增強安全性、使用敏感資料類型和標籤的分類、Windows 資訊保護、資料外洩防護、電子郵件加密以及特殊存取權限管理。

如果您遵照 Microsoft 365 企業版的端到端部署，那麼現在您已準備好讓[工作負載和案例](deploy-workloads.md)利用基礎架構的所有功能和設定。
