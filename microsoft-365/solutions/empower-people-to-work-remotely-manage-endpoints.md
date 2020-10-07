---
title: 步驟 4： 為您的裝置、電腦和其他端點部署端點管理
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 端點管理員來管理受管理的裝置、電腦及其他端點。
ms.openlocfilehash: 5c6e433918709a55f03d786891ec0fd7ac62a26b
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377232"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>步驟 4： 為您的裝置、電腦和其他端點部署端點管理

若雇用遠端工作者，您必須支援日益增加的個人裝置。 端點管理是原則型的安全性方法，要求裝置必須符合特定準則，才能獲得存取資源的授權。 [Microsoft 端點管理員] 提供現代化管理功能，保護您的雲端資料及內部檔案的安全。 

端點管理員提供可管理行動裝置、電腦、虛擬機器、嵌入式裝置及伺服器的服務和工具，並結合您可能已經知道且正在使用的服務。

![端點管理元件](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune 是一種雲端式服務，專門用於 Microsoft 365 隨附的行動裝置管理 (MDM) 和行動應用程式管理 (MAM)。 

- **MDM：** 針對組織擁有的裝置，您可以執行完全控制功能，包括設定、功能及安全性。 裝置會在 Intune 中「註冊」，並在其中接收 Intune 原則以及規則和設定。 例如，您可以設定密碼和 PIN 需求、建立 VPN 連線、設定威脅防護等等。

- **MAM：** 遠端工作者可能不希望您在其個人裝置 (也稱為攜帶您自己的裝置 (BYOD)) 上擁有完全控制權。 您可以提供遠端工作者選項，但是仍然保護貴組織。 例如，如果遠端工作者想要完全存取組織資源，可以註冊其裝置。 或者，如果這些使用者只想要存取電子郵件或 Microsoft Teams，請使用需要多重要素驗證 (MFA) 的應用程式保護原則來使用這些應用程式。

如需詳細資訊，請參閱 [Microsoft Intune 概觀](https://docs.microsoft.com/intune/fundamentals/what-is-intune)。

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager 是一種內部部署管理解決方案，可管理網路或網際網路上的桌上型電腦、伺服器和膝上型電腦。 使用 Configuration Manager 部署應用程式、軟體更新及作業系統。 您也可以即時監視合規性、查詢和操作用戶端，以及執行更多動作。 您可以在雲端啟用此功能，讓它與 Intune、Azure AD、Microsoft Defender ATP 和其他雲端服務整合。 

如需詳細資訊，請參閱 [Configuration Manager 概觀](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)。

## <a name="co-management"></a>共同管理

共同管理會使用 Intune 和其他 Microsoft 365 雲端服務，將您現有的內部部署 Configuration Manager 投資與雲端結合。 您可以選擇將 Configuration Manager 或 Intune 設定為不同工作負載的管理單位。 

共同管理使用 Intune 型雲端功能，包括條件式存取權和強制執行裝置合規性。 您可以將部分工作保留在內部部署中，同時雲端中執行其他工作。

如需詳細資訊，請參閱[共同管理概觀](https://docs.microsoft.com/mem/configmgr/comanage/overview)。

## <a name="desktop-analytics"></a>電腦分析

桌面分析是與 Configuration Manager 整合的雲端型服務，可提供深入解析與情報，讓您對 Windows 用戶端做出正確決策。 它會結合組織的資料，與從連線到 Microsoft 雲端服務的上百萬裝置上彙總的資料。 

使用電腦分析，您可以：

- 建立組織中執行之應用程式的庫存。
- 使用最新的 Windows 10 功能更新評估應用程式相容性。
- 找出相容性問題，並根據啟用雲端的資料深入解析來接收緩解建議。
- 建立試驗組，代表最少裝置集的整個應用程式和驅動程式資源。
- 將 Windows 10 部署到試驗和生產管理的裝置。

如需詳細資訊，請參閱[桌面分析概觀](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)。

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot 是一種零觸控、自助式 Windows 部署平台。 其中包含用來設定和預先設定新裝置的技術集合，讓這些技術可供生產使用。 您也可以使用 Windows Autopilot 來重設、重新利用和復原裝置。 

Windows Autopilot 能讓 IT 部門透過簡單易行的流程，幾乎不需要管理任何基礎架構即可預先設定裝置。 

- 從使用者的角度來看，只需要幾個簡單的操作就能將裝置準備就緒。 
- 從 IT 專業人員的角度，使用者唯一需要進行的互動就是連線網路和驗證認證。

如需詳細資訊，請參閱 [Windows Autopilot 概觀](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)。

## <a name="admin-technical-resources-for-endpoint-management"></a>適用於端點管理的系統管理技術資源

- [第 3 部分影片，為遠端工作者適用的 Windows 10 裝置管理](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [第5部分影片，為遠端工作者適用的使用者桌面和瀏覽器管理](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [為 Microsoft 365 部署移動性基礎結構](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [如何註冊不同的裝置類型以管理行動裝置](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [如何向使用者說明 Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>步驟 3 的結果

您正在使用端點管理員功能套件來管理行動裝置、電腦、虛擬機器、嵌入式裝置及伺服器。

## <a name="next-step"></a>下一步

繼續進行[步驟 5](empower-people-to-work-remotely-teams-productivity-apps.md)，讓您的遠端工作者能使用 Microsoft 365 生產力應用程式，例如 Microsoft Teams。
