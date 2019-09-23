---
title: 保留原則概觀
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 透過保留原則，您可以主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)；將單一原則套用到整個組織或只套用到特定位置或使用者；以及將原則套用到所有內容或只套用到符合特定條件的內容。
ms.openlocfilehash: 45c2459a99b083ac98ea85853882df2e16cf59d3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077783"
---
# <a name="overview-of-retention-policies"></a>保留原則概觀

對大多數組織來說，其資料 (電子郵件、文件、即時訊息等) 的數量和複雜性日益增加。有效管理或控管此資訊至關重要，因為您需要：
  
- **主動遵守產業規範和內部原則**，需要您將某些內容至少保留一段時間，例如，Sarbanes-Oxley 法案可能需要您將某些類型的內容保留七年。 
    
- **降低發生訴訟或安全性漏洞的風險**，方法為永久刪除您不再需要保留的舊內容。 
    
- **協助貴組織有效分享知識並提高靈活度**，方法為確保使用者只使用目前和相關的內容。 
    
保留原則可協助您實現所有這些目標。管理內容通常需要下列兩個動作：
  
- **保留**內容，以便無法在保留期間結束之前將其永久刪除。 
    
- 在保留期間結束之前，永久**刪除**內容。 
    
透過保留原則，您可以：
  
- 主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)。
    
- 將單一原則套用到整個組織或只套用到特定位置或使用者。
    
