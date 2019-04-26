---
title: 資訊保護基礎結構的允出準則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 檢查資訊保護型服務和基礎結構的準則，確定您的設定符合 Microsoft 365 企業版的需求。
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283692"
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

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>必要：設定增強的 Microsoft 365 安全性

您已為 [Office 365 提升安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)設定下列設定：

- Microsoft 365 安全性中心的威脅管理原則
- Exchange Online 的其他全租用戶設定
- SharePoint 系統管理中心中的全租用戶共用原則
- Azure Active Directory (Azure AD) 中的設定

您已經[為 SharePoint、OneDrive 和 Microsoft Teams 啟用了 Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/zh-TW/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。

如有需要，[步驟 3](infoprotect-configure-increased-security-office-365.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>選用：設定環境的分類

您已與您的法務和法規遵循小組合作，為組織的資料監管和安全性原則開發出適當的分類和標籤配置。 

這些原則對應以下設定及部署：

- 敏感資料類型
- 保留標籤
- 敏感度標籤
- Azure 資訊保護標籤

如有需要，[步驟 2](infoprotect-configure-classification.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>選用：在 Office 365 中設定特殊權限存取管理

您已使用[在 Office 365 中設定特殊存取權限管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主題中的資訊來啟用特殊存取權限，並在組織中建立一個或多個特殊存取權限原則。 您已設定這些原則，並且啟用了即時存取，以存取敏感資料或存取關鍵配置設定。

如有需要，[步驟 4](infoprotect-configure-privileged-access-management.md) 可協助您符合這項要求。 

## <a name="results-and-next-steps"></a>結果和後續步驟

Microsoft 365 企業版的資訊保護基礎架構使用已定義的安全性層級、Office 365 的增強安全性、使用敏感資料類型和標籤的分類以及特殊存取權限管理。

如果您遵照 Microsoft 365 企業版的端到端部署，那麼現在您已準備好讓[工作負載和案例](deploy-workloads.md)利用基礎架構的所有功能和設定。
