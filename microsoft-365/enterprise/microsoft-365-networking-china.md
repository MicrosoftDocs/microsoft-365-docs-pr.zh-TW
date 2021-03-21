---
title: 適用于中國使用者的 Microsoft 365 全域租使用者效能優化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
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
ms.openlocfilehash: 2ba0509425b60aec35d29b23b84e3b6346d2f5cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923191"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>適用于中國使用者的 Microsoft 365 全域租使用者效能優化

>[!IMPORTANT]
>本指南專屬於使用案例，在該案例中， **企業的 microsoft 365 使用者** 會連接到 **全域 Microsoft 365 租** 使用者。 本 **指南不適用於** 由世紀運作之 Office 365 中的承租人。

針對具有全球 Microsoft 365 租使用者的企業和中國的公司形象，中國使用者的 Microsoft 365 用戶端效能對中國電信的網際網路架構而言是很複雜的因素。

中國 Isp 對全球公用網際網路的管制 offshore 連線，可流覽周邊裝置，這種裝置可能會高層次的跨邊界網路擁塞。 這項擁塞會針對所有進出中國的網際網路流量，建立封包遺失和延遲。

![Microsoft 365 流量-未優化](../media/O365-networking/China-O365-unoptimized.png)

封包遺失和延遲對網路服務的效能有不利的影響，尤其是需要大量資料交換的服務 (例如大型檔案傳輸) 或需要接近即時效能 (音訊和影片應用程式) 。

本主題的目標是提供最佳作法，以減輕 Microsoft 365 服務上的中國跨框線網路擁塞的影響。 本主題不會解決其他常見的最後一個效能問題，例如由於中國運營商中的複雜路由而導致大量資料包延遲的問題。

## <a name="corporate-network-best-practices"></a>公司網路的最佳作法

許多具有全球 Microsoft 365 承租人和中國使用者的企業，都已在全球範圍內實施含公司網路流量的私人網路與 offshore 位置之間的流量。 這些企業可以利用此網路基礎結構，避免跨框線網路擁塞，並在中國優化其 Microsoft 365 服務效能。

>[!IMPORTANT]
>就像所有私人 WAN 實施一樣，您必須為您的國家和/或地區參考法規需求，以確保您的網路設定符合規範。

第一步，您必須遵循 [Microsoft 365 的網路規劃和效能調整](./network-planning-and-performance.md)，遵循我們的基準網路指導方針。 主要目標應該是盡可能避免從中國網際網路存取全球 Microsoft 365 服務。

- 利用您現有的私人網路，在中國辦公網路和 offshore 位置之間傳送 Microsoft 365 網路流量，該位置是在中國以外的公用網際網路上出口。 在中國以外的任何位置幾乎都會提供明確的利益。 網路系統管理員可以透過使用 [Microsoft 全球網路](/azure/networking/microsoft-global-network)的低延遲互連區域中的 egressing 進行進一步的優化。 香港，日本和韓國為範例。
- 設定使用者裝置以透過 VPN 連線存取公司網路，以允許 Microsoft 365 流量傳輸公司網路的私人 offshore 連結。 確定 VPN 用戶端未設定成使用分割隧道，或使用者裝置已設定為忽略 Microsoft 365 流量的分割隧道。
- 設定您的網路以路由傳送您私人 offshore 連結的所有 Microsoft 365 流量。 如果您必須將私人連結的流量降到最低，您可以選擇只在 [ **優化** ] 類別中路由終結點，並允許要求 **允許** 和 **預設** 端點傳輸網際網路。 這可將優化的流量限制在高延遲和封包遺失的重要服務上，以提升效能，並將頻寬消耗降至最低。
- 如果可能的話，請使用 UDP （而非 TCP）即時媒體資料流程流量，例如用於小組。 UDP 可提供比 TCP 更佳的即時媒體資料流程效能。

如需如何選擇性路由 Microsoft 365 流量的相關資訊，請參閱 [管理 Office 365 端點](managing-office-365-endpoints.md)。 如需所有全球 Office 365 URLs 及 IP 位址的清單，請參閱 [Office 365 URLs 和 ip 位址範圍](urls-and-ip-address-ranges.md)。

![Microsoft 365 流量優化](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>使用者最佳作法

在中國，使用與商業網路無連線的遠端位置（例如，住宅、咖啡店、旅館及分公司）連線至全球 Microsoft 365 承租人的使用者，可能會因為其裝置和 Microsoft 365 之間的流量，必須傳輸中國網路的擁塞網路電路，因此可能會產生較低的網路效能。

如果在公司網路中的跨框線私人網路絡和/或 VPN 存取不是一個選項，請訓練您的中國使用者來遵循這些最佳作法，以降低個別使用者的效能問題。

- 利用支援快取的豐富 Office 用戶端 (例如，Outlook、小組、OneDrive 等 ) 和避免網路型用戶端。 Office 用戶端快取及離線存取功能可大幅減少網路擁塞和延遲的影響。
- 如果您的 Microsoft 365 租使用者已設定 _音訊會議_ 功能，小組使用者可以透過公用交換電話網路 (PSTN) 加入會議。 如需詳細資訊，請參閱 [Office 365 中的音訊會議](/microsoftteams/audio-conferencing-in-office-365)。
- 如果使用者遇到網路效能問題，他們應該向其 IT 部門報告疑難排解，並在懷疑 Microsoft 365 服務發生問題時升級至 Microsoft 支援服務。 並非所有問題都是由跨框線的網路效能所造成。

Microsoft 正致力於改善 Microsoft 365 使用者經驗，並透過最廣泛的網路架構和特性範圍來改善用戶端的效能。 請造訪 [Office 365 技術社區](https://techcommunity.microsoft.com/t5/office-365/bd-p/Office365General) ，以啟動或加入交談、尋找資源，以及提交功能要求和建議。

## <a name="related-topics"></a>相關主題

[Microsoft 365 的網路規劃和效能調整](./network-planning-and-performance.md)

[Microsoft 365 網路連線原則](microsoft-365-network-connectivity-principles.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Microsoft 全球網路](/azure/networking/microsoft-global-network)