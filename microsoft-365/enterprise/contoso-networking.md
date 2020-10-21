---
title: Contoso Corporation 的網路
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 瞭解 Contoso 網路基礎結構，以及公司如何使用其 SD-WAN 技術，以取得適用于企業雲端服務之 Microsoft 365 的最佳網路效能。
ms.openlocfilehash: ca673e6dcbf0f3db4bde33d388598e5f4ffac914
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637184"
---
# <a name="networking-for-the-contoso-corporation"></a>Contoso Corporation 的網路

為了採用雲端包容的基礎結構，Contoso 設計出網路流量與雲端服務的傳輸基礎。而非內部中樞輻射模型，其主要是針對下一個層級的 office 階層的網路連線和流量，將使用者位置對應至網際網路上最接近 Microsoft 365 網路位置的本機網際網路出口和本機連線。

## <a name="networking-infrastructure"></a>網路基礎結構

以下是連結 Contoso 分公司的網路元素：

- 多重通訊協定標籤切換 (MPLS) WAN 網路

  MPLS WAN 網路會將巴黎總部和地區性辦事處連接至分支和 hub 設定中的衛星辦公室。網路可讓使用者存取內部部署伺服器，這些伺服器是在巴黎總部中組成企業營運應用程式。它也會將所有一般網際網路流量路由傳送至巴黎 office，網路安全裝置會在其中清除要求。在每個辦公室內，路由器會將流量傳遞給有線主機或子網上的無線訪問點，使用私人 IP 位址空間。

- Microsoft 365 流量的本機直接網際網路存取

  每個 office 都有一個軟體定義的 WAN (SD-WAN) 裝置，其具有一個或多個具有一或多個本機網際網路 ISP 網路電路的裝置，其透過 proxy 伺服器進行網際網路連線。這通常是指本機 ISP 的 WAN 連結，也提供公用 IP 位址和本機 DNS 伺服器。

- 網際網路呈現方式

  Contoso 擁有 contoso \. com 公用功能變數名稱。Contoso public 網站定購產品是巴黎校園中網際網路連線資料中心的一組伺服器。Contoso 在網際網路上使用 a/24 公用 IP 位址範圍。

圖1顯示 Contoso 網路基礎結構及其與網際網路的連線。

![Contoso 網路](../media/contoso-networking/contoso-networking-fig1.png)
 
**圖1： Contoso 網路**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>使用 SD-WAN 以取得與 Microsoft 的最佳化網路連線

Contoso 遵循 [Microsoft 365 網路連線原則](microsoft-365-network-connectivity-principles.md) (部分機器翻譯)，以便：

- 識別並區分 Microsoft 365 網路流量
- 在當地輸出網路連線
- 避免網路 hairpin
- 略過重複的網路安全性裝置

Microsoft 365 的網路流量有三種類別： *Optimize*、 *Allow*及 *Default*。 優化及允許流量是在端點上加密及保護的受信任網路流量，且是 Microsoft 365 網路的目標。

Contoso 決定：

- 使用直接網際網路出局以優化和允許類別流量，以及將所有預設類別流量轉寄給巴黎型中央網際網路連線。

- 在每個 office 上部署 SD-WAN 裝置，成為遵循這些原則並為 Microsoft 365 雲端式服務達成最佳網路效能的簡易方法。

  SD-WAN 裝置有一個給當地辦公室網路使用的 LAN 連接埠，和多個 WAN 連接埠。 一個 WAN 埠會連接到其 MPLS 網路。 另一個連接至本機 ISP 電路。 SD-WAN 裝置會透過 ISP 連結路由 [最佳化] 和 [允許] 類別的網路流量。

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Contoso 企業營運應用程式基礎結構

Contoso 為下列專案設計其企業營運應用程式和伺服器內部網路基礎結構：

- 衛星辦公室使用當地快取伺服器以儲存經常存取的文件和內部網站。
- 地區中樞針對地區和衛星辦公室使用地區應用程式伺服器，這些伺服器會與巴黎總部的伺服器同步處理。
- 巴黎校園資料中心包含服務于整個組織的集中式應用程式伺服器。

圖2顯示跨 Contoso 內部網路存取伺服器時所使用之網路流量百分比。

![內部應用程式的 Contoso 基礎結構](../media/contoso-networking/contoso-networking-fig2.png)
 
**圖2：內部應用程式的 Contoso 基礎結構**

針對衛星或地區性 hub 分公司，衛星和地區性 hub office server 可以處理員工所需資源的60%。 其他40% 的資源要求必須透過 WAN 連結移至巴黎校園。

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>適用于企業的 Microsoft 365 的網路分析和準備工作

Contoso 使用者成功採用 Microsoft 365 的企業服務，取決於對網際網路的高可用性和高性能連線，或直接與 Microsoft 雲端服務的連接。 Contoso 採取下列步驟，為企業雲端服務方案及執行 Microsoft 365 的優化連線：

1. 建立公司 WAN 網狀圖以協助規劃

   為了開始其網路規劃，Contoso 建立了一個圖表，顯示其辦公室位置、現有的網路連線能力、現有的網路周邊裝置，以及網路上所管理的服務類別。 在規劃及實施網路連線的後續步驟中，他們使用此圖表。

2. 建立適用于商業網路連線的 Microsoft 365 方案

   Contoso 使用 [Microsoft 365 網路連接性原則](microsoft-365-network-connectivity-principles.md) 和範例參考網路架構，將 SD-WAN 識別為 Microsoft 365 連線的慣用拓撲。

3. 在每個辦公室分析網際網路連線利用率與 MPLS-WAN 頻寬，並視需要增加頻寬

   已分析每個 office 的目前使用狀況，並已增加電路，使預測的 Microsoft 365 雲端式流量可以運作，平均使用20% 的未用容量。

4. 優化 Microsoft 網路服務的效能

   Contoso 已決定 Office 365、Intune 和 Azure 端點的集合，以及網際網路路徑中已設定的防火牆、安全性裝置及其他系統，以取得最佳效能。 Office 365 的端點，可將類別流量設定為透過 ISP 電路進行路由傳送的 SD-WAN 裝置。

5. 設定內部 DNS

   DNS 必須能夠運作，並且可以在本機針對 Microsoft 365 流量進行查閱。

6. 驗證網路端點及埠連線能力

   Contoso 執行 Microsoft network connectivity test 工具，以驗證 Microsoft 365 for enterprise 雲端服務的連線能力。

7. 優化員工電腦的網路連線能力

   已檢查個別電腦，確定已安裝最新的作業系統更新，而且所有用戶端上的端點安全性監視皆為作用中狀態。

## <a name="next-step"></a>下一步

[了解](contoso-identity.md) Contoso 如何針對員工在雲端中利用其內部部署 Active Directory Domain Services (AD DS)，以及如何針對客戶和商務合作夥伴利用同盟驗證。

## <a name="see-also"></a>請參閱

[Microsoft 365 的網路藍圖](networking-roadmap-microsoft-365.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)

[測試實驗室指南](m365-enterprise-test-lab-guides.md)
