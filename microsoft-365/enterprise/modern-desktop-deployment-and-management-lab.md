---
title: Windows 10 和 Office 365 部署的 Lab Kit
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 04/26/2021
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並得知何處可以存取 Windows 和 Office 部署的 Lab Kit。
ms.openlocfilehash: 33db334ecf977b351ac963107c647c7eff414cc0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288884"
---
# <a name="windows-10-and-office-365-deployment-lab-kit"></a>Windows 10 和 Office 365 部署的 Lab Kit

Windows 10 和 Office 365 部署實驗室套件的設計目的是協助您規劃、測試及驗證執行 Windows 10 企業版和 Microsoft 365 Apps 企業版的桌面部署和管理。 套件封面中的實驗室使用 Microsoft Endpoint Configuration Manager、桌面分析、Office 自訂工具、OneDrive、Windows Autopilot 等等。

強烈建議使用此套件準備 Windows 8.1 升級為 Windows 10 的組織。 如果您目前使用 Windows 10、Microsoft 365 Apps 企業版 (先前 Office 365 專業增強版) 或 Office 2019，也會套用這種方式。 在隔離環境中，產生的實驗室非常適合用來探索部署工具的更新，並測試部署相關的自動化。

[下載 Windows 10 和 Office 365 部署實驗室套件](https://www.microsoft.com/evalcenter/evaluate-lab-kit)。

## <a name="a-complete-lab-environment"></a>完整的實驗室環境

套件為您提供自動布建的虛擬實驗室環境（包括已加入網域的桌面用戶端、網域控制站、Internet 閘道和完全設定的 Configuration Manager 實例）。 套件包含下列產品的最新評估版本：

- 新增！ Windows 10 企業版，版本21H1
- Windows 7 企業版
- 新增！ Microsoft Endpoint Configuration Manager，版本2103
- Windows Assessment and Deployment Kit for Windows 10
- Microsoft Deployment Toolkit
- Microsoft Application Virtualization (App-V)
- Microsoft BitLocker Administration and Monitoring
- Windows Server
- Microsoft SQL Server

產生的實驗設計為連線到的實驗：

- Microsoft 365 E5
- Microsoft 365 Apps 企業版
- 具有 Enterprise Mobility + Security (EMS) 的 Office 365 E5

## <a name="step-by-step-labs"></a>逐步實驗室

詳細的實驗室指南可透過多個部署和管理案例來引導您。 我們已為最新版本的 Intune 和 Configuration Manager 更新實驗室。

### <a name="plan-and-prepare-infrastructure"></a>規劃及準備基礎結構

- 電腦分析
- 雲端管理閘道 & 雲端發佈點
- 新增！ 租使用者附加及共同管理
- 新增！ 端點分析
-  (VPN) 的遠端存取

### <a name="prepare-configuration"></a>準備設定

- 優化 Windows 10 更新傳遞
- 使用群組原則來處理 Windows 10
- 使用 Microsoft Intune 服務 Windows 10
- 使用 Configuration Manager 服務 Windows 10
- 使用 Configuration Manager 維護 Microsoft 365 Apps 企業版
- 使用 Intune 服務 Microsoft 365 Apps 企業版
- 安全性與合規性

### <a name="prepare-applications"></a>準備應用程式

- Office 的準備工作工具
- MSIX Win32 應用程式的打包及轉換

### <a name="deploy-windows-10"></a>部署 Windows 10

- Configuration Manager 中的作業系統部署工作順序
- Microsoft 部署工具組中的作業系統部署工作順序 (MDT) 
- Windows Autopilot
- 部署及管理新的 Microsoft Edge

### <a name="deploy-microsoft-365-apps-for-enterprise"></a>部署 Microsoft 365 Apps 企業版

- 雲端管理部署
- 本機管理的部署
- Microsoft 365 Apps 企業版在非 AD 上加入的裝置上部署
- 使用 Configuration Manager Enterprise 受管理的部署
- 使用 Microsoft Intune Enterprise 受管理的部署
- 使用 Microsoft Intune 的 LOB 部署和管理
- 部署 Microsoft Teams
- 新增！ 工作分派篩選

### <a name="deploy-windows-virtual-desktop"></a>部署 Windows 虛擬機器

- Prepare、deploy、optimize

## <a name="where-to-find-the-windows-10-and-office-365-deployment-lab-kit"></a>哪裡可以找到 Windows 10 和 Office 365 部署實驗室工具組

[下載 Windows 和 Office 部署的 Lab Kit](https://www.microsoft.com/evalcenter/evaluate-lab-kit)。

> [!NOTE]
> 請使用寬頻網際網路連線來下載此內容，並允許自動布建30-45 分鐘。 實驗室環境至少需要 16 GB 的可用記憶體和 150 GB 可用磁碟空間。 為了達到最佳效能，建議使用 32 GB 的可用記憶體和 300 GB 的可用空間。 套件會在2021年8月23日到期。 在到期之前會發佈新的版本。

## <a name="additional-guidance"></a>其他指引

- [來自 Microsoft Mechanics 的桌面部署中心系列影片](https://www.aka.ms/watchhowtoshift)
- [Microsoft Endpoint Configuration Manager 作業系統部署](/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)
- [Windows 10 部署計劃](/windows/deployment/planning/index)
- [Microsoft 365 Apps 部署指南](/deployoffice/deployment-guide-microsoft-365-apps)
- [開始使用 Intune](/intune/get-started-evaluation)

## <a name="related-resources"></a>相關資源

- [介紹 Microsoft Office 365](https://www.microsoft.com/microsoft-365/default.aspx) (英文)
- [商務用 Office 365](https://products.office.com/business/office)
- [Introducing Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
- [適用於企業的 Windows 10](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)
- [適用於中小型企業的 Windows 10](https://www.microsoft.com/WindowsForBusiness/windows-for-small-business)
