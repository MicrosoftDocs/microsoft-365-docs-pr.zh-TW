---
title: '從 Microsoft Cloud Deutschland 遷移的遷移階段動作和影響 (一般) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
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
description: 摘要：瞭解從 Microsoft 雲端德國移動 (Microsoft Cloud Deutschland) 到新德文 datacenter 區域中的 Office 365 服務的遷移階段動作和影響。
ms.openlocfilehash: e630e88fa25bc97bcac27a032499bc31718be396
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826207"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>從 Microsoft Cloud Deutschland 遷移的遷移階段動作和影響 (一般) 

從 Microsoft Cloud Deutschland 的承租人遷移 (MCD) Microsoft Office 365 全域服務的地區 "德國"，會做為每一個工作負載的一組階段和各自設定的動作執行。 下圖顯示遷移至新德文資料中心的九個階段。

![遷移至新的德國資料中心的九個階段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

根據組織的整體規模和複雜度，遷移程式會在數周內完成。 進行遷移時，使用者與系統管理員可以繼續利用本檔中詳細資訊的服務。 在遷移期間，圖形和表格會定義階段和步驟。

|步驟|持續時間|負責的參與方|描述|
|:--------|:--------|:--------|:--------|
|Opt-In|小時|客戶|選擇您的組織進入遷移。|
|預備工作|天|客戶|完成準備使用者、工作站和網路以進行遷移所需的工作。|
|Azure Active Directory (Azure AD) |1-2 天|微軟|將 Azure AD 組織遷移至全球。|
|Azure|星期|客戶|建立新的全球性 Azure 訂閱和轉換 Azure 服務。|
|訂閱 & 授權轉換|1-2 天|微軟|購買全球訂閱、取消 Microsoft Cloud Deutschland 訂閱及轉換使用者授權。|
|SharePoint 和 OneDrive|15 + 天|微軟|遷移 SharePoint 和 OneDrive 以取得商務內容，保留 sharepoint.de URLs。|
|Exchange Online|15 + 天|微軟|將 Exchange Online 內容和轉換遷移至全球 URLs。|
|安全性與合規性|1-2 天|微軟|轉換安全性 & 合規性原則和內容。|
|商務用 Skype|1-2 天|微軟|從商務用 Skype 切換至 Microsoft 團隊。|
|Power BI & Dynamics 365|15 + 天|微軟|遷移 Power BI 及 Dynamics 365 內容。|
|完成 Azure AD|1-2 天|微軟|完成租使用者切換為全球。|
|Clean-Up|1-2 天|客戶|清除舊版連線至 Microsoft Cloud Deutschland，例如 Active Directory Federation Services (AD FS) 信賴憑證者信任、Azure AD Connect 及 Office 用戶端重新開機。|

階段和其動作可確保重要資料和經驗已遷移至 Office 365 泛型服務。 租使用者新增至遷移佇列後，每個工作負載都會以後端服務執行的一組步驟完成。 某些工作負載可能需要管理員 (或使用者) ，否則遷移可能會影響[如何組織遷移時](ms-cloud-germany-transition.md#how-is-the-migration-organized)所執行和討論之階段的使用狀況？

下列各節包含當工作負載透過遷移的各個階段所進行的動作和影響。 請複習表格，並決定哪些動作或效果適用于您的組織。 確定您已準備好在必要時，依照各自階段執行步驟。 無法完成必要的步驟，可能會造成服務中斷，而且可能會推遲完成遷移至 Office 365 服務。

## <a name="opt-in"></a>Opt-In

**適用于**：在 Microsoft Cloud Deutschland 中主控 Office 365 租使用者的所有客戶 (MCD) 

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-----|:-------|
| 我們無法在不同意的情況下，遷移 MCD 中主控的 Office 365 承租人。 | Microsoft 會以兩種方式之一提升遷移許可權，讓 Microsoft 能夠將資料和服務的轉換轉變為 Office 365 全域服務實例。 <ol><li>Office 365 租使用者管理員會將您加入至 Microsoft 導向的遷移。 </li><li> 客戶在5月1日後2020，更新 MCD Office 365 租使用者中的任何訂閱。 我們會每月向這些客戶通報每月的遷移，等候30天讓客戶有機會取消，然後直接加入宣告。</li></ol> | <ul><li>承租人會標示為「遷移」，系統管理中心會顯示確認。 </li><li>確認會發佈到 Office 365 租使用者訊息中心。 服務設定會從 Microsoft Cloud Deutschland 端點繼續。 </li><li>租使用者管理員必須監視 Office 365 訊息中心，以取得遷移階段狀態的更新。 </li></ul>|

## <a name="subscription-phase-3"></a>訂閱 (階段 3) 

**適用于**：在 Microsoft Cloud Deutschland 中主控 Office 365 租使用者的所有客戶 (MCD) 

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-----|:-------|
| 會轉移訂閱，並重新指派授權。 | 當租使用者轉換為 Office 365 服務後，會為轉接的 Microsoft 雲端 Deutschland 訂閱購買對應的 Office 365 服務訂閱。 已指派 Microsoft Cloud Deutschland 授權的使用者將會被指派 Office 365 服務授權。 舊版 Microsoft Cloud Deutschland 訂閱會從 Office 365 服務租使用者完成時移除。 | <ul><li>如果您的組織處於「授權超額」狀況， (使用超過授權的席位) 時，可能會封鎖遷移，直到修正為止。 請參閱 [預備工作](ms-cloud-germany-transition-add-pre-work.md?view=o365-worldwide#applies-to-everyone) 以瞭解如何確保您的已分配座位元數目符合所使用的席位。</li><li> 對現有訂閱所做的變更會遭到封鎖 (例如，在此階段中，不會有新的訂閱購買或座位元數目變更) 。 </li><li> 將會封鎖授權指派變更。 </li><li> Microsoft Cloud Deutschland 訂閱將會遷移到對應的 Office 365 服務訂閱。 由 Microsoft (（也稱為「 _提供對應_) 」）定義該訂閱的 Office 365 服務提供。 </li><li> Office 365 服務所提供 (服務方案) 的功能數目可以大於原始 Microsoft 雲端 Deutschland 提供的功能。 Office 365 服務中的使用者授權會指派給類似的 Microsoft Cloud Deutschland (服務方案) 中的功能。 所有使用者的使用者授權都會自動指派給新功能。 必要時，系統管理員必須採取明確的動作以停用這些授權。 </li><li> 完成訂閱遷移後，office 365 服務和德國訂閱將會顯示在 Office 365 系統管理入口網站中，並以德國訂閱狀態為 _deprovisioned_。 </li><li> 使用者將會重新指派與新 Office 365 服務訂閱相關聯的授權。 任何對德國訂閱或 SKU Guid 具有相依相依性的客戶流程，都將會中斷，且必須與 Office 365 服務選項一起修正。 </li><li> Office 365 服務中的新訂閱每月都會以新字詞購買， (每月/每季/每年) ，且客戶將會收到未使用的 Microsoft Cloud Deutschland 訂閱餘額的按比例退款。 </li><li> 將不會遷移協力廠商 Microsoft Cloud Deutschland 承租人。 CSP 客戶將會遷移到相同協力廠商的新 Office 365 服務租使用者下的 Office 365 服務。 客戶遷移後，協力廠商只可以從 Office 365 服務租使用者管理此客戶。 </li><li> 您也可以使用其他功能 (例如，Microsoft Planner 和 Microsoft Flow) ，除非租使用者系統管理員停用。如需如何停用指派給使用者授權之服務方案的詳細資訊，請參閱 [在指派使用者授權時，停用 Microsoft 365 服務的存取權](disable-access-to-services-while-assigning-user-licenses.md)。 |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint 線上 (階段 4) 

**適用于**：所有使用 SharePoint 線上的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-----|:-------|
| 轉換 SharePoint 和 OneDrive | SharePoint 線上和商務 OneDrive 會從 Microsoft Cloud Deutschland 遷移至此階段中的 Office 365 全域服務。<br><ul><li>現有的 Microsoft Cloud Deutschland URLs 會保留 (例如， `contoso.sharepoint.de`) 。</li><li>保留現有的網站。</li><li>Microsoft Cloud Deutschland 或 Office 365 全域服務實例中，由 Security Token Service 所發出的用戶端驗證權杖 (STS) 在轉換期間是有效的。</li></ul>|<ul><li>在遷移期間，內容將是唯讀的兩個簡短期間。 在此期間，您會發現 SharePoint 中的「無法編輯內容」橫幅。</li><li>搜尋索引不會被保留，而且可能需要最多10天才能重建。</li><li>在遷移期間，商務內容的 SharePoint 線上和 OneDrive 會以唯讀的兩個簡短期間為唯讀。 在此期間，使用者會看到「您無法編輯內容」橫幅。</li><li>當您完成 SharePoint 線上遷移時，在重新建立索引時，可能無法使用 SharePoint 線上及 OneDrive 商務內容的搜尋結果。 在此期間內，搜尋查詢可能不會傳回完整的結果。 與搜尋索引相關的功能（例如 SharePoint 線上新聞）可能會受到影響，而重建索引完成。</li></ul>|
||||

其他考慮：

- 如果您的組織仍然使用 SharePoint 2010 工作流程，他們將無法再在 2021 12 月31日之後運作。 SharePoint 2013 工作流程仍然受到支援，不過預設為從 2020 1 月1日開始的新承租人關閉。 在完成 SharePoint 線上服務的遷移之後，建議您移至 [電源自動化] 或其他支援的解決方案。

- 尚未遷移其 SharePoint 線上實例的 Microsoft 雲端 Deutschland 客戶必須保持 SharePoint 線上 PowerShell module SharePointOnline/16.0.20616.12000 版本或下列的版本。 否則，透過 PowerShell 或用戶端物件模型的 SharePoint 線上連線將會失敗。

- SharePoint 線上實例遷移的 Microsoft Cloud Deutschland 客戶必須更新 SharePoint 線上 PowerShell module SharePointOnline/CSOM to version 16.0.20717.12000 或以上版本。 否則，透過 PowerShell 或用戶端物件模型的 SharePoint 線上連線將會失敗。

## <a name="exchange-online-phase-5"></a>Exchange Online (階段 5) 

**適用于：** 所有使用 Exchange Online 的客戶

如果您使用的是 Exchange Online 混合式： Exchange Online 混合管理員  **必須執行混合式設定向導 (HCW)** 做為這項轉換的一部分。 請參閱 [適用于 Exchange 的預備高級遷移步驟](ms-cloud-germany-transition-add-experience.md#exchange-online-before-phase-5)

如遷移準備 [事項中所](ms-cloud-germany-transition-add-pre-work.md#exchange-online)述，在 **遷移步驟階段5開始之前，** Exchange Online 混合式客戶必須執行 Exchange 混合式設定向導的最新版本 (HCW) 在「Office 365 德國」模式中，為遷移至 Office 365 全域服務準備內部部署設定。

當 [！注意事項] 當郵件中心通知發佈完成時， **遷移階段 5** () ，您必須使用 Office 365 全球化設定重新執行 HCW，將內部部署系統指向 Office 365 泛型服務。 如果您使用自訂網域，可能需要其他的 DNS 更新。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| Exchange Online 信箱會從 Microsoft Cloud Deutschland 移至 Office 365 泛型服務。| Exchange Online 設定會將新的隨用本機德文區域新增至轉換的組織。 Office 365 泛型服務區域會設定為預設值，這可讓內部負載平衡服務將信箱重新分配至 Office 365 服務中的適當預設區域。 在此轉換中，任何一側 (MCD 或全域服務) 的使用者都位於相同的組織中，而且可以使用 URL 端點。 |<ul><li>將使用者和服務從舊版 MCD URLs (outlook.office.de) 轉換為新的 Office 365 服務 URLs (`https://outlook.office365.com`) 。</li><li>使用者可能會在遷移期間，繼續透過舊版 MCD URLs 存取服務，但在完成遷移時，需要停止使用舊版 URLs。</li><li>使用者應使用「全球 Office 入口網站」功能（ (行事曆、郵件、人員) ）轉換為 Office Online 功能。 流覽至尚未遷移至 Office 365 服務的服務，在遷移之前將無法運作。 </li><li>在遷移期間，Outlook Web App 不會提供公用資料夾體驗。 </li></ul>|
| 更新 AutoDiscover 的自訂 DNS 設定| 在 Exchange Online 階段 (階段 5) 時，必須更新目前指向 Microsoft Cloud Deutschland 之 AutoDiscover 的客戶管理 DNS 設定，以參照 Office 365 全域端點。 <br> 必須更新具有指向 autodiscover-outlook.office.de 之 CNAME 的現有 DNS 專案，以指向 autodiscover.outlook.com。 |  可用性要求和服務探索呼叫透過 AutoDiscover 直接指向 Office 365 服務。 在遷移完成後，未執行這些 DNS 更新的客戶可能會遇到自動探索服務的問題。 |
||||

其他考慮：
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` 只會在租使用者在階段9內切換之後運作。 連結會產生「發生錯誤」錯誤訊息，直到這段時間為止。

- 在其他環境中存取共用信箱的 Outlook Web App 使用者 (例如，MCD 環境中的使用者存取全域環境中的共用信箱) 會提示您第二次驗證。 使用者必須先驗證並存取其信箱 `outlook.office.de` ，然後開啟中的共用信箱 `outlook.office365.com` 。 當存取另一個服務中所主控的共用資源時，他們將需要第二次進行驗證。

- 針對現有的 Microsoft Cloud Deutschland 客戶或過渡中的客戶。使用檔案 > 資訊將共用信箱新增至 Outlook 時 **> 新增帳戶**，查看行事曆許可權可能會失敗 (Outlook 用戶端嘗試使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars` 。 ) 客戶若要新增帳戶以查看行事曆許可權，您可以新增登錄機碼，如在 [outlook 中共用行事曆的使用者經驗變更](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 中所述，此動作會成功。 使用群組原則，可在整個組織中部署此登錄機碼。

- 在遷移階段，使用 PowerShell Cmdlet **New-new-migrationendpoint**、 **Set-MigrationEndpoint** 和 **MigrationsServerAvailability** 可能會導致 proxy) 上的錯誤 (錯誤。 當仲裁信箱已遷移至世界，但不是由系統管理員信箱遷移時，就會發生這種情況。 若要解決此問題，在建立租使用者 PowerShell 會話時，請使用仲裁信箱做為 **ConnectionUri** 中的路由提示。 例如：

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

若要深入瞭解遷移中組織和遷移 Exchange Online 資源之後的差異，請在 [新的德國資料中心區域遷移至 Office 365 服務期間，查看客戶經驗](ms-cloud-germany-transition-experience.md)中的資訊。

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection/安全性與合規性 (階段 6) 

**適用于：** 所有使用 Exchange Online 的客戶<br>

後端 Exchange Online Protection (EOP) 功能會複製到新的地區 "德國"。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 遷移 Exchange Online 路由及歷史郵件詳細資料。 | Exchange Online 可讓您從外部主機路由傳送至 Office 365。 外部 MX 記錄會轉換成路由傳送至 EOP 服務。 會遷移租使用者設定及歷史記錄詳細資料。 |<ul><li>Microsoft-managed DNS 專案會從 Office 365 德國 EOP 更新為 Office 365 服務。</li><li>客戶應該等候30天之後，EOP 雙重寫入以進行 EOP 遷移。 否則，可能會遺失資料。</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>商務用 Skype Online (階段 7) 

**適用于：** 所有使用 SharePoint 線上的客戶

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->
| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 將商務用 Skype 遷移至小組。 | 現有商務用 Skype 客戶會遷移至歐洲的 Office 365 全球服務，然後轉換為 Office 365 服務地區 "德國" 的 Microsoft 小組。 |<ul><li>使用者將無法在遷移日期登入商務用 Skype。 遷移前的10天，我們會發佈到系統管理中心，讓您瞭解何時進行遷移，以及當我們開始遷移時，會發生什麼情況。</li><li> 已遷移原則設定。 </li><li>使用者將會遷移到小組，並且在遷移後將不再有商務用 Skype。 </li><li>使用者必須已安裝團隊桌面用戶端。 安裝將透過商務用 Skype 基礎結構上的原則進行，但如果失敗，使用者仍需下載用戶端或使用支援的瀏覽器進行連線。 </li><li>連絡人和會議會遷移到小組。</li><li>使用者將無法在時間服務轉換為 Office 365 服務時登入商務用 Skype，而不會在客戶 DNS 專案完成之前登入。 </li><li>連絡人和現有的會議將繼續充當商務用 Skype 會議。 </li><li>PowerShell 會使用來管理租使用者和使用者的設定和原則。 連線至 PowerShell 會話時，請新增下列專案： <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"`</li></ul>|
||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (階段 8) 

**適用于：** 所有使用 Microsoft Dynamics 365 的客戶

具有 Dynamics 365 的客戶需要額外的合約，以獨立遷移組織的 Dynamics 組織。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| Microsoft Dynamics 資源 | Microsoft Dynamics 的客戶將會受到 Microsoft 工程或 Microsoft FastTrack 的接洽，以將 Microsoft Dynamics 365 轉換成 Office 365 泛型服務實例。 * |<ul><li>遷移後，系統管理員會驗證組織。 <</li><li>管理員會視需要修改工作流程。 </li><li>系統管理員會視需要清除 AdminOnly 模式。</li><li>系統管理員會適當地從 _沙箱_ 變更組織類型。</li><li>通知使用者新的 URL 可以存取實例 (org) 。</li><li>更新任何與新端點 URL 的輸入連線。 </li><li>在轉換期間，使用者將無法使用 Dynamics 服務。 </li><li>使用者在遷移每個組織之後，必須驗證組織的健康情況和功能。</li></ul>|
|||||

\* (i) 使用 Microsoft Dynamics 365 的客戶，必須在此遷移案例中採取動作，如所提供的遷移程式所定義。  (ii) 客戶採取行動的失敗即表示 Microsoft 將無法完成遷移。  (iii) 當 Microsoft 因客戶的 inaction 而無法完成遷移時，客戶的訂閱會在2021年10月29日到期。

## <a name="power-bi-phase-8-of-9"></a>Power BI (階段8之 9) 

**適用于：** 所有使用 Microsoft Power BI 的客戶 (PBI) 

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| Power BI 資源的遷移 | 使用 Microsoft Power BI (PBI) 的客戶會在手動觸發現有的 PBI 遷移工具，將 Power BI 轉換為 Office 365 全域服務實例後，由 Microsoft 工程或 Microsoft FastTrack 進行接洽。\*\* |<ul><li>下列的 Power BI 專案將 _不_ 會轉換，必須重新建立這些專案： <</li><li>即時資料集 (例如，流式傳送或推入資料集) 。 </li><li>Power BI 內部部署資料閘道設定和資料來源。 </li><li>在遷移後，建立在即時資料集之上的報告將無法使用，且必須重新建立。 </li><li>在轉換期間，使用者將無法使用 Power BI 服務。 無法取得服務，不應超過24小時。</li><li>遷移後，使用者將需要使用 Power BI 服務重新設定資料來源及其內部部署資料閘道。  在執行這項作業之前，使用者將無法使用這些資料來源，對這些資料來源執行排程的重新整理和/或直接查詢。 </li><li>無法遷移容量與特優工作區。 客戶必須先刪除所有容量，再進行遷移，然後在遷移之後重新建立。 視需要將工作區移回容量。</li></ul>  |
||||

\*\* (i) 使用 Microsoft Power BI 的客戶必須採取遷移程式所定義的遷移程式，採取行動。  (ii) 客戶採取行動的失敗即表示 Microsoft 將無法完成遷移。  (iii) 當 Microsoft 因客戶的 inaction 而無法完成遷移時，客戶的訂閱會在2021年10月29日到期。

## <a name="office-apps"></a>Office 應用程式

**適用于：** 所有使用 Office 桌面應用程式的客戶 (Word、Excel、PowerPoint、Outlook ... ) 

轉換至地區 "德國" 的 office 365 租使用者要求所有使用者關閉、登出 Office 365，然後重新登出所有 Office 桌面應用程式 (Word、Excel、PowerPoint、Outlook 等等 ) 和 OneDrive 在租使用者遷移到達階段9之後。 登出和簽出，可讓 Office 服務從全域 Azure AD 服務取得新的驗證權杖。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 用戶端，office Online 在 Office 用戶端轉換時，Azure AD 已完成租使用者範圍以指向 Office 365 服務。 | 這種設定變更可讓 Office 用戶端更新並指向 Office 365 服務端點。 | <ul><li>通知使用者關閉 _所有_ Office 應用程式，然後重新登入 (或強制用戶端重新開機，或強制使用者登入) ，以讓 Office 用戶端選擇變更。 </li><li>通知使用者和問訊台人員使用者 *可能會* 看到 office 橫幅，提示他們在轉換的72小時內重新啟用 office 應用程式。 </li><li>必須關閉個人電腦上的所有 Office 應用程式，且使用者必須登出後再登入。 在黃色啟用欄中，登入以重新啟用 Office 365 服務。</li><li>共用電腦需要與個人電腦類似的動作，而且不需要特殊的程式。 </li><li>在行動裝置上，使用者必須登出應用程式，並將其關閉，然後再次登入。 </li></ul>|
||||

## <a name="office-services"></a>Office 服務

MCD 中最近 (使用的 MRU) 服務是從轉換為 Office 365 全域服務，而不是遷移。 從 Office.com 入口網站遷移後，只會顯示從 Office 365 泛型服務端的 MRU 連結。 MCD 中的 MRU 連結在 Office 365 全域服務中不會顯示為 MRU 連結。 在 Office 365 全域服務中，只有在租使用者遷移到達階段9之後，才能存取 MRU 連結。

## <a name="next-step"></a>後續步驟

[執行其他預備工作](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>其他資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
