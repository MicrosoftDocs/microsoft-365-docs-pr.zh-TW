---
title: 規劃群組管理
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: 瞭解如何規劃 Microsoft 365 群組管理。
ms.openlocfilehash: 4427f210bc1691ef04b97fa4802313078f8d0997
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049408"
---
# <a name="plan-for-governance-in-groups"></a>群組管理的規劃

Microsoft 365 群組具有一套豐富的工具，可實施貴組織可能需要的任何控管功能。 本文將引導 IT 專業人員要求適當的問題，以判斷其控管需求，以及如何根據組織設定檔來符合這些需求。

## <a name="why-microsoft-365-groups"></a>為什麼為 Microsoft 365 群組？
![影像 desc](../../media/01.png)

我們知道目前的組織使用各種各樣的工具集。 使用團隊聊天的開發人員小組、主管電子郵件，以及透過企業社交的整個組織。 因為每個群組都是唯一的，且具有自身的功能需求和 workstyle，所以使用多個協同作業工具。 有些只會使用電子郵件，有些人會主要在聊天中生活。 

如果使用者感覺其所提供的工具不符合其需求，他們就可能會下載其最愛的使用者應用程式，以支援其案例。 雖然此程式可讓使用者快速開始，但在組織中有多個登入、難於共用，而且沒有任何單一位置可供查看內容時，可讓整個組織的使用者體驗變得令人沮喪。 這個概念稱為「陰影 IT」，並對組織帶來極大的風險。 它可減少統一管理使用者存取、確保安全性和服務合規性需求的能力。

Microsoft 365 群組可提供使用者並降低其陰影的風險，方法是提供單一步驟，以共同作業所需的一些工具。 Microsoft 365 群組可讓您選擇您想要共同作業的一組人員，並輕鬆地設定要共用之人員的資源集合。 手動將許可權指派給資源是過去的工作，因為新增成員至群組時，會自動授與群組所提供之所有資產的必要許可權。

## <a name="technical-architecture"></a>技術架構

Microsoft 365 群組支援三種主要通訊方法。 可以在這些體驗內建立群組，並將其用於 Microsoft 365：
- Outlook：透過使用共用群組收件匣和行事曆的電子郵件進行協同作業
- Microsoft 小組：一種持續聊天的工作區，您可以在其中以特定子群組為基礎的各種主題，進行非正式、即時的交談
- Yammer：共同作業的企業社交體驗

> [!NOTE]
> 透過其他團隊合作應用程式建立新的群組（例如，SharePoint、Planner 或 Stream），將會建立具有 Outlook 收件匣的群組，以及連接至 Microsoft 小組的功能。

根據建立群組的位置，會自動布建特定資源，例如：
- [收件](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)匣-群組成員之間的電子郵件交談。 此收件匣具有電子郵件地址，可以設定為接受來自群組以外的人員，甚至是組織外的郵件，與傳統的通訊群組清單非常類似。
 - 行事[曆](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)–用於排程與群組相關的事件
- [SharePoint 小組網站](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)–中央存放庫，提供與群組相關的資訊、連結和內容。
- [SharePoint 文件庫](https://support.microsoft.com/en-us/office/share-group-files-in-outlook-749bc73b-90c9-4760-9b6f-9aa1cf01b403)–群組存放及共用檔案的中央位置
- [OneNote 筆記本](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)–用於收集創意、調查和資訊
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) –用於指派及管理群組成員中的專案工作
- [Yammer 群組](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)–具有交談及共用資訊的常見位置
- Microsoft 小組– Microsoft 365 中的閒談型工作區

