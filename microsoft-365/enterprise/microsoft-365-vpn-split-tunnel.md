---
title: 概觀：使用 VPN 分割通道搭配 Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: 使用 VPN 分割通道搭配 Office 365 將遠端使用者的 Office 365 連線能力最佳化的指引。
ms.openlocfilehash: c92599469431732136637cee2bb6a029c4eb4037
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259244"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>使用 VPN 分割通道將遠端使用者的 Office 365 連線能力最佳化
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

針對透過 vpn 將其遠端工作者裝置連線到公司網路或雲端基礎結構的客戶，Microsoft 建議使用 _vpn 分割隧道_ 設定來路由傳送的金鑰 Office 365 案例 **Microsoft Teams**、 **SharePoint 線上** 及 **Exchange Online** 。 這一點特別重要，因為這是第一行的工作，可協助在大規模的工作間生產力（如 COVID-19 危機）期間繼續員工生產力。

![分割通道 VPN 設定](../media/vpn-split-tunneling/vpn-model-2.png)

_圖 1：VPN 分割通道解決方案，具有直接傳送到服務的明確 Office 365 例外狀況。不管目的地為何，所有其他流量都會通過 VPN 通道。_

此方法的本質是提供一種簡單的方法，讓企業能緩和 VPN 基礎結構飽和的風險，並且在最短的時間範圍內盡可能大幅提升 Office 365 效能。 將 VPN 用戶端設定為允許最關鍵、高容量的 Office 365 流量繞過 VPN 通道，可達到下列優點：

