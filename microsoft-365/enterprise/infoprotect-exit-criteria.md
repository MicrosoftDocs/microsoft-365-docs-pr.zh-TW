---
title: 資訊保護基礎結構的允出準則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 檢查資訊保護型服務和基礎結構的準則，確定您的設定符合 Microsoft 365 企業版的需求。
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866647"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>資訊保護基礎結構的允出準則

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

完成基本的基礎結構之前，請確定您的資訊保護基礎結構符合這些條件。 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>必要：定義組織的安全性和資訊保護層級

您已規劃並決定組織需要的安全性層級。這些層級定義了最低層級的安全性和資訊機密性增加的其他層級及其所需的資料安全性。

您至少要使用三種安全性層級：

- 基準
- 敏感性
- 高管制

如有需要，[步驟 1](infoprotect-define-sec-infoprotect-levels.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>必要：設定增強的 Office 365 安全性

您已根據[設定 Office 365 租用戶的增強安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)中的資訊，設定下列項目以增強安全性：

- Office 365 安全與規範中心中的威脅管理原則
- Exchange Online 的其他全租用戶設定
- SharePoint 系統管理中心中的全租用戶共用原則
- Azure Active Directory 中的設定

您也已經[啟用 Office 365 進階威脅防護 (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)。

如有需要，[步驟 3](infoprotect-configure-increased-security-office-365.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>選用：設定環境的分類

您已與法律和法規遵循小組合作，為組織的資料開發出適當的分類和標籤配置，包括下列各項：

- 敏感資料類型
- Office 365 標籤
- Azure 資訊保護標籤

如有需要，[步驟 2](infoprotect-configure-classification.md) 可協助您符合這項要求。 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>選用：在 Office 365 中設定特殊權限存取管理

您已使用[在 Office 365 中設定特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (機器翻譯) 主題中的資訊，在您的 Office 365 組織中啟用特殊權限存取並建立一或多個特殊權限存取原則。您已設定這些原則並且啟用 Just-In-Time 存取，以存取機密資料或存取重要組態設定。

如有需要，[步驟 4](infoprotect-configure-privileged-access-management.md) 可協助您符合這項要求。 

## <a name="next-step"></a>下一步

您現在可以開始部署[工作負載和案例](deploy-workloads.md)，例如在 Microsoft 365 企業版基本基礎結構上執行的 Microsoft Teams 和 Exchange Online。
