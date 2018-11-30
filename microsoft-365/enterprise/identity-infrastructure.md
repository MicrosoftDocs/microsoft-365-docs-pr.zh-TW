---
title: 第 2 階段：身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版身分識別基礎結構的部署步驟。
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866524"
---
# <a name="phase-2-identity"></a>第 2 階段：身分識別

![](./media/deploy-foundation-infrastructure/identity_icon.png)

在 Microsoft 365 企業版中，妥善的規劃與執行的身分識別基礎結構造就了強大的安全性，利用已驗證的使用者和裝置來存取生產力的工作負載及其資料。

>[!Note]
>如果您已部署身分識別基礎結構，請參閱[身分識別允出準則](identity-exit-criteria.md)，確定您符合 Microsoft 365 企業版的必要與選用條件。
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>規劃及部署 Microsoft 365 企業版的身分識別基礎結構 

使用下列步驟在雲端規劃及部署新的身分識別基礎結構。您也可以使用這些步驟讓現有的內部部署或混合式身分識別基礎結構能搭配使用 Microsoft 365 企業版。 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [規劃使用者與群組](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [保護全域系統管理員帳戶](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [設定隨選全域系統管理員](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [簡化密碼重設](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [設定多重要素驗證](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [防護認證洩露](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [同步處理目錄](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [監控同步處理健康情況](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [簡化密碼更新](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [簡化使用者登入](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [自訂 Office 365 登入頁面](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [設定自動授權](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [監控租用戶和登入活動](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [允許使用者建立及管理自己的群組](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [設定動態群組成員資格](identity-automatic-group-membership.md) |

完成這些步驟之後，請移至此階段的[允出準則](identity-exit-criteria.md)，以確定您符合 Microsoft 365 企業版的必要與選用條件。

## <a name="identity-and-device-access-recommendations"></a>身分識別與裝置存取建議

Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。針對身分識別，使用下列文章中的建議和設定以及本階段的步驟：

- [必要條件](identity-access-prerequisites.md)
- [一般身分識別與裝置存取原則](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

深入了解 Microsoft 的 IT 專業人員如何使用以下資源，規劃及部署 Microsoft 365 企業版的身分識別功能：

- [在 Microsoft 管理使用者身分識別並且保護存取權](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [針對提升權限的存取使用 Azure AD Privileged Identity Management](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何為 Microsoft 365 雲端服務[部署混合式身分識別基礎結構](contoso-identity.md)。

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [規劃使用者與群組](identity-plan-users-groups.md) |
