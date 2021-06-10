---
title: 實作 ExpressRoute for Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: 瞭解如何針對 Office 365 執行 ExpressRoute，其可提供許多網際網路對向 Office 365 服務的備用路由路徑。
ms.openlocfilehash: d75fe3a6dab4926babeef61fc14894566ff819b0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051363"
---
# <a name="implementing-expressroute-for-office-365"></a>實作 ExpressRoute for Office 365

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

ExpressRoute Office 365 提供許多網際網路對向 Office 365 服務的備用路由路徑。 Office 365 的 ExpressRoute 架構是以 Office 365 服務（已透過 ExpressRoute 網際網路存取）上的廣告公開 IP 首碼為基礎，以在您的網路中接下來再發佈這些 ip 首碼。 透過 ExpressRoute，您可以透過網際網路和 ExpressRoute，有效地啟用多種不同的路由路徑，以進行許多 Office 365 服務。 網路上路由的狀態可能代表如何設計內部網路拓撲的重大變更。
  
 **狀態：** 完成指南 v2
  
您必須仔細規劃 Office 365 執行的 ExpressRoute，以滿足網路複雜性，使其可透過使用插入核心網路和網際網路之路由的專用電路進行路由傳送。 如果您和您的小組沒有在本指南中執行詳細的規劃與測試，當 ExpressRoute 電路啟用時，可能會遇到間歇性或全部的連線中斷 Office 365 服務。
  
若要取得成功的實施，您需要分析基礎結構需求、深入瞭解網路評估與設計，以分段且可控的方式仔細規劃推廣，並建立詳細的驗證和測試計劃。 對於大型的分散式環境而言，每個月的實施範圍都很少見。 本指南旨在協助您預先規劃。
  
大量成功的部署可能需要六個月的計畫，而且常常包括來自組織中許多區域的小組成員，包括網路、防火牆和 Proxy 伺服器管理員、Office 365 系統管理員、安全性、使用者支援、專案管理，以及執行的資助。 您在規劃程式中的投資，可減少因停機或複雜且昂貴的疑難排解而導致部署失敗的可能性。
  
在此實施指南開始之前，我們預期會完成下列先決條件。
  
1. 您已完成網路評估，以判斷是否建議和核准 ExpressRoute。

2. 您已選取 ExpressRoute 網路服務提供者。 尋找 [ExpressRoute 合作夥伴和對等位置](/azure/expressroute/expressroute-locations)的詳細資料。

