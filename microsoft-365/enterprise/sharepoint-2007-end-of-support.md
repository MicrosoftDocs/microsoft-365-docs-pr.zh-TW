---
title: SharePoint Server 2007 終止支援藍圖
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: 在2017年10月10日，SharePoint Server 2007 已結束支援。 在本文中，瞭解升級、遷移和支援選項。
ms.openlocfilehash: c89f150618150e352de476e0a0982fd2d98348e2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688810"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>SharePoint Server 2007 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

在 **2017 年10月 10**日，Microsoft Office SharePoint Server 2007 已到達支援終止。 若尚未開始從 SharePoint Server 2007 遷移至 Microsoft 365 或更新版本的 SharePoint 伺服器內部部署，現在是開始規劃的時間。 本文將詳細說明如何將資料移轉至 SharePoint 線上，或升級 SharePoint 伺服器內部部署的資源。 
  
## <a name="what-does-end-of-support-mean"></a>終止支援是什麼意思？

SharePoint Server （幾乎所有的 Microsoft 產品）都具有支援週期，Microsoft 提供了新功能、bug 修正、安全性修正等等。 產品的生命週期從首次發行日期算起，通常會持續 10 年，而這個生命週期的結束就稱為產品支援結束。 在支援終止時，Microsoft 不再提供：
  
- 可能發生之任何問題的技術支援；
    
- 所發現且可能會影響伺服器穩定性及可用性之問題的錯誤修正。
    
- 已發現並可能導致伺服器遭受安全性破壞之弱點的安全性修正程式。和 
    
- 時區更新。
    
雖然您的 SharePoint Server 2007 伺服器陣列在10月 10 2017 日之後仍會運作，但不會為產品 (（包括安全性修補程式/) 修復程式）提供進一步的更新、修補程式或修復程式，而 Microsoft 支援人員會將其支援工作完全移至較新版本的產品。 因為您的安裝將不再受支援或修補，所以由於支援方法的終止，您應該升級產品或遷移重要資料。
  
> [!TIP]
> 若尚未計畫升級或遷移，請參閱： [SharePoint 2007 遷移選項](sharepoint-2007-migration-options.md)，如需一些開始位置的範例。 您也可以搜尋可協助升級或 Microsoft 365 遷移 (或兩者) 的 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=841249) 。 
  
