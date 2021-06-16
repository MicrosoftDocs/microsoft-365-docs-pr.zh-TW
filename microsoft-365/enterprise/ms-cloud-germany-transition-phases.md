---
title: '從 Microsoft Cloud Deutschland 進行遷移的遷移階段動作和影響) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：瞭解從 microsoft cloud 德國移動 (microsoft cloud Deutschland) 到新德文 datacenter 區域中 Office 365 服務的遷移階段動作和影響。
ms.openlocfilehash: c80a7cfc4f930011f65a07c4b46cdf4921766c34
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930448"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移的遷移階段動作和影響

從 microsoft Cloud (Deutschland 租使用者遷移) microsoft 的 Office 365 全域服務的地區 "德國"，會做為每個工作負載的一組階段和各自設定的動作執行。 下圖顯示遷移至新德文資料中心的十大階段。

[![遷移至新的德國資料中心 ](../media/ms-cloud-germany-migration-opt-in/migration-organization.png) 的十大階段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png#lightbox)

根據組織的整體規模和複雜度，遷移程式會在數周內完成。 進行遷移時，使用者與系統管理員可以繼續利用本檔中詳細資訊的服務。 在遷移期間，圖形和表格會定義階段和步驟。

> [!NOTE]
> Azure 服務的遷移不在本檔中。 如需相關資訊，請參閱 [Azure 德國的遷移指南](/azure/germany/germany-migration-main)。

|步驟|持續時間|負責的參與方|描述|
|:--------|:--------|:--------|:--------|
|Opt-In|小時|客戶|選擇您的組織進入遷移。|
|預備工作|天|客戶|完成準備使用者、工作站和網路以進行遷移所需的工作。|
|Azure Active Directory (Azure AD) |1-2 天|Microsoft|將 Azure AD 組織遷移至全球。|
|Azure|星期|客戶|建立新的全球性 Azure 訂閱和 [轉換 Azure 服務](/azure/azure-resource-manager/management/move-resource-group-and-subscription)。|
|訂閱 & 授權轉換|1-2 天|Microsoft|購買全球訂閱、取消 Microsoft Cloud Deutschland 訂閱及轉換使用者授權。|
|SharePoint 和 OneDrive|15 + 天|Microsoft|遷移 SharePoint 和商務用 OneDrive 內容，保留 sharepoint.de URLs。|
|Exchange Online|15 + 天|Microsoft|將 Exchange Online 內容及切換遷移至世界 URLs。|
|安全性與合規性|1-2 天|Microsoft|轉換安全性 & 合規性原則和內容。|
|商務用 Skype|1-2 天|Microsoft|從商務用 Skype 轉換成 Microsoft Teams。|
|Power BI & Dynamics 365|15 + 天|Microsoft|遷移 Power BI 及 Dynamics 365 內容。|
|完成 Azure AD|1-2 天|Microsoft|完成租使用者切換為全球。|
|Clean-Up|1-2 天|客戶|清除舊版連線至 Microsoft Cloud Deutschland，例如 Active Directory Federation Services (AD FS) 信賴憑證者信任、Azure AD 連線和 Office 用戶端重新開機。|
|已停用端點|30 天|Microsoft|完成 Azure AD 後30天之後，Microsoft Cloud Deutschland Azure AD 服務將停止已轉換組織的端點存取。 端點要求（例如驗證）會從這個點向前失敗，以進行 Microsoft Cloud Deutschland service。 在連結至 Microsoft Cloud Deutschland 中的 Office 365 服務實例中執行 Azure 工作負載的客戶，會移至稍後的最後一個遷移階段。 |

階段和其動作可確保重要資料和經驗已遷移至 Office 365 泛型服務。 租使用者新增至遷移佇列後，每個工作負載都會以後端服務執行的一組步驟完成。 某些工作負載可能需要管理員 (或使用者) ，否則遷移可能會影響[如何組織遷移時](ms-cloud-germany-transition.md#how-is-the-migration-organized)所執行和討論之階段的使用狀況？

下列各節包含當工作負載透過遷移的各個階段所進行的動作和影響。 請複習表格，並決定哪些動作或效果適用于您的組織。 確定您已準備好在必要時，依照各自階段執行步驟。 若無法完成必要的步驟，可能會造成服務中斷，而且可能會推遲完成對 Office 365 服務的遷移。

## <a name="phase-opt-in"></a>階段： Opt-In

**適用于**：在 microsoft 雲端 Deutschland 中主控 Office 365 租使用者的所有客戶 (MCD) microsoft 無法遷移 MCD 中主控 Office 365 租使用者，而不同意。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-----|:-------|
|**客戶任務**：授與遷移的同意| 客戶授與遷移的同意，讓 Microsoft 獲得遷移的許可權，並將資料和服務的轉換轉變為 Office 365 泛型服務實例。 有兩種方式 <ol><li>Office 365 承租人管理員會將您加入至 Microsoft 導向的遷移。 </li><li> 客戶已在2020年5月1日後，更新 MCD Office 365 承租人中的任何訂閱。 Microsoft 每個月都會向這些客戶通報每月遷移，請等候30天，讓客戶有機會取消，然後直接加入宣告。</li></ol> | <ul><li>承租人會標示為「遷移」，系統管理中心會顯示確認。 </li><li>確認會發佈到 Office 365 租使用者訊息中心。 服務設定會從 Microsoft Cloud Deutschland 端點繼續。 </li><li> </li></ul>
|**承租人管理員**：監視郵件|租使用者管理員必須監視 Office 365 訊息中心，以便在此時間進行遷移階段狀態的更新。|客戶可以及時執行必要的工作。
||||

## <a name="phase-1-before-the-migration-starts"></a>階段1：開始遷移

請務必熟悉 [適用于所有客戶的遷移準備步驟](ms-cloud-germany-transition-add-pre-work.md)。

若您已在您擁有的一或多個 DNS 命名空間中設定稱為 _msoid_ 的 DNS CNAME，必須先移除 CNAME，直到最後一個階段8結束。 您可以在階段8結束之前的任何時間移除 CNAME _msoid_ 。 請參閱 [DNS 的準備](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains)工作。

若要在 Microsoft 雲端 Deutschland 實例中針對 Office 365 和 Azure 使用單一登入，您必須據此準備及排程您的 Azure 訂閱遷移。 請務必瞭解[Microsoft Azure 的準備工作準備](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure)工作。

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD 連線搭配 AD FS 同盟
**適用于**：使用 AD FS 同盟的客戶

套用 **時**：第2階段開始之前

如果您使用的是 Active Directory Federation Services (AD FS) ，請務必在第2階段開始 **之前**，先在新增 Office 365 全域服務的信賴憑證者 [信任之前與之後備份 ADFS 設定](ms-cloud-germany-transition-add-adfs.md)。

## <a name="phase-2-azure-ad-migration"></a>階段2： Azure AD 遷移
在這個階段中，Azure Active Directory 將會遷移至新的資料中心區域，並成為作用中。 舊的 Azure AD 端點仍可使用。

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online混合式修改 Set-authserver 內部部署
**適用于：** 使用作用中 Exchange 混合式設定與內部部署 Exchange 伺服器的所有客戶

套用 **時**：第2階段結束之後

Set-authserver 內部部署必須指向全域 Security Token Service (STS) ，以在 Azure AD 遷移完成後進行驗證。
這可確保來自以混合式內部部署環境為目標之遷移狀態之使用者的 Exchange 可用性要求的驗證要求已驗證，可存取內部部署服務。 同樣地，這可確保來自內部部署的要求驗證，以 Office 365 泛型服務端點。 Azure AD 遷移 (階段 2) 完成之後，內部部署 Exchange (混合) 拓撲的系統管理員必須為 Office 365 泛型服務新增新的驗證服務端點。 使用此命令 Exchange PowerShell， `<TenantID>` 以 Azure Active Directory 上 Azure 入口網站中找到的組織租使用者識別碼取代。

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

無法完成此工作可能會導致混合空閒忙碌要求無法為已從 Microsoft Cloud Deutschland 遷移至 Office 365 服務的信箱使用者提供資訊。

## <a name="phase-3-subscription-transfer"></a>階段3：訂閱轉移

**適用于**：在 Microsoft 雲端 Deutschland 中主控 Office 365 租使用者的所有客戶 (MCD) 

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 轉移訂閱| Microsoft Cloud Deutschland 訂閱將會遷移到對應的 Office 365 泛型服務訂閱。 <ul><li>該訂閱的 Office 365 泛型服務是由 Microsoft (（也稱為「_提供對應_) 」）所定義。</li><li> 對應的 Office 365 全域服務訂閱會在傳輸的 Microsoft 雲端 Deutschland 訂閱的 Office 365 全域實例中購買。</li><li>舊版 Microsoft Cloud Deutschland 訂閱會在完成時從 Office 365 服務租使用者移除。</li></ul>| <ul><li>對現有訂閱所做的變更會遭到封鎖 (例如，在此階段中，不會有新的訂閱購買或座位元數目變更) 。</li><li>將會封鎖授權指派變更。</li><li>完成訂閱遷移時，Office 365 服務和 microsoft cloud Deutschland 訂閱都會顯示在 Office 365 系統管理員入口網站中，但 microsoft cloud Deutschland 訂閱的狀態為 _deprovisioned_。 </li><li>任何對 Microsoft Cloud Deutschland 訂閱或 SKU guid 產生相依性的客戶處理都將會中斷，而且必須使用 Office 365 服務選項加以修正。 </li><li>Office 365 服務中的新訂閱將會以新的字詞 (每月/每季/每年) 進行購買，客戶將會收到未使用的 Microsoft 雲端 Deutschland 訂閱餘額的按比例退款。 </li></ul> |
|已重新指派授權|在 Office 365 Global 實例中，會將授權指派給已指派 Microsoft Cloud Deutschland 授權的使用者。|<ul><li>使用者將會重新指派與新的 Office 365 服務訂閱相關聯的授權。 所有使用者的使用者授權都會自動指派給新功能。</li><li>Office 365 服務) 提供的功能 (服務方案的數量，可大於原始 Microsoft 雲端 Deutschland 提供的功能。 Office 365 服務中的使用者授權將會指派給類似的 Microsoft Cloud Deutschland 功能 (服務方案) 。 </li></ul> 
|系統 **管理員任務** 停用功能|管理員必須採取明確的動作來停用這些功能（如有必要）。 |<ul><li>使用者在入口網站中看到新的未知服務</li><li>您也可以使用其他功能 (例如，Microsoft Planner 和 Microsoft Flow) ，除非租使用者管理員停用。如需如何停用指派給使用者授權之服務方案的詳細資訊，請參閱[在指派使用者授權時停用 Microsoft 365 服務的存取權](disable-access-to-services-while-assigning-user-licenses.md)。</li></ul>
|**系統管理員任務**|使用 Office 365 服務選項，修正對 Microsoft Cloud Deutschland 訂閱或 SKU guid 產生相依性的任何客戶流程|客戶流程繼續運作。
||||

**適用** 于：使用 Office 365 合作夥伴入口網站的 Microsoft 合作夥伴

在階段2和階段3之間，可能無法存取夥伴入口網站。 在這段時間內，合作夥伴可能無法存取合作夥伴入口網站上的承租人資訊。 由於每個遷移都不同，以協助工具的持續時間可能是以小時為單位。

[合作夥伴租使用者遷移](ms-cloud-germany-transition-add-csp.md#partner-tenant-migration)提供雲端解決方案供應商的其他資訊。


## <a name="phase-4-sharepoint-online"></a>階段4：線上 SharePoint

**適用于**：所有使用 SharePoint 線上的客戶

如果您仍在使用 SharePoint 2013 工作流程，請在 SharePoint 線上遷移期間限制 SharePoint 2013 工作流程的使用。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-----|:-------|
| 轉換 SharePoint 和 OneDrive | SharePoint在此階段中，線上和商務用 OneDrive 會從 Microsoft Cloud Deutschland 遷移到 Office 365 泛型服務。<br><ul><li>現有的 Microsoft Cloud Deutschland URLs 會保留 (例如， `contoso.sharepoint.de`) 。</li><li>保留現有的網站。</li><li>Microsoft Cloud Deutschland 或 Office 365 全域服務實例中，由 Security Token Service 所發出的用戶端驗證權杖 (STS) 在轉換期間是有效的。</li></ul>|<ul><li>在遷移期間，內容將是唯讀的兩個簡短期間。 在此期間，您會發現 SharePoint 中的「無法編輯內容」橫幅。</li><li>搜尋索引不會被保留，而且可能需要最多10天才能重建。</li><li>SharePoint在遷移期間，線上和商務用 OneDrive 內容將是唯讀的兩個簡短期間。 在此期間，使用者會看到「您無法編輯內容」橫幅。</li><li>當您完成 SharePoint 線上遷移時，在重新建立索引時，可能無法使用 SharePoint 線上及商務用 OneDrive 內容的搜尋結果。 在此期間內，搜尋查詢可能不會傳回完整的結果。 與搜尋索引相關的功能（例如 SharePoint 線上新聞）可能會受到影響，而重建索引完成。</li><li>SharePoint 2013 工作流程會在遷移期間中斷，且必須在遷移之後重新發佈。</li></ul>
|**SPO Admin**：重新發佈 SharePoint 2013 工作流程| SharePoint 線上系統管理員會在遷移後重新發佈 SharePoint 2013 工作流程。| 這是必要的動作。 若失敗，可能會造成使用者混淆、協助服務台通話並降低生產力。
|**PowerShell 使用者**：更新為新模組| SharePoint Online PowerShell 模組的所有使用者都必須更新 module/16.0.20717.12000，SharePoint 線上遷移完成後，SharePointOnline 或以上版本的或更新版本。 完成會在訊息中心進行通訊。| SharePoint線上透過 PowerShell 或用戶端物件模型將不再失敗。
||||

其他考慮：

- 如果您的組織仍然使用 SharePoint 2010 工作流程，他們將無法再在 2021 12 月31日之後運作。 SharePoint 2013 工作流程仍然受到支援，不過預設為從 2020 1 月1日開始的新承租人關閉。 在完成 SharePoint 線上服務的遷移之後，建議您移至 Power Automate 或其他支援的解決方案。
 - 尚未遷移其 SharePoint 線上實例的 Microsoft 雲端 Deutschland 客戶必須保持 SharePoint 線上 PowerShell module SharePointOnline/16.0.20616.12000 版本或下列的版本。 否則，透過 PowerShell 或用戶端物件模型的 SharePoint 線上連線將會失敗。
- 在此階段中，SharePoint URLs 背後的 IP 位址會變更。 轉換為 Office 365 泛型服務之後，保留之租使用者的位址 URLs (例如， `contoso.sharepoint.de` `contoso-my.sharepoint.de`) 將變更為[全球 Microsoft 365 URLs 和 IP 位址範圍 (SharePoint 線上及商務用 OneDrive) ](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#sharepoint-online-and-onedrive-for-business)。
- 在轉換 SharePoint 和 OneDrive 服務時，Office 線上可能無法如預期般運作。 

> [!NOTE]
> 若您使用 eDiscovery，請確定您已知道 [ediscovery 遷移經驗](ms-cloud-germany-transition-add-scc.md)。

## <a name="phase-5-exchange-online"></a>階段5： Exchange Online 
從第5階段開始，Exchange Online 信箱會從 Microsoft Cloud Deutschland 移至 Office 365 泛型服務。

Office 365 泛型服務區域會設定為預設值，這可讓內部負載平衡服務在 Office 365 服務的適當預設區域中重新發佈信箱。 在此轉換中，任何一側 (MCD 或全域服務) 的使用者都位於相同的組織中，而且可以使用 URL 端點。

新的地區 "德國" 會新增至組織設定。 Exchange Online 設定會將新的隨用德國地區新增至轉換的組織。

- 將使用者和服務從舊版 MCD URLs (`https://outlook.office.de`) 轉換為新的 Office 365 服務 URLs () `https://outlook.office365.com` 。
-  新德文資料中心區域的 Exchange Online 服務 (Outlook 網頁存取及 Exchange 系統) 管理中心]，可在此階段中取得，但之前將無法使用。
- 使用者可能會在遷移期間，繼續透過舊版 MCD URLs 存取服務，但在完成遷移時，需要停止使用舊版 URLs。
- 使用者應使用全球 Office 入口網站進行 Office 線上功能 (行事曆、郵件、人員) 的轉換。 流覽至尚未遷移至 Office 365 服務的服務，在遷移之前將無法運作。 
- 這項限制也適用于背景服務，例如「我的帳戶」。 在階段9完成後，就可以使用 My Global 服務的帳戶。 在此之前，使用者必須使用 MCD 入口網站來管理其帳戶設定。
- 在遷移期間，Outlook Web App 不會提供公用資料夾體驗。

如果您想要在第5階段中修改使用者相片，請參閱[階段5的 Exchange Online PowerShell Set-UserPhoto](#exchange-online-powershell)。

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>Exchange Online 的自動探索 DNS 記錄
**適用于：** 使用具有自訂網域 Exchange Online 的客戶

在 Exchange Online 階段 (階段 5) 時，必須更新目前指向 Microsoft Cloud Deutschland 之自動探索的客戶管理 DNS 設定，以參考 Office 365 通用端點。 <br> 必須更新具有指向 autodiscover-outlook.office.de 之 CNAME 的現有 DNS 專案，以指向 **autodiscover.outlook.com**。

在 **遷移階段9完成時，** 未執行這些 DNS 更新的客戶可能會在遷移完成時遇到服務問題。

> [!NOTE]
> 可忽略自動探索專案之自訂網域之系統管理中心的驗證錯誤。 只有當 CNAME 記錄變更為 autodiscover.outlook.com 時，服務才能正常運作。

### <a name="exchange-online-powershell"></a>Exchange Online PowerShell
**適用于：** 使用 Exchange Online Exchange Online 管理員 PowerShell

在遷移階段，使用 PowerShell Cmdlet **New-MigrationEndpoint**、 **Set-MigrationEndpoint** 和 **測試 MigrationsServerAvailability** 可能會導致 proxy) 上的錯誤 (錯誤。 當仲裁信箱已遷移至世界，但不是由系統管理員信箱遷移時，就會發生這種情況。 若要解決此問題，在建立租使用者 PowerShell 會話時，請使用仲裁信箱做為 **ConnectionUri** 中的路由提示。 例如：

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```
使用 PowerShell Cmdlet **UserPhoto** 時，如果使用者信箱已遷移，但系統管理員信箱尚未遷移，將會產生錯誤，反之亦然。 在此情況下，系統管理員必須傳遞其相片在 `ConnectionUri` 建立租使用者 PowerShell 會話時需要變更之使用者的電子郵件識別碼： 
```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>" 
```
 其中 `<user_email>` 是使用者信箱之電子郵件識別碼的預留位置。 

其他考慮：
- 在其他環境中存取共用信箱的 Outlook Web App 使用者 (例如，MCD 環境中的使用者存取全域環境中的共用信箱) 系統會提示您第二次驗證。 使用者必須先驗證並存取其信箱 `outlook.office.de` ，然後開啟中的共用信箱 `outlook.office365.com` 。 當存取另一個服務中所主控的共用資源時，他們將需要第二次進行驗證。
- 若為現有的 Microsoft Cloud Deutschland 客戶或過渡中的客戶，當使用檔案 > 資訊將共用信箱新增至 Outlook 時 **> [新增帳戶**]， (Outlook 用戶端嘗試使用 Rest API) 時，可能會失敗 `https://outlook.office.de/api/v2.0/Me/Calendars` 。 想要新增帳戶以查看行事曆許可權的客戶可以新增登錄機碼，如在[Outlook 中共用行事曆的使用者經驗變更](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec)中所述，以確保此動作可成功。 使用群組原則，可在整個組織中部署此登錄機碼。
- 使用作用中 Exchange 混合式設定的所有客戶都無法將信箱從內部部署 Exchange Server 移至 Exchange Online，也不能移至 Microsoft 雲端 Deutschland，也不能移至德國的新資料中心區域。 客戶必須確定進行中的信箱移動已在階段5之前完成，並且在完成此階段後會繼續進行。
- `Test-MigrationServerAvailabiilty`在從 Microsoft Cloud Deutschland 到 Office 365 服務的 Exchange 中執行作業時執行 PowerShell Cmdlet 可能無法運作。 不過，遷移完成後，它會正常運作。
- 在遷移信箱之後，如果用戶端遇到認證或授權問題，請在遷移端點中重新輸入內部部署系統管理員認證 `Set-MigrationEndpoint -Identity <endpointName> -Credential $(Get-Credential)` ，或是使用 Exchange 控制台 (ECP) 進行設定。
- 請確定所有使用舊版通訊協定的使用者，在其 Exchange 信箱移至新的德國資料中心區域之後，將其 Exchange Online 信箱移至新的德國資料中心區域，以進行[的預先遷移步驟](ms-cloud-germany-transition-add-pre-work.md#exchange-online)中所述，在其裝置中 (POP3/IMAP4/SMTP) 。
- 在遷移信箱之後，無法再使用 Outlook Web App 排程商務用 Skype 的會議。 如有必要，使用者必須改用 Outlook。

若要深入瞭解遷移中組織的差異，以及遷移 Exchange Online 資源之後，請在[遷移至新的德國資料中心區域中的 Office 365 服務時，複查客戶體驗](ms-cloud-germany-transition-experience.md)中的資訊。

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>階段6： Exchange Online Protection/安全性與合規性

**適用于：** 所有使用 Exchange Online 的客戶<br>

後端 Exchange Online Protection (EOP) 功能會複製到新的地區 "德國"。 Exchange Online 可讓從外部主機路由傳送至 Office 365，而且會遷移歷史租使用者詳細資料，也包括後端服務的安全性和合規性功能。

使用 Exchange Online 功能的客戶，只 (非混合) 不需要在此階段引起注意。

### <a name="exchange-online-hybrid-deployments"></a>Exchange Online混合式部署
**適用于：** 使用作用中 Exchange 混合式設定與內部部署 Exchange 伺服器的所有客戶

在 **遷移步驟階段5開始之前**，請確定已套用 [Exchange 預備](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers)工作。 Exchange Online 混合式客戶必須執行最新版本的 Exchange 混合式設定向導 (HCW) in 「Office 365 德國」模式，以準備用於遷移的內部部署設定，以 Office 365 泛型服務。

**系統管理動作：**
- 在遷移階段6的開始和完成遷移階段 9 (，當郵件中心通知發佈) 時，您必須使用 [Office 365 全球設定]，將內部部署系統指向 Office 365 泛型服務，以再次執行 HCW。 無法在階段9之前完成此工作 [遷移完成] 可能會導致 NDRs 內部部署 Exchange 部署和 Office 365 之間路由傳送郵件。
- 停止或刪除任何上架或脫離信箱移動，亦不會在 Exchange 內部部署和 Exchange Online 之間移動信箱。  這可確保信箱移動要求不會失敗，併發生錯誤。 若失敗，可能會導致服務或 Office 用戶端失敗。
- Exchange Online HCW 所建立的連接器以外的其他 Send-Connectors，必須在 HCW 執行完成之後，在此階段中立即更新，否則會停止運作。 必須針對這些傳送連接器更新 TLS 網域。 <br> 若要更新 TLS 網域，請在 Exchange Server 環境中使用下列 PowerShell 命令：
```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online---transition-to-microsoft-teams"></a>階段7：商務用 Skype 線上-轉換成 Microsoft Teams
**適用于：** 所有使用商務用 Skype 線上的客戶

請複查[商務用 Skype 線上遷移的預先遷移步驟](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online)，並確定您已完成所有步驟。
在這個階段中，商務用 Skype 將會遷移至 Microsoft Teams。 現有的商務用 Skype 客戶會遷移至歐洲的 Office 365 泛型服務，然後轉換為 Office 365 服務地區 "德國" 的 Microsoft Teams。

- 使用者將無法在遷移日期登入商務用 Skype。 在遷移前10天內，客戶會在系統管理中心收到訊息，該訊息會宣佈進行遷移的時間，以及遷移開始時的時間。
- 已遷移原則設定。
- 使用者將會遷移至 Teams，而且在遷移之後將無法再存取商務用 Skype。
- 使用者必須已安裝 Microsoft Teams 桌面用戶端。 安裝會透過商務用 Skype 基礎結構上的原則在10天內進行，但如果失敗，使用者仍需下載用戶端或使用支援的瀏覽器進行連線。
- 連絡人和會議會遷移至 Microsoft Teams。
- 使用者將無法在時間服務轉換至 Office 365 服務之間登入商務用 Skype，直到客戶 DNS 專案完成為止。
- 連絡人與現有的會議將繼續充當商務用 Skype 會議。

為商務用 Skype 設定虛名網域後，必須更新 DNS 專案。 請參閱[Microsoft 365 系統管理中心的網域](https://admin.microsoft.com/Adminportal/Home#/Domains)，並在您的 DNS 設定中套用變更。 

如果您必須在遷移階段9完成之後，使用 PowerShell 連線至商務用 Skype，請使用下列 PowerShell 程式碼來連接：

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential
```

### <a name="known-limitations-until-finalizing-azure-ad-migration"></a>完成 Azure AD 遷移之前的已知限制
Microsoft Teams 會利用 Azure AD 的功能。 在未完成 Azure AD 的遷移時，有些 Microsoft Teams 的功能無法全部使用。 在階段9之後，當 Azure AD 的遷移完成後，下列功能會完全可用：

- 無法在 Microsoft Teams 系統管理中心中管理應用程式。
- 只有在 Teams 管理員已限制使用者建立新小組的許可權時，才可以在 Microsoft Teams 用戶端中建立新的團隊。 無法在 Microsoft Teams 系統管理中心中建立新的小組。 
- 無法使用 Microsoft Teams 的 web 版本。

## <a name="phase-8-dynamics-365"></a>階段8： Dynamics 365

**適用于：** 所有使用 Microsoft Dynamics 365 的客戶

請務必熟悉 [Microsoft Dynamics 365 安裝](ms-cloud-germany-transition-add-pre-work.md#dynamics365) 程式的準備工作。

具有 Dynamics 365 的客戶需要額外的合約，以獨立遷移組織的 Dynamics 組織。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| Microsoft Dynamics 資源 | microsoft dynamics 的客戶將會受到 microsoft 工程或 microsoft FastTrack 的接洽，以將 microsoft dynamics 365 轉換成 Office 365 泛型服務實例。 * |<ul><li>遷移後，系統管理員會驗證組織。 </li><li>管理員會視需要修改工作流程。 </li><li>系統管理員會視需要清除 AdminOnly 模式。</li><li>系統管理員會適當地從 _沙箱_ 變更組織類型。</li><li>通知使用者新的 URL 可以存取實例 (org) 。</li><li>更新任何與新端點 URL 的輸入連線。 </li><li>在轉換期間，使用者將無法使用 Dynamics 服務。 </li><li>使用者在遷移每個組織之後，必須驗證組織的健康情況和功能。</li></ul>|
||||

\* (i) 使用 Microsoft Dynamics 365 的客戶，必須在此遷移案例中採取動作，如所提供的遷移程式所定義。  (ii) 客戶採取行動的失敗即表示 Microsoft 將無法完成遷移。  (iii) 當 Microsoft 因客戶的 inaction 而無法完成遷移時，客戶的訂閱會在2021年10月29日到期。

## <a name="phase-8-power-bi"></a>階段8： Power BI

**適用于：** 所有使用 Microsoft Power BI 的客戶 (PBI) 

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 遷移 Power BI 資源 | 使用 microsoft Power BI (PBI) 的客戶會在手動觸發現有的 PBI 遷移工具，以將 Power BI 轉換至 Office 365 全域服務實例後，由 microsoft 工程或 microsoft FastTrack 所佔用。\*\* |<ul><li>將 _不_ 會轉換下列 Power BI 專案，而必須重新建立這些專案： <</li><li>即時資料集 (例如，流式傳送或推入資料集) 。 </li><li>Power BI 內部部署資料閘道設定和資料來源。 </li><li>在遷移後，建立在即時資料集之上的報告將無法使用，且必須重新建立。 </li><li>在轉換期間，使用者將無法使用 Power BI 服務。 無法取得服務，不應超過24小時。</li><li>遷移後，使用者將需要使用 Power BI 服務重新設定資料來源及其內部部署資料閘道。  在執行這項作業之前，使用者將無法使用這些資料來源，對這些資料來源執行排程的重新整理和/或直接查詢。 </li><li>無法遷移容量與特優工作區。 客戶必須先刪除所有容量，再進行遷移，然後在遷移之後重新建立。 視需要將工作區移回容量。</li></ul>  |
||||

\*\* (i) 使用 Microsoft 的客戶，Power BI 在遷移程式中所定義的遷移程式時，必須採取行動。  (ii) 客戶採取行動的失敗即表示 Microsoft 將無法完成遷移。  (iii) 當 Microsoft 因客戶的 inaction 而無法完成遷移時，客戶的訂閱會在2021年10月29日到期。

## <a name="phase-9-office-apps"></a>階段9： Office 應用程式

**適用于：** 所有使用 Office 桌面應用程式的客戶 (Word、Excel、PowerPoint、Outlook、OneDrive ... ) 

在這個階段中，所有用戶端應用程式和 Office Online 都執行用戶端轉換。 Azure AD 終結租使用者範圍，以指向 Office 365 服務和相關端點。

Office 365 承租人轉換至地區 "德國" 時，會要求所有使用者關閉、登出所有 Office 的桌面應用程式，以 Office 365 和傳回所有的桌面應用程式 (Word、Excel、PowerPoint、Outlook 等。在租使用者遷移到達階段9之後，) 和商務用 OneDrive 用戶端。 登出和簽出，可讓 Office 服務從全域 Azure AD 服務取得新的驗證權杖。

在執行從應用程式登出和登入後，Office 桌面應用程式無法運作，強烈建議您在受影響的機器上執行[Office 用戶端切換工具 (OCCT) ](https://github.com/microsoft/OCCT) ，以修正問題。

如果已在 Windows 用戶端上預先部署及排程[Office 用戶端轉換工具 (OCCT) ](https://github.com/microsoft/OCCT) ，則不需要登出/登入程式。

使用最近的 Office 應用程式可確保最佳的使用者體驗。 企業應該考慮使用 [每月 Enterprise] 通道。

請確定您已完成行動 [裝置](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) 的準備工作。

其他考慮：
- 通知使用者關閉所有的 Office 應用程式，然後重新登入 (或強制用戶端重新開機，或強制使用者登入) ，以啟用 Office 用戶端選擇變更。
- 通知使用者和問訊台人員使用者可能會看到 Office 橫幅，提示他們重新啟用已轉換的72小時內 Office 應用程式。
- 必須關閉個人電腦上的所有 Office 應用程式，而且使用者必須登出，然後再登入。 在黃色啟用欄中，登入以重新啟用 Office 365 服務。
- 共用電腦需要與個人電腦類似的動作，而且不需要特殊的程式。
- 在行動裝置上，使用者必須登出應用程式，並將其關閉，然後再次登入。

## <a name="phase-9-line-of-business-apps"></a>階段9：商務營運應用程式

**適用于：** 所有使用連線至 Office 365 的企業營運應用程式的客戶

若您有企業營運營運應用程式，請確定您已完成商務營運服務 [應用程式](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) 的準備工作。

## <a name="phase-9--10-azure-ad-finalization"></a>階段 9 & 10： Azure AD 完成

**適用于：** 所有客戶

當 Office 365 租使用者完成遷移的最後一個步驟時 (階段9： Azure AD 終止) ，所有服務都會轉換為全球。 任何應用程式或使用者都不應該存取任何 Microsoft Cloud Deutschland 端點的承租人資源。 自動，30天完成終止後，Microsoft Cloud Deutschland Azure AD 服務將停止已轉換租使用者的端點存取。 端點要求（例如驗證）會從這個點向前失敗，以進行 Microsoft Cloud Deutschland service。  

Microsoft Azure 客戶必須在[azure 遷移行動手冊](/azure/germany/germany-migration-main)中所述的步驟，在其租使用者完成遷移至世界 (階段 9) 之後，再轉換其 Azure 工作負載。  

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 更新使用者端點 | 確定所有使用者都使用適當的 Microsoft 全球端點存取服務 |在遷移完成後30天之後，Microsoft Cloud Deutschland 端點會停止接受要求;用戶端或應用程式流量將會失敗。  |
| 更新 Azure AD 應用程式端點 | 您必須更新驗證、Azure Active Directory (Azure AD) Graph 及 MS Graph 端點，讓應用程式成為 Microsoft 全球服務的端點。 | 在遷移完成後30天之後，Microsoft Cloud Deutschland 端點會停止接受要求;用戶端或應用程式流量將會失敗。 |
| 遷移 Azure 工作負載 | Azure 服務客戶必須針對 Azure 服務布建全球通用訂閱，並根據 [Azure 遷移行動手冊](/azure/germany/germany-migration-main)執行遷移。 | 當完全轉換為全球服務 (階段 10) 時，客戶將無法再存取 Microsoft Cloud Deutschland Azure 入口網站中呈現的 Azure 工作負載。 |
||||

**適用于：** 使用 Azure AD 註冊或加入裝置的客戶

完成階段9後，Azure AD 已註冊及加入的裝置必須連線到新德文 datacenter 區域中已轉換的 Azure AD 實例。
未重新加入至 Azure AD 的裝置可能會在階段10結束時不再運作。 如需詳細指示及詳細資訊，請參閱 [裝置的其他相關資訊](ms-cloud-germany-transition-add-devices.md)。

### <a name="azure-ad-connect"></a>Azure AD Connect
**適用于：** 與 Azure AD connect 同步處理的所有客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 更新 Azure AD 連線。 | 在完成剪切至 Azure AD 之後，組織會完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。 此時，客戶必須確定已完成的 delta 同步處理常式，然後在該程式中，將 `AzureInstance` Deutschland Microsoft Cloud) 中的字串 (值變更為登錄路徑中的 0 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | 變更登錄機碼的值 `AzureInstance` 。 若無法這麼做，將在不再提供 Microsoft Cloud Deutschland 端點後，導致物件不會進行同步處理。 |
|||||

## <a name="post-migration"></a>遷移後

請確定您已閱讀 [遷移後活動](ms-cloud-germany-transition-add-experience.md) 文章，並據此加以執行。
