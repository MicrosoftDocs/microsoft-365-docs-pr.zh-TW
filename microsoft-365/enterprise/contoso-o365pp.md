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
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754339"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>適用於 Contoso 的 Microsoft 365 Apps 企業版部署

Contoso 將其電腦升級至 Windows 10 企業版和 Microsoft 365 應用程式的企業版，以啟用更有效率的共同作業、更好的安全性，以及更新式的桌面體驗。在評估其基礎結構和業務需求之後，Contoso 識別出下列部署的主要需求：

- 所有的電腦都應該執行適用于 enterprise 的 Microsoft 365 應用程式。
- 部署應盡可能使用現有的管理工具和基礎結構。
- 在使用者的裝置上部署必須支援多種語言和現有的架構。
- 電腦應該以最少的 IT 管理成本和對使用者的影響降至最低的方式，保持最新狀態及安全性。

## <a name="deployment-tools"></a>部署工具

根據他們的需求，Contoso 選擇透過 Configuration Manager 來部署 Windows 10 企業版和 Microsoft 365 應用程式 (目前的分支) 。Configuration Manager 針對大型環境進行調整，並提供對安裝、更新及設定的廣泛控制。它也具有內建的功能，可讓您更輕鬆快捷地部署及管理 Office，包括：

- 對等快取，可在部署至遠端位置的裝置時協助有限的網路容量。
- Office 用戶端管理儀表板，可讓您輕鬆地部署 Office 和監控更新，並可讓系統管理員存取最新的部署和管理功能。
- 智慧語言套件部署，包括自動部署與作業系統相同的語言。
- 在部署期間，從用戶端移除 Office 的現有版本的完全支援和便於使用的方法。

除了 Configuration Manager 之外，Contoso 使用 [office 增益集和 VBA 的準備工作](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)工具，可以從 Microsoft 取得免費工具，以評估其 Office 宏及增益集的相容性問題。

## <a name="managing-deployment-and-updates"></a>管理部署和更新

Microsoft 365 應用程式 enterprise 具有新的版本模型： Office 即服務。服務模型可讓您輕鬆掌握最新的功能。不過，它通常需要 IT 部門變更其部署與測試新版本的方式。若要將相容性問題降至最低，以確保其電腦維持在最新狀態，Contoso 會分兩個階段部署 Windows 和 Office：

- 首先，他們將 Microsoft 365 應用程式部署到整個組織中的一小小組代表裝置。 此試驗群組是用來測試應用程式、增益集及硬體與 Microsoft 365 應用程式企業版的應用程式。
- Contoso 在四個月後解決應用程式、增益集與硬體試驗群組中的所有重大問題， 並將 Microsoft 365 Apps 企業版部署至整個組織的裝置 (大型群組)。

Contoso 從雲端啟用自動更新，而不是使用 Configuration Manager 管理 Office 更新。 雲端式更新可減少管理負荷，同時確保裝置保持最新狀態。

Contoso 已遵循用於部署 Office 的功能更新的兩階段方式：在試驗群組中的裝置接收到的功能更新，于組織的其餘部分中的裝置的兩個月之前， (廣泛的群組) 。 若要為 Office 啟用這項功能，Contoso 使用兩個建議的 [更新通道](https://docs.microsoft.com/DeployOffice/overview-update-channels)：

- 對試驗群組更新的半年通道(預覽)
- 針對廣泛的群組更新 Semi-Annual Enterprise 通道

由於半年企業通道 (預覽) 比半年企業通道早四個月發行 Microsoft 365 Apps 企業版，因此 Contoso 有時間在無需管理更新下，進型驗證更新。

## <a name="deployment-process"></a>部署程序

為了完成 Office 部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：

1. 部署之前，Contoso 使用 Office 增益集和 VBA 的準備工作工具組來測試其應用程式和 Office 增益集，以評估其與 Microsoft 365 應用程式的相容性。
1. 在 Configuration Manager 中，他們會在其用戶端裝置上啟用對等快取，以在部署至遠端位置的用戶端裝置時，協助有限的網路容量。 
1. Contoso 在 Configuration Manager 中將兩個部署群組定義為裝置集合：一個試驗群組和一個廣泛的群組。 試驗群組（包含整個組織中一小部分的代表裝置），用來進一步測試應用程式、增益集，以及 Windows 10 企業版和 Microsoft 365 應用程式的硬體。
1. 他們會使用 Office 用戶端管理儀表板和 Office 365 Installer 嚮導（同時是 Configuration Manager 主控台的一部分）建立 Office 的部署套件。 他們會為企業套件建立兩個 Microsoft 365 應用程式，一個用於 Semi-Annual Enterprise 通道 (Preview) 上的試驗群組，另一個適用于 Semi-Annual Enterprise 通道上的廣泛群組。
2. 每個 Office 套件都包含英文、法文和德文語言套件。 如果裝置所需的語言並未包含在 Office 套件中，該語言套件會從 Office 內容傳遞網路（ (CDN) 中自動下載）。
3. 他們先使用 Office 套件中的內建功能自動移除所有現有的 MSI 版本 Office，再安裝 Microsoft 365 Apps 企業版。
4. 在 Configuration Manager 中，他們會將 Windows 和 Office 套件部署到跨其網路的發佈點。 然後，他們會執行 Configuration Manager 部署工作順序，將 Microsoft 365 應用程式的試用版應用程式部署到試驗群組。
5. 當使用者解決試驗群組的相容性問題之後，Contoso 執行工作順序，將 Microsoft 365 應用程式套件部署到廣泛的群組。

因為 Contoso 選擇從雲端自動更新裝置，因此不需要管理 Configuration Manager 中的程序。 其裝置會根據初始部署中所定義的更新通道，直接從雲端自動更新。

以下是 Contoso Microsoft 365 Apps for enterprise 安裝和持續更新部署架構。

![適用于企業的 Microsoft 365 應用程式的 Contoso 部署基礎結構](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>下一步

深入瞭解 Contoso 如何在 Microsoft 365 for enterprise 中 [使用 Microsoft Intune](contoso-mdm.md) 來管理其裝置，以及他們在整個組織中執行的應用程式。

## <a name="see-also"></a>請參閱

[Microsoft 365 Apps 企業版](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)
