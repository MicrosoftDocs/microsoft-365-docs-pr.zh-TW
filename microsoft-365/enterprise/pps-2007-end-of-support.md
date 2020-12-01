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
description: PerformancePoint Server 2007、ProClarity 及 SharePoint Server 2007 已接通支援的終止。 請閱讀本文，以協助規劃您的 BI 解決方案升級。
ms.openlocfilehash: 4a13e6f8a40de78c0d98b03369b52a78899fc7a9
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519594"
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
  
## <a name="what-does-end-of-support-mean"></a>*支援終止的* 意義為何？

就像大多數的 Microsoft 產品一樣，PerformancePoint Server 2007 SP3、ProClarity 軟體及 SharePoint 伺服器 2007 SP3，都有一個支援週期，Microsoft 會在其中提供新功能、錯誤修正及安全性更新。 產品的生命週期一般會從產品的初始發行版本持續10年。 該生命週期的結束即稱為產品的支援終止。 隨著 ProClarity、PerformancePoint 伺服器及 SharePoint Server 2007 已達到其支援的終止，Microsoft 不再提供：
  
- 可能發生問題的技術支援。
    
- 針對所探索之問題的錯誤修正，而且可能會影響伺服器的穩定性和可用性。
    
- 已探索的漏洞安全性修正程式，可能會導致伺服器或應用程式遭受安全性破壞。
    
- 時區更新。
    
您的 ProClarity 安裝、SharePoint Server 2007 SP3 和 PerformancePoint Server 2007 SP3 仍會繼續執行，即使支援已結束也是一樣。 不過，我們強烈建議您儘快從這些應用程式進行遷移。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

Microsoft BI 應用程式已有許多變更，自2007起，您必須考慮數個選項，如下表所匯總。
  
