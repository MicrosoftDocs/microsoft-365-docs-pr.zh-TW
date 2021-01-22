---
title: '從 Microsoft Cloud Deutschland 移 (階段動作和) '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 摘要：從 Microsoft Cloud 德國 (Microsoft Cloud Deutschland) 移往新的德國資料中心地區的 Office 365 服務時，有額外的客戶經驗資訊。
ms.openlocfilehash: 3f9bc40d7551dfcdb65abcf8b150f98b8242d7d2
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921687"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>從 Microsoft Cloud Deutschland 移 (階段動作和)  

租使用者從 Microsoft Cloud Deutschland 移向德國地區的 Microsoft Office 365 服務會以一組階段及其針對每個工作量的設定動作執行。 此圖顯示移移至新德國資料中心的九個階段。

![移移至新德國資料中心的九個階段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

下列各節提供從 Microsoft Cloud 德國 (Microsoft Cloud Deutschland) 移至新德國資料中心地區的 Office 365 服務時，客戶體驗的其他資訊。

## <a name="services"></a>服務

### <a name="azure-ad-phase-2-of-9"></a>Azure AD (階段 2/9) 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| Microsoft Cloud Deutschland 中的 Azure AD 租使用者已複製到 Office 365 服務。 | Azure AD 會複製租使用者至 Office 365 服務。 租使用者和使用者識別碼會保留。 Azure AD 服務通話會從 Microsoft Cloud Deutschland 重新導向至 Office 365 服務，且服務透明。 | 所有 Office 客戶 | - GDPR (一般資料保護規定) 資料主體要求 (DSR) 會從 Azure 系統管理入口網站執行，以用於未來要求。 任何位於 Microsoft Cloud Deutschland 的舊版或非客戶診斷資料，在 30 天之後或之前刪除。 <br><br> - 在 Active Directory Federation Services (AD FS) 使用聯邦驗證的客戶，不應該對在移改期間用於內部部署 Active Directory 之所有驗證的發行者 URI 進行變更。 變更發行者 URI 會導致網域中的使用者驗證失敗。 您可以在 AD FS 中直接變更發行者 URI，或在網域從受管理轉換為聯盟時變更，反之亦然。 我們建議客戶不要新增、移除或轉換 Azure AD 租使用者中已移轉的聯盟網域。 完全完成移移之後，可以變更發行者 URI。 <br><br> - 多重要素驗證 (MFA) 要求，在租使用者複製到 Office 365 服務時，使用 Microsoft Authenticator 做為使用者 ObjectID (GUID) 。 儘管出現此顯示行為，MFA 要求還是會如預期執行。  使用 Office 365 服務端點啟用的 Microsoft Authenticator 帳戶會顯示 UPN (使用者) 。  使用 Microsoft Cloud Deutschland 端點新增的帳戶會顯示使用者 ObjectID，但可同時與 Microsoft Cloud Deutschland 和 Office 365 服務端點一起使用。  |
| 建立指向全域 STS 服務的 AuthServer 內部部署。 | 這可確保針對以混合式內部部署環境為目標，而針對 Exchange 可用性要求而遷移至 Microsoft Cloud Deutschland 的使用者的要求，會經過驗證，以存取內部部署服務。 同樣地，這可確保驗證從內部部署到 Office 365 服務端點的要求。 | 使用混合式部署 (內部部署或部署) Exchange Online 客戶 | Azure AD 移移完成後，內部部署 Exchange (混合式) 拓撲的系統管理員必須新增 Office 365 服務的新驗證服務端點。 使用 Exchange PowerShell 的這個命令，以 Azure Active Directory (Azure 入口網站找到的貴組織的租使用者 `<TenantID>` 識別碼) 。  <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 無法完成此工作可能會導致混合式空閒/忙碌要求無法針對從 Microsoft Cloud Deutschland 移移至 Office 365 服務的信箱使用者提供資訊。  |
| Azure 資源的移移。 | 使用 Office 365 和 Azure 資源 (例如網路、計算和儲存空間) 的客戶將執行資源移移至 Office 365 服務實例。 此移移會由客戶負責。 訊息中心文章會發出開始訊號。 移入必須先完成，才能在 Office 365 服務環境中完成 Azure AD 組織。 | Azure 客戶 | 有關 Azure 移移，請參閱 Azure 移移劇本 [、Azure 德國移移指南概觀](https://docs.microsoft.com/azure/germany/germany-migration-main)。 |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (階段 5/9) 

如果您使用 **Set-UserPhoto：**

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 新的德國地區會新增到現有的組織設定，而信箱會移至 Office 365 服務。 | Exchange Online 組式會將新的當地德文地區加入轉換組織。 此 Office 365 服務區域設為預設值，可讓內部負載平衡服務將信箱重新發佈至 Office 365 服務中適當的預設區域。 在此轉換中，位於德國 (Office 365 服務) 位於同一個組織，且可以使用任一 URL 端點。 |  Exchange Online | 如果使用者信箱已經移轉，但是系統管理員信箱尚未移轉，或是系統管理員無法執行 **Set-UserPhoto**，即 PowerShell Cmdlet。 在這種情況下，系統管理員必須在設定連接期間，使用下列語法傳遞 `ConnectionUri` 額外的字串： <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> 其 `<user_email>` 相片需使用 **Set-UserPhoto** 變更之使用者之電子郵件識別碼的預留位置。 |
|||||

如果您使用的是混合式內部部署：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
|停止或刪除信箱的任何上機或登出移動。  | 這可確保移動要求不會發生錯誤。 | 使用混合式部署 (內部部署或) Exchange Online 客戶 | 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
|||||

### <a name="dynamics-phase-8-of-9"></a>動態 (階段 8/9) 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics 資源 | 使用 Microsoft Dynamics 的客戶會使用工程或 FastTrack 來將 Dynamics 轉換至 Office 365 服務實例。* | Microsoft Dynamics 365 客戶 | - 移移之後，系統管理員會驗證組織。 <br><br> - 系統管理員會在必要時修改工作流程。 <br><br> - 系統管理員會適當清除 AdminOnly 模式。 <br><br> - 系統管理員會在適當的時候變更沙 _盒中的組織_ 類型 <br><br> - 通知使用者使用新 URL 存取組織 (實例) 。 <br><br> - 更新新端點 URL 的任何輸入連結。 <br><br> - 使用者在轉換期間無法使用 Dynamics 服務。 <br><br> - 每一個組織移移之後，使用者必須驗證組織健康狀態和功能。  |
|||||

\* (i) Microsoft Dynamics 365 的客戶必須按照所提供的移移程式定義，在此移移情境中採取行動。  (ii) 若客戶未採取行動，表示 Microsoft 無法完成移移。  (iii) Microsoft 因客戶不回應而無法完成移移，則客戶的訂閱將在 2021 年 10 月 29 日到期。 


### <a name="power-bi-phase-8-of-9"></a>Power BI (階段 8/9) 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 移移 Power BI 資源 | 手動觸發現有的 PBI 移轉工具將 Power BI 轉換至 Office 365 服務實例之後，擁有 Microsoft Power BI 的客戶將會使用工程或 FastTrack 來參與。\*\* | Microsoft Power BI 客戶 | - 下列 Power BI 專案 _將不會轉換_ ，而且必須重新建立： <br><br> - 即時資料集 (例如串流或推送資料集) 。 <br> - Power BI 內部部署資料閘道組配置和資料來源。 <br> - 在即時資料集上建立的報告在移移之後將無法使用，而且必須重新建立。 <br><br> - 使用者在轉換期間無法使用 Power BI 服務。 服務的使用時間不應該超過 24 小時。 <br><br> - 使用者必須重新登錄資料來源及其內部部署資料閘道，以在移移之後使用 Power BI 服務。  在此之前，使用者將無法使用這些資料來源來執行排定的重新處理及/或針對這些資料來源直接查詢。 <br><br> - 無法移移容量和進位工作區。 客戶需要先刪除所有需求，再進行移移，然後再重新建立。 將工作區移回所需位置。  |
|||||

\*\* (我) Microsoft Power BI 的客戶必須按照所提供的移移程式定義，在此移移情境中採取行動。  (ii) 若客戶未採取行動，表示 Microsoft 無法完成移移。  (iii) Microsoft 因客戶不回應而無法完成移移，則客戶的訂閱將在 2021 年 10 月 29 日到期。 


### <a name="office-apps-phase-9-of-9"></a>Office 應用程式 (階段 9/9) 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 用戶端、Office 用戶端切換期間 Office Online、Azure AD 完成租使用者範圍以指向 Office 365 服務。 | 此組配置變更可讓 Office 用戶端更新並指向 Office 365 服務端點。 | 所有 Office 客戶 | - 通知使用者關閉 _所有_ Office App，然後重新重新使用 (或強制用戶端重新開機，以及讓使用者) 以讓 Office 用戶端能夠接起變更。 <br><br> - 通知使用者和技術支援中心員工，使用者可能會看到 Office 橫幅，提示他們在切換後 72 小時內重新啟用 Office App。 <br><br> - 個人電腦上所有的 Office 應用程式都必須關閉，使用者必須先登出，然後再一次重新登錄。 在黃色啟用欄中，請重新啟用 Office 365 服務。 <br><br> - 共用的機器需要與個人電腦類似的動作，而且不需要特殊的程式。 <br><br> - 在行動裝置上，使用者必須登出應用程式、關閉應用程式，然後再次重新登錄。 |
|||||

## <a name="during-migration"></a>在移轉期間

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (階段 4/9) 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| SharePoint 和 OneDrive 會轉換。 | SharePoint 和 OneDrive 在此階段從 Microsoft Cloud Deutschland 移移至 Office 365 服務。 現有的 Microsoft Cloud Deutschland URL 會 `contoso.sharepoint.de` () 。 由 Microsoft Cloud Deutschland 或 Office 365 服務所發行的權杖在轉換期間有效。 | SharePoint 客戶 | Inflight SharePoint 2013 工作流程將在移改期間中斷，而且必須在移改後重新發佈。 |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (階段 5/9) 

針對 eDiscovery：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 移移期間，針對 SharePoint Online、商務用 OneDrive 和 Exchange Online 位置，eDiscovery 搜尋將會失敗，或將 0 個結果退回。 | 在移移期間，客戶可以在安全性與合規性中心 （包括內容搜尋&建立案例、保留、[搜尋](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)[和匯出](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)。  不過，針對已移移的 SharePoint Online、商務用 OneDrive 和 Exchange Online 位置進行搜尋時，會返回 0 個結果或產生錯誤。 有關補救，請參閱影響 _欄_ 。 | 所有使用 eDiscovery 的客戶 |  萬一搜尋在移移期間會回報 0 個結果或錯誤，請針對 SharePoint Online 採取下列動作： <br><br>  您可以遵循從 OneDrive 或 SharePoint 下載檔案和資料夾中的指示，直接從 SharePoint Online/商務用 [OneDrive 網站下載網站](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)。 這個方法會要求 SharePoint Online 系統管理員許可權或網站的唯讀許可權。 <br><br> 如果超出限制 ，如從 [OneDrive](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)或 SharePoint 下載檔案和資料夾所解說，客戶可以遵循將 SharePoint 和 Teams 檔案與電腦同步處理中的指引，來使用商務用 OneDrive 同步 [處理用戶端](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)。 <br><br> - Exchange Online <br><br> - [Exchange Server 中的就地電子檔探索](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>商務用 Skype Online (階段 7/9) 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 將商務用 Skype 移移至 Teams。 | 現有的商務用 Skype 客戶會移轉至歐洲地區的 Office 365 服務，然後轉換至位於德國 Office 365 服務地區的 Microsoft Teams。 | 商務用 Skype 客戶 |  PowerShell 將用於管理您的租使用者和使用者的設定和策略。 當您連接到 PowerShell 會話時，請新增下列專案： <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>移轉後

### <a name="azure-ad-phase-9-of-9"></a>Azure AD (階段 9/9) 

混合式：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 更新 Azure AD Connect。 | Azure AD 完全結束後，組織即會完全使用 Office 365 服務，且不再連接至 Microsoft Cloud Deutschland。 此時，客戶必須確保完成 Delta 同步處理常式，之後，在註冊表路徑中將 `AzureInstance` 3 (Microsoft Cloud Deutschland) 的字串值變更為 0。 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` | 連接 Azure AD 的混合式組織 | 變更 ， `AzureInstance` 即為的登錄機碼的值。 否則，Microsoft Cloud Deutschland 端點不再可用之後，會導致物件未同步處理。 |
|||||

針對聯合驗證：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 從 Microsoft Cloud Deutschland AD FS 移除仰賴方的信任。 | Azure AD 完全結束後，組織即會完全使用 Office 365 服務，且不再連接至 Microsoft Cloud Deutschland。 此時，客戶需要移除對 Microsoft Cloud Deutschland 端點的仰賴方信任。 當使用 Azure AD 做為身分識別提供者或 IdP (時，唯有沒有客戶應用程式指向 Microsoft Cloud Deutschland 端點時，才能)  (。 | 聯合驗證組織 | 無。 |
|||||

For Azure AD:

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 如果原始要求未通過核准，將需要在移移前 30 天內再次要求加入 Azure AD 群組的要求。 | 如果使用者在移送前 30 天內未核准要求，使用者客戶將需要使用 Access 面板再次提交加入 Azure AD 群組的要求。 | 在移移前 30 天內未核准 Azure AD 群組核准要求的使用者 |  使用者： <ol><li>流覽至 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>尋找一個 Azure AD 群組，該群組的成員資格核准擱置中為移移前的 30 天。</li><li>再次要求加入 Azure AD 群組。</li></ol> 除非在移移後重新要求，否則無法核准在移移前 30 天內加入群組的要求。 |
|||||

For DNS:

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服務端點內部部署 DNS 服務。 | 必須更新指向 Office 365 Germany 的客戶管理 DNS 專案，以指向 Office 365 服務端點。 | 所有 Office 客戶 | 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
|||||

針對 Office 365 服務端點的協力廠商服務：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服務端點的合作夥伴和協力廠商服務。 | - 必須更新指向 Office 365 Germany 的協力廠商服務和合作夥伴，以指向 Office 365 服務端點。 範例：重新註冊，以對齊您的廠商和合作夥伴，以及應用程式圖庫應用程式版本 （如果可用）。 <br><br> - 將運用圖形 API 的所有自訂應用程式指向 `graph.microsoft.de` `graph.microsoft.com` . 如果利用其他端點已變更的 API，也需要更新。 <br><br> - 變更所有非第一方企業應用程式，以重新導向至全球端點。  | 所有 Office 客戶 | 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (階段 4/9) 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 重新發佈 SharePoint 2013 工作流程。 | 在移移前的工作中，我們減少 SharePoint 2013 工作流程的數量。 移移完成後，客戶就可以重新發佈工作流程。 | 所有 Office 客戶 | 這是必要的動作。 若未執行此工作，可能會導致使用者混淆及技術支援人員電話。 |
| 透過 Outlook 共用專案 | 租使用者切換之後，透過 Outlook 共用專案無法再運作。 | SharePoint Online 和商務用 OneDrive | - 在 SharePoint Online 和商務用 OneDrive 中，您可以透過 Outlook 共用專案。 按下 Outlook 按鈕後，系統即會建立可共用連結，並推送到 Outlook Web App 中的新郵件中。 <br><br> - 租使用者切換之後，這種共用方法將無法執行。 我們知道這是一個已知的問題。 不過，由於這項 Outlook 功能已是被取消使用的路徑，因此在推出這項功能之前，並無法修正此問題。 |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (階段 5/9) 

如果您使用的是混合式 Exchange 組式：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 針對 Office 365 服務重新 (HCW) 執行混合式組配置精靈。 | 現有的 HCW 組配置旨在支援 Microsoft Cloud Deutschland。 Exchange 服務移移完成後，我們會從 Microsoft Cloud Deutschland 完成內部部署組配置。 | 進行混合式部署的 Exchange Online 客戶 | - 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 在 Exchange 信箱移 (5 天或 5 天以上通知開始移) ，通知用戶端應停止並刪除其信箱的任何上機或登出移動。  如果沒有，就會在移動要求中看見錯誤。 <br><br> - Exchange 信箱移移完成後，通知用戶端他們可以繼續上機和登出移動。 <br> 執行 **Test-MigrationServerAvailabiilty** 是 PowerShell Cmdlet，在將 Exchange 從 Microsoft Cloud Deutschland 移轉至 Office 365 服務期間可能無法運作。 不過，移移完成後，它可正常運作。 <br><br> 如果用戶端在移轉信箱之後遇到認證或授權問題，使用者可以執行或利用 Exchange 控制台 (ECP) ，在移轉端點重新輸入其內部部署系統管理員 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` 認證。  |

針對 eDiscovery：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
|  所有 SharePoint Online、商務用 OneDrive 和 Exchange Online 位置已隨著安全性與合規性中心移 (SCC) 。 | 所有 eDiscovery 活動都應該從全球租使用者執行。 搜尋現在可以 100% 成功。  任何失敗或錯誤都應該遵循一般支援通道。 | 所有使用 eDiscovery 的客戶 | 無。 |
| 移除在移移前步驟中建立全組織的保留政策 | 客戶可以移除在客戶移移前作業期間所建立全組織的保留政策。 | 所有已將保留原則做為移移前步驟一部分的客戶。 | 無。 |
|||||



## <a name="next-step"></a>下一步

[瞭解移移階段的動作和影響](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>其他相關資訊

開始：

- [從 Microsoft Cloud Deutschland 移向新的德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [移移期間的客戶經驗](ms-cloud-germany-transition-experience.md)

在轉場中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預先作業](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[裝置](ms-cloud-germany-transition-add-devices.md)、[體驗](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他資訊](ms-cloud-germany-transition-add-adfs.md)。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
