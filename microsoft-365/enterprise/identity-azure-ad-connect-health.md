---
title: 步驟 8：監控同步處理健全狀況
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
description: 了解及設定 Azure AD Connect Health。
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866541"
---
# <a name="step-8-monitor-synchronization-health"></a>步驟 8：監控同步處理健全狀況

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步驟中，您會在每個內部部署身分識別伺服器上安裝 Azure AD Connect Health 代理程式，以監控您的身分識別基礎結構，以及由 Azure AD Connect 提供的同步處理服務。監控資訊會在 Azure AD Connect Health 入口網站提供，您可以在其中檢視警訊、效能監控、使用量分析及其他資訊。

![Azure AD Connect Health 的元件](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

如何使用 Azure AD Connect Health 的關鍵設計決策取決於您如何使用 Azure AD Connect：

- 如果您使用的是**受管理的驗證**選項，請先從[使用 Azure AD Connect Health 搭配同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)開始，以了解並設定 Azure AD Connect Health。
- 如果您使用**同盟驗證**搭配 Active Directory 同盟服務 (AD FS) 來同步處理帳戶及群組名稱，請先從[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 開始，以了解並設定 Azure AD Connect Health。

完成此步驟後的結果：

- 已在內部部署身分識別提供者伺服器上安裝 Azure AD Connect Health 代理程式。
- Azure AD Connect Health 入口網站會顯示您內部部署基礎結構和同步處理活動的目前狀態以及 Office 365 和 EMS 訂閱的 Azure AD 租用戶。

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-sync-health)。


## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [簡化密碼更新](identity-password-writeback.md) |

