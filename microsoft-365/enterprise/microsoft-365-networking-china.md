---
title: 為中國使用者 Microsoft 365 全域承租人效能優化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文提供針對全球 Microsoft 365 承租人的中國使用者優化網路效能的指導方針。
ms.openlocfilehash: f48b552dec72d78e2429aedf6a3834dba6c7590a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844499"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>為中國使用者 Microsoft 365 全域承租人效能優化

> [!IMPORTANT]
> 此指導方針是特定使用案例中的 **企業 Microsoft 365 使用者** 連接至 **全域 Microsoft 365 租** 使用者的情況。 本 **指南不適用於** 由世紀運作 Office 365 中的承租人。

針對具有全球 Microsoft 365 承租人和中國公司內建的企業，Microsoft 365 針對中國使用者的用戶端效能是由中國電訊的網際網路架構所獨有的因素所複雜。

中國 Isp 對全球公用網際網路的管制 offshore 連線，而這些裝置會透過可能會高層次的跨框線網路擁塞的周邊裝置。 這項擁塞會針對所有進出中國的網際網路流量，建立封包遺失和延遲。

![Microsoft 365 流量未優化](../media/O365-networking/China-O365-unoptimized.png)

封包遺失和延遲對網路服務的效能有不利的影響，尤其是需要大量資料交換的服務 (例如大型檔案傳輸) 或需要接近即時效能 (音訊和影片應用程式) 。

本主題的目標是提供最佳作法，以減輕對 Microsoft 365 服務上的中國跨框線網路擁塞的影響。 本主題不會解決其他常見的最後一個效能問題，例如由於中國運營商中的複雜路由而導致大量資料包延遲的問題。

## <a name="corporate-network-best-practices"></a>公司網路的最佳作法

許多具有全球 Microsoft 365 承租人和中國使用者的企業，都已在全球範圍內實施含公司網路流量之公司網路流量的私人網路。 這些企業可以利用此網路基礎結構，避免跨框線網路擁塞，並優化其在中國的 Microsoft 365 服務效能。

> [!IMPORTANT]
> 就像所有私人 WAN 實施一樣，您必須為您的國家和/或地區參考法規需求，以確保您的網路設定符合規範。

第一步，請務必遵循我們的基準網路指導方針，以[供 Microsoft 365 的網路規劃和效能調整](./network-planning-and-performance.md)。 主要目標應該是盡可能避免從中國的網際網路存取全域 Microsoft 365 服務。

- 利用您現有的私人網路，在中國辦公網路和 offshore 位置之間傳輸網路流量，在中國以外的公用網際網路上送出 Microsoft 365 網路流量。 在中國以外的任何位置幾乎都會提供明確的利益。 網路系統管理員可以透過使用 [Microsoft 全球網路](/azure/networking/microsoft-global-network)的低延遲互連區域中的 egressing 進行進一步的優化。 香港，日本和韓國為範例。
- 設定使用者裝置以透過 VPN 連線存取公司網路，允許傳輸公司網路的私人 offshore 連結的 Microsoft 365 流量。 確定 VPN 用戶端未設定成使用分割隧道，或使用者裝置設定為忽略 Microsoft 365 流量的分割隧道。 如需優化 Teams 和即時媒體流量之 VPN 連線的詳細資訊，[請參閱本節](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)。
- 設定您的網路，以路由傳送您私人 offshore 連結的所有 Microsoft 365 流量。 如果您必須將私人連結的流量降到最低，您可以選擇只在 [ **優化** ] 類別中路由終結點，並允許要求 **允許** 和 **預設** 端點傳輸網際網路。 這可將優化的流量限制在高延遲和封包遺失的重要服務上，以提升效能，並將頻寬消耗降至最低。
- 如果可能的話，請使用 UDP （而非 TCP）即時媒體資料流程流量，例如用於 Teams。 UDP 可提供比 TCP 更佳的即時媒體資料流程效能。

如需如何選擇性路由 Microsoft 365 流量的詳細資訊，請參閱[管理 Office 365 端點](managing-office-365-endpoints.md)。 如需所有全球 Office 365 URLs 及 ip 位址的清單，請參閱[Office 365 URLs 及 ip 位址範圍](urls-and-ip-address-ranges.md)。

