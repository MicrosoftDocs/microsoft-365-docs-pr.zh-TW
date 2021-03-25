---
title: 從 Microsoft Cloud Deutschland 進行遷移的準備工作
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
description: 摘要：從 Microsoft Cloud 德國移動 (Microsoft Cloud Deutschland) 到新德文 datacenter 區域中的 Office 365 服務的準備工作。
ms.openlocfilehash: d05b3fc06c4530a69c49962b0d2b793353033c99
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165606"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移的準備工作

使用下列連結可取得與貴組織相關的預備工作步驟：

- 針對 **所有** 在 Microsoft Cloud Deutschland 中使用 Office 365 的客戶，請執行 [下列步驟](#general-tenant-migration-considerations)。
- 若為 **DNS 變更**，請執行 [此步驟](#dns)。
- 如果您是在內部部署使用 **Active Directory Federation Services** ，請執行 [下列步驟](#active-directory-federation-services-ad-fs)。
- 如果您使用的是 **SharePoint 線上**，請執行 [此步驟](#sharepoint-online)。
- 如果您使用的是 **Exchange Online** 或 **exchange 混合** 式，請執行 [此步驟](#exchange-online)。
- 如果您使用 **的是商務用 Skype Online**，請執行 [此步驟](#skype-for-business-online)
- 如果您正在使用協力廠商行動裝置管理 (MDM) 解決方案，請執行 [此步驟](#mobile-device-management)。
- 如果您使用的是 **協力廠商服務** 或 **企業營運 (LOB)** 與 Office 365 整合的應用程式，請執行 [此步驟](#line-of-business-apps)。
- 如果您也是使用 **Dynamics 365**，請執行 [此步驟](#dynamics365)。
- 如果您也是使用 **POWER BI**，請執行 [此步驟](#power-bi)。
- 如果您也是使用 **Azure 服務** 與 Office 365 訂閱，請執行 [此步驟](#microsoft-azure)。

## <a name="general-tenant-migration-considerations"></a>一般承租人遷移考慮

**適用于：** 在 Microsoft Deutschland 雲端實例中使用 Office 365 的所有客戶

遷移期間會保留 Office 365 租使用者和使用者識別碼。 Azure AD 服務呼叫會從 Microsoft Cloud Deutschland 重新導向至 Office 365 泛型服務，而且對於 Office 365 服務是透明的。

- 一般資料保護法規 (GDPR) 資料主體要求 (Dsr) 會從 Azure Admin 入口網站執行，以供未來的要求使用。 在 Microsoft 雲端 Deutschland 中的任何舊版或非客戶診斷資料會在經過30天之後刪除。
- 多重要素驗證 (MFA) 要求會在將租使用者複製到 Office 365 服務時，以使用者身分顯示 GUID) ，ObjectID (GUID。 雖然這種顯示行為，MFA 要求仍會如期執行。  使用 Office 365 服務端點所啟動的 Microsoft 驗證程式帳戶會顯示使用者主要名稱 (UPN) 。  使用 Microsoft Cloud Deutschland 端點新增的帳戶會顯示使用者 ObjectID，但會同時搭配 Microsoft Cloud Deutschland 和 Office 365 服務端點使用。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 準備在遷移後，通知使用者如何重新開機和登出用戶端。 | Office 用戶端授權會從 Microsoft Cloud Deutschland 轉換為遷移中的 Office 365 服務。 用戶端登出及簽入 Office 用戶端後，用戶端會挑選新的有效授權。 | 使用者的 Office 產品需要重新整理 Office 365 服務的授權。 如果未重新整理授權，Office 產品可能會遇到授權驗證錯誤。 |
| 確定 Office 365 服務的網路連線能力 [URLs 及 IP 位址](https://aka.ms/o365urls)。 | 由客戶所主控的所有用戶端和服務，用來存取 Office 365 服務，必須能夠存取 Office 365 泛型服務端點。 <br>若您或您的共同作業夥伴有適當的防火牆規則，可防止存取 Office 365 服務中所列的 URLs 和 IP 位址 [URLs 和 ip 位址](https://aka.ms/o365urls) 必須變更防火牆規則，以允許存取 Office 365 全域服務端點| 如果不是在階段4之前完成，則可能會發生服務或用戶端軟體失敗  |
| 取消所有的試用訂閱。 | 不會遷移試用訂閱，而且會封鎖付費訂閱的轉接。 | 若使用者在取消後存取，試用版服務會到期且無法運作。 |
| 分析 Microsoft Cloud Deutschland 與 Office 365 泛型服務之間授權功能的差異。 | Office 365 服務包含目前 Microsoft Cloud Deutschland 中無法使用的其他功能和服務。 在訂閱轉移期間，使用者將可以使用新功能。 | <ul><li> 分析 Microsoft Cloud Deutschland 和 Office 365 泛型服務的授權所提供的不同功能。 開始使用 [Office 365 平臺服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 </li><li> 判斷是否應該開始停用 Office 365 服務的任何新功能，以限制使用者或使用者變更管理的影響，並視需要變更使用者授權指派。 </li><li>準備使用者及服務台人員，以取得 Office 365 服務提供的新服務和功能。 |
| 建立整個組織 [保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention) ，以防止在遷移期間因無意中刪除內容。  |<ul><li>為了確保使用者不會在遷移期間由使用者意外刪除內容，客戶可以選擇啟用整個組織的保留原則。 </li><li>雖然不需要保留，但在遷移期間可隨時使用保留原則，但具有保留原則是備份的安全性機制。 同時，所有客戶可能不會使用保留原則，尤其是有關保留原則的使用者。</li></ul>| 如 [深入瞭解保留原則和保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)所述套用保留原則。 如果這不是在第4階段中執行，則可能會發生服務或用戶端軟體失敗。 </li></ul>|
|||||

## <a name="dns"></a>DNS

<!-- before phase 9 -->

**適用于**：在自己的 DNS 網域中設定自訂 _msoid_ CNAME 的客戶

若設定， _msoid_ CNAME 只會影響使用 Office 桌面用戶端的客戶 (Microsoft 365 應用程式、office 365 ProPlus、office 2019、2016、... ) 。

若您已在您擁有的一或多個 DNS 命名空間中設定稱為 _msoid_ 的 DNS CNAME，必須先移除 CNAME，直到最後一個階段8結束。 您可以在階段8結束之前的任何時間移除 CNAME _msoid_ 。

若要確認您是否已在 DNS 命名空間中設定 CNAME，請遵循下列步驟，並以您自己的功能變數名稱取代 _contoso.com_ ：

```console
nslookup -querytype=CNMAE msoid.contoso.com
```

如果命令列傳回 DNS 記錄，請從您的網域中移除 _msoid_ CNAME。

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)

<!-- before phase 4 -->

**適用于**：使用 AD FS 內部部署的客戶，以驗證連線至 Microsoft Office 365 的使用者<br>
套用 **時**：第4階段之前的任何時間

讀取及套用 [ADFS 遷移步驟](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**適用于**：使用 SharePoint 2013 內部部署的客戶<br>
套用 **時**：第4階段之前的任何時間

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 限制 SharePoint 2013 工作流程，在 SharePoint 線上遷移期間使用。 | 減少 SharePoint 2013 工作流程，並在轉換之前完成航班中的工作流程。 | Inaction 可能會造成使用者混淆和問訊台通話。 |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**適用** 于：已啟用共用行事曆和可用性位址空間的 Exchange Online 客戶<br>
套用 **時**：階段9結束之前的任何時間

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 通知外部合作夥伴即將進行的轉換至 Office 365 服務。 | 可用性位址空間設定允許與 Office 365 共用空閒/忙碌資訊。 | 若失敗，可能會導致服務或用戶端在後續的遷移階段失敗。 |
||||

### <a name="exchange-online-hybrid-configuration"></a>Exchange Online 混合式設定

**適用于：** 所有在內部部署 Exchange 伺服器皆使用 Exchange 混合式設定的客戶<br>
套用 **時**：第5階段之前的任何時間

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 在您的租使用者進入遷移階段5之前，更新至最新版本的混合式設定向導 (HCW) 。 您可以在收到您的 Office 365 租使用者遷移已開始 (階段 1) 之後，立即啟動此活動。<br>您的 Exchange 系統管理員必須先卸載舊版的 HCW，然後 (17.0.5378.0 或以上) 中安裝及執行最新版本 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 。 |<ul><li>最新版本的 HCW 包含必要更新，以支援從 Microsoft Cloud Deutschland 實例將 Exchange Online 遷移至 Office 365 泛型服務。</li><li> 更新包括 _傳送連接器_ 和 _接收連接器_ 的內部部署憑證設定變更。</li><li>在階段5之前執行 HCW 時，請在 [office _365 Exchange Online_ ] 下的清單方塊的第2頁面上，選取 office _365 組織_ 位於下列清單中的 [Office 365： Exchange Online]。</li><li>**附注**：完成 Office 365 租使用者的階段9後，您將會再次移除並重新安裝 HCW，這次是使用 HCW 的第二頁上的「Office 365 全球」設定，以透過 Exchange Online 泛型服務完成混合式設定。</li></ul>|在 Exchange 遷移)  (第5階段之前執行 HCW 可能會導致服務或用戶端失敗。 |
| 建立 Set-authserver 內部部署指向全域安全性 Token 服務 (STS) 進行驗證 | 這可確保來自以混合式內部部署環境為目標之遷移狀態之使用者的 Exchange 可用性要求的驗證要求已驗證，可存取內部部署服務。 同樣地，這可確保從內部部署到 Office 365 全域服務端點的要求驗證。 | Azure AD 遷移 (階段 2) 完成之後，內部部署 Exchange (混合) 拓撲的系統管理員必須為 Office 365 泛型服務新增新的驗證服務端點。 使用此命令從 Exchange PowerShell，取代 `<TenantID>` Azure Active Directory 上 azure 入口網站中找到的組織租使用者識別碼。<br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1`<br> 無法完成此工作可能會導致混合空閒忙碌要求無法為已從 Microsoft Cloud Deutschland 遷移至 Office 365 服務的信箱使用者提供資訊。  |
||||

## <a name="skype-for-business-online"></a>商務用 Skype Online

<!-- before phase 7 -->

**適用于**：商務用 Skype Online 客戶<br>
套用 **時**：第7階段之前的任何時間

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 為在德國存取商務用 Skype 的使用者部署小組桌面用戶端。 | 遷移將商務用 Skype 使用者移至 Microsoft 小組，以共同作業、呼叫和聊天。 或者，部署 Microsoft 團隊桌面用戶端，或確定有支援的瀏覽器。 | Inaction 將導致 Microsoft 小組共同作業服務不可用。 |
| 複查並準備遷移相關的 DNS 變更。 | 針對商務用 Skype Online，客戶擁有的 DNS 區域變更。 |<ul><li>建議您將任何客戶擁有的網域 DNS 記錄的存留時間 (TTL) 更新為5分鐘，以加速 DNS 記錄的更新。 不過，與此 DNS 變更相關聯的 Microsoft 受管理轉換，可能需要在所提供的24小時變更視窗內任何時間進行。 </li><li>未來可能會中斷服務。 使用者無法登入商務用 Skype，將會重新導向至 Office 365 服務中已遷移的小組體驗。 </li></ul>|
| 準備使用者和管理的訓練和準備工作，以轉換至 Microsoft 團隊。 | 在您計畫使用者的通訊和準備工作時，從 Skype 切換至小組成功。 | <ul><li>用戶端必須注意新服務，以及如何在將其服務轉換成 Office 365 服務後使用。 </li><li>在對客戶虛名網域和初始網域進行 DNS 變更之後，使用者就會登入商務用 Skype，並看到他們現在已遷移到小組。 這也會在背景中為小組下載桌面用戶端。 </li></ul>|
||||

## <a name="mobile-device-management"></a>行動裝置管理

<!-- before phase 5 -->
**適用于：** 使用協力廠商行動裝置管理 (MDM) 解決方案的客戶<br>
套用 **時**：第5階段之前的任何時間

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 準備使用者和系統管理訓練，以供使用者移除並重新將其帳戶新增至 Microsoft Outlook，以供 iOS 和 Android。 | Microsoft Outlook for iOS 和 Android 使用 Microsoft 雲端 Deutschland 中的信箱所設定的帳戶，可能必須先移除並新增至 Outlook，才能正確地同步處理新的 Office 365 服務設定。 | 適用于 iOS 和 Android 客戶的 Microsoft Outlook | 先前為 Microsoft Cloud Deutschland 設定的 Outlook 信箱可能無法挑選新的 Office 365 服務設定，從而導致其他使用者體驗的錯誤和降級效能。 IT 系統管理員鼓勵提供檔，以主動指示使用者移除其帳戶到 Microsoft Outlook for iOS 和 Android 時，如果在遷移之後發生登入或同步處理郵件的問題。 |
| 決定遷移後是否需要重新配置。 | 行動裝置管理 (MDM) 解決方案可能會以端點為目標 `outlook.de` 。 在此轉換至 Office 365 服務時，用戶端設定檔應更新為 Office 365 服務 URL `outlook.office365.com` 。 | Exchange Online 和 MDM 客戶 | 當端點可供存取時，用戶端仍可繼續運作 `outlook.de` ，但如果無法再使用 Microsoft 雲端 Deutschland 端點，使用者將會失敗。 |
|||||

## <a name="line-of-business-apps"></a>企業營運應用程式

**適用于：** 使用企業營運 (LOB) 應用程式與 Microsoft Cloud Deutschland 提供之端點的客戶<br>
套用 **時**：在階段2完成之後和階段9結束之前

如果您使用的是協力廠商服務或企業營運 (LOB) 與 Office 365 整合的應用程式，則必須解決 Microsoft Cloud Deutschland 實例所提供之端點上的任何相依性。 例如，如果您的 LOB 應用程式正在連線 `https://graph.microsoft.de/` ，您必須將端點變更為 `https://graph.microsoft.com/` 。 在第2階段後，您的租使用者便可使用 Microsoft Office 365 泛型服務的端點。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 決定遷移後是否需要重新配置。 | 與 Office 365 整合的協力廠商服務和應用程式可能會編碼為預期 Microsoft Cloud Deutschland IP 位址和 URLs。 | 必要的動作。 Inaction 可能會導致服務或用戶端軟體失敗。 |
||||

## <a name="dynamics-365"></a>Dynamics 365

**適用于**：使用 Microsoft Dynamics 365 的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 若為 Dynamics 365 沙箱訂閱，請務必從 Microsoft Cloud Deutschland 中的 Dynamics 365 訂閱下載 Dynamics SQL 實例的實際執行環境。 在沙箱遷移之前，應將最新的實際備份還原至沙箱。 | 遷移 Dynamics 365 需要客戶確保沙箱環境以最新的實際執行資料庫重新整理。 | FastTrack 小組會協助客戶執行晾乾的執行，以驗證從 8. x 到9.1 的版本升級。 |
||||

## <a name="power-bi"></a>Power BI

**適用于**：使用 power BI 的客戶

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 從 Power BI 訂閱移除不會從 Power BI Microsoft Cloud Deutschland 遷移至 Office 365 服務的物件。 | 遷移 Power BI 服務需要客戶採取行動，以刪除特定的專案，例如資料集和儀表板。 | <ul><li>管理員可能必須將下列專案從其訂閱中移除： </li><li>Real-Time 資料集 (例如，流式傳送或推入資料集)  </li><li>Power BI 內部部署資料閘道設定和資料來源 </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

如果您使用的是 Office 365 和 Microsoft Azure 的相同 Azure Active Directory 身分識別分割區，請確定您準備好進行 Microsoft Azure 服務的客戶導向遷移。

> [!NOTE]
> 您的 Microsoft Azure 服務遷移必須在您的 Office 365 租使用者達到遷移階段3之前啟動，且必須在完成遷移階段8之前完成。

使用 Office 365 和 Azure 資源的客戶 (例如，網路、計算和儲存) 會執行將資源遷移至 Office 365 服務實例。 這種遷移是客戶的責任。 訊息中心文章會通知開始。 在 Office 365 服務環境中完成 Azure AD 組織之前，必須完成遷移。 如需 Azure 遷移，請參閱 azure 遷移行動手冊（ [Azure 德國遷移指南的概述](https://docs.microsoft.com/azure/germany/germany-migration-main)）。

| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 使用您的合作夥伴，判斷哪些 Azure 服務正在使用中，並準備今後從德國遷移至 Office 365 服務租使用者。 遵循 [Azure 遷移行動手冊](/azure/germany/germany-migration-main)中所述的步驟。 |<ul><li>遷移 Azure 資源是一項客戶責任，需要在規定的步驟後手動工作。 瞭解組織中所使用的服務是成功遷移 Azure 服務的關鍵。 </li><li> Office 365 德國在相同身分識別分割下具有 Azure 訂閱的客戶 (組織) 必須遵循 Microsoft 規定的訂單，當他們可以開始訂閱和服務遷移時。</li></ul>|<ul><li>客戶可能會有多個 Azure 訂閱，每個包含基礎結構、服務和平臺元件的訂閱。 </li><li> 管理員應識別訂閱和專案關係人，以確保在此遷移事件中，可能會有提示進行遷移和驗證。 </li><li>無法順利完成這些訂閱和指定時程表內的 Azure 元件的遷移，會影響 Office 和 Azure AD 轉換至 Office 365 服務的完成，而且可能會導致資料遺失。 </li><li> 訊息中心通知會通知用戶端遷移開始的點。 </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>其他相關資訊

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
