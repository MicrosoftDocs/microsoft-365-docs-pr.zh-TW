---
title: '從 Microsoft Cloud Deutschland 移 (和一般移) '
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
description: 摘要：瞭解從 Microsoft Cloud 德國 (Microsoft Cloud Deutschland) 移往新德國資料中心地區的 Office 365 服務的移移階段動作和影響。
ms.openlocfilehash: f0c81813522be1f9d759980df98995f1adb261c5
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921619"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>從 Microsoft Cloud Deutschland 移 (和一般移) 

租使用者從 Microsoft Cloud Deutschland 移向德國地區的 Microsoft Office 365 服務會以一組階段及其針對每個工作量的設定動作執行。 此圖顯示移移至新德國資料中心的九個階段。

![移移至新德國資料中心的九個階段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

階段及其動作可確保重要資料和體驗能夠移移至 Office 365 服務。 將租使用者加入移移佇列之後，每個工作量都會以一組在後端服務上執行的步驟完成。 某些工作負載可能需要系統管理員 (或使用者) 採取動作，或是移移可能會影響執行和在移移如何組織方式中討論之階段 [的使用？](ms-cloud-germany-transition.md#how-is-the-migration-organized)

下列各節包含工作負載在移移各個階段進行時的動作和效果。 請查閱資料表，判斷貴組織適用哪些動作或效果。 請決定您已準備好按照需要，在各自階段執行步驟。 若無法完成必要的步驟，可能會導致服務中斷，而且可能會延遲移移至 Office 365 服務的完成。

## <a name="exchange-online"></a>Exchange Online

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 新的德國地區會新增加至現有的組織設定，而信箱會移至 Office 365 服務。 | Exchange Online 組式會將新的當地德文地區加入轉換組織。 此 Office 365 服務區域設為預設值，可讓內部負載平衡服務將信箱重新發佈至 Office 365 服務中適當的預設區域。 在此轉換中，位於德國 (Office 365 服務) 位於同一個組織，且可以使用任一 URL 端點。 | Exchange Online | - 將使用者和服務從德國 URL 轉換至 Office 365 服務 URL `https://outlook.office365.com` () 。 <br><br> - 使用者在移移期間會繼續透過舊版德國 URL 存取服務。 不需要立即採取行動。 <br><br> - 使用者應該開始使用 Office Online office.com入口網站，包括 (、郵件、人員) 。 尚未移移至 Office 365 服務的流覽功能必須等到移移之後才能運作。 <br><br> - Outlook Web App 不會在移移期間提供公用資料夾體驗。 |
|||||

其他考慮事項：

- `myaccount.msft.com` 只會在 Office 365 的切換之後才能使用。 在此之前，連結會產生「發生錯誤」錯誤訊息。

- 存取其他環境中共用信箱的 Outlook Web App 使用者 (例如，德國環境的使用者存取全域環境的共用信箱) 將會提示使用者第二次進行驗證。 使用者必須先在中進行驗證並存取其信箱 `outlook.office.de` ，然後開啟位於中的共用信箱 `outlook.office365.com` 。 當他們存取其他服務所託管的共用資源時，必須再驗證一次。

- 對於現有的 Microsoft Cloud Deutschland 客戶或轉換中的客戶，當使用檔案 >**資訊 >** 新增帳戶將共用信箱新增到 Outlook 時，檢視日曆許可權可能會失敗 (Outlook 用戶端嘗試使用 Rest API .) 想要新增帳戶以檢視日曆許可權的客戶，可以新增登錄機密鑰，如在 Outlook 中共用日曆的使用者體驗變更中所述，以確保此動作會成功。 `https://outlook.office.de/api/v2.0/Me/Calendars` [](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 您可以使用群組原則，在全組織部署此註冊表金鑰。

- 在移轉階段，使用 PowerShell Cmdlets **New-migrationEndpoint、Set-MigrationEndpoint** 及 **Test-MigrationsServerAvailability** 可能會導致錯誤 (Proxy) 。  當仲裁信箱已移移至全球，但系統管理員信箱尚未或相反的情況時，即會發生此情況。 若要解決此問題，在建立租使用者 PowerShell 會話時，請使用仲裁信箱做為 **ConnectionUri** 中的路由提示。 例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- 如果您使用的是 Exchange Online 混合式：

    - 您必須重新執行混合式組配置精靈 (HCW) ，以在轉換前針對 Microsoft Cloud Deutschland 更新內部部署組配置，並針對 Office 365 服務進行清理，重新執行 HCW。 如果您使用自訂網域，可能需要其他 DNS 更新。

若要進一步瞭解組織在移移和 Exchange Online 資源移移之後的差異，請查閱新的德國資料中心地區移移至 [Office 365](ms-cloud-germany-transition-experience.md)服務期間客戶經驗中的資訊。

## <a name="exchange-online-protection"></a>Exchange Online Protection

後端 Exchange Online Protection (EOP) 功能會複製到新的德國地區。 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 移移 Exchange Online 路由和歷史郵件詳細資料。 | Exchange Online 可啟用從外部主機到 Office 365 的路由。 外部 MX 記錄會轉換至 EOP 服務的路由。 租使用者組配置和歷史詳細資料會移移。 | Exchange Online 客戶 | - Microsoft 管理的 DNS 專案會從 Office 365 Germany EOP 更新為 Office 365 服務。 <br><br> - 客戶應該等候 EOP 雙重寫入後 30 天，再進行 EOP 移移。 否則，資料可能會遺失。 |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 會轉換。 | SharePoint 和 OneDrive 在此階段從 Microsoft Cloud Deutschland 移移至 Office 365 服務。 現有的 Microsoft Cloud Deutschland URL 會保留 (例如 `contoso.sharepoint.de`) 。 由 Microsoft Cloud Deutschland 或 Office 365 服務所發行的權杖在轉換期間有效。 | SharePoint 客戶 | - 內容在移移期間將只會讀取兩個簡短的期間。 在此期間，預期 SharePoint 中會顯示「無法編輯內容」橫幅。 <br><br> - 系統不會保留搜尋索引，且最多可能需要 10 天的時間重新建立。 <br><br> - SharePoint/OneDrive 內容在移移期間將會有兩個簡短的唯讀期間。 在此時，使用者會短暫看到「無法編輯內容」橫幅。 <br><br> - 重建索引時，搜尋索引可能無法使用。 在一段期間，搜尋查詢可能不會回完整結果。 <br><br> - 保留現有的網站。 |
|||||

其他考慮事項：

- 當 SharePoint Online 移轉到德國區域完成後，會重新建立資料索引。 重新索引完成時，取決於搜尋索引的功能可能會受到影響。

- 如果貴組織仍在使用 SharePoint 2010 工作流程，在 2021 年 12 月 31 日之後，這些工作流程將不再運作。 SharePoint 2013 工作流程將維持支援，但從 2020 年 11 月 1 日開始新租使用者預設為關閉。 移轉至 SharePoint Online 服務完成後，建議您移至 Power Automate 或其他支援的解決方案。

- OneDrive 移移至德文地區之後，資料索引重建完畢。 重新索引進行中時，取決於搜尋索引的功能可能會受到影響。

- 尚未移移 SharePoint Online 實例的 Microsoft Cloud Deutschland 客戶需要留在 SharePoint Online PowerShell 模組/Microsoft.SharePointOnline.CSOM 版本 16.0.20616.12000 或以下版本。 否則，透過 PowerShell 或用戶端物件模型連線至 SharePoint Online 失敗。

- 移移 SharePoint Online 實例的 Microsoft Cloud Deutschland 客戶必須將 SharePoint Online PowerShell 模組/Microsoft.SharePointOnline.CSOM 更新至版本 16.0.20717.12000 或更新版本。 否則，透過 PowerShell 或用戶端物件模型連線至 SharePoint Online 失敗。


## <a name="skype-for-business-online"></a>商務用 Skype Online

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 將商務用 Skype 移移至 Teams。 | 現有的商務用 Skype 客戶會移轉至歐洲地區的 Office 365 服務，然後轉換至位於德國 Office 365 服務地區的 Microsoft Teams。 | 商務用 Skype 客戶 | - 使用者無法于移移日期當天註冊商務用 Skype。 移移前 10 天，我們會張貼文章到系統管理中心，讓您知道移移將在何時進行，以及何時開始移移。 <br><br> - 已移移群組原則。 <br><br> - 使用者將會移移至 Teams，且移移之後將無法再使用商務用 Skype。 <br><br> - 使用者必須安裝 Teams 桌面用戶端。 安裝將在透過商務用 Skype 基礎結構上之政策進行 10 天內進行，但如果失敗，使用者仍必須下載用戶端或與支援的瀏覽器連接。 <br><br> - 連絡人和會議將會移移至 Teams。 <br><br> - 在轉換到 Office 365 服務的期間服務轉換期間 ，或等到客戶 DNS 專案完成之後，使用者才能使用商務用 Skype 來註冊。 <br><br> - 連絡人和現有的會議會繼續作為商務用 Skype 會議功能。 |
|||||

## <a name="office-services"></a>Office 服務

Office 中最近使用的 MRU (服務) 從德國服務完全轉換到 Office 365 服務，而不是移移。 從 Office 365 服務端移之後，系統只會顯示來自 Office 365 服務Office.com連結。 來自德國服務的 MRU 連結在 Office 365 服務中不會以 MRU 連結顯示。 在 Office 365 中，MRU 連結只能在租使用者移移完成後才能使用。

## <a name="subscription"></a>訂閱

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 未經同意，無法轉移客戶。 | Microsoft 以兩種方式之一取得遷移權利，讓 Microsoft 能夠解決資料和服務轉換至 Office 365 服務實例的問題。 <br> 系統管理員加入宣告 Microsoft 導向移移。 <br> 客戶于 2020 年 5 月 1 日之後續約其 Microsoft Cloud Deutschland 租使用者的任何訂閱。 我們每個月會通知這些客戶移轉，等候 30 天，讓客戶有機會取消，然後直接加入宣告，再使用 ICM 進行追蹤。 | 所有 Office 客戶 | - 租使用者已標示為已同意移移，且系統管理中心會顯示確認。 <br><br> - 確認會張貼至 Cloud 德國訊息中心租使用者。 服務群組原則會從 Microsoft Cloud Deutschland 端點繼續。 <br><br> - 監控訊息中心，以更新移移階段狀態。 |
| 訂閱會移轉，並重新指派授權。 | 租使用者轉換至 Office 365 服務之後，會針對移轉的 Microsoft Cloud Deutschland 訂閱購買對應的 Office 365 服務訂閱。 已指派 Microsoft Cloud Deutschland 授權的使用者將會獲得 Office 365 服務授權。 舊版 Microsoft Cloud Deutschland 訂閱完成後，會從 Office 365 服務租使用者移除。 | 所有 Office 客戶 | - 將會封鎖現有訂閱的變更 (例如，在此階段期間不會) 購買新訂閱或變更) 數量。 <br><br> - 將會封鎖授權指派變更。 <br><br> - Microsoft Cloud Deutschland 訂閱將會移移至對應的 Office 365 服務訂閱。 該訂閱的 Office 365 服務優惠是由 Microsoft (_也稱為優惠地圖服務) 。_ <br><br> - Office 365 (提供) 方案的功能數量可能會比原始的 Microsoft Cloud Deutschland 優惠更大。 Office 365 服務中的使用者授權將會相當於指派給類似的 Microsoft Cloud Deutschland 功能， (方案) 。 所有使用者的使用者授權都會自動指派給新功能。 系統管理員需要採取明確動作，才能停用這些授權 。 <br><br> - 訂閱移移完成後，Office 365 系統管理入口網站中將會同時顯示 Office 365 服務與德國訂閱，且德國訂閱狀態為已 _取消提供_。 <br><br> - 使用者將會重新指派與新的 Office 365 服務訂閱綁定授權。 任何相依于德國訂閱或 SKU GUID 的客戶程式將會中斷，且必須隨著 Office 365 服務方案一起修訂。 <br><br> - Office 365 服務的新訂閱將會以新的期限購買 (每月/每季/每年) ，而客戶將針對 Microsoft Cloud Deutschland 訂閱未使用的餘額按比例獲得退款。 <br><br> - 合作夥伴 Microsoft Cloud Deutschland 租使用者不會移移。 在相同合作夥伴的新 Office 365 服務租使用者下，CSP 客戶將會移移至 Office 365 服務。 客戶移移之後，合作夥伴只能從 Office 365 服務租使用者管理此客戶。 <br><br> - 除非租使用者 (停用 Microsoft Planner 和 Microsoft Flow) ，否則其他功能可供使用。若要瞭解如何停用指派給使用者授權的服務方案，請參閱在指派使用者授權時停用 [Microsoft 365 服務的存取權](disable-access-to-services-while-assigning-user-licenses.md)。  |
|||||

## <a name="next-step"></a>下一步

[執行其他預先作業](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>其他相關資訊

開始：

- [從 Microsoft Cloud Deutschland 移向新的德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [移移期間的客戶經驗](ms-cloud-germany-transition-experience.md)

在轉場中移動：

- [其他預先作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[裝置](ms-cloud-germany-transition-add-devices.md)、[體驗](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他資訊](ms-cloud-germany-transition-add-adfs.md)。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
