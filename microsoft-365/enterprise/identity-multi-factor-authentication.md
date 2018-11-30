---
title: 步驟 5：設定多重要素驗證
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定使用者帳戶的多重要素驗證。
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866603"
---
# <a name="step-5-set-up-multi-factor-authentication"></a>步驟 5：設定多重要素驗證

*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在本步驟中，您將設定多重要素驗證 (MFA)，以將第二層安全性新增至使用者登入和交易。在使用者已正確地輸入密碼後，MFA 需要額外的驗證方法。少了 MFA，密碼是唯一的驗證方式。密碼的問題是攻擊者容易猜測許多密碼或在不知情的情況下與未受信任的對象共用密碼。

透過 MFA，第二層安全性可以是：

- 不容易遭到偽造或重複的個人和受信任裝置 (例如智慧型手機)。
- 生物識別屬性 (例如指紋)。

您將啟用 MFA，並以每個使用者帳戶為基礎設定次要驗證方法。請務必讓使用者知道 MFA 已啟用，他們就了解要求 (例如強制使用智慧型手機登入) 並能順利登入。

如需更多資訊，請參閱 [Office 365 部署的多重要素驗證方案](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)。

若要設定多重要素驗證，[設定 Office 365 使用者的多重要素驗證](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。

您可以要求含條件式存取原則的 MFA。例如，您可以設定在決定驗證為中或高風險時需要 MFA 的原則。如需詳細資訊，請參閱[常見的身分識別與裝置存取原則](identity-access-policies.md#require-mfa-based-on-sign-in-risk)。

>[!Note]
>在部分應用程式中 (例如 Microsoft Office 2010 或更舊版本和 Apple Mail) 您無法使用 MFA。若要使用這些應用程式，您將需要使用「應用程式密碼」取代您的傳統密碼。應用程式密碼允許應用程式略過 MFA 並繼續執行。若需應用程式密碼的更多資訊，請參閱[建立 Office 365 的應用程式密碼](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183)。
>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [測試實驗室指南：多重要素驗證](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-mfa)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [防護認證洩露](identity-azure-ad-identity-protection.md) |

