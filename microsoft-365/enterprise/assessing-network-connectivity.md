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
description: Microsoft 365 的設計目的是讓全球客戶可以使用網際網路連線來連線至服務。 隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而改善。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905473"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>評估 Microsoft 365 網路連線能力

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft 365 的設計目的是讓全球客戶可以使用網際網路連線來連線至服務。 隨著服務演變，Microsoft 365 的安全性、效能和可靠性會隨著使用網際網路的客戶建立服務的連接而改善。
  
規劃使用 Microsoft 365 的客戶應評估其現有和預測的網際網路連線需求，做為部署專案的一部分。 針對企業級部署，可靠且適當地調整 internet 連線能力是使用 Microsoft 365 功能和案例的重要部分。
  
根據您的大小和喜好設定，許多不同的人員和組織可以執行網路評估。 評估的網路範圍也會因您在部署程式中所處的位置而有所不同。 為了協助您更深入瞭解執行網路評估的方式，我們產生了網路評估指南，協助您瞭解可用的選項。 這種評估會判斷需要新增至部署專案的步驟和資源，讓您能夠成功採用 Microsoft 365。
  
綜合網路評估會為網路設計挑戰提供可能的解決方案，以及執行詳細資料。 有些網路評估會顯示對 Microsoft 365 的最佳網路連線能力，可與現有網路和網際網路出口基礎結構的次要設定或設計變更搭配使用。

有些評估會指出 Microsoft 365 的網路連線需要網路元件的額外投資。 例如，跨分支辦公室和多個地理區域的商業網路可能需要投資 SD-WAN 解決方案或優化的路由基礎結構，以支援與 Microsoft 365 的網際網路連線。 有時候，評估會指出與 Microsoft 365 的網路連線，會受到諸如 [商務用 Skype Online 媒體質量](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)等案例的法規或效能需求影響。 這些額外需求可能會造成網際網路連線基礎結構、路由優化和特殊直接連線的投資。

協助您評估網路的一些資源：

