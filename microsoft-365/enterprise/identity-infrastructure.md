---
title: 第 2 階段：身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版身分識別基礎結構的部署步驟。
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981946"
---
# <a name="phase-2-identity"></a>第 2 階段：身分識別

![](./media/deploy-foundation-infrastructure/identity_icon.png)

在 Microsoft 365 企業版中，妥善的規劃與執行的身分識別基礎結構造就了強大的安全性，利用已驗證的使用者和裝置來存取生產力的工作負載及其資料。

請觀看這段影片，以大略了解身分識別模型和 Microsoft 365 企業版的驗證。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
>如果您已部署身分識別基礎結構，請參閱[身分識別允出準則](identity-exit-criteria.md)，確定您符合 Microsoft 365 企業版的必要與選用條件。
>

如需每個 Microsoft 365 企業版方案的身分識別功能、Azure Active Directory (Azure AD) 的角色、內部部署和雲端式元件，以及最常見的驗證組態，請參閱[身分識別基礎結構海報](media/identity-infrastructure/M365E-ID-Infra.pdf)。

[![身分識別基礎結構海報](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)

這份雙頁海報可讓您快速了解有關 Microsoft 365 企業版的身分識別概念和組態。

您也可以[下載此海報](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>規劃及部署 Microsoft 365 企業版的身分識別基礎結構 

使用下列步驟在雲端規劃及部署新的身分識別基礎結構。您也可以使用這些步驟讓現有的內部部署或混合式身分識別基礎結構能搭配使用 Microsoft 365 企業版。 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [規劃使用者與群組](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [保護您的特殊權限身分識別](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [設定混合式身分識別](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [設定安全的使用者驗證](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [簡化使用者的存取權](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [使用群組更輕鬆地進行管理](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [設定身分識別治理](identity-governance.md) |

完成這些步驟之後，請移至此階段的[允出準則](identity-exit-criteria.md)，以確定您符合 Microsoft 365 企業版身分識別的必要與選用條件。

## <a name="identity-and-device-access-recommendations"></a>身分識別與裝置存取建議

Microsoft 會針對[身分識別與裝置存取](microsoft-365-policies-configurations.md)提供一組建議，以確保安全且具有生產力的員工。針對身分識別，使用下列文章中的建議和設定以及本階段的步驟：

- [必要條件](identity-access-prerequisites.md)
- [一般身分識別與裝置存取原則](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

了解 Microsoft 的 IT 專家如何使用[管理身分識別和保護存取](https://www.microsoft.com/zh-TW/itshowcase/deploying-and-managing-microsoft-365#primaryR5)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何為 Microsoft 365 雲端服務[部署混合式身分識別基礎結構](contoso-identity.md)。

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [規劃使用者與群組](identity-plan-users-groups.md) |
