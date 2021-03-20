---
title: 將 (網路連接至雲端) —一種架構師的視點
description: 深入瞭解如何透過避免最常見的陷阱，為雲端連線優化您的網路。
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 7de9aec29b0a57e85e3539fc2e99384de545c52a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904633"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>將 (網路連接至雲端) —一種架構師的視點

在本文中， [Fisher](https://www.linkedin.com/in/edfisher/)的安全性 & 規範架構架構中，說明如何透過避免最常見的陷阱，為雲端連線優化您的網路。 

## <a name="about-the-author"></a>關於作者

![Ed Fisher 相片](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

我目前是一個位於東南亞地區的主要技術專家，著重于安全性 & 合規性。 在過去10年中，我已與移至 Office 365 的客戶合作。 我已使用小型店，具有許多地方的政府機構和企業，有成千上萬的使用者在世界各地散佈，許多其他客戶都有成千上萬的使用者、世界各部分的多個位置，需要更高的安全性，以及許多法規遵從性需求。 我已協助成百上千的企業和數百萬使用者可安全且安全地移至雲端。

透過過去25年的背景，包含安全性、基礎結構及網路工程，並在加入 Microsoft 之前將兩個先前的雇主移至 Office 365，我已在您的表格的一面執行大量時間，並記住類似的專案。 雖然不是兩個客戶完全相同，也有相似的需求，而且在使用標準化服務（例如任何 SaaS 或 PaaS 平臺）時，最佳的做法一般都相同。

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>這不是網路，就是您使用 (mis) 時，如何使用！

不論發生多少次，它永遠無法 amaze 我的 *創意* 安全性小組和網路小組如何嘗試如何連接至 Microsoft 雲端服務。 永遠都堅持使用一些安全性原則、符合性標準或更好的方式，而不願意參與與其嘗試完成的談話，或是更好、更輕鬆、更具成本效益及更具效能 *的方式。*

當這類內容上報給我時，我一般會願意採取挑戰，並透過原因及其原因，將其引導至所需的位置。 不過，如果我已完全告別，我必須分享，有時我只想讓他們執行他們的動作，然後再回告訴您，當他們最後 concede 時，就不會這麼做。 我可能會想這麼做，但 *不* 這麼做。 我所做的就是嘗試說明我即將包含在此文章中的所有專案。 不論您的角色為何，如果您的組織想要使用 Microsoft 雲端服務，可能會有一些可協助您找出的智慧。

## <a name="guiding-principles"></a>指導原則

讓我們從周圍的部分基本規則開始。 我們正在討論如何安全地連線至雲端服務，以確保最低的複雜性和最大的效能，同時維持實際的安全性。 無論您或您的客戶，都不會將其計數器的計數器計數器的任何計數器，都將無法使用您最喜歡的 proxy 伺服器。

- **您可以做到，並非表示您應該**：或從 Jurassic 駐留影片 "Paraphrase Ian Malcolm。是的，是的，但是您的安全性小組非常 preoccupied，但他們是否可以讓他們不會停止思考是否應該。
- **安全性並非平均複雜度**：您只需要花更多資金、路由傳送更多裝置，或按一下 [更多按鈕]，就不會安全。
- **Office 365 是透過網際網路存取**：但這與 office 365 是網際網路的功能不同。 這是由 Microsoft 所管理並由您管理的 SaaS 服務。 與您在網際網路上流覽的網站不同的是，您實際上可以查看 curtain，而且可以套用您所需的控制項以滿足您的原則和相容性標準，只要您瞭解在您可以符合您的目標時，您可能只需要以不同的方式來執行。
- **Chokepoints 已損壞，已當地語系化的 breakouts 很好**：每個人都永遠都想要 backhaul 其所有使用者的所有網際網路流量，以加以監控並強制執行原則，但通常是因為其在其所有位置都不是布建網際網路存取，或其執行方式。 但這些 chokepoints 都是正確的 .。。流量淺的點。 無法防止使用者流覽 Instagram 或流式顯示的 cat 影片，但不會以相同的方式處理重要的商務應用程式流量。
- [！注意]**如果 dns ain't 快樂，ain't 什麼高興**：透過不良的 dns 可 hamstrung 最佳設計網路，不論是由 recursing 對世界其他區域中的伺服器的要求，或是使用 ISP 的 dns 伺服器或其他快取 dns 解析資訊的公用 DNS 伺服器。
- **只是因為這是您如何使用的方式，不表示這是您現在應該採取** 的做法：不斷的技術變更，Office 365 並未例外。 套用內部部署服務開發及部署的安全性措施，或控制隨意瀏覽不會提供相同等級的安全性保證，而且可能會對效能造成嚴重的負面影響。
- 您 **可以透過網際網路來存取 Office 365**：這是簡而言之。 無論您想要在您的使用者和 edge 之間進行什麼動作，當該流量離開您的網路之後及進入我們之前，該流量仍會透過網際網路傳送。 即使您是使用 Azure ExpressRoute 直接將網路的某些延遲機密流量路由傳送給我們，您絕對需要有網際網路連線能力。 接受。 請勿 overthink。

## <a name="where-bad-choices-are-often-made"></a>經常進行不良選擇的地方

當安全性名稱中有很多地方會發生不良決策時，這些是我經常遇到的客戶。 許多客戶交談都包含所有這些討論。

### <a name="insufficient-resources-at-the-edge"></a>Edge 沒有足夠的資源

許多客戶都在部署嶄新環境，而且他們的使用者可以運作的使用者以及網際網路出口的方式，都有多年的經驗。 客戶是否有 proxy 伺服器或允許直接存取，以及是否只是 NAT 輸出流量，在幾年內就是這麼做，而且不會考慮在將傳統的內部應用程式移至雲端時，要開始逐步傳送的程度。

頻寬一定很重要，但 NAT 裝置可能無法處理增加的負載，而且可能會啟動較早關閉的連線來釋放資源。 大多數連接至 Office 365 的用戶端軟體都需要持續連線，而使用者完全使用 Office 365 時，可能會有32或多個同時連線。 如果 NAT 裝置將其提前除去，這些應用程式可能會在嘗試使用不再存在的連接時，變成無回應。 當他們放棄並嘗試建立新的連線時，其網路設備上的負載會進一步增加。

### <a name="localized-breakout"></a>當地語系化的專題討論

在此清單中的其他專案會立即向外移動一件事。 將您的使用者流量 Backhauling 至中央出局點，尤其是當該出局點位於您的使用者所在的其他地區時，會帶來不必要的延遲，同時會影響用戶端經驗和下載速度。 Microsoft 在世界各地都有一個目前狀態，所有服務和對等都是以幾乎每個主要的 ISP 所建立的所有服務和對等狀態，所以將使用者的流量路由傳送至 *本機* ，可確保在最小延遲的情況下，快速進入網路

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS 解析流量應該遵循網際網路出局路徑

當然，用戶端若要尋找任何端點，則必須使用 DNS。 Microsoft 的 DNS 伺服器評估 DNS 要求的來源，以確保我們傳回與要求來源最接近的回應（以網際網路字詞為單位）。 確定您的 DNS 已設定，因此名稱解析要求會與使用者的流量完全相同的路徑，lest 您將其授與其他地區的端點。 這表示讓本機 DNS 伺服器「移至 root」，而不是轉寄至遠端資料中心的 DNS 伺服器。 並留意公開及私人 DNS 服務，其可能會從世界上一個部分快取結果，並提供給他們，來自世界其他部分的要求。

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>若為 proxy 或非 proxy，即表示問題

考慮的第一個考慮因素是是否要 proxy 使用者的連線到 Office 365。 這一點很簡單;不 proxy。 Office 365 是透過網際網路存取，但不是網際網路。 它是核心服務的擴充，應視為這樣。 您可以在服務中使用 proxy 執行的任何動作（如 DLP 或反惡意程式碼或內容檢查），而且可以在規模上使用，而不需要破譯 TLS 加密的連線。 不過，如果您真的想要以其他方式控制的流量 proxy，請注意我們的指導方針 [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) 和流量類別 [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) 。 我們有三種類型的流量用於 Office 365。 優化和允許真的應該是直接的，並略過您的 proxy。 預設值可為 proxy。 詳細資料位於這些檔中 .。。閱讀。

使用 proxy 的大多數客戶在實際查看其執行內容時，請先意識到當用戶端對 proxy 進行 HTTP 連線要求時，proxy 現在只會有昂貴的額外路由器。 在使用中的通訊協定（例如 MAPI 和 RTC）甚至不是網頁 proxy 所知道的通訊協定，所以即使 TLS 破譯，也不會真正取得任何額外的安全性。 您取得額外 *的* 延遲。 [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md)如需詳細資訊，請參閱，包括 Microsoft 365 流量的優化、允許和預設類別。

最後，請考慮 proxy 的整體影響及其對應的回應，以應對這種影響。 隨著透過 proxy 進行越來越多的連線，它可能會降低 TCP 規模因素，使其不需要大量增加流量的緩衝。 我已看到客戶的客戶，其 proxy 因其使用的比例因數為0而超載。 因為縮放比例是指數值，我們喜歡使用8，所以每個比例因數值的減少都會對輸送量造成極大的負面影響。

TLS 檢查是指安全性！ 但不是真的！ 許多具有 proxy 的客戶都想使用它們來檢查所有流量，這表示 TLS "中斷並檢查"。 當您針對透過 HTTPS 存取的網站執行此作業時 (隱私權考慮，但) proxy 可能必須這麼做，10或20個併發資料流程的數量為幾百毫秒。 如果有較大的下載或可能的影片，其中一或多個連線可能會更長一些，但是在整體上，大多數的連線會很快地建立、傳送和關閉。 「中斷」和「檢查」表示 proxy 必須加倍工作。 對於從用戶端到 proxy 的每個連線，proxy 還必須對端點進行個別的連線。 因此，1會變成2，2變成4，32會變成64。 ... 請參閱我要前往何處？ 您很可能會為一般網頁衝浪調整 proxy 方案的大小，但是當您嘗試對 Office 365 的用戶端連線執行相同的作業時，並行連線的數量可能會比您所調整的數量還要大。

### <a name="streaming-isnt-important-except-that-it-is"></a>流式處理並不重要，只 *是*

使用 UDP 的 Office 365 中唯一的服務是 Skype (即將淘汰) 和 Microsoft 團隊。 小組對資料流程流量（包括音訊、影片及簡報共用）使用 UDP。 流式流量是即時的，例如當您使用語音、影片和展示卡片或演示程式進行線上會議時。 這類使用 UDP 是因為如果丟棄或無序接收封包，它實際上是由使用者 unnoticeable，而且資料流程可以繼續進行。

當您不允許來自用戶端的輸出 UDP 流量給服務時，他們可以回退使用 TCP。 不過，如果丟棄 TCP 封包， *所有專案都會停止* ，直到重新傳輸超時 (RTO) 到期，而且遺失的封包可以重新傳輸。 如果封包到達順序不正常，所有的封包都會停止，直到其他的封包到達，而且可依順序重新組合。 這兩種情況都會導致音訊 () 和影片的最大餘地？和影片 (您是否已按一下某些專案 .。。哦，它已) ，會導致效能不良及不良的使用者體驗。 請記得我在 proxy 上放置的內容？ 當您強制團隊用戶端使用 proxy 時，強制其使用 TCP。 現在，您會造成負面效能影響兩次。

### <a name="split-tunneling-may-seem-scary"></a>分割的隧道可能似乎有點可怕

但不是。 所有與 Office 365 的連線都是透過 TLS。 我們現在已經為您提供了 TLS 1.2，而且即將停用舊版用戶端，因為舊版用戶端仍會使用它們，而且這是一種風險。

強制 TLS 連線（或32）以先透過 VPN 傳送，然後再移至服務，不會增加安全性。 它會增加延遲，並減少整體輸送量。 在某些 VPN 解決方案中，它甚至會強制 UDP 經由 TCP，這會對資料流程流量產生非常負面的影響。 而且，除非您執行 TLS 檢查，否則沒有任何不利的不利因素。 在客戶中，一種非常常見的主題是大多數的員工都是「遠端」，這是因為他們會看到大量的頻寬和效能影響，讓所有使用者都能使用 VPN 來進行連線，而不是設定分割隧道以供 access [優化類別 Office 365 端點](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)。

這是一種簡單的修復方式，可讓您進行分割，也就是您應該執行的工作。 如需詳細資訊，請確定您已透過 [VPN 分割隧道，針對遠端使用者，查看 [優化 Office 365 的連線能力](../enterprise/microsoft-365-vpn-split-tunnel.md)]。

## <a name="the-sins-of-the-past"></a>過去的原罪

許多情況下，進行不良選擇的原因來自于 (1) 不知道服務的運作方式， (2) 嘗試遵循在採用雲端之前所撰寫的公司原則，而 (3) 安全性小組，他們可能不會輕易相信有多種方式可以達成其目標。 但願上述及下列連結將協助您使用第一個。 必須有執行的資助，才可超過第二個。 解決安全性原則的目標，而不是其方法，可協助第三個。 從設定內容仲裁、DLP 到資訊保護、端點驗證到零天威脅的條件式存取，任何最終目標合理的安全性原則都可以利用 Office 365 中提供的功能來完成，而且不會對內部部署網路齒輪、強制 VPN 隧道及 TLS 中斷及檢查產生任何相依性。

其他情況下，在組織開始移至雲端之前所調整和購買的硬體，只是無法擴充以處理新的流量模式和載入。 如果您真的必須透過單一出局點路由傳送所有流量，以及/或 proxy，請先準備好升級網路設備和頻寬。 小心監視兩者上的使用狀況，因為隨著以上的使用者，經驗不會變慢。 所有人都會順利進入，直到到達問題點為止，所有人都會受到影響。

## <a name="exceptions-to-the-rules"></a>規則的例外狀況

如果您的組織需要 [租使用者限制](/azure/active-directory/manage-apps/tenant-restrictions)，您必須使用具有 TLS 中斷的 proxy，並檢查以強制透過 proxy 執行某些流量，但是您不需要強制所有流量透過它。  這不是全部或任何的主張，所以請注意 proxy 必須修改的內容。

如果您想要允許分割分割，但同時又使用 proxy 進行一般 web 流量，請確定您的 PAC 檔案定義必須直接走向什麼，以及如何為透過 VPN 隧道定義的有趣流量定義。 我們會提供範例 PAC 檔案 [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) ，讓這項管理工作變得更容易。

## <a name="conclusion"></a>總結

成千上萬的組織（包括幾乎所有的《財富500」）都會針對其使命至關重要的功能使用 Office 365。 它們會安全地進行，也可以透過網際網路進行。

不論您在玩什麼樣的安全性目標，都有沒有必要的方法可讓您完成，不需要 VPN 連線、proxy 伺服器、TLS 中斷及檢查或集中式網際網路出口，以盡可能快地讓使用者的流量從您的網路和我們的流量中取得，而不論您的網路是公司總部，還是一部遠端辦公室。，或該使用者在家運作。 我們的指導方針取決於如何建立 Office 365 服務，以確保安全且性能的使用者體驗。

## <a name="further-reading"></a>進一步閱讀

[Office 365 網路連接原則](../enterprise/microsoft-365-network-connectivity-principles.md)

[Office 365 URL 與 IP 位址範圍](../enterprise/urls-and-ip-address-ranges.md)

[管理 Office 365 端點](../enterprise/managing-office-365-endpoints.md)

[Office 365 IP 位址和 URL Web 服務](../enterprise/microsoft-365-ip-web-service.md)

[評估 Office 365 的網路連線能力](../enterprise/assessing-network-connectivity.md)

[Office 365 網路與效能調整](../enterprise/network-planning-and-performance.md)

[評估 Office 365 的網路連線能力](../enterprise/assessing-network-connectivity.md)

[使用基準與效能歷程記錄進行 Office 365 效能調整](../enterprise/performance-tuning-using-baselines-and-history.md)

[Office 365 的效能疑難排解規劃](../enterprise/performance-troubleshooting-plan.md)

[內容傳遞網路](../enterprise/content-delivery-networks.md)

[Microsoft 365 連線測試](https://connectivity.office.com/)

[Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 網路部落格](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[使用 VPN 分割隧道的遠端使用者的 Office 365 連線能力](../enterprise/microsoft-365-vpn-split-tunnel.md)