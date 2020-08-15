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
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695616"
---
# <a name="microsoft-365-network-assessment-preview"></a>Microsoft 365 網路評估 (預覽) 

在 Microsoft 365 系統管理中心連線至 Microsoft 365 頁面時， **網路評估** 會將許多網路效能度量的匯總，提煉成商業網路健康情況的快照，以點值從 1-100 來表示。 網路評估同時適用于整個承租人和每個地理位置，讓使用者可以從該位置連線到您的租使用者，為 Microsoft 365 系統管理員提供一種簡單的方法來立即抓住商業網路健康情況的 gestalt，並快速深入查看任何全球辦公室位置的詳細報告。

網路評估點值是在查看時所整理的延遲、頻寬、下載速度及連線品質度量平均測量值。 Microsoft 所擁有網路的效能度量會從這些測量值中排除，以確保評估結果對於公司網路明確且特定。

![網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

「非常低的網路評估」價值表示 Microsoft 365 用戶端在連線至租使用者時發生重大問題，或維持回應的使用者體驗，而高值則表示設定正確的網路，而不會發生很少的效能問題。 80% 的值代表正常的基準，您不應預期會因網路效能而收到有關 Microsoft 365 連線或回應回應的一般使用者意見。 隨著重複網路連線能力的增強，此值會隨著使用者經驗而增加。

>[!IMPORTANT]
>Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。

## <a name="network-assessment-panel"></a>網路評估面板

每個網路評估，不論是限定在租使用者或特定辦公室位置，都會顯示一個包含評估詳細資料的面板。 這個面板顯示評估的橫條圖，其百分比和每個元件工作負載的總點數，包括只接收度量資料的工作負載。 針對 office 位置網路評估，我們也會顯示基準，此基準是所有 Microsoft 365 用戶端中報告與您辦公室位置的資料。

![範例網路評估價值](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

面板中的 **評估分解** 會顯示每個元件工作負載的評估。

**評估記錄**會顯示過去30天的評估和基準。

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>租使用者網路評估與 office 位置網路評估

網路評估會將辦公位置的網路周邊環境設計，評定為 Microsoft 的網路。 對網路周邊的增強功能最適合於每個辦公室位置，或會影響多個位置的增強功能。

我們會在 [網路效能一覽表] 頁面上，顯示整個 Microsoft 365 租使用者的網路評估值，以及該位置 [摘要] 頁面上每個偵測到之 office 位置的特定值。

## <a name="exchange-online"></a>Exchange Online

針對 Exchange Online，從用戶端電腦到 Exchange 前端伺服器的 TCP 延遲是測量。 這可能會受到網路透過客戶局域網和 WAN 的距離所影響。 這種情況也可能會受到網路仲介裝置或服務的影響，以延遲連線或造成封包重發。

## <a name="sharepoint-online"></a>SharePoint Online

針對 SharePoint 線上，可供使用者存取檔的下載速度進行度量。 這可能會受到用戶端電腦與 Microsoft 網路之間網路環路上可用頻寬的影響。 這通常是因為網路擁塞存在於複雜網路裝置或不良覆蓋 Wi-Fi 區域中的網路擁塞所影響。

## <a name="microsoft-teams"></a>Microsoft Teams

針對 Microsoft 小組，網路品質是指 UDP 延遲、UDP 抖動及 UDP 封包遺失。 UDP 可用於 Microsoft 小組的通話和會議音訊和影片媒體連線。 這可能會受到延遲和下載速度相同的因素所影響，除了 UDP 是分別設定為較為常見的 TCP 通訊協定以外，其他情況也是在網路的 UDP 支援中使用網路中斷性。

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心的網路效能建議 (預覽) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 網路效能深入 (預覽) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 connectivity test in M365 Admin Center (預覽) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location 服務 (預覽) ](office-365-network-mac-location-services.md)
