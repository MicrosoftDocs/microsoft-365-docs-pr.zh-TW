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
description: PerformancePoint Server 2007、ProClarity 及 SharePoint Server 2007 已到達支援終止。 請閱讀本文，以協助規劃您的 BI 解決方案升級。
ms.openlocfilehash: aa6adae24d78b6be72f17fd56c272b1293e6fcdc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927333"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>PerformancePoint Server 2007 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Office 2007 伺服器及應用程式已達到其支援的終止程度，包括您在商務智慧 (BI) 解決方案時可能使用的伺服器和應用程式。 下表列出受影響的 BI 應用程式：
  
|**Microsoft BI 應用程式**|**日期支援結束**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity 桌面 Professional 6。3  <br/> ProClarity SharePoint Viewer 6。3  <br/> |2017 年 7 月 11 日  <br/> |
|SharePoint伺服器 2007 Service Pack 3  <br/> |2017 年 10 月 10 日  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |2018 年 1 月 9 日  <br/> |
   
如需詳細資訊，請參閱[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-does-end-of-support-mean"></a>*支援終止的* 意義為何？

就像大多數的 Microsoft 產品一樣，PerformancePoint Server 2007 SP3、ProClarity 軟體，以及 SharePoint 的伺服器 2007 SP3，都有支援週期，Microsoft 會在其中提供新功能、錯誤修正及安全性更新。 產品的生命週期一般會從產品的初始發行版本持續10年。 該生命週期的結束即稱為產品的支援終止。 隨著 ProClarity、PerformancePoint Server 和 SharePoint Server 2007 已達到其支援的終止，Microsoft 不再提供：
  
- 可能發生問題的技術支援。
    
- 針對所探索之問題的錯誤修正，而且可能會影響伺服器的穩定性和可用性。
    
- 已探索的漏洞安全性修正程式，可能會導致伺服器或應用程式遭受安全性破壞。
    
- 時區更新。
    
您的 ProClarity 安裝、SharePoint Server 2007 SP3 和 PerformancePoint Server 2007 SP3 仍會繼續執行，即使支援已結束也是一樣。 不過，我們強烈建議您儘快從這些應用程式進行遷移。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

Microsoft BI 應用程式已有許多變更，自2007起，您必須考慮數個選項，如下表所匯總。
  
|**如果您正在使用此 .。。**|**探索下列選項 .。。**|**請記住這一點 .。。**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 監控 &amp; 分析功能，包括：<br/>-PerformancePoint 監控伺服器 <br/>-PerformancePoint 儀表板設計工具<br/>-用於呈現 PerformancePoint 儀表板、計分卡及報表之 SharePoint Services (的儀表板檢視器) <br/> |Excel 雲端或內部部署) 的 **瀏覽器** (中的 Excel。 如需概要，請參閱[Excel 和 Microsoft 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。<br/><br/> **Power BI** 雲端或內部部署) 中的 (。 如需簡介，請參閱[什麼是 Power BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (內部部署) 。 如需概述，請參閱[SQL Server Reporting Services (SSRS) ：建立、部署及管理行動裝置和分頁報告](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)。 <br/><br/> **PerformancePoint Services** (內部部署) 。 如需簡介，請參閱[PerformancePoint Services (的新功能 SharePoint Server 2010) ](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))。 <br/> |Excel 是以線上 (雲端架構) 或內部部署解決方案提供。 您可以使用 Excel 來滿足許多報表和儀表板的需求。  <br/><br/> Power BI 提供為線上或內部部署解決方案。 Microsoft 365 中不包含 Power BI。 不過，您可以開始使用 Power BI 免費。 稍後，視您的資料使用量和業務需求而定，您可以使用 Microsoft 365 E5 升級為 Power BI Pro。<br/> <br/> 報表服務和 PerformancePoint Services 都是內部部署解決方案。 <br/><br/> PerformancePoint Services 可在 SharePoint Server 2010、SharePoint server 2013 及 SharePoint Server 2016 中取得。 <br/> <br/> Excel、Power BI、Reporting Services 或 PerformancePoint Services 都無法使用 PerformancePoint Server 2007 中可用的某些功能和報告類型。 請複查可用的功能，以判斷您的業務需求的最佳解決方案。 <br/> |
| ProClarity 軟體，包括：<br/>-ProClarity 桌面 Professional<br/> -ProClarity Analytics Server<br/>-ProClarity SharePoint 檢視器<br/> |**與 Microsoft 合作夥伴合作** ，找出最符合您需求的解決方案。 請造訪 [Microsoft 合作夥伴中心](https://go.microsoft.com/fwlink/?linkid=841249)。 <br/><br/> 您也可以考慮在瀏覽器、Power BI、SQL Server Reporting Services 或 PerformancePoint Services 中搭配 Excel 使用 Excel。  <br/> |在其他 Microsoft 的產品中皆可使用 ProClarity 軟體的某些功能，包括 Excel、Power BI、報表服務及 PerformancePoint Services。  <br/> |
|SharePoint伺服器 2007 KPIs (也稱為 MOSS KPIs)   <br/> |**使用 Excel Services Excel**。 如需簡介，請參閱[Excel 和 Excel Services 中的商務智慧 (SharePoint Server 2013) ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |使用 SharePoint server 2007 建立的 MOSS KPIs，可用於 SharePoint Server 2010，SharePoint server 2013，以及 SharePoint 伺服器2016。 不過，您無法建立新的 MOSS KPIs。  <br/> |
|Excel 2007  <br/> |**Excel** 雲端或內部部署) 中的 (。 如需概要，請參閱[Excel 和 Office 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。 <br/><br/> **Power BI** 雲端或內部部署) 中的 (。 如需簡介，請參閱[什麼是 Power BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Excel 和 Power BI 會為您的組織提供雲端架構和內部部署解決方案，並支援各種資料來源。  <br/> |
   
### <a name="help-selecting-a-solution"></a>協助您選取解決方案

使用這麼多的 BI 選項時，最好決定哪個選項。 我們有線上指南可提供協助。 請參閱 [選擇 Microsoft 商務智慧 (BI) 工具進行分析與報告](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)。
  
### <a name="what-if-i-dont-upgrade-now"></a>如果現在不升級，該怎麼辦？

您可以選擇不立即升級。 您的現有伺服器及應用程式會繼續執行。 不過，您不會收到任何更新，包括安全性更新，因為支援已結束。 而且，如果您的伺服器應用程式發生錯誤，您將無法從 Microsoft 技術支援取得協助。
  
## <a name="how-do-i-plan-my-upgrade"></a>如何規劃升級？

在您探索升級選項之後，下一步是準備升級計畫。 下列各節包含有助於的資訊及其他資源。 您有四個主要選項，包括在雲端或內部部署中使用的兩個，以及僅限內部部署的兩個選項：
  
|**選項**|**在雲端或內部部署中？**|
|:-----|:-----|
|[使用 SharePoint Server (內部部署) 的 Excel](#excel-with-sharepoint-server-on-premises) <br/> |兩者都要  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |兩者都要  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |僅內部部署  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |僅內部部署  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>在雲端或內部部署) 中使用 Excel (

使用 Excel （也稱為 *Excel Services* SharePoint Server），您可以在瀏覽器視窗中查看和使用活頁簿，即使電腦上並未安裝 Excel 也是一樣。 您可以使用 Excel 來建立報表、計分卡和儀表板。 然後，與其他人共用您的活頁簿，使用者可以在瀏覽器中使用 Excel，不論是 Microsoft 365 還是 SharePoint Server 內部部署中使用 SharePoint 線上。 您可以使用儲存在內部部署或雲端的資料，讓您可以使用各種各樣的資料來源。
  
下表比較使用 Excel 與 Microsoft 365 搭配 SharePoint 伺服器搭配使用 Excel 的主要優點。 詳細資訊如下。
  
|**在雲端中使用 Microsoft 365 (的 Excel)**|**使用 SharePoint Server (內部部署) 的 Excel**|
|:-----|:-----|
|**您獲得最新的 Excel 版本**。 透過 Microsoft 365，您可以取得最新版的 Excel （包括功能強大的新圖表類型），也就是快速輕鬆地建立圖表與表格的功能，以及支援更多資料來源。 <br/> <br/> **安裝程式會變得更簡單**。 Excel 隨附于商務 Microsoft 365 中，因此沒有任何繁重的部分抬起。 註冊並登入，當您升級內部部署伺服器時，您的執行速度會更快且更有效率。 <br/> <br/> **人們可以隨處存取其活頁簿**。 使用電腦、smart phone 及平板電腦時，使用者可以安全地從任何位置查看活頁簿。 <br/> <br/> **還有更多！** 請參閱[BI Excel 和 Office 365 中的功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。 <br/> |**您管理全域設定**。 做為 SharePoint 管理員，您可以指定全域設定，例如安全性、負載平衡、會話管理、活頁簿快取及外部資料連線。 <br/> <br/> **您可以搭配 PerformancePoint Services 使用 Excel Services**。 您可以將 Excel Services 和 PerformancePoint Services 設定成 SharePoint 伺服器安裝的一部分，並在 PerformancePoint 儀表板中包含 Excel Services 報告。 <br/> <br/> **還有更多！** 請參閱[Business 情報 in Excel 和 Excel Services (SharePoint Server 2013) ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>在雲端中使用 Microsoft 365 (的 Excel) 

如果您移至 Microsoft 365，將會有最新的服務和應用程式，包括 Excel 2016。 Microsoft 365 中無法使用 PerformancePoint Services，因此您將會以 Excel 活頁簿或其他報告取代 PerformancePoint 儀表板內容。 好消息是 Excel 2016 具有許多新圖表類型，而且在 Excel 中建立不錯的儀表板比以往更容易。 而且會定期新增新功能。 若要深入瞭解，請參閱[Excel 2016 Windows 的新功能](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)。
  
此外，如果您購買50席位或 Microsoft 365，Microsoft FastTrack 小組可以協助您進行設定。 若要深入瞭解，請造訪 [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)。
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>使用 SharePoint Server (內部部署) 的 Excel

如果您升級為較新版本的 SharePoint，您可以在 Excel Services 或瀏覽器中使用 Excel，如下所示：
  
- SharePoint Server 2010 中的 Excel Services
    
- SharePoint Server 2013 的 Excel Services
    
- Excel，也就是從 SharePoint Server 2016 分開安裝 Office Online Server 的一部分。
    
您也可以在新版本的 SharePoint 伺服器上設定 PerformancePoint Services，並搭配 Excel 使用。
  
若要深入瞭解您的 SharePoint 升級選項，請參閱[SharePoint Server 2007 終止支援藍圖](sharepoint-2007-end-of-support.md)。
  
若要深入瞭解 Excel Services，請參閱[Excel Services 一覽 (SharePoint Server 2010) ](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))。
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>在雲端或內部部署) 中使用 Power BI (

Power BI 是一套商務 analytics 工具，可用於分析資料及共用洞察力。 使用 Power BI，您可以使用內部部署或線上資料來源建立互動報表和儀表板。 人員可以在其電腦或行動裝置上查看和使用您的報表和儀表板。
  
Power BI 不是 Microsoft 365 或 SharePoint 伺服器的一部分。 這是個別的服務，包含 Power BI Desktop、Power BI 閘道和 Power BI 服務。 Power BI 也會與 SharePoint 線上整合。 您可以免費開始使用 Power BI。 您可以根據您的資料使用量和業務需求，使用 Microsoft 365 E5 升級為 Power BI Pro。 若要深入瞭解，請參閱[什麼是 Power BI？](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>使用 Reporting Services (內部部署) 

SQL Server Reporting Services 提供穩健的報表解決方案。 您可以設定純模式或 SharePoint 整合模式中的 Reporting Services。 您可以使用數種不同的工具來編寫報表，包括報表設計人員、Report Builder 及 Power View。 使用最新版的 SQL Server，您也可以使用 SQL Server 行動報告 Publisher 來傳送縮放至任何畫面大小的報告。 這可讓檢視器使用其行動裝置上的報告。 若要深入瞭解，請參閱[SQL Server Reporting Services (SSRS) ：建立、部署及管理行動裝置和分頁報告](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)。
  
### <a name="use-performancepoint-services-on-premises"></a>使用 PerformancePoint Services (內部部署) 

PerformancePoint Server 2007 是與 SharePoint 伺服器2007分開銷售。 從 SharePoint Server 2010 開始，PerformancePoint Services 是 SharePoint Server 中的服務應用程式。 因此，您不需要購買個別的伺服器授權或硬體，即可使用 PerformancePoint Services。
  
若要從 PerformancePoint Server 2007 移至 PerformancePoint Services，您可以移至 SharePoint 伺服器的更新版本，並設定 PerformancePoint Services。 您要移動的 SharePoint 伺服器版本，決定您是否可以將現有的儀表板內容從 PerformancePoint Server 2007 匯入 PerformancePoint Services。
  
- 如果您升級為 SharePoint Server 2010，您可以將 PerformancePoint 儀表板內容從 PerformancePoint Server 2007 匯入 SharePoint Server 2010 中的 PerformancePoint Services。 若要深入瞭解，請參閱匯[入嚮導： SharePoint Server 2010 PerformancePoint Server 2007 內容](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14))。
    
- 如果您移至 SharePoint server 2013 或 SharePoint Server 2016，您很可能需要建立新的儀表板內容， (資料來源、報表、計分卡和儀表板頁面) 。
    
若要開始 PerformancePoint Services 升級計畫，請參閱下列資源：
  
- [SharePoint伺服器2007終止支援藍圖](sharepoint-2007-end-of-support.md)
    
- 當您知道要移動的 SharePoint 版本，請參閱對應的文章，以取得 PerformancePoint Services：
    
  - [規劃 PerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [SharePoint Server 2013 的 PerformancePoint Services 概觀](/sharepoint/administration/performancepoint-services-overview)
    
  - [SharePoint Server 2016 中的 PerformancePoint Services 概觀](/sharepoint/administration/performancepoint-services-overview)
    
當您升級為 PerformancePoint Services 時，會收到一些新的功能和增強功能。 PerformancePoint Services 提供改良的計分卡;新的視覺化效果，例如分解樹狀目錄及 KPI 詳細資料包表;其他圖表類型;更好的時間智慧篩選功能;並改進輔助功能規格。 若要深入瞭解，請參閱[PerformancePoint Services (的新功能 SharePoint Server 2010) ](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))。
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>我可以在哪裡取得有關升級的說明？

不論您是要升級內部部署還是移至 Microsoft 365，我們建議您使用 Microsoft partner。 合格的合作夥伴可協助您找出最符合您的業務需求及協助您部署的解決方案。 請造訪 [Microsoft 合作夥伴中心](https://go.microsoft.com/fwlink/?linkid=841249)，並使用搜尋篩選器尋找解決方案提供者。
  
## <a name="related-topics"></a>相關主題

[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)