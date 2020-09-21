---
title: 'Microsoft 365 網路評估 (預覽) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: 'Microsoft 365 網路評估 (預覽) '
ms.openlocfilehash: 21fb9515ea1621225cffbe23fe87d0daeb5265de
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104543"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 網路評估 (預覽) 

在 Microsoft 365 系統管理中心的網路連線中， **網路評估** 會將許多網路效能度量的集合提煉成商業網路周邊健康情況的快照，以來自 0-100 的點值來表示。 網路評估會告訴您，客戶負責網路設計的程度會影響 Office 365 使用者體驗。 網路評估同時適用于整個承租人和每個地理位置，讓使用者可以從該位置連線到您的租使用者，為 Microsoft 365 系統管理員提供一種簡單的方法來立即抓住商業網路健康情況的 gestalt，並快速深入查看任何全球辦公室位置的詳細報告。

網路評估點值是一天內編譯的 TCP 延遲、下載速度及 UDP 連線品質計量的平均。 Microsoft 所擁有網路的效能度量會從這些測量值中排除，以確保評估結果對於公司網路明確且特定。

![網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

「非常低的網路評估」價值表示 Microsoft 365 用戶端在連線至租使用者時發生重大問題，或維持回應的使用者體驗，而高值則表示設定正確的網路，而不會發生很少的效能問題。 80% 的值代表正常的基準，您不應預期會因網路效能而收到有關 Microsoft 365 連線或回應回應的一般使用者意見。 隨著重複網路連線能力的增強，此值會隨著使用者經驗而增加。

| 網路評估 | 預期的使用者經驗 |
| :----------------- | :----------------------- |
| 100                | 最佳                     |
| 80                 | 符合建議    |
| 60                 | 可以接受               |
| 40                 | 使用者可能會遇到問題 |
| 共                 | 使用者可能會抱怨       |
| 0                  | 網路問題討論的一般主題 |

>[!IMPORTANT]
>Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。

## <a name="network-assessment-panel"></a>網路評估面板

每個網路評估，不論是限定在租使用者或特定辦公室位置，都會顯示一個包含評估詳細資料的面板。 這個面板顯示評估的橫條圖，其百分比和每個元件工作負載的總點數，包括只接收度量資料的工作負載。 針對 office 位置網路評估，我們也會365顯示每五個 quintiles 中，每五個的資料，都與您的辦公室位置報告的資料在相同的城市中。

![範例網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

面板中的 **評估分解** 會顯示每個元件工作負載的評估。

**評估記錄**會顯示過去30天的評估和基準。 您也可以使用 [記錄] 索引標籤，在最多兩年中報告任何 office 位置的計量歷程記錄。[記錄] 索引標籤可讓您選取要報告的屬性，並選擇報告的時間範圍您可以反白顯示網路更新專案的影響，並查看網路評估的改進功能。

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>租使用者網路評估與 office 位置網路評估

網路評估會將辦公位置的網路周邊環境設計，評定為 Microsoft 的網路。 在每個辦公室位置，最適合對網路周邊進行改進。

我們會在 [網路效能一覽表] 頁面上顯示整個 Microsoft 365 租使用者的網路評估值，這是所有 office 位置之網路評估的加權平均值。 在該位置的 [摘要] 頁面上，每個偵測到之 office 位置的特定網路評估值也是一種。

## <a name="exchange-online"></a>Exchange Online

針對 Exchange Online，從用戶端電腦到 Exchange 服務前面門的 TCP 延遲是測量。 這可能會受到網路透過客戶局域網和 WAN 的距離所影響。 這種情況也可能會受到網路仲介裝置或服務的影響，以延遲連線或造成封包重發。 而且會受到最近的 Exchange 服務前端門的距離所影響。 中間的 (也稱為第50個百分點值或 P50 量值，) 是針對前三天的所有度量所取。

Exchange Online 評估是使用下表進行。 在頻帶中以線性方式指派閾值之間的任何 TCP 延遲數位。

| TCP 延遲   | 點 |
| :------------ | :----- |
| 10ms 或更少  | 100    |
| 25ms          | 80     |
| 100ms         | 60     |
| 200ms         | 40     |
| 300ms         | 共     |
| 350ms 或更多 | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

針對 SharePoint 線上，可供使用者從 SharePoint 或 OneDrive 存取檔的下載速度。 這可能會受到用戶端電腦與 Microsoft 網路之間網路環路上可用頻寬的影響。 這通常是因為網路擁塞存在於複雜網路裝置或不良覆蓋 Wi-Fi 區域中的網路擁塞所影響。 下載速度是以每秒 mb 為單位，大約一十分之一每秒額定百萬位元的電路。 每秒兆單位都很有用，因為您可以直接查看1秒內可下載的檔案大小。 第25個百分點值 (也稱為 P25 量值，) 是針對前三天的所有度量所取。 這第25個百分點可協助減少隨時間變化的擁塞影響。

使用下表進行 SharePoint 線上評估。 在頻帶中以線性方式指派閾值之間的任何下載速度。

| 下載速度 | 點 |
| :------------- | :----- |
| 20MBps 或更多 | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 共     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

針對 Microsoft 小組，網路品質是指 UDP 延遲、UDP 抖動及 UDP 封包遺失。 UDP 可用於 Microsoft 小組的通話和會議音訊和影片媒體連線。 這可能會受到延遲和下載速度相同的因素所影響，除了 UDP 是分別設定為較為常見的 TCP 通訊協定以外，其他情況也是在網路的 UDP 支援中使用網路中斷性。 中間的 (也稱為第50個百分點值或 P50 量值，) 是針對前三天的所有度量所取。 

從一到五的比例，我們計算來自這些 UDP 量值的平均觀點評分。 然後，我們會對應至 Microsoft 小組網路評估的0-100 點規模。  整體正常情況超過87.5 點，整體壞點低於50點。

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心的網路連線 (預覽) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 網路效能深入 (預覽) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 connectivity test in M365 Admin Center (預覽) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location 服務 (預覽) ](office-365-network-mac-location-services.md)

[Microsoft 365 network connectivity test 工具 (預覽) ](office-365-network-mac-perf-onboarding-tool.md)
