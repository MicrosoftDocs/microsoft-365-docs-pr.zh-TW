---
title: 適用於 Contoso 的 Microsoft 365 Apps 企業版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 來部署 Microsoft 365 Apps 企業版。
ms.openlocfilehash: 71958b2e87882e478a852db1f906f61207837854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907671"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>適用於 Contoso 的 Microsoft 365 Apps 企業版部署

Contoso 將其電腦升級為 Windows 10 企業版和 Microsoft 365 Apps 企業版，以啟用更有效率的共同作業、更好的安全性，以及更新式的桌面體驗。 在評估其基礎結構和業務需求之後，Contoso 識別出下列部署的主要需求：

- 所有的電腦都應該執行 Microsoft 365 Apps 企業版。
- 部署應盡可能使用現有的管理工具和基礎結構。
- 在使用者的裝置上部署必須支援多種語言和現有的架構。
- 電腦應該以最少的 IT 管理成本和對使用者的影響降至最低的方式，保持最新狀態及安全性。

## <a name="deployment-tools"></a>部署工具

根據他們的需求，Contoso 選擇透過 Configuration Manager (目前的分支) 來部署 Windows 10 企業版和 Microsoft 365 Apps 企業版。 Configuration Manager 適合大型環境，並提供安裝、更新及設定的全面控制。 它也具有內建的功能，可讓您更輕鬆快捷地部署及管理 Office，包括：

- 對等快取，可在部署至遠端位置的裝置時協助有限的網路容量。
- Office 用戶端管理儀表板，可讓您輕鬆地部署 Office 和監視更新，並可讓系統管理員存取最新的部署和管理功能。
- 智慧語言套件部署，包括自動部署與作業系統相同的語言。
- 在部署期間，從用戶端移除現有版本 Office 的完全支援和便於使用的方法。

除了 Configuration Manager 之外，Contoso 使用[準備工作工具來 Office 增益集和 VBA](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)、Microsoft 的免費工具，以評估其 Office 宏及增益集的相容性問題。

## <a name="managing-deployment-and-updates"></a>管理部署和更新

Microsoft 365 Apps 企業版具有新的版本模型： Office 為服務。 服務模型可讓您輕鬆掌握最新的功能。 不過，它通常需要 IT 部門變更其部署與測試新版本的方式。 為了盡可能減少相容性問題，並確保其電腦維持在最新狀態，Contoso 會分兩個階段部署 Windows 和 Office：

- 首先，他們會將 Microsoft 365 Apps 企業版部署到整個組織中一小部分的代表裝置。 這個試驗群組是用來測試應用程式、增益集及硬體與 Microsoft 365 Apps 企業版。
- Contoso 在四個月後解決應用程式、增益集與硬體試驗群組中的所有重大問題， 並將 Microsoft 365 Apps 企業版部署至整個組織的裝置 (大型群組)。

Contoso 從雲端啟用自動更新，而不是使用 Configuration Manager 管理 Office 的更新。 雲端式更新可減少管理負荷，同時確保裝置保持最新狀態。

Contoso 已遵循用於部署 Office 的功能更新的兩階段方式：試驗群組中的裝置收到的功能會在組織的其餘部分中的裝置之前四個月更新， (廣泛的群組) 。 若要為 Office 啟用這項功能，Contoso 使用兩個建議的[更新通道](/DeployOffice/overview-update-channels)：

- 對試驗群組更新的半年通道(預覽)
- Semi-Annual 廣泛群組的更新 Enterprise 通道

由於半年企業通道 (預覽) 比半年企業通道早四個月發行 Microsoft 365 Apps 企業版，因此 Contoso 有時間在無需管理更新下，進型驗證更新。

## <a name="deployment-process"></a>部署程序

為了完成 Office 部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：

1. 在部署之前，Contoso 使用準備工作工具來 Office 增益集和 VBA 來測試其應用程式，並 Office 增益集來評估其與 Microsoft 365 Apps 企業版的相容性。
1. 在 Configuration Manager 中，他們會在其用戶端裝置上啟用對等快取，以在部署至遠端位置的用戶端裝置時，協助有限的網路容量。 
1. Contoso 在 Configuration Manager 中將兩個部署群組定義為裝置集合：一個試驗群組和一個廣泛的群組。 試驗群組（包含整個組織中一小部分的代表裝置）是用來進行應用程式、增益集的其他測試，以及 Windows 10 企業版和 Microsoft 365 Apps 企業版的硬體。
1. 他們會使用 Office 用戶端管理儀表板和 Office 365 Installer 嚮導（同時是 Configuration Manager 主控台的一部分）建立 Office 的部署套件。 他們建立兩個 Microsoft 365 Apps 企業版套件，一個用於 Semi-Annual Enterprise 通道 (預覽) ，另一個用於 Semi-Annual Enterprise 通道上的廣泛群組。
2. 每個 Office 套件包含英文、法文和德文語言套件。 如果裝置所需的語言並未包含在 Office 封裝中，該語言套件會從 Office 中自動下載內容傳遞網路 (CDN) 。
3. 他們先使用 Office 套件中的內建功能自動移除所有現有的 MSI 版本 Office，再安裝 Microsoft 365 Apps 企業版。
4. 在 Configuration Manager 中，他們會將 Windows 和 Office 套件部署到其網路上的發佈點。 然後，他們會執行 Configuration Manager 部署工作順序，將試驗 Microsoft 365 Apps 企業版套件部署到試驗群組。
5. 當使用者解決試驗群組的相容性問題之後，Contoso 執行工作順序，將 Microsoft 365 Apps 企業版套件部署到廣泛的群組。

因為 Contoso 選擇從雲端自動更新裝置，因此不需要管理 Configuration Manager 中的程序。 其裝置會根據初始部署中所定義的更新通道，直接從雲端自動更新。

以下是 Contoso Microsoft 365 Apps 企業版安裝和持續更新部署架構。

![Microsoft 365 Apps 企業版的 Contoso 部署基礎結構](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>下一步

瞭解 Contoso 如何使用 Microsoft 365 for enterprise 中的[Microsoft Intune](contoso-mdm.md)來管理其裝置，以及他們在組織中執行的應用程式。

## <a name="see-also"></a>另請參閱

[Microsoft 365 Apps 企業版](/deployoffice/deployment-guide-microsoft-365-apps)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)