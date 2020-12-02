---
title: 從 Microsoft Cloud Deutschland 進行遷移的其他經驗資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
ms.openlocfilehash: b282a12966e7a6dc8a1a331409834322c5087a10
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551872"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移的其他經驗資訊 

下列各節提供客戶經驗的其他資訊。

## <a name="services"></a>服務

### <a name="azure-ad"></a>Azure AD

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| Microsoft Cloud Deutschland 中的 Azure AD 租使用者已複製到 Office 365 服務。 | Azure AD 會將租使用者複製到 Office 365 服務。 會保留承租人和使用者識別碼。 Azure AD 服務呼叫會從 Microsoft Cloud Deutschland 重新導向至 Office 365 服務，且對服務而言是透明的。 | 所有 Office 客戶 | -一般資料保護法規 (GDPR) 資料主體要求 (Dsr) 會從 Azure Admin 入口網站執行，以供未來的要求使用。 在 Microsoft 雲端 Deutschland 中的任何舊版或非客戶診斷資料會在經過30天之後刪除。 <br><br> -使用與 Active Directory Federation Services 的同盟驗證的客戶 (AD FS) 不應該變更在遷移期間用於所有內部部署 Active Directory 驗證的 issuer URIs。 變更簽發者 URIs 會導致網域中的使用者驗證失敗。 簽發者 URIs 可以直接在 AD FS 中變更，或將網域從 _managed_ 轉換成 _同盟，反之亦然_ 。 我們建議客戶不要新增、移除或轉換已遷移之 Azure AD 租使用者中的同盟網域。 在遷移完全完成後，可以變更發行者 URIs。 <br><br> -多重要素驗證 (，當租使用者複製到 Office 365 服務時，使用 Microsoft 驗證者的 MFA) 要求會顯示為使用者 ObjectID (GUID) 。 雖然這種顯示行為，MFA 要求仍會如期執行。  使用 Office 365 服務端點所啟動的 Microsoft 驗證程式帳戶會顯示使用者主要名稱 (UPN) 。  使用 Microsoft Cloud Deutschland 端點新增的帳戶會顯示使用者 ObjectID，但會同時搭配 Microsoft Cloud Deutschland 和 Office 365 服務端點使用。  |
| 建立指向全域 STS 服務的 Set-authserver 內部部署。 | 這可確保針對目標為混合式內部部署環境的 Exchange 可用性要求進行遷移至 Microsoft Cloud Deutschland 的使用者要求經過驗證，才能存取內部部署服務。 同樣的，這會確保從內部部署到 Office 365 服務端點的要求驗證。 | 具有混合式 (內部部署) 部署的 Exchange Online 客戶 | Azure AD 遷移完成之後，內部部署 Exchange 的系統管理員 (混合) 拓撲必須為 Office 365 服務新增新的驗證服務端點。 使用來自 Exchange PowerShell 的此命令，取代 `<TenantID>` 您組織的租使用者識別碼 (在 **Azure Active Directory**) 上的 azure 入口網站中找到。 <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> 無法完成此工作可能會導致混合空閒忙碌要求無法為已從 Microsoft Cloud Deutschland 遷移至 Office 365 服務的信箱使用者提供資訊。  |
| 遷移 Azure 資源。 | 使用 Office 365 和 Azure 資源的客戶 (例如，網路、計算和儲存) 會執行將資源遷移至 Office 365 服務實例。 這種遷移是客戶的責任。 訊息中心文章會通知開始。 在 Office 365 服務環境中完成 Azure AD 組織之前，必須完成遷移。 | Azure 客戶 | 如需 Azure 遷移，請參閱 azure 遷移行動手冊（ [Azure 德國遷移指南的概述](https://docs.microsoft.com/azure/germany/germany-migration-main)）。 |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

如果您使用 **的是設定 UserPhoto**：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 新的德國區域會新增至現有的組織設定，並將信箱移至 Office 365 服務。 | Exchange Online 設定會將新的隨用本機德文區域新增至轉換的組織。 此 Office 365 服務區域已設定為預設值，可讓內部負載平衡服務將信箱重新分配至 Office 365 服務中的適當預設區域。 在此轉換中，任何一側 (德國或 Office 365 服務) 的使用者都位於相同的組織中，而且可以使用 URL 端點。 |  Exchange Online | 如果使用者信箱已遷移，但系統管理員信箱尚未遷移，或反過來，系統管理員將無法執行 **UserPhoto**，請使用 PowerShell Cmdlet。 在此情況下，系統管理員必須 `ConnectionUri` 使用下列語法，在連接設定期間傳遞另一個字串： <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> 其中 `<user_email>` 是使用者的電子郵件識別碼的預留位置，其相片需要使用 **UserPhoto** 加以變更。 |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

如果您使用的是混合式內部部署，請執行下列步驟：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
|停止或刪除信箱的任何上架或脫離移動。  | 這可確保移動要求不會失敗，併發生錯誤。 | 具有混合式 (內部部署) 部署的 Exchange Online 客戶 | 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamics

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| Microsoft Dynamics 資源 | 使用 Microsoft Dynamics 的客戶將會進行工程或 FastTrack，以將動態轉換為 Office 365 服務實例。 * | Microsoft Dynamics 365 客戶 | -遷移後，系統管理員會驗證組織。 <br><br> -系統管理員會視需要修改工作流程。 <br><br> -系統管理員會視需要清除 AdminOnly 模式。 <br><br> -系統管理員會適當地從 _沙箱_ 變更組織類型。 <br><br> -通知使用者新的 URL 存取實例 (org) 。 <br><br> -更新任何指向新端點 URL 的輸入連線。 <br><br> -轉換期間，使用者將無法使用 Dynamics 服務。 <br><br> -在遷移每個組織之後，使用者必須驗證組織的健康情況和功能。  |
|||||

\* (i) 使用 Microsoft Dynamics 365 的客戶，必須在此遷移案例中採取動作，如所提供的遷移程式所定義。  (ii) 客戶採取行動的失敗即表示 Microsoft 將無法完成遷移。  (iii) 當 Microsoft 因客戶的 inaction 而無法完成遷移時，客戶的訂閱會在2021年10月29日到期。 


### <a name="power-bi"></a>Power BI

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| Power BI 資源的遷移 | 當手動觸發現有的 PBI 遷移工具，將 Power BI 轉換為 Office 365 服務實例後，Microsoft Power BI 的客戶將會涉嫌從事工程或 FastTrack。\*\* | Microsoft Power BI 客戶 | - _不_ 會轉換下列的 Power BI 專案，必須重新建立這些專案： <br><br> -即時資料集 (例如，流式傳送或推入資料集) 。 <br> -Power BI 內部部署資料閘道設定和資料來源。 <br> -在遷移後，在即時資料集之上建立的報告將無法使用，且必須重新建立。 <br><br> -在轉換期間，使用者將無法使用 Power BI 服務。 無法取得服務，不應超過24小時。 <br><br> -遷移後，使用者將需要使用 Power BI 服務重新設定資料來源及其內部部署資料閘道。  在執行這項作業之前，使用者將無法使用這些資料來源，對這些資料來源執行排程的重新整理和/或直接查詢。 <br><br> -無法遷移容量與特優工作區。 客戶必須先刪除所有容量，再進行遷移，然後在遷移之後重新建立。 視需要將工作區移回容量。  |
|||||

\*\* (i) 使用 Microsoft Power BI 的客戶必須採取遷移程式所定義的遷移程式，採取行動。  (ii) 客戶採取行動的失敗即表示 Microsoft 將無法完成遷移。  (iii) 當 Microsoft 因客戶的 inaction 而無法完成遷移時，客戶的訂閱會在2021年10月29日到期。 


### <a name="office-apps"></a>Office 應用程式

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 用戶端，office Online 在 Office 用戶端轉換時，Azure AD 已完成租使用者範圍以指向 Office 365 服務。<!--v-gmoor: What?--> | 這種設定變更可讓 Office 用戶端更新並指向 Office 365 服務端點。 | 所有 Office 客戶 | -從客戶擁有的 DNS 中移除 MSOID CName （若有的話）。 <br><br> -通知使用者關閉 _所有_ Office 應用程式，然後重新登入 (或強制用戶端重新開機，或強制使用者登入) ，以讓 Office 用戶端選擇變更。 <br><br> -通知使用者和問訊台人員使用者 *可能會* 看到 office 橫幅，提示他們在轉換的72小時內重新啟用 office 應用程式。 <br><br> -必須關閉個人電腦上的所有 Office 應用程式，且使用者必須登出後再登入。 在黃色啟用欄中，登入以重新啟用 Office 365 服務。 <br><br> -共用電腦需要與個人電腦類似的動作，而且不需要特殊的程式。 <br><br> -在行動裝置上，使用者必須登出應用程式，關閉它們，然後再次登入。 |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>在移轉期間


### <a name="exchange-online"></a>Exchange Online

針對 eDiscovery：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 在遷移期間，電子檔探索搜尋會失敗，或傳回0個結果，以供 SharePoint 線上、OneDrive 商務及已遷移的 Exchange Online 位置。 | 在遷移期間，客戶可以繼續在安全性 & 規範中心（包括內容搜尋）中建立案例、保留、搜尋和匯出。  不過，針對已遷移的 SharePoint 線上、OneDrive 商務和 Exchange Online 位置進行搜尋會傳回0個結果或產生錯誤。 如需修正，請參閱 _影響_ 欄。 | 所有使用 eDiscovery 的客戶 |  在遷移期間，如果搜尋傳回0個結果或發生錯誤，請在線上 SharePoint 執行下列動作： <br><br>  遵循 [從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中的指示，直接從 SharePoint Online/OneDrive 取得商務網站下載網站。 此方法將需要 SharePoint 線上系統管理員許可權或網站的唯讀許可權。 <br><br> 若超出限制（ [從 OneDrive 或 SharePoint 下載檔案及資料夾](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)中所述），客戶可以遵循 [與電腦同步 SharePoint 及小組](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)檔案的指導方針，使用 OneDrive 進行商務同步處理用戶端。 <br><br> -Exchange Online <br><br> - [在 Exchange Server 中 In-Place eDiscovery](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 會轉換 SharePoint 和 OneDrive。 | 在此階段中，SharePoint 和 OneDrive 會從 Microsoft Cloud Deutschland 遷移至 Office 365 服務。 現有的 Microsoft Cloud Deutschland URLs 會保留 (`contoso.sharepoint.de`) 中。 Microsoft Cloud Deutschland 或 Office 365 服務所簽發的標記在轉換期間是有效的。 | SharePoint 客戶 | Inflight SharePoint 2013 工作流程會在遷移期間中斷，且必須在遷移之後重新發佈。 |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>商務用 Skype Online

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 將商務用 Skype 遷移至小組。 | 現有商務用 Skype 客戶會遷移至歐洲的 Office 365 服務，然後轉換為 Office 365 服務的德國地區中的 Microsoft 團隊。 | 商務用 Skype 客戶 |  PowerShell 會使用來管理租使用者和使用者的設定和原則。 連線至 PowerShell 會話時，請新增下列專案： <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>移轉後

### <a name="azure-ad"></a>Azure AD

若為混合式：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 更新 Azure AD Connect。 | 在完成剪下 Azure AD 後，組織就完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。 此時，客戶必須確定已完成的 delta 同步處理常式，然後在該程式中，將 `AzureInstance` Deutschland Microsoft Cloud) 中的字串 (值變更為登錄路徑中的 0 `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` 。 | 混合式 Azure AD –連線的組織 | 變更登錄機碼的值 `AzureInstance` 。 若無法這麼做，將在不再提供 Microsoft Cloud Deutschland 端點後，導致物件不會進行同步處理。 |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

對於同盟驗證：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 從 Microsoft Cloud Deutschland AD FS 移除信賴憑證者信任。 | 在完成剪下 Azure AD 後，組織就完全使用 Office 365 服務，而且不再連接至 Microsoft 雲端 Deutschland。 此時，客戶需要移除對 Microsoft Cloud Deutschland 端點的信賴憑證者信任。 只有當 Azure AD 以身分識別提供者的方式 (IdP) 時，才可以在未客戶的任何應用程式指向 Microsoft Cloud Deutschland 端點時執行此動作。 | 同盟驗證組織 | 無。 |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

針對 Azure AD：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 在過去30天內加入 Azure AD 群組的要求若未獲核准原始要求，將需要重新要求遷移。 | 若使用者在遷移前的30天內未獲核准，使用者的客戶將需要使用存取面板提交要求，以重新加入 Azure AD 群組。 | 在遷移前30天內，未核准 Azure AD 群組核准要求的使用者 |  做為使用者： <ol><li>流覽至 [Access 面板](https://account.activedirectory.windowsazure.com/r#/joinGroups)。</li><li>尋找在遷移前30天內，成員核准已擱置的 Azure AD 群組。</li><li>要求重新加入 Azure AD 群組。</li></ol> 在遷移後，若要加入超過30天使用中的群組的要求，則無法進行核准。 |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

若為 DNS：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 更新 Office 365 服務端點的內部部署 DNS 服務。 | 客戶管理的 DNS 專案（指向 Office 365 德國）必須更新，以指向 Office 365 服務端點。 | 所有 Office 客戶 | 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

針對 Office 365 服務端點的協力廠商服務：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 更新合作夥伴及 Office 365 服務端點的協力廠商服務。 | -指向 Office 365 德國的協力廠商服務和合作夥伴必須更新，以指向 Office 365 服務端點。 範例：請重新註冊，以與您的廠商和協力廠商（應用程式的畫廊應用程式版本）搭配使用（如果有的話）。 <br><br> -Point 所有利用圖形 API 的自訂應用 `graph.microsoft.de` 程式 `graph.microsoft.com` 。 其他含有已變更端點的 APIs 也必須更新（如果利用）。 <br><br> -變更所有非協力廠商企業應用程式，以重新導向全球端點。  | 所有 Office 客戶 | 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

如果您使用的是混合式 Exchange 設定：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 針對 Office 365 服務，重新執行混合式設定向導 (HCW) 。 | 現有的 HCW 設定是為了支援 Microsoft Cloud Deutschland。 隨著 Exchange 服務的遷移完成，我們會將內部部署設定從 Microsoft Cloud Deutschland 中分離出來。 | 執行混合式部署的 Exchange Online 客戶 | 必要的動作。 若失敗，可能會導致服務或軟體用戶端失敗。 在 Exchange 信箱遷移開始 (，但有5天或以上的通知) ，請通知用戶端他們應該停止並刪除其信箱的任何上架或脫離移動。  如果不是，他們會在移動要求中看到錯誤。 <br><br> -Exchange 信箱遷移完成後，請通知用戶端他們可以繼續進行上架和脫離移動。 <br> 在從 Microsoft Cloud Deutschland 將 Exchange 遷移至 Office 365 服務時，執行 **MigrationServerAvailabiilty 指令程式**，會執行 PowerShell Cmdlet。 不過，遷移完成後，它會正常運作。 <br><br> 如果在遷移信箱之後，用戶端遇到認證或授權問題，使用者可以執行 `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` ，或是使用 Exchange 控制台 (ECP) ，在遷移端點中重新輸入其內部部署系統管理員認證。  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

針對 eDiscovery：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
|  所有的 SharePoint 線上、商務 OneDrive 和 Exchange Online 位置都與安全性與合規性中心一起遷移， (SCC) 。 | 所有 eDiscovery 活動都應該從世界租使用者執行。 搜尋現在會是100% 成功。  任何失敗或錯誤都應該遵循正常支援通道。 | 使用 eDiscovery 的所有客戶 | 無。 |
| 移除在遷移前步驟中建立的全組織保留原則 | 客戶可以移除在客戶的預先遷移工作中所建立的全組織保留原則。 | 所有在遷移前步驟中套用保留原則的客戶。 | 無。 |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 重新發佈 SharePoint 2013 工作流程。 | 在遷移前的工作中，我們減少了 SharePoint 2013 工作流程的數目。 現在已完成遷移，客戶便可重新發佈工作流程。 | 所有 Office 客戶 | 這是必要的動作。 若失敗，可能會造成使用者混淆和問訊台通話。 |
| 透過 Outlook 共用專案 | 在租使用者切換後，透過 Outlook 共用專案將不再運作。 | SharePoint Online 和商務用 OneDrive | -在線上和商務 OneDrive 中 SharePoint，您可以透過 Outlook 共用專案。 按下 Outlook 按鈕之後，會建立可共用的連結，並將其推入至 Outlook Web App 中的新郵件。 <br><br> -租使用者切換後，這種共用方法將無法運作。 我們承認這是已知的問題。 不過，由於此 Outlook 功能是在被否決的路徑中，因此在完成棄用之前，不會規劃修復此問題。 |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>下一步

[瞭解遷移階段的動作和影響](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>詳細資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [遷移階段的動作和影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [服務](ms-cloud-germany-transition-add-general.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
