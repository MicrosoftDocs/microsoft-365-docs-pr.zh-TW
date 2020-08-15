---
title: 從 SharePoint 2010 升級
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: 尋找要從 SharePoint 2010 和 Sharepoint Server 2010 升級的資訊和資源，以支援在10月13日2020上進行。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57e44cf14a74f6a5a2098512e0a2339037d70655
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688247"
---
# <a name="upgrading-from-sharepoint-2010"></a>從 SharePoint 2010 升級

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft SharePoint 2010 和 SharePoint Server 2010 會在 **年4月 13 2021 日**到達支援的支援。 本文將詳細說明如何在 Microsoft 365 中將現有的 SharePoint 伺服器2010資料移轉至 SharePoint 線上，或升級內部部署 SharePoint Server 2010 環境。
  
## <a name="what-is-end-of-support"></a>什麼是支援終止？

當您的 SharePoint Server 2010 和 SharePoint Foundation 2010 軟體達到其支援週期的結尾時 (Microsoft 提供新功能、bug 修正、安全性修正等) 時，這稱為軟體的「支援終止」，或有時候是「退休」。 在支援的 (或 EOS) 產品時，實際上沒有任何實際關機或停止運作;不過，軟體支援結束時，Microsoft 不再提供：
  
- 可能發生之任何問題的技術支援；
    
- 所發現且可能會影響伺服器穩定性及可用性之問題的錯誤修正。
    
- 所發現且可能會讓伺服器容易受到安全性威脅之弱點的安全性修正。
    
- 時區更新。
    
這表示，將不會為產品 (（包括安全性修補程式/修正) ）提供進一步的更新、修補程式或修正，而且 Microsoft 支援人員會將其支援工作完全移至較新的版本。 在支援 SharePoint Server 2010 方法之後，您應該充分利用機會，以在升級產品及/或遷移重要資料之前，裁切您不再需要的資料。
  
