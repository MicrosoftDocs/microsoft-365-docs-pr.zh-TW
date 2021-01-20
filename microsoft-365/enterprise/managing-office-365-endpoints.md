---
title: 管理 Office 365 端點
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: 瞭解如何管理 Office 365 端點，以與企業組織網路架構搭配運作。
ms.openlocfilehash: 41dceae78d80a78b023517e8b6c5c5c0d73da2ef
ms.sourcegitcommit: 64262f6f42dcce6a4608b2e3c7ca6190b7009093
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905282"
---
# <a name="managing-office-365-endpoints"></a>管理 Office 365 端點

擁有多個辦公室位置和相連 WAN 的多數企業組織，都需要針對 Office 365 網路連線的設定。 您可以讓所有信任的 Office 365 網路要求直接通過防火牆，藉此略過所有額外的封包層級檢查或處理，進而將網路效能最佳化。 這會降低延遲和您的周邊容量需求。 要為使用者提供最佳效能的第一步，就是要找出 Office 365 網路流量。 如需詳細資訊，請參閱 [Office 365 Network Connectivity 原則](microsoft-365-network-connectivity-principles.md)。

Microsoft 建議您使用 [office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)，存取 office 365 網路端點和進行中的變更。

無論您管理重要 Office 365 網路流量的方式為何，Office 365 都需要網際網路連線。 [Office 365 IP 位址和 URL Web 服務中未包含的其他端點](additional-office365-ip-addresses-and-urls.md)中會列出需要連線的其他網路端點。

您使用 Office 365 網路端點的方式，將取決於您的企業組織網路架構。 本文概述企業網路架構可與 Office 365 IP 位址和 URL 整合的幾種方式。 選擇信任哪些網路要求的最簡單方法，就是使用在每個辦公室位置都支援自動 Office 365 設定的 SD-WAN 裝置。

## <a name="sd-wan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>重要 Office 365 網路流量的本機分支出口 SD-WAN

在每個分支辦公室位置，您可以提供設定為將 Office 365 的流量進行路由傳送的 SD-WAN 裝置，將端點的 [優化] 或 [優化] 和 [允許] 類別直接傳送至 Microsoft 的網路。 其他網路流量包括內部部署資料中心流量、一般網際網路網站流量，而連至 Office 365 [預設] 類別端點的流量會傳送到您在其中具有更實質網路周邊的另一個位置。

Microsoft 使用 SD-WAN 提供者來啟用自動設定。 如需詳細資訊，請參閱 [Office 365 網路合作夥伴計畫](microsoft-365-networking-partner-program.md)。

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>使用 PAC 檔案用於導向重要 Office 365 流量的路由

使用 PAC 或 WPAD 檔案來管理與 Office 365 相關聯但沒有 IP 位址的網路要求。 一般而言，透過 Proxy 或周邊裝置傳送的網路要求會增加延遲。 雖然 [SSL 中斷和檢查] 會造成最大的延遲，但其他服務 (例如 Proxy 驗證和信譽查閱) 可能會導致效能不佳，並產生不良的使用者體驗。 此外，這些周邊網路裝置需要足夠的容量來處理所有網路連線要求。 針對導向 Office 365 網路要求，建議略過 Proxy 或檢查裝置。
  
[PowerShell Gallery Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) 是 PowerShell 指令碼，會讀取來自 Office 365 IP 位址和 URL Web 服務的最新網路端點，並建立範例 PAC 檔案。 您可以修改指令碼，使它與您現有的 PAC 檔案管理整合。

