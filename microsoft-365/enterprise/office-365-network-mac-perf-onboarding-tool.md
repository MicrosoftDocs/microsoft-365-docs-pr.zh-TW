---
title: Microsoft 365 connectivity test (preview) Microsoft 365 系統管理中心
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
description: 'Microsoft 365 connectivity test in M365 Admin Center (預覽) '
ms.openlocfilehash: 421df459e2a8a1c1c62680b2d3658f5bdd297b25
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688538"
---
# <a name="microsoft-365-connectivity-test-in-the-microsoft-365-admin-center-preview"></a>Microsoft 365 connectivity test in the Microsoft 365 admin center (preview) 

Microsoft 365 connectivity test 位於 <https://connectivity.office.com> 。 其為輔助工具，可在 Microsoft 365 系統管理中心的 [ **健康情況 |] 底下使用網路洞察力和網路總分資訊。網路效能** 功能表。

>[!NOTE]
>上架工具支援 WW 商業銀行和 GCC 中的承租人，但不支援 GCC 高、DoD、德國或中國的承租人。

Microsoft 365 系統管理中心的網路洞察力是以 Microsoft 365 租使用者的產品度量為基礎。 相比之下，來自 Microsoft 365 連線測試的網路洞察力是在本機的工具中執行。 您可以在產品中執行的測試是有限的，而且在使用者可以收集更多資料的地方執行測試時，可能會產生更深入的洞察力。 請考慮，Microsoft 365 系統管理中心的網路洞察力會顯示在特定辦公室位置使用 Microsoft 365 的網路問題。 Microsoft 365 連線測試可協助識別導致網路效能改進動作的問題根源。

建議您將這些功能搭配使用，讓您可以在 Microsoft 365 系統管理中心中評估每個辦公室位置的網路品質狀態，並且在部署以 Microsoft 365 連線測試為基礎的測試之後找到更多細節。

>[!IMPORTANT]
>Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。

## <a name="the-advanced-tests-client-application"></a>高級測試用戶端應用程式

Microsoft 365 connectivity test 有兩個部分。 網站有可供 <https://connectivity.office.com> 下載的 Windows 用戶端應用程式。 可供下載的用戶端執行高級網路連線測試，大部分的測試都需要執行。

您可以從網站執行高級用戶端測試，它會在執行時，將結果填入回網頁。

![O365 網路上架工具範例測試結果](../media/m365-mac-perf/m365-mac-perf-onboarding-tool-tests.png)

## <a name="user-office-location"></a>使用者辦公室位置

使用者辦公室位置是從使用者網頁瀏覽器中偵測到。 用來識別商業網路周邊特定部分的網路距離。

使用者辦公室位置會顯示在地圖視圖上。

## <a name="distance-to-the-network-egress-location"></a>網路出局位置的距離

我們會在伺服器端識別網路出局 IP 位址。 位置資料庫是用來查詢網路出口的大致位置，並決定從該位置到辦公室位置的距離。 如果距離大於500英里 (800 公里) 會顯示為網路洞察力。

網路出局位置會顯示在地圖視圖上，並聯機至使用者辦公室位置，表示企業 WAN 內部的網路 backhaul。

從網路出局 IP 位址查看的位置可能不正確，這會導致此測試的錯誤結果。 若要驗證特定 IP 位址是否發生此錯誤，您可以使用可公開存取的網路 IP 位址位置網站。

建議使用 Microsoft 365 網路連線，將使用者辦公室位置的本機和直接網路輸出實施至網際網路。 對本機和直接出口的增強功能是解決這種網路洞察力的最佳方式。

## <a name="exchange-online-service-front-door"></a>Exchange Online 服務前面門

「使用中 Exchange Online 服務前門」是以 Outlook 這麼做的相同方式來識別，我們會從使用者辦公室位置測量網路的 TCP 延遲。 這兩種都是顯示的，與目前位置的建議最佳服務前端門清單相較。 如果使用非最佳 Exchange Online 服務前門，這會顯示為網路洞察力。

