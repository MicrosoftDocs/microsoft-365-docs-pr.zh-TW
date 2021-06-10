---
title: 使用 Office 365 ExpressRoute 進行網路規劃
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
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
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: 在本文中，您將瞭解 Office 365 的 Azure ExpressRoute，以及如何使用它進行網路規劃。
ms.openlocfilehash: 440d4fafadd7e9b504dc4ffdac1123a2956ed798
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923573"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>使用 Office 365 ExpressRoute 進行網路規劃

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

ExpressRoute for Office 365 提供網路與 Microsoft 資料中心之間的第3層連線能力。 電路使用邊界閘道通訊協定 (BGP) Office 365 前端伺服器的路由公佈。 從您的內部部署裝置的觀點來看，當他們需要選取正確的 TCP/IP 路徑 Office 365 時，Azure ExpressRoute 被視為網際網路的替代方式。
  
Azure ExpressRoute 會將直接路徑新增至 Microsoft 資料中心內 Office 365 伺服器所提供之一組特定支援的功能和服務。 Azure ExpressRoute 不會取代網際網路連線至 Microsoft 資料中心或基本網際網路服務，例如功能變數名稱解析。 Azure ExpressRoute 和您的網際網路電路應該是安全且多餘的。
  
下表著重于 Office 365 內容中的網際網路和 Azure ExpressRoute 連接之間的一些差異。

|**網路規劃的差異**|**網際網路網路連線**|**ExpressRoute 網路連接**|
|:-----|:-----|:-----|
| 存取必要的網際網路服務，包含;  <br/>  DNS 名稱解析  <br/>  憑證吊銷驗證  <br/>  內容傳遞網路（CDNs）  <br/> |是  <br/> |對 Microsoft 所擁有的 DNS 和/或 CDN 基礎結構的要求可能會使用 ExpressRoute 網路。  <br/> |
| 存取 Office 365 服務，包含;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  商務用 Skype Online  <br/>  瀏覽器中 Office  <br/>  Office 365入口網站和驗證  <br/> |是，所有的應用程式和功能  <br/> |是的， [特定的應用程式和功能](./urls-and-ip-address-ranges.md) <br/> |
|周邊環境中的內部部署安全性。  <br/> |是  <br/> |是  <br/> |
|高可用性規劃。  <br/> |容錯移轉至備用網際網路網路連線  <br/> |容錯移轉至備用的 ExpressRoute 連接  <br/> |
|與可預測網路設定檔的直接連線。  <br/> |否  <br/> |是  <br/> |
|IPv6 連線能力。  <br/> |是  <br/> |是  <br/> |

