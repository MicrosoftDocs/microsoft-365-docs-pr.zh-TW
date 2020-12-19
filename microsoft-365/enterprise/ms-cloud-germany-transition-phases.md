---
title: '從 Microsoft Cloud Deutschland 遷移的遷移階段動作和影響 (一般) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
ms.openlocfilehash: 4a54fed8a109c3d03b735a5db3cb48060f5c438f
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719389"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>從 Microsoft Cloud Deutschland 遷移的遷移階段動作和影響 (一般) 

從 Microsoft Cloud Deutschland 將租使用者遷移至 Microsoft Office 365 服務的德國地區時，會做為每個工作負載的一組已設定的動作執行。 這些動作可確保重要資料和經驗已遷移至 Office 365 服務。 租使用者新增至遷移佇列後，每個工作負載都會以後端服務執行的一組步驟完成。 某些工作負載可能需要管理員 (或使用者) ，否則遷移可能會影響[如何組織遷移時](ms-cloud-germany-transition.md#how-is-the-migration-organized)所執行和討論之階段的使用狀況？

下列各節包含當工作負載透過遷移的各個階段所進行的動作和影響。 請複習表格，並決定哪些動作或效果適用于您的組織。 確定您已準備好在必要時，依照各自階段執行步驟。 無法完成必要的步驟，可能會造成服務中斷，而且可能會推遲完成遷移至 Office 365 服務。

## <a name="exchange-online"></a>Exchange Online

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 新的德國地區新增至現有的組織設定，而信箱移至 Office 365 服務。 | Exchange Online 設定會將新的隨用本機德文區域新增至轉換的組織。 此 Office 365 服務區域已設定為預設值，可讓內部負載平衡服務將信箱重新分配至 Office 365 服務中的適當預設區域。 在此轉換中，任何一側 (德國或 Office 365 服務) 的使用者都位於相同的組織中，而且可以使用 URL 端點。 | Exchange Online | -將使用者和服務從 URLs 德國轉接至 Office 365 服務 URLs (`https://outlook.office365.com`) 。 <br><br> -在遷移期間，使用者將繼續透過傳統的德國 URLs 存取服務。 無需立即採取任何動作。 <br><br> -使用者應開始使用 Office Online 功能的 office.com 入口網站 (行事曆、郵件、人員) 。 流覽至尚未遷移至 Office 365 服務的服務，在遷移之前將無法運作。 <br><br> -Outlook Web App 在遷移期間不會提供公用資料夾體驗。 |
|||||

其他考慮：

- `myaccount.msft.com` 只會在轉換 Office 365 之後運作。 連結會產生「發生錯誤」錯誤訊息，直到這段時間為止。

- 在其他環境中存取共用信箱的 Outlook Web App 使用者 (例如，德國環境中的使用者存取全域環境中的共用信箱) 會提示您第二次驗證。 使用者必須先驗證並存取其信箱 `outlook.office.de` ，然後開啟中的共用信箱 `outlook.office365.com` 。 當存取另一個服務中所主控的共用資源時，他們將需要第二次進行驗證。

- 針對現有的 Microsoft Cloud Deutschland 客戶或過渡中的客戶。使用檔案 > 資訊將共用信箱新增至 Outlook 時 **> 新增帳戶**，查看行事曆許可權可能會失敗 (Outlook 用戶端嘗試使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars` 。 ) 客戶若要新增帳戶以查看行事曆許可權，您可以新增登錄機碼，如在 [outlook 中共用行事曆的使用者經驗變更](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 中所述，此動作會成功。 使用群組原則，可在整個組織中部署此登錄機碼。

- 在遷移階段，使用 PowerShell Cmdlet **New-new-migrationendpoint**、 **Set-MigrationEndpoint** 和 **MigrationsServerAvailability** 可能會導致 proxy) 上的錯誤 (錯誤。 當仲裁信箱已遷移至世界，但不是由系統管理員信箱遷移時，就會發生這種情況。 若要解決此問題，在建立租使用者 PowerShell 會話時，請使用仲裁信箱做為 **ConnectionUri** 中的路由提示。 例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- 如果您使用的是 Exchange Online 混合式：

    - 您必須先重新執行混合式設定向導 (HCW) 以在轉換之前更新 Microsoft Cloud Deutschland 的內部部署設定，然後在 Office 365 服務時重新執行 HCW。 如果您使用自訂網域，可能需要其他的 DNS 更新。

若要深入瞭解遷移中組織和遷移 Exchange Online 資源之後的差異，請在 [新的德國資料中心區域遷移至 Office 365 服務期間，查看客戶經驗](ms-cloud-germany-transition-experience.md)中的資訊。

## <a name="exchange-online-protection"></a>Exchange Online Protection

後端 Exchange Online Protection (EOP) 功能會複製到新的德國地區。 

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 遷移 Exchange Online 路由及歷史郵件詳細資料。 | Exchange Online 可讓您從外部主機路由傳送至 Office 365。 外部 MX 記錄會轉換成路由傳送至 EOP 服務。 會遷移租使用者設定及歷史記錄詳細資料。 | Exchange Online 客戶 | -Microsoft-managed DNS 專案會從 Office 365 德國 EOP 更新為 Office 365 服務。 <br><br> -客戶應等候30天之後，EOP 雙重寫入以進行 EOP 遷移。 否則，可能會遺失資料。 |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 會轉換 SharePoint 和 OneDrive。 | 在此階段中，SharePoint 和 OneDrive 會從 Microsoft Cloud Deutschland 遷移至 Office 365 服務。 現有的 Microsoft Cloud Deutschland URLs 會保留 (例如， `contoso.sharepoint.de`) 。 Microsoft Cloud Deutschland 或 Office 365 服務所發出的權杖在轉換期間是有效的。 | SharePoint 客戶 | -在遷移期間，只會有兩個簡短句點的內容是唯讀的。 在此期間，您會發現 SharePoint 中的「無法編輯內容」橫幅。 <br><br> -搜尋索引不會被保留，而且可能需要最多10天才能重建。 <br><br> -SharePoint/OneDrive 內容將會在遷移期間的兩個簡短期間是唯讀的。 在此期間，使用者會看到「您無法編輯內容」橫幅。 <br><br> -重建索引時，搜尋索引可能無法使用。 在此期間內，搜尋查詢可能不會傳回完整的結果。 <br><br> -保留現有的網站。 |
|||||

其他考慮：

- 當 SharePoint Online 移轉到德國區域完成後，會重新建立資料索引。 與搜尋索引相依的功能可能會受到影響時重建索引完成。

- 如果您的組織仍然使用 SharePoint 2010 工作流程，他們將無法再在 2021 12 月31日之後運作。 SharePoint 2013 工作流程仍然受到支援，不過預設為從 2020 1 月1日開始的新承租人關閉。 在完成 SharePoint 線上服務的遷移之後，建議您移至 [電源自動化] 或其他支援的解決方案。

- OneDrive 遷移至德文地區後，就會重建資料索引。 在建立索引的過程中，取決於搜尋索引的功能可能會受到影響。


## <a name="skype-for-business-online"></a>商務用 Skype Online

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 將商務用 Skype 遷移至小組。 | 現有商務用 Skype 客戶會遷移至歐洲的 Office 365 服務，然後轉換為 Office 365 服務的德國地區中的 Microsoft 團隊。 | 商務用 Skype 客戶 | -使用者無法在遷移日期登入商務用 Skype。 遷移前的10天，我們會發佈到系統管理中心，讓您瞭解何時進行遷移，以及當我們開始遷移時，會發生什麼情況。 <br><br> -已遷移原則設定。 <br><br> -將使用者遷移至小組，並在遷移後不再具有商務用 Skype。 <br><br> -使用者必須已安裝團隊桌面用戶端。 安裝將透過商務用 Skype 基礎結構上的原則進行，但如果失敗，使用者仍需下載用戶端或使用支援的瀏覽器進行連線。 <br><br> -連絡人和會議會遷移到小組。 <br><br> -使用者無法在時間服務轉換為 Office 365 服務時登入商務用 Skype，而不能在客戶 DNS 專案完成之前登入。 <br><br> -連絡人和現有的會議將繼續充當商務用 Skype 會議。 |
|||||

## <a name="office-services"></a>Office 服務

Office 中最近使用 (MRU) 服務，是從德國服務切換至 Office 365 服務，而不是遷移。 從 Office.com 入口網站遷移後，只會顯示從 Office 365 服務端的 MRU 連結。 來自德國服務的 MRU 連結在 Office 365 服務中不會顯示為 MRU 連結。 在 Office 365 中，只有在完成承租人遷移後，才能存取 MRU 連結。

## <a name="subscription"></a>訂閱

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 不同意，我們無法遷移客戶。 | Microsoft 會以兩種方式之一提升遷移許可權，讓 Microsoft 能夠將資料和服務的轉換轉變為 Office 365 服務實例。 <br> 系統管理員會將您加入至 Microsoft 導向的遷移。 <br> 客戶在2020年5月1日之後，更新其 Microsoft Cloud Deutschland 承租人中的任何訂閱。 我們會將每月的遷移權利通知給這些客戶，等候30天讓客戶有機會取消，然後直接加入宣告，在 ICM 中追蹤。 | 所有 Office 客戶 | -租使用者已標示為「同意遷移」，系統管理中心會顯示確認。 <br><br> -確認已發佈至雲端德國訊息中心租使用者。 服務設定會從 Microsoft Cloud Deutschland 端點繼續。 <br><br> -監視訊息中心以瞭解遷移階段狀態的更新。 |
| 會轉移訂閱，並重新指派授權。 | 當租使用者轉換為 Office 365 服務後，會為轉接的 Microsoft 雲端 Deutschland 訂閱購買對應的 Office 365 服務訂閱。 已指派 Microsoft Cloud Deutschland 授權的使用者將會被指派 Office 365 服務授權。 舊版 Microsoft Cloud Deutschland 訂閱會從 Office 365 服務租使用者完成時移除。 | 所有 Office 客戶 | -將會封鎖對現有訂閱所做的變更 (例如，在此階段中，不會有新的訂閱購買或座位元數目變更) 。 <br><br> -將會封鎖授權指派變更。 <br><br> -Microsoft Cloud Deutschland 訂閱將會遷移到對應的 Office 365 服務訂閱。 由 Microsoft (（也稱為「 _提供對應_) 」）定義該訂閱的 Office 365 服務提供。 <br><br> -Office 365 服務所提供 (服務方案) 的功能數目可以大於原始 Microsoft 雲端 Deutschland 提供的功能。 Office 365 服務中的使用者授權會指派給類似的 Microsoft Cloud Deutschland (服務方案) 中的功能。 所有使用者的使用者授權都會自動指派給新功能。 必要時，系統管理員必須採取明確的動作以停用這些授權。 <br><br> -訂閱遷移完成後，office 365 服務和德國訂閱都會顯示在 Office 365 系統管理入口網站中，並以德國訂閱狀態為 _deprovisioned_。 <br><br> -使用者將會重新指派與新 Office 365 服務訂閱相關聯的授權。 任何對德國訂閱或 SKU Guid 具有相依相依性的客戶流程，都將會中斷，且必須與 Office 365 服務選項一起修正。 <br><br> -Office 365 服務中的新訂閱每月都會以新字詞購買 (每月/每季/每年) ，且客戶將會收到未使用的 Microsoft Cloud Deutschland 訂閱餘額的按比例退款。 <br><br> -不會遷移協力廠商的 Microsoft 雲端 Deutschland 承租人。 CSP 客戶將會遷移到相同協力廠商的新 Office 365 服務租使用者下的 Office 365 服務。 客戶遷移後，協力廠商只可以從 Office 365 服務租使用者管理此客戶。 <br><br> -您可以使用其他功能 (例如，Microsoft Planner 和 Microsoft Flow) ，除非租使用者系統管理員停用。如需如何停用指派給使用者授權之服務方案的詳細資訊，請參閱 [在指派使用者授權時，停用 Microsoft 365 服務的存取權](disable-access-to-services-while-assigning-user-licenses.md)。  |
|||||

## <a name="next-step"></a>後續步驟

[執行其他預備工作](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>其他相關資訊

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