- 將原則套用到所有內容或只套用到符合特定條件的內容，例如包含特定關鍵字或[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。
    
當內容受限於保留原則時，人員可以繼續編輯及使用的內容，一樣不會變更，因為內容保留在其原始位置。但在某人編輯或刪除受限於原則的內容時，將會有複本儲存至安全位置，在原則仍然有效時會持續進行保留。
  
最後，有些組織可能需要遵守法規，例如證券交易委員會 (SEC) 法規 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。若要滿足這個需求，您可以使用「保留鎖定」。原則鎖定之後，任何人 (包括系統管理員) 均無法關閉原則或執行較不嚴格的限制。
  
您可以在以下位置建立和管理保留原則：

- [Microsoft 365 合規性中心](https://compliance.microsoft.com/) 的 [原則]**** 頁面。
- [Office 365 安全性與合規性中心](https://protection.office.com/) 的 [資料控管]**** 下的 [保留]**** 頁面。
  
## <a name="how-a-retention-policy-works-with-content-in-place"></a>保留原則如何就地使用內容

當您在保留原則中包括網站或信箱這類的位置時，內容仍會留在其原始位置。使用者可以繼續使用其文件或郵件，一樣不會變更。但在他們編輯或刪除原則中包含的內容時，系統會保留內容的複本，與您套用原則時存在的內容相同。
  
針對 SharePoint 網站集合，當使用者編輯或刪除原始內容時，原始內容的複本會保留在文件保留庫；針對電子郵件和公用資料夾，複本會保留在 [可復原的項目] 資料夾中。大部分人員看不到這些安全位置和保留內容。使用保留原則時，人員甚至不知道其內容受到原則約束。
  
附註：
  
- 小組（交談）的內容會儲存在 Exchange 中，其中會根據訊息類型（電子郵件或交談）套用原則。
    
- 套用到 Office 365 群組的保留原則同時包含群組信箱和網站。
    
### <a name="content-in-onedrive-accounts-and-sharepoint-sites"></a>OneDrive 帳戶和 SharePoint 網站中的內容

保留原則是在網站集合層級套用。在保留原則中包含 SharePoint 網站集合或 OneDrive 帳戶時，如果原本沒有文件保留庫，則會建立一個文件保留庫。您可以在網站集合的頂層網站中**網站內容**頁面上檢視這個文件保留庫。大部分的使用者都無法檢視文件保留庫，因為只有網站集合管理員才能檢視文件保留庫。
  
如有使用者嘗試變更或刪除受限於保留原則的網站內容，保留原則會先檢查內容在套用原則後是否有所變更。如果這是套用保留原則後的第一次變更，保留原則會先將內容複製到文件保留庫，然後允許使用者變更或刪除原始內容。請注意，網站集合中的任何內容都可複製到文件保留庫，即使內容不符合保留原則所使用的查詢亦然。
  
接著，計時器工作會清除文件保留庫。計時器工作會定期執行，並比較文件保留庫中的所有內容與網站上保留原則所使用的所有查詢。除非內容至少符合一個查詢，否則計時器工作將從文件保留庫中永久刪除該內容。
  
前述機制適用於在套用保留原則時即存在的內容。除此之外，任何在網站納入保留原則後才在網站集合中建立或新增的內容，在刪除之後仍將保留。不過，新內容在第一次編輯時並不會複製到文件保留庫，而只有在刪除時才會。若要保留所有檔案版本，您必須開啟版本設定 — 請參閱以下關於版本的章節。
  
請注意，如果使用者嘗試刪除受限於保留原則的文件庫、清單、資料夾或網站，使用者將會收到錯誤訊息。如果資料夾受限於原則，使用者一開始就移動或刪除資料夾內的任何檔案，則使用者可以刪除資料夾。另外請注意，文件保留庫只會在第一個項目必須複製到文件庫的時候建立，而不是建立保留原則的時候。因此，若要測試原則，您首先必須在受限於原則的網站中編輯或刪除文件，然後瀏覽至文件保留庫檢視保留的副本。
  
![在 SharePoint 和 OneDrive 中的內容生命週期的圖表](media/Retention_Diagram_of_retention_flow_in_sites.png)
  
將保留原則指派給 OneDrive 帳戶或 SharePoint 網站之後，內容可以依循下列兩個途徑之一：
  
1. **若已修改或刪除內容**：在保留期間，文件保留庫中會建立指派保留原則時即存在之原始內容的複本。 計時器工作會在此處定期執行，並識別保留期間已過期的項目，這些項目將被移置第二階段資源回收桶，並會在 93 天後永久刪除。 請注意，終端使用者無法檢視第二階段資源回收筒（只能看到第一階段資源回收筒），但網站集合管理員可以檢視且還原在該處的內容。

    > [!NOTE]
    > 我們最近已變更保留文件庫中刪除內容的方式。 為了防止意外的資料遺失，我們不再永久刪除保留文件庫中的內容。 相反地，我們只永久刪除資源回收筒中的內容。所以保留文件庫中的所有內容將移至第二階段資源回收筒。
    
2. 在保留期間，**如果未修改或刪除內容**，則內容會在保留期間結束時移至第一階段資源回收筒。如果使用者從該處刪除內容，或清空此資源回收筒 (也稱為清除)，則文件會移至第二階段資源回收筒。93 天保留期間涵蓋了第一和第二階段資源回收筒。在 93 天保留期間結束時，將永久刪除第一或第二階段資源回收筒中的文件。請注意，資源回收筒未編製索引，因此搜尋不會在該處尋找內容。這表示，eDiscovery 保留無法在資源回收筒中找到任何內容來保留。 
    
### <a name="content-in-mailboxes-and-public-folders"></a>信箱與公用資料夾中的內容

對於使用者的信箱、行事曆和其他項目，保留原則會在信箱層級套用。對於公用資料夾，保留原則會套用在資料夾層級套用，而不是信箱層級。信箱和公用資料夾都是使用 [可復原的項目] 資料夾來保留項目。已指派 eDiscovery 權限的人員可以檢視其他使用者的 [可復原的項目] 資料夾中的項目。 
  
根據預設，當使用者刪除 [刪除的郵件] 資料夾以外的資料夾中的郵件時，該郵件會移至 [刪除的郵件] 資料夾。當使用者刪除 [刪除的郵件] 資料夾中的項目時，郵件會移至 [可復原的項目] 資料夾。此外，使用者可以將任何資料夾中的項目虛刪除 (SHIFT+DELETE)，這會略過 [刪除的郵件] 資料夾，並將項目直接移至 [可復原的項目] 資料夾。
  
程序會定期評估 [可復原的項目] 資料夾中的項目。如果項目不符合至少一個保留原則的規則，則系統會從 [可復原的項目] 資料夾中永久刪除項目 (也稱為硬刪除)。
  
當使用者嘗試變更信箱項目的特定內容時 (例如主旨、內文、附件、寄件者和收件者，或是傳送或接收郵件的日期)，在認可變更之前，會先將原始項目的複本儲存至 [可復原的項目] 資料夾。後續每次變更時都會執行此動作。在保留期間結束時，即會永久刪除 [可復原的項目] 資料夾中的複本。
  
如果使用者離職，且其信箱包含在保留原則中，則一旦刪除使用者的 Office 365 帳戶，信箱就會變成非作用中信箱。非作用中信箱的內容仍受限於信箱在變成非作用中之前放置在其上的任何保留原則，而且 eDiscovery 可搜尋此內容。如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。
  
![電子郵件和公用資料夾中的保留流程圖](media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)
  
將保留原則指派給信箱或公用資料夾之後，內容可以依循下列兩個途徑之一：
  
1. 在保留期間，**如果使用者已永久修改或刪除項目** (按 SHIFT+DELETE 或從 [刪除的郵件] 中刪除)，則項目會移至 (或在編輯的情況下複製到) [可復原的項目] 資料夾。在那裡，此程序會定期執行，並識別其保留期間已過期的項目，而且會在保留期間結束後的 14 天內永久刪除這些項目。請注意，14 天是預設設定，但它最多可設為 30 天。
    
2. 在保留期間，**如果未修改或刪除項目**，則相同的程序會在信箱中的所有資料夾上定期執行，並識別其保留期間已過期的項目，而且會在保留期間結束後的 14 天內永久刪除這些項目。請注意，14 天是預設設定，但它最多可設為 30 天。 
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>保留原則如何使用網站集合中的文件版本

版本設定是 SharePoint Online 和商務用 OneDrive 中所有文件庫的功能。根據預設，版本設定會保留至少五百個主要版本，但您也可以提高此限制。如需詳細資訊，請參閱[啟用和設定清單或文件庫的版本設定](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37)。
  
保留原則會保留 SharePoint 網站集合或 OneDrive 帳戶中文件的所有版本。每次編輯或刪除受限於保留原則的文件時，版本會複製到文件保留庫。文件保留庫中文件的每個版本都會以個別項目存在，並有自己的保留期間：
  
- 如果保留原則是以建立內容的時間為基礎，則每個版本都有與原始文件相同的到期日。原始文件及其版本都在相同時間到期。
    
- 如果保留原則根據內容的前次修改時間，則每個版本都有自己的到期日，而此到期日根據為了建立該版本而修改原始文件的時間。原始文件及其版本彼此單獨到期。
    
## <a name="retaining-content-for-a-specific-period-of-time"></a>將內容保留特定的一段時間

透過保留原則，您可以無限期保留內容，或將內容保留特定的天數、月數或年數。請注意，保留內容的持續時間是從內容的存留期，而不是從套用保留原則的時間算起。您可以選擇存留期根據內容的建立時間，還是內容的前次修改時間 (適用於 OneDrive 和 SharePoint)。
  
例如，如果您想要將網站集合中的內容自從前次前次修改後保留七年，而且該網站集合中的某文件已有六年未曾修改，則若該文件後續仍未修改，則只會再保留一年。如果該文件重新編輯，則其存留期將會從新的前次修改日期算起，因而會再保留七年。
  
同樣地，如果您想要將信箱中的內容保留七年，而且六年前已傳送某訊息，則該訊息只會保留一年。對於 Exchange 內容，時間一律根據接收或傳送的日期 (它們是相同的)。根據前次修改時間保留內容僅適用於 OneDrive 和 SharePoint 中的網站內容。
  
您可以選擇是否要在保留期間結束時永久刪除內容。保留原則也可以僅刪除舊內容，而不保留它 - 請參閱下節。
  
![保留設定頁面](media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
## <a name="deleting-content-thats-older-than-a-specific-age"></a>刪除早於特定存留期的內容

保留原則可以同時保留，然後刪除內容，或僅刪除舊內容，而不保留它。
  
如果您的保留原則刪 內容，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改內容的時間算起。
  
![刪除設定](media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
例如，假設您建立三年後刪除內容的保留原則，然後將該原則指派給所有 OneDrive 帳戶，其中包含許多四或五年前建立的內容。在此情況下，第一次指派保留原則後，很快就會刪除大量的內容。基於這個原因，**刪除內容的保留原則可以對您的內容產生相當大的影響**。 
  
因此，在第一次將保留原則指派給網站集合之前，您應先考量現有內容的存留期，以及原則對該內容可能造成的影響。您也可以在指派新原則之前先與使用者溝通，讓他們有時間評估可能的影響。請注意，只在您建立保留原則之前，檢閱其設定時才會出現此警告。
  
![有關刪除內容的警告](media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions"></a>只將原則套用到符合特定條件之內容的進階設定

保留原則可以套用至其包含之位置中的所有內容，或您可以選擇只將保留原則套用到包含特定關鍵字或[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。
  
![進階保留選項](media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="retain-content-that-contains-specific-keywords"></a>保留包含特定關鍵字的內容

您可以只將保留原則套用至符合特定條件的內容，然後只對該內容採取保留動作。可使用的條件現在支援將保留原則套用至包含特定字詞或片語的內容。您可以使用 AND、OR、NOT 等搜尋運算子來精簡查詢。如需這些運算子的詳細資訊，請參閱[內容搜尋的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
即將推出對新增可搜尋屬性 (例如 **subject:**) 的支援。
  
請注意，查詢型保留會使用搜尋索引來識別內容。
  
![查詢編輯器](media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="retain-content-that-contains-sensitive-information"></a>保留包含敏感資訊的內容

您也可以只將保留原則套用至包含[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。例如，您可以選擇只將唯一的保留需求套用至包含個人識別資訊 (PII) 的內容，例如納稅人身分識別碼、社會安全編號或護照號碼。
  
![敏感資訊類型頁面](media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
附註：
  
- 敏感資訊的進階保留不適用於 Exchange 公用資料夾或商務用 Skype，因為這些位置不支援敏感資訊類型。
    
- 您應該了解 Exchange Online 會使用郵件流程規則 (也稱為傳輸規則) 來識別敏感資訊，因此這僅適用於傳輸中的郵件，不適用於已儲存在信箱中的所有項目。對於 Exchange Online，這表示保留原則可以識別敏感資訊，並只對在原則套用至信箱**之後**收到的訊息採取保留動作。(請注意，上一節所述的查詢型保留並沒有這項限制，因為它會使用搜尋索引來識別內容)。 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>將保留原則套用到整個組織或特定位置

您可以輕鬆地將保留原則套用到整個組織、整個位置，或只套用到特定位置或使用者。
  
### <a name="org-wide-policy"></a>全組織原則

保留原則的最強大功能之一，就是它會根據預設套用至 Office 365 中的各個位置，包括：
  
- Exchange 電子郵件
    
- SharePoint 網站集合
    
- OneDrive 帳戶
    
- Office 365 群組 (套用到群組信箱、網站和文件中的內容。 即將推出對於 Planner、Yammer、CRM Microsoft 小組、PowerBI、Stream、Exchange 和 SharePoint 小組網站中內容的支援。)
    
- Exchange 公用資料夾
    
![所有位置選項](media/c343bd8e-42ac-4f17-a338-36f3c9598a86.png)
  
全組織保留原則的其他重要功能包含：
  
- 原則可以包含的信箱或網站數目沒有任何限制。
    
- 對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承此原則。


  
### <a name="a-policy-that-applies-to-entire-locations"></a>套用到整個組織的原則

當選擇位置時，您可以輕鬆地包含或排除整個位置，例如 Exchange 電子郵件或 OneDrive 帳戶。若要這麼做，只需將該位置的 [狀態]**** 切換為開啟或關閉。 
  
如同全組織原則一般，若原則套用到整個位置的任何組合，則原則可以包含的信箱或網站數目沒有限制。例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，則所有網站和信箱都會包含在內，無論有多少。對於 Exchange，套用原則後建立的任何新信箱都會自動繼承此原則。
 
![選擇位置頁面](media/6ac0c2d6-1abf-4690-b3f6-9ca506887ba3.png)
  
### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>具有特定包含或排除的原則

您也可以將保留原則套用至特定使用者。若要這麼做，請將該位置的 [狀態]**** 切換為開啟，然後使用連結來包含或排除特定使用者、Office 365 群組或位置。 
  
不過請注意，包含或排除超過 1000 個特定使用者的保留原則有下列限制：
  
- 這類保留原則最多可包含 1,000 個信箱和 100 個網站集合。
    
- 一個租用戶最多可包含 10,000 個保留原則。
    
雖然有這些限制，但請了解您可以套用全組織原則或套用到整個位置的原則來超過這些限制。
  
### <a name="skype-locations"></a>Skype 位置

不同於 Exchange 電子郵件，您無法僅將 Skype 位置的狀態切換為開啟，即可包含所有使用者，但您可以開啟該位置，然後手動選擇您想要保留其交談的使用者。
  
選擇商務用 Skype 使用者時，您可以選取直欄標題中的 [名稱]**** 方塊，來快速地包含所有使用者 - 不過，請務必了解每個使用者在原則中都會算成特定包含。因此，如果包含超過 1,000 個使用者，則會套用上一節中提到的限制。在這裡選取所有 Skype 使用者，不等同於根據預設全組織原則能夠包含所有 Skype 使用者。 
  
![選擇 Skype 使用者頁面](media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
請注意，**交談歷程記錄** (Outlook 中的資料夾) 是與 Skype 封存無關的功能。使用者可以關閉**交談歷程記錄**，但會執行 Skype 的封存，方法為將 Skype 交談的複本儲存在使用者無法存取但 eDiscovery 可以使用的隱藏資料夾中。

### <a name="office-365-groups-locations"></a>Office 365 群組的位置

若要保留 Office 365 群組的內容，您需要使用 Office 365 群組位置。 即使 Office 365 群組有 Exchange 信箱，包含整個 Exchange 位置的保留原則並不會包含 Office 365 群組信箱中的內容。 套用到 Office 365 群組的保留原則同時包含群組信箱和網站。 套用至 Office 365 群組的保留原則可保護由 Office 365 群組所建立的資源，其中包括 Microsoft Teams。

此外，無法使用 Exchange 位置來包含或排除特定群組信箱。雖然 Exchange 位置最初允許選取群組信箱，但是當您嘗試儲存保留原則時，您會收到「RemoteGroupMailbox 不是Exchange 位置的有效選取項目」錯誤。 
  
### <a name="teams-locations"></a>Teams 位置

您可以使用保留原則來保留 Teams 中的聊天和通道訊息。Teams 聊天儲存在涉及聊天的每個使用者之信箱的隱藏資料夾中，而 Teams 通道訊息則儲存在團隊的群組信箱中類似的隱藏資料夾中。不過，請務必了解 Teams 會使用 Azure 提供的聊天服務，其中也會儲存此資料，而且根據預設這項服務會永遠儲存該資料。基於這個原因，我們強烈建議您使用 Teams 位置來保留和刪除 Teams 資料。使用 Teams 位置會同時從 Exchange 信箱和基礎 Azure 提供的聊天服務中永久刪除資料。如需詳細資訊，請參閱 [Microsoft Teams 中的安全性及合規性概觀](https://go.microsoft.com/fwlink/?linkid=871258)。
  
請注意，套用到 Exchange 或 Office 365 群組位置中使用者或群組信箱的保留原則不會影響 Teams 聊天和頻道訊息。即使 Teams 聊天和通道訊息儲存在 Exchange 中，它們也只會受到套用至 Teams 位置的保留原則影響。
  
我們仍在致力於 Teams 中的保留，而且即將推出額外的功能。與此同時，以下是需要注意的一些限制：
  
- **Teams 需要個別的保留原則** 當您建立保留原則，並在 Teams 位置上切換為開啟時，所有其他位置都會切換為關閉。包含 Teams 的保留原則只能包含 Teams，不得包含其他位置。 
    
- **Teams 不包含在全組織原則中** 如果建立全組織原則，則不會包含 Teams，因為它們需要個別的保留原則。 
    
- **Teams 不支援進階保留** 當建立保留原則時，如果您選擇[只將原則套用到符合某些條件之內容進階設定](#advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions)，則無法使用 Teams 位置。此時，Teams 中的保留適用於所有聊天和通道訊息內容。
    
- **只能刪除至少保留 30 天的 Teams 內容** 目前不支援建立一個原則來刪除保留不到 30 天的 Teams 內容。如果想要將此原則套用至 Teams 內容，請指定等於或大於 30 天的保留期間。 
    
- **Teams 最多可能需要 30 天來清除保留的內容** 套用至 Teams 的保留原則將刪除所有相關儲存位置中的內容。不過，一經啟動之後，Teams 用戶端可能就需要最多 30 天，根據保留原則清除內容。但是，即使內容仍會出現在 Teams 用戶端中，但在保留期間結束時，該內容不會出現在內容搜尋或 eDiscovery 中。 
    
在小組中，聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。 上傳至頻道內的檔案則會儲存在小組的 SharePoint 網站中。 因此，若要保留或刪除小組中的檔案，您需要建立適用於套用至 SharePoint 和 OneDrive 位置的保留原則。 如果想要套用原則至某個特定小組的檔案，您可以選擇該小組的 SharePoint 網站，以及該小組中使用者的 OneDrive 帳戶。
  
套用到 Teams 的保留原則可以使用[保留鎖定](#locking-a-retention-policy)。
  
![聊天和通道訊息的 Teams 位置](media/127345da-e802-4b3a-afc7-6e354dc3f409.png)
  
## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>從保留原則中排除特定類型的 Exchange 項目
您可以使用 PowerShell，從保留原則中排除特定類型的 Exchange 項目。例如，您可以排除語音信箱訊息、 IM 交談，以及信箱中的其他 商務用 Skype Online 內容。您也可以排除行事曆、附註和工作項目。僅使用 PowerShell 才能提供此功能；建立保留原則時，無法在 UI 中提供它。
  
若要這麼做，請使用 `New-RetentionComplianceRule` 和 `Set-RetentionComplianceRule` Cmdlet 中的 `ExcludedItemClasses` 參數。如需 PowerShell 的詳細資訊，請參閱下節[尋找保留原則的 PowerShell Cmdlet](#find-the-powershell-cmdlets-for-retention-policies)。


## <a name="locking-a-retention-policy"></a>鎖定保留原則
有些組織可能需要遵守由監管機構定義的法規，例如證券交易委員會 (SEC) 法規 17a-4，要求在保留原則開啟之後，不能關閉或執行較不嚴格的限制。使用「保留鎖定」，您可以鎖定原則，讓任何人 (包括系統管理員) 均無法關閉原則或執行較不嚴格的限制。
  
鎖定原則之後，任何人均無法關閉它，或從原則中移除位置。也不能修改或刪除在保留期間受限於原則的內容。鎖定原則之後，修改保留原則的唯一方式是藉由在其中新增位置，或延長其持續時間。鎖定的原則可以增加或擴充，但是無法減少或關閉。
  
因此，在您鎖定保留原則之前，**務必**了解您組織的合規性需求，並且**不要鎖定原則**，除非您確定它是您需要的原則。

### <a name="lock-a-retention-policy-by-using-powershell"></a>使用 PowerShell 鎖定保留原則
  
您僅可以使用 PowerShell 鎖定保留原則。

第一，[連接到 Office 365 安全性與合規性中心 PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=799771)。

第二，若要檢視您的保留原則清單，並尋找您想要鎖定的原則名稱，請執行 `Get-RetentionCompliancePolicy`。

![PowerShell 中保留原則的清單](media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

第三，若要在保留原則上放置保留鎖定，請執行含有將 `RestrictiveRetention` 參數設為 True 的 `Set-RetentionCompliancePolicy`，例如：

`Set-RetentionCompliancePolicy -Identity “<Name of Policy>” – RestrictiveRetention $true`

![PowerShell 中的 RestrictiveRetention 參數](media/retention-policy-preservation-lock-restrictiveretention.PNG)

執行 Cmdlet 之後，您會看到確認提示。請選擇 [全部同意]****。

![確認您在 PowerShell 想要鎖定保留原則的提示。](media/retention-policy-preservation-lock-confirmation-prompt.PNG)

現已在保留原則上放置保留鎖定。如果您執行 `Get-RetentionCompliancePolicy`，並將 `RestrictiveRetention` 參數設為 True，例如：

`Get-RetentionCompliancePolicy -Identity “<Name of Policy>” |Fl`

![顯示在 PowerShell 中已鎖定所有參數的原則](media/retention-policy-preservation-lock-locked-policy.PNG)
  
## <a name="releasing-a-retention-policy"></a>發佈保留原則

您可以隨時關閉或刪除保留原則。 當您這麼做時，保留在文件保留庫中的任何 SharePoint 或 OneDrive 的內容不會立即永久被刪除。 相反地，為了防止意外的資料遺失，我們有 30 天的寬限期，在這期間，保留文件庫中不會發生該原則的內容到期，因此，如有需要，您可以在這裡還原任何內容。 您也可以在寬限期期間再次開啟保留原則，這麼一來，將不會刪除該原則的內容。

SharePoint 和 OneDrive 中的此 30 天寬限期與 Exchange 中的 30 天延遲保留對應。 如需詳細資訊，請參閱[管理延遲保留信箱](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)。

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>原則保留，哪一個優先？

很有可能內容會套用多個保留原則，這些原則各有不同的動作 (保留、刪除或兩者) 和保留期間。哪一個優先？請放心，最低限度，由一個原則保留的內容不會被另一個原則永久刪除。
  
![原則保留圖](media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
若要了解不同的保留原則如何套用至內容，請記住以下保留原則：
  
1. **保留優先於刪除。** 假設一個保留原則要在 3 年後刪除 Exchange 電子郵件，但另一個保留原則要保留 Exchange 電子郵件 5 年再刪除。任何達到 3 年的內容會遭到刪除，在使用者檢視中看不到它們，但仍會保留在 [可復原的項目] 資料夾，直到內容達到 5 年，便會永久刪除。 
    
2. **最長保留期間優先。** 如果內容套用多個保留內容的原則，則會一直保留到最長保留期間結束為止。 
    
3. **明確包含優先於隱含包含。** 意思是： 
    
    1. 如果包含保留設定的標籤是由使用者手動指派給項目 (例如 Exchange 電子郵件或 OneDrive 文件)，則此標籤優先於在網站或信箱層級指派的原則，並優先於文件庫指派的預設標籤。例如，如果明確標籤要保留 10 年，但指派給網站的原則只要保留 5 年，則標籤優先。請注意，自動套用的標籤會被視為隱含而不是明確，因為它們是由 Office 365 自動套用。
    
    2. 如果保留原則包含特定位置 (例如特定使用者的信箱或商務用 OneDrive 帳戶)，則此原則優先於其他套用至所有使用者信箱或商務用 OneDrive 帳戶但未特地包含該使用者信箱的保留原則。
    
4. **最短刪除期間優先。** 同樣地，如果內容套用多個刪除內容的原則 (無保留)，則會在最短保留期間結束時刪除。 
    
了解保留原則從上到下的仲裁流程：如果所有原則或標籤套用的規則都在同一個層級，則流程會移到下一個層級來決定套用規則的優先順序。
  
最後，保留原則或標籤無法永久刪除 eDiscovery 保留的任何內容。保留解除時，這些內容便再度符合上述的清理程序。
  
## <a name="use-a-retention-policy-instead-of-these-features"></a>使用保留原則，而不是這些功能

單一保留原則可以輕鬆地套用到 Office 365 中的整個組織和位置，包括 Exchange Online、SharePoint Online、商務用 OneDrive 和 Office 365 群組。如果您需要保留或刪除 Office 365 中任何位置的內容，則我們建議您使用保留原則。(您也可以使用標籤與保留設定搭配 - 如需詳細資訊，請參閱[標籤概觀](labels.md)。)
  
有一些之前用來保留或刪除 Office 365 中的內容的其他功能。 如下所示。 這些功能會隨著保留原則和保留標籤繼續運作。 但建議您使用保留原則或標籤 (而非所有這些功能) 來進行資料控管。 保留原則是唯一可以同時保留及刪除 Office 365 中的內容之功能。
  
### <a name="exchange-online"></a>Exchange Online

- [管理 Office 365 安全性與合規性中心的 eDiscovery 案例](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (eDiscovery 保留) 
    
- [就地保留與訴訟暫止](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery 保留) 

- [如何找出位於 Exchange Online 信箱的保留類型](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [保留標記和保留原則](https://go.microsoft.com/fwlink/?linkid=846125)，又稱為[郵件記錄管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (僅限刪除) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和商務用 OneDrive

- [管理 Office 365 安全性與合規性中心的 eDiscovery 案例](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (eDiscovery 保留) 
    
- [在 eDiscovery 中心將內容新增至案例及保留來源](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (eDiscovery 保留) 
    
- [文件刪除原則的概觀](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (僅限刪除) 
    
- [設定就地記錄管理](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保留) 
    
- [網站關閉及刪除的使用原則](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (僅限刪除) 
    
- [資料管理原則](intro-to-info-mgmt-policies.md) (僅限刪除) 
    
請注意，如果您之前曾為了資料控管而使用任何 eDiscovery 保留，您應為主動合規性改用保留原則。 您應僅對電子文件探索使用保留。
  
### <a name="retention-policies-override-information-management-policies"></a>保留原則會覆寫資訊管理原則

在 SharePoint 網站中，您可能會使用[資訊管理原則](intro-to-info-mgmt-policies.md)來保留內容。 如果您將保留原則套用至已對清單或文件庫使用內容類型原則或資訊管理原則的站台，這些原則將會被忽略，而保留原則會有效用。 
  
## <a name="what-happened-to-preservation-policies"></a>保留原則發生了什麼情況？

如果您過去使用的是保留原則 (preservation policy)，該原則現已自動轉換為只使用保留動作的保留原則 (retention policy)，即該原則不會刪除內容。 保留原則將繼續運作，並保留您的內容，而不會要求您進行任何變更。 您可以在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/) 的 [原則]**** 頁面，或在[安全性與合規性中心](https://protection.office.com/) 的 [資料控管]**** 下的 [保留]**** 頁面上尋找這些原則。 您可以編輯保留原則以變更保留期間，但您不能進行其他變更，例如新增或移除位置。 
  
## <a name="permissions"></a>權限

您的合規性小組中負責建立保留原則的成員必須具備[安全性與合規性中心](https://protection.office.com/) 的權限。 根據預設，租用戶管理員將可存取此位置，並且可直接讓法務人員與其他人存取[安全性與合規性中心](https://protection.office.com/) ，而不需要為其提供租用戶管理員的所有權限。若要這麼做，我們建議您：移至[安全性與合規性中心](https://protection.office.com/) 的 [權限]**** 頁面，編輯 [規範管理員]**** 角色群組，將該成員加入此角色群組。 
  
如需詳細資訊，請參閱[授與使用者存取 Office 365 安全性與合規性中心的權限](/security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。
  
需要這些權限才能建立及套用保留原則。原則強制執行不需要內容的存取權。
  
## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>尋找保留原則的 PowerShell Cmdlet

若要使用保留原則 Cmdlet，您需要：
  
1. [使用遠端 PowerShell 連線到 Office 365 安全性與合規性中心](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用這些 [Office 365 安全性與合規性中心 Cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
## <a name="more-information"></a>詳細資訊

- [標籤概觀](labels.md)
- [SharePoint Online 限制](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Microsoft Teams 的限制和規格](https://docs.microsoft.com/zh-TW/microsoftteams/limits-specifications-teams) 
    

