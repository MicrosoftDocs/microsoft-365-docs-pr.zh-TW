---
title: Exchange 2007 終止支援藍圖
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 在 Exchange Server 2007 的支援終止後，瞭解您的選項，然後開始規劃遷移至 Microsoft 365、Office 365 或 Exchange 2016。
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924197"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

Exchange Server 2007 已于四月2017取得支援終止。 若尚未開始從 Exchange 2007 到 Microsoft 365、Office 365 或 Exchange 2016 的遷移，現在是開始規劃的時間。
  
## <a name="what-does-end-of-support-mean"></a>*支援終止的* 意義為何？

和所有 Microsoft 產品一樣，Exchange Server 也擁有支援生命週期，我們會在這段期間提供新功能、錯誤修正、安全性修正等支援。 此生命週期一般會從產品的初始發行版本持續10年。 此週期的結尾稱為產品的支援終止。 因為 Exchange 2007 于2017年4月11日到達其支援的結尾，所以 Microsoft 不再提供：
  
- 可能發生問題的技術支援。
    
- 針對可能會影響伺服器穩定性和可用性問題的錯誤修正。
    
- 安全性修正程式可能會導致伺服器遭受安全性破壞的漏洞。
    
- 時區更新。
    
Exchange 2007 的安裝會在終止支援的日期之後繼續執行。 但由於沒有新的更新或支援，強烈建議您儘快從 Exchange 2007 進行遷移。
  
