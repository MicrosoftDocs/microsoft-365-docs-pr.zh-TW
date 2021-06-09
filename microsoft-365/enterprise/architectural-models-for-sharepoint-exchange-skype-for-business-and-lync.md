---
title: 適用於 SharePoint、Exchange、商務用 Skype 和 Lync 的架構模型
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: 取得描述 SharePoint、Exchange、商務用 Skype 和 Lync 的架構模型、部署和平臺選項的 IT 海報。
ms.openlocfilehash: 6c8aea1f6389c5007adb1800639488972483d5fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905509"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>適用於 SharePoint、Exchange、商務用 Skype 和 Lync 的架構模型

本文中的 IT 海報說明 SharePoint、Exchange、商務用 Skype 和 Lync 的架構模型和部署選項。 它們也提供在 Microsoft Azure 中部署 SharePoint 的設計資訊。
  
透過使用 Microsoft 365，您可以透過雲端提供熟悉的共同作業和通訊服務。 使用一些例外狀況，不論是維護內部部署還是使用 Microsoft 365，使用者經驗都會保持不變。 

這種統一的使用者體驗會使每個工作負載的位置變複雜。 此外，它也會引發一些問題：
  
- 如何選擇個別工作負載的平臺？
    
- 是否應該保留任何內部部署服務？
    
- 混合式部署適用的情況為何？
    
- Azure 如何適應圖片？
    
- Azure 支援的 Office server 工作負載設定為何？
    
> [!TIP]
> 本文中的大部分海報都有多種語言版本。 可用的語言包括中文、英文、法文、德文、義大利文、日文、韓文、葡萄牙文、俄文及西班牙文。 若要下載下列其中一種語言的海報，請在海報縮圖圖像下，選取 [ **其他語言**]。
  
讓我們知道您的心得！請傳送電子郵件給我們：[cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com)。 
  
使用下列連結可取得所需的海報：
  
