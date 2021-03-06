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
description: 使用保留原則可以有效地控制使用者透過電子郵件、文件和交談生成的內容。 保留想要的內容，清除不想要的內容。
ms.openlocfilehash: 97b90cc84e2b14e5c63779ea8b941a5ffe64bcd7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362327"
---
# <a name="create-and-configure-retention-policies"></a>建立及設定保留原則

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

使用保留原則，主動決定是否要保留內容、刪除內容，或保留然後刪除內容，以管理貴組織的資料。

保留原則可讓您在容器層級指派相同的保留設定，以自動由該容器中的內容繼承，進而有效率地執行此工作。 例如，SharePoint 網站的所有專案、使用者 Exchange 信箱中的所有電子郵件訊息、搭配 Microsoft Teams 所使用的團隊所有頻道訊息。 如果您不確定要使用容器層級的保留原則或專案層級的保留標籤，請參閱 [保留原則及保留標籤](retention.md#retention-policies-and-retention-labels)。

如需有關保留原則及其在 Microsoft 365 中運作方式的詳細資訊，可參閱 [了解保留原則及保留標籤](retention.md)。

> [!NOTE]
> 此頁面上的資訊適用於合規性系統管理員。 如果您不是系統管理員，且想要了解你所使用之應用程式的保留原則設定方式，請與您的技術支援中心、IT 部門或系統管理員聯繫。 若您在 Teams 聊天和頻道訊息中看見有關保留原則的訊息，建議您檢閱 [關於保留原則的 Teams 訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。

## <a name="before-you-begin"></a>在您開始之前

您組織中的全域系統管理員擁有建立及管理保留標籤及其原則的完整權限。 若您未以全域系統管理員的身分登入，請參閱 [建立和管理保留標籤所需權限](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)。

## <a name="create-and-configure-a-retention-policy"></a>建立及設定保留原則

雖然保留原則可以支援在保留原則中識別為「位置」的多個服務，但您無法建立包含所有受支援位置的單一保留原則：

- Exchange 電子郵件
- SharePoint 網站
- OneDrive 帳戶
- Microsoft 365 群組
- 商務用 Skype
- Exchange 公用資料夾
- Teams 通道訊息
- Teams 聊天
- Yammer 社群訊息
- Yammer 使用者訊息

建立保留原則時若選取 Teams 或 Yammer 位置，系統會自動排除另一個位置。 這表示，應遵循的指示將取決於您是否要包含 Teams 或 Yammer 位置而定：

- [Teams 位置保留原則的指示](#retention-policy-for-teams-locations)
- [Yammer 位置保留原則的指示](#retention-policy-for-yammer-locations)
- [Teams 和 Yammer 以外位置保留原則的指示](#retention-policy-for-locations-other-than-teams-and-yammer)

當您有多個保留原則，以及當您同時使用保留標籤時，請參閱 [保留原則優先或以什麼為優先？](retention.md#the-principles-of-retention-or-what-takes-precedence) 以瞭解在相同的內容上同時有多個保留設定套用時，會有什麼樣的結果。

### <a name="retention-policy-for-teams-locations"></a>Teams 位置的保留原則

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。

2. 選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。

3. 針對 **[選擇要套用原則的位置]** 頁面，請選取 Teams 的任何或所有位置：
    - **Teams 頻道訊息**：來自標準頻道聊天和標準頻道會議的訊息，但非來自有自身原則位置的 [私人頻道](/microsoftteams/private-channels)。
    - **Teams 聊天**：來自私人一對一聊天、群組聊天和會議聊天的訊息。
    - **Teams 私人頻道訊息**：來自私人頻道聊天和私人頻道會議的訊息。 此選項目前正在預覽中推出，如果沒有顯示，請過幾天再試一次。
    
   根據預設， [會選取所有團隊和所有使用者](#a-policy-that-applies-to-entire-locations)，但您可以選取 **[編輯]** 選項來設定[特定包含或排除](#a-policy-with-specific-inclusions-or-exclusions)的保留原則。 不過，在變更預設值之前，請注意保留原則的下列結果，該保留原則在已針對包含或排除項進行設定時，會刪除郵件：
    
    - 對於群組聊天訊息和私人頻道訊息，因為訊息複本會儲存於聊天中包含的每位使用者的信箱中，所以系統會繼續從未指派此原則的使用者於「電子文件探索」結果中退回郵件複本。
    - 對於未指派此原則的使用者，已刪除的郵件將會回到其 Teams 搜尋結果中，但因為從指派給使用者之原則中已永久刪除，所以不會顯示郵件內容。

4. 在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。

   您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。 如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。

5. 完成精靈以儲存您的設定。

如需使用 Teams 保留原則並了解使用者體驗的指引，請參閱 Teams 文件的 [Microsoft Teams 的保留原則](/microsoftteams/retention-policies)。

如需 Teams 保留運作方式的技術詳細資料，包括哪些郵件元素支援保留和時間資訊及逐步範例，請參閱[了解 Microsoft Teams 的保留](retention-policies-teams.md)。

#### <a name="known-configuration-issues"></a>已知的設定問題

- 雖然您可以選取選項，在上次修改項目時開始保留期間，但是一律會使用 **項目建立時間** 的值。 對於已編輯的訊息，原始訊息的一份副本會與原始時間戳記一起儲存，以識別建立此預先編輯訊息的時間，且預先編輯後的訊息具有較新的時間戳記。

- 當您選取 **[Teams 頻道訊息]** 位置的 **[編輯]** 時，您可能會看到不是團隊的 Microsoft 365 群組。 請勿選取這些群組。

- 當您選取 Teams 聊天位置的 **[編輯]** 時，您可能會看到來賓和非信箱使用者。 保留原則並非為這些使用者設計，因此請不要選取他們。


#### <a name="additional-retention-policy-needed-to-support-teams"></a>支援 Teams 所需的其他保留原則

Teams 不僅是提供聊天和頻道訊息功能，還有更多功能。 如果您有透過 Microsoft 365 群組 (之前稱為 Office 365 群組) 建立的小組，您應該額外使用 [Microsoft 365 群組 **]** 位置來設定包含該 Microsoft 365 群組的保留原則。 此保留原則適用於群組的信箱、網站和檔案中的內容。

如果您有未與 Microsoft 365 群組連線的 Teams 位置，您需要有可以包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則，用以保留及刪除 Teams 中的檔案：

- 在聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。

- 上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。

> [!TIP]
> 當團隊未連線至 Microsoft 365 時，您可以將保留原則套用到僅特定團隊的檔案，方法是選取團隊的 SharePoint 網站，以及團隊中使用者的 OneDrive 使用者帳戶。

套用至 Microsoft 365、SharePoint 網站或 OneDrive 帳戶的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。 在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者選取檔案時，會收到「找不到檔案」錯誤。 此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。

### <a name="retention-policy-for-yammer-locations"></a>Yammer 位置的保留原則

> [!NOTE]
> Yammer 的保留原則處於預覽階段，目前不會在因保留原則而刪除郵件時通知使用者。
>
> 若要使用此功能，您的 Yammer 網路必須處於[原生模式](/yammer/configure-your-yammer-network/overview-native-mode)，而非混合模式。

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。

2. 選取 **[新增保留原則]** 以建立新的保留原則。

3. 在 **[選擇要套用原則的位置]** 頁面，請將 Yammer 的一個或兩個位置切換為開啟: **Yammer 社群訊息** 和 **Yammer 使用者訊息**。
    
    > [!IMPORTANT]
    > 雖然您可以只針對 Yammer 使用者訊息建立保留原則，但此位置的保留原則可以從 Yammer 應用程式刪除所有社群成員的社群訊息。
    > 
    > 如果您選擇這個選項，且保留原則將設定為刪除使用者訊息，請確定您了解此含意。 有關詳細資訊，請參閱 [保留功能如何 Yammer 搭配使用](retention-policies-yammer.md#how-retention-works-with-yammer)。
    
    預設會選取所有社群和使用者，但是您可以指定要包含或排除的社群和使用者，以縮小範圍。
    
    針對 Yammer 使用者訊息： 
    - 如果您保留預設值 **全部**，將不會包含 Azure B2B 來賓使用者。 
    - 如果您選取 **[包含]** 欄的 **[編輯]**，就可以將保留原則套用至外部使用者 (如果您知道其帳戶)。

4. 在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。 
    
    您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。 如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。

5. 完成精靈以儲存您的設定。

如需保留原則對 Yammer 運作方式的詳細資訊，請參閱[了解 Yammer 的保留](retention-policies-yammer.md)。

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>支援 Yammer 所需的額外保留原則

Yammer 不僅可提供社群訊息和私人訊息功能，還有更多功能。 若要保留及刪除您 Yammer 網路的電子郵件訊息，請使用 [Microsoft 365 群組 **]** 位置來設定包含用於 Yammer 的任何 Microsoft 365 群組的額外保留原則。 

若要保留及刪除 Yammer 中儲存的檔案，您需要包含 **SharePoint 網站** 或 **OneDrive 帳戶** 位置的保留原則：

- 在私人訊息中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。 

- 上傳到社群的檔案會儲存在 Yammer 社群的 SharePoint 網站中。

套用至 SharePoint 網站或 OneDrive 帳戶的保留原則可能會在刪除 Yammer 訊息之前便刪除這些訊息中參考的檔案。 在這種情況下，檔案仍會顯示在 Yammer 訊息中，但是當使用者選取檔案時，會遇到「找不到檔案」錯誤。 此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Teams 和 Yammer 以外位置的保留原則

針對適用於下列任何服務的保留原則，使用下列指示：

- Exchange：電子郵件和公用資料夾
- SharePoint：網站
- OneDrive：帳戶
- Microsoft 365 群組
- 商務用 Skype

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)，選取 **[原則]** >  **[保留]**。

2. 選取 **[新保留原則]** 以啟動 [建立保留原則] 精靈，並命名新的保留原則。

3. 針對 **[選擇套用原則的位置]** 頁面，開啟或關閉除 Teams 位置以外的任何位置。 您可以將每個位置保留為預設值，以便[將原則套用於整個位置](#a-policy-that-applies-to-entire-locations)，或[指定包含和排除](#a-policy-with-specific-inclusions-or-exclusions)。

    位置專用資訊：
    - [Exchange 電子郵件和 Exchange 公用資料夾](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint 網站和 OneDrive 帳戶](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Microsoft 365 群組](#configuration-information-for-microsoft-365-groups)
    - [商務用 Skype](#configuration-information-for-skype-for-business)

4. 在精靈的頁面上，如需 **決定是否要保留內容、刪除內容，或兩者皆可**，請指定保留及刪除內容的設定選項。

    您可以建立只會保留內容但不刪除內容的保留原則，建立會保留並於一段指定的時間後刪除內容的原則，或直接在一段時間後刪除指定內容的原則。 如需詳細資訊，請參閱此頁面上的[保留和刪除內容的設定 ](#settings-for-retaining-and-deleting-content)。

5. 完成精靈以儲存您的設定。

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Exchange 電子郵件和 Exchange 公用資料夾的設定資訊

**Exchange 電子郵件** 位置支援使用者的電子郵件、行事曆和其他信箱專案的保留，方法是套用信箱層級的保留設定。 同時支援共用信箱。

當您將保留設定套用至 **所有收件者** 時，任何 [非使用中的信箱](create-and-manage-inactive-mailboxes.md) 皆會納入。 不過，如果您變更此預設值並設定[特定包含或排除範圍](#a-policy-with-specific-inclusions-or-exclusions)，則不支援非使用中的信箱，也不會針對這些信箱套用或排除保留設定。

此外，資源信箱和 Microsoft 365 群組信箱不支援 **所有收件者** 預設，或特定包含或排除範圍。 對於 Microsoft 365 群組信箱，請改為選取 **[Microsoft 365 群組]** 位置。

如果您選擇要包含或排除的收件者，您可以選取通訊群組和啟用電子郵件功能的安全性群組。 在幕後，這些群組會在設定時自動展開，以選取群組中使用者的信箱。 如果這些群組的成員資格於稍後變更，則現有的保留原則不會自動更新。

如需有關在設定 Exchange 保留設定時包含和排除哪些信箱項目的詳細資訊，請參閱[保留與刪除包含的內容](retention-policies-exchange.md#whats-included-for-retention-and-deletion)

**Exchange 公用資料夾** 位置會將保留設定套用至所有的公用資料夾，且無法在資料夾或信箱層級套用。

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>SharePoint 網站和 OneDrive 帳戶的配置資訊

當您選擇 [SharePoint 網站 **]** 位置時，保留原則即可保留及刪除在 SharePoint 通訊網站中的文件、未由 Microsoft 365 群組連結的小組網站，以及傳統網站。 此選項不支援由 Microsoft 365 群組所連線的小組網站，而是會使用套用至群組信箱、網站和檔案中內容的 [Microsoft 365 群組 **]** 位置。

雖然保留原則可套用到網站層級，但只有文件會套用保留設定。 如需有關在設定 SharePoint 和 OneDrive 保留設定時所包含和排除之內容的詳細資訊，請參閱 [保留與刪除所包含的內容](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion)。 

當您為 SharePoint 網站或 OneDrive 帳戶指定您的位置時，您不需要存取網站的權限，而當你在 **[編輯位置]** 頁面上指定 URL 時也不會需要進行任何的驗證。 不過，您指定的 SharePoint 網站會在精靈結束時進行檢查，以確認其存在。 如果此檢查失敗，您會看到一則訊息，指出您輸入的 URL 驗證失敗，且精靈不會建立保留原則，直到驗證檢查通過為止。 如果您看到這則訊息，請返回精靈並變更 URL 或從保留原則將網站移除。

若要特別指定包含或排除某個 OneDrive 帳戶，URL 的格式要求如下：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

例如，針對 contoso 租用戶中使用者名稱為 "rsimone" 的使用者：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

若要驗證租用戶的語法並識別使用者的 URL，請參閱[取得組織中所有使用者的 OneDrive URL 清單](/onedrive/list-onedrive-urls) (部分機器翻譯)。

### <a name="configuration-information-for-microsoft-365-groups"></a>Microsoft 365 群組的設定資訊

若要保留或刪除一個 Microsoft 365 群組 (之前稱為 Office 365 群組) 的內容，請使用 [Microsoft 365 群組 **]** 位置。 即使 Microsoft 365 群組有 Exchange 信箱，包含整個 **Exchange 電子郵件** 位置的保留原則並不會包含 Microsoft 365 群組信箱中的內容。 雖然 **Exchange 電子郵件** 位置一開始會允許您指定要包括或排除的群組信箱，但是當您嘗試儲存保留原則時，您會收到 "RemoteGroupMailbox" 不是 Exchange 位置之有效選項的錯誤訊息。

根據預設，套用到 Microsoft 365 群組的保留原則包括群組信箱和 SharePoint 小組網站。 此位置涵蓋儲存在 SharePoint 小組網站中的檔案，但不涵蓋有自己的保留原則位置的小組聊天或小組頻道訊息。

若因為您希望保留原則只套用至 Microsoft 365 信箱，或只套用至已連結的 SharePoint 小組網站而要變更預設值，請使用 [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell Cmdlet 與具有下列其中一個值的 *應用程式* 參數：

- `Group:Exchange` 只針對已連結到群組的 Microsoft 365 信箱。
- `Group:SharePoint` 只針對已連結至群組的 SharePoint 網站。

若要回到所選 Microsoft 365 群組的信箱和 SharePoint 網站的預設值，請指定 `Group:Exchange,SharePoint`。

### <a name="configuration-information-for-skype-for-business"></a>商務用 Skype 的設定資訊

不同於其他位置，您無法將 Skype 位置的狀態切換為開啟以自動包含所有使用者。 相反地，當您開啟該位置時，您接下來必須選取 [編輯] 選項，以手動選擇您想要保留與其交談的使用者:

![編輯保留原則的 Skype 位置](../media/skype-location-retention-policies.png)

選取此 [編輯] 選項之後，您可以在 **商務用 Skype** 窗格中選取 [名稱] 欄位前的隱藏方塊，以快速包含所有使用者。 不過，請務必了解，會將每個使用者算成原則中的一個特定包含。 因此，如果透過選擇此方塊包含 1,000 位使用者，會與手動選取要包含的 1,000 位使用者相同，這是商務用 Skype 所支援的最大值。

請注意 Outlook 中的 **[交談記錄]** 資料夾的功能與 Skype 封存毫無關聯。 使用者可以關閉 **[交談記錄]**，但 Skype 封存的運作方式是，將 Skype 交談的複本儲存在使用者無法存取但 eDiscovery 可以使用的隱藏資料夾。

## <a name="settings-for-retaining-and-deleting-content"></a>保留和刪除內容的設定

透過在保留原則中選擇用於保留和刪除內容的設定，您的保留原則會具有下列其中一個設定達一段指定的期間：

- 僅保留

    在此設定中，請選擇 **[在特定期內保留項目]** 和 **在保留期結束時：不做任何處理**。 或者，選取 **[永遠保留項目]**。

- 保留然後刪除

    在此設定中，請選擇 **[在特定期內保留項目]** 和 **在保留期結束時：自動刪除項目**。

- 僅刪除

    在此設定中，選擇 **「只有項目達到特定存留期時才刪除它」**。

### <a name="retaining-content-for-a-specific-period-of-time"></a>將內容保留特定的一段時間

設定保留原則時，您會選擇保留項目，或將其保留特定數天、數月或數年。 或者永遠保留項目。

設定保留原則時，您可以選擇無限期保留內容，或將內容保留特定數天、數月或數年。 保留時長是從內容的存留期起算，而不是從套用保留原則的時間起算。

保留期間開始時，您還可以選擇建立內容的時間，或者對於檔案和 SharePoint、OneDrive 和 Microsoft 365 群組，還支援選擇上次修改內容的時間。

範例：

- SharePoint：如果您想要將網站集合中的項目在此內容前次修改後保留七年，而且該網站集合中的某文件已有六年未曾修改，則若該文件後續仍未修改，則只會再保留一年。如果該文件重新編輯，則其存留期將會從新的前次修改日期算起，因而會再保留七年。

- Exchange：如果您想要將信箱中的項目保留七年，而且六年前已傳送某郵件，則該郵件只會保留一年。對於 Exchange 項目，時間會根據接收電子郵件或寄出電子郵件的日期。根據前次修改時間保留項目只會套用到 OneDrive 和 SharePoint 中的網站內容。

在保留期間結束時，您會選擇是否要永久刪除內容：

![保留設定頁面](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>刪除早於特定存留期的內容

保留原則可以保留然後刪除項目，或刪除舊項目而不保留它們。

在這兩種情況下，如果您的保留原則刪除項目，請務必了解，文件刪除原則所指定的期限並不是從指派原則的時間算起，而是從建立或修改項目的時間算起。

因此，在第一次指派保留原則之前，尤其是在該原則删除項目時，請首先考慮現有內容的期限以及該原則可能對該內容產生的影響。您也可以在指派新原則前先與使用者溝通，讓他們有足夠的時間來評估可能的影響。

### <a name="a-policy-that-applies-to-entire-locations"></a>套用到整個組織的原則

當您選擇位置時，除了商務用 Skype，預設設定是當位置的狀態為 **開啟** 時的 **全部**。

將保留原則套用至整個位置的任何組合時，原則可以包含的收件者、網站、帳戶、群組等的數量沒有限制。

例如，如果原則包含所有 Exchange 電子郵件和所有 SharePoint 網站，無論有多少個網站和收件者都會全部包含。而對於 Exchange，在套用原則後建立的任何新信箱都會自動繼承原則。

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>具有特定包含或排除的原則

注意，當您使用選用設定將保留設定限定為特定使用者、特定 Microsoft 365 群組或特定網站時，需要注意根據原則而異的限制。 如需詳細資訊，請參閱[保留原則和保留標籤原則的限制](retention-limits.md)。 

若要使用選用設定限定保留設定範圍，請確保該位置的 **[狀態]** 為 **[開啟]**，然後使用連結來包含或排除特定使用者、Microsoft 365 群組或網站。

> [!WARNING]
> 如果您設定 [包含] 然後移除最後一個，則設定會還原為該位置的 **[全部]**。  儲存原則前，請確定這是您想要的設定。
>
> 例如，如果您指定一個 SharePoint 網站要包含在設定為刪除資料的保留原則中，然後移除單一網站，則預設所有 SharePoint 網站都會遵守永久刪除資料的保留原則。 Exchange 收件者、OneDrive 帳戶、Teams 聊天使用者等都適用。
>
> 在這種情況下，如果您不想讓該位置的 **[所有]** 設定遵守保留原則，可以將位置切換為 [關閉]。 或者，指定 [排除] 以免於使用原則。

## <a name="updating-retention-policies"></a>更新保留原則

在建立及儲存標籤或原則之後，部分設定無法變更，其中包括：
- 保留原則名稱和保留期間以外的保留設定，以及開始保留期間的時間。

如果您編輯保留原則，且項目已受限於保留原則中的原始設定，則除了新識別的項目以外，還會將您的更新設定自動套用至這些項目。

此更新通常相當快，但可能需要數天的時間。 當您的 Microsoft 365 位置間的原則複寫完成時，您會在 Microsoft 365 合規性中心看到保留原則的狀態從 **開啟 (處理中)** 變成 **開啟 (成功)**。

## <a name="locking-the-policy-to-prevent-changes"></a>鎖定原則以防止變更

如果您需要確保沒有人可以關閉原則、刪除原則或放寬限制，請參閱 [使用「保留鎖定」來限制變更保留原則和保留標籤原則](retention-preservation-lock.md)。