![Microsoft 365 流量優化](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>使用者最佳作法

在中國與商業網路無連線的情況下，從遠端位置（例如，住宅、咖啡店、旅館及分公司）連線至全球 Microsoft 365 租使用者的使用者，由於其裝置和 Microsoft 365 之間的流量，必須傳輸中國網路的擁塞網路電路，因此可能會產生較低的網路效能。

如果在公司網路中的跨框線私人網路絡和/或 VPN 存取不是一個選項，請訓練您的中國使用者來遵循這些最佳作法，以降低個別使用者的效能問題。

- 利用支援快取的豐富 Office 用戶端 (例如 Outlook、Teams、OneDrive 等 ) ，並避免使用網頁型用戶端。 Office 用戶端快取及離線存取功能可大幅減少網路擁塞和延遲的影響。
- 如果您的 Microsoft 365 租使用者已設定 _音訊會議_ 功能，Teams 使用者可以透過公用交換電話網路 (PSTN) 加入會議。 如需詳細資訊，請參閱[Office 365 中的音訊會議](/microsoftteams/audio-conferencing-in-office-365)。
- 如果使用者遇到網路效能問題，他們應該向其 IT 部門報告疑難排解，並在懷疑 Microsoft 365 服務有問題時，升級至 Microsoft 支援人員。 並非所有問題都是由跨框線的網路效能所造成。

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>針對中國的使用者優化 Microsoft Teams 會議網路效能

針對具有全球 Microsoft 365 租使用者的組織和目前狀態為中國的組織，Microsoft 365 以中國網際網路架構為基礎的獨特因素，針對中國使用者用戶端效能可能會複雜。 透過下列指導，許多公司和學校都已經報告好的結果。 不過，此範圍會限制在控制 IT 網路安裝的使用者網路位置，例如，office 位置或具有 VPN 連線的家用/行動電話端點。 Microsoft Teams 通話和會議通常是從外部位置（例如，家用辦事處、行動地點、旅途中和咖啡店）使用。 因為呼叫和會議依賴即時媒體流量，所以這些 Teams 體驗對網路擁塞特別敏感。

因此，Microsoft 已與電信服務提供者合作，使用中國國內和 public internet connections 之間的較高品質、優先的網路路徑，以及 Microsoft 365 global cloud 中的 Teams 和 Skype 服務，以執行 Teams 和商務用 Skype 線上即時媒體流量。 這項功能產生的封包遺失和其他關鍵度量值的增加率超過10個，這會影響使用者的經驗。

>[!IMPORTANT]
>目前，這些改進功能不會使用 Teams 或 Microsoft 資料流程參加 Microsoft Live Events 會議，例如大型廣播或 "城鎮廳" 樣式會議。 若要查看即時事件會議，中國的使用者需要使用私人網路或 SDWAN/VPN 解決方案。 不過，網路增強功能將有益於呈現或產生即時事件會議的使用者，因為該經驗是做為製造者或簡報者的一般 Teams 會議。

### <a name="organization-network-best-practices-for-teams-meetings"></a>Teams 會議的組織網路最佳作法

在下列情況下，您必須考慮如何利用這些網路增強功能（假定先前的指南考慮私人網路絡擴充，以避免跨框線網路擁塞）。 組織辦公室網路有兩個一般選項：

1. 不進行任何新增動作。 繼續遵循有關私人網路旁路的先前指導方針，避免交叉框線擁塞。 Teams 即時媒體流量會利用該安裝程式（如之前）。
2. 會執行分割/混合式模式。
   - 除了 Teams 會議及呼叫即時媒體流量以外，針對所有標記為要優化的流量，使用先前的指導方針。
   - 透過公用網際網路路由傳送 Teams 會議及呼叫即時媒體流量。 如需識別即時媒體網路流量的詳細資訊，請參閱下列資訊。

透過公用網際網路傳送 Teams 即時媒體音訊和影片流量，其使用較高品質的連線，可能會造成相當大的成本節約，因為它是免費的，而是透過私人網路絡傳送該流量。 如果使用者同時使用 SDWAN 或 VPN 用戶端，則可能會有類似的額外優點。 有些組織可能也想要讓更多的資料越過公用網際網路連線（一般作法）。

您可以將相同的選項套用至 SDWAN 或 VPN 設定。 例如，使用者使用 SDWAN 或 VPN 將 Microsoft 365 流量路由傳送到公司網路，然後利用該網路的私人分機，避免跨框線擁塞。 使用者的 SDWAN 或 vpn 現在可以設定為排除 Teams 會議及呼叫來自 VPN 路由的即時流量。 此 VPN 設定稱為分割隧道。 如需詳細資訊，請參閱[VPN 分割隧道的 Office 365](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel) 。

您也可以繼續針對所有 Microsoft 365 流量（包括 Microsoft Teams 即時流量）使用 SDWAN 或 VPN。 Microsoft 不建議使用 SDWAN 或 VPN 解決方案。

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Teams 會議的家用、行動和使用者網路最佳作法

當以室內電話或行動連線方式連線至中國的公用網際網路服務，中國的使用者就能利用這些改進功能。 在公用網際網路上 Teams 即時媒體音訊和影片流量，直接受益于增強的連線性和品質。

不過，來自其他 Microsoft 365 服務的資料，以及其他 Teams 中的流量（如聊天或檔案），將無法直接受益于這些增強功能。 組織網路外部的使用者可能仍然會遭受這種流量的網路效能不良。 如本文所述，您可以使用 VPN 或 SDWAN 緩解這些影響。 您也可以讓使用者透過網頁用戶端使用豐富的桌面用戶端，以支援應用程式內快取，以減輕網路問題。

### <a name="identifying-teams-real-time-media-network-traffic"></a>識別 Teams 即時媒體網路流量

若要設定網路裝置或 VPN/SDWAN 設定，您只需要排除 Teams 即時媒體音訊和影片流量。 您可以在 Office 365 URLs 的官方清單[及 IP 位址範圍](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams)上找到 ID 11 的流量詳細資料。 其他所有網路設定應該會維持原樣。

Microsoft 正致力於提升 Microsoft 365 使用者經驗，以及透過最廣泛的網路架構和特性範圍來提升用戶端的效能。 流覽[Office 365 網路技術 Community](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)以啟動或加入交談、尋找資源，以及提交功能要求和建議

## <a name="related-topics"></a>相關主題

[Microsoft 365 的網路規劃和效能調整](./network-planning-and-performance.md)

[Microsoft 365 網路連線原則](microsoft-365-network-connectivity-principles.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Microsoft 全球網路](/azure/networking/microsoft-global-network)
