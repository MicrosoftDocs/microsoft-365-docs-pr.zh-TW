---
title: 建立及設定保留原則以自動保留或刪除內容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 透過保留原則，您可以主動決定要保留內容、刪除內容，還是兩者 (保留然後刪除內容)；將單一原則套用到整個組織或套用到特定位置或使用者；以及將原則套用到所有內容或套用到符合特定條件的內容。
ms.openlocfilehash: 3a08bd67ff705b0b11b815843041b146fbef388f
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656727"
---
# <a name="create-and-configure-retention-policies"></a>建立及設定保留原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

使用保留原則主動決定是否要保留內容、刪除內容，還是兩者，即保留然後刪除內容。 

透過將相同的保留設定依照位置如網站或信箱層級的內容進行指派，保留原則可讓您工作的更有效率，。 如果您不確定是否要使用保留原則或保留標籤，可參閱[保留原則及保留標籤](retention.md#retention-policies-and-retention-labels)。

如需有關保留原則及其運作方式的詳細資訊，可參閱 [瞭解保留原則](retention.md)。

## <a name="before-you-begin"></a>在您開始之前

您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。 若您未以全域系統管理員的身分登入，請參閱 [建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。

## <a name="create-and-configure-a-retention-policy"></a>建立及設定保留原則

雖然保留原則可以支援多個位置，但您無法建立含括所有支援位置的單一個保留原則：
- Exchange 電子郵件
- SharePoint 網站
- OneDrive 帳戶
- Microsoft 365 群組
- 商務用 Skype
- Exchange 公用資料夾
- Teams 通道訊息
- Teams 聊天

當您在建立保留原則時選取任一個 Teams 位置時，系統會自動排除其他的位置。 因此，請依照您是否要涵蓋 Teams 位置來決定要遵循的指示：

- [Teams 位置的保留原則相關指示](#retention-policy-for-teams-locations)
- [除了 Teams 以外的位置保留原則相關指示](#retention-policy-for-locations-other-than-teams)

當您有多個保留原則，以及當您同時使用保留標籤時，請參閱 [保留原則優先或以什麼為優先？](retention.md#the-principles-of-retention-or-what-takes-precedence) 以瞭解在相同的內容上同時有多個保留設定套用時，會有什麼樣的結果。

### <a name="retention-policy-for-teams-locations"></a>Teams 位置的保留原則

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。

2. 選取 **[新增保留原則]** 以建立新的保留原則。

3. 在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。 
    
    您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。 如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。
    
    請勿選取 **[使用進階保留設定]**，因為 Teams 位置不支援此選項。 

4. 在 **[選擇位置]** 頁面上，選取 **[讓我選擇特定位置]**。 然後切換 Teams 的其中一個或兩個位置：**Teams 頻道訊息** 和 **[Teams 聊天]**。
     
    針對 **Teams 頻道訊息**，會包含來自標準頻道的訊息，但不會包含 [私人頻道](https://docs.microsoft.com/microsoftteams/private-channels)。 目前，保留原則尚未支援 [私人頻道]。
    
    根據預設，系統會選取所有的小組，但是您可以調整要納入的小組，或要排除的小組。

5. 完成精靈以儲存您的設定。

如需 Teams 保留原則的詳細資訊，請參閱在 Teams 文件中的 [Microsoft Teams 的保留原則](https://docs.microsoft.com/microsoftteams/retention-policies)。

#### <a name="additional-retention-policy-needed-to-support-teams"></a>支援 Teams 所需的其他保留原則

Teams 不僅是提供聊天和頻道訊息功能，還有更多功能。 如果您有透過 Microsoft 365 群組 (之前稱為 Office 365 群組) 建立的團隊，您應該額外使用 **Office 365 群組**位置來設定包含該 Microsoft 365 群組的保留原則。 此保留原則適用於群組的信箱、網站和檔案中的內容。

如果您有未與 Microsoft 365 群組連線的 Teams 位置，您需要有可以包含 **SharePoint 網站**或 **OneDrive 帳戶**位置的保留原則，用以保留及刪除 Teams 中的檔案：

- 在聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。 

- 上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。

> [!TIP]
> 當團隊未連線至 Microsoft 365 時，您可以將保留原則套用到僅特定團隊的檔案，方法是選取團隊的 SharePoint 網站，以及團隊中使用者的 OneDrive 使用者帳戶。

套用至 Microsoft 365、SharePoint 網站或 OneDrive 帳戶的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。 在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者選取檔案時，會收到「找不到檔案」錯誤。 此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。


### <a name="retention-policy-for-locations-other-than-teams"></a>除了 Teams 以外的位置保留原則

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。

2. 選取 **[新增保留原則]** 以建立新的保留原則。

3. 在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。 
    
    您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。 如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。
    
    然後決定應該將保留原則套用至所有內容，或套用至符合特定條件的內容。 如需有關這些進階保留設定的詳細資訊，請參閱此頁面上的[用來識別符合特定條件內容的進階設定](#advanced-settings-to-identify-content-that-meets-specific-conditions)。 

4. 針對 [選擇位置]**** 頁面，選取保留原則是否應套用至組織中所有支援的位置，或您想要指定位置。 如果您選擇特定位置，則也可以指定包含和排除。 
    
    如需在組織的保留原則或特定位置之間選擇的詳細資訊，請參閱此頁面上的[將保留原則套用到整個組織或特定位置](#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。
    
    位置專用資訊：
    - [Exchange 電子郵件和 Exchange 公用資料夾](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 網站和 OneDrive 帳戶](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Office 365 群組](#configuration-information-for-microsoft-365-groups)
    - [商務用 Skype ](#configuration-information-for-skype-for-business)

5. 完成精靈以儲存您的設定。


#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Exchange 電子郵件和 Exchange 公用資料夾的設定資訊

**Exchange 電子郵件** 位置支援使用者的電子郵件、行事曆和其他信箱專案的保留，方法是套用信箱層級的保留設定。

包含了以下的電子郵件項目：郵件訊息（包括草稿）具有任何的附件檔案、工作和行事曆項目（具有結束日期），以及備註。 不包含沒有結束日期標示的連絡人、任何工作和行事曆項目。 儲存在信箱中（例如 Skype 和 Teams 儲存的訊息）的其他項目不會包含在此位置。 這些項目有各自具備的保留原則。

即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件**位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。 若要保留這些信箱中的內容，請選取 **[Office 365 群組]** 位置。

**Exchange 公用資料夾** 位置會將保留設定套用至所有的公用資料夾，且無法在資料夾或信箱層級套用。

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>SharePoint 網站和 OneDrive 帳戶的配置資訊

當您選擇 **SharePoint 網站** 位置時，保留原則即可保留和刪除在 SharePoint 通訊網站中的文件、未與 Office 365 群組連結的小組網站，以及傳統網站。 此選項不支援由 Office 365 群組所連結的小組網站，而是使用套用倒群組信箱、網站和檔案中的內容的 **Office 365 群組**位置。

雖然保留原則可套用到網站層級，但只有文件會套用保留設定。 保留設定不適用於組織結構，包含像是文件庫、清單及網站內的資料夾。 

當您為 SharePoint 網站或 OneDrive 帳戶指定您的位置時，您不需要存取網站的權限，而當你在 **[編輯位置]** 頁面上指定 URL 時也不會需要進行任何的驗證。 不過，SharePoint 網站必須編制索引，而您指定的網站會在精靈結束時進行檢查，以確認這些網站是否存在。

如果此檢查失敗，您會看到一則訊息，指出您輸入的 URL 驗證失敗，且精靈不會建立保留原則，直到驗證檢查通過為止。 如果您看到這則訊息，請返回精靈並變更 URL 或從保留原則將網站移除。

若要特別指定包含或排除某個 OneDrive 帳戶，URL 的格式要求如下：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

例如，針對 contoso 租用戶中使用者名稱為 "rsimone" 的使用者：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

若要驗證租用戶的語法並識別使用者的 URL，請參閱[取得組織中所有使用者的 OneDrive URL 清單](https://docs.microsoft.com/onedrive/list-onedrive-urls) (部分機器翻譯)。

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 群組的設定資訊

若要保留或刪除一個 Microsoft 365 群組（之前稱為 Office 365 群組）的內容，請使用 **Office 365 群組** 的位置。 即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件**位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。 此外，雖然 **Exchange 電子郵件**位置一開始會允許您指定要包含或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是Exchange 位置的有效選項錯誤訊息。

套用到 Microsoft 365 群組的保留原則同時包含群組信箱和網站。 套用至 Microsoft 365 群組的保留原則可保護由 Microsoft 365 群組所建立的資源，其中包括 Microsoft Teams。

### <a name="configuration-information-for-skype-for-business"></a>商務用 Skype 的設定資訊

不同於 Exchange 電子郵件，您無法將 Skype 位置的狀態切換為開啟以包含所有使用者，但當您開啟該位置時，可以手動選擇您想要保留其交談的使用者：

![為保留原則選擇 Skype 位置](../media/skype-location-retention-policies.png)
  
當您選取 [選擇使用者]**** 時，您可以選取欄標題中的 [名稱]**** 方塊，快速包含所有使用者。 不過，請務必了解，會將每個使用者算成原則中的一個特定包含。 因此，如果您包含超過 1,000 個使用者，則會套用上一節提及的限制。 在這裡選取所有 Skype 使用者，和整個組織的原則能夠根據預設包含所有 Skype 使用者並不一樣。 
  
![選擇 Skype 使用者頁面](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
請注意，**交談歷程記錄** (Outlook 中的資料夾) 是與 Skype 封存無關的功能。使用者可以關閉**交談歷程記錄**，但會執行 Skype 的封存，方法為將 Skype 交談的複本儲存在使用者無法存取但電子文件探索可以使用的隱藏資料夾中。


## <a name="settings-for-retaining-and-deleting-content"></a>保留和刪除內容的設定

透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：

- 僅保留
- 保留然後刪除
- 僅刪除

### <a name="retaining-content-for-a-specific-period-of-time"></a>將內容保留特定的一段時間

設定保留原則時，您會選擇無限期保留內容，或將內容保留特定數天、數月或數年。 保留內容的持續時間是從內容的存留期起算，而不是從套用保留原則的時間起算。 您可以選擇存留期是否要根據內容建立的時間，或前次修改的時間 (針對 OneDrive 和 SharePoint)。

範例：
  
- SharePoint：如果您在將網站集合中的內容自上次修改起保留七年，而該網站集合中的某文件已有六年未曾修改，如果後續仍未修改該文件，則只會再保留該文件一年。 如果該文件重新編輯，則其存留期將會從新的前次修改日期起算，因而會再保留七年。
  
- Exchange：同樣地，如果您要讓信箱中的內容保留七年，而六年前已傳送過某封郵件，該郵件則只會再保留一年。 若為 Exchange 內容，時限是以收到內送電子郵件的日期，或傳送外寄電子郵件的日期為基礎。 根據前次修改時間保留內容只會套用到 OneDrive 和 SharePoint 中的網站內容。
  
在保留期間結束時，您會選擇是否要永久刪除內容：
  
![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
### <a name="deleting-content-thats-older-than-a-specific-age"></a>刪除早於特定存留期的內容

保留原則可以保留然後刪除內容，或刪除舊內容而不保留它。
  
如果您的保留原則刪 內容，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改內容的時間算起。
  
![刪除設定](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
例如，假設您建立一個刪除超過三年時間之內容的保留原則，然後將該原則指派給所有 OneDrive 帳戶，而此帳戶包含許多四或五年前建立的內容。 在此情況下，第一次指派保留原則後，很快地許多內容將會遭到刪除。 基於這個原因，請務必了解，會刪除內容的保留原則會對您的內容造成相當大的影響。 
  
因此，在第一次將保留原則指派給網站集合之前，您應先考量現有內容的存留期，以及原則對該內容可能造成的影響。您也可以在指派新原則之前先與使用者溝通，讓他們有時間評估可能的影響。請注意，只在您建立保留原則之前，檢閱其設定時才會出現此警告。
  
![有關刪除內容的警告](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-to-identify-content-that-meets-specific-conditions"></a>用來識別符合特定條件內容的進階設定

保留原則可以套用至其包含之位置中的所有內容，或您可以選擇只將保留原則套用到包含特定關鍵字或[特定類型的敏感資訊](what-the-sensitive-information-types-look-for.md)的內容。
  
![進階保留選項](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="identify-content-that-contains-specific-keywords"></a>識別包含特定關鍵字的內容

您可以將保留原則套用到僅符合特定條件的內容，然後針對該內容執行保留動作。 可用的條件可支援將保留原則套用至包含特定字詞或詞組的內容。 您可以使用 AND、OR 和 NOT 這類搜尋運算子來精簡您的查詢。 如需有關這些運算子的詳細資訊，請參閱[內容查詢的關鍵字查詢和搜尋條件](keyword-queries-and-search-conditions.md)。
  
即將推出對新增可搜尋屬性 (例如 **subject:**) 的支援。
  
查詢型保留會使用搜尋索引來識別內容。
  
![查詢編輯器](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="identify-content-that-contains-sensitive-information"></a>識別包含敏感性資訊的內容

您也可以只將保留原則套用至包含[特定類型的機密資訊](what-the-sensitive-information-types-look-for.md)之內容。例如，您可以選擇只將唯一的保留需求套用至包含個人識別資訊 (PII) 的內容，例如納稅人身分識別碼、社會安全編號或護照號碼。
  
![敏感資訊類型頁面](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
附註：
  
- 敏感資訊的進階保留不適用於 Exchange 公用資料夾或商務用 Skype，因為這些位置不支援敏感資訊類型。
    
- Exchange Online 使用郵件流程規則來識別敏感性資訊 (也稱為傳輸規則)，因此這只適用於傳輸過程中的郵件，而不是所有已儲存在信箱中的項目。 對於 Exchange Online，這表示保留原則可識別機密資訊，並只對在原則套用到信箱「之後」**** 收到的郵件執行保留動作。 上一節所述之以查詢為基礎的保留沒有此限制，因為它使用搜尋索引來識別內容。 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>將保留原則套用到整個組織或特定位置

您可以輕鬆地將保留原則套用到整個組織、整個位置，或只套用到特定位置或使用者。
  
### <a name="org-wide-policy"></a>全組織原則

保留原則最強大的功能之一，就是它可套用至 Microsoft 365 中的各個位置，包括：
  
- Exchange 電子郵件
    
- SharePoint 網站集合
    
- OneDrive 帳戶
    
- Microsoft 365 群組
    
- Exchange 公用資料夾
    

![所有位置選項](../media/retention-policies-all-locations.png)

全組織保留原則的其他重要功能包含：
  
- 原則可以包含的信箱或網站數目沒有任何限制。
    
- 對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承此原則。
  
### <a name="a-policy-that-applies-to-entire-locations"></a>套用到整個組織的原則

當您選擇位置時，您可以輕鬆地包含或排除整個位置，例如 Exchange 電子郵件或 OneDrive 帳戶。 若要這麼做，請將該位置的 [狀態]**** 切換到開啟或關閉。 
  
就像整個組織的原則一樣，如果將原則套用到整個組織的任何組合，原則可包含的信箱或網站數量則沒有限制。 

例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和信箱都會全部包含。 而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>具有特定包含或排除的原則

您也可以將保留原則套用至特定使用者、特定 Microsoft 365 群組或特定網站。 若要這麼做，請將該位置的 [狀態]**** 切換到開啟，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。 
  
不過，使用此設定時，如果您的保留原則包含或排除超過 1,000 個特定位置，則會有一些限制：
  
- 保留原則的數目上限：
    - 1000 個信箱
    - 1,000 個 Microsoft 365 群組
    - 1000 個 Teams 私人聊天使用者
    - 100 個網站 (OneDrive 或 SharePoint)

針對一個租用戶支援的原則數目上限：10,000 個。 這些項目包括保留原則、保留標籤原則，以及自動套用保留原則。

如果您的保留原則可能受限於這些限制，請選擇適用於整個位置的設定選項，或使用整個組織的原則。

## <a name="updating-retention-policies"></a>更新保留原則

如果您編輯保留原則，且內容已受限於保留原則中的原始設定，則除了新識別的內容以外，還會將您的更新設定自動套用至此內容。

此更新通常相當快，但可能需要數天的時間。 當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從**開啟 (處理中)** 變成**開啟 (成功)**。

## <a name="lock-a-retention-policy-by-using-powershell"></a>使用 PowerShell 鎖定保留原則

如果您需要使用[保留鎖定](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)才能符合法規要求，您必須使用 PowerShell。 因為系統管理員無法在套用保留鎖定之後停用或刪除保留原則，因此在 UI 中無法使用此功能來防範意外的設定。

具有任何設定的所有保留原則都支持保留鎖定。 不過，當您使用下列的 PowerShell 命令時，您會發現 **工作量** 參數永遠顯示 **Exchange、SharePoint、OneDriveForBusines、Skype、ModernGroup**，而不是反映原則中設定的實際工作量。 這只是顯示問題。

1. [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

2. 執行 [Get-RetentionCompliancePolicy](https://powershell/module/exchange/get-retentioncompliancepolicy) 列出您的保留原則清單，並尋找您想要鎖定的原則名稱。 例如：
    
   ![PowerShell 中保留原則的清單](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)
    
3. 若要將保留鎖定置於保留原則上，請以保留原則名稱執行 [Set-RetentionCompliancePolicy]( ) cmdlet，並將 *RestrictiveRetention* 參數設為 true：
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    例如：
    
    ![PowerShell 中的 RestrictiveRetention 參數](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     當系統提示時，請閱讀並確認此設定隨附的限制，然後選擇 **全部皆是**：
    
   ![確認您在 PowerShell 想要鎖定保留原則的提示。](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

保留鎖定現在放置於保留原則上。 若要確認，請再次執行 `Get-RetentionCompliancePolicy`，但指定保留原則名稱並顯示原則參數：

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

您應該會看到 **RestrictiveRetention** 設定為 **True**。 例如：

![PowerShell 中顯示所有參數的鎖定原則](../media/retention-policy-preservation-lock-locked-policy.PNG)
  