![透過防火牆和 Proxy 連線至 Office 365。](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**圖 1 - 簡單的企業網路周邊**

PAC 檔案已在圖 1 的第 1 點部署至 Web 瀏覽器。 將 PAC 檔案用於導向重要 Office 365 網路流量的出口時，您也需要在您的網路周邊防火牆上允許連線到這些 URL 背後的 IP 位址。 方法是擷取 PAC 檔案中所指定相同的 Office 365 端點類別的 IP 位址，並根據這些位址建立防火牆 ACL。 防火牆是圖 1 中的第 3 點。

另外，如果您選擇只將 [最佳化] 類別端點直接路由，則您傳送到 Proxy 伺服器的任何必要的 [允許] 類別端點，將都必須列在 Proxy 伺服器中，才能略過進一步處理。 例如，[SSL 中斷和檢查] 與 [Proxy 驗證] 與 [最佳化] 和 [允許] 類別端點不相容。 Proxy 伺服器是圖 1 中的第 2 點。

常見的設定是針對抵達 Proxy 伺服器之 Office 365 網路流量的目的地 IP 位址，允許而不處理來自 Proxy 伺服器的所有輸出流量。 如需 [SSL 中斷和檢查] 問題的相關資訊，請參閱[對 Office 365 流量使用協力廠商網路裝置或解決方案](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365)。

Get-PacFile 指令碼將會產生兩個類型的 PAC 檔案。

| 類型 | 說明 |
|:-----|:-----|
|**1** <br/> |傳送 [最佳化] 端點流量導向，並將其餘項目傳送到 Proxy 伺服器。 <br/> |
|**2** <br/> |傳送 [最佳化] 和 [允許] 端點流量導向，並將其餘項目傳送到 Proxy 伺服器。 此類型也可以用來將所有支援的 ExpressRoute for Office 365 流量傳送到 ExpressRoute 網路區段，並將其他所有項目傳送到 Proxy 伺服器。 <br/> |

以下是呼叫 PowerShell 指令碼的簡單範例：

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

您可以傳遞至腳本的參數很多：

| 參數 | 說明 |
|:-----|:-----|
|**ClientRequestId** <br/> |這是必要項目，且是傳遞至 Web 服務的 GUID，代表正在進行呼叫的用戶端電腦。 <br/> |
|**Instance** <br/> |Office 365 服務實例，其預設為全球通用。 這也會傳遞到 web 服務。 <br/> |
|**TenantName** <br/> |您的 Office 365 租用戶名稱。 傳遞至 Web 服務，並用作某些 Office 365 URL 中的可取代參數。 <br/> |
|**Type** <br/> |您要產生的 Proxy PAC 檔案類型。 <br/> |

以下是使用其他參數呼叫 PowerShell 指令碼的另一個範例：

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>Proxy 伺服器略過處理 Office 365 網路流量

在未將 PAC 檔案用於導向輸出流量的情況下，您仍想要設定您的 Proxy 伺服器，以在周邊網路上略過處理。 部分 Proxy 伺服器廠商已啟用此功能的自動設定，如 [Office 365 網路合作夥伴計畫](microsoft-365-networking-partner-program.md)中所述。

如果您是手動執行此動作，則必須從 Office 365 IP 位址和 URL Web 服務取得 [優化] 和 [允許] 端點類別資料，並設定 proxy 伺服器以略過處理這些情況。 務必避免 [最佳化] 和 [允許] 類別端點的 [SSL 中斷和檢查] 與 [Proxy 驗證]。
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Office 365 IP 位址和 URL 的變更管理

除了為您的網路周邊選取適當的設定以外，您必須為 Office 365 端點採用變更管理程序。 這些端點會定期變更，而如果您不管理變更，在新增 IP 位址或 URL 之後，最終可能會造成使用者遭到封鎖或效能不佳。

對 Office 365 IP 位址和 URL 的變更，一般大約會在每個月的最後一天發佈。 有時候，由於營運、支援或安全性需求，變更的發佈時間可能不會按此排程進行。

當發佈的變更因為新增 IP 位址或 URL 而需要您採取動作時，您應該預期會在我們發佈該變更的時間起，收到 30 天的通知，到該端點上有 Office 365 服務為止。 雖然我們會以此通知期間為目標，但由於營運、支援或安全性需求，可能不會永遠可行。 不需要立即採取動作來維護連線的變更 (例如移除 IP 位址或 URL，或較不重要的變更)，則不會事先通知。 無論提供何種通知，我們都會列出每個變更的預期服務生效日期。

### <a name="change-notification-using-the-web-service"></a>使用 Web 服務變更通知

您可以使用「Office 365 IP 位址和 URL Web 服務」來取得變更通知。 建議您每一小時呼叫 **/version** Web 方法一次，以檢查您用來連線至 Office 365 的端點版本。 如果此版本相較於您使用的版本有所變更，則應從 **/endpoints** Web 方法取得最新的端點資料，並選擇性地從 **/changes** Web 方法取得差異。 如果您發現版本沒有任何變更，則不需要呼叫 **/endpoints** 或 **/changes** Web 方法。

如需詳細資訊，請參閱 [Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)。

### <a name="change-notification-using-rss-feeds"></a>使用 RSS 摘要變更通知

「Office 365 IP 位址和 URL Web 服務」提供可在 Outlook 中訂閱的 RSS 摘要。 在每個 Office 365 服務執行個體特定的頁面上，會提供每個 IP 位址和 URL 的 RSS URL 連結。 如需詳細資訊，請參閱 [Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)。

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>使用 Microsoft Flow 變更通知和核准檢閱

我們了解，您可能仍需要手動處理每個月會進行的網路端點變更。 您可以使用 Microsoft Flow 來建立一個流程，以透過電子郵件通知您，並在 Office 365 網路端點變更時，選擇性地針對變更執行核准程序。 檢閱完成之後，您可以讓流程自動將變更以電子郵件傳送到您的防火牆和 Proxy 伺服器管理小組。

如需 Microsoft Flow 範例和範本的相關資訊，請參閱[使用 Microsoft Flow 接收有關 Office 365 IP 位址和 URL 變更的電子郵件](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651)。
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Office 365 網路端點常見問題集

請參閱這些有關 Office 365 網路連線的常見問題。
  
### <a name="how-do-i-submit-a-question"></a>如何提交問題？

請按一下底部的連結來告訴我們文章是否有幫助，並提交任何其他問題。 我們會仔細查看意見反應，並以最常見的問題更新這裡的問題。
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>如何判斷我的租用戶位置？

 判斷 **租用戶位置** 的最佳方式是使用我們的 [資料中心地圖](https://aka.ms/datamaps)。
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>我與 Microsoft 的對等互連是否適當？

 關於 **對等互連位置**，在 [與 Microsoft 對等互連](https://www.microsoft.com/peering)中有更詳細的說明。
  
有了全球超過 2500 個 ISP 對等互連關聯性及 70 個網路節點，從您的網路連接到我們的網路應該會非常流暢。 您不妨花幾分鐘確認您 ISP 的對等互連關聯性是最佳狀態，[此處提供一些範例](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__guidance/)供您了解與我們網路的良好及不佳的對等互連遞交機制。
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>我發現網路要求的目的地 IP 位址不在已發佈清單上，我需要提供存取權給這些 IP 位址嗎？

我們只提供您應直接路由到的 Office 365 伺服器的 IP 位址。 這不是您會看到網路要求之所有 IP 位址的完整清單。 您會看到對 Microsoft 和協力廠商所擁有、未發佈之 IP 位址的網路要求。 這些 IP 位址是以動態方式產生或管理，此方式在變更時不會即時通知。 如果您的防火牆對於這些網路要求無法允許以 FQDN 為基礎的存取，請使用 PAC 或 WPAD 檔案來管理要求。
  
看到您想要取得更多資訊的 Office 365 相關聯 IP？
  
1. 使用 CIDR 計算工具 (例如用於 [IPv4](https://www.ipaddressguide.com/cidr) 或 [IPv6](https://www.ipaddressguide.com/ipv6-cidr) 的這些) 檢查 IP 位址是否包含在更大的發佈範圍中。 例如，40.96.0.0/13 會包括 IP 位址40.103.0.1，儘管 40.96 不符合40.103。
2. 使用 [whois 查詢](https://dnsquery.org/)查看合作夥伴是否擁有該 IP。 如果這是 Microsoft 所擁有，則可能是內部合作夥伴。 許多合作夥伴網路端點會列為屬於 _預設_ 類別，其中的 IP 位址並未發佈。
3. 該 IP 位址可能不屬於 Office 365 或相依性。 Office 365 網路端點發佈不包含所有 Microsoft 網路端點。
4. 請檢查憑證。 透過瀏覽器，使用 *HTTPS:// \<IP_ADDRESS\>* 連接至 IP 位址，並檢查憑證上所列的網域，以瞭解哪些網域與 IP 位址相關聯。 如果它是 Microsoft 擁有的 IP 位址，而不是在 Office 365 IP 位址清單上，則此 IP 位址可能會與 Microsoft CDN 相關聯，例如  *MSOCDN.NET*  或其他未發佈 IP 資訊的 microsoft 網域。 如果您發現憑證上的網域確實是我們宣稱有列出 IP 位址的網域，請通知我們。

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>部分 Office 365 URL 指向 CNAME 記錄，而非 DNS 中的 A 記錄。 我需要對 CNAME 記錄執行什麼動作？

用戶端電腦需要 DNS A 或 AAAA 記錄 t) hat 包含一或多個 IP 位址 (es) 才能連線至雲端服務。 Office 365 中包含的部分 URL 會顯示 CNAME 記錄，而非 A 或 AAAA 記錄。 這些 CNAME 記錄是中繼的，且在鏈結中可能會有數個。 它們會最終一律將解析為 IP 位址的 A 或 AAAA 記錄。 例如，請考慮下列 DNS 記錄系列，其最終會解析為 IP 位址 _IP_1_：

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

這些 CNAME 重新導向是 DNS 的一般部分，並且對用戶端電腦且對 Proxy 伺服器都是透明的。 它們用於負載平衡、內容傳遞網路、高可用性及服務事件緩和。 Microsoft 不會發佈中繼 CNAME 記錄，它們可能會隨時變更，而且您不應需要在您的 Proxy 伺服器中將它們設為允許。

Proxy 伺服器會驗證初始 URL，在上述範例中為 serviceA.office.com，此 URL 會包含在 Office 365 發佈中。 Proxy 伺服器會要求將該 URL 進行 DNS 解析為 IP 位址，並將接收回 IP_1。 它不會驗證中繼 CNAME 重新導向記錄。

Microsoft 不支援使用實編碼的設定或 whitelisting，而是以間接的 Office 365 Fqdn 為基礎，而且知道會造成客戶連線問題。 在 CNAME 重新導向上封鎖的 DNS 解決方案，或以其他方式錯誤解析 Office 365 DNS 專案的 DNS 解決方案，可透過已啟用 DNS 遞迴的 DNS 轉寄站或使用 DNS 根提示來加以解決。 許多協力廠商網路周邊產品會以本機方式 [，使用 office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)，將建議的 Office 365 端點 whitelisting 整合在其設定中。

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>為什麼 Microsoft 網域名稱內會有 nsatc.net 或 akadns.net 等名稱？

Office 365 及其他 Microsoft 服務使用數種協力廠商服務，例如 Akamai 和 MarkMonitor，以改善您的 Office 365 體驗。 為了持續為您提供最佳的體驗，我們日後可能會變更這些服務。 協力廠商網域可以主控內容，例如 CDN，也可以主控服務，例如地理流量管理服務。 目前使用中的部分服務包括：
  
當您看到包含 *\* nsatc.net* 的要求時， [MarkMonitor](https://www.markmonitor.com/)正在使用中。 這個服務提供網域名稱保護與監控功能，以防範惡意行為。
  
當您看到 *\* exacttarget.com* 的要求時， [ExactTarget](https://www.marketingcloud.com/)正在使用中。 這個服務提供電子郵件連結管理與監控功能，以防範惡意行為。
  
當您看到包含下列其中一個 FQDN 的要求，就表示 [Akamai](https://www.akamai.com/) 使用中。 這個服務提供地理位置 DNS 及內容傳遞網路服務。
  
```console
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net
```

<a name="bkmk_thirdparty"> </a>
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>我必須具備 Office 365 最基本的連線能力

由於 Office 365 是專為網際網路運作打造的套件，因此它所保證的可靠性與可用性，皆以許多標準網際網路服務可供使用為前提。 例如，您必須能連接到 DNS、CRL 與 CDN 等標準網際網路服務，才能使用 Office 365，這一點與您使用大部分現代網際網路服務時並無不同。

Office 365 套件可劃分成幾個主要服務領域。 您可以選擇性地為連線啟用這些功能，且有一個共同區域，也就是全部和永遠必要的功能。

| 服務區域 | 描述 |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online 和 Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online 和商務用 OneDrive <br/> |
|**商務用 Skype Online 和 Microsoft Teams** <br/> |商務用 Skype 和 Microsoft Teams <br/> |
|**通用** <br/> |Office 365 專業增強版、瀏覽器、Azure AD 及其他常見網路端點中的 Office <br/> |

除了基本網際網路服務之外，還需要一些只用於整合功能的協力廠商服務。 雖然這些是整合所需要的，但在 Office 365 端點文章中標示為選用，這表示當端點無法存取時，服務的核心功能仍可繼續運作。 任何必要的網路端點都必須將必要屬性設定為 true。 任何選用的網路端點都會將必要的屬性設定為 false，而且記事屬性將會詳細說明當連線封鎖時，應預期的遺失功能。
  
如果您嘗試使用 Office 365，而且找不到協力廠商服務可供存取，您會想要 [透過 proxy 和防火牆，確定允許所有標為必要或選用的 fqdn](urls-and-ip-address-ranges.md)。
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>如何封鎖對 Microsoft 消費者服務的存取權限？

限制存取我們的消費者服務，應由您完成且自行承擔風險。 封鎖消費者服務的唯一可靠方法是限制存取 *login.live.com* FQDN。 使用此 FQDN 的服務種類廣泛，其中包括非消費者服務，如 MSDN、TechNet 及其他服務。 這個 FQDN 也會由 Microsoft 支援服務的安全檔案交換程式所使用，且需要它才能傳輸檔案，以利於 Microsoft 產品的疑難排解。  限制對此 FQDN 的存取權可能會導致您需要包含例外規則，以處理與這些服務相關聯的網路要求。
  
請記住，只封鎖 Microsoft 消費者服務並無法防止您網路上的使用者利用 Office 365 租用戶或其他服務將資訊外流。

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>我的防火牆需要 IP 位址，且無法處理 URL。 我如何針對 Office 365 設定它？

Office 365 不會提供所有必要網路端點的 IP 位址。 某些僅提供 URL，且分類為預設。 在預設類別中 URLs 應該允許透過 proxy 伺服器的要求。 如果您沒有 proxy 伺服器，請參閱如何設定 web 要求的 URLs 使用者在網頁瀏覽器的 [位址] 欄中輸入文字。使用者也不會提供 IP 位址。 不提供 IP 位址的 Office 365 預設類別 URLs 應該以相同的方式來設定。

## <a name="related-topics"></a>相關主題

[Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)

[Microsoft Azure Datacenter IP 範圍](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft 公用 IP 空間](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Microsoft Intune 的網路基礎結構需求](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute 和 Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[Office 365 URL 和 IP 位址範圍](urls-and-ip-address-ranges.md)
  
[管理 ExpressRoute for Office 365 連線](managing-expressroute-for-connectivity.md)
  
[Office 365 網路連線原則](microsoft-365-network-connectivity-principles.md)
