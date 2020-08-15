---
title: PerformancePoint Server 2007 終止支援藍圖
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007、ProClarity 及 SharePoint Server 2007 已接通支援的終止。 請閱讀本文以規劃您的 BI 解決方案升級。
ms.openlocfilehash: b9718630ff92b8093fa3940b12dde1b34486616c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695554"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>PerformancePoint Server 2007 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Office 2007 伺服器及應用程式已達到其支援的終止程度，包括您在商務智慧 (BI) 解決方案中可能使用的伺服器和應用程式。 下表列出受影響的 BI 應用程式：
  
|**Microsoft BI 應用程式**|**日期支援結束**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity 桌面專業6。3  <br/> ProClarity SharePoint Viewer 6。3  <br/> |2017 年 7 月 11 日  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |2017 年 10 月 10 日  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |2018 年 1 月 9 日  <br/> |
   
如需詳細資訊，請參閱 [協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-does-end-of-support-mean"></a>終止支援是什麼意思？

Microsoft 產品（例如 PerformancePoint Server 2007 SP3、ProClarity 軟體及 SharePoint 伺服器2007） SP3 都有支援週期，Microsoft 會在其中提供新功能、錯誤修正及安全性更新。 產品的生命週期一般會從產品的初始發行日期起10年後開始，而且生命週期的結束也稱為產品的支援終止。 隨著 ProClarity、PerformancePoint 伺服器及 SharePoint Server 2007 已達到其支援的結尾，Microsoft 將不再提供：
  
- 可能發生問題的技術支援
    
- 針對探索的問題，以及可能影響伺服器穩定性和可用性的錯誤修正
    
- 已發現並可能導致伺服器或應用程式易受安全性破壞之弱點的安全性修正程式
    
- 時區更新
    
您的 ProClarity 安裝、SharePoint Server 2007 SP3 和 PerformancePoint Server 2007 SP3 仍會繼續執行，即使支援已結束也是一樣。 不過，我們強烈建議您儘快從這些應用程式進行遷移。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

透過這些 BI 應用程式的支援結束，這是探索選項及準備升級計畫的絕佳時間。 Microsoft BI 應用程式已有許多變更，自2007起，您有數個選項要考慮，如下表所匯總：
  
|**如果您正在使用此 .。。**|**探索下列選項 .。。**|**請記住這一點 .。。**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 監控 &amp; 分析功能，包括：  <br/><br/>  PerformancePoint 監控伺服器  <br/><br/>  PerformancePoint 儀表板設計工具  <br/><br/>  用於呈現 PerformancePoint 儀表板、計分卡及報表之 SharePoint 服務 (的儀表板檢視器)   <br/> |在雲端或內部部署) 中 **，在瀏覽器**中 (excel。 如需概要，請參閱 [Excel 和 Microsoft 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> 雲端或內部部署) 中的**POWER BI** (。 如需簡介，請參閱 [什麼是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (內部部署) 。 如需概述，請參閱 [SQL Server Reporting Services (SSRS) ：建立、部署及管理行動裝置和分頁報告](https://go.microsoft.com/fwlink/?linkid=841342) <br/><br/> **PerformancePoint 服務** (內部部署) 。 如需概述，請參閱 [PerformancePoint 服務的新功能 (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841343) <br/> |Excel 是以線上 (雲端架構) 或內部部署解決方案的形式提供。 Excel 的功能可滿足許多報表和儀表板的需求。  <br/><br/> Power BI 可以做為線上或內部部署解決方案。 Power BI 並未包含在 Microsoft 365 中，但您可以立即開始使用 Power BI，然後根據您的資料使用量和業務需求，使用 Microsoft 365 E5 升級至 Power BI Pro。 <br/> <br/> 報表服務和 PerformancePoint 服務都是內部部署解決方案。  <br/><br/> PerformancePoint 服務可在 SharePoint Server 2010、SharePoint Server 2013 及 SharePoint Server 2016 中取得。 <br/> <br/> Excel、Power BI、Reporting Services 或 PerformancePoint 服務中無法使用 PerformancePoint Server 2007 中可用的某些功能和報表類型。 您將會想要查看可用的功能，以判斷您的業務需求的最佳解決方案。  <br/> |
| ProClarity 軟體，包括： <br/> <br/>  ProClarity 桌面專業版  <br/> <br/> ProClarity Analytics Server  <br/> <br/> ProClarity SharePoint 檢視器  <br/> |**與 Microsoft 合作夥伴合作** ，找出最符合您需求的解決方案。 流覽 [Microsoft Partner Center](https://go.microsoft.com/fwlink/?linkid=841249) <br/><br/> 您也可以在瀏覽器、Power BI、SQL Server Reporting Services 或 PerformancePoint 服務中考慮使用 Excel 搭配 Excel。  <br/> |在其他 Microsoft 的產品中，有許多（但非全部） ProClarity 可用的功能和功能，包括 Excel、Power BI、Reporting Services 及 PerformancePoint 服務。  <br/> |
|SharePoint Server 2007 KPIs (也稱為 MOSS KPIs)   <br/> |**Excel Services 的 excel**。 如需簡介，請參閱 [excel 和 Excel Services 中的商務智慧 (SharePoint Server 2013) ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |使用 SharePoint Server 2007 建立的 MOSS KPIs，可用於 SharePoint Server 2010、SharePoint Server 2013，以及 SharePoint 伺服器 2016;不過，無法建立新的 MOSS KPIs。  <br/> |
|Excel 2007  <br/> |在雲端或內部部署) 中 (**Excel** 。 如需概要，請參閱 [Excel 和 Office 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> 雲端或內部部署) 中的**POWER BI** (。 如需簡介，請參閱 [什麼是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Excel 和 Power BI 都為您的組織提供雲端架構和內部部署解決方案，並支援各種資料來源。  <br/> |
   
### <a name="what-if-i-need-help-selecting-a-solution"></a>如果我需要協助選取解決方案，該怎麼辦？

使用這麼多的 BI 選項時，最好決定哪個選項。 我們有線上指南可協助您進行協助。 請參閱 [選擇 Microsoft 商務智慧 (BI) 工具進行分析與報告](https://go.microsoft.com/fwlink/?linkid=839877)。
  
### <a name="what-happens-if-i-dont-upgrade-now"></a>若現在不升級，會發生什麼事？

您可以選擇在此時間不升級。 您的現有伺服器及應用程式會繼續執行。 不過，您不會收到任何進一步的更新-包括安全性更新-在支援結束之後。 而且，如果您的伺服器應用程式發生錯誤，您將無法從 Microsoft 技術支援取得協助。
  
## <a name="how-do-i-plan-my-upgrade"></a>如何規劃升級？

在您探索升級選項之後，下一步是準備升級計畫。 下列各節包含其他資源的資訊和連結，可協助您規劃解決方案。 當您遇到 Microsoft BI 應用程式時，您有四個主要選項，包括在雲端或內部部署中運作的兩個，以及僅限內部部署解決方案的兩個選項：
  
|**選項**|**在雲端或內部部署中？**|
|:-----|:-----|
|[Excel](#excel-with-sharepoint-server-on-premises) <br/> |兩者都要  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or on-premises) <br/> |兩者都要  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |僅內部部署  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |僅內部部署  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>在雲端或內部部署中使用 Excel () 

使用 Excel （也稱為「SharePoint Server 中的 Excel 服務」）時，即使電腦未安裝 Excel，使用者還是可以在瀏覽器視窗中查看和使用活頁簿。 您可以使用 Excel 來建立報表、計分卡和儀表板，然後在瀏覽器中使用 Excel 來與其他人共用您的活頁簿，不論您是在 Microsoft 365 中使用 SharePoint 線上，還是 SharePoint 伺服器內部部署。 而且，您可以使用儲存在內部部署或雲端的資料，讓您能夠使用各種各樣的資料來源。
  
下表比較使用 Excel 搭配 Microsoft 365 的主要優點，以使用具有下列其他資訊的 Excel SharePoint Server。
  
|**在雲端中使用 Microsoft 365 (的 Excel) **|**具有 SharePoint Server (內部部署) 的 Excel **|
|:-----|:-----|
|**您獲得最新、最強大的 Excel 版本**。 使用 Microsoft 365，您會獲得最新版本的 Excel，其中包含功能強大的新圖表類型、快速輕鬆地建立圖表與表格的功能，以及支援更多資料來源。 <br/> <br/> **安裝程式會變得更簡單**。 Excel 隨附于 Microsoft 365 for business，所以不需要在您的部分上抬起。 註冊並登入，您將能夠更快且更有效率地執行與升級您的內部部署伺服器。 <br/> <br/> **人們可以隨處存取其活頁簿**。 使用電腦、smart phone 及平板電腦時，使用者可以安全地從任何位置查看活頁簿。 <br/> <br/> **還有更多**！ [在 Excel 和 Office 365 中查看 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**您管理全域設定**。 做為 SharePoint 管理員，您可以指定全域設定，例如安全性、負載平衡、會話管理、活頁簿快取及外部資料連線。 <br/> <br/> **您可以搭配使用 Excel services 與 PerformancePoint 服務**。 您可以將 Excel Services 和 PerformancePoint 服務設定成 SharePoint 伺服器安裝的一部分，並將 Excel Services 報告加入 PerformancePoint 儀表板中。 <br/> <br/> **還有更多**！ 請參閱 [excel 和 Excel Services 中的商務智慧 (SharePoint Server 2013) ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>在雲端中使用 Microsoft 365 (的 Excel) 

如果您移至 Microsoft 365，您將會獲得最新的服務和應用程式，包括 Excel 2016。 在 Microsoft 365 中無法使用 PerformancePoint 服務，因此您將會以 Excel 活頁簿或其他報告取代 PerformancePoint 儀表板內容。 好消息是，Excel 2016 在 Excel 中有許多新圖表類型和建立美觀的儀表板，要比以往更容易。 而且會定期新增新功能。 若要深入瞭解，請參閱 [Excel 2016 For Windows 的新功能](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)。
  
而且，當您購買50席位或以上的 Microsoft 365 時，Microsoft FastTrack 小組可以協助您進行設定。 若要深入瞭解，請造訪 [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)。
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>具有 SharePoint Server (內部部署) 的 Excel

如果您升級至較新版本的 SharePoint，您可以在 excel Services 或瀏覽器中使用 Excel，如下所示：
  
- SharePoint Server 2010 中的 Excel Services
    
- SharePoint Server 2013 的 Excel Services
    
- Excel，也就是從 SharePoint Server 2016 分開安裝的 Office Online 伺服器的一部分
    
您也可以在新版本的 SharePoint 伺服器中設定 PerformancePoint 服務，以及搭配 Excel 使用。
  
若要深入瞭解您的 SharePoint 升級選項，請參閱 [SharePoint Server 2007 終止支援藍圖](sharepoint-2007-end-of-support.md)。
  
若要深入瞭解 Excel Services，請參閱 [Excel services 總覽 (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841362)。
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>使用雲端或內部部署中的 Power BI () 

Power BI 是一套商務 analytics 工具，可用於分析資料及共用洞察力。 使用 Power BI，您可以使用內部部署或線上資料來源建立互動報表和儀表板。 使用者可以使用其電腦或行動裝置來查看和使用報表和儀表板。
  
Power BI 並未包含在 Microsoft 365 或 SharePoint Server 中，但是個別的服務，其中包含 Power BI Desktop、Power BI 閘道和 Power BI 服務。 Power BI 也會與 SharePoint 線上整合。 您可以免費開始使用 Power BI，而且視您的資料使用量和業務需求而定，使用 Microsoft 365 E5 升級至 Power BI Pro。 若要深入瞭解，請參閱 [什麼是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>使用 Reporting Services (內部部署) 

SQL Server Reporting Services 提供強大的報表解決方案，以及在純模式或 SharePoint 整合模式中安裝及設定 Reporting Services 的功能。 您可以使用數種工具（包括報表設計工具、報表建立工具及 Power View）製作報表。 使用最新版的 SQL Server，您也可以使用 SQL Server 行動報告發行者來傳送可擴充至任何畫面大小的報告，讓您的組織可以使用其行動裝置上的報告。 若要深入瞭解，請參閱 [SQL Server Reporting Services (SSRS) ：建立、部署及管理行動裝置和分頁報告](https://go.microsoft.com/fwlink/?linkid=841342)。
  
### <a name="use-performancepoint-services-on-premises"></a> (內部部署) 使用 PerformancePoint 服務

如您所知，PerformancePoint Server 2007 是從 SharePoint 伺服器2007另行購買的。 從 SharePoint Server 2010 開始，PerformancePoint 服務是 SharePoint Server 中的服務應用程式。 這表示您不需要購買個別的伺服器授權或硬體，即可使用 PerformancePoint 服務。
  
若要從 PerformancePoint Server 2007 移至 PerformancePoint 服務，您可以移至 SharePoint 伺服器的更新版本，並設定 PerformancePoint 服務。 您要移動的 SharePoint 伺服器版本，會決定您是否可以將現有的儀表板內容從 PerformancePoint Server 2007 匯入 PerformancePoint 服務。
  
- 如果您要升級為 SharePoint Server 2010，您可以從 PerformancePoint Server 2007 將 PerformancePoint 儀表板內容匯入至 SharePoint Server 2010 中的 PerformancePoint 服務。 若要深入瞭解如何運作，請參閱匯 [入嚮導： PerformancePoint server 2007 內容來 SharePoint 伺服器 2010](https://go.microsoft.com/fwlink/?linkid=838873)。
    
- 如果您要移至 SharePoint Server 2013 或 SharePoint 伺服器2016，您很可能需要建立新的儀表板內容， (資料來源、報表、計分卡和儀表板頁面) 。
    
若要開始執行 PerformancePoint 服務升級計畫，請參閱下列資源：
  
1. [SharePoint Server 2007 終止支援藍圖](sharepoint-2007-end-of-support.md)
    
2. 當您知道要移動的 SharePoint 版本，請參閱 PerformancePoint 服務的對應文章：
    
  - [規劃 PerformancePoint Services (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [SharePoint Server 2013 的 PerformancePoint Services 概觀](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [SharePoint Server 2016 中的 PerformancePoint Services 概觀](https://go.microsoft.com/fwlink/?linkid=874704)
    
當您升級為 PerformancePoint 服務時，您會喜歡一些新的功能和增強功能。 PerformancePoint 服務可提供更佳的計分卡、新的視覺化功能（例如分解樹狀目錄）和 KPI 詳細資料包表，以及更好的時間智慧篩選功能，以及改善的可存取性。 若要深入瞭解，請參閱 [PerformancePoint 服務的新功能 (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841343)。
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>我可以在哪裡取得有關升級的說明？

不論您是要升級內部部署或移至 Microsoft 365，我們建議您使用 Microsoft 合作夥伴。 合格的合作夥伴可協助您找出最符合您的業務需求及協助您部署的解決方案。 請造訪 [Microsoft 合作夥伴中心](https://go.microsoft.com/fwlink/?linkid=841249)，並使用搜尋篩選器尋找解決方案提供者。
  
## <a name="related-topics"></a>相關主題

[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)