- 如需有關 Microsoft 365 網路的概念資訊，請參閱 [Microsoft 365 網路連線概述](microsoft-365-networking-overview.md) 。
- 請參閱 [Microsoft 365 網路連線原則](./microsoft-365-network-connectivity-principles.md) ，以瞭解安全管理 Microsoft 365 流量的連線原則，並取得最佳的效能。
- 註冊 [microsoft FastTrack](https://www.microsoft.com/fasttrack) 以取得 microsoft 365 規劃、設計及部署的指導性協助。 
- 請參閱下列 [Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) 一節，以執行基本的連線測試，其可提供有關在指定使用者位置和 Microsoft 365 之間進行的網路連線增強功能的特定指導方針。

> [!NOTE]
> 若要使用 Office 365 ExpressRoute，必須使用 Microsoft 授權。 Microsoft 會在客戶的法規需求規定直接連線時，檢查每個客戶要求，並且只有授權 ExpressRoute 的 Office 365 使用方式。 如果您有這樣的需求，請提供文位元組選及網路連結，以 [瞭解 Office 365 要求表單 ExpressRoute](https://aka.ms/O365ERReview) 中是否需要直接連線才能開始 Microsoft 複查。 嘗試建立 Office 365 之路由篩選的未授權訂閱將會收到 [錯誤訊息](https://support.microsoft.com/kb/3181709)。
  
規劃 Microsoft 365 的網路評估時，應考慮的要點：
  
- Microsoft 365 是透過公用網際網路執行的安全、可靠、高效能服務。 我們會繼續投資以加強服務的這些方面。 所有 Microsoft 365 服務均可透過網際網路連線取得。

- 我們不斷優化 Microsoft 365 的核心層面，例如，針對網際網路連線的可用性、全域訪問能力和效能。 例如，許多 Microsoft 365 服務會利用一組擴充的網際網路對向邊緣節點。 此 edge 網路可為透過網際網路的連線提供最佳的鄰近性和效能。

- 在考慮使用 Microsoft 365 做任何包含的服務（如小組或商務用 Skype Online 語音、影片或會議功能）時，客戶應完成端對端網路評估，並使用 [Microsoft FastTrack](https://www.microsoft.com/fasttrack)符合連線需求。

如果您正在評估 Microsoft 365，但不確定從網路評估開始，或發現需要協助您克服的網路設計挑戰，請與您的 Microsoft 帳戶小組合作。

## <a name="the-microsoft-365-connectivity-test"></a>Microsoft 365 connectivity test

[Microsoft 365 連線測試](https://aka.ms/netonboard)是一項概念證明 (POC) 網路評估工具，可對您的 microsoft 365 租使用者執行基本連線測試，並針對最佳 microsoft 365 效能進行特定的網路設計建議。 工具強調常見的大型商業網路周邊設計選擇，這些選項對網際網路網頁流覽很有用，但會影響大型 SaaS 應用程式（如 Microsoft 365）的效能。

網路上架工具會執行下列作業：

- 偵測您的位置，您也可以指定要測試的位置。
- 檢查網路出局的位置
- 測試最近的 Microsoft 365 服務前端門的網路路徑
- 使用可下載的 Windows 10 應用程式，提供與 proxy 伺服器、防火牆和 DNS 相關的周邊網路設計建議，以進行高級測試。 工具也會執行商務用 Skype Online、Microsoft 小組 SharePoint 線上和 Exchange Online 的效能測試。

工具有兩個元件：一種瀏覽器架構使用者介面，可收集基本連線資訊，以及可執行高級測試並傳回其他評估資料的可下載 Windows 10 應用程式。

瀏覽器型工具會顯示下列資訊：

- [結果與影響] 索引標籤
  - 在使用中的服務前蓋地圖上的位置
  - 其他服務前門的地圖上的位置，可提供最佳連線能力
  - 與其他 Microsoft 365 客戶相較于您附近的相對效能
- 詳細資料與解決方案] 索引標籤
  - 依城市和國家/地區的使用者位置
  - 透過城市、州和國家的網路出局位置
  - 使用者進入網路出局距離
  - Microsoft 365 Exchange Online 服務的前門位置
  - 適用于使用者位置的最佳 Microsoft 365 Exchange Online 服務前門 (s) 
  - 以較佳效能顯示大都市區域中的客戶

「高級測試下載」應用程式提供下列其他資訊：

-  (新增) 的詳細資料和方案] 索引標籤
  - 使用者的預設閘道
  - 用戶端 DNS 伺服器
  - 用戶端 DNS 遞迴解析程式
  - Exchange Online DNS 伺服器
  - 線上 DNS 伺服器 SharePoint
  - Proxy 伺服器識別
  - Media connectivity 檢查
  - 媒體質量封包遺失
  - 媒體質量延遲
  - 媒體質量抖動
  - 媒體質量資料包重新排序
- 對多項特定功能端點的連線性測試
- 網路路徑診斷，包含對 Exchange Online、SharePoint 線上及小組服務的 tracert 和延遲資料

您可以閱讀有關 Microsoft 365 連線測試的資訊，並提供 [新的 microsoft 365 connectivity TEST POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) 的意見，並提供新的網路設計建議博客文章。 有關此工具及其他 Microsoft 365 網路更新未來更新的資訊將會發佈到 [Office 365 網路](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) 博客。
  
您可以使用以下簡短連結回來： [ https://aka.ms/o365networkconnectivity 。](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 網路連線概況](microsoft-365-networking-overview.md)

[Microsoft 365 網路連線原則](./microsoft-365-network-connectivity-principles.md)

[管理 Office 365 端點](managing-office-365-endpoints.md)

[Office 365 URL 與 IP 位址範圍](urls-and-ip-address-ranges.md)

[Office 365 IP 位址和 URL Web 服務](microsoft-365-ip-web-service.md)

[Microsoft 365 網路和效能調整](network-planning-and-performance.md)

[Microsoft 365 企業版概觀](microsoft-365-overview.md)