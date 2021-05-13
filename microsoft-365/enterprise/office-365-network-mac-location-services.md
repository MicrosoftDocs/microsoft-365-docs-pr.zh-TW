---
title: Microsoft 365網路連接位置服務
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365網路連接位置服務
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470445"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365網路連接位置服務

Microsoft 365 系統管理中心現在會顯示 **網路洞察力和效能建議**，也就是從您的 Microsoft 365 租使用者收集到的即時效能度量。 只有租使用者中的系統管理使用者可以查看這些計量。 組織網路連線是透過網際網路的網路出局位置，為每個辦公室的位置所設計。 Microsoft 365 用戶端連線會使用該路由，然後透過網際網路到 Microsoft 服務的前端伺服器。 識別辦公室位置是可顯示這些網路洞察力的關鍵。

## <a name="location-in-network-measurements"></a>網路度量的位置

組織的管理員可以選擇是否要在此功能使用的網路度量中包含的位置。 這可讓您在每個辦公室所在的城市自動探索。 位置資訊不是精確的，而且會加以混淆以300m 及依城市分類。 在 Windows 裝置上捕獲位置時，裝置會在工具託盤中顯示 **位置使用中** 圖示。 管理員可能會想要通知使用者此圖示的外觀。 透過這項處理，該位置會被視為組織辦公室位置，而非人員或裝置的位置。 網路洞察力可在這些已探索的 office 位置城市顯示。 如果您想要在建議中獲得更高的精確度，您可以輸入特定的 office 位置位址。 而是會將網路洞察力匯總到這些位置。 Office 位置的匯總不能大於300米。

## <a name="location-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的位置

在 Microsoft 365 系統管理中心中，Bing map 控制項是用來顯示組織辦公室位置的位置。 控制項也會顯示所選辦公室位置的網路周邊拓撲。 當系統管理員新增 office 位置的特定位址詳細資料時，Bing 地圖服務也會用來建議位址，讓資料輸入更容易。

## <a name="terms-of-use"></a>使用條款

透過 Bing 地圖服務提供的任何內容（包括 geocodes），只能在提供內容的產品內使用。 客戶使用由 Bing 地圖服務所提供的 Microsoft 365 系統管理中心位置服務功能，受 _Bing 地圖服務 End-User 使用條款_ 的制約， <https://go.microsoft.com/?linkid=9710837> 並由 [Microsoft 隱私權聲明](https://go.microsoft.com/fwlink/?LinkID=248686)使用。

**TomTom** 也支援此功能（透過 Bing 地圖服務提供）。 您可以在 TomTom 的產品和服務上找到相關資訊 [https://www.tomtom.com/legal](https://www.tomtom.com/legal) 。

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心的網路連線 (預覽) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 網路效能深入 (預覽) ](office-365-network-mac-perf-insights.md)

[ (預覽 Microsoft 365 網路評估) ](office-365-network-mac-perf-score.md)

[Microsoft 365 系統管理中心的 Microsoft 365 連線測試 (預覽) ](office-365-network-mac-perf-onboarding-tool.md)