若要深入瞭解為每個群組建立的資源，請參閱[瞭解 Microsoft 365 群組](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。

> [!NOTE]
> 透過 Yammer 或小組建立新的 Microsoft 365 群組時，群組不會出現在 Outlook 或通訊錄中，因為這些使用者之間的主要通訊會在各自的用戶端中發生。 Yammer 群組無法連線至 Microsoft 團隊。

## <a name="where-to-start-a-conversation"></a>開始交談的位置
在 Microsoft 365 內有多個地方可以進行交談。 瞭解開始交談的位置可協助組織定義通訊策略。

![影像 desc](../../media/03.png)

- 小組：聊天型工作區（高速度共同作業）–內環
   - 專為與您每天使用的人員共同作業
  - 以單一體驗將資訊放在使用者的手邊
  - 新增索引標籤、連接器和 bot
  - 即時聊天、音訊/視訊會議、記錄的會議

- Yammer：跨整個組織（enterprise 社交）進行連線–外環
  - 業務部的社區，其共同共同感興趣或專業知識的人員跨職能群組，但不一定要在日常運作中協同運作。
  - 領導能力，學習社區，以角色為基礎的社區

- Outlook 群組：新式 DL （以電子郵件為基礎的協同作業）
  - 目標通訊的廣泛目標
  - DLs 升級為 Microsoft 365 群組–[您應該升級的原因為何？](https://support.microsoft.com/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint –所有 Microsoft 365 群組的核心內容共同作業體驗
  - 每個群組都取得連線的 SharePoint 小組網站
  - 共用內容、建立自訂頁面和作者資訊
  - [將](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)現有的 SharePoint 小組網站連線至新的 Microsoft 365 群組

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>以比例管理及管理 Microsoft 365

Microsoft 365 群組具有一套豐富的工具，可實施貴組織可能需要的任何控管功能。 下一節將說明功能、建議最佳作法，並提供指導方針，以判斷進行控管需求的適當問題，以及如何符合這些需求。

**本節**內容：
- [控制誰可以建立 Microsoft 365 群組](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [群組虛刪除及還原](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [群組命名原則](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [群組到期原則](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [群組來賓存取](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [& 資訊保護的群組原則](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [升級傳統共同作業工具](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [群組報告](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>控制誰可以建立 Microsoft 365 群組
使用者可以從多個端點（包括 Outlook、SharePoint、小組及其他環境）建立群組。

![影像 desc](../../media/04.png)
> [!Tip]
>- 強烈考慮自行服務以供群組擁有者。
>- 記錄並交流如何要求群組。
>- 在您的雲端旅程中重新訪問誰可以建立群組。
>- 請考慮使用動態成員資格設定安全性群組的成員，以控制群組的建立。
>- 評估哪些群組案例可以透過動態成員資格加以管理，並允許其他人員使用自助服務。

群組中的布建主要模型有三種：開放、IT led 及可控。 下表說明每個模型的優點。

| Model          | 優點                                                   |
| -------------- | ------------------------------------------------------------ |
| 開啟（預設值） | 使用者可以視需要建立自己的群組，而不需要等候或加以干擾。 |
| IT-led         | 使用者向群組要求。 您可以在其中選取最佳共同作業工具，以滿足其需求。 |
| 控制     | 群組建立限制在特定人員、小組或服務。 若要深入瞭解，請參閱[管理誰可以建立 Microsoft 365 群組](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)。 |

您的組織可能會有特定需求，以對可以建立群組的使用者實施嚴格的控制。 請使用下表來協助決策，以決定您的組織符合您的組織的布建模型。

|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>哪一種布建模型符合您的組織需求？</li><li>您的組織是否需要將群組建立限制為系統管理員？</li><li>您的組織是否需要將群組建立限制為安全性群組成員？</li><li>您的組織是否需要根據使用者屬性（例如部門）動態建立某些群組？</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>記錄組織的群組和小組建立需求。</li><li>規劃在群組推廣中執行這些需求。</li><li>傳遞和發行您的原則，告知使用者他們可能會期望的行為</li><li>規劃在適用的情況下執行動態成員資格。</li></ul>|

> [!Important]
> 限制群組和小組的建立會降低使用者的生產力，因為許多 Microsoft 365 服務都需要建立群組才能讓服務運作。 若要深入瞭解，請參閱[為何控制誰會建立 Microsoft 365 群組？](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)

#### <a name="resources"></a>*資源*
- [管理可建立 Microsoft 365 群組的人員](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [根據物件屬性動態填入群組](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [如何將 Outlook 的 Microsoft 365 群組預設設定變更為 public 或 private](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [同步處理安全性群組與小組成員資格](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>群組虛刪除及還原
如果您已刪除 Microsoft 365 群組，預設會保留30天。 此 30 天期間稱為「虛刪除」，因為您仍可還原該群組。 30 天之後，該群組和關聯的內容將會被永久刪除，而且無法還原。

> [!Tip]
>- 將還原程式傳遞給您的使用者。
>- 訓練您的技術支援小組。
>- 追蹤即將使用 PowerShell script 刪除的即將進行的群組。

|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>您是否需要將特定資產封存以進行長期儲存體？</li><li>您的組織是否有某些保留需求？</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>傳遞和發行刪除及還原原則，以告知使用者他們可能期望的行為 </li><li> 記錄您的組織監控已刪除群組的需求。</li><li>規劃在群組推廣過程中執行這些需求。</li></ul>|

> [!Important]
>在「虛刪除」期間，如果使用者嘗試存取網站，則會看到 403 禁止訊息。 在此期間之後，如果使用者嘗試存取網站，則會看到 404 找不到訊息。

#### <a name="resources"></a>*資源*
- [還原已刪除的 Microsoft 365 群組](https://docs.microsoft.com/en-us/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [在 Azure Active Directory 中還原已刪除的 Microsoft 365 群組](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [使用 Remove-UnifiedGroup Cmdlet 來刪除群組](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>群組命名原則
命名原則可協助您和您的使用者識別群組、成員資格、地理區域的功能，或群組的建立者。 命名原則也可協助分類通訊錄中的群組。 您可以使用原則來封鎖群組名稱和別名中所用的特定字詞。

> [!Tip]
> - 使用簡短字串做為尾碼。
> - 使用具有值的屬性。
> - 不太創造性，總名稱長度的最大值為264個字元。
> - 上傳組織的特定封鎖文字，以限制使用。


|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>您的組織是否需要特定的組命名慣例？</li><li>您的組織是否需要跨所有工作負載的命名慣例？</li><li>您的組織是否有您要防止使用者使用的特定文字？</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>記錄組織命名群組的需求。 </li><li> 規劃在群組推廣過程中執行這些需求。</li><li> 交流及發行命名原則及標準，以告知使用者。</li></ul>|

> [!Important]
>命名原則會套用至所有群組工作負載（如 Outlook、Microsoft 小組、SharePoint、Planner、Yammer 等）上建立的群組。 它會套用至群組名稱和群組別名。 當使用者建立群組，以及為現有的群組編輯群組名稱或別名時，便會套用此方式。

#### <a name="resources"></a>*資源*
- [Microsoft 365 群組命名原則](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [在 Azure Active Directory 中強制執行 Microsoft 365 群組的命名原則](https://go.microsoft.com/fwlink/?linkid=868340)
- [用於設定群組設定的 Azure Active Directory Cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
- [群組命名的預覽功能](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>群組到期原則
管理員可以指定到期期限及任何到達該期間結束時間的任何群組，且不會被刪除。 到期期限是在建立群組時或在最後一次更新的日期時開始。 在到期之前，系統會自動將電子郵件傳送給群組擁有者，以允許使用者在其他到期間隔內更新群組。 主動群組會自動更新。

將群組設定為過期後：
- 當到期臨近時，群組的擁有者會收到更新群組的通知。
- 任何未更新的群組都已刪除
- 任何刪除的群組可在30天內由群組擁有人或系統管理員還原

> [!Tip]
> - 最初使用特定群組的試驗。
> - 根據 Microsoft 365 系統管理中心中的活動報告，選擇非使用中的群組。
> - 將更新程式告知群組擁有者。
> - 您的技術支援小組的板載。
> - 確定群組具有多個擁有者，並設定孤立群組的電子郵件。


|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>您的組織是否需要指定小組的到期日？</li><li>決定處理孤立群組的策略。</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>記錄組織的群組到期、資料保留及封存需求。</li><li>規劃在群組推廣過程中執行這些需求。</li><li>規劃實施自訂工作來報告擁有單一擁有者或 ownerless 的群組。 </li></ul>|

> [!Important]
>當您變更到期原則時，服務會重新計算每個群組的到期日。 它永遠從建立群組的日期開始計數，然後套用新的到期原則。

#### <a name="resources"></a>*資源*
- [Microsoft 365 群組到期原則](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [設定 Microsoft 365 群組的到期原則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>群組來賓存取
系統管理員可以控制是否允許來賓存取其整個組織或個別 Microsoft 365 群組的 Microsoft 365 群組。 他們也可以控制誰能允許將來賓新增至群組。
>[!Tip]
>- 在租使用者層級啟用來賓存取。 如有需要，請封鎖特定群組。
>- 使用 allow/封鎖來賓網域、訪客 inviter role、access 評論、使用條款等方式來管理。
>- 透過審核記錄檔追蹤來賓使用者活動。

|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>您是否需要限制以每個群組為單位新增來賓的功能？</li><li> 您的組織是否需要針對法律或法規遵從性需求顯示相關免責聲明？</li><li>您的組織是否需要減少新增及移除使用者的系統管理工作？</li><li>您的組織是否需要來賓/外部存取的「審核」控制？</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>針對特定分類群組的來賓/外部存取的檔需求，包括保留期間和發生次數。</li><li>記錄組織對哪些群組需要使用條款和存取權的需求。 </li><li>執行檢查以有效管理內部及來賓使用者的群組成員資格。</li></ul>|


#### <a name="resources"></a>*資源*
- [與組織外部人員合作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [在 Microsoft 365 群組中管理來賓存取](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Microsoft 365 群組中的來賓存取權](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Azure AD 存取權檢閱](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Azure Active Directory 使用條款功能](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google 同盟](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>& 資訊保護的群組原則
Microsoft 365 群組是以 Microsoft 365 的高級安全性和合規性功能為基礎，支援分類、審核與報告、符合性內容搜尋、電子探索、法律封存及保留原則。
>[!Tip]
>- 設定對應至組織需求的分類、使用指導方針及標籤。
>- 保留原則可以獨立于標籤定義。
>- 審核群組活動：建立、刪除等等。
>- 根據分類管理群組隱私權和來賓存取。

|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>您的組織是否有特定的使用需求需要與所有使用者通訊？</li><li>您的組織是否需要所有內容的分類？</li><li>您的組織是否需要在特定的一段時間內保留內容？</li><li>您的組織是否需要將特定的資料保留原則套用至群組？</li><li>您的組織是否希望能夠封存非使用中的群組，以保留內容？</li><li>群組建立者是否需要將組織特定類別指派給小組的功能？</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>記錄組織的群組使用指導方針</li><li>記錄組織的分類需求。</li><li>根據分類（如敏感度、保留、來賓存取）決定要強制執行的原則。</li><li>定義組織的靈敏度標籤，以及您想要關聯的保護設定。</li><li>定義標籤原則，以控制哪些使用者和群組可查看那些標籤。</li><li>設定[群組敏感度標籤預覽](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)，然後開始分類組織中的群組。</li><li>規劃在群組推廣中執行這些需求。</li></ul>|


#### <a name="resources"></a>*資源*
- [連結至您的 Microsoft 365 群組使用指導方針](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [為您組織中的 Office 群組建立分類](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [設定群組設定](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [保留原則概觀](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [敏感度標籤概觀](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)
- [標籤概觀](https://docs.microsoft.com/office365/securitycompliance/labels)
- [搜尋稽核記錄](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)
- [建立或移除就地法律封存](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [建立保留原則](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [在安全性 & 規範中心執行內容搜尋](https://docs.microsoft.com/Office365/SecurityCompliance/content-search)
- [使用 PowerShell 大量建立及發佈保留標籤](https://docs.microsoft.com/office365/securitycompliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>升級傳統共同作業工具
在幾年中，組織必須依靠通訊群組與公司內部和外部的人員群組進行通訊及共同作業。 不過現在，Outlook 中的 Microsoft 365 群組可提供更強大的共同作業解決方案。 此外，如果您想要讓該網站現代化，可將 Microsoft 365 群組連接至現有的 SharePoint 網站很重要。

>[!Tip]
>- 透過 Exchange 系統管理中心（或使用 PowerShell Cmdlet）輕鬆升級所有合格的通訊群組清單。
>- 將現有的 SharePoint 小組網站連線至新的 Microsoft 365 群組。

|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>貴組織是否有[未符合升級資格](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade)的通訊群組清單？<li>決定哪一種群組是最適合遷移的通訊群組清單。</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>識別哪些通訊群組清單是升級為 Microsoft 365 群組的首選。</li><li>分析您現有的 SharePoint 小組網站，以查看哪些網站已準備好進行群組連線。</li><li>讓您公司中的其他小組知道您已升級您的通訊群組，以及您採取哪些步驟讓它成功！</li></ul>|


#### <a name="resources"></a>*資源*
- [將通訊群組清單（DL）升級至 Outlook 中的群組](https://aka.ms/whyupgradedls)
- 透過 Exchange 系統管理中心或透過[PowerShell 腳本](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)，只按一下一次即可升級
- [將通訊群組清單遷移至 Microsoft 365 群組-系統管理說明](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [將現有的 SharePoint 網站連線至 Microsoft 365 群組：](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [分析和使用掃描程式資料](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint 現代化掃描器](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization)（位於 GitHub 上的工具）

### <a name="groups-reporting"></a><a name="groups-reporting"></a>群組報告
Microsoft 365 報告儀表板會顯示您組織中的所有 Microsoft 產品的活動綜述。 此功能可讓您深入了解個別產品層級報表，更加深入解析各產品內的活動。
> [!TIP]
>- 您可以使用群組報告深入瞭解組織中 Microsoft 365 群組的活動，並查看已建立及使用的群組數目。
>-您可以針對過去7天、30天、90天或180天的趨勢，查看 Microsoft 365 群組報告。
>- 監視群組間的活動群組信箱交談，群組網站/檔案活動，包含外部成員計數的群組成員資格的詳細資料。
>- 定期監控使用中群組的群組擁有者，以瞭解使用案例，並在內部 amplify。
>- 利用 Power BI 內容套件取得其他洞察力。


|         |         |         |
|---------|---------|---------|
|![影像 desc](../../media/decision_point.png)|決策點|<ul><li>您的組織是否需要定期報告，以瞭解 Microsoft 365 群組的使用方式？<li>您的組織是否需要具有外部成員之所有群組的報告？</li></ul>|
|![影像 desc](../../media/next_steps.png)|後續步驟|<ul><li>記錄組織對「定期檢查群組活動報告」的需求。</li></ul>|


#### <a name="resources"></a>*資源*
- [系統管理中心的 Microsoft 365 報告](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Office 365 採用內容套件](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD 內容套件](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph 群組活動 API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Microsoft 365 群組報告（整合群組）](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [在 Azure Active Directory 入口網站中審核活動報告](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph-使用增量查詢追蹤變更](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>根據您的雲端採用旅程開始入門

Microsoft 365 群組提供您組織可能需要的一組豐富的管理功能。 請考慮下列組織設定檔，作為瞭解最佳作法的指導，請詢問適當的問題，以判斷控管的需求，以及如何符合這些需求。

**請考慮下列組織設定檔：**
- 小型企業
- 中型企業
- 管制或企業

### <a name="small-business"></a>小型企業
請考慮已部署 Microsoft 365 的組織，其至少有 Exchange Online 和 SharePoint 線上授權，包括商務基本版和商務版的方案，以及 Enterprise E1、E3 和 E5 計畫，但沒有 Azure 主動 Director Premium 授權。

| 階段 | 說明 |
| --------------- | ------------------------------------------------------------ |
| 指引 |<ul><li>請考慮使用自助布建模型。</li><li> Outlook & SharePoint 網站中的群組[預設為私人](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395)。</li><li> 群組可以透過一次或透過 PowerShell 升級現有的通訊群組清單（DLs）來建立。 請參閱[將通訊群組清單升級至 Microsoft 365 群組](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)。</li><li> 啟用來賓存取，但使用 allow/封鎖來賓網域來管理。</li><li> 使用「群組報告」來深入瞭解使用者如何使用群組。</li><li> 請考慮建立全組織的小組 Microsoft 小組小組，以成為單一小組共同作業之一部分的方式。 </li></ul>|
| 後續步驟      |<ul><li>請考慮使用[網站設計和網站腳本](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)，使用[JSON 架構參照](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)內定義的動作，將預設設計定義為控制項。</li><li>審查[群組報告](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)。</li><li>追蹤總群組和非作用中/主動群組。</li><li>追蹤使用的 Exchange 和 SharePoint 儲存區。</li><li>跨群組信箱交談、群組網站/檔案活動等來查看群組活動。</li></ul> |

### <a name="medium-sized-business"></a>中型企業
除了上述建議之外，還請考慮下列情況：已部署 Microsoft 365 的中型企業，至少有一個企業版 E3/E5 和 Azure Active Directory Premium P1 授權。

| 階段 | 說明 |
| --------------- | ------------------------------------------------------------ |
| 指引 |<ul><li>決定開放或 IT led 的布建模型。</li><li> 考慮根據與部門類似的 Azure AD 屬性，建立與[動態成員資格規則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)相關聯的特定群組</li><li> 定義組織內的分類，例如高度機密、機密（預設值）（一般）。</li><li>  根據保留和敏感度等分類定義原則。</li><li> SharePoint 是每個 Microsoft 365 群組的內容服務。 考慮[針對三種保護層級](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection)（基準、機密和高度機密），設計及部署 SharePoint 線上網站。 如需這三種保護層級的詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)。</li><li> 預設會在 GAL 中列出公用和私人群組。 決定您想要在 Microsoft 小組外部建立的 GAL 群組中顯示哪些群組。  使用[Set-UnifiedGroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) Cmdlet 的 "HiddenFromAddressListsEnabled" 或 "HidefromExchangeClients" 隱藏特定群組。</li></ul> |
| 後續步驟      |<ul><li>定義[使用指導方針](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)，以協助您的使用者瞭解最佳作法，以協助讓使用者保持有效的群組，並在內部內容原則上進行教育。 例如，瞭解分類、原則及程式。 </li><li>定義群組必須更新或將被刪除-到期原則的群組生命週期期間。</li><li>考慮建立下列自訂工作，以根據分類實施原則。</li><li>將隱私權設定為私人。</li><li>停用外部成員資格/共用。 </li><li>電子郵件通知群組成員[沒有擁有](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)者的群組。</li><li>強制擁有權原則（最少2個擁有者）。</li><li> 根據分類定義群組的保留原則。 </li><li>保留原則的概述。</li><li>使用 Powershell 來識別具有分類和[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)的群組。</li><li>請考慮使用網站設計和網站腳本，使用[JSON 架構參照](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)內定義的動作來定義控制項。</li><li>請考慮[使用網站設計](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial)和 Microsoft 流程建立簡易網站目錄。 每當使用此網站設計建立網站時，便會捕獲網站的詳細資料，並將其寫入清單。 </li></ul>|

### <a name="regulated-or-enterprise"></a>管制或企業
除了上述建議之外，針對高管制或大型的輸入 prises （如政府、金融服務或醫療保健），您必須至少有一個企業版 E3/版本的企業版 E3/P2 授權，365才可使用此功能。

| 階段 | 說明 |
| --------------- | ------------------------------------------------------------ |
| 指引 |<ul><li> 針對以分類為基礎之群組相關聯的 SharePoint 網站，定義其資料管理原則。</li><li>[使用標籤和 DLP 來保護 SharePoint 線上](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)檔案。</li><li>[使用 Azure 資訊保護來保護 SharePoint 線上](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)檔案。</li><li> 在與使用者的慣用資料位置（[多地理](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)位置）關聯的區域中布建的群組網站。</li><li> 具有外部成員之群組的成員資格審閱（[存取權檢查](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)）。</li><li>在取得存取之前，請確定員工或來賓使用者看到相關的免責聲明以取得法律或法規遵從性需求。 （[使用條款](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)）。</li><li>以特定[分類（也就是外部使用者](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561)）識別及報告 Microsoft 365 群組。</li><li>必須使用[set-unifiedgroup 指令程式](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx)（使用 HiddenGroup-MembershipEnabled 參數）建立群組建立時的機密群組，以供需要隱藏的成員資格。</li><li>定義組織的[靈敏度標籤](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)，以[使用加密來限制存取內容](https://docs.microsoft.com/Office365/SecurityCompliance/encryption-sensitivity-labels)，併發布至特定的 Microsoft 365 群組。</li><li>使用[具有 Windows 資訊保護的敏感度標籤，](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)防止敏感內容離開您的組織在執行 windows 的裝置上。 |
| 後續步驟      | <ul><li> 使用網站設計和網站腳本，定義建立新網站時所發生的預設[動作](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/)。 例如，[設定外部共用設定](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting)或[觸發 Microsoft 流程以撥打 Azure 函式](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function)，以套用非本機支援的設定。 </li><li> 記錄需求，以[使用標籤和 DLP 來保護 SharePoint 線上](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)檔案，以與 Microsoft 365 群組相關聯的網站。</li><li>檔組織需求，以保護連線至 Microsoft 365 群組的[SharePoint Online 網站與](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files)檔案。 </li><li>記錄組織對特定使用者或群組發佈[敏感度標籤](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)的需求，以保護內容。</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>群組管理功能規劃檢查清單

您可以透過 Azure Active Directory 管理大量群組相關的控制項。 若要深入瞭解設定群組設定，請參閱[Azure Active Directory Cmdlet 以設定群組設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

請使用下表來決定部署組織需求所需的功能。 這會協助您決定所需的授權，以便您可以事先規劃。

| **功能**      | **詳細資料**                                    | **需要 Azure AD Premium 授權** | **決策** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| 群組命名原則 | 使用以前置詞尾碼為基礎的自訂封鎖文字。 | P1                                    |      TBD     |
| 群組分類 | 為小組指派分類。 | P1                                    |   TBD        |
| 群組來賓存取 | 允許或防止來賓加入群組。 | 否                                    |  TBD        |
| 群組建立 | 將小組建立限制為系統管理員。 | 否                                    |   TBD        |
| 群組建立 | 將小組建立限制為安全群組成員。 | P1                                    |     TBD      |
| 群組使用指導方針 | 設定連結會在所有群組建立端點上顯示的群組使用指導方針。 | P1                                    |   TBD        |
| 隱藏成員資格 | 從不是群組成員的使用者隱藏 Microsoft 365 群組的成員 | 否                                    |   TBD        |
| 到期原則 | 設定到期原則，以管理 Microsoft 365 群組的生命週期。 | P1                                    |  TBD        |
| 群組活動報告 | 深入瞭解組織中 Microsoft 365 群組的活動，並查看正在建立及使用的 Microsoft 365 群組數目。 | 否                                    |    TBD       |
| 保留原則 | 在 [安全性 & 規範中心] 中為 Microsoft 365 群組設定保留原則，以保留或刪除特定時段的資料。 **附注：** 使用此功能需要 Office 365 Enterprise E3 或更新版本的授權。 | 否                                    |    TBD       |
| 資料遺失防護原則 | 在 Microsoft 365 群組連線的網站中識別敏感資訊，並防止意外共用。 **附注：** 使用此功能需要 Office 365 Enterprise E3 或更新版本的授權。 | 否                                    |     TBD      |
| 封存及還原 | 當團隊不再使用中，但您想要讓它保留以供參考，或以後重新啟用時，請封存團隊。 | 否                                    |   TBD        |
| 存取權檢查 | 執行檢查以有效管理內部及來賓使用者的群組成員資格 | P2                                    |   TBD       |
| 使用條款 | 組織可用於向使用者呈現資訊的簡單方法。 此簡報可確保使用者看到相關的免責聲明以取得法律或法規遵從性需求。 | P1                                    |         TBD  |