> [!NOTE]
> 軟體生命週期一般會從產品的初始發行日期起10年。 您可以搜尋 [microsoft 的解決方案提供者](https://go.microsoft.com/fwlink/?linkid=841249) ，以協助升級至下一個版本的軟體，或搭配 microsoft 365 遷移 (或兩者) 。 請務必注意，您已知道重要基礎技術的支援日期，尤其是您用 SharePoint 所用的 SQL Server 版本。 請參閱 [固定生命週期原則](https://support.microsoft.com/help/14085) ，以瞭解產品生命週期的詳細資料。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

首先，檢查 [產品生命週期網站](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)上的支援結束日期。 接下來，請務必在此日期的知識中規劃升級或遷移時間。 請記住，您的產品不會在列出的日期  *停止運作*  ，而且您可以繼續使用，但由於在該日期之後將不再修補您的安裝，因此您將需要可協助您更順利轉換至產品的下一版本的策略。 
  
此矩陣可協助您在遷移產品功能和使用者資料時，繪製課程：
  
| 支援產品的結束 | 良好 | 最佳 |
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013 (內部部署)   <br/> |SharePoint Online  <br/> |
||SharePoint Server 2013 與 SharePoint 線上混合  <br/> |SharePoint Server 2016 (內部部署)   <br/> |
| | |SharePoint 雲端混合式搜尋  <br/> |
   
如果您選擇 [比例下限] 上的 [選項] (好的選項) ，當您從 SharePoint Server 2010 遷移完成後，您必須立即開始規劃其他升級。 

您可以採取三個路徑，以避免 SharePoint Server 2010 的支援結束。

![SharePoint Server 2010 升級路徑](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

>[!Note]
>SharePoint Server 2010 和 SharePoint Foundation 2010 的支援終止于4月13日的2021，但 *請注意* ，您應該時刻檢查 [產品生命週期網站](https://support.microsoft.com/lifecycle) 的最新日期。
>

  
## <a name="where-should-i-go-next"></a>下一步應該在哪裡？

SharePoint Server 2013 和 SharePoint Foundation 2013 可以在您自己的伺服器上安裝內部部署。 否則，您可以使用 SharePoint 線上，也就是 Microsoft Microsoft 365 的一部分線上服務。 您可以選擇：
  
- 移轉至 SharePoint Online
    
- 升級 SharePoint Server 或 SharePoint Foundation 內部部署
    
- 進行上述兩種操作
    
- 實施 [SharePoint 的混合](https://docs.microsoft.com/sharepoint/hybrid/hybrid) 式解決方案 
    
請留意相關的隱藏成本，以維護伺服器陣列繼續進行、維護或遷移自訂專案，以及升級 SharePoint Server 所依賴的硬體。 如果您已意識到以上所有事項，則繼續升級內部部署會比較容易。 否則，如果您在舊版的 SharePoint 伺服器上執行伺服器陣列，但沒有大量自訂，您可以從規劃的遷移受益至線上 SharePoint。 您也可以在內部部署 SharePoint 伺服器環境中，將一些資料放在 SharePoint Online 中，以減少保留所有內部部署資料的硬體管理數量。 將一些資料移至 SharePoint 線上時可能更經濟。
  
> [!NOTE]
> SharePoint 系統管理員可以建立 Microsoft 365 訂閱、設定全新 SharePoint Online 網站，然後從 SharePoint Server 2010 完全移除，以將最基本的檔只放至全新的 SharePoint 線上網站。 從這裡開始，任何剩餘的資料都可能從 SharePoint Server 2010 網站耗盡為內部部署封存。 
  
|**SharePoint Online**|**SharePoint Server 內部部署**|
|:-----|:-----|
|高成本的時間 (規劃/執行/驗證)   <br/> |高成本的時間 (規劃/執行/驗證)   <br/> |
|降低基金成本 (未購買硬體)   <br/> |基金 (購買硬體) 更高成本  <br/> |
|遷移時成本為一次  <br/> |每個未來遷移重複的單一時間成本  <br/> |
|低擁有權總成本/維護  <br/> |高擁有權總成本/維護  <br/> |
   
當您遷移至 Microsoft 365 時，一次的移動會在規劃資料和決定要對雲端進行的工作時，以及決定要在) 進行的工作時，花更長的時間進行規劃、前期 (。 不過，當您的資料移轉後，就會自動從該點進行升級，因為您不再需要管理軟硬體更新，而且伺服器陣列的時間將由 Microsoft 服務等級協定 ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) 所備份。
  
### <a name="migrate-to-sharepoint-online"></a>移轉至 SharePoint Online

請確定 SharePoint 線上提供您所需的所有功能，方法是檢查其 [服務描述](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)。
  
目前尚無任何方式可以直接從 SharePoint Server 2010 (或 SharePoint Foundation 2010) 遷移，以 SharePoint 線上，所以許多工作是手動進行的。 這可讓您有機會在移動之前封存及修剪不再需要的資料和網站。 您可以將其他資料封存到儲存體。 另外請記住，SharePoint Server 2010 和 SharePoint Foundation 2010 都不會在支援結束時停止運作，所以管理員可以有一個句點，在此期間，如果客戶忘記移動某些資料，SharePoint 仍會執行。
  
如果您升級為 SharePoint Server 2013 或 SharePoint Server 2016，並決定將資料放入 SharePoint 線上，您的移動也可能會涉及使用 [SharePoint 遷移 API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) (，將資訊遷移至 OneDrive 的商務) 。 
  
|**SharePoint 線上優勢**|**SharePoint 線上缺點**|
|:-----|:-----|
|Microsoft 提供 SPO 硬體和所有硬體管理。  <br/> |SharePoint Server 內部部署和 SPO 之間可用的功能可能會有所不同。  <br/> |
|您是訂閱的全域系統管理員，而且可能會指派管理員來 SPO 網站。  <br/> |在 Microsoft SharePoint Server 內部部署中，伺服器陣列管理員可使用的部分動作不存在 (或不是必要) 在 Microsoft 365 的 SharePoint 系統管理員角色中，但 SharePoint 管理、網站集合管理，以及網站擁有權是您的組織當地的地方。  <br/> |
|Microsoft 會對底層硬體和軟體 (套用修補程式、修正及更新，包括 SharePoint 線上執行) 的 SQL server。  <br/> |由於服務沒有存取基礎檔案系統，因此某些自訂專案有限。  <br/> |
|Microsoft 發佈 [服務等級協定](https://go.microsoft.com/fwlink/?linkid=843153) ，並快速移動以解決服務等級事件。  <br/> |備份與還原和其他修復選項會透過服務自動覆寫 SharePoint 線上備份會覆寫（如果不使用）。  <br/> |
|安全性測試和伺服器效能調整是由 Microsoft 在服務中持續執行。  <br/> |變更使用者介面及其他 SharePoint 功能會由服務安裝，而且可能需要切換開啟或關閉。  <br/> |
|Microsoft 365 符合許多行業標準： [microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165)。  <br/> |遷移的[FastTrack](https://go.microsoft.com/fwlink/?linkid=518597)協助是有限的。  <br/> 大部分的升級是手動或透過 [SharePoint 線上和 OneDrive 遷移內容藍圖](https://go.microsoft.com/fwlink/?linkid=843184)中所述的 SPO 遷移 API。  <br/> |
|Microsoft 支援工程師和資料中心內的員工都沒有無限制的系統管理員存取您的訂閱。  <br/> |若需要升級硬體基礎結構以支援較新版本的 SharePoint，或若升級需要次要伺服器陣列，可能會有額外的成本。  <br/> |
|解決方案供應商可以協助一次將您的資料移轉至 SharePoint 線上的工作。  <br/> |您的控制項內並未 SharePoint 線上的所有變更。 遷移後，功能表、文件庫和其他功能的設計差異可能會暫時影響可用性。  <br/> |
|線上產品會自動更新整個服務的意義，但功能可能會取代，而且不會有真正的支援生命週期的結束。  <br/> |SharePoint Server (或 SharePoint Foundation) 以及基礎 SQL server 的支援週期已結束。  <br/> |
   
如果您決定建立新的 Microsoft 365 網站，並在需要時手動將資料移轉到它，您可以查看您的 [Microsoft 365 選項](https://www.microsoft.com/microsoft-365/)。
  

  
### <a name="upgrade-sharepoint-server-on-premises"></a>升級 SharePoint 伺服器內部部署

到目前為止 SharePoint 內部部署產品的最新版本 (SharePoint Server 2019) ，SharePoint 伺服器升級必須  *連續*進行，這表示您無法從 SharePoint server 2010 升級為 SharePoint 伺服器2016，也無法直接 SharePoint 2019。 
  
串列升級路徑： 

- SharePoint Server 2010 \> SharePoint server 2013 \> SharePoint server 2016
   
如果您選擇追蹤從 SharePoint 2010 到 SharePoint 伺服器2016的整個路徑，這將需要一些時間與進行規劃。 升級在升級的硬體方面需要成本 (請注意，SQL server 也必須升級) 、軟體和管理。 此外，可能需要升級自訂專案，或甚至放棄自訂專案。 請務必先收集所有重要自訂專案的附注，再升級 SharePoint 伺服器陣列。
  
> [!NOTE]
> 您可以維持 SharePoint 2010 伺服器陣列的支援，在新的硬體 (上安裝 SharePoint 伺服器2016伺服器陣列，讓個別的伺服器陣列執行並列) ，然後規劃並執行手動遷移內容 (，以下載及重新上傳內容，例如) 。 這些手動移動會有可能的缺陷 (例如，來自2010的檔具有目前最後一個修改過的帳戶，且具有執行手動移動) 之帳戶的別名，而且某些工作必須在 (重新建立網站、子網站、許可權和清單結構) 的時間之前完成。 最好是考慮哪些資料可以移至儲存區，或不再需要。 這可減少遷移的影響。 無論是哪種方式，在升級之前先清理您的環境。 請確定您的現有伺服器陣列在升級之前是否運作正常，並在您解除委任之前 (以確認) ！ 
  
請記得查看 **支援和不支援的升級路徑**： 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
如果您有 **自訂**，請務必為遷移路徑中的每個步驟規劃升級： 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**內部部署優勢**|**內部部署缺點**|
|:-----|:-----|
|完全控制 SharePoint 伺服器陣列的所有層面 (及其 SQL) 從伺服器硬體向上。  <br/> |所有中斷和修正都是貴公司 (的責任，但是如果您的產品並非支援，您可以接洽「付費的 Microsoft 支援」) ：  <br/> |
|SharePoint Server 內部部署的完整功能集合，具有透過混合方式將內部部署伺服器陣列連線至 SharePoint Online 訂閱的選項。  <br/> |升級、修補程式、安全性修正程式、硬體升級，以及 SharePoint 伺服器的所有維護，而且其 SQL 伺服器陣列都是在內部部署管理。  <br/> |
|自訂選項的完整存取權，與 SharePoint 線上的功能更高。  <br/> |[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165) 必須手動設定內部部署。  <br/> |
|您的內部部署 (在您的控制項) 上進行安全性測試和伺服器效能調整。  <br/> |Microsoft 365 可能使 SharePoint 線上使用的功能無法與內部部署 SharePoint 伺服器互動  <br/> |
|解決方案供應商可以協助將資料移轉至下一個版本的 SharePoint Server (，但超過) 。  <br/> |您的 SharePoint 伺服器網站不會自動使用 SharePoint Online 中所看到 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 憑證。  <br/> |
|在內部部署中 SharePoint Server 內部部署命名慣例、備份與還原及其他復原選項的完整控制權。  <br/> |SharePoint Server 內部部署對產品生命週期保密。  <br/> |
   
### <a name="upgrade-resources"></a>升級資源

請先比較硬體和軟體需求。 如果您在目前的硬體上沒有符合升級的基本需求，這可能表示您必須先升級伺服器陣列或 SQL server 中的硬體，否則您可能會決定將部分的網站移至 SharePoint 線上的「長綠」硬體。 進行評估之後，請遵循支援的升級路徑和方法。
  
- **硬體/軟體需求**： 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **軟體界限和限制**： 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- 下列專案**的升級程式概述**： 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-sharepoint-server-on-premises"></a>在 SharePoint 線上和 SharePoint 伺服器內部部署之間建立 SharePoint 的混合式解決方案

另一個選項 (可能是內部部署和線上世界的最佳方式，以供部分遷移需求) 混合式，您可以將 SharePoint Server 2013 或2016或2019伺服器陣列連線至 SharePoint 線上，以建立 SharePoint 混合式： [深入瞭解 SharePoint 混合式解決方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)。
  
如果您決定混合式 SharePoint 伺服器陣列是您的遷移目標，請務必規劃應該在線上中移動的網站和使用者，以及必須保留內部部署的網站和使用者。 檢查和排名您的 SharePoint 伺服器陣列內容， (判斷對公司的高、中或低影響的資料，) 對您作出這項決策都有説明。 您可能只需要與 SharePoint Online 共用 () 的使用者帳戶來登入，而 (b) SharePoint 伺服器搜尋索引--則在您查看網站的使用方式之前，可能不會有任何明確的做法。 如果您的公司後來決定將您的所有內容遷移至 SharePoint 線上，您可以將所有剩餘的帳戶和資料線上移動，並解除委任您的內部部署伺服器陣列，而且 SharePoint 伺服器陣列的管理/管理將透過從該點開始的 Microsoft 365 主控台進行。
  
請務必熟悉現有的混合式類型，以及如何設定內部部署 SharePoint 伺服器陣列與 Microsoft 365 訂閱之間的連線。

| 選項 | 描述 |
|:-----|:-----|
|[Microsoft 規範服務](https://go.microsoft.com/fwlink/?linkid=843165)。  <br/> |遷移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)協助是有限的。  <br/> 大部分的升級是手動或透過 [SharePoint 線上和 OneDrive 遷移內容藍圖](https://go.microsoft.com/fwlink/?linkid=843184)中所述的 SPO 遷移 API。  <br/> |
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
> 請記住，您的 SharePoint 伺服器2010伺服器陣列即將第一次升級、內部部署，以 SharePoint 伺服器2013或 SharePoint Server 2016，以使用 [混合] 選項。 SharePoint Foundation 2010 和 SharePoint Foundation 2013 無法建立與 SharePoint 線上的混合連接。 

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>適用於 Office 2010 用戶端與伺服器和 Windows 7 的選項摘要

如需適用於 Office 2010 用戶端與伺服器和 Windows 7 的升級、移轉和移至雲端選項的視覺摘要，請參閱[終止支援海報](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![Office 2010 用戶端與伺服器和 Windows 7 終止支援海報的影像](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

這張單頁海報可讓您快速了解可以採取的各種方法，以防止Office 2010 用戶端與伺服器產品以及 Windows 7 進入終止支援，而海報上也會強調顯示 Microsoft 365 企業版中慣用的方式和選項支援。

您可以[下載](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)此海報，並以 Letter、Legal 或 Tabloid (11 x 17) 格式列印此海報。
        
## <a name="related-topics"></a>相關主題

[協助您從 Office 2007 或2010伺服器及用戶端升級的資源](upgrade-from-office-2010-servers-and-products.md)
  
[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)
  
[從 SharePoint 2010 升級至 SharePoint 2013 的最佳作法](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)
  
[在 SharePoint 2013 中針對資料庫的升級問題進行疑難排解](https://go.microsoft.com/fwlink/?linkid=843195)
  
[搜尋 Microsoft 解決方案供應商以協助您升級](https://go.microsoft.com/fwlink/?linkid=841249)
  
[已更新 SharePoint 2013 的產品服務原則](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)
  
[已更新 SharePoint Server 2016 的產品服務原則](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
  

