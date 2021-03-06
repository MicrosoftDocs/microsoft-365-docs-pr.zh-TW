---
title: 實作 Office 365 的 VPN 分割通道
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
f1.keywords:
- NOCSH
description: 如何實作 Office 365 的 VPN 分割通道
ms.openlocfilehash: c2195eb9e3af3c591ff59d0b0f87583455b9b119
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843647"
---
# <a name="implementing-vpn-split-tunneling-for-office-365"></a>實作 Office 365 的 VPN 分割通道

>[!NOTE]
>本主題是一組針對遠端使用者處理 Office 365 最佳化的主題之一。
>- 如需使用 VPN 分割通道來最佳化遠端使用者的 Office 365 連線的概觀，請參閱[概觀：Office 365 的 VPN 分割通道](microsoft-365-vpn-split-tunnel.md)。
>- 如需針對中國使用者最佳化 Office 365 全球租用戶效能的相關資訊，請參閱 [Office 365 針對中國使用者的效能最佳化](microsoft-365-networking-china.md)。

在許多年中，企業已使用 Vpn 來支援其使用者的遠端體驗。 當核心工作負載保留於內部部署時，從遠端用戶端透過公司網路上資料中心路由傳送的 VPN 是遠端使用者存取企業資源的主要方法。 為了保護這些連線，企業會沿著 VPN 路徑建立數層的網路安全解決方案。 這項安全性是為了保護內部基礎結構，並可將流量重新路由傳送至 VPN，然後透過內部部署網際網路周邊，來保護外部網站的行動流覽。 Vpn、網路週邊和相關的安全性基礎結構通常是針對定義的流量，專門建立及調整，通常是從公司網路內部開始，大多數連線都是在內部網路界限內進行。

有好長一段時間，只要遠端使用者的並行規模適中，且周遊 VPN 的流量很低，將來自遠端使用者裝置的所有連線傳送回內部部署網路 (也稱為 **強制通道**) 的 VPN 模型多半是永續的。  即使在應用程式從公司周邊內部移至公用 SaaS 雲端之後，有些客戶能會如同現狀持續使用 VPN 強制通道，Office 365 就是主要範例。

在連線至分散式和效能相關的雲端應用程式時，使用強制隧道 Vpn 是不夠的，但是某些企業可能已接受負面影響，因此可從安全性觀點維護現狀。 以下是這種情況的範例圖表：

![分割通道 VPN 設定](../media/vpn-split-tunneling/enterprise-network-traditional.png)

此項問題已在許多年內成長，許多客戶都會報告大量的網路流量模式轉變。 用於保留內部部署的流量現在會連接至外部雲端端點。 許多 Microsoft 客戶回報其先前大約有 80% 的網路流量送至某個內部來源 (在上圖中以虛線表示)。 在 2020 年，該數字現在大約為 20% 或更低，因為他們已將主要工作負載移轉到雲端，這些趨勢在其他企業並不常見。 經過一段時間，隨著雲端旅程進展，上述模型會變得益加麻煩且不永續，並使組織在移至雲端優先的世界時不太靈活。

全球的 COVID-19 危機已使此問題提升，而需要立即補救。 為了確保員工安全的需求已經對企業 IT 支援大規模在家工作的生產力，產生了空前的需求。 Microsoft Office 365 很正確，可協助客戶滿足要求，但從家用運作的使用者的高並行性會產生大量的 Office 365 流量，如果透過強制的隧道 VPN 和內部部署網路周邊路由，則會導致快速飽和並以容量以外的速度執行 VPN 基礎結構。 在這個新的實際情況下，使用 VPN 存取 Office 365，已不再只是效能障礙，但只會影響 Office 365 但仍然必須依賴 VPN 才能運作之重要業務作業的困難牆。

多年以來，Microsoft 一直與客戶和更廣的產業密切合作，以提供自有服務內這些問題的有效、新式解決方案，並且符合業界最佳做法。 Office 365 服務的[連線原則](./microsoft-365-network-connectivity-principles.md)，旨在能針對遠端使用有效地運作，同時仍然允許組織維持安全性及控制其連線能力。 在有限的工作中，您也可以快速執行這些解決方案，但對上述問題有重大的積極影響。

