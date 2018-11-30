---
title: 步驟 6：防護認證洩露
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
description: 了解並設定 Azure AD Identity Protection。
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866763"
---
# <a name="step-6-protect-against-credential-compromise"></a>步驟 6：防護認證洩露

*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在本步驟中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。Azure AD Identity Protection 提供許多方法，協助防止攻擊者透過您的帳戶和群組而入侵，以及協助保護您最寶貴的資料。

使用 Azure AD Identity Protection，您可以：

|||
|:---------|:---------|
|判斷並處理組織身分識別中潛在的弱點|Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。Identity Protection 可使用此資料產生報告和警訊，協助您評估問題及採取行動。|
|偵測與組織身分識別相關的可疑活動，並自動進行回應處理|您可以設定風險原則，在達到指定的風險層級時，會自動回應偵測到的問題。由 Azure Active Directory 和 Enterprise Mobility + Security (EMS) 提供的這些原則，以及其他條件式存取控制，可自動封鎖存取或採取修正動作，包括密碼重設和要求後續登入的多重要素驗證。|
|調查可疑事件，並使用系統管理動作加以解決|您可以使用安全性事件的相關資訊來調查風險事件。基本工作流程可用於追蹤調查及啟動修復動作，例如密碼重設。|

請參閱 [Azure AD Identity Protection 的相關詳細資訊](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。

請參閱[啟用 Azure AD Identity Protection 的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。

此步驟的結果會是您已啟用 Azure AD Identity Protection，並將其用於：

- 解決潛在的身分識別弱點。
- 偵測可能的認證洩露嘗試。
- 調查並解決持續的可疑身分識別事件。

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-ident-prot)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [同步處理目錄](identity-azure-ad-connect.md) |