3. 您已閱讀並瞭解 [ExpressRoute 檔](https://azure.microsoft.com/documentation/services/expressroute/) ，且您的內部網路可滿足 ExpressRoute 先決條件端對端。

4. 您的小組已閱讀頻道9上的所有公開指導方針與檔， [https://aka.ms/expressrouteoffice365](./azure-expressroute.md) [https://aka.ms/ert](https://aka.ms/ert) 並[針對 Office 365 訓練](https://channel9.msdn.com/series/aer)系列查看其 Azure ExpressRoute，以瞭解重要的技術詳細資料，包括：

      - SaaS 服務的網際網路相依性。

      - 如何避免對稱路由並處理複雜路由。

      - 如何結合周邊安全性、可用性和應用層級控制項。

## <a name="begin-by-gathering-requirements"></a>請先收集需求
<a name="requirements"> </a>

首先，決定您規劃要在組織中採用的功能和服務。 您必須決定將使用不同的 Office 365 服務功能，以及網路上的哪些位置將使用這些功能主控人員。 在案例目錄中，您需要新增每個案例所需的網路屬性。例如輸入和輸出網路流量流量，以及 Office 365 端點是否可用於 ExpressRoute。
  
若要收集組織的需求：
  
- 編目組織所使用之 Office 365 服務的輸入和輸出網路流量。 請參閱 Office 365 URLs 及 IP 位址範圍] 頁面，以瞭解不同 Office 365 案例所需之流程的描述。

- 收集現有網路拓撲的檔，顯示內部 WAN 主幹和拓撲的詳細資料、衛星網站的連線、最後的使用者連線能力、路由傳送至網路周邊出局點，以及 proxy 服務。

  - 識別在 Office 365 及其他 Microsoft 服務所連線之網狀圖上的輸入服務端點，同時顯示網際網路和擬議中的 ExpressRoute 連線路徑。

  - 識別各位置之間的所有地理位置使用者位置和 WAN 連線，以及哪些位置目前擁有網際網路的出入，以及哪些位置已建議將出口到 ExpressRoute 對等位置。

  - 識別所有 edge 裝置，例如 proxy、防火牆等等，以及將其關聯編目為透過網際網路和 ExpressRoute 的流量。

  - 記錄使用者是否會透過直接路由或間接應用程式 proxy，針對網際網路和 ExpressRoute 流量，存取 Office 365 服務。

- 將您的租使用者位置和符合-me 位置新增至您的網狀圖。

- 從主要使用者位置，估計預期和觀測的網路效能和延遲特性，以 Office 365。 請記住，Office 365 是一組全域及分散式服務，而且使用者將會連線至可能與租使用者位置不同的位置。 因此，建議您衡量及優化使用者與最接近的 Microsoft 全球網路 edge 與 ExpressRoute 和網際網路連線之間的延遲。 您可以從網路評估中使用您的結果，以協助您進行這種工作。

- 列出公司網路安全性和高可用性需求，必須符合新的 ExpressRoute 連線。 例如，當網際網路出口或 ExpressRoute 電路失敗時，使用者如何繼續存取 Office 365。

- 記錄哪個輸入和輸出 Office 365 網路流量將使用網際網路路徑，而這會使用 ExpressRoute。 您的使用者地理位置和內部部署網路拓朴詳細資料的詳細資訊可能要求計畫與另一個使用者位置不同。

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>編目輸出和輸入的網路流量
<a name="trafficCatalog"> </a>

若要將路由和其他網路複雜性降到最低，我們建議您只針對 Office 365 針對因法規需求或網路評估的結果而必須透過專用連線的網路流量流量，使用 ExpressRoute。 此外，我們建議您分段 ExpressRoute 路由的範圍，並將輸出和輸入網路流量資料流程當做實施專案的不同和不同階段。 僅針對使用者啟動的輸出網路流量流程部署 Office 365 的 ExpressRoute，並讓透過網際網路的輸入網路流量流動，可協助控制拓撲複雜性的增加，以及引入其他非對稱路由可能性的風險。
  
您的網路流量目錄應包含您的內部部署網路與 Microsoft 之間的所有輸入和輸出網路連線清單。
  
- 輸出網路流量流程是指從您的內部部署環境（例如從內部用戶端或伺服器）啟動連接的任何案例，其目的地為 Microsoft 服務。 這些連線可以是直接 Office 365 或間接的，例如，當連線經由 proxy 伺服器、防火牆或其他網路裝置的路徑上 Office 365。

- 輸入網路流量流程是從 Microsoft 雲端啟動至內部部署主機的任何案例。 這些連線通常需要透過防火牆和其他安全性基礎結構，客戶安全性原則需要對外發起流程。

請閱讀 [確保路由 [與 ExpressRoute Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)的郵件路由的 **路由對稱** 區段]，以判斷哪些服務會傳送輸入流量，並在 [Office 365 端點](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)參考文章中尋找 ExpressRoute 標示為 **Office 365** 的欄，以判斷其他的連接資訊。
  
針對每個需要輸出連線的服務，您會想要描述服務的已規劃連線，包括網路路由、proxy 設定、封包檢查和頻寬需求。
  
針對每個需要輸入連線的服務，您需要一些額外的資訊。 Microsoft 雲端中的伺服器將會建立與您的內部部署網路的連線。 為了確保能夠正確地進行連線，您會想要說明此連線的所有方面，包括;可接受這些輸入連線的服務的公用 DNS 專案、CIDR 格式的 IPv4 IP 位址、所涉及的 ISP 裝置，以及如何處理這些連線的輸入 NAT 或來源 NAT。
  
不論是透過網際網路或 ExpressRoute 進行連線以確保未引進非對稱路由，都應複查輸入連線。 在某些情況下，Office 365 服務的內部部署端點可能也需要由其他 Microsoft 和非 Microsoft 服務來存取輸入連線。 使 ExpressRoute 路由傳送至這些服務 Office 365 目的，不會中斷其他案例是非常重要的。 在許多情況下，客戶可能需要對內部網路執行特定變更（例如來源為 NAT），以確保在 ExpressRoute 啟用之後，來自 Microsoft 的輸入資料流程仍保持對稱。
  
以下是所需詳細資料層級的範例。 在此情況下 Exchange 混合會透過 ExpressRoute 路由傳送至內部部署系統。

|**Connection 屬性**|**值**|
|:-----|:-----|
|**網路流量方向** <br/> |入境  <br/> |
|**服務** <br/> |Exchange 混合式  <br/> |
|**Public Office 365 端點 (來源)** <br/> |Exchange Online (IP 位址)   <br/> |
|**Public On-Premises 端點 (目的地)** <br/> |5.5.5.5  <br/> |
|**公用 (網際網路) DNS 專案** <br/> |Autodiscover.contoso.com  <br/> |
|**其他 (非 Office 365) 中是否使用此內部部署端點 Microsoft 服務** <br/> |否  <br/> |
|**Internet 上的使用者或系統是否會使用此內部部署端點** <br/> |是  <br/> |
|**透過公用端點發佈的內部系統** <br/> |Exchange Server client access role (內部部署) 192.168.101、192.168.102、192.168.103  <br/> |
|**公用端點的 IP 廣告** <br/> |**至網際網路**： 5.5.0.0/16  <br/> **若要 ExpressRoute**： 5.5.5.0/24  <br/> |
|**安全性/周邊控制** <br/> |**網際網路路徑**： DeviceID_002  <br/> **ExpressRoute 路徑**： DeviceID_003  <br/> |
|**高可用性** <br/> |跨2地理冗余的主動/主動  <br/> ExpressRoute 電路-芝加哥和達拉斯  <br/> |
|**路徑對稱控制** <br/> |**方法**：來源 NAT  <br/> **網際網路路徑**：來源 NAT 輸入連線至192.168.5。5  <br/> |**ExpressRoute 路徑**：從 (芝加哥) 和 192.168.2.0 (達拉斯) 的來源 NAT 連接  <br/> |

以下是僅限輸出之服務的範例：

|**Connection 屬性**|**值**|
|:-----|:-----|
|**網路流量方向** <br/> |出境  <br/> |
|**服務** <br/> |SharePoint Online  <br/> |
|**內部部署端點 (來源)** <br/> |使用者工作站  <br/> |
|**Public Office 365 端點 (目的地)** <br/> |SharePoint線上 (IP 位址)   <br/> |
|**公用 (網際網路) DNS 專案** <br/> |\*sharepoint.com (及其他 Fqdn)   <br/> |
|**CDN轉 介** <br/> |CDN 提供者所維護的 cdn.sharepointonline.com (及其他 fqdn) )   <br/> |
|**IP 播發和 NAT 正在使用中** <br/> |**網際網路路徑/來源 NAT**： 1.1.1.0/24  <br/> **ExpressRoute 路徑/來源 NAT**： 1.1.2.0/24 (芝加哥) 和 1.1.3.0/24 (達拉斯)   <br/> |
|**Connectivity 方法** <br/> |**Internet**： via layer 7 proxy ( 的 pac 檔案)   <br/> **ExpressRoute**：直接路由 (沒有 proxy)   <br/> |
|**安全性/周邊控制** <br/> |**網際網路路徑**： DeviceID_002  <br/> **ExpressRoute 路徑**： DeviceID_003  <br/> |
|**高可用性** <br/> |**網際網路路徑**：重複的網際網路出局  <br/> **ExpressRoute 路徑**：跨2地理位置冗余 ExpressRoute 電路-芝加哥和達拉斯的主動/主動 ' 熱刷」路由  <br/> |
|**路徑對稱控制** <br/> |**方法**：所有連接的來源 NAT  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>您的網路拓撲設計與區域連通性
<a name="topology"> </a>