使用非最優 Exchange Online 服務前門可能是由網路 backhaul 在公司網路出口之前所造成，因此我們建議您在本機和直接的網路出口。 這種情況也可能是使用遠端 DNS 遞迴解析伺服器所造成，在此情況下，我們建議您將 DNS 遞迴解析程式伺服器與網路出局對齊。

我們計算對 Exchange Online 服務前門的 TCP 延遲的潛在改進。 若要執行此動作，請查看已測試的使用者 office 位置網路延遲，並從目前的位置減去網路延遲，以 closets Exchange Online 服務前門。 差異代表潛在的改進機會。

## <a name="comparison-of-performance-of-customers-in-the-area"></a>區域中客戶效能的比較

Exchange Online 服務前端的使用者辦公室位置的網路 TCP 延遲會與其他 Microsoft 365 客戶在相同大都市區域中進行比較。 如果相同地鐵區域中10% 以上的客戶都具有較佳的效能，就會顯示網路洞察力。

在城市中的所有使用者都可以存取相同的電信基礎結構，以及對網際網路電路和 Microsoft 網路的接近程度，就會產生網路洞察力。

## <a name="in-use-default-gateway"></a>使用預設閘道

「使用中的預設閘道」是測試用戶端為路由 TCP/IP 網路連線所設定的路由器。

這只是為了提供資訊，不會參與任何網路洞察力。

## <a name="in-use-dns-servers"></a>在 [使用 DNS 伺服器 (s) 

這會顯示在執行測試的用戶端電腦上設定的 DNS 伺服器。 它可能是 DNS 遞迴解析器伺服器，但這不常見。 這很可能是 DNS 轉寄站伺服器，可快取 DNS 結果並將任何未緩存的 DNS 要求轉送至另一部 DNS 伺服器。

這只是為了提供資訊，不會參與任何網路洞察力。

## <a name="identified-dns-recursive-resolver-server"></a>已識別 DNS 遞迴解析程式伺服器

在 [使用中的 DNS 遞迴解析程式] 中，進行特定的 DNS 要求，然後要求 DNS 名稱伺服器接收相同的要求時，便會加以識別。 此 IP 位址是 DNS 遞迴解析程式，它會在 IP 位址位置資料庫中查閱，以尋找位置。 然後計算從使用者辦公室位置到 DNS 遞迴解析伺服器位置的距離。 如果距離大於500英里 (800 公里) 會顯示為網路洞察力。

從網路出局 IP 位址查看的位置可能不正確，這會導致此測試的錯誤結果。 若要驗證特定 IP 位址是否發生此錯誤，您可以使用可公開存取的網路 IP 位址位置網站。

這項網路洞察力特別會影響 Exchange Online 服務前端的選取範圍。 若要解決此深入瞭解，本機和 direct 網路出局應該是必要條件，而且 DNS 遞迴解析器應該位於該網路出口之外。

## <a name="dns-lookup-of-exchange-online-front-end-server-and-sharepoint-online-front-end-server"></a>Exchange Online 前端伺服器及 SharePoint 線上前端伺服器的 DNS 查詢

這些會顯示這兩種 Microsoft 365 工作負載的服務前門的 DNS 記錄。 它們僅供參考，而且沒有相關聯的網路洞察力。

## <a name="proxy-server-identification"></a>Proxy 伺服器識別

我們識別在本機電腦上設定的 proxy 伺服器 (s) 。 我們會識別是否有任何在網路路徑中設定，以優化類別 Microsoft 365 網路流量。 我們識別從使用者辦公室位置到 proxy 伺服器的距離。 會先透過 ICMP ping 測試距離，如果失敗，我們會使用 TCP ping 進行測試，最後如果失敗，我們會在 IP 位址位置資料庫中查詢 proxy 伺服器的 IP 位址。 如果 proxy 伺服器的500英里後超過英里 (800 公里) 離開使用者辦公室位置，我們就會顯示網路洞察力。

## <a name="media-quality-checks"></a>媒體質量檢查

