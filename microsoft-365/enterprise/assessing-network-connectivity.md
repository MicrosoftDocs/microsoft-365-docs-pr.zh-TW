---
title: 評估 Microsoft 365 網路連線能力
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
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
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 的設計是要讓全球各地的客戶能夠使用網際網路連線來連線至服務。 隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而有所改善。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905473"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>評估 Microsoft 365 網路連線能力

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 的設計是要讓全球各地的客戶能夠使用網際網路連線來連線至服務。 隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而有所改善。
  
規劃使用 Microsoft 365 的客戶應評估其現有和預測的網際網路連線需求，做為部署專案的一部分。 針對企業級部署，可靠且適當地調整 internet 連線能力是使用 Microsoft 365 功能和案例的重要部分。
  
根據您的大小和喜好設定，許多不同的人員和組織可以執行網路評估。 評估的網路範圍也會因您在部署程式中所處的位置而有所不同。 為了協助您更深入瞭解執行網路評估的方式，我們產生了網路評估指南，協助您瞭解可用的選項。 這種評估會決定需要新增至部署專案的步驟和資源，讓您能夠順利採用 Microsoft 365。
  
綜合網路評估會為網路設計挑戰提供可能的解決方案，以及執行詳細資料。 有些網路評估會顯示出最佳的網路連線 Microsoft 365 能力，可搭配次要設定或對現有網路和網際網路出口基礎結構進行的設計變更。

有些評估會指出 Microsoft 365 的網路連線需要網路元件的額外投資。 例如，跨分支辦公室和多個地理區域的商業網路可能需要投資 SD-WAN 解決方案或優化的路由基礎結構，以支援 Microsoft 365 的網際網路連線。 有時候，評估會指出對 Microsoft 365 的網路連線會受到諸如[商務用 Skype 線上媒體質量](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)等案例的法規或效能需求影響。 這些額外需求可能會造成網際網路連線基礎結構、路由優化和特殊直接連線的投資。

協助您評估網路的一些資源：

- 如需有關 Microsoft 365 網路的概念資訊，請參閱[Microsoft 365 網路連線概述](microsoft-365-networking-overview.md)。
- 請參閱[Microsoft 365 網路連線原則](./microsoft-365-network-connectivity-principles.md)，以瞭解可安全地管理 Microsoft 365 流量，以及取得最佳效能的連線原則。
- 在規劃、設計及部署 Microsoft 365，註冊[Microsoft FastTrack](https://www.microsoft.com/fasttrack)以取得引導協助。 
- 請參閱下列的[Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test)一節，以執行基本的連線測試，以提供有關在指定使用者位置和 Microsoft 365 之間進行的網路連線增強功能的特定指導性。

> [!NOTE]
> 若要使用 Office 365 ExpressRoute，必須使用 Microsoft 授權。 Microsoft 會檢查每個客戶要求，並且只會授權 ExpressRoute，以供客戶的法規需求直接連線時 Office 365 使用方式。 如果您有這樣的需求，請提供文位元組選和 web 連結至您所述的規章，表示[ExpressRoute Office 365 要求表單](https://aka.ms/O365ERReview)開始 Microsoft 複查時，必須直接連線。 嘗試為 Office 365 建立路由篩選的未授權訂閱將會收到[錯誤訊息](https://support.microsoft.com/kb/3181709)。
  
規劃 Microsoft 365 的網路評估時，應考慮的要點：
  
- Microsoft 365 是透過公用網際網路執行的安全、可靠、高效能服務。 我們會繼續投資以加強服務的這些方面。 所有 Microsoft 365 服務均可透過網際網路連線來取得。

- 我們正在不斷優化 Microsoft 365 的核心層面，例如可用性、全域接觸能力，以及網際網路連線的效能。 例如，許多 Microsoft 365 服務都會利用一組擴充的網際網路對向邊緣節點。 此 edge 網路可為透過網際網路的連線提供最佳的鄰近性和效能。

- 當您考慮使用 Microsoft 365 進行任何包含的服務，例如 Teams 或商務用 Skype 線上語音、影片或會議功能時，客戶應完成端對端網路評估，並使用[Microsoft FastTrack](https://www.microsoft.com/fasttrack)滿足連線性需求。

如果您正在評估 Microsoft 365，但不確定要從網路評估開始，或發現需要協助您克服的網路設計挑戰，請與您的 Microsoft 帳戶小組合作。

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 connectivity test

[Microsoft 365 連線測試](https://aka.ms/netonboard)是針對 Microsoft 365 租使用者執行基本連線測試 (POC) 網路評估工具的概念證明，並針對最佳 Microsoft 365 效能進行特定的網路設計建議。 此工具強調常見的大型商業網路周邊設計選擇，這些選項對網際網路網頁流覽很有用，但會影響大型 SaaS 應用程式（如 Microsoft 365）的效能。

網路上架工具會執行下列作業：

- 偵測您的位置，您也可以指定要測試的位置。
- 檢查網路出局的位置
- 測試最近 Microsoft 365 服務前門的網路路徑
- 提供使用可下載的 Windows 10 應用程式進行的高級測試，使周邊網路設計建議與 proxy 伺服器、防火牆和 DNS 有關。 工具也會執行商務用 Skype 線上、Microsoft Teams SharePoint 線上及 Exchange Online 的效能測試。

工具有兩個元件：一種瀏覽器架構使用者介面，可收集基本連線資訊，以及執行高級測試並傳回其他評估資料的可下載 Windows 10 應用程式。

瀏覽器型工具會顯示下列資訊：

- [結果與影響] 索引標籤
  - 在使用中的服務前蓋地圖上的位置
  - 其他服務前門的地圖上的位置，可提供最佳連線能力
  - 與接近您的其他 Microsoft 365 客戶的相對效能
- 詳細資料與解決方案] 索引標籤
  - 依城市和國家/地區的使用者位置
  - 透過城市、州和國家的網路出局位置
  - 使用者進入網路出局距離
  - Microsoft 365 Exchange Online 服務前門位置
  - Microsoft 365 使用者位置) Exchange Online 服務前端 (s 的最佳
  - 以較佳效能顯示大都市區域中的客戶

「高級測試下載」應用程式提供下列其他資訊：

-  (新增) 的詳細資料和方案] 索引標籤
  - 使用者的預設閘道
  - 用戶端 DNS 伺服器
  - 用戶端 DNS 遞迴解析程式
  - Exchange OnlineDNS 伺服器
  - SharePoint線上 DNS 伺服器
  - Proxy 伺服器識別
  - Media connectivity 檢查
  - 媒體質量封包遺失
  - 媒體質量延遲
  - 媒體質量抖動
  - 媒體質量資料包重新排序
- 對多項特定功能端點的連線性測試
- 網路路徑診斷，包含 Exchange Online 的 tracert 和延遲資料，SharePoint 線上和 Teams 服務

您可以閱讀 Microsoft 365 更新的 Microsoft 365 連線測試，並提供[新的網路設計建議，並提供新的網路設計建議，以進行](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130)博客文章。 此工具及其他 Microsoft 365 網路更新的未來更新資訊將會發佈到[Office 365 網路](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)博客。
  
您可以使用以下簡短連結回來： [ https://aka.ms/o365networkconnectivity 。](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 網路連線概況](microsoft-365-networking-overview.md)

[Microsoft 365 網路連線能力準則](./microsoft-365-network-connectivity-principles.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)

[Microsoft 365 網路和效能調整](network-planning-and-performance.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)