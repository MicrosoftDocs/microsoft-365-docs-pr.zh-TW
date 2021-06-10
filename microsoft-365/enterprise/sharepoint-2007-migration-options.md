---
title: SharePoint 2007 要考慮的遷移選項
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文包含使用 SharePoint Server 2007 之使用者的資訊，以協助他們規劃升級。
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924877"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint 2007 要考慮的遷移選項

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Microsoft SharePoint 2007 和 SharePoint Server 2007 已到達支援的結尾。 是時候升級！ 本文提供遷移選項的相關資訊。
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>SharePoint 的常見升級策略

有多種方法可升級 SharePoint 伺服器環境。 如果您有 Microsoft Office SharePoint Server 2007 伺服器陣列，以下是升級方法的一些範例：
  
- 資料庫附加
    
- 並列升級
    
- 就地升級 
    
- 混合式升級 (就地搭配已拆離資料庫/個別資料庫附加) 
    
- SharePoint 混合 (連線至內部部署 SharePoint) 
    
- 在網站集合或文件庫之間手動移動資料
    
- FastTrack 嚮導升級為 Microsoft 365 ([SharePoint 線上部署顧問](https://aka.ms/spoguidance)) 
    
- 在 Microsoft 365 中 SharePoint Online (SPO) 的遷移 API
    
哪種方法最適合您？
  
在升級時，您對伺服器陣列的作用和用途的知識是戰術性的實力。 人們使用 SharePoint 伺服器陣列的方式，可協助您選擇您的選項。
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 也有一個逐步升級未涵蓋于這裡。 若要查看步驟特定升級文章的清單，請參閱[SharePoint Server 2007 結束支援藍圖](sharepoint-2007-end-of-support.md)。 
  
請記得檢查[產品生命週期](https://support.microsoft.com/lifecycle/search)和系統需求，以瞭解升級所用 SharePoint 的任何版本。 如此一來，您就會知道下一次升級是必要的 (例如，如果您在傳統產品（如 SharePoint Server 2010）上暫停以規劃更多升級，請確定您知道其支援日期的結束日期) ，並確定您有支援方案的硬體。 
  
如果您打算將部分（或全部）的 SharePoint 網站轉換為雲端中 Microsoft 365，這是書簽[Microsoft 365 和 Office 365 服務說明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)的連結的時間。 您將需要服務說明，以瞭解 SharePoint 線上功能，以及它們與內部部署 SharePoint 伺服器的差異。 升級功能 Microsoft Office SharePoint 伺服器2007伺服器陣列。 如果您的安裝中有中斷的網站，請在升級之前加以修正。
  
## <a name="a-note-about-managing-risk"></a>有關管理風險的附注

例如「並列」的方法對於升級邏輯的配置很重要。 當您同時升級時，您會維護 Microsoft Office SharePoint Server 2007 伺服器陣列，但在新的硬體上建立伺服器陣列，以從其開始下一個版本 (SharePoint Server 2010) 。 這可透過三種方式進行：
  
1. 您有一個地方，您可以使用資料庫附加的方式，將 Microsoft Office SharePoint 伺服器2007資料庫備份，以進行升級。
    
2. 如果您找出 Microsoft Office SharePoint Server 2007 伺服器陣列上只會使用少量重要的文件庫和其他資訊，可以選擇從 Microsoft Office SharePoint server 2007 手動移動資料，以 SharePoint 伺服器2010，或是只將特定網站和網站帶至下一個版本 (這樣可讓您的工作更容易) 。
    
3. 您對 Microsoft Office SharePoint server 2007 伺服器陣列所做的較少，就像您升級時，伺服器陣列包含的資料更安全。
    
In-Place 升級等方法將直接作用於您的 Microsoft Office SharePoint 伺服器2007伺服器陣列，讓您更少的選項可放棄路徑，然後再從 pristine 環境重新開始。 您可以盡可能組建一些安全措施， (例如進行原始環境的備份或測試) 。 例如，如果您的 Microsoft Office SharePoint Server 2007 伺服器陣列是虛擬的，且是重複備份及還原的目的，請在升級服務時段之前備份及還原最新的資料庫。 知道您可以還原資料庫備份的選項，並不會使您成為安全保護，但可讓您高枕無憂。
  
> [!TIP]
> [Microsoft Office SharePoint server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12))、 [SharePoint server 2010](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14))、 [SharePoint server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)及[SharePoint 伺服器 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade)的最佳作法檔都存在。 您也可以搜尋具有升級或 Microsoft 365 遷移經驗的[Microsoft 合作夥伴](https://partnercenter.microsoft.com/pcv/search)。 
  
## <a name="make-your-plan"></a>制定計畫

如果您需要升級，您需要一個計畫，而且在這些情況下，一個大小不會全部容納。 您的計畫可能非常簡單，只是「使用 SharePoint 線上建立 Microsoft 365 訂閱，註冊網域」，然後重新導向人員，將檔案儲存在這裡。 它可能不是。 這是您所決定的，而是由您和您的使用者實際需要。
  
> [!NOTE]
> 在已結束生命週期的軟體上執行時，會有很大的危險。 當發現問題時，已不支援的產品不再有修補。 這也表示如果發生新的安全性威脅，將不會有安全性修補程式或修復程式，因為已不再支援生命週期結束產品。 請避免這種狀況！ 
  
### <a name="first-know-your-farm"></a>首先，知道您的伺服器陣列

升級時，您的決策應根據伺服器陣列對您的組織所執行的動作而定。 它會滿足什麼需求？ 其角色為何？ 您公司中的每個伺服器陣列都有不同的角色。 您的部分 SharePoint 伺服器陣列可能很 *重要*，有些則可能是檔案封存--在安全維護中。 或者，如果您的伺服器陣列同時填滿許多角色，您可能需要知道哪些網站集合、網站或文件庫皆有，任何自訂專案，以及其重要性。 在此層級分析您的資料似乎很多，但在升級或遷移之前，它會節約您的網域的時間和精力。 一旦您知道所有移動的部分，以及最重要的位數之後，您也會知道您已 outgrown 及可以留下什麼。 這項知識只會對您的未來帶來益處。 
  
那麼，使用者怎麼說對您的 SharePoint 伺服器陣列而言最為重要？
  
- 內建的 SharePoint 功能
    
- 大型資料主體 (例如檔案的封存) 
    
- 可用性
    
- 伺服器陣列中的重要應用程式、網頁元件或檔 (任務重要的伺服器陣列) 
    
- 符合規範標準
    
- 自訂
    
如果您對您的 SharePoint 伺服器陣列執行一些重要的動作，請說其作用像是有關用戶端服務需求重要資料的大型目錄，您可以在「重要應用程式」旁進行勾選標記，也可以將它放在「可用性」旁，但如果您無法使用 SharePoint 一段時間，您的業務就會受到影響。 同樣地，您也可以檢查「自訂」，因為您伺服器陣列所提供的重要服務是以自訂程式碼、網站定義或多個共同作業的自訂專案為基礎。
  
如果 SharePoint 符合這些需求，而不需要在使用軟體的內建功能之外的任何地方執行任何作業，而且您一般會更新它並執行正常的管理與維護 SharePoint，也就是您在舊版本的 SharePoint 中所做的原因。 換句話說，它已經做了您所需的動作，而且您現在還不需要升級，Microsoft Office SharePoint 伺服器2007的支援結束。
  
當您在專案中列出這些專案時，您會建立升級的準則。 換句話說，任何升級都會必須符合此條碼才能考慮。 這為您提供一種方法，讓您可以排除目前不符合您需求的方法。
  
### <a name="a-simple-sample-plan"></a>簡單的範例計畫

您可能需要在您的 SharePoint 升級所需的路徑上，與領導和其他系統管理員達成共識。 SharePoint伺服器管理員通常會與 Microsoft SQL Server 系統管理員合作、與網路及安全性小組合作等等。 在有許多專案關係人的情況下，您可能需要建立或調整升級和遷移計畫的合約。 例如，如果您遷移資料，讓部分公司在 Microsoft 365 中使用 SharePoint 線上，則可能需要在網路內部進行效能調整或測試。 受影響的小組應提前通知。
  
在我的簡易範例中，我會顯示 SharePoint 管理員的提案，然後列出所有已商定的利益關係人的計畫。 為了清楚起見，請記錄您的協定和決策。
  
方案會在深入分析伺服器陣列後開始，並嘗試識別伺服器陣列的角色、痛點及其他重要資訊，這些資訊會導致縮小某些升級選項。 之後，SharePoint 系統管理員所進行的升級提案，以及專案關係人同意行動計畫。
  
我的 ' 最重要」專案符號清單：
  
- 可供 SharePoint 內建的可用性、功能，以及符合性標準。
    
- 大部分的資料都是在三個網站集合上，開發人員小組使用一種會議工作區尤為重要，且在全球範圍內大量使用。
    
- 有17個其他廣泛使用的網站。
    
- 兩個文件庫 (根網站集合上的會議工作區和檔，) 每個) 的 (超過8000個檔的最大。 我們有大量的封存檔和清單包含試算表附件。
    
- 有十四個文件庫的清單，其具有必須符合規範的敏感性資料。
    
- 我們必須能夠在任何位置執行保留和電子探索。
    
- 由於 InfoSec 規則，此資料中的部分資料必須保持內部部署。
    
 **我的升級和遷移選擇：**
  
| 是 | 否 |
|:-----|:-----|
|使用資料庫附加升級資料庫  <br/> |就地升級   <br/> |
|以並行方式升級伺服器陣列  <br/> |混合式升級  <br/> |
|在 Microsoft 365 (中為個人網站資料提供遷移 API)   <br/> |SharePoint尚未需要混合式 ()   <br/> |
|某些手動資料移轉至 SharePoint 線上以進行重要資料  <br/> |FastTrack 嚮導升級為 Microsoft 365  <br/> |
   
 **建議的計畫：**
  
在內部部署環境中，使用 SharePoint 並行的版本，以進行虛擬化，讓我們能夠先升級資料庫。 從 SharePoint 2007 至 SharePoint 2010。 系統管理員和 Devs 測試所產生的伺服器陣列。 使用者測試產生的伺服器陣列。 修正這段時間內的任何顯示-停止問題。 再一次，並排將 SharePoint 2010 資料庫升級為 SharePoint 2013。 測試。 使用者測試/試驗。 修正這段時間內的任何顯示-停止問題。
  
- 如果與 SPO 混合使用的搜尋同盟符合您的需求，請考慮。
    
- 如果您想要從這裡升級至 SharePoint 線上，請考慮[FastTrack 協助](https://fasttrack.microsoft.com)。 
    
- 決定是否可將任何網站集合卸載為 Microsoft 365 訂閱。  (Microsoft 365 符合許多[規範標準](/compliance/regulatory/offering-home)。 Microsoft 365 具有[eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) ，而且可以透過規範中心進行[封存](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E)。 )  
    
否則，繼續執行 SharePoint Server 2016 的並列升級。
  
> [!NOTE]
> 在規劃升級的系統管理員和實際的程式之間的建議各項間，是由升級所依賴的其他專案關係人所進行的交談。 例如，有時候，經濟效益會強制管理員變更其計畫。 不論是哪一種最終決定，您都應該記錄商定的計畫是什麼。 其外觀可能類似如下： 
  
 **我的行動方案：**
  
在內部部署中，我們使用虛擬環境建立預設的 SharePoint Server 2010 和2013。 SharePoint伺服器2016會在新的硬體上建立，以符合2016的系統需求。 若要將資料庫附加到從 SharePoint 2007 到其所有版本之間的更新，並 SharePoint 伺服器2016，我們將執行資料庫。 若原生功能尚未符合我們的需求，請在 SharePoint Server 2016 環境中重新建立及測試核心自訂。 如果取得成功，我們會在新的硬體上使用已升級的資料庫和較少的自訂專案，進行內部部署伺服器陣列。 我們會將已升級的內容資料庫附加至新的網站集合，SharePoint Server 2013、test、user test/試驗，然後再將 DNS 切回到新的 SharePoint 伺服器2016環境以供即時使用。
  
- 我們不會考慮 SharePoint Server 2016 之間的同盟混合，也不會立即 SharePoint 線上。
    
- 大約35% 的網站可以使用虛名網域轉變為新的 SPO 網站，或者最終會變成商務用 OneDrive 儲存區。 尋找其他機會來轉換網站，或將新網站路由傳送至 SPO。
    
- 這部分的部分遷移是手動進行的，您可以使用拖放方式商務用 OneDrive 個人網站，也可以透過遷移 API 進行。
    
更詳細的步驟，或特定升級方向的連結數目應遵循計畫。 MOSS 2007 電腦不應解除委任，為了進行比較，應維護虛擬環境;不過，當使用者重新導向至 SharePoint Server 2016 時，將會完成升級。
  
選擇方法的主要因素是升級的總成本和時間成本 (您會在 SharePoint 遷移藍圖文章) 中深入瞭解。 不過，事先規劃可讓您極大的好處是設定期望、明智的選擇，以及將成功的方式呈現成一組幀。
  
## <a name="related-links"></a>相關連結

[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft 生命週期原則及生命週期搜尋](https://support.microsoft.com/lifecycle)
  
[搜尋可協助升級或遷移的 Microsoft 合作夥伴](https://partnercenter.microsoft.com/pcv/search)