|**如果您正在使用此 .。。**|**探索下列選項 .。。**|**請記住這一點 .。。**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 監控 &amp; 分析功能，包括：<br/>-PerformancePoint 監控伺服器 <br/>-PerformancePoint 儀表板設計工具<br/>-用於呈現 PerformancePoint 儀表板、計分卡及報表的 SharePoint 服務 (的儀表板檢視器) <br/> |在雲端或內部部署) 中 **，在瀏覽器** 中 (excel。 如需概述，請參閱 [Excel 和 Microsoft 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。<br/><br/> 雲端或內部部署) 中的 **POWER BI** (。 如需簡介，請參閱 [什麼是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (內部部署) 。 如需概述，請參閱 [SQL Server Reporting Services (SSRS) ：建立、部署及管理行動裝置和分頁報告](https://go.microsoft.com/fwlink/?linkid=841342)。 <br/><br/> **PerformancePoint 服務** (內部部署) 。 如需概述，請參閱 [PerformancePoint 服務的新功能 (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841343)。 <br/> |Excel 是以線上 (雲端架構) 或內部部署解決方案的形式提供。 Excel 可滿足許多報表和儀表板的需求。  <br/><br/> Power BI 是以線上或內部部署解決方案提供。 Power BI 並未包含在 Microsoft 365 中。 不過，您可以開始使用 Power BI for free。 稍後，視您的資料使用量和業務需求而定，您可以使用 Microsoft 365 E5 升級至 Power BI Pro。<br/> <br/> 報表服務和 PerformancePoint 服務都是內部部署解決方案。 <br/><br/> PerformancePoint 服務可在 SharePoint Server 2010、SharePoint Server 2013 及 SharePoint Server 2016 中取得。 <br/> <br/> Excel、Power BI、Reporting Services 或 PerformancePoint 服務中無法使用 PerformancePoint Server 2007 中提供的某些功能和報表類型。 請複查可用的功能，以判斷您的業務需求的最佳解決方案。 <br/> |
| ProClarity 軟體，包括：<br/>-ProClarity 桌面專業版<br/> -ProClarity Analytics Server<br/>-ProClarity SharePoint 檢視器<br/> |**與 Microsoft 合作夥伴合作** ，找出最符合您需求的解決方案。 請造訪 [Microsoft 合作夥伴中心](https://go.microsoft.com/fwlink/?linkid=841249)。 <br/><br/> 您也可以在瀏覽器、Power BI、SQL Server Reporting Services 或 PerformancePoint 服務中考慮使用 Excel 搭配 Excel。  <br/> |有幾個但並非 ProClarity 軟體的所有功能都可用於其他 Microsoft 的產品，包括 Excel、Power BI、Reporting Services 及 PerformancePoint 服務。  <br/> |
|SharePoint Server 2007 KPIs (也稱為 MOSS KPIs)   <br/> |**Excel Services 的 excel**。 如需簡介，請參閱 [excel 和 Excel Services 中的商務智慧 (SharePoint Server 2013) ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |使用 SharePoint Server 2007 建立的 MOSS KPIs，可用於 SharePoint Server 2010，SharePoint Server 2013，以及 SharePoint 伺服器2016。 不過，您無法建立新的 MOSS KPIs。  <br/> |
|Excel 2007  <br/> |在雲端或內部部署) 中 (**Excel** 。 如需概要，請參閱 [Excel 和 Office 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。 <br/><br/> 雲端或內部部署) 中的 **POWER BI** (。 如需簡介，請參閱 [什麼是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |Excel 和 Power BI 都為您的組織提供雲端架構和內部部署解決方案，並支援各種資料來源。  <br/> |
   
### <a name="help-selecting-a-solution"></a>協助您選取解決方案

使用這麼多的 BI 選項時，最好決定哪個選項。 我們有線上指南可提供協助。 請參閱 [選擇 Microsoft 商務智慧 (BI) 工具進行分析與報告](https://go.microsoft.com/fwlink/?linkid=839877)。
  
### <a name="what-if-i-dont-upgrade-now"></a>如果現在不升級，該怎麼辦？

您可以選擇不立即升級。 您的現有伺服器及應用程式會繼續執行。 不過，您不會收到任何更新，包括安全性更新，因為支援已結束。 而且，如果您的伺服器應用程式發生錯誤，您將無法從 Microsoft 技術支援取得協助。
  
## <a name="how-do-i-plan-my-upgrade"></a>如何規劃升級？

在您探索升級選項之後，下一步是準備升級計畫。 下列各節包含有助於的資訊及其他資源。 您有四個主要選項，包括在雲端或內部部署中使用的兩個，以及僅限內部部署的兩個選項：
  
|**選項**|**在雲端或內部部署中？**|
|:-----|:-----|
|[具有 SharePoint Server (內部部署) 的 Excel ](#excel-with-sharepoint-server-on-premises) <br/> |兩者都要  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |兩者都要  <br/> |
|[Reporting Services](#use-reporting-services-on-premises) <br/> |僅內部部署  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |僅內部部署  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>在雲端或內部部署中使用 Excel () 

在 Excel （也稱為「SharePoint Server」中的 *Excel Services* ）中，您可以在瀏覽器視窗中查看和使用活頁簿，即使電腦上並未安裝 excel 也是一樣。 您可以使用 Excel 來建立報表、計分卡和儀表板。 然後，與其他人共用您的活頁簿，使用者可以在瀏覽器中使用 Excel，不論是 Microsoft 365 或內部部署 SharePoint 伺服器都使用 SharePoint 線上。 您可以使用儲存在內部部署或雲端的資料，讓您可以使用各種各樣的資料來源。
  
下表比較使用 Excel 搭配 Microsoft 365 的主要優點，以搭配 SharePoint Server 使用 Excel。 詳細資訊如下。
  
|**在雲端中使用 Microsoft 365 (的 Excel)**|**具有 SharePoint Server (內部部署) 的 Excel**|
|:-----|:-----|
|**您獲得最新、最強大的 Excel 版本**。 使用 Microsoft 365，您會獲得最新版本的 Excel，其中包含強大的新圖表類型、快速快捷地建立圖表和表格的功能，以及支援更多資料來源。 <br/> <br/> **安裝程式會變得更簡單**。 Excel 隨附于 Microsoft 365 for business，所以不需要在您的部分上抬起。 註冊並登入，當您升級內部部署伺服器時，您的執行速度會更快且更有效率。 <br/> <br/> **人們可以隨處存取其活頁簿**。 使用電腦、smart phone 及平板電腦時，使用者可以安全地從任何位置查看活頁簿。 <br/> <br/> **還有更多！** 請參閱 [Excel 和 Office 365 中的 BI 功能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)。 <br/> |**您管理全域設定**。 做為 SharePoint 管理員，您可以指定全域設定，例如安全性、負載平衡、會話管理、活頁簿快取及外部資料連線。 <br/> <br/> **您可以搭配使用 Excel services 與 PerformancePoint 服務**。 您可以將 Excel Services 和 PerformancePoint 服務設定成 SharePoint 伺服器安裝的一部分，並將 Excel Services 報告加入 PerformancePoint 儀表板中。 <br/> <br/> **還有更多！** 請參閱 [excel 和 Excel Services (SharePoint Server 2013) 中的商務智慧 ](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>在雲端中使用 Microsoft 365 (的 Excel) 

如果您移至 Microsoft 365，您將會獲得最新的服務和應用程式，包括 Excel 2016。 PerformancePoint 服務無法在 Microsoft 365 中使用，因此您將使用 Excel 活頁簿或其他報表取代 PerformancePoint 儀表板內容。 好消息是 Excel 2016 具有許多新圖表類型，而且在 Excel 中建立美觀的儀表板比以往更容易。 而且會定期新增新功能。 若要深入瞭解，請參閱 [Excel 2016 For Windows 的新功能](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)。
  
此外，如果您購買50以上的 Microsoft 365，Microsoft FastTrack 小組可以協助您進行設定。 若要深入瞭解，請造訪 [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)。
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>具有 SharePoint Server (內部部署) 的 Excel

如果您升級至較新版本的 SharePoint，您可以在 excel Services 或瀏覽器中使用 Excel，如下所示：
  
- SharePoint Server 2010 中的 Excel Services
    
- SharePoint Server 2013 的 Excel Services
    
- Excel，也就是從 SharePoint Server 2016 分開安裝的 Office Online 伺服器的一部分
    
您也可以在新版本的 SharePoint 伺服器中設定 PerformancePoint 服務，以及搭配 Excel 使用。
  
若要深入瞭解您的 SharePoint 升級選項，請參閱 [SharePoint Server 2007 終止支援藍圖](sharepoint-2007-end-of-support.md)。
  
若要深入瞭解 Excel Services，請參閱 [Excel services 總覽 (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841362)。
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>使用雲端或內部部署中的 Power BI () 

Power BI 是一套商務 analytics 工具，可用於分析資料及共用洞察力。 使用 Power BI，您可以使用內部部署或線上資料來源建立互動報表和儀表板。 人員可以在其電腦或行動裝置上查看和使用您的報表和儀表板。
  
Power BI 不是 Microsoft 365 或 SharePoint 伺服器的一部分。 這是個別的服務，其中包含 Power BI Desktop、Power BI 閘道和 Power BI 服務。 Power BI 也會與 SharePoint 線上整合。 您可以免費開始使用 Power BI。 您可以根據您的資料使用量和業務需求，升級至 Power BI Pro 搭配 Microsoft 365 E5。 若要深入瞭解，請參閱 [什麼是 POWER BI？](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>使用 Reporting Services (內部部署) 

SQL Server Reporting Services 提供強大的報表解決方案。 您可以設定純模式或 SharePoint 整合模式中的 Reporting Services。 您可以使用數種不同的工具來編寫報表，包括報表設計工具、報表產生者及 Power View。 使用最新版的 SQL Server，您也可以使用 SQL Server 行動報告發行者來傳送可擴充至任何畫面大小的報告。 這可讓檢視器使用其行動裝置上的報告。 若要深入瞭解，請參閱 [SQL Server Reporting Services (SSRS) ：建立、部署及管理行動裝置和分頁報告](https://go.microsoft.com/fwlink/?linkid=841342)。
  
### <a name="use-performancepoint-services-on-premises"></a> (內部部署) 使用 PerformancePoint 服務

PerformancePoint Server 2007 是與 SharePoint 伺服器2007分開銷售。 從 SharePoint Server 2010 開始，PerformancePoint 服務是 SharePoint Server 中的服務應用程式。 因此，您不需要購買個別的伺服器授權或硬體，即可使用 PerformancePoint 服務。
  
若要從 PerformancePoint Server 2007 移至 PerformancePoint 服務，您可以移至 SharePoint 伺服器的更新版本，並設定 PerformancePoint 服務。 您要移動的 SharePoint 伺服器版本，會決定您是否可以將現有的儀表板內容從 PerformancePoint Server 2007 匯入 PerformancePoint 服務。
  
- 如果您升級為 SharePoint Server 2010，您可以將 PerformancePoint 儀表板內容從 PerformancePoint Server 2007 匯入 SharePoint Server 2010 中的 PerformancePoint 服務。 若要深入瞭解，請參閱匯 [入嚮導： PerformancePoint server 2007 content to SharePoint server 2010](https://go.microsoft.com/fwlink/?linkid=838873)。
    
- 如果您移至 SharePoint Server 2013 或 SharePoint Server 2016，您很可能需要建立新的儀表板內容， (資料來源、報表、計分卡和儀表板頁面) 。
    
若要開始執行 PerformancePoint 服務升級計畫，請參閱下列資源：
  
- [SharePoint Server 2007 終止支援藍圖](sharepoint-2007-end-of-support.md)
    
- 當您知道要移動的 SharePoint 版本，請參閱 PerformancePoint 服務的對應文章：
    
  - [規劃 PerformancePoint Services (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=841363)
    
  - [SharePoint Server 2013 的 PerformancePoint Services 概觀](https://go.microsoft.com/fwlink/?linkid=841551)
    
  - [SharePoint Server 2016 中的 PerformancePoint Services 概觀](https://go.microsoft.com/fwlink/?linkid=874704)
    
當您升級為 PerformancePoint 服務時，您會收到一些新的功能和增強功能。 PerformancePoint 服務提供改良的計分卡;新的視覺化效果，例如分解樹狀目錄及 KPI 詳細資料包表;其他圖表類型;更好的時間智慧篩選功能;並改進輔助功能規格。 若要深入瞭解，請參閱 [PerformancePoint 服務的新功能 (SharePoint Server 2010) ](https://go.microsoft.com/fwlink/?linkid=841343)。
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>我可以在哪裡取得有關升級的說明？

不論您是在內部部署還是移至 Microsoft 365，我們建議您使用 Microsoft partner。 合格的合作夥伴可協助您找出最符合您的業務需求及協助您部署的解決方案。 請造訪 [Microsoft 合作夥伴中心](https://go.microsoft.com/fwlink/?linkid=841249)，並使用搜尋篩選器尋找解決方案提供者。
  
## <a name="related-topics"></a>相關主題

[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)