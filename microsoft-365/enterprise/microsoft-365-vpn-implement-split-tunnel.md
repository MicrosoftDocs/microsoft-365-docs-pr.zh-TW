---
title: 實作 Office 365 的 VPN 分割通道
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/15/2020
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
f1.keywords:
- NOCSH
description: 如何實作 Office 365 的 VPN 分割通道
ms.openlocfilehash: 1fa86501e9cf29ffd41ec5b25a86cc4f2b139d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695651"
---
# <a name="implementing-vpn-split-tunneling-for-office-365"></a>實作 Office 365 的 VPN 分割通道

>[!NOTE]
>本主題是一組針對遠端使用者處理 Office 365 最佳化的主題之一。
>- 如需使用 VPN 分割通道來最佳化遠端使用者的 Office 365 連線的概觀，請參閱[概觀：Office 365 的 VPN 分割通道](microsoft-365-vpn-split-tunnel.md)。
>- 如需針對中國使用者最佳化 Office 365 全球租用戶效能的相關資訊，請參閱 [Office 365 針對中國使用者的效能最佳化](microsoft-365-networking-china.md)。

多年以來，企業一直使用 VPN 來支援其使用者的遠端體驗。 當核心工作負載保留於內部部署時，從遠端用戶端透過公司網路上資料中心路由傳送的 VPN 是遠端使用者存取企業資源的主要方法。 為了保護這些連線，企業會沿著 VPN 路徑建立數層的網路安全解決方案。 這是為了保護內部基礎結構，並將流量重新路由傳送到 VPN，然後透過內部部署網際網路周邊送出，以保護外部網站的行動流覽。 Vpn、網路週邊和相關的安全性基礎結構通常是專為定義的流量量而建立及調整，通常是從公司網路內部發起連線，而大部分連線都是在內部網路界限內進行。

有好長一段時間，只要遠端使用者的並行規模適中，且周遊 VPN 的流量很低，將來自遠端使用者裝置的所有連線傳送回內部部署網路 (也稱為**強制通道**) 的 VPN 模型多半是永續的。  即使在應用程式從公司周邊內部移至公用 SaaS 雲端之後，有些客戶能會如同現狀持續使用 VPN 強制通道，Office 365 就是主要範例。

使用強制通道 VPN 來連線到分散式和效能敏感型雲端應用程式並不太好，但是從安全性的觀點來看，有些企業可能為了維持現狀而接受了其負面影響。 以下是這種情況的範例圖表：

![分割通道 VPN 設定](../media/vpn-split-tunneling/vpn-ent-challenge.png)

此問題已在數年內持續成長，許多客戶都回報網路流量模式重大轉變。 用於保留內部部署的流量現在會連接至外部雲端端點。 許多 Microsoft 客戶回報其先前大約有 80% 的網路流量送至某個內部來源 (在上圖中以虛線表示)。 在 2020 年，該數字現在大約為 20% 或更低，因為他們已將主要工作負載移轉到雲端，這些趨勢在其他企業並不常見。 經過一段時間，隨著雲端旅程進展，上述模型會變得益加麻煩且不永續，並使組織在移至雲端優先的世界時不太靈活。

全球的 COVID-19 危機已使此問題提升，而需要立即補救。 為了確保員工安全的需求已經對企業 IT 支援大規模在家工作的生產力，產生了空前的需求。 Microsoft Office 365 非常適當的位置，可協助客戶滿足這項需求，但是從家裡運作之使用者的高併發性會產生大量的 Office 365 流量，如果透過強制的隧道 VPN 和內部部署網路周邊路由，則會產生快速的飽和，並以容量外執行 VPN 基礎結構。 在這個新的實際情況下，使用 VPN 存取 Office 365 不再只是效能障礙，但不只會影響 Office 365，但仍然必須依賴 VPN 運作之重要業務作業的硬性留言板。