在您瞭解服務及其相關的網路流量流程之後，您可以建立一個網狀圖，以包含這些新的連線需求，並示範 Office 365 使用 ExpressRoute 所做的變更。 您的圖表應包含：
  
1. 所有可存取 Office 365 和其他服務的使用者位置。

2. 所有網際網路和 ExpressRoute 出局點數。

3. 所有用來管理網路連線的輸出和輸入裝置（包括路由器、防火牆、應用程式 proxy 伺服器及入侵偵測/防護）。

4. 所有輸入流量的內部目的地，例如接受來自 ADFS web 應用程式 proxy 伺服器之連線的內部 ADFS 伺服器。

5. 將要宣告之所有 IP 子網的目錄

6. 識別每個人員存取 Office 365 的位置，並列出將用於 ExpressRoute 的「搜尋」位置。

7. 內部網路拓撲的位置和部分，在此拓撲中，會接受、篩選和傳播從 ExpressRoute 獲知的 Microsoft IP 首碼。

8. 網路拓撲應該會說明每個網路部分的地理位置，以及它如何透過 ExpressRoute 和/或網際網路連線至 Microsoft 網路。

下圖顯示每個使用者在其中使用 Office 365 的位置，以及輸入和輸出路由播發，以供 Office 365。
  
![ExpressRoute 地區地理位置](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
對於輸出流量，使用者會以下列三種方式之一存取 Office 365：
  
1. 透過北美地區的 [會見-me] 位置來為加州人員提供人員。

2. 透過香港中的「會見-我」地區的位置，為香港使用者。

3. 透過來自孟加拉的人員，而不會有較少的人員，也沒有布建 ExpressRoute 電路。

![區域圖表的輸出連線](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
同樣地，來自 Office 365 的輸入網路流量會以下列其中一種方式傳回：
  
1. 透過北美地區的 [會見-me] 位置來為加州人員提供人員。

2. 透過香港中的「會見-我」地區的位置，為香港使用者。

3. 透過來自孟加拉的人員，而不會有較少的人員，也沒有布建 ExpressRoute 電路。

![區域圖表的輸入連接](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>決定適當的 [符合我的位置] 位置

[！提示] 選擇 [符合我的位置]，這是 ExpressRoute 電路連接至 Microsoft 網路的實體位置，會受到人員存取 Office 365 的位置影響。 SaaS 提供，Office 365 不會以 Azure 所用的相同方式，在 IaaS 或 PaaS 區域模型下運作。 相反地，Office 365 是一組分散式服務，其中的使用者可能需要跨多個資料中心及地區連接端點，而且不一定會位於使用者租使用者所在的相同位置或地區。
  
這表示當您為 Office 365 ExpressRoute 選擇 [符合我的位置] 時，所需的最重要考慮是組織中的人員將從該位置進行連接。 最佳 Office 365 連線的一般建議是執行路由傳送，因此，對 Office 365 服務要求的使用者要求會透過最短的網路路徑傳送至 Microsoft 網路，也通常稱為「熱刷」路由。 例如，如果大部分的 Office 365 使用者位於一或兩個位置，請選取最接近于這些使用者位置之最接近的 [我的位置]，即可建立最佳設計。 如果您的公司在許多不同的地區都有大量使用者人口，您可能想要考慮有多個 ExpressRoute 電路，並符合我的場所。 針對您的某些使用者位置，Microsoft 網路和 Office 365 中最短/最適合的路徑，可能不會透過您的內部 WAN，也不需要 ExpressRoute 符合我的內部點，但透過網際網路。
  
這通常會有多個可在與您的使用者相對應的區域內選取的 [符合 me] 位置。 填寫下表以引導您的決策。

|**在加州和紐約的計畫 ExpressRoute 符合我的場所**||
|:-----|:-----|
|位置  <br/> |人員人數  <br/> |透過網際網路出局對 Microsoft 網路的預期延遲  <br/> |對 ExpressRoute 的 Microsoft 網路的預期延遲  <br/> |
|Los Angeles  <br/> |10,000  <br/> |~ 15ms  <br/> |~ 10ms (經由矽谷)   <br/> |
|華盛頓  <br/> |15,000  <br/> |~ 20 毫秒  <br/> |~ 10ms 透過紐約 ()   <br/> |
|達拉斯  <br/> |5,000  <br/> |~ 15ms  <br/> |~ 40ms 透過紐約 ()   <br/> |

在顯示 Office 365 區域的全域網路架構之後，ExpressRoute 網路服務提供者的 [符合我的位置]，並已建立人員依位置的數量，即可用來識別是否可以進行任何優化。 它也可能會顯示全域髮夾網路連線，其中的流量會路由傳送到遠處的位置，以便取得「我的位置」的位置。 如果已探索全域網路上的髮夾，則應該先修正此，然後再繼續進行。 請找到另一個 [符合我的位置] 位置，或使用選擇性的網際網路專題討論顯示點，以避免髮夾。
  
第一個圖表顯示一份客戶的範例，其中包含北美地區的兩個實體位置。 您可以查看 office 位置的相關資訊、Office 365 租使用者位置，以及許多 ExpressRoute 「我的位置」的選項。 在此範例中，客戶根據兩項原則選取 [符合我的位置]，順序如下：
  
1. 最接近組織中的人員。

2. 最接近于主控 Office 365 的 Microsoft 資料中心。

![ExpressRoute US 地理位置會見-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
進一步擴充此概念，第二個圖表會顯示一個包含類似資訊和決策過程的多國客戶的範例。 此客戶在孟加拉的小型辦公室中，只有十個人的小小組，專注于在地區內成長其足跡。 Chennai 中有一個 [符合我的位置] 和 [Microsoft datacenter]，其上的 Office 365 主控于 Chennai 中，因此符合 me 的位置很有意義;不過，如果是10位人員，額外電路的費用會非常繁重。 當您查看網路時，您需要判斷在網路中傳送網路流量所涉及的延遲，是否比花資本以取得另一部 ExpressRoute 電路更有效。
  
或者，在透過網際網路傳送至 Microsoft 網路的網路流量透過網際網路傳送至其內部網路的網路流量，在下列情況下所述，其他孟加拉的使用者可能會體驗更好的效能。
  
![區域圖表的輸出連線](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>針對 Office 365 實施方案建立您的 ExpressRoute
<a name="implementation"> </a>

您的實施計畫應該同時包含設定 ExpressRoute 的技術詳細資料，以及在網路上設定其他所有基礎結構的詳細資料，如下所示。
  
- 規劃在 ExpressRoute 和網際網路之間分割的服務。

- 規劃頻寬、安全性、高可用性和容錯移轉。

- 設計輸入和輸出路由，包含不同位置的適當路由路徑優化

- 決定要將哪些 ExpressRoute 路由宣告到您的網路中，以及用戶端選擇網際網路或 ExpressRoute 路徑的機制為何;例如，direct routing 或 application proxy。

- 規劃 DNS 記錄變更，包括 [寄件者原則架構](../security/defender-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md) 專案。

- 規劃 NAT 策略（包括輸出和輸入來源 NAT）。

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>規劃使用網際網路和 ExpressRoute 網路路徑的路由
<a name="paths"> </a>

- 針對您的初始部署，建議使用網際網路的所有輸入服務（例如輸入電子郵件或混合式連線）。

- 規劃使用者用戶端 LAN 路由，例如設定 [PAC/WPAD](./managing-office-365-endpoints.md)檔案、預設路由、proxy 伺服器和 BGP 路由播發。

- 規劃周邊路由，包括 proxy 伺服器、防火牆和雲端 proxy。

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>規劃頻寬、安全性、高可用性和容錯移轉
<a name="availability"> </a>

針對每個主要 Office 365 工作量建立所需頻寬的計畫。 個別估計 Exchange Online、SharePoint 線上及商務用 Skype 線上頻寬需求。 您可以使用我們為 Exchange Online 和商務用 Skype 所提供的評估計算機做為開始位置;不過，使用使用者設定檔和位置的具有代表性範例的試驗測試，必須充分瞭解貴組織的頻寬需求。
  
新增如何處理每個網際網路的安全性和 ExpressRoute 外接位置，以記住 Office 365 使用公開對等的所有 ExpressRoute 連線，但仍然必須根據公司的安全性原則（連接至外部網路）加以保護。
  
針對您的計畫新增詳細資料，以瞭解哪些人員將會受到哪種類型的中斷影響，以及哪些人員能夠以最簡單的方式執行其工作。
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>規劃頻寬需求，包括抖動、延遲、擁塞和餘地等商務用 Skype 需求
  
商務用 Skype線上也有特定額外的網路需求，在[商務用 Skype 線上的媒體質量和網路連線效能](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)中有所詳述。
  
閱讀 [使用 Office 365 ExpressRoute 的網路規劃](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的 **Azure ExpressRoute Azure 規劃的區段頻寬規劃**。
  
當您的試驗使用者執行頻寬評估時，您可以使用我們的指南。[使用基準和效能歷史記錄 Office 365 效能調整](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)。
  
#### <a name="plan-for-high-availability-requirements"></a>規劃高可用性需求
  
建立高可用性的計畫，以符合您的需求，並將此方案併入更新的網路拓撲圖表。 使用 [Office 365 ExpressRoute 的網路規劃](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的 **Azure ExpressRoute 讀取「高可用性和容錯移轉**」一節。
  
#### <a name="plan-for-network-security-requirements"></a>規劃網路安全性需求
  
建立符合網路安全性需求的計畫，並將此方案併入更新的網路拓撲圖表。 閱讀將 **安全性控制套用至 Azure ExpressRoute 的** 章節，以針對 [Office 365 的 ExpressRoute 使用網路規劃](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的 Office 365 案例。
  
### <a name="design-outbound-service-connectivity"></a>設計輸出服務連線
<a name="outbound"> </a>

ExpressRoute Office 365 具有可能不熟悉的 *輸出* 網路需求。 具體而言，表示您的使用者和網路要 Office 365 的 IP 位址，並做為到 Microsoft 的輸出網路連線的來源端點，必須遵循下列所述的特定需求。
  
1. 端點必須是公用 IP 位址，已註冊至您的公司或電信公司，可提供給您的 ExpressRoute 連線能力。

2. 端點必須透過 ExpressRoute 播發及驗證/認可。

3. 端點不能透過相同或更喜歡的路由躍點數宣告至網際網路。

4. 端點不能用於與 ExpressRoute 上未設定的 Microsoft 服務的連接。

如果您的網路設計不符合這些需求，則由於路由黑色 holing 或非對稱路由，您的使用者將無法 Office 365 和其他 Microsoft 服務上遇到連線失敗的危險。 當您透過 ExpressRoute 傳送 Microsoft 服務的要求時，會發生此情況，但回應會透過網際網路路由傳送回來，反之亦然，回應會被狀態網路裝置（例如防火牆）中斷。
  
您可以用來符合上述需求的最常見方法，就是使用來源 NAT，以作為網路的一部分，或由您的 ExpressRoute 載體所提供。 來源 NAT 可讓您從 ExpressRoute 摘要網際網路網路的詳細資料和私人 IP 位址，以及結合適當的 IP 路由通告，提供一種簡易的機制，以確保路徑對稱。 如果您使用 ExpressRoute 對等位置特有的狀態網路裝置，則必須針對每個 ExpressRoute 對等位置執行個別的 NAT 集區，以確保路徑對稱。
  
如需詳細資訊，請參閱 [EXPRESSROUTE NAT 需求](/azure/expressroute/expressroute-nat)。
  
將輸出連線的變更新增至網路拓撲圖表。
  
### <a name="design-inbound-service-connectivity"></a>設計輸入服務連線
<a name="inbound"> </a>

在大部分的企業 Office 365 部署中，會假設某些形式的輸入連線從 Office 365 至內部部署服務，例如 Exchange、SharePoint 及商務用 Skype 混合案例、信箱遷移，以及使用 ADFS 基礎結構進行驗證。 當您在內部部署網路與 Microsoft 之間啟用額外的路由路徑，以進行輸出連線 ExpressRoute 時，即使您想要讓這些流程繼續使用網際網路，這些輸入連線可能會不慎受到非對稱路由的影響。 建議使用下列幾種防範措施，以確保從 Office 365 至內部部署系統的網際網路的輸入流量不會受到任何影響。
  
若要降低輸入網路流量流程的非對稱路由風險，所有的輸入連線都應該先使用來源 NAT，然後才會將其路由傳送至您的網路網段，使其可在 ExpressRoute 中進行路由查看。 如果允許傳入連線到具有路由 ExpressRoute 查看的網段，但沒有來源 NAT，則來自 Office 365 的要求會從網際網路進入，但是回到 Office 365 的回應將優先于 ExpressRoute 的網路路徑回到 Microsoft 網路，造成不對稱的路由。
  
您可以考慮下列其中一個執行模式，以滿足這項需求：
  
1. 在要求使用網路設備（例如防火牆或從網際網路到您的內部部署系統的負載平衡器）上的網路設備（例如防火牆或負載平衡器）路由進入內部網路之前，請先執行來源 NAT。

2. 確定 ExpressRoute 路由不會傳播到輸入服務（例如前端伺服器或反向 proxy 系統）的網段，處理網際網路連線。

針對您的網路中的這些案例明確會計，並保留透過網際網路的所有輸入網路流量，有助於將非對稱路由的部署和操作風險降至最低。
  
在某些情況下，您可能會選擇透過 ExpressRoute 連線來引導某些輸入流量。 在這些案例中，請採取下列其他考慮。
  
1. Office 365 只能針對使用公用 ip 的內部部署端點。 這表示即使內部部署輸入端點只對 ExpressRoute 的 Office 365 公開，仍然必須具有與其相關聯的公用 IP。

2. Office 365 服務會執行的所有 DNS 名稱解析，以解析內部部署端點使用公用 DNS。 這表示您必須將輸入服務端點的 FQDN 註冊至網際網路上的 IP 對應。

3. 為了透過 ExpressRoute 接收輸入的網路連線，必須透過 ExpressRoute 將這些端點的公用 IP 子網宣告給 Microsoft。

4. 請仔細評估這些輸入網路流量流量，以確保依照公司的安全性和網路原則套用適當的安全性和網路控制項。

5. 當您的內部部署輸入端點透過 ExpressRoute 通告給 Microsoft 時，ExpressRoute 會有效成為所有 Microsoft 服務（包括 Office 365）之端點的首選路由路徑。 這表示這些端點子網必須只用于與 Office 365 服務通訊，而不會在 Microsoft 網路上其他服務。 否則，您的設計將會造成與其他 Microsoft 服務的輸入連線更喜歡路由傳送輸入 ExpressRoute 的非對稱路由，而傳回路徑會使用網際網路。

6. 當 ExpressRoute 的電路或符合我的位置已停機時，您必須確定內部部署輸入端點仍可透過個別網路路徑接受要求。 這可能表示透過多個 ExpressRoute 電路公佈這些端點的子網。

7. 建議您透過 ExpressRoute 為進入網路的所有輸入網路流量資料流程套用來源 NAT，尤其是當這些資料流程跨狀態網路裝置（例如防火牆）。

8. 有些內部部署服務（例如 ADFS proxy 或 Exchange 自動探索）可能會從網際網路接收來自 Office 365 服務和使用者的輸入要求。 針對這些要求 Office 365 會將相同的 FQDN 與透過網際網路的使用者要求進行目標。 允許從網際網路至內部部署端點的輸入使用者連線，同時強制 Office 365 連線使用 ExpressRoute，都代表大量的路由複雜性。 對於絕大多數使用 ExpressRoute 執行這類複雜案例的客戶，由於運作考慮，所以不建議使用。 這項額外的額外負荷包括管理非對稱路由的風險，而且會要求您認真管理跨多個維度的路由通告和原則。

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>更新您的網路拓撲計畫，以顯示避免對稱路由的方式
<a name="asymmetric"> </a>

您想要避免使用不對稱的路由，以確保您組織中的人員能夠順利使用 Office 365 以及網際網路上的其他重要服務。 客戶有兩個常見設定可導致非對稱路由。 現在，請查看您計畫要使用的網路設定，並檢查是否有其中一個不對稱的路由案例可以存在。
  
為了開始，我們會檢查與下列網狀圖表相關的幾個不同情況。 在此圖中，所有接收輸入要求的伺服器（例如，ADFS 或內部部署混合伺服器）皆位於新的 Jersey 資料中心，且會通告至網際網路。
  
1. 當周邊網路安全時，傳入要求沒有來源 NAT 可用。

2. 新 Jersey 資料中心的伺服器能夠同時查看網際網路和 ExpressRoute 路由。

![ExpressRoute 連線能力概述](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
我們也會針對如何修正這些問題提出建議。
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>問題1： Cloud to Internet over Internet 上的內部部署連接
  
下圖說明當您的網路設定沒有透過網際網路提供來自 Microsoft 雲端之輸入要求的 NAT 時，所採用的非對稱網路路徑。
  
1. 來自 Office 365 的輸入要求會從公用 DNS 中檢索內部部署端點的 IP 位址，並將要求傳送至您的周邊網路。

2. 在此錯誤的設定中，未在傳送流量的周邊網路上設定或提供來源 NAT，進而產生實際來源 IP 位址，以當作傳回目的地使用。

  - 網路上的伺服器會透過任何可用的 ExpressRoute 網路連線，將退回流量路由傳送至 Office 365。

  - 結果是該流向 Office 365 的非對稱路徑，導致連線中斷。

![ExpressRoute Asymetric 路由問題1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>解決方案1a：來源 NAT
  
只要將來源 NAT 新增至輸入的要求，即可解析這種已設定錯誤的網路。 在此圖表中：
  
1. 傳入要求會繼續透過新的 Jersey 資料中心周邊網路進入。 此時間源 NAT 可供使用。

2. 伺服器的回應會傳回與來源 NAT 相關聯的 IP 位址，而不是原始 IP 位址，進而導致回應沿著相同的網路路徑傳回。

![ExpressRoute Asymetric 路由解決方案1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>解決方案1b：路由範圍
  
或者，您也可以選擇不允許公佈 ExpressRoute BGP 首碼，移除這些電腦的備用網路路徑。 在此圖表中：
  
1. 傳入要求會繼續透過新的 Jersey 資料中心周邊網路進入。 這段時間，新的 Jersey 資料中心無法使用透過 ExpressRoute 電路宣告給 Microsoft 的首碼。

2. 伺服器發回的 IP 位址會傳回與原始 IP 位址相關聯的 IP 位址，而這會導致回應是沿著相同的網路路徑傳回。

![ExpressRoute Asymetric 路由解決方案2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>問題2： Cloud over ExpressRoute 上的內部部署連接
  
下圖說明當您的網路設定不會提供來自 Microsoft cloud over ExpressRoute 之輸入要求的 NAT 時，所採用的非對稱網路路徑。
  
1. 來自 Office 365 的輸入要求會從 DNS 中檢索 IP 位址，並將要求傳送至您的周邊網路。

2. 在此錯誤的設定中，未在傳送流量的周邊網路上設定或提供來源 NAT，進而產生實際來源 IP 位址，以當作傳回目的地使用。

  - 網路上的電腦會透過任何可用的 ExpressRoute 網路連線，將退回流量路由傳送至 Office 365。

  - 結果是 Office 365 的非對稱連接。

![ExpressRoute Asymetric 路由問題2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>解決方案2：來源 NAT
  
只要將來源 NAT 新增至輸入的要求，即可解析這種已設定錯誤的網路。 在此圖表中：
  
1. 傳入的要求會繼續透過紐約資料中心的周邊網路進入。 此時間源 NAT 可供使用。

2. 伺服器的回應會傳回與來源 NAT 相關聯的 IP 位址，而不是原始 IP 位址，進而導致回應沿著相同的網路路徑傳回。

![ExpressRoute Asymetric 路由解決方案3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>紙張驗證網路設計是否有對稱路徑

此時，您必須驗證您的執行計畫是否為您將使用 Office 365 的不同案例提供路由對稱性。 當人員使用服務的不同功能時，您會識別預計會採取的特定網路路由。 從內部部署網路和 WAN 路由傳送至周邊裝置，到連接路徑;ExpressRoute 或網際網路，以及連線到線上端點的連線。
  
您必須針對先前識別為組織所採用之服務的所有 Office 365 網路服務執行這項作業。
  
這可協助您逐步完成與第二個人的路由。 向使用者說明，每個網路躍點預期會從何處取得下一個路由，並確保您熟悉路由路徑。 請記住，ExpressRoute 一定會提供更具範圍的路由給 Microsoft server IP 位址，使其具有低於網際網路預設路由的路由成本。
  
### <a name="design-client-connectivity-configuration"></a>設計 Client Connectivity Configuration
<a name="asymmetric"> </a>

![使用具有 ExpressRoute 的 PAC 檔案](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
如果您是使用 proxy 伺服器來進行網際網路系結流量，則必須調整任何 PAC 或用戶端設定檔，以確保網路上的用戶端電腦已正確設定為傳送您想要 Office 365 的 ExpressRoute 流量，而不 transiting proxy 伺服器，而其餘的流量（包括部分 Office 365 流量）會傳送至相關的 proxy。 如需[管理 Office 365 端點](./managing-office-365-endpoints.md)（例如 PAC 檔案）的指南，請參閱本指南。
  
> [!NOTE]
> 端點經常變更，只要每週。 您應根據貴組織已採用的服務和功能，只進行變更，以減少所需的變更數目，以減少保持最新的變更數目。 請密切注意 RSS 摘要中的 [ **有效日期** ]：在此 rss 摘要中已宣告變更，且記錄保留所有過去的變更為止，已宣告的 IP 位址可能不會宣告或從通告中移除，直到達到有效日期為止。
  
## <a name="build-your-deployment-and-testing-procedures"></a>建立部署及測試程式
<a name="testing"> </a>

您的實施計畫應同時包含測試和回滾規劃。 如果您的實施未如期運作，方案應設計為在探索問題之前，影響最少人數。 以下是您的方案應考慮的一些高層次原則。
  
1. 階段網路段和使用者服務上架，以將中斷降至最低。

2. 規劃使用 traceroute 與 TCP 連線的測試路由，並從不同的網際網路連線主機進行連接。

3. 在具有測試 Office 365 租使用者的隔離測試網路上，您最好會進行輸入和輸出服務的測試。

      - 或者，如果客戶尚未使用 Office 365 或在試驗中，也可以在生產網路上執行測試。

      - 或者，您也可以在實際執行中斷期間進行測試，而不是僅供測試及監視之用。

      - 或者，您可以在每個第三層路由器節點上檢查每個服務的路由，以進行測試。 只有在缺乏實體測試帶來風險的情況時，才可使用此回退功能。

### <a name="build-your-deployment-procedures"></a>建立部署程式

您的部署程式應該向幾個階段中的小小組人員進行測試，然後再部署至較大的人員群組。 以下是幾種方法來分段 ExpressRoute 的部署。
  
1. 使用 Microsoft 對等設定 ExpressRoute，並將路由播發轉送到單一主機，只用于分段測試目的。

2. 將路由傳送至 ExpressRoute 網路的單一網段，一開始，並依網路段或地區展開路由廣告。

3. 如果是第一次部署 Office 365，請使用 ExpressRoute 網路部署做為少數人員的示範。

4. 如果使用 proxy 伺服器，您也可以設定測試 PAC 檔案，以引導少量的人員在進行測試與意見 ExpressRoute 之前新增其他。

您的實施計畫應該列出必須採取的每個部署程式，或需要用來部署網路設定的命令。 當網路停機時間到達所做的所有變更時，應從已預先撰寫的書面部署計畫和對等方檢查。 請參閱我們 ExpressRoute 之技術設定的指導方針。
  
- 如果您已變更任何內部部署伺服器的 IP 位址以繼續傳送電子郵件，請更新您的 SPF TXT 記錄。

- 如果您已變更 IP 位址以容納新的 NAT 設定，則為內部部署伺服器更新任何 DNS 專案。

- 確定您已訂閱 RSS 摘要，以取得 Office 365 端點通知，以維護任何路由或 proxy 設定。

完成 ExpressRoute 部署後，應執行測試計劃中的程式。 應該記錄每個程式的結果。 您必須在此事件中包含復原原始實際執行環境的程式，測試計劃結果表示執行失敗。
  
### <a name="build-your-test-procedures"></a>建立測試程式

您的測試程式應該包含每個輸出和輸入網路服務的測試，Office 365 都使用 ExpressRoute，而不是會使用。 程式應包括從每個唯一的網路位置進行測試，包括在公司局域網中非內部部署的使用者。
  
測試活動的一些範例包含下列各項。
  
1. 從您的內部部署路由器 Ping 至您的網路操作員路由器。

2. 驗證您的內部部署路由器是否已接收 500 + Office 365 和 CRM Online IP 位址播發。

3. 驗證您的輸入和輸出 NAT 是在 ExpressRoute 和內部網路之間運作。

4. 驗證從您的路由器宣告到您的 NAT 的路由。

5. 驗證 ExpressRoute 已接受您宣告的首碼。

      - 使用下列 Cmdlet 來確認對等通告：

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. 驗證您的公用 NAT IP 範圍不會透過任何其他 ExpressRoute 或公用網際網路網路電路宣告給 Microsoft，除非它是先前範例中的較大範圍的特定子集。

7. ExpressRoute 電路成對，請驗證兩個 BGP 會話是否都在執行中。

8. 在 NAT 內設定單一主機，並使用 ping、tracert 和 tcpping 來測試跨新電路與主機 outlook.office365.com 的連線能力。 或者，您也可以在鏡像的埠上使用 Wireshark 或 Microsoft 網路監視器3.4 之類的工具，以驗證您能夠連線至與 outlook.office365.com 相關聯的 IP 位址。

9. 測試 Exchange Online 的應用層級功能。

  - 測試 Outlook 可以連接到 Exchange Online 和傳送/接收電子郵件。

  - 測試 Outlook 能夠使用線上模式。

  - 測試 smartphone 連線能力及傳送/接收能力。

10. 測試 SharePoint 線上的應用層級功能

  - 測試商務用 OneDrive 同步處理用戶端。

  - 測試 SharePoint 線上 web 存取。

11. 測試商務用 Skype 呼叫案例的應用層級功能：

  - 加入電話會議做為已驗證的使用者 [由使用者初始化的邀請]。

  - 邀請使用者撥打電話會議 [從 MCU 傳送邀請]。

  - 以匿名使用者身分使用商務用 Skype web 應用程式加入會議。

  - 從您的有線電腦連線、IP 電話及行動裝置加入通話。

  - 呼叫同盟使用者 o 呼叫至 PSTN 驗證：通話已完成，通話品質可接受，連線時間是可接受的。

  - 確認已針對承租人和同盟使用者的兩個成員更新連絡人的狀態。

### <a name="common-problems"></a>常見問題

非對稱路由是最常見的實施問題。 以下是一些要尋找的常見來源：
  
- 就地使用開放或單層網路路由拓撲，但沒有源 NAT。

- 不使用 SNAT 透過網際網路和 ExpressRoute 連接來路由傳送至輸入服務。

- 在部署廣泛之前，請勿在測試網路上測試 ExpressRoute 上的輸入服務。

## <a name="deploying-expressroute-connectivity-through-your-network"></a>透過您的網路部署 ExpressRoute 連通性
<a name="testing"> </a>

將您的部署逐步劃分到網路的一個網段，以逐步向網路的不同部分推出，並以每個新的網路區段復原的計畫。 如果您的部署與 Office 365 部署對齊，請先將您的部署部署到 Office 365 試驗使用者，再從那裡進行擴充。
  
先進行測試，然後再進行實際執行：
  
- 執行部署步驟以啟用 ExpressRoute。

- 測試您的查看網路路由是否如預期。

- 在每個輸入和輸出服務上執行測試。

- 如果您探索任何問題，就會復原。

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>使用測試網路段設定 ExpressRoute 的測試連接

現在，您已完成的計畫是在一小段時間進行測試。 在此測試中，您將建立單一 ExpressRoute 連線與 Microsoft 對等網路對內部部署網路上的測試子網的關聯。 您可以設定[試用 Office 365 租](https://go.microsoft.com/fwlink/p/?LinkID=403802)使用者與 test 子網之間的連線，並在測試子網中包含您將在生產環境中使用的所有輸出和輸入服務。 設定測試網路段的 DNS，並建立所有輸入和輸出服務。 執行測試計劃，並確定您熟悉每個服務和路由傳播的路由。
  
### <a name="execute-the-deployment-and-test-plans"></a>執行部署和測試計劃

當您完成上述專案時，請核對您已完成的區域，並確定您和您的小組已在執行部署和測試計劃之前，先查看這些專案。
  
- 網路變更所涉及的輸出和輸入服務清單。

- 全域網路架構圖表顯示網際網路出口和 ExpressRoute 的 [符合我的位置] 位置。

- 示範用於每個已部署服務之不同網路路徑的網路路由圖表。

- 部署計畫，包含必要時執行變更和回滾的步驟。

- 測試每個 Office 365 和網路服務的測試計劃。

- 已完成輸入和輸出服務之實際執行路由的紙張驗證。

- 測試網段上的完整測試，包括可用性測試。

選擇一個長時間足以透過整個部署計畫及測試計劃執行的中斷時段，並有一些時間可供進行疑難排解，以及在必要時回復的時間。
  
> [!CAUTION]
> 由於透過網際網路和 ExpressRoute 進行路由的複雜性質，建議您在此視窗中新增額外的緩衝時間，以處理複雜路由疑難排解。
  
### <a name="configure-qos-for-skype-for-business-online"></a>設定商務用 Skype 線上的 QoS

QoS 是取得商務用 Skype 線上之語音和會議權益所需的。 您可以在確保 ExpressRoute 網路連接不會封鎖任何其他 Office 365 服務存取之後，設定 QoS。 QoS 的設定會在[商務用 Skype Online ExpressRoute 和 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)的文章中說明。
  
## <a name="troubleshooting-your-implementation"></a>您的實施疑難排解
<a name="troubleshooting"> </a>

第一個要注意的地方是在實施方案中未錯過任何專案，在此實施方案中的步驟。 若有可能複製錯誤並加以調試，請傳回並執行進一步的小型網路測試。
  
識別測試期間哪些輸入或輸出服務失敗。 針對每個失敗的服務，明確取得 IP 位址與子網。 繼續進行並流覽紙張上的網路拓撲圖表，並驗證路由。 特別驗證通告 ExpressRoute 路由的位置，在中斷期間（如果可能有追蹤）進行路由測試。
  
以網路追蹤方式執行 PSPing 每個用戶端點，並評估來源和目的地 IP 位址，以驗證其是否如預期。 對您在埠25公開的任何郵件主機執行 telnet，確認在預期的情況中，SNAT 會隱藏原始來源 IP 位址。
  
請記住，當您使用 ExpressRoute 連線部署 Office 365 時，必須確定 ExpressRoute 的網路設定為最優化設計，而且您已優化網路上的其他元件，例如用戶端電腦。 除了使用此規劃指南來疑難排解可能錯過的步驟之外，我們也編寫[Office 365 的性能疑難排解計畫](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c)。
  
您可以使用下列短連結返回這裡：[https://aka.ms/implementexpressroute365]()
  
## <a name="related-topics"></a>相關主題

[評估 Office 365 網路連線能力](assessing-network-connectivity.md)
  
[Azure ExpressRoute for Office 365](azure-expressroute.md)
  
[管理 ExpressRoute for Office 365 連線](managing-expressroute-for-connectivity.md)
  
[使用 ExpressRoute for Office 365 進行路由傳送](routing-with-expressroute.md)
  
[使用 ExpressRoute for Office 365 進行網路規劃](network-planning-with-expressroute.md)
  
[在 Office 365 案例的 ExpressRoute 中使用 BGP 社區](bgp-communities-in-expressroute.md)
  
[商務用 Skype Online 中的媒體品質和網路連線效能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[針對商務用 Skype Online 最佳化您的網路](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[商務用 Skype Online 中的 ExpressRoute 與 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[使用 ExpressRoute 的通話流程](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[使用基準與效能歷程記錄進行 Office 365 效能調整](performance-tuning-using-baselines-and-history.md)
  
[Office 365 的效能疑難排解規劃](performance-troubleshooting-plan.md)
  
[Office 365 URL 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 網路與效能調整](network-planning-and-performance.md)