此測試會安裝並執行商務用 Skype 網路評估工具，並解釋結果。 可在上找到工具 [https://www.microsoft.com/download/details.aspx?id=53885](https://www.microsoft.com/download/details.aspx?id=53885) 。

這些是 Microsoft 小組音訊和視頻通話及會議功能所使用的 UDP 通訊協定測試。 我們測試 UDP 封包遺失、UDP 網路延遲、UDP 抖動及 UDP 封包重新排序。 如果有任何一種情況超出允許的範圍，就會顯示網路洞察力。

## <a name="tcp-connectivity-tests"></a>TCP 連線測試

我們會將使用者辦公室位置的 HTTP 連線測試至所有必要的 Microsoft 365 網路端點。 這些是發佈于 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。 對於任何無法連線的必要網路端點，都會顯示網路洞察力。

在商業網路周邊或使用做為雲端 proxy 的 proxy 伺服器、防火牆或其他網路安全裝置封鎖連線能力 ay。

## <a name="ssl-interception-tests"></a>SSL 截取測試

我們會在每個必要的 Microsoft 365 網路端點（已于所定義的 [優化] 或 [允許] 類別中）測試 SSL 憑證 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。 如果任何測試未找到 Microsoft SSL 憑證，則所連接的加密網路必須已被仲介網路裝置截獲。 網路洞察力會顯示在任何截獲的加密網路端點上。

如果 Microsoft 未提供 SSL 憑證，我們會顯示測試的 FQDN 和使用中的 SSL 憑證擁有者。 這個 SSL 憑證擁有者可能是 proxy 伺服器廠商，也可能是企業自我簽署憑證。

## <a name="network-path-diagnostics"></a>網路路徑診斷

本節顯示 ICMP traceroute 至 Exchange Online 服務前門、SharePoint Online 服務前門和 Microsoft 團隊服務前門的結果。 只提供此資訊，而且沒有相關聯的網路洞察力。

## <a name="faq"></a>常見問題集

以下是一些常見問題的解答。

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Microsoft 是否已發行及支援此工具？

這是一項概念證明，我們計畫定期提供更新，直到我們達到一般可用性發行狀態時，才會從 Microsoft 取得支援。 請提供意見反應以協助我們改進。 我們打算將更詳細的 Office 365 網路上架指南發佈為此工具的一部分，此工具是由其測試結果自訂為組織的一部分。

### <a name="what-is-microsoft-365-service-front-door"></a>何謂 Microsoft 365 服務的前門？

Microsoft 365 服務前端是 Microsoft 全球網路的進入點，Office 用戶端和服務會在此位置中斷其網路連線。 為了獲得最佳網路連接至 Microsoft 365，建議您的網路連線在您的城市或地鐵的最接近的 Microsoft 365 前端。

附注： Microsoft 365 服務前端與 Azure marketplace 中提供的「Azure 前門服務」產品沒有直接關聯。

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>何謂最優的 Microsoft 365 服務前門？

最佳的 Microsoft 365 服務前端是最接近您的網路出局，通常是在您的城市或大都市區域中。 使用 Microsoft 365 網路效能工具判斷您使用中的 Microsoft 365 服務前門和最優服務前門的位置。 如果工具判斷您的使用中的前門是最優的，您就會以最優化方式連線至 Microsoft 的全球網路。

### <a name="what-is-an-internet-egress-location"></a>何謂網際網路出口的位置？

網際網路出局位置是網路流量結束商業網路並連接到網際網路的位置。 此位置也會識別為您具有網路位址轉譯 (NAT) 裝置的位置，通常是您與網際網路服務提供者 (ISP) 的位置。 如果您看到位置和網際網路出局位置之間有長距離的距離，則這可能會識別重要的 WAN backhaul。

## <a name="related-topics"></a>相關主題

[Microsoft 365 系統管理中心的網路效能建議 (預覽) ](office-365-network-mac-perf-overview.md)

[Microsoft 365 網路效能深入 (預覽) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 網路評估 (預覽) ](office-365-network-mac-perf-score.md)

[Microsoft 365 Network Connectivity Location 服務 (預覽) ](office-365-network-mac-location-services.md)
