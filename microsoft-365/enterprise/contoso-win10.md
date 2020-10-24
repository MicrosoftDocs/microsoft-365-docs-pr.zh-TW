---
title: Contoso 的 Windows 10 企業版部署
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
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 來部署 Windows 10 企業版的就地升級。
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754242"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso 的 Windows 10 企業版部署

在 Microsoft 365 for enterprise 的廣泛展示之前，Contoso 具有 Windows 相容的電腦和裝置，其混合了 Windows 7 (10% ) 、Windows 8.1 (65% ) 和 Windows 10 (25% ) 。Contoso 想要升級其電腦的 Windows 10 企業版利用高級安全性，並從自動部署更新，降低 IT 負荷。 

在評估基礎架構和業務需求後，Contoso 識別這些部署的關鍵需求：

- 執行 Windows 10 企業版的電腦和裝置越多越好
- 實施就地升級以利用現有的 Configuration Manager 基礎架構
- 控制要部署的 Windows 10 企業版版本及週期性的更新
- 電腦和裝置應在最低 IT 管理成本與對使用者影響最低的情況下，保持最新狀態

最新的定義是指符合 Contoso 業務需求的受支援 Windows 10 企業版，並非指所有 Windows 相容的電腦皆執行 Windows 10 企業版最新版本。

## <a name="deployment-tools"></a>部署工具

在 Windows 10 企業版就地升級之前和期間，Contoso 使用以下 Windows Analytics 解決方案：

- 升級整備狀況  

  收集系統、應用程式及驅動程式資料以供分析，然後識別可能會阻擋升級的相容性問題與 Microsoft 已知問題的建議修正。

- 升級相容性  

  針對 Windows 更新顯示裝置的狀態，讓您能視需要確保這些裝置處於最新更新狀態。

- 裝置健全狀況  

  識別經常當機，因此可能需要重建或更換的裝置，以及導致裝置當機的裝置驅動程式，並建議能減少當機次數的驅動程式替代版本。 提供 Windows 資訊保護設定錯誤的通知，並傳送提示給使用者。
 
Contoso 已擁有 Configuration Manager (最新分支) 基礎架構。Configuration Manager 可針對大型環境進行調整並提供安裝、更新及設定的全面控制，其內建功能更讓您可輕鬆且有效率地部署及管理 Windows 10 企業版。

## <a name="planning-process"></a>規劃程序

Contoso 使用 Windows Analytics 中的升級準備，判斷已安裝應用程式的集合，及其與 Windows 10 企業版的相容性。

## <a name="deployment-process"></a>部署程序

為了完成 Windows 10 企業版的就地升級部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：

1. 為 Configuration Manager 啟用對等快取。
2. 根據大量授權服務中心建立自訂 Windows 套件。
3. 使用 Configuration Manager 將 Windows 套件部署到跨網路的發佈點，並將其部署至三個驗證和部署過渡群組。
4. 使用 Windows Analytics 的「裝置健全狀況」和「升級相容性」解決方案，對在三個驗證和部署執行週期中的電腦和裝置執行成功評估。
5. 根據 Windows Analytics 資訊，Contoso 決定要部署至廣泛部署群組的 Windows 10 企業版版本。
6. 執行 Configuration Manager 部署工作順序，將選取的 Windows 套件部署到廣泛的部署群組。
7. 使用裝置健康情況和更新規範解決方案，在廣泛的部署群組中監控電腦和裝置，以解決問題。

這是 Contoso 就地升級和持續更新部署的基礎架構。

![Contoso 的 Windows 10 企業版部署基礎架構](../media/contoso-win10/contoso-win10-fig1.png)

此基礎架構的組成為：

- Configuration Manager，其：
  - 從 Microsoft 網路中的 Microsoft 大量授權取得取得 Windows 10 企業版套件的映像。
  - 部署套件的管理中心點。
- 通常位於 Contoso 地區中心辦公室的地區發布點。
- 在不同位置上的 Windows 電腦和裝置，會根據群組成員資格，針對就地升級或持續更新接收及安裝部署套件。

## <a name="next-step"></a>下一步

瞭解 Contoso 如何利用其 Configuration Manager 基礎結構，在其整個組織中 [部署及保留目前的 Microsoft 365 應用程式](contoso-o365pp.md) 。 

## <a name="see-also"></a>請參閱

[Windows 10 企業版](https://docs.microsoft.com/windows/deployment/)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)
