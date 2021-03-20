---
title: SharePoint Online 效能調整的簡介
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: 本文說明在 SharePoint Online 中設計最佳效能的頁面時所應考量的特定事項。
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909735"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>SharePoint Online 效能調整的簡介

本文說明在 SharePoint Online 中設計最佳效能的頁面時所應考量的特定事項。
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online 度量資訊

下列廣泛的 SharePoint Online 度量值提供有關效能的實際環境資料：
  
- 頁面載入速度
    
- 每頁所需來回行程次數
    
- 服務的問題
    
- 導致效能降低的其他事項
    
### <a name="conclusions-reached-because-of-the-data"></a>資料所導出的結論

資料會告訴我們：
  
- 大部分頁面在 SharePoint Online 上的執行狀況良好。
    
- 非自訂頁面載入速度很快。
    
- 商務用 OneDrive、小組網站和系統頁面 (如 _layouts 等) 載入速度都很快。
    
- 最慢的 1% SharePoint Online 頁面載入時間需要超過 5000 毫秒。
    
您可使用的一項簡單基準測試是透過比較您的入口網站載入時間和商務用 OneDrive 首頁載入時間來測量效能，因其使用的自訂功能不多。 在進行網路效能問題疑難排解時，這通常是支援人員要求您完成的第一個步驟。
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>檢查效能時，請使用標準使用者帳戶

網站集合系統管理員、網站擁有者、編輯者或參與者皆屬於其他的安全性群組，擁有額外的權限，因此擁有 SharePoint 在頁面上載入之外的其他元素。
  
這適用於 SharePoint 內部部署和 Sharepoint，但在內部部署狀況中，差異不會像在 SharePoint Online 中那樣容易發現。
  
為了正確評估使用者執行頁面的效能，請使用標準使用者帳戶，以避免載入安全性群組相關的製作控制和其他流量。
  
## <a name="connection-categories-for-performance-tuning"></a>效能調整的連線類別

您可將伺服器與使用者之間的連線分類成三種主要元件。 在設計 SharePoint Online 頁面以深入瞭解載入時間時，請將這些元件納入考量。
  
- **伺服器**：Microsoft 在資料中心主控的伺服器。
    
- **網路**：Microsoft 網路、網際網路以及資料中心和您的使用者之間的內部部署網路。
    
- **瀏覽器**：載入頁面所在。
    
在這三種連線中，通常有五個原因會造成 95% 的頁面緩慢情形。 本文將討論這些原因：
  
- 瀏覽問題
    
- 內容彙總
    
- 大型檔案
    
- 對伺服器的要求太多
    
- 網頁組件處理
    
### <a name="server-connection"></a>伺服器連線

許多影響 SharePoint 內部部署效能的問題也會在 SharePoint Online 上出現。
  
一如預期，您有許多手段可控制伺服器在內部部署 SharePoint 中的執行效能。 但在 SharePoint Online 上，情形略有不同。 您讓伺服器執行的工作越多，呈現頁面所需的時間就越長。 而在 SharePoint 中，含有多個網頁組件的複雜頁面才是造成這方面問題的最大禍首。
  
SharePoint Server 內部部署
  
![內部部署伺服器的螢幕擷取畫面](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![伺服器連線的螢幕擷取畫面](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
在 SharePoint Online 上，某些網頁要求可能實際上最後會呼叫多部伺服器。 原本只是一個要求，最後卻可能演變成涉及多部伺服器的多個要求。 從頁面載入的觀點來看，這些互動不僅成本昂貴且會讓效率變慢。
  
這些伺服器對伺服器的互動範例如下：
  
- Web 對 SQL Server
    
- Web 對應用程式伺服器
    
另一個導致伺服器互動速度變慢的因素是快取遺漏。 不同於內部部署 SharePoint，雖然機率微乎其微，但您有可能會叫用相同伺服器來取得之前造訪的頁面；這個情形會讓物件快取過時。
  
### <a name="network-connection"></a>網路連線

在未利用 WAN 的內部部署 SharePoint 中，您可以在資料中心與使用者之間使用高速連線。 從網路的觀點來看，這通常能簡化管理程序。
  
在 SharePoint Online 上，則還要再考慮幾個因素，例如：
  
- Microsoft 網路
    
- 網際網路
    
- ISP
    
不論您使用哪個 SharePoint (和那個網路) 版本，會導致網路忙碌的因素通常包括：
  
- 承載過大
    
- 檔案太多
    
- 與伺服器的實體距離太遠
    
您可以在 SharePoint Online 中利用的其中一項功能為 Microsoft CDN (內容傳遞網路)。 CDN 基本上是部署到多個資料中心的分散式伺服器集合。 使用 CDN 時，頁面上的內容可裝載於接近用戶端的伺服器，即便用戶端離原始 SharePoint 伺服器很遠。 Microsoft 未來將多加利用此功能來儲存無法自訂之頁面的本機執行個體，例如 SharePoint Online 管理首頁。 如需有關 CDN 的詳細資訊，請參閱[內容傳遞網路](content-delivery-networks.md) (部分機器翻譯)。
  
您必須注意但可能無能為力的因素是您的 ISP 連線速度。 簡單的速度測試工具會告訴您連線速度。
  
### <a name="browser-connection"></a>瀏覽器連線

從效能的觀點來看，有幾個與網頁瀏覽器有關的因素要考慮進去。
  
造訪複雜頁面會影響效能。 大部分瀏覽器的快取都很小 (大約 90 MB)，而平均網頁大小通常是 1.6 MB 左右。 不需要多久時間就會把快取用完。
  
頻寬可能也是個問題。 例如，若使用者在另一個工作階段中觀看影片，則會影響您的 SharePoint 網頁效能。 您無法阻止使用者串流媒體，但可控制為使用者載入頁面的方式。
  
請看下列文章來取得不同的 SharePoint Online 頁面自訂技術和其他最佳作法，以協助您達到最佳效能。
  
- [SharePoint Online 的瀏覽選項](navigation-options-for-sharepoint-online.md)
    
- [使用 Sharepoint Online 網頁診斷工具](page-diagnostics-for-spo.md)
    
- [SharePoint Online 的影像最佳化](image-optimization-for-sharepoint-online.md)
    
- [在 SharePoint Online 中延遲載入圖片與 JavaScript](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [SharePoint Online 中的縮製和統合](minification-and-bundling-in-sharepoint-online.md)
    
- [使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [使用內容搜尋網頁組件 (而非內容查詢網頁組件) 來改善 SharePoint Online 中的效能](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [SharePoint Online 容量規劃和負載測試](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [診斷 SharePoint Online 的效能問題](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [使用 SharePoint Online 的物件快取](using-the-object-cache-with-sharepoint-online.md)
    
- [操作方法：如何避免在 SharePoint Online 中受到節流控制或封鎖](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
