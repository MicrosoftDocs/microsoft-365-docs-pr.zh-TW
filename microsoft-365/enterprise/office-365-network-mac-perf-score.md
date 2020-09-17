---
title: 'Microsoft 365 網路評估 (預覽) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: 15eb514980bb53bd32380e44b6bfa174670f6b85
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948311"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 網路評估 (預覽) 

在 Microsoft 365 系統管理中心與 Microsoft 365 的連線能力頁面中， **網路評估** 會將許多網路效能度量的匯總，提煉成商業網路周邊健康情況的快照，以點數從 0-100 來表示。 網路評估同時適用于整個承租人和每個地理位置，讓使用者可以從該位置連線到您的租使用者，為 Microsoft 365 系統管理員提供一種簡單的方法來立即抓住商業網路健康情況的 gestalt，並快速深入查看任何全球辦公室位置的詳細報告。

網路評估點值是 TCP 延遲、下載速度及 UDP 連線品質度量在查看時所進行的平均衡量。 Microsoft 所擁有網路的效能度量會從這些測量值中排除，以確保評估結果對於公司網路明確且特定。

![網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

「非常低的網路評估」價值表示 Microsoft 365 用戶端在連線至租使用者時發生重大問題，或維持回應的使用者體驗，而高值則表示設定正確的網路，而不會發生很少的效能問題。 80% 的值代表正常的基準，您不應預期會因網路效能而收到有關 Microsoft 365 連線或回應回應的一般使用者意見。 隨著重複網路連線能力的增強，此值會隨著使用者經驗而增加。

>[!IMPORTANT]
>Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。

## <a name="network-assessment-panel"></a>網路評估面板

每個網路評估，不論是限定在租使用者或特定辦公室位置，都會顯示一個包含評估詳細資料的面板。 這個面板顯示評估的橫條圖，其百分比和每個元件工作負載的總點數，包括只接收度量資料的工作負載。 針對 office 位置網路評估，我們也會顯示基準，此基準是所有 Microsoft 365 用戶端中報告與您辦公室位置的資料。

![範例網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

面板中的 **評估分解** 會顯示每個元件工作負載的評估。

**評估記錄**會顯示過去30天的評估和基準。 您也可以使用 [記錄] 索引標籤，在最多兩年中報告任何 office 位置的計量歷程記錄。

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>租使用者網路評估與 office 位置網路評估

網路評估會將辦公位置的網路周邊環境設計，評定為 Microsoft 的網路。 對網路周邊的增強功能最適合於每個辦公室位置，或會影響多個位置的增強功能。

我們會在 [網路效能一覽表] 頁面上，顯示整個 Microsoft 365 租使用者的網路評估值，以及該位置 [摘要] 頁面上每個偵測到之 office 位置的特定值。

## <a name="exchange-online"></a>Exchange Online

針對 Exchange Online，從用戶端電腦到 Exchange 前端伺服器的 TCP 延遲是測量。 這可能會受到網路透過客戶局域網和 WAN 的距離所影響。 這種情況也可能會受到網路仲介裝置或服務的影響，以延遲連線或造成封包重發。 中間的 (也稱為第50個百分點值或 P50 量值，) 是針對前三天的所有度量所取。

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

針對 SharePoint 線上，可供使用者從 SharePoint Online 或 OneDrive 存取檔的下載速度。 這可能會受到用戶端電腦與 Microsoft 網路之間網路環路上可用頻寬的影響。 這通常是因為網路擁塞存在於複雜網路裝置或不良覆蓋 Wi-Fi 區域中的網路擁塞所影響。 下載速度是以每秒 mb 為單位，大約一十分之一每秒額定百萬位元的電路。 第25個百分點值 (也稱為 P25 量值，) 是針對前三天的所有度量所取。

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

Microsoft 小組評估是使用下表進行。 所有三個 UDP 測量值都必須超過所列的臨界值，以達到顯示的點數。 在頻帶內沒有任何單一位置的評估。

| UDP 封包遺失 | UDP 延遲 | UDP 抖動 | 點 |
| :-------------- | :---------- | :--------- | :----- |
| 0.25%           | 60ms        | 15ms       | 100    |
| 1.00%           | 120ms       | 40ms       | 80     |
| 1.50%           | 240ms       | 65ms       | 60     |
| 3.00%           | 275ms       | 80ms       | 40     |
| 5.00%           | 350ms       | 150ms      | 共     |
| 任何較高      | 任何較高  | 任何較高 | 0      |

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心的網路效能建議 (預覽) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 網路效能深入 (預覽) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 connectivity test in M365 Admin Center (預覽) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location 服務 (預覽) ](office-365-network-mac-location-services.md)
