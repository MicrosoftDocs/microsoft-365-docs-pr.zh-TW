---
title: 第4 階段：Office 365 專業增強版
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 企業版 Office 365 專業增強版的部署步驟。
ms.openlocfilehash: 5c32257fb9066f170da1f1a3cfe4b865e383cfcb
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646398"
---
# <a name="phase-4-office-365-proplus"></a>階段 4：Office 365 專業增強版

![階段 4：Office 365 專業增強版](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*本文同時適用於 Microsoft 365 企業版和 Microsoft 365 教育版的 E3 和 E5 版本*

Microsoft 365 企業版包含 Office 365 專業增強版 (Office 的訂閱版本)。 如同 Office 2019，Office 365 專業增強版包括所有 Office 應用程式，而這些應用程式會直接安裝在您的用戶端裝置上。 與 Office 2019 不同，Office 365 專業增強版會定期更新新的功能，並擁有可讓使用者在多個裝置上安裝 Office 的使用者型授權模型。 如需詳細資訊，請參閱[關於企業中的 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。

您在這個階段將 Office 365 專業增強版部署到用戶端裝置，這是 Microsoft 365 企業版的一部分。除了本指引，我們建議您使用 [Microsoft Fastrack](https://fasttrack.microsoft.com/office) 來進行部署。 

如果您已部署 Office 365 專業增強版，請參閱此階段的[允出準則](office365proplus-exit-criteria.md)，以確保其符合 Microsoft 365 企業版的必要條件。

>[!Note]
>若要同時部署 Windows 10 企業版和 Office 365 專業增強版，請參閱[桌面部署中心](desktop-deployment-center-home.md)。
>

## <a name="step-1-assess-your-environment"></a>步驟 1：評估環境

部署 Office 365 專業增強版之前，請遵循[針對部署 Office 365 專業增強版評估環境和需求](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)中的指引。此評估包括系統需求、用戶端裝置的詳細資料 (例如架構、所需的語言)、 授權需求、網路功能、應用程式相容性。完成評估可協助您為規劃部署做出重要決策。

## <a name="step-2-plan-your-deployment"></a>步驟 2：規劃部署

評估環境之後，請遵循[規劃 Office 365 專業增強版的部署](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中的指引建立部署規劃。規劃包含下列決策： 

- 如何部署 Office，包括要使用哪些工具 (例如 System Center 設定管理員或 Office 部署工具)，以及從何處安裝 Office
- 如何管理 Office 的更新
- 使用哪些更新通道 (Office 更新通道可控制使用者收到 Office 應用程式功能更新的頻率)
- 您想要使用的 Office 安裝套件和部署群組，包括哪些使用者應安裝哪些 Office 應用程式和語言

[規劃文章](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中有這些選項的最佳做法，包括管理部署、管理更新、定義安裝套件、建立部署群組。 

## <a name="step-3-deploy"></a>步驟 3：部署

根據部署規劃，選擇您要部署的方式：

- **[使用 System Center 設定管理員部署 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager)：** 使用設定管理員部署管理，從網路上的發佈點下載並部署 Office

- **[使用 ODT 從雲端部署 Office 365 專業增強版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud)：** 使用 ODT 管理部署，直接從 Office CDN 將 Office 安裝在用戶端裝置上
 
- **[從 Office 入口網站自行安裝 Office 365 專業增強版](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658)：** 從 Office 入口網站管理部署，讓使用者直接從入口網站將 Office 安裝在他們的用戶端裝置上

許多組織會組合使用這些選項讓不同使用者使用。例如，組織可能會使用設定管理員為大部分的使用者部署 Office，但為一小群不常連線到內部網路的工作者啟用自行安裝。 

如果您的組織使用設定管理員，建議您升級至最新分支並更新至最新版本。如需詳細資訊，請參閱[我應該使用設定管理員的哪一個分支？](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

了解 Microsoft 的專家如何[部署和管理 Office 365 專業增強版的更新](https://www.microsoft.com/zh-TW/itshowcase/deploying-and-managing-microsoft-365#primaryR7)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何[部署 Office 365 專業增強版](contoso-o365pp.md)。

![Contoso 公司](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

[Office 365 ProPlus 基礎結構允出準則](office365proplus-exit-criteria.md)
