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
description: 深入瞭解您的選項 Exchange Server 2007 已到達支援終止的位置，並開始規劃遷移至 Microsoft 365、Office 365 或 Exchange 2016。
ms.openlocfilehash: 864a4bc64f35a12dfea1a98b3d50430cd3e5714b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688801"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 終止支援藍圖

*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*

在 **2017 年4月11日**，Exchange Server 2007 已到達支援終止。 若尚未開始從 Exchange 2007 遷移至 Microsoft 365、Office 365 或 Exchange 2016，現在是開始規劃的時間。 
  
## <a name="what-does-end-of-support-mean"></a>終止支援是什麼意思？

和所有 Microsoft 產品一樣，Exchange Server 也擁有支援生命週期，我們會在這段期間提供新功能、錯誤修正、安全性修正等支援。 產品的生命週期從首次發行日期算起，通常會持續 10 年，而這個生命週期的結束就稱為產品支援結束。 由於 Exchange 2007 于2017年4月11日到達支援的結尾，所以 Microsoft 不再提供：
  
- 可能發生之任何問題的技術支援；
    
- 所發現且可能會影響伺服器穩定性及可用性之問題的錯誤修正。
    
- 所發現且可能會讓伺服器容易受到安全性威脅之弱點的安全性修正。
    
- 時區更新。
    
Exchange 2007 的安裝會在此日期之後繼續執行。 不過，由於以上所列的變更，強烈建議您儘快從 Exchange 2007 遷移。
  
如需有關 Office 2007 伺服器即將支援終止的詳細資訊，請參閱 [規劃從 Office 2007 伺服器及產品升級](upgrade-from-office-2007-servers-and-products.md)。
  
## <a name="what-are-my-options"></a>我有哪些選擇？

既然 Exchange 2007 已經達到其支援的終止程度，強烈建議您探索選項並準備遷移計畫。 您可以：
  
- 使用轉換、分段或混合式遷移，遷移至 Microsoft 365。
    
- 在您的內部部署伺服器上，將 Exchange 2007 伺服器遷移至較新版本的 Exchange。
    
下列各節將詳細探討每個選項。
  
### <a name="migrate-to-microsoft-365"></a>移轉至 Microsoft 365

將您的電子郵件遷移至 Microsoft 365，是協助您淘汰 Exchange 2007 部署的最佳且最簡單的選項。 透過遷移至 Microsoft 365，您可以從10年舊的技術將單一躍點變為一流的功能，如下所示：
  
- 合規性功能，例如保留原則、就地保留和訴訟資料暫留、就地電子文件探索等；
    
- Microsoft 365 群組;
    
- 焦點收件匣；
    
- MyAnalytics;
    
- REST APIs，以程式設計方式存取電子郵件、行事曆、連絡人等等。
    
Microsoft 365 也會先取得新功能並體驗，您的使用者通常可以立即開始使用。 除了新功能，您也不需要擔心：
  
- 購買及維護硬體；
    
- 支付伺服器的加熱和冷卻費用；
    
- 保持獲得最新安全性、產品和時區修正程式；
    
- 維護儲存和軟體以支援合規性要求；
    
- 升級至新版本的 Exchange-您總在 Microsoft 365 的最新版 Exchange。
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>我應該如何遷移至 Microsoft 365？

視您的組織而定，您有幾個選項可協助您取得 Microsoft 365。 選擇 [遷移] 選項時，您需要考慮一些事項，如您需要移動的席位數目或信箱數目、您想要遷移的時間長度，以及遷移期間是否需要在內部部署安裝與 Microsoft 365 之間進行無縫整合。 下表顯示您將會決定使用哪一種方法的遷移選項及最重要的因素。
  
| |
|**移轉選項**|**組織規模**|**持續時間**|
|:-----|:-----|:-----|
|完全移轉  <br/> |少於 150 個基座  <br/> |一週或更短  <br/> |
|分段移轉  <br/> |超過 150 個基座  <br/> |數周  <br/> |
|完整混合式移轉  <br/> |數百到數千個座位  <br/> |幾個月以上  <br/> |
   