如需 Office 已結束支援之2007伺服器的詳細資訊，請參閱[規劃從 Office 2007 伺服器及產品升級](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

您可以：
  
- 使用轉換、分段或混合式遷移，遷移至 Microsoft 365。
    
- 在您的內部部署伺服器上，將 Exchange 2007 伺服器遷移至較新版本的 Exchange。
    
下列各節將詳細探討每個選項。
  
### <a name="migrate-to-microsoft-365"></a>移轉至 Microsoft 365

將您的電子郵件遷移至 Microsoft 365 是協助淘汰 Exchange 2007 部署的最佳和最簡單的選項。 透過遷移至 Microsoft 365，您可以從10年舊的技術將單一躍點變為一流的功能，包括：
  
- 合規性功能，例如保留原則、In-Place 和訴訟暫止、就地 eDiscovery 及其他
    
- Microsoft 365 群組
    
- Focused Inbox
    
- MyAnalytics
    
- REST APIs，以程式設計方式存取電子郵件、行事曆、連絡人等
    
Microsoft 365 也會先取得新功能並體驗，所以您和您的使用者通常可以立即開始使用。 您不需要擔心：
  
- 購買及維護硬體。
    
- 支付熱量和冷卻您的伺服器。
    
- 保持最新的安全性、產品和時區修正。
    
- 維護儲存和軟體以支援規範的需求。
    
- 升級至新版本的 Exchange。 使用 Microsoft 365 時，永遠都是最新版本的 Exchange。
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>我應該如何遷移至 Microsoft 365？

您有一些遷移選項。 您需要考慮一些事項，包括：

- 您需要移動的席位或信箱數目。
- 您想要將遷移持續多久。
- 在遷移期間，您是否需要在內部部署與 Microsoft 365 之間進行無縫整合。

下表顯示決定使用哪一種方法的遷移選項及最重要因素：
  

|**移轉選項**|**組織規模**|**持續時間**|
|:-----|:-----|:-----|
|完全移轉  <br/> |少於 150 個基座  <br/> |一週或更短  <br/> |
|分段移轉  <br/> |超過 150 個基座  <br/> |數周  <br/> |
|完整混合式移轉  <br/> |數百到數千個座位  <br/> |幾個月以上  <br/> |
   
下列各節提供這些方法的概述。 如需詳細資訊，請參閱 [決定遷移路徑](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)。 
  
#### <a name="cutover-migration"></a>完全移轉

在完全遷移中，您可以將所有信箱、通訊群組、連絡人等遷移至預先選定的日期和時間 Microsoft 365。 遷移完成後，請關閉內部部署 Exchange 伺服器，並以獨佔方式開始使用 Microsoft 365。
  
對於沒有許多信箱的小型組織而言，切換遷移非常棒，只想要快速 Microsoft 365，而且不想處理其他方法的複雜部分。 不過，它應在一周或更少的時間完成，而且需要使用者重新設定其 Outlook 設定檔。 轉換遷移最多可以處理2000個信箱，但是強烈建議您使用它來遷移最多150個信箱。 如果您嘗試遷移其他的信箱，您可能會在您的最後期限之前，用完轉移所有信箱的時間，而且 IT 支援人員可能會因要求而淹沒，以協助使用者重新設定 Outlook。
  
如果您想要進行完全遷移，請考慮下列事項：
  
- Microsoft 365 將需要使用 TCP 埠443上 Outlook 任何地方，連線至 Exchange 2007 伺服器。
    
- 將所有內部部署信箱移至 Microsoft 365。
    
- 您需要具有使用者信箱讀取權的內部部署系統管理員帳戶。
    
- 您想要在 Microsoft 365 中使用的 Exchange 2007 公認的網域必須新增為服務中已驗證的網域。
    
- 在您開始遷移與開始完成階段之間的時間，Microsoft 365 會定期同步處理 Microsoft 365 和內部部署信箱。 這可讓您完成遷移，而不必擔心您的內部部署信箱中留下的電子郵件。
    
- 使用者將會收到其 Microsoft 365 帳戶的新臨時密碼。 他們第一次登入信箱時，需要變更其密碼。
    
- 您將需要 Microsoft 365 授權，其中包含您要遷移之每個使用者信箱的 Exchange Online。
    
- 使用者必須在他們的每個裝置上設定新 Outlook 設定檔，然後再次下載電子郵件。 Outlook 將下載的電子郵件數量可能有所差異。 如需詳細資訊，請參閱 [變更保留離線的郵件數目](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
如需有關轉換遷移的詳細資訊，請參閱：
  
- [轉換電子郵件遷移所需注意的事項](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [執行電子郵件的完全遷移](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>分段移轉

在分段遷移中，您有幾個您想要遷移至 Microsoft 365 的成百上千個信箱，需要花一周或更多時間來完成遷移，而且不需要任何高級混合式遷移功能（如共用 Free/Busy 行事曆資訊）。
  
分段遷移非常適合需要花更多時間將其信箱遷移至 Microsoft 365，但仍可在數周內完成遷移的計畫。 您可以成批遷移信箱。 您可以控制在指定時間要遷移的信箱數目和信箱數目。 例如，您可以在相同的部門中批次使用者的信箱，以確保同時移動所有使用者。 或者，您可能會離開執行中的信箱直到最後一個批次。 使用轉換遷移時，您的使用者將需要重新建立其 Outlook 設定檔。
  
如果您想要進行分段遷移，請考慮下列事項：
  
- Microsoft 365 需要使用 TCP 埠443上 Outlook 的任何地方，連線至 Exchange 2007 伺服器。
    
- 您需要具有使用者信箱讀取權的內部部署系統管理員帳戶。
    
- 您計畫用於 Microsoft 365 的 Exchange 2007 公認的網域必須新增為服務中已驗證的網域。
    
- 您必須建立 CSV 檔案，並在批次中使用每個計畫要遷移之每個信箱的完整名稱和電子郵件地址。 您也需要為每個要遷移的信箱加入新的密碼，並將該密碼傳送給每位使用者。 使用者第一次登入新 Microsoft 365 信箱時，系統會提示使用者變更密碼。
    
- 在您啟動遷移批次及開始完成階段之間，Microsoft 365 會定期同步處理包含在批次中的 Microsoft 365 和內部部署信箱。 這可讓您完成遷移，而不必擔心您的內部部署信箱中留下的電子郵件。
    
- 您將需要 Microsoft 365 授權，其中包含您要遷移之每個使用者信箱的 Exchange Online。
    
- 使用者必須在他們的每個裝置上設定新 Outlook 設定檔，然後再次下載電子郵件。 Outlook 將下載的電子郵件數量可能有所差異。 如需詳細資訊，請參閱 [變更保留離線的郵件數目](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
如需有關分段遷移的詳細資訊，請參閱：
  
- [分步電子郵件遷移所需注意的事項](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [執行電子郵件的分段遷移](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>完整混合式

在完整的混合式遷移中，您的組織有多個成百上千的信箱，且您想要將一些或所有的信箱移至 Microsoft 365。 因為這些移轉通常是較為長期的作業，混合式移轉能夠：
  
- 顯示內部部署使用者 Microsoft 365 中使用者的空閒/忙碌行事曆資訊，反之亦然。
    
- 請參閱包含內部部署和 Microsoft 365 中的收件者的統一全域通訊清單。
    
- 不論是內部部署或在 Microsoft 365 中，請查看所有使用者的完整 Outlook 收件者屬性。
    
- 使用 TLS 和憑證，在內部部署 Exchange 伺服器與 Microsoft 365 之間安全地進行電子郵件通訊。
    
- 將內部部署 Exchange 伺服器與 Microsoft 365 之間傳送的郵件視為內部部署，使其能夠執行下列作業：
    
  - 由傳輸和規範代理程式正確評估並處理，並以內部郵件為目標。
    
  - 略過反垃圾郵件篩選。
    
完全混合式遷移最適合預期會以多個月為混合式設定的組織。 您將取得本節先前所列的功能，以及目錄同步處理、整合的相容性功能，以及使用線上信箱移動將信箱移至 Microsoft 365 的功能。 Microsoft 365 會變成您的內部部署組織的分機。
  
如果您想要進行完整混合式遷移，請考慮下列事項：
  
- 完全混合式遷移不適用於所有類型的組織。 由於完整混合式移轉十分複雜，即使它具有多項優點，但這種設定所需付出的心力和成本往往令擁有少於數百個信箱的組織望之卻步。 如果這聽起來像是您的組織，建議您改為考慮轉換或分段遷移。
    
- 您必須在 Exchange 2007 組織中部署至少一部 Exchange 2013 server，以充當「混合伺服器」。 此伺服器會代表 Exchange 2007 伺服器與 Microsoft 365 通訊。
    
- Microsoft 365 需要使用 TCP 埠443上的 Outlook Anywhere 來連線至混合伺服器。
    
- 您必須使用內部部署的 Active directory 伺服器及 Microsoft 365 之間的 Azure Active Directory (Azure AD) 連線設定目錄同步處理。
    
- 使用者可以使用相同的使用者名稱和密碼登入他們的 Microsoft 365 信箱，就像登入本機網路時一樣。  (此功能需要有密碼同步處理和/或 Active Directory Federation Services 的 Azure AD 連線。 ) 
    
- 您將需要 Microsoft 365 授權，其中包含您要遷移之每個使用者信箱的 Exchange Online。
    
- 使用者不需要在大部分裝置上設定新的 Outlook 設定檔，不過某些老式的 Android 手機可能需要新的設定檔。 使用者不需要 redownload 他們的電子郵件。
    
若完整混合式遷移是正確的，請參閱下列資源，以協助您進行遷移：
  
- [Exchange 部署助理](/exchange/exchange-deployment-assistant)
    
- [Exchange Server 混合式部署](/exchange/exchange-hybrid)
    
- [混合組態精靈](/exchange/hybrid-configuration-wizard)
    
- [混合組態精靈常見問題集](/exchange/hybrid-configuration-wizard-faqs)
    
- [混合式部署必要條件](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>遷移至較新版本的 Exchange Server

我們強烈相信您可以透過遷移至 Microsoft 365，獲得最佳的價值和使用者經驗。 不過，我們也知道某些組織必須將電子郵件保存在內部部署中。 這可能是因為法規需求，保證資料不會儲存在另一個國家/地區的資料中心，或類似的位置。 如果您選擇將電子郵件保留在內部部署中，您可以將 Exchange 2007 環境遷移至 Exchange 2010、Exchange 2013 或 Exchange 2016。
  
如果您無法遷移至 Microsoft 365，建議您將遷移至 Exchange 2016。 Exchange 2016 包含 Exchange 舊版本的所有功能。 雖然有些功能只能在 Microsoft 365 中使用，但也最為接近 Microsoft 365 的使用體驗。 請查看您遺漏的一些事項：
  
|**Exchange 版本**|**功能**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based 不 ACLs 的存取控制 (許可權)   <br/>  Outlook Web App 信箱原則  <br/>  能夠在組織之間共用空閒/忙碌及委派行事曆  <br/> |
|Exchange 2013  <br/> | *Exchange 2010 的功能和 .。。*  <br/>  簡化的架構，可將伺服器角色的數目降至三個 (信箱、用戶端存取、Edge Transport)   <br/>  可協助保護機密資訊防止外洩的資料外洩防護原則 (DLP)  <br/>  改進的 Outlook Web App 體驗  <br/> |
|Exchange 2016  <br/> | *Exchange 2013 的功能和 .。。*  <br/>  更進一步簡化的伺服器角色，只有信箱和邊際傳輸  <br/>  與 SharePoint 整合一併改善的 DLP  <br/>  改善的資料庫恢復  <br/>  線上文件共同作業 |
   
#### <a name="which-version-should-i-migrate-to"></a>我應該遷移至哪一個版本？

建議您先假設您要遷移至 Exchange 2016。 然後，使用下列資訊確認您的假設或排除 Exchange 2016。 如果您由於某些原因無法遷移至 Exchange 2016，請執行與 Exchange 2013 相同的程式，依此類推。
  
|**考量事項**|**其他資訊**|
|:-----|:-----|
|終止支援日期  <br/> | 如同 Exchange 2007，每個 Exchange 版本都有自己的支援結束日期：  <br/> *Exchange 2010* -2020 年1月  <br/> *Exchange 2013* - 2023 年 4 月  <br/> *Exchange 2016* - 2025 年 10 月  <br/>  先前的支援終止，您將需要執行另一個遷移。<br/> |
|Exchange 2010 和2013的遷移路徑。  <br/> |以下是遷移至 Exchange 2010 或 Exchange 2013 的一般階段：  <br/> -將 Exchange 2010 或2013安裝至您現有的 Exchange 2007 組織。 <br/>-將服務和其他基礎結構移至 Exchange 2010 或2013。<br/>-將信箱和公用資料夾移至 Exchange 2010 或2013。<br/>-解除委任剩餘 Exchange 2007 伺服器。 |
|Exchange 2016 的遷移路徑  <br/> |以下是遷移至 Exchange 2016 的一般階段：  <br/> -將 Exchange 2013 安裝到現有的 Exchange 2007 組織。<br/>-將服務和其他基礎結構移至 Exchange 2013。<br/>-將信箱和公用資料夾移至 Exchange 2013。<br/>-解除委任剩餘 Exchange 2007 伺服器。<br/>-將 Exchange 2016 安裝到現有的 Exchange 2013 組織。<br/>-將信箱、公用資料夾、服務及其他基礎結構移動至 Exchange 2016 (訂單並不重要) 。 解除委任剩餘 Exchange 2013 伺服器。<br/><br/> **附注：** 從 Exchange 2013 Exchange 2016 遷移非常簡單。 這兩個版本的硬體需求幾乎相同，而且這些版本都非常相容。 因此，您可以重建為 Exchange 2013 購買的伺服器，並在其上安裝 Exchange 2016。 針對線上信箱移動，大部分使用者甚至不會注意到，使用者的信箱已移離伺服器後再回到 Exchange 2016。           |
|版本共存  <br/> | 當遷移至 .。。  <br/> **Exchange 2016：** 無法在包含 Exchange 2007 伺服器的組織中安裝 Exchange 2016。 您必須先遷移至 Exchange 2010 或 2013 (我們強烈建議 Exchange 2013) 、移除所有 Exchange 的2007伺服器，然後遷移至 Exchange 2016。  <br/> **Exchange 2010 或 Exchange 2013：** 您可以將 Exchange 2010 或 Exchange 2013 安裝至現有的 Exchange 2007 組織。 這可讓您安裝一或多個 Exchange 2010 或2013伺服器，並執行您的遷移。  <br/> |
|伺服器硬體  <br/> | 伺服器硬體需求已從 Exchange 2007 變更。 請確認您的硬體是否相容。 如需詳細資訊，請參閱：  <br/> [Exchange 2016 系統需求](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013 系統需求](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 的系統需求](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  在較新的伺服器中，您會發現 Exchange 效能及計算能力增加和儲存容量的大幅改善，也意味著您可能需要較少的伺服器來支援相同數量的信箱。  <br/> |
|作業系統版本  <br/> | 每個版本的最低支援作業系統版本為：  <br/> **Exchange 2016** -Windows Server 2012  <br/> **Exchange 2013** -Windows Server 2008 R2 SP1  <br/> **Exchange 2010** -Windows Server 2008 SP2  <br/>  Exchange 支援性[清單](/Exchange/plan-and-deploy/supportability-matrix)中，尋找有關作業系統支援的詳細資訊。  <br/> |
|Active Directory 樹系功能等級  <br/> | 每個版本的最低支援 Active Directory 樹系功能等級為：  <br/> Exchange 2016 ****：Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  若要瞭解更多關於樹系功能等級支援的資訊[Exchange 支援性清單](/Exchange/plan-and-deploy/supportability-matrix)。  <br/> |
|Office 用戶端版本  <br/> | 每個版本的最低支援 Office 用戶端版本為：  <br/> **Exchange 2016** -Office 2010 (更新的最新版本)   <br/> **Exchange 2013** -Office 2007 SP3  <br/> **Exchange 2010** -Office 2003  <br/>  若要瞭解詳細資訊，請參閱 Office 的用戶端支援[Exchange 支援性清單](/Exchange/plan-and-deploy/supportability-matrix)。  <br/> |
   
#### <a name="how-do-i-migrate"></a>如何遷移？

如果您決定將電子郵件保留在內部部署中，請使用下列資源來協助您進行遷移：
  
- [Exchange 部署助理](/exchange/exchange-deployment-assistant)
    
- Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes)、 [2013](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)、 [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)的 Active Directory 架構變更
    
- Exchange [2016](/Exchange/plan-and-deploy/system-requirements)、 [2013](/exchange/exchange-2013-system-requirements-exchange-2013-help)、 [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))的系統需求
    
- Exchange [2016](/Exchange/plan-and-deploy/prerequisites)、 [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help)、 [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))的必要條件
    
## <a name="get-help"></a>取得說明

如果您要遷移至 Microsoft 365，您可能有資格使用 Microsoft FastTrack 服務。 FastTrack 提供最佳作法、工具及資源，讓您的遷移 Microsoft 365 盡可能順利地進行遷移。 尤其可貴的是，支援工程師會逐步引導您進行遷移（從規劃及設計所有遷移最後一個信箱的方式）。 如需 FastTrack 的詳細資訊，請參閱 [Microsoft FastTrack](https://fasttrack.microsoft.com/)。
  
如果您在遷移至 Microsoft 365 時發生問題，但您未使用 FastTrack，或您將遷移至較新版本的 Exchange Server，我們將在這裡提供協助。 以下是您可使用的一些資源：
  
- [技術社群](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [客戶支援](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>相關主題

[協助您升級 Office 2007 伺服器及用戶端的資源](upgrade-from-office-2007-servers-and-products.md)