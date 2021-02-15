---
title: 從 Microsoft Cloud Deutschland 進行遷移的準備工作
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
description: 摘要：從 Microsoft Cloud 德國移動 (Microsoft Cloud Deutschland) 到新德文 datacenter 區域中的 Office 365 服務的準備工作。
ms.openlocfilehash: 8160756bdbf973741f5e75f45dc2a2044f63e39b
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242839"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移的準備工作


使用下列連結可取得與貴組織相關的預備工作步驟：

- 針對所有訂閱，請執行 [下列步驟](#applies-to-everyone)。
- 如果您使用的是 Exchange Online 或 Exchange 混合式，請執行 [此步驟](#exchange-online)。
- 如果您使用的是 SharePoint 線上，請執行 [此步驟](#sharepoint-online)。
- 如果您正在使用協力廠商行動裝置管理 (MDM) 解決方案，請執行 [此步驟](#mobile)。
- 如果您使用的是協力廠商服務或企業營運 (LOB) 與 Office 365 整合的應用程式，請執行 [此步驟](#line-of-business-apps)。
- 如果您同時使用的是 Office 365 訂閱隨附的 Azure 服務，請執行 [此步驟](#azure)。
- 如果您也是使用 Dynamics 365，請執行 [此步驟](#dynamics365)。
- 如果您也是使用 Power BI，請執行 [此步驟](#power-bi)。
- 若為 DNS 變更，請執行 [此步驟](#dns)。
- 如果您使用的是同盟身分識別，請執行 [下列步驟](#federated-identity)。

## <a name="applies-to-everyone"></a>適用于所有人

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 確定 Office 365 服務的網路連線能力 [URLs 及 IP 位址](https://aka.ms/o365urls)。 | 由客戶所主控的所有用戶端和服務，用來存取 Office 365 服務，必須能夠存取 Office 365 服務端點。 | 所有轉換的客戶，以及網路訪問限制為 Microsoft Cloud Deutschland 的客戶。 | 必要的動作。 如果這不是在第4階段中執行，則可能會發生服務或用戶端軟體失敗。 |
| 複查並準備遷移相關的 DNS 變更。 | 針對商務用 Skype Online，客戶擁有的 DNS 區域變更。 | 商務用 Skype Online 客戶 | -建議您將任何客戶擁有的網域 DNS 記錄的存留時間 (TTL) 更新為5分鐘，以加速 DNS 記錄的更新。 不過，與此 DNS 變更相關聯的 Microsoft 受管理轉換，可能需要在所提供的24小時變更視窗內任何時間進行。 <br><br> -未來可能會中斷服務。 使用者無法登入商務用 Skype，將會重新導向至 Office 365 服務中已遷移的小組體驗。 |
| 準備使用者和管理的訓練和準備工作，以轉換至 Microsoft 團隊。 | 在您計畫使用者的通訊和準備工作時，從 Skype 切換至小組成功。 | 商務用 Skype Online 客戶 | -用戶端必須注意新服務，以及如何在將其服務轉換為 Office 365 服務後使用。 <br><br> -在對客戶虛名網域和初始網域進行 DNS 變更之後，使用者就會登入商務用 Skype，並看到他們現在已遷移到小組。 這也會在背景中為小組下載桌面用戶端。 |
| 準備使用者和系統管理訓練，以供使用者移除並重新將其帳戶新增至 Microsoft Outlook，以供 iOS 和 Android。 | Microsoft Outlook for iOS 和 Android 使用 Microsoft 雲端 Deutschland 中的信箱所設定的帳戶，可能必須先移除並新增至 Outlook，才能正確地同步處理新的 Office 365 服務設定。 | 適用于 iOS 和 Android 客戶的 Microsoft Outlook | 先前為 Microsoft Cloud Deutschland 設定的 Outlook 信箱可能無法挑選新的 Office 365 服務設定，從而導致其他使用者體驗的錯誤和降級效能。 IT 系統管理員鼓勵提供檔，以主動指示使用者移除其帳戶到 Microsoft Outlook for iOS 和 Android 時，如果在遷移之後發生登入或同步處理郵件的問題。 |
| 準備在遷移後，通知使用者如何重新開機和登出用戶端。 | Office 用戶端授權會從 Microsoft Cloud Deutschland 轉換為遷移中的 Office 365 服務。 用戶端登出及簽入 Office 用戶端後，用戶端會挑選新的有效授權。 | Microsoft 365 應用程式客戶 |  使用者的 Office 產品需要重新整理 Office 365 服務的授權。 如果未重新整理授權，Office 產品可能會遇到授權驗證錯誤。 |
| 取消所有的試用訂閱。 | 不會遷移試用訂閱，而且會封鎖付費訂閱的轉接。 | 所有客戶 | 若使用者在取消後存取，試用版服務會到期且無法運作。 |
| 為在德國存取商務用 Skype 的使用者部署小組桌面用戶端。 | 遷移將使用者移至小組，以進行共同作業、呼叫和交談。 或者，部署小組桌面用戶端，或確定有支援的瀏覽器。 | 商務用 Skype 客戶 | Inaction 將導致小組共同作業服務不可用。 |
| 分析 Microsoft Cloud Deutschland 與 Office 365 服務之間授權功能的差異。 | Office 365 服務包含目前 Microsoft Cloud Deutschland 中無法使用的其他功能和服務。 在訂閱轉移期間，使用者將可以使用新功能。 | 所有客戶 | -分析 Microsoft Cloud Deutschland 和 Office 365 服務的授權所提供的不同功能。 開始使用 [Office 365 平臺服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)。 <br><br> -判斷是否應該開始停用 Office 365 服務的任何新功能，以限制使用者或使用者變更管理的影響，並視需要變更使用者授權指派。 <br><br> -針對 Office 365 服務提供的新服務和功能，準備使用者及服務台人員。 |
| 建立整個組織 [保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention) ，以防止在遷移期間因無意中刪除內容。  | -若要確保使用者不會在遷移期間由使用者意外刪除內容，客戶可以選擇啟用整個組織的保留原則。 <br><br> -雖然不需要保留，但在遷移期間任何時間保留的保留原則都應該如預期般運作，具有保留原則的備份安全機制。 同時，所有客戶可能不會使用保留原則，尤其是有關保留原則的使用者。 | Office 客戶 | 如 [深入瞭解保留原則和保留標籤](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)所述套用保留原則。 如果這不是在第4階段中執行，則可能會發生服務或用戶端軟體失敗。  |
| [備份 Active Directory Federation Services (AD FS) 伺服器](ms-cloud-germany-transition-add-adfs.md#backup) 陣列以取得嚴重損壞修復案例。 | 客戶必須適當備份 AD FS 伺服器陣列，以確保在不觸及網域之發行者 URI 的情況下，對全域 & 的信賴憑證者信任可以還原。 Microsoft 建議在伺服器陣列的備份中使用 AD FS 快速還原（如有必要）。 | 同盟驗證組織 | 必要的動作。 當客戶的 AD FS 伺服器陣列失敗時，Inaction 將會在遷移期間產生服務影響。 如需詳細資訊，請參閱《 ADFS 遷移步驟] (https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |


## <a name="exchange-online"></a>Exchange Online

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 通知外部合作夥伴即將進行的轉換至 Office 365 服務。 | 可用性位址空間設定允許與 Office 365 共用空閒/忙碌資訊。 | 已啟用共用行事曆和可用性位址空間的 Exchange Online 客戶。 | 必要的動作。  若失敗，可能會導致服務或用戶端在後續的遷移階段失敗。 |
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


### <a name="for-hybrid-exchange"></a>混合式 Exchange

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 卸載舊版的混合式設定向導 (HCW) ，然後安裝並執行最新版本 17.0.5378.0 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) 。 | 最新版本的 HCW 包含必要更新，以支援從 Microsoft Cloud Deutschland 轉換為 Office 365 服務的客戶。 <br><br> 更新包括傳送連接器和接收連接器對內部部署憑證設定的變更。 | Exchange Online 客戶執行混合式部署 | 必要的動作。 在階段5之 9 (Exchange) 之前失敗，可能會導致服務或用戶端失敗。 |
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

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 限制 SharePoint 2013 工作流程，在 SharePoint 線上遷移期間使用。 | 減少 SharePoint 2013 工作流程，並在轉換之前完成航班中的工作流程。 | SharePoint 線上客戶 | Inaction 可能會造成使用者混淆和問訊台通話。 |
|||||

## <a name="mobile"></a>行動裝置

如果您正在使用協力廠商行動裝置管理 (MDM) 解決方案：

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 決定遷移後是否需要重新配置。 | MDM 解決方案可能會以端點為目標 `outlook.de` 。 在此轉換至 Office 365 服務時，用戶端設定檔應更新為 Office 365 服務 URL `outlook.office365.com` 。 | Exchange Online 和 MDM 客戶 | 當端點可供存取時，用戶端仍可繼續運作 `outlook.de` ，但如果無法再使用 Microsoft 雲端 Deutschland 端點，使用者將會失敗。 |
|||||

## <a name="line-of-business-apps"></a>企業營運應用程式

如果您使用的是協力廠商服務或企業營運 (LOB) 與 Office 365 整合的應用程式： 

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 決定遷移後是否需要重新配置。 | 與 Office 365 整合的協力廠商服務和應用程式可能會編碼為預期 Microsoft Cloud Deutschland IP 位址和 URLs。 | 所有客戶 | 必要的動作。 Inaction 可能會導致服務或用戶端軟體失敗。 |
|||||

## <a name="azure"></a>Azure 

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 使用您的合作夥伴，判斷哪些 Azure 服務正在使用中，並準備今後從德國遷移至 Office 365 服務租使用者。 遵循 [Azure 遷移行動手冊](https://docs.microsoft.com/azure/germany/germany-migration-main)中所述的步驟。 | 遷移 Azure 資源是一項客戶責任，需要在規定的步驟後手動工作。 瞭解組織中所使用的服務是成功遷移 Azure 服務的關鍵。 <br><br> Office 365 德國在相同身分識別分割下具有 Azure 訂閱的客戶 (組織) 必須遵循 Microsoft 規定的訂單，當他們可以開始訂閱和服務遷移時。 | Azure 客戶 | -客戶可以有多個 Azure 訂閱，每個包含基礎結構、服務和平臺元件的訂閱。 <br><br> -系統管理員應識別訂閱和利益關係人，以確保在此遷移事件中，可能會進行遷移和驗證。 <br><br> 無法順利完成這些訂閱和指定時程表內的 Azure 元件的遷移，會影響 Office 和 Azure AD 轉換至 Office 365 服務的完成，而且可能會導致資料遺失。  <br><br> -郵件中心通知會通知用戶端遷移開始的位置。 |
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

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 若為 Dynamics 365 沙箱訂閱，請務必從 Microsoft Cloud Deutschland 中的 Dynamics 365 訂閱下載 Dynamics SQL 實例的實際執行環境。 在沙箱遷移之前，應將最新的實際備份還原至沙箱。 | 遷移 Dynamics 365 需要客戶確保沙箱環境以最新的實際執行資料庫重新整理。 | Microsoft Dynamics 客戶 | FastTrack 小組會協助客戶執行晾乾的執行，以驗證從 8. x 到9.1 的版本升級。 |
|||||

## <a name="power-bi"></a>Power BI

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 從 Power BI 訂閱移除不會從 Power BI Microsoft Cloud Deutschland 遷移至 Office 365 服務的物件。 | 遷移 Power BI 服務需要客戶採取行動，以刪除特定的專案，例如資料集和儀表板。 | Power BI 客戶 | 管理員可能必須將下列專案從其訂閱中移除： <br> -Real-Time 資料集 (例如，流式傳送或推入資料集)  <br> -Power BI 內部部署資料閘道設定和資料來源 |
|||||

## <a name="dns"></a>DNS

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 移除 MSOID，從客戶擁有的 DNS CName （若有的話），請在 Azure AD 切中的任何時間存在。 可以設定為5分鐘的 TTL，使變更能快速生效。 | 由客戶擁有的 DNS 區域變更 | Office 用戶端服務客戶 | 
|||||

## <a name="federated-identity"></a>同盟身分識別

| 步驟 (s)  | 描述 | 適用於 | 影響 |
|:-------|:-----|:-------|:-------|
| 新增單一登入 (SSO) 至現有的信賴憑證者信任，並停用 AD FS 中繼資料自動更新的識別碼。 | 開始遷移之前，必須先將識別碼新增至 AD FS 信賴憑證者信任。 若要避免意外移除信賴憑證方識別碼，請停用中繼資料更新的自動更新。 <br><br> 在 AD FS 伺服器上執行下列命令： <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | 同盟驗證組織 | 必要的動作。 Inaction SharePoint (第4階段之前 9) 會在遷移期間產生服務影響。  |
| 為全域 Azure AD 端點產生信賴憑證者信任。 | 客戶必須手動建立信賴憑證者信任 (RPT) 到 [全域](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) 端點。 方法是透過 GUI 新增 RPT，方法是利用全域同盟中繼資料 URL，然後使用 [AZURE AD RPT 宣告規則](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (于 AD FS 說明中) 產生宣告規則並將其匯入 RPT。 | 同盟驗證組織 | 必要的動作。 Inaction 會在遷移期間產生服務影響。 |
|||||

## <a name="more-information"></a>詳細資訊

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

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
