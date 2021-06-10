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
description: SharePoint Server 2007 的支援已于10月2017結束。 在本文中，瞭解升級、遷移和支援選項。
ms.openlocfilehash: 224b0af90d6a314aa15a2c0dab7b60626e5abde8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924865"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>SharePoint Server 2007 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

在 **2017 年10月 10** 日，Microsoft Office SharePoint Server 2007 已到達支援終止。 如果您未從 SharePoint Server 2007 遷移至 Microsoft 365 或更新版本的 SharePoint Server 內部部署，現在是開始規劃的時間。 本文提供的資源可協助您將資料移轉至 SharePoint 線上或升級 SharePoint 伺服器內部部署。
  
## <a name="what-does-end-of-support-mean"></a>*支援終止的* 意義為何？

SharePoint伺服器與大多數的 Microsoft 產品一樣，都有支援週期，Microsoft 提供了新功能、bug 修正、安全性修正等等。 此生命週期一般會從產品的初始發行版本持續10年。 此週期的結尾稱為產品的支援終止。 在支援結束後，Microsoft 不再提供：
  
- 可能發生問題的技術支援。
    
- 針對可能會影響伺服器穩定性和可用性問題的錯誤修正。
    
- 安全性修正程式可能會導致伺服器遭受安全性破壞的漏洞。
    
- 時區更新。
    
您的 SharePoint Server 2007 伺服器陣列在10月 10 2017 日之後仍會運作，但不會發佈產品的進一步更新、修補程式或修正，包括安全性修補程式/修正程式。 Microsoft 支援已完全將其支援工作移至較新版本的產品。 因為您已不再支援或修補您的安裝，所以應該升級產品或遷移重要的資料。
  
> [!TIP]
> 若尚未計畫升級或遷移，請參閱： [SharePoint 2007 遷移選項](sharepoint-2007-migration-options.md)，以瞭解開始位置的一些範例。 您也可以搜尋可協助升級或 Microsoft 365 遷移 (或兩者) 的[Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=841249)。
  
