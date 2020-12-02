---
title: Microsoft 365 網路連線原則
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
search.appverid: MET150
ms.assetid: 76e7f232-917a-4b13-8fe2-4f8dbccfe041
f1.keywords:
- NOCSH
description: 本文提供安全地最佳化 Microsoft 365 網路連線的最新指導方針。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a6f104f53abd0a9aa2376b09c93af96d7f8178e8
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519736"
---
# <a name="microsoft-365-network-connectivity-principles"></a>Microsoft 365 網路連線原則

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

在您開始為 Microsoft 365 網路連線規劃網路之前，務必了解安全管理 Microsoft 365 流量以及可能獲取最佳效能的連線原則。 本文將會協助您了解關於安全最佳化 Microsoft 365 網路連線的最新指引。
  
傳統企業網路的主要設計目的，是為使用者提供應用程式和資料 (裝載於公司運作的資料中心) 的存取權，同時具有強式周邊網路安全性。 傳統模型假設使用者是從公司網路周邊網路內部存取應用程式和資料，透過分公司的 WAN 連結，或是透過 VPN 連線遠端存取。
  
採用像是 Microsoft 365 的 SaaS 應用程式，會將某些服務和資料組合移到網路周邊之外。 若沒有最佳化，使用者與 SaaS 應用程式之間的流量會受限於封包檢查、網路 hairpin、與遠距端點的不當連線和其他因素所引入的延遲。 您可以藉由了解和實作關鍵最佳化指引，確保最佳的 Microsoft 365 效能和可靠性。
  
在本文中，您將了解：
  
