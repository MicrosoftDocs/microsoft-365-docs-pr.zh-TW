---
title: SharePoint 線上新式入口網站限制
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: 深入瞭解 SharePoint Online 中新式網站的效能建議，例如限制對 Sharepoint 和外部端點的呼叫。
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688708"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint 線上新式入口網站限制

本文提供 SharePoint Online 中新式入口網站的效能建議。 使用本文中的指導方針優化新式入口網站效能，並避免常見的效能問題。

## <a name="performance-considerations-for-modern-portal-sites"></a>新式入口網站的效能考慮

從效能優化的觀點來看，有一些特徵可讓新式入口網站獨一無二。 在 SharePoint Online 中的共同作業與入口網站之間的主體差異為比例。 入口網站一般會將更多的網頁檢視提供給超過共同作業網站的使用者數目，而且可能包含更多靜態內容和更少可編輯的資源。 此外，新式網站的架構與傳統網站不同的是，在此情況下，呈現頁面和執行程式碼會在用戶端（而非伺服器）上進行的大部分處理。

現代入口網站的效能優化主要是以一些整體目標為重點：

- 減少每個網站頁面元件的總大小
- 將一般靜態檔案（例如影像、樣式表及腳本）的卸載裝載至 CDN
- 只對 SharePoint 和外部端點進行必要的通話限制
- 避免相同內容的重複要求

本文中的許多指導方針主要致力於最小化及優化 SharePoint 線上的呼叫。 每次載入頁面時進行重複呼叫都會影響使用者的效能，因為資訊會在每次從服務中取得，即使尚未變更。 因此，SharePoint 的要求可以分類為所有使用者或每個個別使用者所需通話的通用通話。 這兩個通話類別的結果應該進行快取，以優化使用者體驗。

>[!NOTE]
>您可以使用 [SharePoint 工具的頁面診斷](https://aka.ms/perftool) ，作為分析 SharePoint 線上網站頁面上的特定效能度量的起點。

## <a name="modern-portal-site-limits-and-recommendations"></a>新式入口網站限制與建議

|**限制**|**建議的最大值**|**附註**|
|:-----|:-----|:-----|:-----|
|頁面和新聞專案  <br/> |每個網站 5,000 個  <br/> |我們建議您將現代化入口網站中的頁數和新聞專案數目限制在5000以下。  <br/> |
|頁面上的網頁元件  <br/> |每頁20張  <br/> |建議每頁使用20或更少的網頁元件，包括現成的 Microsoft 網頁元件和自訂網頁元件。 <br/> 如需詳細資訊，請參閱 [優化網頁元件效能 SharePoint 線上新式網站頁面](modern-web-part-optimization.md)。  <br/> |
|頁面上的動態網頁元件  <br/> |每頁4個  <br/> |動態網頁元件，可讓一或多個查詢 SharePoint 以取得最新的資料，每頁應限制為4。 「 _新聞_ 網頁元件」是動態網頁元件的範例。 <br/> 如需詳細資訊，請參閱 [優化網頁元件效能 SharePoint 線上新式網站頁面](modern-web-part-optimization.md)。    <br/> |
|安全性群組  <br/> |每個網站20個  <br/> |安全性群組的數目會影響現代入口網站中的許多查詢規模。 建議您將安全性群組的數目限制在盡可能的小，但不得超過每個網站的20個。  <br/> |
|網站導航中的專案  <br/> |每個網站100個  <br/> |我們建議您新增少於100個專案到網站導航，並使用現成的導覽控制項。  <br/> 如需詳細資訊，請參閱 [SharePoint Online 新式網站頁面中的優化頁面體重](modern-page-weight-optimization.md)。 <br/> |
|圖像大小上限  <br/> |每個映射 300 Kb  <br/> |建議您將影像大小限制為300kb 或更小，並使用 CDN 來裝載影像、樣式單及腳本。 <br/>如需詳細資訊，請參閱 [在 SharePoint 線上新式網站頁面上優化影像](modern-image-optimization.md) ，並 [使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。  <br/> |
|具有編輯許可權的使用者  <br/> |每個網站200個使用者  <br/> |SharePoint 入口網站已針對查看和使用內容進行優化。 對入口網站的編輯許可權應該限制為一組限制的使用者，因為編輯許可權會下載其他控制項，因此這些使用者的執行速度會變慢。 大量具有編輯許可權的使用者會影響整體體驗。 <br/> |
|協力廠商 Iframe  <br/> |每頁2個  <br/> |Iframe 會因載入個別的外部頁面（包括所有相關聯的內容，例如 javascript、CSS 及 framework 元素）而無法預知。 如果您必須使用 Iframe，請將其數目限制為2個或更少的頁面。<br/> 如需詳細資訊，請參閱 [在 SharePoint 線上新式和傳統發佈網站頁面上優化 iframe](modern-iframe-optimization.md)。 <br/> |
|呼叫 UPA 服務  <br/> |每位使用者每小時1個  <br/> |建議您不要對 UPA (User Profile 應用程式) 服務上的 _每個要求_ 進行呼叫。 [Microsoft GRAPH API](https://docs.microsoft.com/graph/call-api)和[PageCoNtext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest)可用於查詢使用者資訊。  <br/> 如果需要 UPA 服務呼叫，請在必要時進行單一通話，然後快取此資訊，以便在相同的會話中重複使用。 |
|呼叫分類服務  <br/> |每位使用者每小時5個  <br/> |建議您不要針對分類服務撥打任何 _要求_ 。 如果需要分類服務通話，請快取資訊，以便在相同的會話中重複使用。 <br/> 如需詳細資訊，請參閱 [在 SharePoint 線上新式和傳統發佈網站頁面上優化頁面通話](modern-page-call-optimization.md)。 <br/> |

## <a name="related-topics"></a>相關主題

[建立狀況良好的 SharePoint 入口網站](https://docs.microsoft.com/sharepoint/portal-health)

[調整 SharePoint Online 效能](tune-sharepoint-online-performance.md)

[調整 Office 365 效能](tune-microsoft-365-performance.md)

[SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[SharePoint 新式體驗中的效能](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[SharePoint Online 入口網站的效能指導方針](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)
