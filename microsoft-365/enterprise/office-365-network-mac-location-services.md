---
title: 'Microsoft 365 Network Connectivity Location 服務 (預覽) '
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
description: 'Microsoft 365 Network Connectivity Location 服務 (預覽) '
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200778"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Microsoft 365 Network Connectivity Location 服務 (預覽) 

Microsoft 365 系統管理中心現在會顯示 **網路洞察力和效能建議**，這些建議是從您的 Microsoft 365 租使用者收集到的即時效能度量，而且只能供您租使用者中的系統管理使用者查看。 組織網路連線是透過網際網路的網路出局位置，為每個辦公室的位置所設計。 Microsoft 365 用戶端連線會使用該路由，然後透過網際網路傳送至 Microsoft 服務的前端伺服器。 識別辦公室位置是可顯示這些網路洞察力的關鍵。

## <a name="location-in-network-measurements"></a>網路度量的位置

組織的管理員可以選擇是否要在此功能使用的網路度量中包含的位置。 這可讓您在每個辦公室所在的城市自動探索。 位置資訊不是精確的，而且會加以混淆以300m 及依城市分類。 在 Windows 裝置上捕獲位置時，系統會顯示工具託盤中的 [ **位置內使用** ] 圖示，系統管理員可能會想要通知使用者這種情況。 透過這項處理，該位置會被視為組織辦公室位置，而非人員或裝置的位置。 網路洞察力可在這些已探索的 office 位置城市顯示。 如果需要更精確的建議，系統管理員可以輸入特定的 office 位置位址，而網路洞察力也會匯總至這些位址。 辦公室位置的合計不能超過300米。

## <a name="location-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的位置

在 Microsoft 365 系統管理中心中，Bing 地圖控制項是用來顯示組織辦公室位置所在的位置，以及顯示所選辦公室位置的網路周邊拓撲。 當系統管理員新增 office 位置的特定位址詳細資料時，Bing 地圖也可以用來建議位址，讓資料輸入更容易。

## <a name="terms-of-use"></a>使用條款

透過 Bing 地圖提供的任何內容（包括 geocodes），只能在提供內容的產品內使用。 客戶使用 Microsoft 365 Admin Center Location 服務功能（由 Bing 地圖供電）受 bing 地圖的制約，其 _使用於的 Bing 地圖使用者使用條款_ <https://go.microsoft.com/?linkid=9710837> 和 _Microsoft 隱私權聲明_ 可用於 <https://go.microsoft.com/fwlink/?LinkID=248686.>

此功能（透過 Bing 地圖提供）也是由 **這裡的技術**支援。 Bing 地圖如何利用這裡技術所提供的位置服務，受下列 _技術服務條款_ 的制約 <https://legal.here.com/en-gb/terms> 。

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心的網路連線 (預覽) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 網路效能深入 (預覽) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 網路評估 (預覽) ](office-365-network-mac-perf-score.md)

[Microsoft 365 connectivity test in M365 Admin Center (預覽) ](office-365-network-mac-perf-onboarding-tool.md)
