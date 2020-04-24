---
title: 階段 4：Microsoft 365 Apps 企業版
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 適用於 Microsoft 365 企業版的 Microsoft 365 Apps 企業版基礎結構部署步驟。
ms.openlocfilehash: fe29b8025a8ccf5babf2c52cd62ebc72860a8a5c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631426"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>階段 4：Microsoft 365 Apps 企業版

![階段 4：Microsoft 365 Apps 企業版](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*本文同時適用於 Microsoft 365 企業版和 Microsoft 365 教育版的 E3 和 E5 版本*

Microsoft 365 企業版包括 Office 的訂閱版本 Microsoft 365 Apps 企業版。 如同 Office 2019，Microsoft 365 Apps 企業版包括所有 Office 應用程式，而這些應用程式會直接安裝在您的用戶端裝置上。 與 Office 2019 不同，Microsoft 365 Apps 企業版會定期更新新的功能，並擁有可讓使用者在多個裝置上安裝 Office 的使用者型授權模型。 如需詳細資訊，請參閱[關於企業中的 Microsoft 365 Apps 企業版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。

您在這個階段將 Microsoft 365 Apps 企業版部署到用戶端裝置，這是 Microsoft 365 企業版的一部分。除了本指引，我們建議您使用 [Microsoft Fastrack](https://fasttrack.microsoft.com/office) 來進行部署。 

如果您已部署 Microsoft 365 Apps 企業版，請參閱此階段的[允出準則](office365proplus-exit-criteria.md)，以確保其符合 Microsoft 365 企業版的必要條件。

>[!Note]
>若要同時部署 Windows 10 企業版和 Microsoft 365 Apps 企業版，請參閱[桌面部署中心](desktop-deployment-center-home.md)。
>

## <a name="step-1-assess-your-environment"></a>步驟 1：評估環境

部署 Microsoft 365 Apps 企業版之前，請遵循[針對部署 Microsoft 365 Apps 企業版評估環境和需求](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus)中的指引。此評估包括系統需求、用戶端裝置的詳細資料 (例如架構、所需的語言)、授權需求、網路功能、應用程式相容性。完成評估可協助您為規劃部署做出重要決策。

## <a name="step-2-plan-your-deployment"></a>步驟 2：規劃部署

評估環境之後，請遵循[規劃 Microsoft 365 Apps 企業版的部署](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中的指引建立部署規劃。規劃包含下列決策： 

- 如何部署 Office，包括要使用哪些工具 (例如 Microsoft Endpoint Configuration Manager 或 Office 部署工具)，以及從何處安裝 Office
- 如何管理 Office 的更新
- 使用哪些更新通道 (Office 更新通道可控制使用者收到 Office 應用程式功能更新的頻率)
- 您想要使用的 Office 安裝套件和部署群組，包括哪些使用者應安裝哪些 Office 應用程式和語言

[規劃文章](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus)中有這些選項的最佳做法，包括管理部署、管理更新、定義安裝套件、建立部署群組。 

## <a name="step-3-deploy"></a>步驟 3：部署

根據部署規劃，選擇您要部署的方式：

- **[使用 Configuration Manager 部署 Microsoft 365 Apps 企業版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager)** 使用 Configuration Manager 管理部署，並從網路上的發佈點下載及部署 Office。

- **[使用 ODT 從雲端部署 Microsoft 365 Apps 企業版](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud)：** 使用 ODT 管理部署，並直接從 Office CDN 將 Office 安裝在用戶端裝置上
 
- **[從 Office 入口網站自行安裝 Microsoft 365 Apps 企業版](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365)：** 從 Office 入口網站管理部署，讓使用者直接從入口網站將 Office 安裝在他們的用戶端裝置上

許多組織會組合使用這些選項讓不同使用者使用。例如，組織可能會使用設定管理員為大部分的使用者部署 Office，但為一小群不常連線到內部網路的工作者啟用自行安裝。 

如果您的組織使用設定管理員，建議您升級至最新分支並更新至最新版本。如需詳細資訊，請參閱[我應該使用設定管理員的哪一個分支？](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何執行 Microsoft 365 企業版

了解 Microsoft 的專家如何[部署和管理 Microsoft 365 Apps 企業版的更新](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何執行 Microsoft 365 企業版

請參閱 Contoso Corporation (虛構但有代表性的跨國企業) 如何[部署 Microsoft 365 Apps 企業版](contoso-o365pp.md)。

![Contoso 公司](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>下一步

[Microsoft 365 Apps 企業版基礎結構的允出準則](office365proplus-exit-criteria.md)