如需詳細的網路規劃指引，請展開下列標題。 我們也為 dives 更深入的 Office 365 訓練系列記錄了10部分的[Azure ExpressRoute](https://channel9.msdn.com/series/aer) 。

## <a name="existing-azure-expressroute-customers"></a>現有 Azure ExpressRoute 客戶

如果您使用現有的 Azure ExpressRoute 電路，而且想要透過此線路新增 Office 365 連線能力，您應該查看電路數目、出局位置和電路大小，以確保其符合 Office 365 使用的需求。 大多數的客戶都需要額外的頻寬，許多需要額外的電路。
  
若要透過現有 Azure ExpressRoute 電路啟用 Office 365 存取，請[設定路由篩選器](/azure/expressroute/how-to-routefilter-portal)以確保可存取 Office 365 服務。
  
Azure ExpressRoute 訂閱是以客戶為中心，這意味著訂閱與客戶密切相關。 身為客戶，您可以有多個 Azure ExpressRoute 電路，而且可以透過這些電路存取許多 Microsoft 雲端資源。 例如，您可以選擇存取 azure 主控的虛擬機器、Office 365 測試租使用者，以及一對使用一對冗余 Azure ExpressRoute 電路的 Office 365 生產租使用者。
  
此表概述兩種類型的對等關係，您可以選擇透過電路實施。

|**對等關係**|**Azure 私人**|**Microsoft**|
|:-----|:-----|:-----|
|**服務** <br/> |IaaS： Azure 虛擬機器  <br/> |PaaS： Azure 公用服務  <br/> SaaS： Office 365  <br/> SaaS： Dynamics 365  <br/> |
|連線初始化 * * * * <br/> |客戶對 Microsoft  <br/> Microsoft 對客戶  <br/> |客戶對 Microsoft  <br/> Microsoft 對客戶  <br/> |
|**QoS 支援** <br/> |無 QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1</sup>QoS 只能在此時間商務用 Skype 支援。
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Azure ExpressRoute 的頻寬規劃

每個 Office 365 客戶都有獨特的頻寬需求，具體取決於每個位置的人員人數、每個 Office 365 應用程式的使用方式，以及其他因素，例如使用內部部署或混合式設備及網路安全性設定。
  
頻寬太少會導致擁塞、資料重新傳輸，以及無法預測的延遲。 頻寬太多會導致不必要的成本。 在現有網路上，頻寬通常是指以百分比表示的電路上的可用空間量。 具有10% 的餘地可能會造成擁塞，而且具有80% 的餘地通常表示不必要的成本。 一般的餘地目標分配為20% 到50%。
  
若要尋找適當的頻寬層級，最佳的方式是測試現有的網路使用量。 在所有網路設定和應用程式都有一些獨特的情況時，這是取得實際使用方式的唯一方式，而且需要。 當您測量時，您會想要密切注意頻寬消耗、延遲及 TCP 擁塞，以瞭解您的網路需求。
  
當您有包括所有網路應用程式的預估基準時，試驗 Office 365，其中包含組織中人員的不同設定檔的小群組，以決定實際使用量，並使用這兩個度量單位來估計每個辦公室位置所需的頻寬量。 如果在測試中發現任何延遲或 TCP 擁塞問題，您可能需要使用 Office 365 將出口移近，或移除大量網路掃描（如 SSL 解密/檢查）。
  
建議使用哪種類型的網路處理的所有建議，適用于 ExpressRoute 和網際網路電路。 在我們的 [效能調整網站](./network-planning-and-performance.md)上，其餘的指導方針也是如此。
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>對 Office 365 案例的 Azure ExpressRoute 套用安全性控制

保護 Azure ExpressRoute 連線能力的方式，會從與保護網際網路連線的原則相同。 許多客戶選擇以 ExpressRoute 路徑來部署網路和周邊控制，將其內部部署網路連接至 Office 365 和其他 Microsoft 雲端。 這些控制項可能包括防火牆、應用程式 proxy、資料洩漏防護、入侵偵測、入侵防護系統等等。 在許多情況下，客戶會將不同層級的控制套用到從內部部署移至 Microsoft 的流量，與從 Microsoft 發起的流量，到客戶的內部部署網路，而不是從內部部署前往一般網際網路目的地的流量。
  
以下是幾個整合安全性的範例，其中包含您選擇要部署的 [ExpressRoute 連接模型](/azure/expressroute/expressroute-connectivity-models) 。

|**ExpressRoute 整合選項**|**網路安全性周邊模型**|
|:-----|:-----|
|位於雲端 exchange 上的共有  <br/> |在建立 ExpressRoute 連接的共同位置設施中，安裝新的或利用現有的安全性/周邊基礎結構。  <br/> 充分利用共同位置的功能，將共同位置的路由傳送/互連和來回連線，加入內部部署的安全性/周邊基礎結構。  <br/> |
|點對點乙太網路  <br/> |終止現有內部部署安全性/周邊基礎結構位置中的點對點 ExpressRoute 連接。  <br/> 安裝 ExpressRoute 路徑特有的新安全性/周邊基礎結構，並結束點對點連接。  <br/> |
|任何 IPVPN  <br/> |利用現有的內部部署安全性/周邊基礎結構，IPVPN 所有進出的位置，以用於 Office 365 連線的 ExpressRoute。  <br/> 髮夾 IPVPN 用於 ExpressRoute，以用於 Office 365 指派為安全性/周邊的特定內部部署位置。  <br/> |

有些服務提供者也會提供受管理的安全性/周邊功能，作為其 Azure ExpressRoute 的整合解決方案的一部分。
  
考慮用於 ExpressRoute Office 365 連線之網路/安全性周邊選項的拓撲放置時，需要考慮下列其他考慮
  
- 深度和類型的網路/安全性控制措施可能對 Office 365 使用者體驗的效能與擴充性產生影響。

- 輸出 (內部部署- \> microsoft) 和內送 (的 \> 內部部署) [如果已啟用] 資料流程可能會有不同的需求。 它們可能會與一般網際網路目的地的輸出有所不同。

- 針對埠/通訊協定和必要的 IP 子網的 Office 365 需求，不論流量透過 ExpressRoute 傳送 Office 365 或透過網際網路，都是相同的。

- 客戶網路/安全性控制措施的拓撲位置，可決定使用者與 Office 365 服務之間的端對端網路，並對網路延遲和擁塞產生大量影響。

- 客戶建議您設計其安全性/周邊拓撲，以用於 Office 365 的 ExpressRoute，依照冗余、高可用性和損毀修復的最佳作法。

以下是 Woodgrove Bank 的範例，它會比較不同 Azure ExpressRoute 連線選項與上述周邊安全性模型。
  
### <a name="example-1-securing-azure-expressroute"></a>範例1：保護 Azure ExpressRoute
  
Woodgrove Bank 考慮執行 Azure ExpressRoute，並在規劃[與 ExpressRoute Office 365 進行路由](routing-with-expressroute.md)的最佳架構之後，以及在使用上述指導方針來瞭解頻寬需求之後，判斷其周邊的安全性最佳方法。
  
針對 Woodgrove，具有多個大陸之位置的多國組織，安全性必須橫跨所有周邊環境。 Woodgrove 的最佳連線選項是具有全球多個對等位置的多點連線，以服務于每個大陸的員工需求。 每個大陸在大陸內包含冗余 Azure ExpressRoute 電路，而且安全性必須橫跨所有這些電路。
  
Woodgrove 的現有基礎結構是可靠的，而且可以處理額外的工作，因此 Woodgrove Bank 可以使用基礎結構來進行 Azure ExpressRoute 和網際網路周邊安全性。 如果不是這種情況，Woodgrove 可以選擇購買其他的設備，以補充現有的設備或處理不同類型的連線。
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>使用 Azure ExpressRoute 的高可用性和容錯移轉
<a name="BKMK_high-availability"> </a>

我們建議您將每個出口的兩個作用中的電路至少布建到您的 ExpressRoute 提供者 ExpressRoute。 這是我們看到客戶失敗的最常見的地方，您可以布建一對主動/主動 ExpressRoute 電路，輕易避免這種情況。 我們也建議至少兩部主動/主動網際網路電路，因為許多 Office 365 服務只可透過網際網路使用。
  
在您網路的出局點內，也就是許多其他的裝置，也就是在人們如何感覺可用性的方式中扮演重要角色。 這兩部分的連線案例並未涵蓋 ExpressRoute 或 Office 365 sla，但他們會在端對端服務可用性（如組織中的人員所察覺）上起重要作用。
  
著重于「使用和運作 Office 365 人員」，如果任何一個元件的失敗都會影響人員使用服務的經驗，請尋找限制受影響人員總數百分比的方法。 如果容錯移轉模式是以複雜的方式，請考慮人員的復原時間很長，並尋找操作簡單且自動的容錯移轉模式。
  
在您的網路外、Office 365、ExpressRoute 和 ExpressRoute 提供者都具有不同層級的可用性。
  
### <a name="service-availability"></a>服務可用性
  
- Office 365 服務是由完善定義的[服務層級協定](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)所涵蓋，其中包含個別服務的正常運作時間和可用性衡量標準。 Office 365 可以維護這類高服務可用性層級的一個原因，就是在使用全域 microsoft 網路的多個 microsoft 資料中心之間進行無縫容錯移轉的個別元件。 此容錯移轉可從資料中心和網路延伸至多個網際網路出局點，並可透過使用服務的人員觀點順利地進行容錯移轉。

- ExpressRoute 會在 Microsoft 網路 Edge 和 ExpressRoute 提供者或夥伴基礎結構之間，于個別專用線路上 [提供99.9% 的可用性 SLA](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) 。 這些服務層級是在 ExpressRoute 電路層級套用，此層級是由 [兩個獨立的互連](/azure/expressroute/expressroute-introduction) 網路設備和每個對等位置中的網路提供者設備兩者所組成。

### <a name="provider-availability"></a>提供者可用性
  
- Microsoft 的服務層級排列會停止在您的 ExpressRoute 提供者或合作夥伴。 這也是您可以選擇會影響可用性層級的第一個位置。 您應該仔細評估您的網路周邊和您的網路對等位置之間，您的 ExpressRoute 提供者之間所提供的架構、可用性和恢復性特性。 請密切注意冗余、對等設備、載波提供之 WAN 回路的邏輯和實體方面，以及任何額外的增值服務，例如 NAT 服務或受管理的防火牆。

### <a name="designing-your-availability-plan"></a>設計可用性計畫
  
強烈建議您規劃及設計 Office 365 的端對端連線案例的高可用性和恢復性。 設計應該包含;
  
- 無單一失敗點，包括網際網路和 ExpressRoute 電路。

- 最小化受影響的人員人數，以及對預期的失敗模式影響的持續時間。

- 從最預期的失敗模式中，優化簡易、可重複和自動復原的處理常式。

- 透過冗余路徑支援整個網路流量和功能的需求，而不會造成大量的降級。

您的連線案例應該包含針對多個獨立和主動網路路徑進行優化，以 Office 365 的網路拓撲。 這會比只針對個別裝置或設備層級的冗余度優化的拓撲而產生更好的端對端可用性。
  
> [!TIP]
> 如果您的使用者分散在多個大陸或地理區域，且每個位置都透過冗余 WAN 環路連線到單一 ExpressRoute 電路所在的單一內部部署位置，您的使用者就會體驗出與網路拓撲設計較少的端對端服務可用性（包括將不同地區連接至最近的對等位置之獨立的 ExpressRoute 電路）。
  
我們建議您布建至少兩個 ExpressRoute 電路，每個電路都使用不同的地理位置對等位置進行連接。 您應該為所有人員使用 Office 365 服務的 ExpressRoute 連線能力，為每個地區布建這種主動-主動對的電路。 這可讓每個地區在會影響主要位置（例如資料中心或對等位置）的災難期間保持連線。 在 active/active 中進行設定，可讓使用者流量分散到多部網路路徑。 這可減少裝置或網路設備中斷期間受影響的人員範圍。
  
建議您不要在網際網路做為備份時使用單一 ExpressRoute 電路。
  
### <a name="example-2-failover-and-high-availability"></a>範例2：容錯移轉和高可用性
  
Woodgrove Bank 的多地理位置設計已完成路由、頻寬、安全性的審查，現在必須透過高可用性評審。 Woodgrove 會想到三個類別的高可用性;恢復能力、可靠性和冗余。
  
恢復功能可讓 Woodgrove 快速從失敗中復原。 可靠性可讓 Woodgrove 在系統中提供一致的結果。 冗余可讓 Woodgrove 在基礎結構的一個或多個鏡像實例之間移動。
  
在每個 edge 設定中，Woodgrove 都有冗余的防火牆、proxy 和 ID。 針對北美版，Woodgrove 在其達拉斯資料中心有一個 edge 設定，而在其弗吉尼亞州資料中心有另一個 edge configuration。 每個位置的冗余設備都提供該位置的恢復能力。
  
Woodgrove Bank 上的網路設定是根據幾個重要的原則建立的：
  
- 在每個地理區域內，有多個 Azure ExpressRoute 電路。

- 地區中的每個電路都可以支援該地區內的所有網路流量。

- 路由會明確根據可用性、位置等的一個或另一個路徑。

- Azure ExpressRoute 電路之間的容錯移轉會自動進行，不需執行 Woodgrove 所需的其他設定或動作。

- 網際網路間的容錯移轉會自動進行，而不需執行 Woodgrove 所需的其他設定或動作。

在此設定中，在實體和虛擬層級具有冗余，Woodgrove Bank 能夠以可靠的方式提供本機恢復功能、區域恢復能力和全域恢復功能。 Woodgrove 在評估每個地區的單一 Azure ExpressRoute 電路以及容錯移轉至網際網路的可能性之後，選擇此設定。
  
如果 Woodgrove 不能每個地區都有多個 Azure ExpressRoute 電路，請將從北美到 Azure ExpressRoute 電路的路由流量新增至亞亞的時間層級，而且所需的 DNS 轉寄站設定也會增加複雜性。
  
建議您不要將網際網路當作備份設定使用。 這會中斷 Woodgrove 的可靠性原則，並使用連線來產生不一致的經驗。 此外，請務必手動設定，以進行容錯移轉，以考慮已設定的 BGP 播發、NAT 設定、DNS 設定及 proxy 設定。 增加的容錯移轉複雜性可增加復原的時間，並降低其診斷及疑難排解所涉及之步驟的能力。
  
仍有關于如何規劃及實施流量管理或 Azure ExpressRoute 的問題？ 請閱讀我們 [網路和效能指導](./network-planning-and-performance.md) 或 [Azure ExpressRoute 常見問題](/azure/expressroute/expressroute-faqs)的其餘部分。
  
## <a name="working-with-azure-expressroute-providers"></a>使用 Azure ExpressRoute 提供者
<a name="BKMK_high-availability"> </a>

根據頻寬、延遲、安全性和高可用性規劃，選擇電路的位置。 知道您想要讓電路取得的最佳位置之後，即可透過 [地區查看目前的提供者清單](/azure/expressroute/expressroute-locations)。
  
請與您的提供者或提供者合作，以選取最佳連線選項、點對點、多點或主控。 請記住，只要頻寬和其他多餘元件支援您的路由和高可用性設計，您就可以混合和比對連線選項。
  
您可以使用下列短連結返回這裡：[https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>相關主題
<a name="BKMK_high-availability"> </a>

[評估 Office 365 網路連線能力](assessing-network-connectivity.md)
  
[Azure ExpressRoute for Office 365](azure-expressroute.md)
  
[管理 ExpressRoute for Office 365 連線](managing-expressroute-for-connectivity.md)
  
[使用 ExpressRoute for Office 365 進行路由傳送](routing-with-expressroute.md)
  
[實作 ExpressRoute for Office 365](implementing-expressroute.md)
  
[在 Office 365 案例的 ExpressRoute 中使用 BGP 社區](bgp-communities-in-expressroute.md)
  
[商務用 Skype Online 中的媒體品質和網路連線效能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[針對商務用 Skype Online 最佳化您的網路](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[商務用 Skype Online 中的 ExpressRoute 與 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[使用 ExpressRoute 的通話流程](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[使用基準與效能歷程記錄進行 Office 365 效能調整](performance-tuning-using-baselines-and-history.md)
  
[Office 365 的效能疑難排解規劃](performance-troubleshooting-plan.md)
  
[Office 365 URL 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 網路與效能調整](network-planning-and-performance.md)
  
[Office 365 端點常見問題集](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) (機器翻譯)