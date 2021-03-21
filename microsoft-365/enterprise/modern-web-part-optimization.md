---
title: 在 SharePoint Online 新式網站頁面中最佳化網頁組件效能
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: 瞭解如何使用頁面診斷，在 SharePoint 線上新式網站頁面中優化網頁元件的效能。
ms.openlocfilehash: 2a72ecd8bc1f6dee4166809f72ce5f9bce422dc9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929057"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a>在 SharePoint Online 新式網站頁面中最佳化網頁組件效能

SharePoint Online 新式網站頁面包含網頁組件，對整體頁面載入時間有影響。 本文可協助您了解如何判斷頁面中的網頁組件如何影響使用者察覺延遲，以及如何修復常見問題。

>[!NOTE]
>如需有關 SharePoint Online 新式入口網站效能的詳細資訊，請參閱 [SharePoint 新式體驗中的效能](/sharepoint/modern-experience-performance)。

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a>使用「適用於 SharePoint 的頁面診斷」工具來分析網頁組件

適用於 SharePoint 的頁面診斷工具是全新 Microsoft Edge (https://www.microsoft.com/edge) 和 Chrome 瀏覽器的擴充功能，可以用來分析 SharePoint Online 新式入口網站與傳統發佈網站頁面。 該工具會針對每個分析頁面提供一份報告，顯示頁面如何針對定義的效能準則組執行。 若要安裝及了解「適用於 SharePoint 的頁面診斷」工具，請造訪[使用適用於 SharePoint Online 的頁面診斷工具](page-diagnostics-for-spo.md)。

>[!NOTE]
>網頁診斷工具只能用於 SharePoint Online，且無法在 SharePoint 系統頁面使用。

當您使用「適用於 SharePoint 的頁面診斷」工具分析 SharePoint 網站頁面時，您可以在 [診斷測試] 窗格的 [網頁組件影響頁面載入時間] 結果中，看到超過基準計量的網頁組件相關資訊。

可能的結果包括：

- **需要注意** (紅色)：任何在檢視區 (頁面首先載入的畫面可見部分) 顯示的 _自訂_ 網頁組件，載入會耗時超過 **兩** 秒。 任何檢視區之外的 _自訂_ 網路組建，載入會耗時超過 **四** 秒。 總計載入時間會顯示在測試結果中，且會依據模組載入、消極式載入、初始、轉譯來細分。
- **改善機會** (黃色)：可能會影響頁面載入時間的項目會顯示在此區段，應該加以檢閱及監控。 包含「現成 (OOTB)」Microsoft 網頁組件。 此區段中顯示的任何 Microsoft 網頁組件結果，會自動向 Microsoft 報告，因此 **不需要任何動作**。 如果您遇到頁面效能緩慢的情形，且頁面上 **所有 Microsoft 網頁組件** 顯示在 **改善機會** 區段的結果中，您應該只記錄支援票證以進行調查。 請注意，未來適用於 SharePoint 的「頁面診斷」工具更新會根據 Microsoft 網頁組件的特定組態，進一步細分結果。
- **不需要任何動作** (綠色)：沒有任何網頁組件傳回資料耗時超過 **兩** 秒。

如果 [網頁組件影響頁面載入時間] 結果顯示在結果的 [需要注意] 或 [改善機會] 區段中，請按一下結果以查看哪些網頁組件導致載入緩慢的詳細資訊。 未來「適用於 SharePoint 的頁面診斷」工具的更新可能會包含分析規則的更新，因此請確保永遠擁有最新版本的工具。

![頁面診斷工具結果](../media/modern-portal-optimization/pagediag-web-part.png)

結果中提供的資訊包括：

- 會 **顯示網頁** 元件是自訂或 Microsoft OOTB。
- **名稱和識別碼** 會顯示識別資訊，可協助您尋找頁面上的網頁元件。
- **Total** 顯示網頁元件對模組載入、初始化及呈現的總時間。 它是網頁元件在頁面上呈現的總的相對時間（從開始到結尾）。
- **模組載入** 顯示下載、評估和載入副檔名 JAVASCRIPT 和 CSS 檔案所需的時間。 接著，它會啟動 Init 處理常式。
- **Lazy Load** 顯示在頁面主要區段中，未看到的延遲載入網頁元件的時間。 在某些情況下，您可能會呈現太多網頁元件，而且會進行佇列以進行轉譯，以盡可能縮短頁面載入時間。
- **Init** 顯示網頁元件初始化資料所花費的時間。
    這是一項非同步呼叫和 init 時間是指當傳回的承諾得以解決時，onInit 函式的時間計算。
- **Render** 顯示在模組載入和 Init 完成之後，呈現 UI (使用者介面) 所花費的時間。
    在 [檔 (] 頁面) 中裝入 DOM 的 JavaScript 執行時間。
    非同步資源的呈現（例如影像）可能需要額外的時間才能完成。

系統會提供此資訊，協助設計人員和開發人員對問題進行疑難排解。 此資訊應提供給您的設計和開發小組。

## <a name="remediate-web-part-performance-issues"></a>修復網頁組件效能問題

按照本節的指導方針進行，以找出 [網頁組件影響頁面載入時間] 結果中列出的網頁組件效能問題，並加以修復。

網頁組件效能不佳有三種可能的原因。 使用下列資訊以判斷您的案例適用的問題，並進行修復。

- 網頁組件指令碼大小和相依性
  - 最佳化初始指令碼，該指令碼會將主要行案例轉譯為 _僅限檢視模式_。
  - 使用 _import()_ 陳述式，移動較少使用的案例，並且編輯模式程式碼 (例如屬性窗格) 以分隔區塊。
  - 檢閱 _package.json_ 檔案的相依性，以完全移除任何無作用程式碼。 將任何僅限測試/建置相依性移至 devDependencies。
  - 若要下載最佳的靜態資源，需要使用 Office 365 CDN。 公用 CDN 來源適用於 _js/css_ 檔案。 如需使用 Office 365 CDN 的詳細資訊，請參閱[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。
  - 重複使用架構，例如隨附於 SharePoint 架構 (SPFx) 的 _React_ 和 _Fabric imports_。 如需詳細資訊，請參閱 [SharePoint 架構的概觀](/sharepoint/dev/spfx/sharepoint-framework-overview) (英文)。
  - 請確保使用最新版本的 SharePoint 架構，並且在新版本可用時升級。
- 資料提取/快取
  - 若網頁元件依賴額外的伺服器呼叫以取得資料以供顯示，請確定這些伺服器 APIs 快取或) 或執行用戶端快取 (例如，使用 _localStorage_ 或 _IndexedDB_ 以進行較大的集合。
  - 如果需要多個呼叫來轉譯重要資料，請考量在伺服器上進行批次處理，或者將要求合併至單一呼叫的其他方法。
  - 或者，如果資料的某些元素需要較慢的 API，但是對於初始轉譯並不重要，請將這些項目分離為個別呼叫，在重要資料轉譯之後執行。
  - 如果多個組件使用相同的資料，請利用共用資料層來避免重複呼叫。
- 轉譯時間
  - 任何媒體來源 (例如影像和影片) 的大小應該調整為容器、裝置及/或網路的限制，以避免下載不必要的大型資產。 如需內容相依性的詳細資訊，請參閱[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)。
  - 避免造成自動重排、複雜 CSS 規則或複雜動畫的 API 呼叫。 如需詳細資訊，請參閱[最小化瀏覽器自動重排](https://developers.google.com/speed/docs/insights/browser-reflow) (英文)。
  - 避免使用鏈結長時間執行工作。 相反地，將長時間執行工作分開至個別佇列。 如需詳細資訊，請參閱[最佳化 JavaScript 執行](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)。
  - 為非同步轉譯媒體或視覺元件保留對應空間，以避免略過畫面格數和間斷 (也稱為 _jank_)。
  - 如果特定瀏覽器不支援轉譯中使用的功能，則載入 polyfill 或排除執行相依程式碼。 如果功能不重要，請以事件處理常式的形式來處理資源，以避免記憶體流失。

在您進行頁面修訂以修復效能問題之前，請記下分析結果中的頁面載入時間。 在修訂後再次執行工具，以查看新結果是否在基準標準內，並檢查新頁面的載入時間，以查看是否有改善。

![頁面載入時間結果](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>頁面載入時間會因為各種因素而有所不同，例如網路負載、一天的時間及其他暫時條件。 您應該在進行變更前後測試幾次頁面載入時間，以協助您計算結果的平均值。

## <a name="related-topics"></a>相關主題

[調整 SharePoint Online 效能](tune-sharepoint-online-performance.md)

[調整 Office 365 效能](tune-microsoft-365-performance.md)

[SharePoint 新式體驗中的效能](/sharepoint/modern-experience-performance)

[內容傳遞網路](content-delivery-networks.md)

[使用 Office 365 內容傳遞網路 (CDN) 搭配 SharePoint Online](use-microsoft-365-cdn-with-spo.md)