---
title: 從 Microsoft Cloud Deutschland 進行移移的預先作業
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
description: 摘要：從 Microsoft Cloud 德國 (Microsoft Cloud Deutschland) 移往新的德國資料中心地區的 Office 365 服務時，事前工作。
ms.openlocfilehash: cd32ce21e18b16660c4292c98ebcc0f7cb982173
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921563"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行移移的預先作業


請使用這些連結，取得與貴組織相關的工作前步驟：

- 針對所有訂閱，請執行 [下列步驟](#applies-to-everyone)。
- 如果您使用的是 Exchange Online 或 Exchange 混合式，請 [執行此步驟](#exchange-online)。
- 如果您使用的是 SharePoint Online，請執行 [此步驟](#sharepoint-online)。
- 如果您使用 MDM 解決方案的協力廠商行動裝置 (，) [執行此步驟](#mobile)。
- 如果您使用與 Office 365 整合的協力廠商服務或企業 (LOB) App，請執行 [此步驟](#line-of-business-apps)。
- 如果您也使用 Office 365 訂閱以外的 Azure 服務，請 [執行此步驟](#azure)。
- 如果您同時使用 Dynamics 365，請執行 [此步驟](#dynamics365)。
- 如果您同時使用 Power BI，請執行 [此步驟](#power-bi)。
- 針對 DNS 變更，請 [執行此步驟](#dns)。
- 如果您使用的是聯合身分識別，請執行 [下列步驟](#federated-identity)。

## <a name="applies-to-everyone"></a>適用于每個人

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 確保 Office [365 服務 URL 和 IP 位址的網路能力](https://aka.ms/o365urls)。 | 客戶所託管用來存取 Office 365 服務的所有用戶端和服務都必須能夠存取 Office 365 服務端點。 | 所有轉換客戶和網路存取僅限於 Microsoft Cloud Deutschland 的客戶。 | 必要的動作。 不回應可能會導致服務或用戶端軟體失敗。 |
| 檢查及準備與移移相關的 DNS 變更。 | 客戶會準備 Exchange Online 和 Exchange Online Protection 的 DNS (MX 記錄等) 。 | Exchange Online 客戶 | 這是建議的動作。 任何動作都表示在 Microsoft Cloud Deutschland 服務停用之前，已移移客戶的電子郵件可能會透過 Microsoft Cloud Deutschland 路由。 |
| 檢查及準備與移移相關的 DNS 變更。 | 商務用 Skype Online 的客戶擁有 DNS 區域變更。 | 商務用 Skype Online 客戶 | - 建議您針對任何客戶擁有的網域 DNS 記錄，將即時 (TTL) 更新為 5 分鐘，以便快速重新整理 DNS 記錄。 不過，在提供的 24 小時變更視窗中，隨時都可能發生與此 DNS 變更相關聯的 Microsoft 管理完全關聯。 <br><br> - 未來可能會中斷服務。 使用者將無法登入商務用 Skype，且會重新導向至 Office 365 服務中已移轉的 Teams 體驗。 |
| 準備使用者與系統管理訓練，並做好轉換至 Microsoft Teams 的準備。 | 規劃使用者通訊與準備，成功從 Skype 轉換到 Teams。 | 商務用 Skype Online 客戶 | - 用戶端必須注意新的服務，以及當其服務轉換到 Office 365 服務之後，如何使用。 <br><br> - 在針對客戶虛名網域和初始網域進行 DNS 變更之後，使用者會登入商務用 Skype，並看到這些變更現在已移入 Teams。 這也會在背景中下載 Teams 桌面用戶端。 |
| 針對使用者移除帳戶，以及將其帳戶重新新增到 iOS 和 Android 版 Microsoft Outlook，準備使用者和管理訓練。 | 在 Microsoft Cloud Deutschland 中以信箱所配置的 iOS 版和 Android 版 Microsoft Outlook 帳戶，可能必須再次移除並新增到 Outlook，才能正確同步處理新的 Office 365 服務配置。 | iOS 和 Android 版 Microsoft Outlook 客戶 | 先前為 Microsoft Cloud Deutschland 所配置的 Outlook 信箱可能無法選取新的 Office 365 服務組組，這可能會導致其他使用者體驗發生錯誤和降級的績效。 我們鼓勵 IT 系統管理員提供檔，主動指示使用者在移移後發生登出或同步處理郵件的問題，以主動指示他們移除帳戶，再將其帳戶重新新增到 iOS 版和 Android 版 Microsoft Outlook。 |
| 準備在移移之後通知使用者重新開機並用戶端與用戶端的簽到與退出。 | Office 用戶端授權將在移轉期間從 Microsoft Cloud Deutschland 移轉至 Office 365 服務。 用戶端在退出並進入 Office 用戶端後，會挑選新的有效授權。 | Microsoft 365 應用程式客戶 |  使用者的 Office 產品需要重新更新 Office 365 服務中的授權。 如果授權未重新更新，Office 產品可能會遇到授權驗證錯誤。 |
| 取消任何試用版訂閱。 | 試用版訂閱將不會移轉，並且會封鎖付費訂閱的移轉。 | 所有客戶 | 如果使用者在取消後存取試用服務，則試用服務已過期且未運作。 |
| 為在德國存取商務用 Skype 的使用者部署 Teams 桌面用戶端。 | 移移會將使用者移至 Teams 進行共同合作、通話和聊天。 或者，部署 Teams 桌面用戶端，或確保可以使用支援的瀏覽器。 | 商務用 Skype 客戶 | 無動作會導致無法取得 Teams 共同處理服務。 |
| 分析 Microsoft Cloud Deutschland 與 Office 365 服務之間的授權功能差異。 | Office 365 服務包含目前 Microsoft Cloud Deutschland 未提供的其他功能和服務。 在訂閱移轉期間，使用者可以使用新功能。 | 所有客戶 | - 分析 Microsoft Cloud Deutschland 和 Office 365 服務授權提供的不同功能。 從 [Office 365 平臺服務描述開始](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 <br><br> - 決定是否應一開始停用 Office 365 服務的任何新功能，以限制對使用者或使用者變更管理的影響，並根據需要變更使用者授權指派。 <br><br> - 為使用者和技術支援人員做好使用 Office 365 服務所提供之新服務與功能的準備。 |
| 建立全組織的 [保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention) ，避免在移移期間不小心刪除內容。  | - 為確保使用者在移移期間不會不小心刪除內容，客戶可以選擇啟用整個組織的保留原則。 <br><br> - 雖然不需要保留，因為隨時在移移期間所保留的保留應會如預期地作用，但具有保留原則是一種備份安全機制。 同時，保留原則不一定所有客戶都使用，特別是擔心保留的客戶。 | Office 客戶 | 請如瞭解保留原則與保留標籤 [一文所述，來申請保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)。 |
| [針對災害復原案例，備份 Active Directory Federation Services (AD FS) ](ms-cloud-germany-transition-add-adfs.md#backup) 伺服器。 | 客戶需要妥善備份 AD FS 伺服器庫，以確保可還原仰賴方對全域 & Germany 端點的信任，而不會重壓網域的發行者 URI。 Microsoft 建議您使用 AD FS 快速還原來備份伺服器，並視需要分別進行還原。 | 聯合驗證組織 | 必要的動作。 如果客戶的 AD FS 伺服器組失敗，則 Inaction 會導致在移移期間影響服務。 |


## <a name="exchange-online"></a>Exchange Online

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 通知外部合作夥伴即將轉換到 Office 365 服務。 | 可用性位址空間配置允許與 Office 365 共用空閒/忙碌資訊。 | Exchange Online 客戶已啟用共用日曆和顯示狀態位址空間。 | 必要的動作。  若未執行此工作，可能會導致在客戶移移的後一個階段中產生服務或用戶端失敗。 |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>適用于混合式 Exchange

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 卸載先前版本的混合式組 (HCW) ，然後安裝並執行最新版的 17.0.5378.0，從 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) | 最新版的 HCW 包含必要的更新，可支援從 Microsoft Cloud Deutschland 轉換至 Office 365 服務的客戶。 <br><br> 更新包括變更傳送連接器和接收連接器內部部署憑證設定。 | Exchange Online 客戶使用混合式部署 | 必要的動作。 若失敗，可能會導致服務或用戶端失敗。 |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

如果您有 SharePoint 2013：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 限制 SharePoint 2013 工作流程，在 SharePoint Online 移改期間使用。 | 轉換前先減少 SharePoint 2013 工作流程，並完成進行中的工作流程。 | SharePoint Online 客戶 | 無反應可能會導致使用者混淆和技術支援人員電話。 |
|||||

## <a name="mobile"></a>行動裝置

如果您使用 MDM 解決方案的協力廠商行動裝置 () 解決方案：

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 判斷移移之後，是否需重新進行任何重新安裝。 | MDM 解決方案可能會鎖定 `outlook.de` 端點。 在轉換到 Office 365 服務之後，用戶端設定檔應該會更新為 Office 365 服務 `outlook.office365.com` URL。 | Exchange Online 和 MDM 客戶 | 當端點可供使用時，用戶端可能會繼續運作，但如果 `outlook.de` Microsoft Cloud Deutschland 端點不再可用，就會失敗。 |
|||||

## <a name="line-of-business-apps"></a>企業經營應用程式

如果您使用與 Office 365 整合的協力廠商服務或企業 (LOB) App： 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 判斷移移之後，是否需重新進行任何重新安裝。 | 與 Office 365 整合的協力廠商服務與應用程式可能編碼為預期 Microsoft Cloud Deutschland IP 位址和 URL。 | 所有客戶 | 必要的動作。 不回應可能會導致服務或用戶端軟體失敗。 |
|||||

## <a name="azure"></a>Azure 

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 與合作夥伴合作，判斷目前使用中的 Azure 服務，並準備未來從德國移移至 Office 365 服務租使用者。 請遵循 Azure 移存劇本 [中所述的步驟](https://docs.microsoft.com/azure/germany/germany-migration-main)。 | 移移 Azure 資源是客戶的責任，需要按照指定的步驟進行手動工作。 瞭解組織中使用哪些服務是成功移移 Azure 服務的關鍵。 <br><br> Office 365 Germany 客戶的 Azure 訂閱在相同身分識別分割 (組織) 必須遵循 Microsoft 指定的訂單，才能開始進行訂閱和服務移移。 | Azure 客戶 | - 客戶可能有多個 Azure 訂閱，每個訂閱都包含基礎結構、服務和平臺元件。 <br><br> - 系統管理員應識別訂閱和專案關係人，以確保可在此移移事件期間立即進行移移和驗證。 <br><br> 未在指定的時程表中順利完成這些訂閱和 Azure 元件移轉，將會影響 Office 和 Azure AD 移轉至 Office 365 服務的完成，並可能導致資料遺失。  <br><br> - 訊息中心通知會指出客戶主導移移可以開始的點。 |
|||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="dynamics-365"></a>Dynamics 365

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 針對 Dynamics 365 沙箱訂閱，請務必從 Microsoft Cloud Deutschland 中的 Dynamics 365 訂閱下載 Dynamics SQL 實例的生產環境。 最新的生產備份應該先還原至沙箱，再進行沙箱化移移。 | 若要移移 Dynamics 365，客戶必須確保沙箱環境已使用最新的生產資料庫重新更新。 | Microsoft Dynamics 客戶 | FastTrack 小組會協助客戶執行完全執行，以驗證從 8.x 升級至 9.1.x 的版本。 |
|||||

## <a name="power-bi"></a>Power BI

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 移除 Power BI 訂閱中不會從 Power BI Microsoft Cloud Deutschland 移為 Office 365 服務的物件。 | 移移 Power BI 服務會要求客戶採取動作，以刪除某些產品，例如資料集和儀表板。 | Power BI 客戶 | 系統管理員可能必須移除其訂閱中的下列專案： <br> - Real-Time資料集 (例如串流或推送資料集)  <br> - Power BI 內部部署資料閘道組配置與資料來源 |
|||||

## <a name="dns"></a>DNS

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 如果在 Azure AD 完全轉換之前存在，請從客戶擁有的 DNS 移除 MSOID、CName。 您可以將 5 分鐘的 TTL 設定為讓變更快速生效。 | 客戶擁有的 DNS 區域變更 | Office 用戶端服務客戶 | 
|||||

## <a name="federated-identity"></a>同盟身分識別

| 步驟 (步驟)  | 說明 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 新增單一登入 SSO (識別碼) 受信任方的信任，並停用 AD FS 中繼資料自動更新。 | 在開始移移之前，必須先將識別碼新增到 AD FS 仰賴的一方信任。 為了避免意外移除仰賴方識別碼，請停用中繼資料更新的自動更新。 <br><br> 在 AD FS 伺服器上執行此命令： <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | 聯盟驗證組織 | 必要的動作。 Inaction 會導致在移移期間影響服務。  |
| 產生全球 Azure AD 端點的仰賴方信任。 | 客戶需要手動建立仰賴的一方信任 (RPT) 至 [全域](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 端點。 透過 GUI 新增 RPT 是利用全域聯合中繼資料 URL，然後使用 AD FS Help (中的 [Azure AD RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) 索賠規則) 來新增 RPT 以完成此工作。 | 聯盟驗證組織 | 必要的動作。 Inaction 會導致在移移期間影響服務。 |
|||||

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