如需 Office 2007 伺服器達到支援終止的詳細資訊，請參閱 [協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

您的第一個終止應該是 [產品生命週期網站](https://go.microsoft.com/fwlink/?linkid=843148)。 如果您有內部部署的 Microsoft 產品為老化，您應該檢查其支援日期是否結束，如果您的遷移一般需要，則為一年或一個年或後的時間，您可以排程升級或遷移。 當您選擇下一個步驟時，它可能會在產品功能方面有助您瞭解，其品質會變得更好、更好及最適合的考慮。 以下為範例：
  
|**良好**|**更好**|**最佳**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint 混合式  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint 混合式  <br/> |
   
如果您選擇規模低端的選項 (足夠好) ，請記住在完成從 SharePoint Server 2007 遷移後，您必須立即開始規劃升級。 SharePoint Server 2007 的支援 (終止于2017年10月10日。 請注意，這些日期可能會變更，並會檢查 [產品生命週期網站](https://support.microsoft.com/lifecycle)。 ) 
  
## <a name="where-can-i-go-next"></a>下一步可以做什麼？

SharePoint Server 可以在您自己的伺服器上安裝內部部署，也可以使用 SharePoint 線上，也就是 Microsoft 365 的一部分線上服務。 您可以選擇：
  
- 移轉至 SharePoint Online
    
- 升級 SharePoint 伺服器內部部署
    
- 進行上述兩種操作
    
- 實施 [SharePoint 的混合](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) 式解決方案 
    
請留意相關的隱藏成本，以維護伺服器陣列繼續進行、維護或遷移自訂專案，以及升級 SharePoint Server 所依賴的硬體。 如果是必要，請務必使用內部部署 SharePoint 伺服器陣列，否則會帶來必要的回報。否則，如果您在舊版的 SharePoint 伺服器上執行伺服器陣列，但沒有大量自訂，您可以從規劃的遷移受益到線上 SharePoint。
  
> [!IMPORTANT]
> 如果不經常使用 SharePoint 2007 中的內容，則會有另一個選項。 有些 SharePoint 管理員可以選擇建立 Microsoft 365 訂閱、設定全新的全新 SharePoint Online 網站，然後從 SharePoint 2007 中完全移除，只需將最基本的檔放至全新的 SharePoint 線上網站。 從該來源，資料可能會從 SharePoint 2007 網站耗盡成封存。 讓考慮使用者如何使用 SharePoint 2007 安裝的資料。 可以採用創造性的方式來解決此問題！ 
  
|**SharePoint 線上 (SPO) **|**SharePoint Server 內部部署**|
|:-----|:-----|
|高成本的時間 (規劃/執行/驗證)   <br/> |高成本的時間 (規劃/執行/驗證)   <br/> |
|降低基金成本 (未購買硬體)   <br/> |基金 (硬體 + devs/系統管理員的成本較高)   <br/> |
|遷移時成本為一次  <br/> |每個未來遷移重複的單一時間成本  <br/> |
|低擁有權總成本/維護  <br/> |高擁有權總成本/維護  <br/> |
   
當您遷移至 Microsoft 365 時，一次性移動會有較低的成本，而您正在組織資料，並決定要對雲端採取的功能和留下的功能。 不過，將會自動從該點進行升級，您不再需要管理硬體和軟體更新，而且伺服器陣列的時間將由 Microsoft 服務等級協定 ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) 所備份。
  
### <a name="migrate-to-sharepoint-online"></a>移轉至 SharePoint Online

請務必查閱相關聯的服務說明，以確定 SharePoint 線上具有您所需的所有功能。 請參閱 [Microsoft 365 和 Office 365 服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)。
  
沒有直接的方法可以從 SharePoint 2007 遷移至 SharePoint 線上;您的移動至 SharePoint 線上將會手動執行。 如果您升級為 SharePoint Server 2013 或 SharePoint Server 2016，您的移動可能也會涉及使用 SharePoint 遷移 API (將資訊遷移至商務 OneDrive （例如) ）。
  
|**線上專業人員**|**線上 Con**|
|:-----|:-----|
|Microsoft 提供 SPO 硬體和所有硬體管理。  <br/> |SharePoint Server 內部部署和 SPO 之間可用的功能可能會有所不同。  <br/> |
|您是訂閱的全域系統管理員，而且可以指派系統管理員 SPO 網站。  <br/> |SharePoint Server 內部部署中的伺服器陣列管理員可使用的部分動作不存在 (或不是必要) 包含在 Microsoft 365 的 SharePoint 系統管理員角色中。  <br/> |
|Microsoft 會對底層的硬體和軟體套用修補程式、修正及更新。  <br/> |由於服務沒有存取基礎檔案系統，因此某些自訂專案有限。  <br/> |
|Microsoft 發佈 [服務等級協定](https://go.microsoft.com/fwlink/?linkid=843153) ，並快速移動以解決服務等級事件。  <br/> |備份與還原和其他修復選項會透過服務自動覆寫 SharePoint 線上備份會覆寫（如果不使用）。  <br/> |
|安全性測試和伺服器效能調整是由 Microsoft 在服務中持續執行。  <br/> |變更使用者介面及其他 SharePoint 功能會由服務安裝，而且可能需要切換開啟或關閉。  <br/> |
|Microsoft 365 符合許多行業標準： [microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165)。  <br/> |遷移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)協助是有限的。  <br/> 大部分的升級是手動或透過 [SharePoint 線上和 OneDrive 遷移內容藍圖](https://go.microsoft.com/fwlink/?linkid=843184)中所述的 SPO 遷移 API。  <br/> |
|Microsoft 支援工程師和資料中心內的員工都沒有無限制的系統管理員存取您的訂閱。  <br/> |若需要升級硬體基礎結構以支援較新版本的 SharePoint，或若升級需要次要伺服器陣列，可能會有額外的成本。  <br/> |
|合作夥伴可協助您將資料移轉到線上 SharePoint 的單一時間工作。  <br/> ||
|線上產品會自動更新整個服務的意義，但功能可能會取代，而且不會有真正的支援端點。  <br/> ||
   
如果您決定建立新的 Microsoft 365 網站，並在需要時手動將資料移轉到它，您可以查看您的 [Microsoft 365 選項](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>升級 SharePoint 伺服器內部部署

過去沒有任何方法可以略過 SharePoint 升級的版本，至少不會在發行 SharePoint Server 2016。 這表示升級順序如下：
  
- SharePoint 2007 \> SharePoint server 2010 \> SharePoint server 2013 \> SharePoint server 2016
   
若要從 SharePoint 2007 到 SharePoint Server 2016 的完整途徑，將會帶來大量的時間，而且在升級的硬體方面需要成本 (請注意，SQL server 也必須升級) 、軟體和管理。 根據功能的重要性，必須升級或放棄自訂專案。
  
> [!NOTE]
> 您可以維持生命週期的 SharePoint 2007 伺服器陣列，在新的硬體 (上安裝 SharePoint 伺服器2016伺服器陣列，讓個別的伺服器陣列執行並列) ，然後規劃並執行手動遷移內容 (，以下載及重新上傳內容，例如) 。 請注意，手動移動的部分陷阱 (例如，移動檔會以執行手動移動) 之帳戶的別名取代最後一個修改的帳戶，而必須在 (時間之前完成的工作，例如重新建立網站、子網站、許可權和清單結構) 。 同樣地，這是考慮您可以移至儲存體或不再需要的資料，可降低遷移影響的動作。
  
無論是哪種方式，在升級之前先清理您的環境。 請確定您的現有伺服器陣列在升級之前是否運作正常，並在您解除委任之前 (以確認) ！ 
  
請記得查看 **支援和不支援的升級路徑**： 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
如果您有 **自訂**，請務必為遷移路徑中的每個步驟規劃升級： 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**內部部署 Pro**|**內部部署 Con**|
|:-----|:-----|
|完全控制 SharePoint 伺服器陣列的所有層面，從伺服器硬體向上。  <br/> |所有中斷和修正都是貴公司 (若您的產品並非支援服務，請與付費的 Microsoft 支援人員接洽) ：  <br/> |
|SharePoint Server 內部部署的完整功能集合，具有透過混合方式將內部部署伺服器陣列連線至 SharePoint Online 訂閱的選項。  <br/> |升級、修補程式、安全性修正程式，以及 SharePoint 伺服器的所有維護都受內部部署管理。  <br/> |
|取得更佳自訂的完整存取權。  <br/> |[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165) 必須手動設定內部部署。  <br/> |
|在您的內部部署 (所執行的安全性測試和伺服器效能調整，都是由您的控制) 。  <br/> |Microsoft 365 可能使 SharePoint 線上使用的功能無法與內部部署 SharePoint 伺服器互動  <br/> |
|合作夥伴可協助您將資料移轉至下一版的 SharePoint Server (且超過) 。  <br/> |您的 SharePoint 伺服器網站不會自動使用 SharePoint Online 中所看到 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 憑證。  <br/> |
|在內部部署中 SharePoint Server 內部部署命名慣例、備份與還原及其他復原選項的完整控制權。  <br/> |SharePoint Server 內部部署對產品生命週期保密。  <br/> |
   
### <a name="upgrade-resources"></a>升級資源

請先知道您符合硬體和軟體需求，然後再遵循支援的升級方法。
  
- **硬體/軟體需求**： 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **軟體界限和限制**： 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- 下列專案**的升級程式概述**： 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 與內部部署之間建立 SharePoint 的混合式解決方案

如果您對遷移的答案是在內部部署所提供的自我控制之間的某個地方，而且 SharePoint Online 提供的擁有成本較低，您可以透過混合方式，將 SharePoint Server 2013 或2016伺服器陣列連線至 SharePoint。 [深入瞭解 SharePoint 混合式解決方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
如果您決定混合式 SharePoint 伺服器陣列將會對您的業務帶來好處，請熟悉現有的混合式類型，以及如何設定內部部署 SharePoint 伺服器陣列與 Microsoft 365 訂閱之間的連線。
  
| 選項 | 描述 |
|:-----|:-----|
[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165)。  <br/> |遷移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)協助是有限的。  <br/> 大部分的升級是手動或透過 [SharePoint 線上和 OneDrive 遷移內容藍圖](https://go.microsoft.com/fwlink/?linkid=843184)中所述的 SPO 遷移 API。  <br/> |
|Microsoft 支援工程師和資料中心內的員工都沒有無限制的系統管理員存取您的訂閱。  <br/> |若需要升級硬體基礎結構以支援較新版本的 SharePoint，或若升級需要次要伺服器陣列，可能會有額外的成本。  <br/> |
|合作夥伴可協助您將資料移轉到線上 SharePoint 的單一時間工作。  <br/> ||
|線上產品會自動更新整個服務的意義，但功能可能會取代，而且不會有真正的支援端點。  <br/> ||
   
如果您決定建立新的 Microsoft 365 網站，並在需要時手動將資料移轉到它，您可以查看您的 [Microsoft 365 選項](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>升級 SharePoint 伺服器內部部署

過去沒有任何方法可以略過 SharePoint 升級的版本，至少不會在發行 SharePoint Server 2016。 這表示升級順序如下：
  
- SharePoint 2007 \> SharePoint server 2010 \> SharePoint server 2013 \> SharePoint server 2016
   
若要從 SharePoint 2007 到 SharePoint Server 2016 的完整途徑，將會帶來大量的時間，而且在升級的硬體方面需要成本 (請注意，SQL server 也必須升級) 、軟體和管理。 根據功能的重要性，必須升級或放棄自訂專案。
  
> [!NOTE]
> 您可以維持生命週期的 SharePoint 2007 伺服器陣列，在新的硬體 (上安裝 SharePoint 伺服器2016伺服器陣列，讓個別的伺服器陣列執行並列) ，然後規劃並執行手動遷移內容 (，以下載及重新上傳內容，例如) 。 請注意，手動移動的部分陷阱 (例如，移動檔會以執行手動移動) 之帳戶的別名取代最後一個修改的帳戶，而必須在 (時間之前完成的工作，例如重新建立網站、子網站、許可權和清單結構) 。 同樣地，這是考慮您可以移至儲存體或不再需要的資料，可降低遷移影響的動作。
  
無論是哪種方式，在升級之前先清理您的環境。 請確定您的現有伺服器陣列在升級之前是否運作正常，並在您解除委任之前 (以確認) ！ 
  
請記得查看 **支援和不支援的升級路徑**： 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
如果您有 **自訂**，請務必為遷移路徑中的每個步驟規劃升級： 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**內部部署 Pro**|**內部部署 Con**|
|:-----|:-----|
|完全控制 SharePoint 伺服器陣列的所有層面，從伺服器硬體向上。  <br/> |所有中斷和修正都是貴公司 (若您的產品並非支援服務，請與付費的 Microsoft 支援人員接洽) ：  <br/> |
|SharePoint Server 內部部署的完整功能集合，具有透過混合方式將內部部署伺服器陣列連線至 SharePoint Online 訂閱的選項。  <br/> |升級、修補程式、安全性修正程式，以及 SharePoint 伺服器的所有維護都受內部部署管理。  <br/> |
|取得更佳自訂的完整存取權。  <br/> |[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165) 必須手動設定內部部署。  <br/> |
|在您的內部部署 (所執行的安全性測試和伺服器效能調整，都是由您的控制) 。  <br/> |Microsoft 365 可能使 SharePoint 線上使用的功能無法與內部部署 SharePoint 伺服器互動  <br/> |
|合作夥伴可協助您將資料移轉至下一版的 SharePoint Server (且超過) 。  <br/> |您的 SharePoint 伺服器網站不會自動使用 SharePoint Online 中所看到 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 憑證。  <br/> |
|在內部部署中 SharePoint Server 內部部署命名慣例、備份與還原及其他復原選項的完整控制權。  <br/> |SharePoint Server 內部部署對產品生命週期保密。  <br/> |
   
### <a name="upgrade-resources"></a>升級資源

請先知道您符合硬體和軟體需求，然後再遵循支援的升級方法。
  
- **硬體/軟體需求**： 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **軟體界限和限制**： 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- 下列專案**的升級程式概述**： 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 與內部部署之間建立 SharePoint 的混合式解決方案

如果您對遷移的答案是在內部部署所提供的自我控制之間的某個地方，而且 SharePoint Online 提供的擁有成本較低，您可以透過混合方式，將 SharePoint Server 2013 或2016伺服器陣列連線至 SharePoint。 [深入瞭解 SharePoint 混合式解決方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
如果您決定混合式 SharePoint 伺服器陣列將會對您的業務帶來好處，請熟悉現有的混合式類型，以及如何設定內部部署 SharePoint 伺服器陣列與 Microsoft 365 訂閱之間的連線。
  
若要瞭解其運作方式的一個好方法是建立 Microsoft 365 開發/測試環境，您可以使用 [測試實驗室指南](m365-enterprise-test-lab-guides.md)加以設定。 當您擁有試用版或購買的 Microsoft 365 訂閱後，您就可以在 SharePoint Online 中建立網站集合、網站及文件庫，以透過使用遷移 API 的方式手動遷移資料 (或-如果您想要透過混合式的嚮導) 將「我的網站」內容遷移至 OneDrive。
  
> [!NOTE]
> 請記住，您的 SharePoint 2007 伺服器陣列將需要升級為 SharePoint Server 2013 或 SharePoint Server 2016，以使用混合選項 
  
## <a name="related-topics"></a>相關主題

[疑難排解並繼續升級 (Office SharePoint Server 2007) ](https://go.microsoft.com/fwlink/?linkid=843192)
  
[ (SharePoint Server 2010 的升級問題疑難排解) ](https://go.microsoft.com/fwlink/?linkid=843194)
  
[在 SharePoint 2013 中針對資料庫的升級問題進行疑難排解](https://go.microsoft.com/fwlink/?linkid=843195)
  
[搜尋 Microsoft 合作夥伴以協助升級](https://go.microsoft.com/fwlink/?linkid=841249)
  
[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)
  