下列各節提供這些方法的概觀。 請參閱[決定移轉方法](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)，了解每種方法的詳細資料。 
  
#### <a name="cutover-migration"></a>完全移轉

完全遷移是指在預先選取的日期和時間，您會將所有信箱、通訊群組、連絡人等遷移至 Microsoft 365;當您完成時，您會關閉內部部署 Exchange 伺服器，並以獨佔方式開始使用 Microsoft 365。
  
「完全遷移」方法適用于沒有非常多信箱的小型組織，想要快速進入 Microsoft 365，而且不想處理其他一些方法。 不過在某種程度上來說，此方法也有限制，因為應該在一週或更短的時間內完成，而且需要使用者重新設定 Outlook 設定檔。 雖然完全移轉可以處理多達 2,000 個信箱，但是強烈建議您在使用此方法時最多移轉 150 個信箱就好。 如果您嘗試移轉超過 150 個信箱，您可能會來不及在期限之前移轉所有信箱，而且 IT 支援人員可能會因協助使用者重新設定 Outlook 而忙到焦頭爛額。
  
如果您想要進行完全遷移，請考慮下列幾點：
  
- Microsoft 365 將需要透過 TCP 埠443，使用 Outlook 無所不在連線至您的 Exchange 2007 伺服器;
    
- 將所有內部部署信箱移至 Microsoft 365;
    
- 您需要具有可讀取使用者信箱內容之存取權的內部部署系統管理員帳戶;
    
- 您想要在 Microsoft 365 中使用的 Exchange 2007 公認的網域必須新增為服務中已驗證的網域。
    
- 在您開始遷移與開始完成階段之間的時間之間，Microsoft 365 會定期同步處理 Microsoft 365 和內部部署信箱。 完成移轉後，您不用擔心電子郵件會留在您的內部部署信箱中；
    
- 使用者將會收到其 Microsoft 365 帳戶的新的臨時密碼，當使用者第一次登入其信箱時，他們必須加以變更。
    
- 您將需要 Microsoft 365 許可證，其中包含您要遷移的每個使用者信箱的 Exchange Online;
    