Microsoft 建議用於最佳化遠端工作者連線的建議策略，著重於迅速緩解傳統方法的問題，以及透過幾個簡單步驟來提高效能。 這些步驟會調整舊版 VPN 方法，以用於略過瓶頸 VPN 伺服器的少數定義端點。 您可以在不同的層級套用同等或甚至更優越的安全性模型，以免除保護公司網路出口處所有流量的需求。 在大多數的情況下，這可在幾小時內有效地達成，而後可隨著需求與允許的時間擴展到其他工作負載。

## <a name="common-vpn-scenarios"></a>常見 VPN 案例

在下列清單中，您會看到企業環境中最常見的 VPN 案例。 大部分客戶通常採用模型 1 (VPN 強制通道)。 本節將協助您快速且安全地轉換至 **模型 2**，可透過相對的工作來獲得，並且具備網路效能和使用者經驗的大量優點。

| Model | 描述 |
| --- | --- |
| [1. VPN 強制通道](#1-vpn-forced-tunnel) | 100% 的流量進入 VPN 隧道（包括內部部署、Internet 和所有 O365/M365） |
| [2. 有少數例外狀況的 VPN 強制通道](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | 預設會使用 VPN 通道 (預設路由會指向 VPN)，具有少數允許直接前往的最重要豁免案例 |
| [3. 有廣泛例外狀況的 VPN 強制通道](#3-vpn-forced-tunnel-with-broad-exceptions) | 預設會使用 VPN 通道 (預設路由會指向 VPN)，具有允許直接前往的廣泛例外狀況 (例如所有 Office 365、所有 Salesforce、所有 Salesforce) |
| [4. VPN 選擇性通道](#4-vpn-selective-tunnel) | VPN 隧道只用于以企業為基礎的服務。 預設路由 (網際網路和所有以網際網路為基礎的服務) 都會直接進入。 |
| [5. 無 VPN](#5-no-vpn) | #2 的變化，而不是舊版 VPN，所有的公司服務都會透過新式的安全性方法發佈， (如 Zscaler ZPA、Azure Active Directory (Azure AD) Proxy/MCAS 等等。 )  |

### <a name="1-vpn-forced-tunnel"></a>1. VPN 強制通道

這是大部分企業客戶最常見的起始案例。 使用強制式 VPN，這表示，不論該端點位於公司網路內的事實，100% 的流量都會導向公司網路。 任何外部 (網際網路) 系結流量，例如 Office 365 或網際網路流覽，則會將內部部署安全性設備（如 proxy）上移出。 在目前的氣候中，以遠端方式運作的使用者幾乎100% 的使用者，此模型會將高負載放在 VPN 基礎結構上，而且可能會大幅降低所有公司流量的效能，進而讓企業在危機時有效運作。

![ VPN 強制通道模型 1](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. 具有少量信任例外狀況的 VPN 強制通道

這種模型在下列情況下會變得更有效率，因為這可讓一些控制且定義的端點非常高，且在此範例中會有非常高的負載和延遲敏感的敏感端點，以略過 VPN 隧道並直接前往 Office 365 服務。 這會大幅改善已卸載服務的效能，也會減少 VPN 基礎結構的負載，因此允許仍需要其執行的元素，以降低資源的爭奪。 本文是此模型所著重于協助您進行過渡的方式，讓您快速進行簡單、明確的動作，以提供許多積極的結果。

![分割通道 VPN 模型 2](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. 有廣泛例外狀況的 VPN 強制通道

第三個模型拓寬模型的範圍，而不只是直接傳送一小小組定義的端點直接，而是直接將所有流量傳送到信任的服務，例如 Office 365 和 SalesForce。 這會進一步減輕公司 VPN 基礎結構的負載，並改善所定義服務的效能。 因為此模型可能需要較長的時間來評估及實施，所以在今後模型2成功到位時，可能會採取重複執行的步驟。

![分割通道 VPN 模型 3](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. VPN 選擇性通道

此模型會顛覆第三個模型，在其中只會將識別為具有公司 IP 位址的流量傳送到 VPN 通道，因此網際網路路徑是其他流量的預設路由。 此模型要求組織能順利達到[零信任](https://www.microsoft.com/security/zero-trust?rtc=1)，才能安全地實作這個模型。 請注意，此模型或某些變化形式因此可能隨著時間而成為必要的預設值，而且有更多服務從公司網路移到雲端。 Microsoft 在內部使用此模型；如需有關 Microsoft 實作 VPN 分割通道的詳細資訊，請參閱[在 VPN 上執行：Microsoft 如何使遠端員工保持聯繫](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) (英文)。

![分割通道 VPN 模型 4](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. 無 VPN

更高級版本的型號，透過現代的安全性方法或 SDWAN 解決方案（如 Azure AD Proxy、MCAS、Zscaler ZPA 等）來發佈任何內部服務。

![分割通道 VPN 模型 5](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>實作 VPN 分割通道

在本節中，您將會發現將 VPN 用戶端架構從 _vpn 強制隧道_ 遷移至 _vpn 強制隧道_ 的簡單步驟，在 [通用 VPN 案例](#common-vpn-scenarios)中， [vpn 分割隧道模型 #2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) 。

下圖說明建議 VPN 分割通道解決方案的運作方式：

![分割通道 VPN 解決方案詳細資料](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. 找出要最佳化的端點

在 [的 Office 365 URL 和 IP 位址範圍](urls-and-ip-address-ranges.md)主題中，Microsoft 清楚地找出需要最佳化的重要端點，並將其分類為 **[最佳化]**。 目前只有四個 URL 和20個要優化的 IP 子網。 這一小組的端點會佔送至 Office 365 服務的 70%-80% 流量，其中包括 Teams 媒體等延遲敏感型端點的流量。 實質上，這是我們需要特別留意的流量，也是對傳統網路路徑和 VPN 基礎結構有驚人壓力的流量。

此類別中的 URL 具有下列特性：

- 是 Microsoft 所擁有和管理的端點，並且在 Microsoft 基礎結構上託管
- 已提供 IP
- 變動率很低，且應保持少量 (目前為 20 個 IP 子網路)
- 屬於頻寬和/或延遲敏感型
- 能夠擁有服務中提供 (而非內嵌在網路上) 的必要安全性元素
- 大約佔送至 Office 365 服務的 70-80% 流量

如需有關 Office 365 端點及其分類和管理方式的詳細資訊，請參閱[管理 Office 365 端點](managing-office-365-endpoints.md)。

#### <a name="optimize-urls"></a>最佳化 URL

您可以在下表中找到目前的最佳化 URL。 在大部分的情況下，您應該只需要使用[瀏覽器 PAC 檔案](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic)中的 URL 端點，這些端點會設定為直接傳送，而不會傳送到 Proxy。

| 最佳化 URL | 連接埠/通訊協定 | 用途 |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | 這是 Outlook 用來連線到 Exchange Online 伺服器的主要 URL 之一，而且有大量的頻寬使用量和連線計數。 線上功能需要低網路延遲，包括：立即搜尋、其他信箱行事曆、空閒/忙碌查閱、管理規則和警示、Exchange Online 封存、傳出寄件匣的電子郵件。 |
| <https://outlook.office.com> | TCP 443 | 此 URL 可供 Outlook Online Web Access 用來連線到 Exchange Online 伺服器，而且對於網路延遲很敏感。 透過 SharePoint Online 上傳和下載大型檔案時，尤其需要連線能力。 |
| HTTPs:// \<tenant\> 。 sharepoint.com | TCP 443 | 這是 SharePoint 線上的主要 URL，具有高頻寬使用量。 |
| HTTPs:// \<tenant\> -my.sharepoint.com | TCP 443 | 這是商務用 OneDrive 的主要 URL，具有高頻寬使用量且可能有來自商務用 OneDrive 同步工具的高連線計數。 |
| Teams 媒體 IP (無 URL) | UDP 3478、3479、3480 和 3481 | 轉送探索分配和即時流量 (3478) 、音訊 (3479) 、影片 (3480) 和影片畫面共用 (3481) 。 這兩個端點用於商務用 Skype 和 Microsoft Teams 媒體流量 (通話、會議等 ) 。 當 Microsoft Teams 用戶端建立通話 (且包含在針對服務所列的必要 IP 內) 時，就會提供大部分的端點。 使用 UDP 通訊協定才能達到最佳媒體品質。   |

在上述範例中，應使用您的 Office 365 租用戶名稱取代 **tenant**。 例如，**contoso.onmicrosoft.com** 會使用 _contoso.sharepoint.com_ 和 _constoso-my.sharepoint.com_。

#### <a name="optimize-ip-address-ranges"></a>最佳化 IP 位址範圍

在撰寫這些端點對應的 IP 範圍時，如下所示。 **強烈** 建議您使用如下的腳本：[此](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category)範例的 [Office 365 IP 及 URL web 服務](microsoft-365-ip-web-service.md)或 [url/IP 頁面](urls-and-ip-address-ranges.md)，在套用設定時檢查是否有任何更新，並將原則設定成定期執行。

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

在上述指令碼中，_$intIndex_ 是連線至網際網路的介面索引 (藉由在 PowerShell 中執行 **get-netadapter** 來尋找；尋找 _ifIndex_ 的值)，而 _$gateway_ 是該介面的預設閘道 (藉由在命令提示字元中執行 **ipconfig** 或在 PowerShell 中執行 **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop** 來尋找)。

新增路由之後，您可以在命令提示字元或 PowerShell 中執行 **route print**，以確認路由表正確無誤。 輸出應包含您所新增的路由，並顯示介面索引 (在此範例中為 _22_) 和該介面的閘道 (在此範例中為 _192.168.1.1_)：

![Route print 輸出](../media/vpn-split-tunneling/vpn-route-print.png)

若要在 [最佳化] 類別中新增 **所有** 目前 IP 位址範圍的路由，您可使用下列指令碼變化形式來查詢 [Office 365 IP 和 URL Web 服務](microsoft-365-ip-web-service.md)，以取得目前的這組最佳化 IP 子網路並將其新增到路由表中。

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

應設定 VPN 用戶端，讓送至 **[最佳化]** IP 的流量以這種方式路由傳送。 這可讓流量利用當地的 Microsoft 資源，例如 Office 365 服務前端門[（如 Azure 前端](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/)），以盡可能將 Office 365 服務和連線端點提供給使用者盡可能接近的情形。 這可讓我們在世界各地的任何地方為使用者提供高效能層級，並充分利用 [Microsoft 世界類別全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)，這可能會在您的使用者直接出局的幾毫秒內。

## <a name="configuring-and-securing-teams-media-traffic"></a>設定及保護 Teams 媒體流量

某些系統管理員可能需要更詳細的資訊，以了解通話流程如何使用分割通道模型在 Teams 中運作，以及如何保護連線的安全。

### <a name="configuration"></a>組態

若為通話和會議，只要 Teams 媒體的必要優化 IP 子網正確地放在路由表中，當 Teams 呼叫[GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute)函數來決定哪個本機介面對應到它應用於特定目的地的路由時，會針對上述 microsoft IP 區塊中的 microsoft 目的地傳回本機介面。

有些 VPN 用戶端軟體允許以 URL 為基礎的路由操作。 不過，Teams 媒體流量沒有相關聯的 URL，因此必須使用 IP 子網路來完成此流量的路由控制。

在某些情況下 (通常與 Teams 用戶端設定無關)，即使備妥正確的路由，媒體流量仍會通過 VPN 通道。 如果您遇到這種情況，則使用防火牆規則封鎖 Teams 的 IP 子網或埠應該足夠的使用。

>[!IMPORTANT]
>為了確保透過所有 VPN 案例中所需的方法來路由傳送 Teams 媒體流量，請確定使用者正在執行 Microsoft Teams 用戶端版本 **1.3.00.13565** 或更高版本。 此版本包含用戶端偵測到可用網路路徑的方式的增強功能。

信號流量是透過 HTTPS 來執行，而不是像是媒體流量機密的延遲，在 URL/IP 資料中標示為 **允許** ，因此可以視需要安全地透過 VPN 用戶端進行路由傳送。

### <a name="security"></a>安全性

避開分割通道的一個常見論點就是這麼做比較不安全，亦即 任何未通過 VPN 通道的流量都不會受益於 VPN 通道所套用的任何加密方案，因此比較不安全。

這種做法的主要反對論點就是媒體流量已經透過 _「安全即時傳輸通訊協定 (SRTP)」_ 加密，這是即時傳輸通訊協定 (RTP) 的設定檔，可為 RTP 流量提供機密性、驗證和重新執行攻擊防護。 SRTP 本身依賴隨機產生的工作階段金鑰，其透過受 TLS 保護的訊號通道進行交換。 在[這份安全性指南](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)中有詳盡的說明，但主要有趣的章節是媒體加密。

媒體流量會使用 SRTP 進行加密，其使用安全亂數產生器所產生的工作階段金鑰，並使用訊號 TLS 通道進行交換。 此外，中繼伺服器與其下一個內部躍點之間的雙向媒體流量也是使用 SRTP 來加密。

商務用 Skype Online 會產生使用者名稱/密碼，以便透過 _Traversal Using Relays around NAT (TURN)_ 安全存取媒體轉送。 媒體轉送會透過受 TLS 保護的 SIP 通道交換使用者名稱/密碼。 值得注意的是，即使 VPN 通道可用於將用戶端連線到公司網路，當流量離開公司網路以觸達服務時，仍然需要以其 SRTP 形式傳送。

有關 Teams 如何降低常見安全性考慮的資訊，例如，在 [實施程式的5.1 安全性考慮](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)中， _NAT (STUN)_ 放大攻擊可以找到。

若要了解遠距工作案例中的新式安全性控制項，也可參閱[在今日獨特的遠端工作情境中，安全專業人員與 IT 達到現代安全控制的另一種方法 (Microsoft 安全小組部落格)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (英文)。

## <a name="testing"></a>測試

準備好原則之後，您應確認其如預期般運作。 有多種方法可測試路徑是否正確設定為使用區域網際網路連線：

- 執行[Microsoft 365 連線測試](https://aka.ms/netonboard)，它會為您執行您包括上述追蹤路由的連接測試。 我們也會在將 VPN 測試新增至此工具，也應提供額外的洞察力。

- 分割通道範圍內端點的簡單追蹤應顯示所採用的路徑，例如：

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  然後，您應該會看到透過本機 ISP 對此端點的路徑，此端點應解析為已設定為分割隧道的 Teams 範圍內的 IP。

- 使用 Wireshark 等工具進行網路擷取。 在通話期間內依據 UDP 篩選，您應會看到流向 Teams **[最佳化]** 範圍中 IP 的流量。 如果 VPN 通道正使用於此流量，則不會在追蹤中顯示媒體流量。

### <a name="additional-support-logs"></a>其他支援記錄

如果需要進一步的資料疑難排解，或要求 Microsoft 支援提供協助，取得下列資訊可加快尋找解決方案的速度。 Microsoft 支援人員 **TSS Windows CMD 通用疑難排解腳本工具** 組可協助您以簡單的方式收集相關記錄檔。 您可以在以下位置找到此工具和使用指示：<https://aka.ms/TssTools.>

## <a name="howto-guides-for-common-vpn-platforms"></a>常見 VPN 平台的 HOWTO 指南

針對在這段期間內來自最常見合作夥伴的 Office 365 流量實作分割通道，本節會提供詳細指南的連結。 我們會在額外的指南可用時加以新增。

- **Windows 10 VPN 用戶端**：[使用原生 Windows 10 VPN 用戶端最佳化遠端工作人員的 Office 365 流量](/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco Anyconnect**：[針對 Office365 最佳化 Anyconnect 分割通道](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect**：[透過 VPN 分割通道排除存取路由最佳化 Office 365 流量](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 Networks BIG-IP APM**：[使用 BIG-IP APM 時透過 VPN 最佳化遠端存取上的 Office 365 流量](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365)
- **Citrix 閘道**：[針對 Office365 最佳化 Citrix 閘道的 VPN 分割通道](https://docs.citrix.com/en-us/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure**：[VPN 通道：如何設定分割通道以排除 Office365 應用程式](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **檢查點 VPN**：[如何設定 Office 365 與其他 SaaS 應用程式的分割 Tunnel](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="faq"></a>常見問題集

Microsoft 安全小組已發佈概括安全性專業人員重要方式的 [文章](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) ，以及在當今獨特的遠端工作案例中，可以取得新式的安全性控制。 此外，以下是關於此主題的一些常見客戶問題以及解答。

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>我要如何停止使用者存取我不信任的其他租用戶 (可能外洩資料)？

解答是[稱為租用戶限制的功能](/azure/active-directory/manage-apps/tenant-restrictions)。 驗證流量既不大量，也不會對延遲特別敏感，因此可透過 VPN 解決方案傳送到應用此功能的內部部署 Proxy。 在這裡維護信任承租人的允許清單，如果用戶端嘗試取得未信任之租使用者的權杖，則 proxy 只會拒絕要求。 如果租用戶受信任，且如果使用者有適當的認證和權利，就可以存取權杖。

因此，即使使用者可以對上述的優化已標示端點進行 TCP/UDP 連線，但沒有有效的權杖即可存取問題租使用者，但他們只是無法登入和存取/移動任何資料。

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>此模式是否允許存取個人 OneDrive 帳戶等消費者服務？

否，不允許，Office 365 端點與消費者服務 (例如 Onedrive.live.com) 不同，因此分割通道不會允許使用者直接存取消費者服務。 送至消費者端點的流量會繼續使用 VPN 通道，且繼續適用現有的原則。

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>當流量不再透過內部部署解決方案傳送時，如何套用 DLP 並保護我的敏感性資料？

為了協助您防止意外洩漏敏感性資訊，Office 365 提供一組豐富的[內建工具](../compliance/information-protection.md)。 您可以使用 Teams 和 SharePoint 的內建 [DLP 功能](../compliance/dlp-learn-about-dlp.md)來偵測不當儲存或共用的敏感性資訊。 如果您的部分遠端工作策略需要隨 (BYOD) 原則，您可以使用以 [應用程式為基礎的條件式存取](/azure/active-directory/conditional-access/app-based-conditional-access) ，防止敏感性資料下載至使用者的個人裝置。

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>我要如何在使用者直接連線的情況下，評估使用者的驗證及維持其控制權？

除了 Q1 所述的租用戶限制功能以外，可以套用[條件式存取原則](/azure/active-directory/conditional-access/overview)來動態評估驗證要求的風險並做出適當的反應。 Microsoft 建議在一段時間內實作[零信任模型](https://www.microsoft.com/security/zero-trust?rtc=1)，而我們可以使用 Azure AD 條件式存取原則，在行動且雲端優先的世界中維持控制權。 您可使用條件式存取原則，根據下列許多因素來對驗證要求是否成功做出即時決策：

- 裝置 – 裝置是否已知/受信任/加入網域？
- IP – 驗證要求來自已知的公司 IP 位址嗎？ 或者來自我們不信任的國家/地區？
- 應用程式 – 使用者是否已獲得使用此應用程式的授權？

然後，我們可以根據這些原則來觸發核准、觸發 MFA 或封鎖驗證等原則。

### <a name="how-do-i-protect-against-viruses-and-malware"></a>如何防禦病毒和惡意程式碼？

同樣地，Office 365 會針對服務本身不同層中標示 [最佳化] 的端點提供保護 (如[本文件概述](/office365/Enterprise/office-365-malware-and-ransomware-protection))。 如所述，在服務中提供這些安全性元素的效率會大大提高，而不是嘗試使用可能無法完全瞭解通訊協定/流量的裝置來執行。根據預設，SharePoint 線上[會自動掃描](../security/office-365-security/virus-detection-in-spo.md)檔案上傳的已知惡意程式碼

針對上述所列的 Exchange 端點， [Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)和[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)執行極佳的工作，提供服務流量的安全性。

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>我可以直接傳送除了最佳化以外的流量？

標示 **[最佳化]** 的端點應獲得優先順序，因為這些端點會為低階工作帶來最大好處。 不過，如果您願意，可使用允許標記的端點，讓服務能正常運作，並為可供必要使用的端點提供 IP 位址。

還有許多廠商提供雲端式 proxy/安全性解決方案稱為 _安全網頁閘道_ ，可提供集中式安全性、控制及公司原則應用程式，以進行一般網頁流覽。 在雲端的高可用性、高可用性及布建的情況下，這些解決方案可能會順利運作，只要允許從雲端的位置將安全的網際網路存取功能從使用者附近的位置傳遞給使用者。 這麼一來，一般瀏覽流量就不需要透過 VPN/公司網路的 U 型線路，同時仍允許集中控制安全性。

即便使用這些解決方案，Microsoft 還是強烈建議將標示 [最佳化] 的 Office 365 流量直接傳送到服務。

如需允許直接存取 Azure 虛擬網路的指引，請參閱[使用 Azure VPN 閘道點對站的遠距工作](/azure/vpn-gateway/work-remotely-support)一文。

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>為何需要連接埠 80？ 傳送的流量是否沒問題？

連接埠 80 只用於重新導向連接埠 443 工作階段之類的情況，無法透過連接埠 80 傳送或存取任何客戶資料。 [加密](../compliance/encryption.md)會概述傳輸中的資料加密，以及在靜止 Office 365 的[流量，以及流量類型的](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic)概要說明如何使用 SRTP 來保護 Teams 媒體流量。

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-office-365"></a>這項建議是否適用於使用全球 Office 365 執行個體的中國使用者？

**否**，不適用。 對上述建議提供一項警告：PRC 中連線到全球 Office 365 執行個體的使用者。 由於區域中經常發生跨境網路擁塞情況，因此直接網際網路出口效能可能變化無常。 區域中的大部分客戶都使用 VPN 運作，將流量匯入公司網路，並利用其獲得授權的 MPLS 迴路或類似於透過最佳化路徑的國家/地區外部出口。 [Office 365 針對中國使用者的效能最佳化](microsoft-365-networking-china.md)這篇文章有進一步的概括說明。

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>分割隧道設定是否適用于瀏覽器中執行的 Teams？

可以透過支援的瀏覽器，在 [[取得用戶端的 Microsoft Teams](/microsoftteams/get-clients#web-client)中列出。

## <a name="related-topics"></a>相關主題

[概觀：Office 365 的 VPN 分割通道](microsoft-365-vpn-split-tunnel.md)

[Office 365 針對中國使用者的效能最佳化](microsoft-365-networking-china.md)

[在今日獨特的遠端工作情境中，安全專業人員與 IT 達到現代安全控制的另一種方法 (Microsoft 安全小組部落格)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) (英文)

[Microsoft 強化 VPN 效能：使用 Windows 10 VPN 設定檔以允許自動連線功能](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[在 VPN 上執行：Microsoft 如何使遠端員工保持聯繫](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv) (英文)

[Office 365 網路連線原則](microsoft-365-network-connectivity-principles.md)

[評估 Office 365 的網路連線能力](assessing-network-connectivity.md)

[Office 365 網路與效能調整](network-planning-and-performance.md)