- 在影響 Office 365 使用者體驗的企業 VPN 架構中，立即緩解大多數客戶所回報效能和網路容量問題的根本原因
  
  建議的解決方案特別是以 [Office 365 URL 和 IP 位址範圍](./urls-and-ip-address-ranges.md)主題中分類為 [最佳化] 的 Office 365 服務端點為目標。 對這些端點的流量非常敏感，延遲和頻寬節流，使其無法略過 VPN 隧道，可大幅改善使用者體驗，並減少公司網路負載。 不是構成大部分頻寬或使用者體驗使用量的 Office 365 連線，可以隨著其餘要送至網際網路的流量持續透過 VPN 通道路由傳送。 如需詳細資訊，請參閱 [VPN 分割通道策略](#the-vpn-split-tunnel-strategy)。

- 可由客戶快速設定、測試及實施，不需要其他基礎結構或應用程式需求

  視 VPN 平台和網路架構而定，實作可能只需幾個小時就能完成。 如需詳細資訊，請參閱[實作 VPN 分割通道](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)。

- 不變更其他連線的路由傳送方式 (包括送至網際網路的流量)，以維持客戶 VPN 實作的安全狀況。

  建議的設定會依循 VPN 流量例外狀況的 **最低權限** 原則，並可讓客戶實作分割通道 VPN，而不會讓使用者或基礎結構暴露於其他安全性風險。 透過 Office 用戶端應用程式堆疊和範圍限定為可在應用程式和網路層級強化之 Office 365 服務的 IP 位址，可將直接路由傳送至 Office 365 端點的網路流量進行加密，以進行完整性驗證。 如需詳細資訊，請參閱[在今日獨特的遠端工作情境中，安全專業人員與 IT 達到現代安全控制的另一種方法 (Microsoft 安全小組部落格)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (英文)。

- 大部分企業 VPN 平台都提供原生支援

  Microsoft 持續與生產商業 VPN 解決方案的產業夥伴合作，協助合作夥伴依據上述建議，針對其解決方案開發目標式指引和設定範本。 如需詳細資訊，請參閱[常見 VPN 平台的 HOWTO 指南](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms)。

>[!TIP]
>Microsoft 建議讓分割通道 VPN 設定著重於針對 Office 365 服務所記載的專用 IP 範圍。 FQDN 或 AppID 型分割通道設定 (雖然在某些 VPN 用戶端平台上可行) 可能未完全涵蓋主要 Office 365 案例，且可能與 IP VPN 路由規則相衝突。 基於這個理由，Microsoft 不建議使用 Office 365 FQDN 來設定分割通道 VPN。 在其他相關案例 (例如 .pac 檔案自訂或要實作 Proxy 旁路) 中，使用 FQDN 設定可能很有用。

如需完整的實作指引，請參閱[實作 Office 365 的 VPN 分割通道](microsoft-365-vpn-implement-split-tunnel.md)。

如需針對遠端工作人員設定 Microsoft 365 的逐步程式，請參閱[設定您的基礎結構以進行遠端工作](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>VPN 分割通道策略

傳統公司網路通常會設計成針對以下的雲端前世界安全地運作：將最重要的資料、服務、應用程式裝載於內部部署環境，且直接連線至內部公司網路 (大多數使用者也會直接連線)。 因此，網路基礎結構會基於以下元素而建置：分公司透過「多重通訊協定標籤切換 (MPLS)」網路連線到總公司，而遠端使用者必須透過 VPN 連線到公司網路，才能存取內部部署端點和網際網路。 在此模型中，來自遠端使用者的所有流量都周遊公司網路，並透過通用出口點路由傳送到雲端服務。

![強制 VPN 設定](../media/vpn-split-tunneling/vpn-model-1.png)

_圖 2：常見 VPN 解決方案，適用於不管目的地為何，所有流量都被迫回到公司網路的遠端使用者_

因為組織會將資料和應用程式移至雲端，所以此模型已開始變得較低的效益，因為它很快就會變得麻煩、昂貴且 unscalable，因此會大幅影響使用者的網路效能和效能，並限制組織的功能，以適應不斷變化的需求。 許多 Microsoft 客戶報告有幾年前80% 的網路流量是內部目的地，但在 2020 80% 加上流量會連接至外部雲端式資源。

COVID-19 危機已使此問題惡化，大多數組織都需要有立即的解決方案。 許多客戶發現強制 VPN 模型無法擴展，或效能不足以因應此危機必然造成的 100% 遠距工作案例。 為了讓這些組織繼續有效運作，需要快速的解決方案。

針對 Office 365 服務，Microsoft 已針對這項問題 squarely 設計的服務連線需求，在此情況下，具有焦點、嚴格控制且相對靜態服務端點的集合，可以非常簡單且快速地進行優化，如此就能為存取服務的使用者提供高效能，並減少 VPN 基礎結構的負擔，以供仍然需要的流量使用。

Office 365 將 Office 365 所需的端點分為三個類別：**最佳化**、**允許** 和 **預設**。 [最佳化] 端點是我們的討論重點，其具有下列特性：

- 是 Microsoft 所擁有和管理的端點，並且在 Microsoft 基礎結構上託管
- 專用於核心 Office 365 工作負載，例如 Exchange Online、SharePoint Online、商務用 Skype Online 及 Microsoft Teams
- 已提供 IP
- 變動率很低，且應保持少量 (目前為 20 個 IP 子網路)
- 屬於大量和/或延遲敏感型
- 能夠擁有服務中提供 (而非內嵌在網路上) 的必要安全性元素
- 大約佔送至 Office 365 服務的 70-80% 流量

這組嚴格限定的端點可從強制 VPN 通道分割出來，並透過使用者的本機介面，安全地傳送到 Office 365 服務。 這稱為 **分割通道**。

如 DLP、AV 保護、驗證和存取控制等安全性元素，可在服務中的不同層級更有效率地針對這些端點進行傳遞。 當我們同時從 VPN 解決方案轉移大量的流量時，這可讓商務用的網路重要流量，可釋放出 VPN 容量。 在許多情況下，應該也能免除經歷冗長且昂貴升級方案來處理這種新運作方式的需求。

![分割 Tunnel VPN 設定詳細資料](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_圖 3：VPN 分割通道解決方案，具有直接傳送到服務的明確 Office 365 例外狀況。不管目的地為何，所有其他流量都被迫回到公司網路。_

從安全性的觀點來看，Microsoft 有一系列的安全性功能，可用來提供類似內部部署安全性堆疊的內嵌檢查所提供的安全性，或甚至更強的安全性。 Microsoft 安全小組的部落格文章[在今日獨特的遠端工作情境中，安全專業人員與 IT 達到現代安全控制的另一種方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (英文) 清楚地概括說明可用的功能，而您可在這篇文章中找到更多詳細的指引。 如需有關 Microsoft 實作 VPN 分割通道的詳細資訊，另請參閱[在 VPN 上執行：Microsoft 如何使遠端員工保持聯繫](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) (英文)。

在許多情況下，此實作可在幾小時內達成，讓組織得以迅速轉向全規模遠距工作來快速解決其所面臨的最迫切問題。 如需 VPN 分割通道實作指引，請參閱[實作 Office 365 的 VPN 分割通道](microsoft-365-vpn-implement-split-tunnel.md)。

## <a name="related-topics"></a>相關主題

[實作 Office 365 的 VPN 分割通道](microsoft-365-vpn-implement-split-tunnel.md)

[Office 365 針對中國使用者的效能最佳化](microsoft-365-networking-china.md)

[在今日獨特的遠端工作情境中，安全專業人員與 IT 達到現代安全控制的另一種方法 (Microsoft 安全小組部落格)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (英文)

[Microsoft 強化 VPN 效能：使用 Windows 10 VPN 設定檔以允許自動連線功能](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[在 VPN 上執行：Microsoft 如何使遠端員工保持聯繫](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) (英文)

[Office 365 網路連線原則](microsoft-365-network-connectivity-principles.md)

[評估 Office 365 的網路連線能力](assessing-network-connectivity.md)

[Microsoft 365 連線測試](https://aka.ms/netonboard)