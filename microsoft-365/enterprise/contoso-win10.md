---
title: Contoso 的 Windows 10 企業版部署
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何使用 System Center Configuration Manager 來部署 Windows 10 企業版的就地升級。
ms.openlocfilehash: f5f8335b8769daf28b55769fc64fed6607b69eb3
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289165"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso 的 Windows 10 企業版部署

**摘要：** 深入了解 Contoso 如何使用 System Center Configuration Manager 來部署 Windows 10 企業版的就地升級。

在 Microsoft 365 企業版廣泛發佈之前，Contoso 擁有與 Windows 相容的電腦和裝置，分別執行 Windows 7 (10%)、Windows 8.1 (65%) 和 Windows 10 (25%)。Contoso 想要升級電腦至 Windows 10 企業版，好利用增強的安全性並透過自動化部署更新降低 IT 成本。 

在評估基礎架構和業務需求後，Contoso 識別這些部署的關鍵需求：

- 執行 Windows 10 企業版的電腦和裝置越多越好
- 實施就地升級以利用現有的 System Center Configuration Manager 基礎架構
- 控制要部署的 Windows 10 企業版版本及週期性的更新
- 電腦和裝置應在最低 IT 管理成本與對使用者影響最低的情況下，保持最新狀態

最新的定義是指符合 Contoso 業務需求的受支援 Windows 10 企業版，並非指所有 Windows 相容的電腦皆執行 Windows 10 企業版最新版本。

## <a name="deployment-tools"></a>部署工具

在 Windows 10 企業版就地升級之前和期間，Contoso 使用以下 Windows Analytics 解決方案：

- 升級整備狀況  

  收集系統、應用程式及驅動程式資料以供分析，然後識別可能會阻擋升級的相容性問題與 Microsoft 已知問題的建議修正。

- 升級相容性  

  收集系統和診斷資料，包含升級安裝進度、商務用 Windows Update (WUfB) 配置資料、Windows Defender 防毒軟體資料，以及其他升級相關資訊，並將這些資料儲存在雲端分析與使用情況。

- 裝置健全狀況  

  收集 Windows 10 系統和診斷資料，包含升級安裝進度、商務用 Windows Update (WUfB) 配置資料、Windows Defender 防毒軟體資料，以及其他升級相關資訊，並將這些資料儲存在雲端分析與使用情況。
 
Contoso 已擁有 Configuration Manager (最新分支) 基礎架構。Configuration Manager 可針對大型環境進行調整並提供安裝、更新及設定的全面控制，其內建功能更讓您可輕鬆且有效率地部署及管理 Windows 10 企業版。

## <a name="planning-process"></a>規劃程序

在部署之前，Contoso 定義了以下週期：

- 三個驗證及部署階段週期 
  - 一個預覽組建週期 
  - 一個全新發行週期
  - 一個先前組建週期 
- 一個根據驗證週期資料的廣泛部署 Windows 10 企業版週期

Contoso 同時也使用 Windows Analytics 的「升級整備狀況」解決方案，判斷已安裝應用程式與 Windows 10 企業版的相容性。

## <a name="deployment-process"></a>部署程序

為了完成 Windows 10 企業版的就地升級部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：

1. 為 Configuration Manager 啟用對等快取。
2. 根據大量授權服務中心建立自訂 Windows 套件。
3. 使用 Configuration Manager 部署 Windows 套件以在內部網路發佈點，並將組建部署至三個驗證和部署執行週期。
4. 使用 Windows Analytics 的「裝置健全狀況」和「升級相容性」解決方案，對在三個驗證和部署執行週期中的電腦和裝置執行成功評估。
5. Contoso 根據 Windows Analytics 資訊，判斷要部署至廣泛部署週期的 Windows 10 企業版版本。
6. 執行 Configuration Manager 的部署工作順序，將指定的 Windows 套件部署至廣泛部署週期。
7. 使用 Windows Analytics 的「裝置健全狀況」和「升級相容性」解決方案，監控在廣泛部署週期中的電腦和裝置及解決問題。

圖 1 顯示就地升級和持續更新部署的基礎架構。

![](./media/contoso-win10/contoso-win10-fig1.png)
 
**圖 1：Contoso 的 Windows 10 企業版部署基礎架構**

此基礎架構的組成為：

- System Center Configuration Manager，功用是：
  - 從 Microsoft 網路中的 Microsoft 大量授權取得取得 Windows 10 企業版套件的映像。
  - 部署套件的管理中心點。
- 通常位於 Contoso 衛星辦公室的地區發布點。
- 在不同地點的 Windows 電腦和裝置會根據週期成員資格，收到並安裝就地升級部署或持續更新套件。

## <a name="next-step"></a>下一步

[深入了解](contoso-o365pp.md) Contoso 如何使用 System Center Configuration Manager 基礎結構，在整個組織部署及保持目前的 Office 365 專業增強版。 

## <a name="see-also"></a>另請參閱

[Microsoft 365 企業版的 Windows 10 企業版](windows10-infrastructure.md)

[部署指南](deploy-microsoft-365-enterprise.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)