如需 Office 2007 伺服器及支援終止的詳細資訊，請參閱可[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

您的第一個終止應該是 [產品生命週期網站](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007)。 如果您有內部部署的 Microsoft 產品已過時，請檢查其支援日期的結束日期，以便讓您有一年的時間來排程升級或遷移。 當您選擇下一個步驟時，請考慮哪些產品功能足夠好、更好及最佳。 以下為範例： 
  
|**良好**|**更好**|**最佳**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint 混合式  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint 混合式  <br/> |
   
如果您選擇 [足夠好的] 選項，則在完成從 SharePoint Server 2007 遷移後，您將很快需要開始規劃另一個升級。 

>[!NOTE] 
>支援終止日期可能會有所變更。 檢查 [產品生命週期網站](https://support.microsoft.com/lifecycle)。
  
## <a name="where-can-i-go-next"></a>下一步可以做什麼？

SharePoint伺服器可以安裝在您自己的伺服器上內部部署。 您也可以使用 SharePoint 線上，也就是 Microsoft 365 的一部分線上服務。 您的選項如下：
  
- 線上遷移至 SharePoint。
    
- 升級 SharePoint 伺服器內部部署。
    
- 請進行上述兩項操作。
    
- 實施[SharePoint 的混合](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)式解決方案。
    
請留意有關維護伺服器陣列、維護或遷移自訂專案，以及升級 SharePoint 伺服器需求之硬體相關的隱藏成本。 如有必要，可獎勵內部部署 SharePoint 伺服器陣列。 不過，如果您在舊版的 SharePoint 伺服器上執行伺服器陣列，但沒有大量自訂，您可以從遷移 SharePoint 線上中受益。
  
> [!IMPORTANT]
> 如果不經常使用 SharePoint 2007 中的內容，則會有另一個選項。 有些 SharePoint 管理員可以選擇建立 Microsoft 365 訂閱、設定新的 SharePoint Online 網站，然後徹底剪下 SharePoint 2007，只會將基本檔帶至全新的 SharePoint 線上網站。 然後，資料可以從 SharePoint 2007 網站排放成封存。 請考慮您的使用者如何使用 SharePoint 2007 安裝中的資料。 您可以有創造性的方式來管理您的需求。
  
|**SharePoint線上 (SPO)**|**SharePoint Server 內部部署**|
|:-----|:-----|
|高成本的時間 (規劃/執行/驗證)   <br/> |高成本的時間 (規劃/執行/驗證)   <br/> |
|降低基金成本 (未購買硬體)   <br/> |基金 (硬體 + devs/系統管理員的成本較高)   <br/> |
|遷移時成本為一次  <br/> |每個未來遷移重複的單一時間成本  <br/> |
|低擁有權總成本/維護  <br/> |高擁有權總成本/維護  <br/> |
   
當您將資料移轉至 Microsoft 365 時，一次性移動會有較低的成本，同時您可以組織資料，並決定要對雲端採取的內容，以及留下的功能。 但未來升級將會自動進行，而且您將不再需要管理硬體和軟體更新。 此外，您伺服器陣列的時間將由 Microsoft 服務等級協定 ([SLA](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)) 所備份。
  
### <a name="migrate-to-sharepoint-online"></a>移轉至 SharePoint Online

請確定 SharePoint 線上具有您需要的所有功能。 請參閱[Microsoft 365 和 Office 365 服務描述](/office365/servicedescriptions/office-365-service-descriptions-technet-library)。
  
您無法直接從 SharePoint 2007 遷移至 SharePoint 線上。 您的移動至 SharePoint 線上將會手動執行。 如果您升級為 SharePoint server 2013 或 SharePoint Server 2016，您可以使用 SharePoint 遷移 API (將資訊遷移至商務用 OneDrive，例如) 。
  
|**線上專業人員**|**線上 con**|
|:-----|:-----|
|Microsoft 提供 SPO 硬體和所有硬體管理。  <br/> |SharePoint Server 內部部署和 SPO 之間可用的功能可能會有所不同。  <br/> |
|您是訂閱的全域系統管理員，而且可以指派系統管理員 SPO 網站。  <br/> |在 SharePoint 伺服器內部部署中，伺服器陣列管理員可以使用的部分動作不存在，也不一定包含 Microsoft 365 中的 SharePoint 系統管理員角色。  <br/> |
|Microsoft 會對底層的硬體和軟體套用修補程式、修正及更新。 <br/> |因為在服務中無法存取基礎檔案系統，所以自訂專案有限。  <br/> |
|Microsoft 發佈 [服務等級協定](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) ，並快速移動以解決服務層級事件。 <br/> |備份與還原及其他修復選項會透過 SharePoint 線上的服務自動進行。 如果不使用，則會覆寫備份。 <br/> |
|安全性測試和伺服器效能調整是由 Microsoft 在服務中持續執行。 <br/> |變更使用者介面及其他 SharePoint 功能會由服務安裝，而且可能需要切換開啟或關閉。 <br/> |
|Microsoft 365 符合許多行業標準： [Microsoft 規範服務](/compliance/regulatory/offering-home)。  <br/> |遷移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)協助是有限的。  <br/> 大部分的升級是手動或透過[SharePoint 線上及 OneDrive 遷移內容藍圖](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)中所述的 SPO 遷移 API。  <br/> |
|Microsoft 支援工程師和資料中心員工不會對您的訂閱進行無限制的系統管理員存取。 <br/> |若需要升級硬體以支援較新版本的 SharePoint，或若升級需要次要伺服器陣列，可能會有額外的成本。  <br/> |
|合作夥伴可協助您將資料移轉到線上 SharePoint 的單一時間工作。  <br/> ||
|線上產品會自動更新。 雖然功能可能取代，但沒有真正的支援端點。 <br/> ||
   
如果您決定建立新的 Microsoft 365 網站，並根據需要將資料手動遷移至該網站，請檢查[Microsoft 365 選項](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>升級 SharePoint 伺服器內部部署

無法在 SharePoint 升級中略過版本。 升級是以串列順序進行：
  
- SharePoint 2007 \> SharePoint server 2010 \> SharePoint server 2013 \> SharePoint server 2016
   
若要從 SharePoint 2007 到 SharePoint Server 2016，表示有大量的時間投資，而且會涉及硬體的成本 (SQL 伺服器也必須升級) 、軟體和管理。 必須升級或放棄自訂專案。
  
> [!NOTE]
> 您可以維持生命週期的 SharePoint 2007 伺服器陣列，在新的硬體 (上安裝 SharePoint 伺服器2016伺服器陣列，讓個別的伺服器陣列執行並列) ，然後規劃並執行手動遷移內容 (，以下載及重新上傳內容，例如) 。 不過，請注意某些手動移動的陷阱，例如，移動檔會以執行手動移動的帳號別名取代最後修改的帳戶。 此外，請考慮必須在一段時間後完成的工作，例如重新建立網站、子網站、許可權和清單結構。 預先考慮您可以移至儲存區或刪除的資料，以降低遷移的影響。
  
在升級之前，請務必先清理您的環境。 請確定您的現有伺服器陣列在您升級之前是正常運作的，當然也是在您解除委任之前。
  
請記得查看 *支援和不支援的升級路徑*： 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
如果您有自訂，請務必為遷移路徑中的每個步驟制定計畫： 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**內部部署 pro**|**內部部署 con**|
|:-----|:-----|
|完全控制 SharePoint 伺服器陣列的所有層面，從伺服器硬體向上。  <br/> |所有中斷和修正都是貴公司的責任 (若您的產品並未超過支援服務) ，您可以接洽付費的 Microsoft 支援人員。  <br/> |
|SharePoint Server 內部部署的完整功能集合，具有透過混合方式將內部部署伺服器陣列連線至 SharePoint Online 訂閱的選項。  <br/> |升級、修補程式、安全性修正程式，以及 SharePoint 伺服器的所有維護都受內部部署管理。  <br/> |
|取得更佳自訂的完整存取權。  <br/> |[Microsoft 規範服務](/compliance/regulatory/offering-home) 必須手動設定內部部署。  <br/> |
|在您的控制項) ，安全性測試和伺服器效能調整都是在您的內部部署 (執行。  <br/> |Microsoft 365 可能會讓 SharePoint 線上使用的功能，不會與 SharePoint 伺服器內部部署互動。  <br/> |
|合作夥伴可協助您將資料移轉至下一版的 SharePoint Server (且超過) 。  <br/> |SharePoint 的伺服器網站不會自動使用 SharePoint 線上中所看到[SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016)憑證。  <br/> |
|在內部部署 SharePoint Server 中完全控制命名慣例、備份及還原及其他修復選項。  <br/> |SharePoint伺服器內部部署對產品生命週期保密。  <br/> |
   
### <a name="upgrade-resources"></a>升級資源

請確定您的環境符合硬體和軟體需求，然後遵循支援的升級方法。
  
- **硬體/軟體需求**： 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **軟體界限和限制**： 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- 下列專案 **的升級程式概述**： 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 與內部部署之間建立 SharePoint 的混合式解決方案

如果您遷移的答案是由內部部署所提供的自我控制，以及 SharePoint Online 所提供的更低的擁有成本，您可以將 SharePoint Server 2013 或2016伺服器陣列連線至透過混合式 SharePoint 線上。 [深入瞭解 SharePoint 混合式解決方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)。
  
如果您決定混合式 SharePoint 伺服器陣列將會對您的業務帶來好處，請熟悉現有類型的混合，以及如何設定內部部署 SharePoint 伺服器陣列與 Microsoft 365 訂閱之間的連線。
  
| 選項 | 描述 |
|:-----|:-----|
[Microsoft 合規性方案](/compliance/regulatory/offering-home)  <br/> |遷移的[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)協助是有限的。  <br/> 大部分的升級是手動或透過[SharePoint 線上和 OneDrive 遷移內容藍圖](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)中所述的 SPO 遷移 API。  <br/> |
|Microsoft 支援工程師和資料中心員工沒有任何無限制的系統管理員存取您的訂閱。<br/> |若需要升級硬體基礎結構以支援較新版本的 SharePoint，或若升級需要次要伺服器陣列，可能會有額外的成本。  <br/> |
|合作夥伴可協助您將資料移轉到線上 SharePoint 的單一時間工作。  <br/> ||
|線上產品會自動更新整個服務。 雖然功能可能取代，但沒有真正的支援端點。<br/> ||
   
如果您決定建立新的 Microsoft 365 網站，並根據需要將資料手動遷移至該網站，請檢查[Microsoft 365 選項](https://www.microsoft.com/microsoft-365/)。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>升級 SharePoint 伺服器內部部署

無法在 SharePoint 升級中略過版本。 升級是以串列順序進行：
  
- SharePoint 2007 \> SharePoint server 2010 \> SharePoint server 2013 \> SharePoint server 2016
   
從 SharePoint 2007 到 SharePoint Server 2016 是一項大幅投資，而且會涉及硬體的成本 (SQL 伺服器也必須升級) 、軟體和管理。 必須升級或放棄自訂專案。
  
> [!NOTE]
> 您可以維持生命週期的 SharePoint 2007 伺服器陣列，在新的硬體 (上安裝 SharePoint 伺服器2016伺服器陣列，讓個別的伺服器陣列執行並列) ，然後規劃並執行手動遷移內容 (，以下載及重新上傳內容，例如) 。 不過，請注意手動移動的潛在缺陷，例如，移動檔會以執行手動移動的帳號別名取代上次修改的帳戶，以及必須在一段時間後完成的工作，例如重新建立網站、子網站、許可權和清單結構。 請考慮您可以移至儲存區或刪除的資料，以降低遷移的影響。
  
在升級之前，請清理您的環境。 請確定您的現有伺服器陣列在您升級之前仍在運作，當然必須先解除委任！ 
  
請記得查看 *支援和不支援的升級路徑*： 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
如果您有 *自訂*，請務必為遷移路徑中的每個步驟規劃升級： 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**內部部署 Pro**|**內部部署 Con**|
|:-----|:-----|
|完全控制 SharePoint 伺服器陣列的所有層面，從伺服器硬體向上。  <br/> |所有中斷和修正都是貴公司的責任。  (若您的產品尚不支援，您可以接洽付費的 Microsoft 支援人員。 )   <br/> |
|SharePoint Server 內部部署的完整功能集合，具有透過混合方式將內部部署伺服器陣列連線至 SharePoint Online 訂閱的選項。  <br/> |升級、修補程式、安全性修正程式，以及 SharePoint 伺服器的所有維護都受內部部署管理。  <br/> |
|取得更佳自訂的完整存取權。  <br/> |[Microsoft 規範服務](/compliance/regulatory/offering-home) 必須手動設定內部部署。  <br/> |
|在您的內部部署中，安全性測試和伺服器效能調整是由您的內部部署所執行。  <br/> |Microsoft 365 可能會讓 SharePoint 線上使用的功能，但不會與 SharePoint 伺服器內部部署互動  <br/> |
|合作夥伴可協助您將資料移轉至下一版的 SharePoint Server (和) 以外。  <br/> |您的 SharePoint 伺服器網站不會自動使用 SharePoint Online 中所看到[SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016)憑證。  <br/> |
|在內部部署 SharePoint Server 中完全控制命名慣例、備份及還原及其他修復選項。  <br/> |SharePoint伺服器內部部署對產品生命週期保密。  <br/> |
   
### <a name="upgrade-resources"></a>升級資源

確定您的環境符合硬體和軟體需求。 然後遵循支援的升級方法。
  
- **硬體/軟體需求：** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **軟體界限和限制：** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **下列專案的升級程式概述：** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>在 SharePoint Online 與內部部署之間建立 SharePoint 的混合式解決方案

如果您遷移的答案是由內部部署所提供的自我控制，以及 SharePoint Online 所提供的更低的擁有成本，您可以將 SharePoint Server 2013 或2016伺服器陣列連線至透過混合式 SharePoint 線上。 [深入瞭解 SharePoint 混合式解決方案](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
如果您決定混合式 SharePoint 伺服器陣列將會對您的業務帶來好處，請熟悉現有類型的混合，以及如何設定內部部署 SharePoint 伺服器陣列與 Microsoft 365 訂閱之間的連線。
  
若要瞭解其運作方式的一個好方法，就是建立 Microsoft 365 開發/測試環境，您可以使用[測試實驗室指南](m365-enterprise-test-lab-guides.md)進行設定。 在您取得試用版或購買 Microsoft 365 訂閱後，您可以在 SharePoint Online 中建立網站集合、網站及文件庫，以便您可以將資料移轉至該位置。 您可以使用遷移 API 手動遷移，或者，如果您想透過混合式嚮導將「我的網站」內容遷移至商務用 OneDrive。
  
> [!NOTE]
> 請記住，若要使用 [混合] 選項，您的 SharePoint 2007 伺服器陣列將需要升級為 SharePoint Server 2013 或 SharePoint server 2016，而不是內部部署。
  
## <a name="related-topics"></a>相關主題

[ (Office SharePoint Server 2007) 疑難排解及繼續升級](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[ (SharePoint Server 2010 的升級問題疑難排解) ](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[在 SharePoint 2013 中針對資料庫的升級問題進行疑難排解](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[搜尋 Microsoft 合作夥伴以協助升級](https://go.microsoft.com/fwlink/?linkid=841249)
  
[協助您從 Office 2007 伺服器及用戶端升級的資源](upgrade-from-office-2007-servers-and-products.md)
