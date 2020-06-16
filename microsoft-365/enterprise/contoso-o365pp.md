---
title: 適用於 Contoso 的 Microsoft 365 Apps 企業版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 來部署 Microsoft 365 Apps 企業版。
ms.openlocfilehash: 4a36e33a6f2ef6df880864dd852f0f63056946e6
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679035"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>適用於 Contoso 的 Microsoft 365 Apps 企業版部署

Contoso upgraded their PCs to Windows 10 Enterprise and Microsoft 365 Apps for enterprise to enable more effective collaboration, better security, and a more modern desktop experience. After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:

- 所有電腦都應該執行 Microsoft 365 Apps 企業版
- 部署應盡可能使用現有管理工具和基礎架構
- 部署必須支援使用者裝置的多種語言及現有基礎架構
- 電腦應在最低 IT 管理成本與對使用者影響最低的情況下，保持最新狀態及安全性

## <a name="deployment-tools"></a>部署工具

Based on their requirements, Contoso chose to deploy Windows 10 Enterprise and Microsoft 365 Apps for enterprise with Configuration Manager (Current Branch). Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Office, including:

- 對等快取，可協助在部署至遠端位置裝置時限制網路流量
- Office 用戶端管理儀表板，讓您更輕鬆地部署 Office 和監控更新，並可讓系統管理員存取最新的部署和管理功能
- 智慧型語言套件部署，包括自動部署與作業系統相同的語言
- 完整支援並有簡單好用的方法，在部署期間從用戶端移除現有的 Office 版本

除了 Configuration Manager，Contoso 也使用「[整備工具組](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)」，此為 Microsoft 提供的免費工具，可用於評估 Office 巨集和增益集的相容性問題。

## <a name="managing-the-deployment-and-updates"></a>管理部署及更新

Microsoft 365 Apps for enterprise has a new release model: Office as a service. The service model makes it easy to stay up to date with new features, but often requires a change in approach for IT departments in how new releases are deployed and tested. To minimize any compatibility issues and to ensure their computers stayed up to date, Contoso deployed Windows and Office in two stages: 

- For the first stage, they deployed Microsoft 365 Apps for enterprise to a small set of representative devices across the organization. This pilot group was used to test apps, add-ins, and hardware with Microsoft 365 Apps for enterprise
- Contoso 在四個月後解決應用程式、增益集與硬體試驗群組中的所有重大問題， 並將 Microsoft 365 Apps 企業版部署至整個組織的裝置 (大型群組)。 

Instead of managing updates to Office with Configuration Manager, Contoso enabled automatic updates from the cloud. Cloud-based updates reduced their administrative overhead while ensuring the devices stayed up to date. 

Contoso followed the same two-stage approach for feature updates that they used for deploying Office: devices in the pilot group received feature updates four months earlier than devices in the rest of the organization (the broad group). To enable this for Office, Contoso used two recommended [update channels](https://docs.microsoft.com/DeployOffice/overview-update-channels): 

- 對試驗群組更新的半年通道(預覽) 
- 對大型群組更新的半年企業通道。 

由於半年企業通道 (預覽) 比半年企業通道早四個月發行 Microsoft 365 Apps 企業版，因此 Contoso 有時間在無需管理更新下，進型驗證更新。 

## <a name="deployment-process"></a>部署程序

為了完成 Office 部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：

1. 在部署之前，他們會使用「整備工具組」測試的應用程式和 Office 增益集，評估其與 Microsoft 365 Apps 企業版的相容性。
2. Contoso 啟用 Configuration Manager 的用戶端對等快取，協助在部署至遠端位置的用戶端裝置時限制網路流量。 
3. They defined two deployment groups as device collections in Configuration Manager: a pilot group and a broad group. The pilot group, which included a small set of representative devices across the organization, was used to do additional testing of apps, add-ins, and hardware with Windows 10 Enterprise and Microsoft 365 Apps for enterprise. 
4. They created deployment packages for Office using the Office Client Management dashboard and the Office 365 Installer wizard, both of which are part of the Configuration Manager console. They built two Microsoft 365 Apps for enterprise packages, one for the pilot group on the Semi-Annual Enterprise Channel (Preview) and one for the broad group on the Semi-Annual Enterprise Channel. 
5. As part of each Office package, they included English, French, and German Language packs. If a device required a language not included in the Office package, it was automatically downloaded from the Office Content Delivery Network (CDN).
6. 他們先使用 Office 套件中的內建功能自動移除所有現有的 MSI 版本 Office，再安裝 Microsoft 365 Apps 企業版。
7. 他們在 Configuration Manager 中將 Windows 和 Office 套件部署到內部網路中發佈點，然後執行 Configuration Manager 部署工作順序將試驗 Microsoft 365 Apps 企業版套件部署到試驗群組。
8. Contoso 在試驗群組解決任何相容性問題後，即會執行工作順序將各種 Microsoft 365 Apps 企業版套件部署到大型群組。

因為 Contoso 選擇從雲端自動更新裝置，因此不需要管理 Configuration Manager 中的程序。 其裝置會根據初始部署時所定義的更新通道，直接從雲端自動進行更新。 

這是 Contoso Microsoft 365 Apps 企業版安裝和持續更新部署的基礎架構。

![Contoso 的 Microsoft 365 Apps 企業版部署基礎結構](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>下一步

[深入了解](contoso-mdm.md) Contoso 如何在 Microsoft 365 企業版中使用 Microsoft Intune 來管理組織中的裝置與執行的應用程式。

## <a name="see-also"></a>請參閱

[適用於 Microsoft 365 企業版的 Microsoft 365 Apps 企業版](office365proplus-infrastructure.md)

[部署指南](deploy-microsoft-365-enterprise.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)