- 套用至客戶雲端連線時的 [Microsoft 365 架構](microsoft-365-network-connectivity-principles.md#BKMK_Architecture)
- 更新的 [Microsoft 365 連線原則](microsoft-365-network-connectivity-principles.md#BKMK_Principles)，以及最佳化網路流量和終端使用者體驗的策略
- [Office 365 端點 Web 服務](microsoft-365-network-connectivity-principles.md#BKMK_WebSvc)，允許網路系統管理員在網路最佳化中使用端點的結構化清單
- [新的 Office 365 端點類別](microsoft-365-network-connectivity-principles.md#BKMK_Categories)以及最佳化指引
- [比較網路周邊網路安全性與端點安全性](microsoft-365-network-connectivity-principles.md#BKMK_SecurityComparison)
- 針對 Microsoft 365 流量的[增量最佳化](microsoft-365-network-connectivity-principles.md#BKMK_IncOpt)選項
- [Microsoft 365 連線測試](https://aka.ms/netonboard)，是一種用來測試 Microsoft 365 基本連線能力的新工具

## <a name="microsoft-365-architecture"></a>Microsoft 365 架構
<a name="BKMK_Architecture"> </a>

Microsoft 365 是分散式軟體即服務 (SaaS) 雲端，透過微服務和應用程式 (例如 Exchange Online、SharePoint Online、商務用 Skype Online、Microsoft Teams、Exchange Online Protection、Office 網頁版等等) 的多元組合，提供生產力和共同作業案例。 雖然特定 Microsoft 365 應用程式在套用至客戶網路以及連線到雲端時，有其獨特的功能，它們都共用一些主要原則、目標和架構模式。 這些連線的原則和架構模式通常適用於其他許多 SaaS 雲端，同時與平台即服務和基礎結構即服務雲端 (例如 Microsoft Azure) 的典型部署模型也有所不同。
  
Microsoft 365 的其中一個最重要架構功能 (經常遭到網路架構遺漏或錯誤解譯) 是在使用者連線方式內容中真正的全域分散式服務。 目標 Microsoft 365 租用戶的位置對於了解客戶資料儲存在雲端內哪個位置而言相當重要，但是使用者的 Microsoft 365 體驗並未涉及到直接與包含資料的磁碟連線。 使用者的 Microsoft 365 體驗 (包括效能、可靠性和其他重要的品質特性) 牽涉到透過高度分散前門服務 (在全球數百個 Microsoft 位置之間相應放大) 的連線。 在大多數情況下，可以藉由允許客戶網路將使用者要求路由傳送到最接近的 Microsoft 365 服務進入點，而無須透過中央位置或區域的出口點連線到 Microsoft 365，達到最佳的使用者體驗。
  
對於大多數客戶而言，Microsoft 365 使用者分散在許多位置之間。 若要達到最佳結果，應該從相應放大 (而非相應增加) 觀點來看本文件中所概述的原則，著重在將連線最佳化到 Microsoft 全域網路所在位置的最接近點，而不是 Microsoft 365 租用戶的地理位置。 基本上，這表示即使 Microsoft 365 租用戶資料儲存在特定地理位置，該租用戶的 Microsoft 365 體驗仍是分散，並且可以出現在與租用戶具有的每個終端使用者位置非常靠近 (網路) 的位置。
  
## <a name="microsoft-365-connectivity-principles"></a>Microsoft 365 連線原則
<a name="BKMK_Principles"> </a>

Microsoft 建議下列原則，以達到最佳的 Microsoft 365 連線和效能。 使用這些 Microsoft 365 連線原則，在連線到 Microsoft 365 時，管理您的流量並取得最佳效能。
  
網路設計的主要目標應該是透過降低從您的網路到 Microsoft 全域網路、Microsoft 公用網路骨幹 (將所有低延遲 Microsoft 資料中心與遍佈全球的雲端應用程式進入點互連) 的來回行程時間 (RTT)，將延遲降至最低。 您可以在 [Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) 中，深入了解 Microsoft 全域網路。
  
<a name="BKMK_P1"> </a>
### <a name="identify-and-differentiate-microsoft-365-traffic"></a>識別並區分 Microsoft 365 流量

![識別 Microsoft 365 流量](../media/621aaec9-971d-4f19-907a-1ae2ef6d72fc.png)
  
識別 Microsoft 365 網路流量是能夠區分來自一般網際網路綁定網路流量的第一步。 Microsoft 365 連線可以藉由實作方法的組合 (例如網路路由最佳化、防火牆規則、瀏覽器 Proxy 設定以及略過特定端點的網路檢查裝置等方法)，來達到最佳化。
  
先前的 Microsoft 365 最佳化指引是將 Microsoft 365 端點分成兩個類別，**必要** 和 **選擇性**。 隨著端點新增支援新的 Microsoft 365 服務和功能，我們已經將 Microsoft 365 端點重新組織為三個類別：**最佳化**、**允許** 和 **預設**。 每個類別的指導方針都適用於該類別的所有端點，讓最佳化更易於了解及實作。
  
如需 Microsoft 365 端點類別和最佳化方法的詳細資訊，請參閱[新 Office 365 端點類別](microsoft-365-network-connectivity-principles.md#BKMK_Categories)一節。
  
Microsoft 現在會將所有 Microsoft 365 端點發佈為網頁服務，並且提供如何最佳地使用此資料的指引。 如需如何取得及使用 Microsoft 365 端點的詳細資訊，請參閱 [Office 365 URL 和 IP 位址範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)一文。
  
<a name="BKMK_P2"> </a>
### <a name="egress-network-connections-locally"></a>在當地輸出網路連線

![在當地輸出網路連線](../media/b42a45be-1ab4-4073-a7dc-fbdfb4aedd24.png)
  
本機 DNS 和網際網路出口對於降低連線延遲，及確保使用者連線連至與 Microsoft 365 服務最接近的進入點，相當重要。 在複雜的網路拓撲中。同時實作本機 DNS 和本機網際網路出口相當重要。 如需 Microsoft 365 如何將用戶端連線路由傳送到最接近進入點的詳細資訊，請參閱[用戶端連線能力](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) 一文。
  
在諸如 Microsoft 365 的雲端服務問世之前，終端使用者網際網路連線能力作為網路架構中的設計因素而言，相對簡單。 當網際網路服務和網站散佈在全球各地時，公司出口點與任何指定目的地端點之間的延遲，成為地理距離很大的函數。
  
在傳統的網路架構中，所有輸出網際網路連線會周遊公司網路，然後從中央位置出口。 隨著 Microsoft 的雲端供應項目成熟，分散式網際網路對應網路架構對於支援延遲敏感雲端服務變得關鍵。 Microsoft 全域網路的設計目的是透過分散式服務 Front Door 基礎結構 (這是一個動態全域進入點網狀架構，將輸入雲端服務連線路由傳送到最接近的進入點) 來容納延遲需求。 目的在於藉由縮短客戶與雲端之間的路由，為 Microsoft 雲端客戶減少「最後一步」的長度。
  
企業 WAN 通常設計為將網路流量回傳到中央總公司，在出口到網際網路之前進行檢查，通常是透過一或多個 Proxy 伺服器。 下圖說明此類網路拓撲。
  
![傳統企業網路模型](../media/fc87b8fd-a191-47a7-9704-1e445599813a.png)
  
因為 Microsoft 365 是在 Microsoft 全域網路 (其中包含遍佈全球的前端伺服器) 上執行，所有通常會有接近使用者位置的前端伺服器。 藉由提供本機網際網路出口，以及設定內部 DNS 伺服器以提供 Microsoft 365 端點的本機名稱解析，目的地為 Microsoft 365 的網路流量可以連線到盡可能接近使用者的 Microsoft 365 前端伺服器。 下圖顯示網路拓撲範例，使得從總公司、分公司及遠端位置連線的使用者，可以依照最接近 Microsoft 365 進入點的最短路由。
  
![具有區域出口點的 WAN 網路模型](../media/4d4c07cc-a928-42b8-9a54-6c3741380a33.png)
  
以這個方式縮短到 Microsoft 365 進入點的網路路徑，可以改善 Microsoft 365 的連線效能和使用者體驗，也可以協助降低未來對於 Microsoft 365 效能和可靠性在網路架構變更所受到的影響。
  
此外，如果回應 DNS 伺服器是遠距或忙碌中，則 DNS 要求會導致延遲。 您可以藉由在分公司位置佈建本機 DNS 伺服器，並且確定這些伺服器已設定為適當地快取 DNS 記錄，將名稱解析延遲降至最低。
  
雖然區域出口針對 Microsoft 365 可以運作良好，最佳的連線模型應該是一律在使用者的位置提供網路出口，無論這是公司網路或遠端位置，例如住家、旅館、咖啡廳或機場。 下圖呈現這個本機直接出口模型。
  
![本機出口網路架構](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)
  
已採用 Microsoft 365 的企業可以透過確定使用者與 Microsoft 365 的連線是採取與最接近 Microsoft 全域網路進入點的可能最短路由，利用 Microsoft 全域網路的分散式前門服務架構。 本機出口網路架構是藉由允許 Microsoft 365 流量透過最接近的出口 (無論使用者位置在哪裡) 進行路由傳送，來達到這個目的。
  
本機出口架構相較於傳統模型，具有以下優點：
  
- 藉由最佳化路由長度，提供最佳的 Microsoft 365 效能。 終端使用者連線是由分散式前門服務基礎結構，動態地路由傳送到最接近的 Microsoft 365 進入點。
- 藉由允許本機出口，降低公司網路基礎結構的負載。
- 藉由利用用戶端端點安全性和雲端安全性功能，保護兩個端點的連線。

<a name="BKMK_P3"> </a>
### <a name="avoid-network-hairpins"></a>避免網路 hairpin

![避免 hairpin](../media/ee53e8af-f57b-4292-a256-4f36733b263a.png)
  
根據一般經驗法則，使用者與最接近 Microsoft 365 端點之間的最短、最直接路由，可以提供最佳效能。 當前往特定目的地的 WAN 或 VPN 流量首先導向到另一個中間位置 (例如雲端型 Web 閘道的安全性堆疊、雲端存取代理程式) 時，會發生網路 hairpin，導致延遲並且可能重新導向至遠距端點。 網路 hairpin 也可能由於路由/對等互連不足或次佳 (遠端) DNS 查閱所導致。
  
若要確保 Microsoft 365 連線即使在本機出口案例中也不會受限於網路 hairpin，請檢查用來為使用者位置提供網際網路出口的 ISP，是否具有與該位置近接 Microsoft 全域網路的直接對等互連關係。 您也會想要將出口路由設定為直接傳送信任的 Microsoft 365 流量，而不是透過處理網際網路流量的第三方雲端或雲端型網路安全性廠商來進行 Proxy 處理或通道傳送。 Microsoft 365 端點的本機 DNS 名稱解析會協助確定除了直接路由之外，也為使用者連線使用最接近的 Microsoft 365 進入點。
  
如果您將雲端型網路或安全性服務用於您的 Microsoft 365 流量，請確定已評估 hairpin 效果，並了解它對 Microsoft 365 效能的影響。 可以藉由檢查服務提供者位置 (流量經由這些位置轉送) 的數量和位置，與您的分公司和 Microsoft 全域網路對等互連點的關係、服務提供者與您的 ISP 和 Microsoft 的網路對等互連關係品質，以及服務提供者基礎結構回傳的效能影響，來完成這項操作。
  
由於 Microsoft 365 進入點及其使用者近接的分散式位置數量相當大，所有將 Microsoft 365 流量路由傳送到任何第三方網路或安全性提供者時，如果提供者網路未針對最佳化 Microsoft 365 對等互連進行設定，則對於 Microsoft 365 連線會有負面影響。
  
<a name="BKMK_P4"> </a>
### <a name="assess-bypassing-proxies-traffic-inspection-devices-and-duplicate-security-technologies"></a>評估略過 Proxy、流量檢查裝置和重複安全性技術

![略過 Proxy、流量檢查裝置和重複安全性技術](../media/0131930d-c6cb-4ae1-bbff-fe4cf6939a23.png)
  
企業客戶應該特別針對 Microsoft 365 繫結流量檢閱他們的網路安全性和降低風險方法，並且使用 Microsoft 365 安全性功能來降低對於 Microsoft 365 網路流量干擾、效能影響及昂貴網路安全性技術的依賴。
  
大部分企業網路會針對使用如 Proxy、SSL 檢查、封包檢查及資料外洩防護系統等技術的網際網路流量，強制執行網路安全性。 這些技術為一般網際網路要求提供重要的風險降低，但是當套用至 Microsoft 365 端點時，可能會大幅降低效能、延展性和使用者體驗的品質。
  
<a name="BKMK_WebSvc"> </a>
#### <a name="office-365-endpoints-web-service"></a>Office 365 端點 Web 服務

Microsoft 365 系統管理員可以使用指令碼或 REST 呼叫，使用來自 Office 365 端點 Web 服務的結構化清單，並且更新周邊防火牆和其他網路裝置的組態。 這樣可確保前往 Microsoft 365 的流量得以識別、適當地進行處理，並且以不同於前往一般且通常未知網際網路網站的網路流量方式進行管理。 如需如何使用 Office 365 端點 Web 服務的詳細資訊，請參閱 [Office 365 URL 和 IP 位址範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)一文。
  
#### <a name="pac-proxy-automatic-configuration-scripts"></a>PAC (Proxy 自動設定) 指令碼
<a name="BKMK_WebSvc"> </a>

Microsoft 365 系統管理員可以建立 PAC (Proxy 自動設定) 指令碼，透過 WPAD 或 GPO 傳遞給使用者電腦。 PAC 指令碼可以用來針對來自 WAN 或 VPN 使用者的 Microsoft 365 要求略過 Proxy，讓 Microsoft 365 流量使用直接網際網路連線，而不是周遊公司網路。
  
#### <a name="microsoft-365-security-features"></a>Microsoft 365 安全性功能
<a name="BKMK_WebSvc"> </a>

Microsoft 對於 Microsoft 365 伺服器和它們所呈現網路端點相關的資料中心安全性、運作安全性和風險降低是透明的。 Microsoft 365 內建安全性功能可用於降低網路安全性風險，例如資料外洩防護、防毒、Multi-Factor Authentication、Customer Lock Box、適用於 Office 365 的 Defender、Microsoft 365 威脅情報、Microsoft 365 安全分數、Exchange Online Protection 及 Network DDOS Security。
  
如需 Microsoft 資料中心和全域網路安全性的詳細資訊，請參閱 [Microsoft 信任中心](https://www.microsoft.com/trustcenter/security)。
  
## <a name="new-office-365-endpoint-categories"></a>新的 Office 365 端點類別
<a name="BKMK_Categories"> </a>

Office 365 端點代表不同的網路位址和子網路集合。 端點可能是 URL、IP 位址或 IP 範圍，部分端點與特定 TCP/UDP 連接埠一起列出。 URL 可以是 FQDN，例如 *account.office.net*，或是萬用字元 URL，例如 *\*.office365.com*。
  
> [!NOTE]
> 網路內 Office 365 端點的位置不會直接與 Microsoft 365 租用戶資料的位置相關。 基於這個原因，客戶應該將 Microsoft 365 視為分散式和全域服務，不應該嘗試根據地理準則封鎖與 Office 365 端點的網路連線。
  
在我們先前針對管理 Microsoft 365 流量的指引中，端點組織為兩個類別，**必要** 和 **選擇性**。 根據服務嚴重性的不同，每個類別中的端點所需的最佳化也不同，許多客戶在將相同網路最佳化應用到 Office 365 URL 和 IP 位址完整清單時面臨了挑戰。
  
在新的模型中，端點分為三個類別，**最佳化**、**允許** 和 **預設**，提供優先順序型樞紐，讓使用者知道要將網路最佳化努力焦點放在哪裡，以便實現最佳效能改善並且獲得投資回報。 端點會根據網路品質、案例的數量和效能封套，以及簡化實作的有效使用者體驗敏感度，合併到上述類別中。 建議的最佳化可以相同方式套用到指定類別中的所有端點。
  
- **最佳化** 端點是連線至每個 Office 365 服務所需的端點，並代表超過 75% 的 Office 365 頻寬、連線和資料量。 這些端點代表對網路效能、延遲和可用性最敏感的 Office 365 案例。 所有端點都裝載於 Microsoft 資料中心。 此類別中端點的變更率預期遠比其他兩個類別中的端點低。 此類別包含小型 (順序為 ~10) 的主要 URL 組合和已定義 IP 子網路組合，專用於核心 Office 365 工作負載，例如 Exchange Online、SharePoint Online、商務用 Skype Online 及 Microsoft Teams。

    一份定義好的重要端點精簡清單，應該能協助您更快且更容易為這些目的地規劃並實作大量網路最佳化。

    *「最佳化」* 端點範例包含 *https://outlook.office365.com*、*https://\<tenant\>.sharepoint.com* 和 *https://\<tenant\>-my.sharepoint.com*。

    最佳化方法包括：

  - 略過網路裝置和服務 (執行流量攔截、SSL 解密、深入封包檢查及內容篩選)的 *「最佳化」* 端點。
  - 略過通常用於一般網際網路瀏覽的內部部署 Proxy 裝置和雲端型 Proxy 服務。
  - 優先評估您的網路基礎結構和周邊系統完全信任的這些端點。
  - 優先降低或消除 WAN 回傳，並且輔助這些端點使用盡可能接近使用者/分公司位置的直接分散式網際網路型出口。
  - 藉由實作分割通道，為 VPN 使用者促成與這些雲端端點的直接連線。
  - 確定 DNS 名稱解析所傳回的 IP 位址符合這些端點的路由出口路徑。
  - 優先處理這些端點的 SD-WAN 整合，以取得進入 Microsoft 全域網路最接近網際網路對等互連點的直接、最低延遲路由。

- **「允許」** 端點是連線至特定 Microsoft 365 服務與功能所需的端點，但對網路效能和延遲不如 *「最佳化」* 類別中的項目敏感。 從頻寬和連線計數立場而言，這些端點的整體網路佔用空間也較小。 這些端點是專用於 Office 365，並且裝載於 Microsoft 資料中心。 它們代表廣泛的 Office 365 微服務及其相依性的集合 (順序為 ~100 URL)，並且預期變更率比 *「最佳化」* 類別中的端點高。 並非此類別中的所有端點都與已定義專用 IP 子網路相關聯。

    *「允許」* 端點的網路最佳化可以改善 Office 365 使用者體驗，但是部分使用者選擇將最佳化範圍更縮小，讓他們的網路變更降至最低。

    *「允許」* 端點的範例包括 *https://\*.protection.outlook.com* 和 *https://accounts.accesscontrol.windows.net*。

    最佳化方法包括：

  - 略過網路裝置和服務 (執行流量攔截、SSL 解密、深入封包檢查及內容篩選)的 *「允許」* 端點。
  - 優先評估您的網路基礎結構和周邊系統完全信任的這些端點。
  - 優先降低或消除 WAN 回傳，並且輔助這些端點使用盡可能接近使用者/分公司位置的直接分散式網際網路型出口。
  - 確定 DNS 名稱解析所傳回的 IP 位址符合這些端點的路由出口路徑。
  - 優先處理這些端點的 SD-WAN 整合，以取得進入 Microsoft 全域網路最接近網際網路對等互連點的直接、最低延遲路由。

- **「預設」** 端點表示不需要任何最佳化的 Office 365 服務和相依性，可以由客戶網路視為一般網際網路繫結流量。 此類別中的部分端點可能不是裝載於 Microsoft 資料中心。 範例包括 *https://odc.officeapps.live.com* 和 *https://appexsin.stb.s-msn.com*。

如需有關 Office 365 網路最佳化技術的詳細資訊，請參閱[管理 Office 365 端點](managing-office-365-endpoints.md) 一文。
  
## <a name="comparing-network-perimeter-security-with-endpoint-security"></a>比較網路周邊網路安全性與端點安全性
<a name="BKMK_SecurityComparison"> </a>

傳統網路安全性的目標是強化公司網路周邊網路，免於入侵和惡意攻擊。 隨著組織採用 Microsoft 365，某些網路服務和資料會部分或全部遷移至雲端。 針對網路架構的任何基礎變更，這個程序需要重新評估網路安全性，將新的因素列入考量：
  
- 採用雲端服務之後，網路服務和資料會在內部部署資料中心與雲端之間散佈，周邊安全性本身已不足夠。
- 遠端使用者從不受控制的位置 (如住家、旅館和咖啡廳) 連線到位於內部部署資料中心和雲端中的公司資源。
- 有目的建置的安全性功能大量內建到雲端服務，也許可以補充或取代現有的安全性系統。

Microsoft 提供大範圍的 Microsoft 365 安全性功能，並且提供採用安全性最佳做法的規範指引，可協助您確保 Microsoft 365 的資料和網路安全性。 建議的最佳做法包括下列項目：
  
- **使用多重要素驗證 (MFA)** MFA 會藉由在使用者輸入密碼之後，要求使用者在其智慧型手機上確認電話來電、簡訊或應用程式通知，對強式密碼策略增加另外一層的保護。

- **使用 Microsoft Cloud App Security** 設定原則以追蹤異常活動並且採取動作。 使用 Microsoft Cloud App Security 設定警示，讓管理員可以檢閱不尋常或是有風險的使用者活動，例如下載大量的資料、多次失敗的登入嘗試或是來自未知或危險 IP 位址的連線。

- **設定資料外洩防護 (DLP)** DLP 可讓您識別敏感性資料，並且建立原則，協助防止使用者意外或故意共用資料。 DLP 可在 Microsoft 365 之間運作，包括 Exchange Online、SharePoint Online 和 OneDrive，因此您的使用者可以保持符合規範，而不會中斷他們的工作流程。

- **使用 Customer Lockbox** 身為 Microsoft 365 系統管理員，您可以使用 Customer Lockbox 控制 Microsoft 技術支援工程師如何在協助工作階段期間存取您的資料。 在工程師需要存取您的資料來排解及修正問題的情況下，Customer Lockbox 可讓您核准或拒絕存取要求。

- **使用 Office 365 安全分數** 一種安全性分析工具，為您建議可以執行的動作以進一步降低風險。 「安全分數」會查看您的 Microsoft 365 設定和活動，並且將它們與 Microsoft 所建立的基準進行比較。 您的得分將會以您與最佳安全性實作的相符程度為準。

用來增強安全性的整體方法應該包含下列考量：
  
- 藉由套用雲端型和 Office 用戶端安全性功能，將重點從周邊安全性切換到端點安全性。
  - 將安全性周邊縮小到資料中心
  - 針對公司內部或遠端位置的使用者裝置，啟用對等信任
  - 專注於保護資料位置和使用者位置
  - 受控使用者電腦具有端點安全性的更高信任
- 從整體管理所有資訊安全性，而不是單獨專注在周邊上
  - 藉由允許受信任的流量略過安全性裝置，並且將非受控裝置分隔為來賓 Wi-Fi 網路，以重新定義 WAN 並且建置周邊網路安全性。
  - 降低公司 WAN 邊緣的網路安全性需求
  - 仍然需要某些網路周邊安全性裝置 (例如防火牆)，但是負載會減少
  - 確保 Microsoft 365 流量的本機出口
- 改進可以逐漸實施，如同[增量最佳化](microsoft-365-network-connectivity-principles.md#BKMK_IncOpt)一節中所述。 取決於您的網路架構，某些最佳化技術可能會提供更佳的成本/效益比，因此您應該選擇對組織最有意義的最佳化。

如需有關 Microsoft 365 安全性與合規性的詳細資訊，請參閱文章 [Microsoft 365 安全性](https://docs.microsoft.com/microsoft-365/security)和 [Microsoft 365 合規性](https://docs.microsoft.com/microsoft-365/compliance)。
  
## <a name="incremental-optimization"></a>增量最佳化
<a name="BKMK_IncOpt"> </a>

我們稍早在本文中呈現了 SaaS 的理想網路連線模型，但是對於具有歷史複雜網路架構的許多大型組織而言，直接做以上所有變更並不實際。 在本節中，我們會討論一些增量變更，可以協助改善 Microsoft 365 效能和可靠性。
  
您用來最佳化 Microsoft 365 流量的方法，將會根據您的網路拓撲和您所實作的網路裝置，而有所不同。 具有許多位置和複雜網路安全性實務的大型企業，必須開發策略，其中包含 [Microsoft 365 連線原則](microsoft-365-network-connectivity-principles.md#BKMK_Principles)一節中列出的大部分或所有原則，而較小型的組織只需要考量其中一或兩項。
  
您可以透過增量程序來達到最佳化，接續地套用各個方法。 下表列出關鍵最佳化方法，編排方式是依照方法對於最大量使用者延遲和可靠性的影響。
  
|**最佳化方法**|**描述**|**影響**|
|:-----|:-----|:-----|
|本機 DNS 解析和網際網路出口  <br/> |在每個位置中佈建本機 DNS 伺服器，並且確保 Microsoft 365 連線出口到盡可能接近使用者位置的網際網路。  <br/> | 將延遲降至最低  <br/>  將可靠連線改善到最接近的 Microsoft 365 進入點  <br/> |
|新增區域出口點  <br/> |如果您的公司網路具有多個位置，但是只有一個出口點，請新增區域出口點，讓使用者可以連線到最接近的 Microsoft 365 進入點。  <br/> | 將延遲降至最低  <br/>  將可靠連線改善到最接近的 Microsoft 365 進入點  <br/> |
|略過 Proxy 和檢查裝置  <br/> |使用 PAC 檔案 (會將 Microsoft 365 要求直接傳送到出口點) 來設定瀏覽器。  <br/> 設定邊緣路由器和防火牆，允許 Microsoft 365 流量不用經過檢查。  <br/> | 將延遲降至最低  <br/>  減少網路裝置上的負載  <br/> |
|針對 VPN 使用者啟用直接連線  <br/> |針對 VPN 使用者，藉由實作分割通道，讓 Microsoft 365 連線直接從使用者的網路連線，而無須透過 VPN 通道。  <br/> | 將延遲降至最低  <br/>  將可靠連線改善到最接近的 Microsoft 365 進入點  <br/> |
|從傳統 WAN 遷移至 SD-WAN  <br/> |SD-WAN (軟體定義廣域網路) 藉由以虛擬設備來取代傳統 WAN 路由器，簡化 WAN 管理以及改進效能，類似於使用虛擬機器 (VM) 的計算資源虛擬化。  <br/> | 改善 WAN 流量的效能和管理性  <br/>  減少網路裝置上的負載  <br/> |

## <a name="related-topics"></a>相關主題

[Microsoft 365 網路連線概況](microsoft-365-networking-overview.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)

[評估 Microsoft 365 網路連線能力](assessing-network-connectivity.md)

[Microsoft 365 的網路規劃和效能調整](network-planning-and-performance.md)

[使用基準與效能歷程記錄進行 Office 365 效能調整](performance-tuning-using-baselines-and-history.md)

[Office 365 的效能疑難排解規劃](performance-troubleshooting-plan.md)

[內容傳遞網路](content-delivery-networks.md)

[Microsoft 365 連線測試](https://aka.ms/netonboard)

[Microsoft 如何建置其快速且可靠的全域網路](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 網路部落格](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