- 使用者必須在他們的每個裝置上設定新 Outlook 設定檔，然後再次下載電子郵件。 Outlook 將下載的電子郵件數量可能有所差異。 如需詳細資訊，請參閱[變更保持離線的郵件數](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
若要深入了解完全移轉，請參閱：
  
- [轉換電子郵件遷移所需注意的事項](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [執行電子郵件的完全遷移](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>分段移轉

分段遷移是指您有幾個（或幾個）以上的信箱，您想要遷移至 Microsoft 365，需要花一周或更多的時間來完成遷移，而且不需要任何高級混合式遷移功能（如共用 Free/Busy 行事曆資訊）。
  
分段遷移非常適合需要花費更多時間將其信箱遷移至 Microsoft 365 的組織，但仍然計畫在數周內完成遷移。 您可以在「批次」遷移信箱，讓您控制在指定時間內遷移信箱的數量。 例如，您可以在相同的部門中批次使用者的信箱，以確保同時移動所有使用者。 或者，您可能會離開執行中的信箱直到最後一個批次。 使用轉換遷移時，您的使用者將需要重新建立其 Outlook 設定檔。
  
如果您想要進行分段遷移，請考慮下列幾點：
  
- Microsoft 365 將需要透過 TCP 埠443，使用 Outlook 無所不在連線至您的 Exchange 2007 伺服器;
    
- 您需要具有可讀取使用者信箱內容之存取權的內部部署系統管理員帳戶;
    
- 您想要在 Microsoft 365 中使用的 Exchange 2007 公認的網域必須新增為服務中已驗證的網域。
    
- 您需要在批次中，使用每個要遷移之信箱的完整名稱和電子郵件地址來建立 CSV 檔案。 您也需要為每個要遷移的信箱加入新的密碼，然後將其密碼傳送給每位使用者。 使用者第一次登入新的 Microsoft 365 信箱時，系統會提示使用者變更密碼;
    
- 在您啟動遷移批次與開始完成階段之間的時間之間，Microsoft 365 會定期同步處理包含在批次中的 Microsoft 365 和內部部署信箱。 完成移轉後，您不用擔心電子郵件會留在您的內部部署信箱中；
    
- 使用者將會收到其 Microsoft 365 帳戶的新的臨時密碼，當使用者第一次登入其信箱時，他們必須加以變更;
    
- 您將需要 Microsoft 365 許可證，其中包含您要遷移的每個使用者信箱的 Exchange Online;
    
- 使用者必須在他們的每個裝置上設定新 Outlook 設定檔，然後再次下載電子郵件。 Outlook 將下載的電子郵件數量可能有所差異。 如需詳細資訊，請參閱[變更保持離線的郵件數](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
若要深入瞭解分段遷移，請參閱：
  
- [分步電子郵件遷移所需注意的事項](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [執行電子郵件的分段遷移](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>完整混合式

完整混合式遷移是指您的組織有許多成百上千的信箱，且您想要將一些或所有的信箱移至 Microsoft 365。 因為這些移轉通常是較為長期的作業，混合式移轉能夠：
  
- 顯示內部部署使用者 Microsoft 365 中使用者的空閒/忙碌行事曆資訊，反之亦然。
    
- 請參閱包含內部部署和 Microsoft 365 中收件者的統一全域通訊清單。
    
- 不論是內部部署或 Microsoft 365，請查看所有使用者的完整 Outlook 收件者屬性。
    
- 使用 TLS 和憑證來保護內部部署 Exchange 伺服器與 Microsoft 365 之間的電子郵件通訊;
    
- 將內部部署 Exchange 伺服器與 Microsoft 365 之間傳送的郵件視為內部部署，讓他們能夠：
    
  - 由傳輸和合規性代理程式正確評估並處理，並以內部郵件為目標;
    
  - 略過反垃圾郵件篩選。
    
完整混合式移轉最適合欲持續處於混合式組態數個月或更久的組織。 您將取得本節先前所列的功能，以及目錄同步處理、整合的相容性功能，以及使用線上信箱移動將信箱移至和移365出的功能。 Microsoft 365 變成內部部署組織的分機號碼。
  
如果您考慮要執行完整混合式移轉，以下是一些該考量的事項：
  
- 完整混合式移轉並不適合所有組織類型。 由於完整混合式移轉十分複雜，即使它具有多項優點，但這種設定所需付出的心力和成本往往令擁有少於數百個信箱的組織望之卻步。 如果這聽起來像是您的組織，強烈建議您改為考慮轉換或分段遷移。
    
- 您必須在 Exchange 2007 組織中部署至少一個 Exchange 2013 伺服器，以充當 "混合伺服器"。 此伺服器會代表您的 Exchange 2007 伺服器與 Microsoft 365 進行通訊;
    
- Microsoft 365 將需要透過 TCP 埠443，使用 Outlook 無所不在連線至「混合伺服器」;
    
- 您必須在內部部署 Active Directory 伺服器與 Microsoft 365 之間，使用 Azure Active Directory (Azure AD) 連線來設定目錄同步處理。
    
- 使用者將能夠使用使用者登入本機網路時所使用的相同使用者名稱和密碼登入他們的 Microsoft 365 信箱。 (需要使用密碼同步處理和/或 Active Directory Federation Services 的 Azure AD Connect) ;
    
- 您將需要 Microsoft 365 許可證，其中包含您要遷移的每個使用者信箱的 Exchange Online;
    
- 使用者不需要在大部分的裝置上設定新的 Outlook 設定檔 (有些舊版的 Android 手機可能需要新的設定檔) ，而且不需要重新下載其電子郵件。
    
如果您適合使用完整混合式移轉，請參閱下列可協助您進行移轉的相關資源：
  
- [Exchange 部署助理](https://aka.ms/exdeploy)
    
- [Exchange Server 混合式部署](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [混合組態精靈](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [混合組態精靈常見問題集](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [混合式部署必要條件](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>遷移至較新版本的 Exchange Server

雖然我們極力相信您可以透過遷移至 Microsoft 365 達到最佳的價值和使用者經驗，我們也會瞭解某些組織必須將電子郵件保存在內部部署中。 這可能是因為法規需求，保證資料不會儲存在另一個國家/地區的資料中心，依此類推。 如果您選擇保留電子郵件的內部部署，您可以將 Exchange 2007 環境遷移至 Exchange 2010、Exchange 2013 或 Exchange 2016。
  
如果您無法遷移至 Microsoft 365，建議您將遷移至 Exchange 2016。 Exchange 2016 包括舊版 Exchange 所包含的所有功能和進步，而且它最符合 Microsoft 365 (的體驗，不過某些功能只有在 Microsoft 365) 中提供。 請查看您遺漏的一些事項：
  
|**Exchange 版本**|**功能**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based 不 ACLs 的存取控制 (許可權)   <br/>  Outlook Web App 信箱原則  <br/>  能夠在組織之間共用空閒/忙碌及委派行事曆  <br/> |
|Exchange 2013  <br/> | *來自 Exchange 2010 和 ... 的功能*  <br/>  將伺服器角色數目減少為三個 (信箱、用戶端存取、邊際傳輸) 的簡化架構  <br/>  可協助保護機密資訊防止外洩的資料外洩防護原則 (DLP)  <br/>  大幅改善的 Outlook Web App 體驗  <br/> |
|Exchange 2016  <br/> | *來自 Exchange 2013 的功能以及…*  <br/>  更進一步簡化的伺服器角色，只有信箱和邊際傳輸  <br/>  與 SharePoint 整合一併改善的 DLP  <br/>  改善的資料庫恢復  <br/>  線上文件共同作業  <br/> |
   
#### <a name="which-version-should-i-migrate-to"></a>我應該遷移至哪一個版本？

建議您先假設您要遷移至 Exchange 2016。 然後，使用下列資訊確認您的假設或排除 Exchange 2016。 如果您因原因或另一個原因而無法遷移至 Exchange 2016，請執行與 Exchange 2013 相同的處理常式，依此類推。
  
|**考量事項**|**其他資訊**|
|:-----|:-----|
|終止支援日期  <br/> | 與 Exchange 2007 類似的是，每個 Exchange 版本都有自己的支援時間結尾：  <br/> **Exchange 2010** -1 月2020  <br/> **Exchange 2013** - 2023 年 4 月  <br/> **Exchange 2016** - 2025 年 10 月  <br/>  終止支援日期愈早，您將需要愈快執行其他移轉。 2020年1月比您想像的要近許多。  <br/> |
|Exchange 2010 和2013的遷移路徑  <br/> |以下是遷移至 Exchange 2010 或 Exchange 2013 的一般階段：  <br/> 將 Exchange 2010 或2013安裝至現有的 Exchange 2007 組織將服務和其他基礎結構移至 Exchange 2010 或2013將信箱和公用資料夾移至 Exchange 2010 或2013解除委任其他 Exchange 2007 伺服器的授權 |
|Exchange 2016 的遷移路徑  <br/> |以下是遷移至 Exchange 2016 的一般階段：  <br/> 將 Exchange 2013 安裝至現有的 Exchange 2007 組織將服務和其他基礎結構移至 exchange 2013 將信箱和公用資料夾移至 Exchange 2013 解除委任其他 Exchange 2007 伺服器將 Exchange 2016 安裝至現有的 Exchange 2013 組織。 將信箱、公用資料夾、服務及其他基礎結構移至 Exchange 2016 (順序無關緊要) 。 解除委任餘下的 Exchange 2013 伺服器 > [!NOTE]> 從 exchange 2013 遷移至 exchange 2016 非常簡單。 這兩個版本都有幾乎相同的硬體需求。 因此，這些版本都是如此相容的，這表示您可以重新建立您為 Exchange 2013 購買的伺服器，並在其上安裝 Exchange 2016。 而且，使用線上信箱移動，大部分使用者永遠不會注意到他們的信箱即將移離伺服器，之後再回到 Exchange 2016。           |
|版本共存  <br/> | 遷移至：  <br/> **Exchange 2016** Exchange 2016 無法安裝在包含 Exchange 2007 伺服器的組織中。 您必須先將 exchange 2010 或2013遷移至 Exchange 或 (我們強烈建議 Exchange 2013) 、移除所有 Exchange 2007 伺服器，然後遷移至 Exchange 2016。  <br/> **Exchange 2010 或 exchange 2013** 您可以將 Exchange 2010 或 Exchange 2013 安裝到現有的 Exchange 2007 組織中。 這可讓您安裝一或多部 Exchange 2010 或2013伺服器，並執行您的遷移。  <br/> |
|伺服器硬體  <br/> | 伺服器硬體需求已從 Exchange 2007 變更。 您必須確認要使用的硬體能夠相容。 如需每個版本的硬體需求相關詳細資訊，請參閱：  <br/> [Exchange 2016 系統需求](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Exchange 2013 系統需求](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Exchange 2010 系統需求](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  透過大幅改善的 Exchange 效能，以及新款伺服器中的提升運算效能及儲存空間容量，您會發現只需要比較少的伺服器就能支援相同信箱數。  <br/> |
|作業系統版本  <br/> | 每個版本的最低支援作業系統版本為：  <br/> **Exchange 2016** Windows Server 2012  <br/> **Exchange 2013** Windows Server 2008 R2 SP1  <br/> **Exchange 2010** Windows Server 2008 SP2  <br/>  如需作業系統支援的相關詳細資訊，請參閱 [Exchange Server 支援性總表](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)。  <br/> |
|Active Directory 樹系功能等級  <br/> | 每個版本的最低支援 Active Directory 樹系功能等級為：  <br/> Exchange 2016** **：Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  如需樹系功能等級支援的相關詳細資訊，請參閱 [Exchange Server 支援性總表](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)。  <br/> |
|Office 用戶端版本  <br/> | 每個版本的最低支援 Office 用戶端版本為：  <br/> Exchange 2016** **：Office 2010 (含最新更新)  <br/> **Exchange 2013** Office 2007 SP3  <br/> **Exchange 2010** Office 2003  <br/>  如需 Office 用戶端支援的相關詳細資訊，請參閱 [Exchange Server 支援性總表](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)。  <br/> |
   
#### <a name="how-do-i-migrate"></a>如何遷移？

如果您決定要將電子郵件保留在內部部署中，您可以使用下列資源來協助您進行遷移：
  
- [Exchange 部署助理](https://aka.ms/exdeploy)
    
- Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx)、 [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx)、 [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)的 Active Directory 架構變更
    
- Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx)、 [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx)、 [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)的系統需求
    
- Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx)、 [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx)、 [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)的必要條件
    
## <a name="what-if-i-need-help"></a>如果我需要協助，該怎麼辦？

如果您要遷移至 Microsoft 365，您可能有資格使用 Microsoft FastTrack 服務。 FastTrack 提供最佳作法、工具及資源，可讓您以盡可能順利的方式遷移至 Microsoft 365。 最棒的是，實際上會有一名支援工程師一路從規劃、設計到移轉完最後一個信箱，全程逐步引導您進行移轉。 若要深入了解 FastTrack，請參閱 [Microsoft FastTrack](https://fasttrack.microsoft.com/)。
  
如果您在遷移至 Microsoft 365 時遇到任何問題，而且您未使用 FastTrack，或您將遷移至較新版本的 Exchange Server，我們將會在這裡提供協助。 以下是您可使用的一些資源：
  
- [技術社群](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [客戶支援](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>相關主題

[協助您升級 Office 2007 伺服器及用戶端的資源](upgrade-from-office-2007-servers-and-products.md)