多年以來，Microsoft 一直與客戶和更廣的產業密切合作，以提供自有服務內這些問題的有效、新式解決方案，並且符合業界最佳做法。 Office 365 服務的[連線原則](https://aka.ms/pnc)，旨在能針對遠端使用有效地運作，同時仍然允許組織維持安全性及控制其連線能力。 透過有限的工作也可非常迅速地實作這些解決方案，而對上述問題造成明顯的正面影響。

Microsoft 建議用於最佳化遠端工作者連線的建議策略，著重於迅速緩解傳統方法的問題，以及透過幾個簡單步驟來提高效能。 這些步驟會針對略過瓶頸 VPN 伺服器的少數定義端點，調整舊版 VPN 方法。 您可以在不同的層級套用同等或甚至更優越的安全性模型，以免除保護公司網路出口處所有流量的需求。 在大多數的情況下，這可在幾小時內有效地達成，而後可隨著需求與允許的時間擴展到其他工作負載。

## <a name="common-vpn-scenarios"></a>常見 VPN 案例

在下列清單中，您會看到企業環境中最常見的 VPN 案例。 大部分客戶通常採用模型 1 (VPN 強制通道)。 本節將協助您快速且安全地轉換至 **模型 2**，可透過相對的工作來獲得，並且具備網路效能和使用者經驗的大量優點。

| **模型** | **描述** |
| --- | --- |
| [1. VPN 強制通道](#1-vpn-forced-tunnel) | 100% 的流量進入 VPN 隧道（包括內部部署、Internet 和所有 O365/M365） |
| [2. 有少數例外狀況的 VPN 強制通道](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | 預設會使用 VPN 通道 (預設路由會指向 VPN)，具有少數允許直接前往的最重要豁免案例 |
| [3. 有廣泛例外狀況的 VPN 強制通道](#3-vpn-forced-tunnel-with-broad-exceptions) | 預設會使用 VPN 通道 (預設路由會指向 VPN)，具有允許直接前往的廣泛例外狀況 (例如所有 Office 365、所有 Salesforce、所有 Salesforce) |
| [4. VPN 選擇性通道](#4-vpn-selective-tunnel) | VPN 隧道只用于以企業為基礎的服務。 預設路由 (網際網路和所有以網際網路為基礎的服務) 都會直接進入。 |
| [5. 無 VPN](#5-no-vpn) | #2 的變化，而不是舊版 VPN，所有的公司服務都會透過新式的安全性方法發佈， (如 Zscaler ZPA、Azure Active Directory (Azure AD) Proxy/MCAS 等等。 )  |

### <a name="1-vpn-forced-tunnel"></a>1. VPN 強制通道

這是大部分企業客戶最常見的起始案例。 使用強制式 VPN，這表示，不論該端點位於公司網路內的事實，100% 的流量都會導向公司網路。 任何要送至外部 (網際網路) 的流量 (例如 Office 365 或網際網路流覽) 都會接著從內部部署安全性設備 (例如 Proxy) 反向送回。 在目前的氛圍中，有將近 100% 的使用者進行遠距工作，因此這個模型對 VPN 基礎結構帶來極高的負載，且可能會顯著阻礙所有公司流量的效能，因而讓企業在危機時刻以更有效率的方式運作。

![ VPN 強制通道模型 1](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. 具有少量信任例外狀況的 VPN 強制通道

這種模型在下列情況下會變得更有效率，因為它允許少量的受控和定義端點非常高的負載和延遲，可略過 VPN 隧道，並在此範例中直接前往 Office 365 服務。 這會大幅改善已卸載服務的效能，也會減少 VPN 基礎結構的負載，因此允許仍需要其執行的元素，以降低資源的爭奪。 本文是此模型所著重于協助您進行過渡的方式，讓您可以輕鬆進行簡單、明確的動作，以提供許多積極的結果。

![分割通道 VPN 模型 2](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. 有廣泛例外狀況的 VPN 強制通道

第三個模型拓寬模型的範圍，而不只是直接傳送一小小組定義的端點直接，而是直接傳送所有流量到受信任的服務，例如 Office 365 和 SalesForce。 這會進一步減輕公司 VPN 基礎結構的負載，並改善所定義服務的效能。 因為此模型可能需要較長的時間來評估及實施，所以在今後模型2成功到位時，可能會採取重複執行的步驟。

![分割通道 VPN 模型 3](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. VPN 選擇性通道

此模型會顛覆第三個模型，在其中只會將識別為具有公司 IP 位址的流量傳送到 VPN 通道，因此網際網路路徑是其他流量的預設路由。 此模型要求組織能順利達到[零信任](https://www.microsoft.com/security/zero-trust?rtc=1)，才能安全地實作這個模型。 請注意，此模型或某些變化形式因此可能隨著時間而成為必要的預設值，而且有更多服務從公司網路移到雲端。 Microsoft 在內部使用此模型；如需有關 Microsoft 實作 VPN 分割通道的詳細資訊，請參閱[在 VPN 上執行：Microsoft 如何使遠端員工保持聯繫](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) (英文)。

![分割通道 VPN 模型 4](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. 無 VPN

更高級版本的型號，透過現代的安全性方法或 SDWAN 解決方案（如 Azure AD Proxy、MCAS、Zscaler ZPA 等）來發佈任何內部服務。

![分割通道 VPN 模型 5](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>實作 VPN 分割通道

在本節中，您會找到將 VPN 用戶端架構從 _「VPN 強制通道」_ 遷移到 _「具有少量信任例外狀況的 VPN 強制通道」_ ([常見 VPN 案例](#common-vpn-scenarios)一節中的[VPN 分割通道模型 2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions)) 所需的簡單步驟。

下圖說明建議 VPN 分割通道解決方案的運作方式：

![分割通道 VPN 解決方案詳細資料](../media/vpn-split-tunneling/vpn-split-detail.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. 找出要最佳化的端點

在 [的 Office 365 URL 和 IP 位址範圍](urls-and-ip-address-ranges.md)主題中，Microsoft 清楚地找出需要最佳化的重要端點，並將其分類為 **[最佳化]**。 目前只有四個 URL 和二十個 IP 子網需要優化。 這一小組的端點會佔送至 Office 365 服務的 70%-80% 流量，其中包括 Teams 媒體等延遲敏感型端點的流量。 實質上，這是我們需要特別留意的流量，也是對傳統網路路徑和 VPN 基礎結構有驚人壓力的流量。

此類別中的 URL 具有下列特性：

- 是 Microsoft 所擁有和管理的端點，並且在 Microsoft 基礎結構上託管
- 已提供 IP
- 變動率很低，且應保持少量 (目前為 20 個 IP 子網路)
- 屬於頻寬和/或延遲敏感型
- 能夠擁有服務中提供 (而非內嵌在網路上) 的必要安全性元素
- 大約佔送至 Office 365 服務的 70-80% 流量

>[!NOTE]
>Microsoft 已努力暫停對 Office 365 的 **[最佳化]** 端點進行變更 (至少在 **2020 年 6 月 30 日**之前)，讓客戶能專注處理其他挑戰，而不需在最初實作後就要維護端點允許清單。 本文將會更新，以反映未來的任何變更。

如需有關 Office 365 端點及其分類和管理方式的詳細資訊，請參閱[管理 Office 365 端點](managing-office-365-endpoints.md)。

#### <a name="optimize-urls"></a>最佳化 URL

您可以在下表中找到目前的最佳化 URL。 在大部分的情況下，您應該只需要使用[瀏覽器 PAC 檔案](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)中的 URL 端點，這些端點會設定為直接傳送，而不會傳送到 Proxy。

| 最佳化 URL | 連接埠/通訊協定 | 用途 |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | 這是 Outlook 用來連線到 Exchange Online 伺服器的主要 URL 之一，而且有大量的頻寬使用量和連線計數。 線上功能需要低網路延遲，包括：立即搜尋、其他信箱行事曆、空閒/忙碌查閱、管理規則和警示、Exchange Online 封存、傳出寄件匣的電子郵件。 |
| <https://outlook.office.com> | TCP 443 | 此 URL 可供 Outlook Online Web Access 用來連線到 Exchange Online 伺服器，而且對於網路延遲很敏感。 透過 SharePoint Online 上傳和下載大型檔案時，尤其需要連線能力。 |
| HTTPs:// \<tenant\> 。 sharepoint.com | TCP 443 | 這是 SharePoint Online 的主要 URL，具有高頻寬使用量。 |
| HTTPs:// \<tenant\> -my.sharepoint.com | TCP 443 | 這是商務用 OneDrive 的主要 URL，具有高頻寬使用量且可能有來自商務用 OneDrive 同步工具的高連線計數。 |
| Teams 媒體 IP (無 URL) | UDP 3478、3479、3480 和 3481 | 轉送探索分配和即時流量 (3478) 、音訊 (3479) 、影片 (3480) 和影片畫面共用 (3481) 。 這兩個端點用於商務用 Skype 和 Microsoft 小組媒體流量 (通話、會議等等 ) 。 當 Microsoft Teams 用戶端建立通話 (且包含在針對服務所列的必要 IP 內) 時，就會提供大部分的端點。 使用 UDP 通訊協定才能達到最佳媒體品質。   |

在上述範例中，應使用您的 Office 365 租用戶名稱取代 **tenant**。 例如，**contoso.onmicrosoft.com** 會使用 _contoso.sharepoint.com_ 和 _constoso-my.sharepoint.com_。

#### <a name="optimize-ip-address-ranges"></a>最佳化 IP 位址範圍

在撰寫這些端點對應的 IP 範圍時，如下所示。 **非常強烈**建議使用[指令碼 (例如此範例)](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category)、[Office 365 IP 和 URL Web 服務](microsoft-365-ip-web-service.md)或 [URL/IP 頁面](urls-and-ip-address-ranges.md)，在套用設定時檢查是否有任何更新，並將原則設定為定期執行。

```
104.146.128.0/17
13.107.128.0/22
13.107.136.0/22
13.107.18.10/31
13.107.6.152/31
13.107.64.0/18
131.253.33.215/32
132.245.0.0/16
150.171.32.0/22
150.171.40.0/22
191.234.140.0/22
204.79.197.215/32
23.103.160.0/20
40.104.0.0/15
40.108.128.0/17
40.96.0.0/13
52.104.0.0/14
52.112.0.0/14
52.96.0.0/14
52.120.0.0/14
```

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. 透過 VPN 最佳化這些端點的存取權

既然我們已找出這些關鍵端點，我們就必須使其避開 VPN 通道，並使其能夠使用使用者的本機網際網路連線直接連線到服務。 完成此動作的方式會因所使用的 VPN 產品和電腦平台而有所不同，但大部分的 VPN 解決方案都可讓您簡單設定套用此邏輯的原則。 如需 VPN 平台專屬分割通道指引的資訊，請參閱[常見 VPN 平台的 HOWTO 指南](#howto-guides-for-common-vpn-platforms)。

如果您想要手動測試解決方案，可執行以下 PowerShell 範例，在路由表層級模擬此解決方案。 此範例會在路由表中新增每個 Teams 媒體 IP 子網路的路由。 您可以測試之前和之後的 Teams 媒體效能，並觀察所指定端點的路由差異。

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>範例：將 Teams 媒體 IP 子網路新增至路由表

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

在上述指令碼中，_$intIndex_ 是連線至網際網路的介面索引 (藉由在 PowerShell 中執行 **get-netadapter** 來尋找；尋找 _ifIndex_的值)，而 _$gateway_ 是該介面的預設閘道 (藉由在命令提示字元中執行 **ipconfig** 或在 PowerShell 中執行 **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop** 來尋找)。

新增路由之後，您可以在命令提示字元或 PowerShell 中執行 **route print**，以確認路由表正確無誤。 輸出應包含您所新增的路由，並顯示介面索引 (在此範例中為 _22_) 和該介面的閘道 (在此範例中為 _192.168.1.1_)：

![Route print 輸出](../media/vpn-split-tunneling/vpn-route-print.png)

若要在 [最佳化] 類別中新增**所有**目前 IP 位址範圍的路由，您可使用下列指令碼變化形式來查詢 [Office 365 IP 和 URL Web 服務](microsoft-365-ip-web-service.md)，以取得目前的這組最佳化 IP 子網路並將其新增到路由表中。

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>範例：將所有最佳化子網路新增至路由表

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
# Query the web service for IPs in the Optimize category
$ep = Invoke-RestMethod ("https://endpoints.office.com/endpoints/worldwide?clientrequestid=" + ([GUID]::NewGuid()).Guid)
# Output only IPv4 Optimize IPs to $optimizeIps
$destPrefix = $ep | where {$_.category -eq "Optimize"} | Select-Object -ExpandProperty ips | Where-Object { $_ -like '*.*' }
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

如果不小心使用不正確的參數新增路由，或只想還原您所做的變更，可使用下列命令來移除剛新增的路由：

```powershell
foreach ($prefix in $destPrefix) {Remove-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

<!--- remmed until we add more reliable interface selection logic
#### Example script to add Teams Media subnets to the route table

```powershell
$adapter = get-netadapter | ? {$_.Status -eq "Up"}
$adapterIndex = $adapter.ifIndex
$gateway = (Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop

$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18"
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```
-->

應設定 VPN 用戶端，讓送至 **[最佳化]** IP 的流量以這種方式路由傳送。 這可讓流量利用當地的 Microsoft 資源，例如 Office 365 服務前端門 [（如 Azure 前端](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) ），以盡可能提供 office 365 服務和連線端點，以盡可能接近您的使用者。 如此一來，我們就能為世界各地的使用者提供極高的效能等級，並充分利用 [Microsoft 的世界級全球網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)，這種情況很可能在使用者直接出口的短短幾毫秒內發生。

## <a name="configuring-and-securing-teams-media-traffic"></a>設定及保護 Teams 媒體流量

某些系統管理員可能需要更詳細的資訊，以了解通話流程如何使用分割通道模型在 Teams 中運作，以及如何保護連線的安全。

### <a name="configuration"></a>組態

在通話和會議中，只要 Teams 媒體所需的最佳化 IP 子網路正確地放在路由表中，當 Teams 呼叫 _GetBestRoute_ 方法來判斷其應該針對特定目的地所使用的介面時，系統就會針對以上所列的 Microsoft IP 區塊中的 Microsoft 目的地傳回本機介面。

有些 VPN 用戶端軟體允許以 URL 為基礎的路由操作。 不過，Teams 媒體流量沒有相關聯的 URL，因此必須使用 IP 子網路來完成此流量的路由控制。

在某些情況下 (通常與 Teams 用戶端設定無關)，即使備妥正確的路由，媒體流量仍會通過 VPN 通道。 如果遇到這種情況，則使用防火牆規則來封鎖 Teams IP 子網路或連接埠，使其無法使用 VPN 應該就夠了。

>[!IMPORTANT]
>為了確保小組媒體流量透過所有 VPN 案例中所需的方法來路由傳送，請確定使用者執行的是 Microsoft 團隊用戶端版本 **1.3.00.13565** 或更高版本。 此版本包含用戶端偵測到可用網路路徑的方式的增強功能。

信號流量是透過 HTTPS 來執行，而不是像是媒體流量機密的延遲，在 URL/IP 資料中標示為 **允許** ，因此可以視需要安全地透過 VPN 用戶端進行路由傳送。

### <a name="security"></a>安全性

避開分割通道的一個常見論點就是這麼做比較不安全，亦即 任何未通過 VPN 通道的流量都不會受益於 VPN 通道所套用的任何加密方案，因此比較不安全。

這種做法的主要反對論點就是媒體流量已經透過 _「安全即時傳輸通訊協定 (SRTP)」_ 加密，這是即時傳輸通訊協定 (RTP) 的設定檔，可為 RTP 流量提供機密性、驗證和重新執行攻擊防護。 SRTP 本身依賴隨機產生的工作階段金鑰，其透過受 TLS 保護的訊號通道進行交換。 在[這份安全性指南](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)中有詳盡的說明，但主要有趣的章節是媒體加密。

媒體流量會使用 SRTP 進行加密，其使用安全亂數產生器所產生的工作階段金鑰，並使用訊號 TLS 通道進行交換。 此外，中繼伺服器與其下一個內部躍點之間的雙向媒體流量也是使用 SRTP 來加密。

商務用 Skype Online 會產生使用者名稱/密碼，以便透過 _Traversal Using Relays around NAT (TURN)_ 安全存取媒體轉送。 媒體轉送會透過受 TLS 保護的 SIP 通道交換使用者名稱/密碼。 值得注意的是，即使 VPN 通道可用於將用戶端連線到公司網路，當流量離開公司網路以觸達服務時，仍然需要以其 SRTP 形式傳送。

有關 Teams 如何降低常見安全性疑慮 (例如語音或 _Session Traversal Utilities for NAT (STUN)_ 放大攻擊) 的資訊，請參閱[這篇文章](https://docs.microsoft.com/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)。

若要了解遠距工作案例中的新式安全性控制項，也可參閱[在今日獨特的遠端工作情境中，安全專業人員與 IT 達到現代安全控制的另一種方法 (Microsoft 安全小組部落格)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (英文)。

## <a name="testing"></a>測試

準備好原則之後，您應確認其如預期般運作。 有多種方法可測試路徑是否正確設定為使用區域網際網路連線：

- 執行 [Microsoft 365 連線測試](https://aka.ms/netonboard) ，它會為您執行您包括上述追蹤路由的連接測試。 我們也會在將 VPN 測試新增至此工具，也應提供額外的洞察力。

- 分割通道範圍內端點的簡單追蹤應顯示所採用的路徑，例如：

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  然後，您應該會看到透過本機 ISP 對此端點的路徑，此端點應解析為已設定分割隧道的小組範圍中的 IP。

- 使用 Wireshark 等工具進行網路擷取。 在通話期間內依據 UDP 篩選，您應會看到流向 Teams **[最佳化]** 範圍中 IP 的流量。 如果 VPN 通道正使用於此流量，則不會在追蹤中顯示媒體流量。

### <a name="additional-support-logs"></a>其他支援記錄

如果需要進一步的資料疑難排解，或要求 Microsoft 支援提供協助，取得下列資訊可加快尋找解決方案的速度。 Microsoft 支援的 **TSS WINDOWS CMD 通用疑難排解腳本工具** 組可協助您以簡單的方式收集相關記錄檔。 您可以在以下位置找到此工具和使用指示：<https://aka.ms/TssTools.>

## <a name="howto-guides-for-common-vpn-platforms"></a>常見 VPN 平台的 HOWTO 指南

針對在這段期間內來自最常見合作夥伴的 Office 365 流量實作分割通道，本節會提供詳細指南的連結。 我們會在額外的指南可用時加以新增。

- **Windows 10 VPN 用戶端**：[使用原生 Windows 10 VPN 用戶端最佳化遠端工作人員的 Office 365 流量](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco Anyconnect**：[針對 Office365 最佳化 Anyconnect 分割通道](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect**：[透過 VPN 分割通道排除存取路由最佳化 Office 365 流量](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 Networks BIG-IP APM**：[使用 BIG-IP APM 時透過 VPN 最佳化遠端存取上的 Office 365 流量](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365)
- **Citrix 閘道**：[針對 Office365 最佳化 Citrix 閘道的 VPN 分割通道](https://docs.citrix.com/en-us/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure**：[VPN 通道：如何設定分割通道以排除 Office365 應用程式](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **檢查點 VPN**： [如何設定 Office 365 和其他 SaaS 應用程式的分割隧道](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="faq"></a>常見問題集

Microsoft 安全小組已發佈概括安全性專業人員重要方式的 [文章](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) ，以及在當今獨特的遠端工作案例中，可以取得新式的安全性控制。 此外，以下是關於此主題的一些常見客戶問題以及解答。

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>我要如何停止使用者存取我不信任的其他租用戶 (可能外洩資料)？

解答是[稱為租用戶限制的功能](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)。 驗證流量既不大量，也不會對延遲特別敏感，因此可透過 VPN 解決方案傳送到應用此功能的內部部署 Proxy。 在這裡維護信任承租人的允許清單，如果用戶端嘗試取得未信任之租使用者的權杖，則 proxy 只會拒絕要求。 如果租用戶受信任，且如果使用者有適當的認證和權利，就可以存取權杖。

因此，即使使用者可對以上標示 [最佳化] 的端點進行 TCP/UDP 連線，若沒有有效的權杖可存取有問題的租用戶，使用者就無法登入及存取/移動任何資料。

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>此模式是否允許存取個人 OneDrive 帳戶等消費者服務？

否，不允許，Office 365 端點與消費者服務 (例如 Onedrive.live.com) 不同，因此分割通道不會允許使用者直接存取消費者服務。 送至消費者端點的流量會繼續使用 VPN 通道，且繼續適用現有的原則。

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>當流量不再透過內部部署解決方案傳送時，如何套用 DLP 並保護我的敏感性資料？

為了協助您防止意外洩漏敏感性資訊，Office 365 提供一組豐富的[內建工具](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)。 您可以使用 Teams 和 SharePoint 的內建 [DLP 功能](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)來偵測不當儲存或共用的敏感性資訊。 如果您的部分遠端工作策略需要隨 (BYOD) 原則，您可以使用以 [應用程式為基礎的條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) ，防止敏感性資料下載至使用者的個人裝置。

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>我要如何在使用者直接連線的情況下，評估使用者的驗證及維持其控制權？

除了 Q1 所述的租用戶限制功能以外，可以套用[條件式存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)來動態評估驗證要求的風險並做出適當的反應。 Microsoft 建議在一段時間內實作[零信任模型](https://www.microsoft.com/security/zero-trust?rtc=1)，而我們可以使用 Azure AD 條件式存取原則，在行動且雲端優先的世界中維持控制權。 您可使用條件式存取原則，根據下列許多因素來對驗證要求是否成功做出即時決策：

- 裝置 – 裝置是否已知/受信任/加入網域？
- IP – 驗證要求來自已知的公司 IP 位址嗎？ 或者來自我們不信任的國家/地區？
- 應用程式 – 使用者是否已獲得使用此應用程式的授權？

然後，我們可以根據這些原則來觸發核准、觸發 MFA 或封鎖驗證等原則。

### <a name="how-do-i-protect-against-viruses-and-malware"></a>如何防禦病毒和惡意程式碼？

同樣地，Office 365 會針對服務本身不同層中標示 [最佳化] 的端點提供保護 (如[本文件概述](https://docs.microsoft.com/office365/Enterprise/office-365-malware-and-ransomware-protection))。 如所述，在服務中提供這些安全性元素的效率會更高，而不是嘗試使用可能不會完全瞭解通訊協定/流量的裝置來執行。根據預設，SharePoint 線上 [會自動掃描](https://docs.microsoft.com/microsoft-365/security/office-365-security/virus-detection-in-spo?view=o365-worldwide) 檔案上傳的已知惡意程式碼

針對以上所列的 Exchange 端點，[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 和 [Office 365 進階威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)都擅於提供送至服務的流量安全性。

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>我可以直接傳送除了最佳化以外的流量？

標示 **[最佳化]** 的端點應獲得優先順序，因為這些端點會為低階工作帶來最大好處。 不過，如果您願意，服務必須具有標記的端點，才能正常運作，並為可用於必要的端點提供 IPs。

另外，也有許多廠商提供雲端式 proxy/安全性解決方案稱為安全網頁閘道，可提供集中式安全性、控制及公司原則應用程式，以供一般 web 流覽之用。 在雲端的高可用性、高可用性及布建的情況下，這些解決方案可能會順利運作，只要允許從雲端的位置將安全的網際網路存取功能從使用者附近的位置傳遞給使用者。 這麼一來，一般瀏覽流量就不需要透過 VPN/公司網路的 U 型線路，同時仍允許集中控制安全性。

即便使用這些解決方案，Microsoft 還是強烈建議將標示 [最佳化] 的 Office 365 流量直接傳送到服務。

如需允許直接存取 Azure 虛擬網路的指引，請參閱[使用 Azure VPN 閘道點對站的遠距工作](https://docs.microsoft.com/azure/vpn-gateway/work-remotely-support)一文。

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>為何需要連接埠 80？ 傳送的流量是否沒問題？

連接埠 80 只用於重新導向連接埠 443 工作階段之類的情況，無法透過連接埠 80 傳送或存取任何客戶資料。 [這篇文章](https://docs.microsoft.com/microsoft-365/compliance/encryption?view=o365-worldwide)概述 Office 365 的傳輸中資料和待用資料加密，而[這篇文章](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic)概述我們如何使用 SRTP 來保護 Teams 媒體流量。

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-office-365"></a>這項建議是否適用於使用全球 Office 365 執行個體的中國使用者？

**否**，不適用。 對上述建議提供一項警告：PRC 中連線到全球 Office 365 執行個體的使用者。 由於區域中經常發生跨境網路擁塞情況，因此直接網際網路出口效能可能變化無常。 區域中的大部分客戶都使用 VPN 運作，將流量匯入公司網路，並利用其獲得授權的 MPLS 迴路或類似於透過最佳化路徑的國家/地區外部出口。 [Office 365 針對中國使用者的效能最佳化](microsoft-365-networking-china.md)這篇文章有進一步的概括說明。

## <a name="related-topics"></a>相關主題

[概觀：Office 365 的 VPN 分割通道](microsoft-365-vpn-split-tunnel.md)

[Office 365 針對中國使用者的效能最佳化](microsoft-365-networking-china.md)

[在今日獨特的遠端工作情境中，安全專業人員與 IT 達到現代安全控制的另一種方法 (Microsoft 安全小組部落格)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (英文)

[Microsoft 強化 VPN 效能：使用 Windows 10 VPN 設定檔以允許自動連線功能](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[在 VPN 上執行：Microsoft 如何使遠端員工保持聯繫](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) (英文)

[Office 365 網路連線原則](microsoft-365-network-connectivity-principles.md)

[評估 Office 365 的網路連線能力](assessing-network-connectivity.md)

[Office 365 網路與效能調整](network-planning-and-performance.md)