- **架構模型**：使用這些資源來判斷 SharePoint 2016 和商務用 Skype 2015 的理想平臺和設定。
    
  - [Microsoft SharePoint 2016 架構模型](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint伺服器2016資料庫](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft 商務用 Skype 2015 架構模型](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **平臺**：使用這些資源來判斷 SharePoint 2013、Exchange 2013 和 Lync 2013 的理想平臺和設定。
    
  - [SharePoint 2013 平臺選項](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013 平臺選項](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013 平臺選項](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **在 azure 中 SharePoint Server 2013**：使用這些 IT 海報，在 azure 基礎結構服務中設計及設定 SharePoint Server 2013 工作負載。
    
  - [Azure 中使用 SharePoint Server 2013 的網際網路網站](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [設計範例： Azure 中用於 SharePoint 2013 的網際網路網站](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [將嚴重損壞修復至 Azure SharePoint](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>架構模型海報

SharePoint 2016 和商務用 Skype 2015 的 IT 海報，可提供一種方式，以輕鬆列印的格式來比較部署方法。 海報會列出所有設定或平臺選項。 每個選項都提供下列資訊：
  
- **概覽**：平臺的簡短摘要，包括概念圖表。
    
- **最** 適合：適合平臺的常見案例。
    
- **授權需求**：部署所需的授權。
    
- **架構任務**：您需要做為架構師的決策。
    
- **It 專業** 人員的工作或責任：您的 it 人員需要規劃的每日責任。
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 架構模型

|項目|描述|
|---|---|
|[![SharePoint Server 2016 架構模型海報的縮圖。](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=52650)|這種 IT 海報描述 business 決策者和解決方案架構設計人員所需瞭解的 SharePoint 線上、Azure 及 SharePoint 內部部署設定。 <br/><br/> - **SharePoint Online (SaaS)**：透過軟體作為服務 SharePoint (SaaS 訂閱模型。 <br/> - **SharePoint 混合**：以您自己的節奏將 SharePoint 的網站和應用程式移至雲端。 <br/> - **azure (中的 SharePoint IaaS)**：將內部部署環境擴充至 Azure，然後在此部署 SharePoint 2016 伺服器。  (此模型是高可用性或嚴重損壞修復環境和開發/測試環境的建議。 )  <br/> - **SharePoint 內部部署**：在您維護的資料中心內計畫、部署、維護和自訂您的 SharePoint 環境。|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016 資料庫

|項目|描述|
|---|---|
|[![SharePoint Server 2016 資料庫海報的縮圖。](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=55041)|這種 IT 海報是 SharePoint Server 2016 資料庫的快速參考。 您將會看到每個資料庫的詳細資料： <br/><br/> - 大小 <br/> - 調整大小指導方針 <br/> - I/O 模式 <br/> - 需求： <br/><br/>  第一頁顯示 SharePoint 系統資料庫和具有多個資料庫的服務應用程式。 第二頁會顯示所有只有單一資料庫的服務應用程式。 <br/><br/>  如需詳細資訊，請參閱[SharePoint Server 2016 中的資料庫類型和描述](/SharePoint/technical-reference/database-types-and-descriptions)。|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft 商務用 Skype 2015 架構模型

|項目|描述|
|---|---|
|[![商務用 Skype 架構模型海報的縮圖。](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=55022)|此海報說明 (PBX) 商務用 Skype 線上、內部部署、混合和雲端私人分支 exchange。 此外，它也會說明公司決策者和解決方案架構設計人員必須瞭解的 Exchange 和 SharePoint 設定的整合。 <br/><br/> 海報適用于 IT 專業人員，其可讓您在線上及商務用 Skype 內部部署商務用 Skype 使用的基礎架構模型，提高知名度。 <br/><br/>請從最符合貴組織需求和方案的設定著手。 視需要考慮和使用其他設定。 例如，您可能想要考慮與 Exchange 和 SharePoint 或利用 Microsoft cloud PBX 產品的解決方案進行整合。|
   
## <a name="platform-options-posters"></a>平台選項海報

SharePoint 2013、Exchange 2013 和 Lync 2013 的 IT 海報提供一種方法，讓您快速比較部署方法。 每個海報都會列出所有設定或平臺選項。 它會針對每個選項提供下列資訊：
  
- **概覽**：平臺的簡短摘要，包括概念圖表。
    
- **最** 適合：適合平臺的常見案例。
    
- **授權需求**：部署所需的授權。
    
- **架構任務**：您需要做為架構師的決策。
    
- **It 專業** 人員的工作或責任：您的 it 人員需要規劃的每日責任。
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013 平台選項

|項目|描述|
|---|---|
|[![SharePoint 2013 平臺選項海報的縮圖影像。](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=40332)|若為商務決策者和架構師，此海報會顯示 SharePoint 2013 的平臺選項，SharePoint Microsoft 365 中的內部部署混合 Microsoft 365、Azure 及僅限內部部署的部署。 它包含每個架構、建議、授權需求的概述，以及每個平臺的架構設計人員和 IT 專業人員工作。 海報著重于 Azure 上的數個 SharePoint 解決方案。|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013 平台選項

|項目|描述|
|---|---|
|[![Exchange 平臺選項海報的縮圖影像。](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=42676)|針對商務決策者和架構師，此海報說明 Exchange 2013 的平臺選項。 客戶可以選擇 Microsoft 365、混合式 Exchange、Exchange Server 內部部署和主控 Exchange 的 Exchange Online。 海報詳述每個架構選項，包含每個架構的特別案例、授權需求和 IT 專業人員責任。|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013 平台選項

|項目|描述|
|---|---|
|[![Lync 2013 平臺選項海報的縮圖影像。](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=41677)|針對商務決策者和架構師，此海報說明 Lync 2013 的平臺選項。 客戶可以選擇 Microsoft 365、混合式 lync、lync Server 內部部署和主控 lync 的 lync Online。 IT 海報詳述每個架構選項，包括每個架構選項的理想案例、授權需求和 IT 專業人員責任。|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Azure 解決方案海報內的 SharePoint

azure 中 SharePoint 的 IT 海報顯示使用 SharePoint Server 2013 的 Azure 架構解決方案。
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>使用 SharePoint Server 2013 Microsoft Azure 中的網際網路網站

|項目|描述|
|---|---|
|[![Azure 中使用 SharePoint Server 2013 海報的網際網路網站影像。](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=41992)|此海報概括列出 Azure 中面向網際網路的網站的重要設計活動和建議架構。  <br/><br/> 如需詳細資訊，請參閱下列文章：  <br/><br/> - [Azure 中使用 SharePoint Server 2013 的網際網路網站](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 2013 的 Azure 架構](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Azure 中用於 SharePoint 2013 的網際網路網站

|項目|描述|
|---|---|
|[![SharePoint Server 2013 海報 Microsoft Azure 中的網際網路網站影像。](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=41991)|使用此設計範例做為您在 Azure 中使用 SharePoint Server 2013 的網際網路對向網站架構的起點。 <br/><br/> 如需詳細資訊，請參閱下列文章：  <br/><br/> - [Azure 中使用 SharePoint Server 2013 的網際網路網站](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 2013 的 Azure 架構](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>對於 Microsoft Azure 的 SharePoint 災害復原

|項目|描述|
|---|---|
|[![用於 Azure 的 SharePoint 嚴重損壞修復程式的海報影像。](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [更多語言](https://www.microsoft.com/download/details.aspx?id=41993)|此 IT 海報說明 Azure 中的嚴重損壞修復環境的架構原則。 <br/><br/> 如需詳細資訊，請參閱下列文章：  <br/><br/> - [SharePointAzure 中的伺服器2013災難修復](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [SharePoint 2013 的 Azure 架構](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>另請參閱

- [Microsoft 365 解決方案與架構中心](../solutions/index.yml)
  
- [Microsoft 雲端架構模式](../solutions/cloud-architecture-models.md)
  
- [測試實驗室指南 Microsoft 365](m365-enterprise-test-lab-guides.md)
  
- [混合式解決方案](hybrid-solutions.md)