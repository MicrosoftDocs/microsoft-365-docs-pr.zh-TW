---
title: '從 Microsoft Cloud Deutschland 遷移的遷移階段動作和影響 (advanced) '
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
description: 摘要：從 Microsoft Cloud (德國移至 Microsoft cloud Deutschland 時的其他客戶體驗資訊) 新德文 datacenter 區域中的 Office 365 服務。
ms.openlocfilehash: 84705eaf78da4d1e8d35f743599f6a4e9e46208f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924419"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>從 Microsoft Cloud Deutschland 遷移的遷移階段動作和影響 (advanced)  

從 Microsoft Cloud Deutschland 將租使用者遷移至 Microsoft Office 365 服務的德國地區時，會做為每一個工作負載的一組階段和各自設定的動作執行。 下圖顯示遷移至新德文資料中心的九個階段。

![遷移至新的德國資料中心的九個階段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

下列各節將提供客戶經驗的其他資訊，從 Microsoft Cloud 德國 (Microsoft Cloud Deutschland) 到新德文 datacenter 區域中的 Office 365 服務。

## <a name="office-365-portal-services"></a>Office 365 入口網站服務

在9的階段2和階段3之9之間，可能無法存取夥伴入口網站。 在這段時間內，合作夥伴可能無法存取合作夥伴入口網站上的承租人資訊。 由於每個遷移都不同，以協助工具的持續時間可能是以小時為單位。

### <a name="prework-for-azure-ad-phase-2"></a>Azure AD (預備) 階段2

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| Microsoft Cloud Deutschland 中的 Azure AD 租使用者已複製到 Office 365 服務。 | Azure AD 會將租使用者複製到 Office 365 服務。 會保留承租人和使用者識別碼。 Azure AD 服務呼叫會從 Microsoft Cloud Deutschland 重新導向至 Office 365 服務，且對服務而言是透明的。 | 所有 Office 客戶 | -一般資料保護法規 (GDPR) 資料主體要求 (Dsr) 會從 Azure Admin 入口網站執行，以供未來的要求使用。 在 Microsoft 雲端 Deutschland 中的任何舊版或非客戶診斷資料會在經過30天之後刪除。 <br><br> -使用與 Active Directory Federation Services 的同盟驗證的客戶 (AD FS) 不應該變更在遷移期間用於所有內部部署 Active Directory 驗證的 issuer URIs。 變更簽發者 URIs 會導致網域中的使用者驗證失敗。 簽發者 URIs 可以直接在 AD FS 中變更，或將網域從 _managed_ 轉換成 _同盟，反之亦然_ 。 我們建議客戶不要新增、移除或轉換已遷移之 Azure AD 租使用者中的同盟網域。 在遷移完全完成後，可以變更發行者 URIs。 <br><br> -多重要素驗證 (，當租使用者複製到 Office 365 服務時，使用 Microsoft 驗證者的 MFA) 要求會顯示為使用者 ObjectID (GUID) 。 雖然這種顯示行為，MFA 要求仍會如期執行。  使用 Office 365 服務端點所啟動的 Microsoft 驗證程式帳戶會顯示使用者主要名稱 (UPN) 。  使用 Microsoft Cloud Deutschland 端點新增的帳戶會顯示使用者 ObjectID，但會同時搭配 Microsoft Cloud Deutschland 和 Office 365 服務端點使用。  |
| 遷移 Azure 資源。 | 使用 Office 365 和 Azure 資源的客戶 (例如，網路、計算和儲存) 會執行將資源遷移至 Office 365 服務實例。 這種遷移是客戶的責任。 訊息中心文章會通知開始。 在 Office 365 服務環境中完成 Azure AD 組織之前，必須完成遷移。 | Azure 客戶 | 如需 Azure 遷移，請參閱 azure 遷移行動手冊（ [Azure 德國遷移指南的概述](/azure/germany/germany-migration-main)）。 |
|||||

### <a name="exchange-online-before-phase-5"></a>第5階段之前的 Exchange Online

**適用于：** 在內部部署中，使用 Exchange 混合式設定與 Exchange 伺服器的所有客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 建立指向全域 STS 服務的 Set-authserver 內部部署。 | 這可確保針對目標為混合式內部部署環境的 Exchange 可用性要求進行遷移至 Microsoft Cloud Deutschland 的使用者要求經過驗證，才能存取內部部署服務。 同樣的，這會確保從內部部署到 Office 365 服務端點的要求驗證。 | Azure AD 遷移完成之後，內部部署 Exchange 的系統管理員 (混合) 拓撲必須為 Office 365 服務新增新的驗證服務端點。 使用來自 Exchange PowerShell 的此命令，取代 `<TenantID>` 您組織的租使用者識別碼 (在 **Azure Active Directory**) 上的 azure 入口網站中找到。<br><br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 無法完成此工作可能會導致混合空閒忙碌要求無法為已從 Microsoft Cloud Deutschland 遷移至 Office 365 服務的信箱使用者提供資訊。  |
|停止或刪除任何上架或脫離信箱移動，也就是不要在 Exchange 內部部署和 Exchange Online 之間移動信箱  | 這可確保信箱移動要求不會失敗，併發生錯誤。 | 若失敗，可能會導致服務或軟體用戶端失敗。 |
||||

<!--
    Question from ckinder
    Not clear if this has to be done before, during or after phase 5
-->

**適用于：** 所有客戶都將使用者相片儲存在 Exchange Online 中，且使用 **UserPhoto**：

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 新的地區 "德國" 會新增至現有的 Exchange Online 組織設定，並將信箱移至 Office 365 服務。 | Exchange Online 設定會將新的隨用本機德文區域新增至轉換的組織。 此 Office 365 服務區域已設定為預設值，可讓內部負載平衡服務將信箱重新分配至 Office 365 服務中的適當預設區域。 在此轉換中，任何一側 (德國或 Office 365 服務) 的使用者都位於相同的組織中，而且可以使用 URL 端點。 | 如果使用者信箱已遷移，但系統管理員信箱尚未遷移，或反過來，系統管理員將無法執行 **UserPhoto**，請使用 PowerShell Cmdlet。 在此情況下，系統管理員必須 `ConnectionUri` 使用下列語法，在連接設定期間傳遞另一個字串： <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> 其中 `<user_email>` 是使用者的電子郵件識別碼的預留位置，其相片需要使用 **UserPhoto** 加以變更。 |
||||

## <a name="during-migration"></a>在移轉期間

### <a name="sharepoint-online-phase-4"></a>SharePoint 線上階段4

**適用于：** 所有使用 eDiscovery 的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 會轉換 SharePoint 和 OneDrive。 | SharePoint 和 OneDrive 會從 Microsoft Cloud Deutschland 遷移至階段4中的 Office 365 泛型服務。 現有的 Microsoft Cloud Deutschland URLs 會保留 (`contoso.sharepoint.de`) 中。 Microsoft Cloud Deutschland 或 Office 365 服務所簽發的標記在轉換期間是有效的。 | Inflight SharePoint 2013 工作流程會在遷移期間中斷，且必須在遷移之後重新發佈。 |
||||

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>eDiscovery 階段4至階段9結束

**適用于：** 所有使用 eDiscovery 的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 從第4階段開始直到階段9完成，電子檔探索搜尋會失敗，或傳回 SharePoint 線上、OneDrive 商務及已遷移之 Exchange Online 位置的0個結果。 | 在遷移期間，客戶可以繼續在 [安全性 & 規範中心](../compliance/manage-legal-investigations.md)（包括 [內容搜尋](../compliance/search-for-content.md)）中建立案例、保留、搜尋和匯出。  不過，針對已遷移的 SharePoint 線上、OneDrive 商務和 Exchange Online 位置進行搜尋會傳回0個結果或產生錯誤。 如需修正，請參閱 _影響_ 欄。 | 在遷移期間，如果搜尋傳回零結果或發生錯誤，請在線上 SharePoint 執行下列動作： <ul><li>遵循 [從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中的指示，直接從 SharePoint Online/OneDrive 取得商務網站下載網站。 此方法將需要 SharePoint 線上系統管理員許可權或網站的唯讀許可權。</li><li>若超出限制（ [從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中所述），客戶可以遵循 [與電腦同步 SharePoint 及小組](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)檔案的指導方針，使用 OneDrive 進行商務同步處理用戶端。</li><li>如需詳細資訊，請參閱  [In-Place eDiscovery In Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="post-migration"></a>移轉後

### <a name="azure-ad-phase-9"></a>Azure AD 階段9

**適用于：** 與 Azure AD connect 同步處理的所有客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 更新 Azure AD Connect。 | 在完成剪下 Azure AD 後，組織就完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。 此時，客戶必須確定已完成的 delta 同步處理常式，然後在該程式中，將 `AzureInstance` Deutschland Microsoft Cloud) 中的字串 (值變更為登錄路徑中的 0 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | 變更登錄機碼的值 `AzureInstance` 。 若無法這麼做，將在不再提供 Microsoft Cloud Deutschland 端點後，導致物件不會進行同步處理。 |
|||||

**適用于：** 使用 ADFS 同盟驗證的所有客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 從 Microsoft Cloud Deutschland AD FS 移除信賴憑證者信任。 | 在完成剪下 Azure AD 後，組織就完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。 此時，客戶需要移除對 Microsoft Cloud Deutschland 端點的信賴憑證者信任。 只有當 Azure AD 以身分識別提供者的方式 (IdP) 時，才可以在未客戶的任何應用程式指向 Microsoft Cloud Deutschland 端點時執行此動作。 | 同盟驗證組織 | 無。 |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
針對 Azure AD：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 在過去30天內加入 Azure AD 群組的要求若未獲核准原始要求，將需要重新要求遷移。 | 若使用者在遷移前的30天內未獲核准，使用者的客戶將需要使用存取面板提交要求，以重新加入 Azure AD 群組。 | 在遷移前30天內，未核准 Azure AD 群組核准要求的使用者 |  做為使用者： <ol><li>流覽至 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>尋找在遷移前30天內，成員核准已擱置的 Azure AD 群組。</li><li>要求重新加入 Azure AD 群組。</li></ol> 在遷移後，若要加入超過30天使用中的群組的要求，則無法進行核准。 |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**適用于：**  所有客戶都管理自己的 DNS 區域

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服務端點的內部部署 DNS 服務。 | 客戶管理的 DNS 專案（指向 Microsoft Cloud Deutschland）必須更新，以指向 Office 365 泛型服務端點。 | 若失敗，可能會導致服務或軟體用戶端失敗。 |
||||

針對 Office 365 服務端點的協力廠商服務：

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 更新合作夥伴及 Office 365 服務端點的協力廠商服務。 | <ul><li>指向 Office 365 德國的協力廠商服務和合作夥伴必須更新，以指向 Office 365 服務端點。 範例：請重新註冊，以與您的廠商和協力廠商（應用程式的畫廊應用程式版本）搭配使用（如果有的話）。 </li><li>將所有利用 Graph API 的自訂應用程式指向 `graph.microsoft.de` `graph.microsoft.com` 。 其他含有已變更端點的 APIs 也必須更新（如果利用）。 </li><li>變更所有非協力廠商企業應用程式，以重新導向全球端點。 </li></ul>| 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
||||

### <a name="sharepoint-online-post-migration"></a>SharePoint 線上後遷移

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 重新發佈 SharePoint 2013 工作流程。 | 在遷移前的工作中，我們減少了 SharePoint 2013 工作流程的數目。 現在已完成遷移，客戶便可重新發佈工作流程。 | 這是必要的動作。 若失敗，可能會造成使用者混淆和問訊台通話。 |
| 透過 Outlook 共用專案 | 在租使用者切換後，可在 SharePoint Online 和商務 OneDrive 中透過 Outlook 共用的專案不再運作。 |<ul><li>在 SharePoint 線上和商務 OneDrive 中，您可以透過 Outlook 共用專案。 按下 Outlook 按鈕之後，會建立可共用的連結，並將其推入至 Outlook Web App 中的新郵件。</li><li>租使用者轉換後，這種共用方法將無法運作。 我們承認這是已知的問題。 不過，由於此 Outlook 功能是在被否決的路徑中，因此在完成棄用之前，不會規劃修復此問題。 </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online 後遷移

如果您使用的是混合式 Exchange 設定：

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 針對 Office 365 服務，重新執行混合式設定向導 (HCW) 。 | 現有的 HCW 設定是為了支援 Microsoft Cloud Deutschland。 隨著 Exchange 服務的遷移完成，我們會將內部部署設定從 Microsoft Cloud Deutschland 中分離出來。 |<ul><li>必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 在 Exchange 信箱遷移開始 (，但有5天或以上的通知) ，請通知用戶端他們應該停止並刪除其信箱的任何上架或脫離移動。  如果不是，他們會在移動要求中看到錯誤。 </li><li>Exchange 信箱遷移完成後，請通知用戶端他們可以繼續上架和脫離移動。 <br> 在從 Microsoft Cloud Deutschland 將 Exchange 遷移至 Office 365 服務時，執行 **MigrationServerAvailabiilty 指令程式**，會執行 PowerShell Cmdlet。 不過，遷移完成後，它會正常運作。 </li><li>如果在遷移信箱之後，用戶端遇到認證或授權問題，使用者可以執行 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ，或是使用 Exchange 控制台 (ECP) ，在遷移端點中重新輸入其內部部署系統管理員認證。 </li></ul>|

### <a name="ediscovery-post-migration"></a>eDiscovery 後遷移

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
|  所有的 SharePoint 線上、商務 OneDrive 和 Exchange Online 位置都與安全性與合規性中心一起遷移， (SCC) 。 | 所有 eDiscovery 活動都應該從世界租使用者執行。 搜尋現在會是100% 成功。  任何失敗或錯誤都應該遵循正常支援通道。 | 使用 eDiscovery 的所有客戶 | 無。 |
| 移除在遷移前步驟中建立的全組織保留原則 | 客戶可以移除在客戶的預先遷移工作中所建立的全組織保留原則。 | 所有在遷移前步驟中套用保留原則的客戶。 | 無。 |
|||||

## <a name="next-step"></a>後續步驟

[瞭解遷移階段的動作和影響](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>其他資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移轉程式資訊](/power-bi/admin/service-admin-migrate-data-germany)
- [開始升級您的 Microsoft Teams](/microsoftteams/upgrade-start-here)