---
title: 從 Microsoft Cloud Deutschland 進行遷移的預先遷移活動
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
description: 摘要：從 microsoft cloud 德國移動 (microsoft cloud Deutschland) 以 Office 365 新德文 datacenter 區域中的服務的準備工作。
ms.openlocfilehash: 08774cdfd831556c194b5175879f211efa250632
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362735"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 進行遷移的預先遷移活動

使用下列連結可取得與貴組織相關的預先遷移步驟。

如果您正在使用

- **在 Microsoft Cloud Deutschland 中 Office 365**，請執行 [下列步驟](#general-tenant-migration-considerations)。
- **自訂網域**，請執行 [此步驟](#dns-entries-for-custom-domains)。
- **Office 應用程式**，請考慮 [此步驟](#office-apps)。
- **SharePoint 線上**，請執行 [此步驟](#sharepoint-online)。
- **Exchange Online** 或 **Exchange 混合**，請執行 [此步驟](#exchange-online)。
- **商務用 Skype 線上**，請執行 [此步驟](#skype-for-business-online)。
- **Dynamics 365**，請執行 [此步驟](#dynamics-365)。
- **Power BI**，請執行 [此步驟](#power-bi)。
- Azure AD 連線的 **Active Directory Federation Services** ，請執行 [下列步驟](#active-directory-federation-services-ad-fs)。
- **協力廠商服務** 或 **企業營運 (LOB)** 與 Office 365 整合的應用程式，請執行 [此步驟](#line-of-business-apps)。
- 協力廠商行動裝置管理 (MDM) 解決方案，請執行 [此步驟](#mobile-device-management)。
- **Azure 服務** 與您的 Office 365 訂閱，請執行 [此步驟](#microsoft-azure)。

## <a name="general-tenant-migration-considerations"></a>一般承租人遷移考慮

**適用于：** 在 Microsoft Deutschland 雲端實例中使用 Office 365 的所有客戶

遷移期間會保留 Office 365 租使用者和使用者識別碼。 Azure AD 服務呼叫會從 Microsoft Cloud Deutschland 重新導向至 Office 365 泛型服務，且對 Office 365 服務而言是透明的。

- 一般資料保護法規 (GDPR) 資料主體要求 (Dsr) 會從 Azure Admin 入口網站執行，以供未來的要求使用。 在 Microsoft 雲端 Deutschland 中的任何舊版或非客戶診斷資料會在經過30天之後刪除。

- 多重要素驗證 (MFA) 要求使用 Microsoft Authenticator 顯示為使用者 ObjectID (GUID) 時，會將租使用者複製到 Office 365 服務。 雖然這種顯示行為，MFA 要求仍會如期執行。  使用 Office 365 服務端點啟用 Microsoft Authenticator 帳戶會顯示使用者主要名稱 (UPN) 。  使用 microsoft cloud Deutschland 端點新增的帳戶會顯示使用者 ObjectID，但是會同時使用 microsoft 雲端 Deutschland 和 Office 365 服務端點。

<br>

****

|步驟 (s) |描述|影響|
|---|---|---|
|準備在遷移後，通知使用者如何重新開機和登出用戶端。|Office 用戶端授權會從 Microsoft Cloud Deutschland 轉換為遷移中 Office 365 服務。 用戶端登入及簽出 Office 用戶端後，用戶端會挑選新的有效授權。|使用者的 Office 產品需要重新整理 Office 365 服務的授權。 如果未重新整理授權，Office 產品可能會遇到授權驗證錯誤。|
|確定 Office 365 服務的網路連線能力[URLs 和 IP 位址](https://aka.ms/o365urls)。|由客戶所主控的所有用戶端和服務，用來存取 Office 365 服務，必須能夠存取 Office 365 泛型服務端點。 <p> 若您或您的共同作業夥伴有適當的防火牆規則，可防止存取 Office 365 服務中所列的 URLs 和 ip 位址[URLs 和 ip 位址](https://aka.ms/o365urls)必須變更防火牆規則，以允許存取 Office 365 全域服務端點|如果不是在階段4之前完成，則可能會發生服務或用戶端軟體失敗|
|取消所有的試用訂閱。|不會遷移試用訂閱，而且會封鎖付費訂閱的轉接。|若使用者在取消後存取，試用版服務會到期且無法運作。|
|分析 Microsoft Cloud Deutschland 與 Office 365 泛型服務之間的授權功能差異。|Office 365 服務包含目前 Microsoft Cloud Deutschland 中無法使用的其他功能和服務。 在訂閱轉移期間，使用者將可以使用新功能。|<ul><li>分析 Microsoft Cloud Deutschland 的授權所提供的不同功能，並 Office 365 泛型服務。 請從[Office 365 平臺服務描述](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)開始。</li><li>決定是否應該最初停用 Office 365 服務的任何新功能，以限制使用者或使用者變更管理上的影響，並視需要變更使用者授權指派。</li><li>準備使用者及服務台人員，以取得 Office 365 服務提供的新服務和功能。</li></ul>|
|建立整個組織 [保留原則](/microsoft-365/compliance/retention) ，以防止在遷移期間因無意中刪除內容。|<ul><li>為了確保使用者不會在遷移期間由使用者意外刪除內容，客戶可以選擇啟用整個組織的保留原則。</li><li>雖然不需要保留，但在遷移期間可隨時使用保留原則，但具有保留原則是備份的安全性機制。 同時，所有客戶可能不會使用保留原則，尤其是有關保留原則的使用者。</li></ul>|如 [深入瞭解保留原則和保留標籤](/microsoft-365/compliance/retention-policies)所述套用保留原則。 如果這不是在第4階段中執行，則可能會發生服務或用戶端軟體失敗。|


## <a name="dns-entries-for-custom-domains"></a>自訂網域的 DNS 專案

<!-- before phase 9 -->

**適用于**：在自己的 DNS 網域中設定自訂 _msoid_ CNAME 或使用 Exchange Online 網域的客戶

若設定， _msoid_ CNAME 只會影響使用 Office 桌面用戶端 (Microsoft 365 Apps、Office 365 專業增強版、Office 2019、2016、... ) 的客戶。

若您已在您擁有的一或多個 DNS 命名空間中設定稱為 _msoid_ 的 DNS CNAME，必須先移除 CNAME，直到最後一個階段8結束。 您可以在階段8結束之前的任何時間移除 CNAME _msoid_ 。

若要確認您是否已在 DNS 命名空間中設定 CNAME，請遵循下列步驟，並以您自己的功能變數名稱取代 _contoso.com_ ：

```console
nslookup -querytype=CNAME msoid.contoso.com
```

如果命令列傳回 DNS 記錄，請從您的網域中移除 _msoid_ CNAME。

> [!NOTE]
> 如果您使用的是 Exchange Online 的自訂網域，您必須可以存取您的 DNS 主機服務提供者。 請確定您可以存取和編輯您的 DNS 設定，您會在遷移期間修改 DNS 記錄。

## <a name="office-apps"></a>Office應用程式

**適用于**：使用 Office app 的客戶，特別是在 Windows 用戶端上 <br>
套用 **時：在** 階段9開始之前的任何時間

Office 365 承租人轉換至地區 "德國" 時，會要求所有使用者關閉、登出所有 Office 的桌面應用程式，以 Office 365 和傳回所有的桌面應用程式 (Word、Excel、PowerPoint、Outlook 等。在租使用者遷移到達階段9之後，) 和商務用 OneDrive 用戶端。 登出和簽出，可讓 Office 服務從全域 Azure AD 服務取得新的驗證權杖。

這對於所有用戶端都是必要的。 為了確保順利進行遷移的體驗，強烈建議您提前通知並指示所有受影響的使用者，並在此即將發生的活動的早期階段。

使用受管理的 Windows 用戶端的客戶可以使用[Office 用戶端切換工具 (OCCT) ](https://github.com/microsoft/OCCT)來準備 Windows 機器。 OCCT 設計為在租使用者到達遷移的階段9之前，定期在 Windows 用戶端上執行。 當您已到達階段9時，OCCT 會自動在機器上執行所有必要的變更，而不需要使用者互動。

OCCT 可在任何時間，在階段9之前部署在 Windows 用戶端上。 [！附注] 如果 OCCT 應支援遷移體驗，建議您儘快啟動部署，以規定用戶端數目上限。

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)

**適用于**：使用 AD FS 內部部署的客戶，以驗證連接至 Microsoft Office 365 的使用者<br>
套用 **時**：第2階段之前的任何時間

讀取及套用 [ADFS 遷移步驟](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**適用于**：使用 SharePoint 2013 內部部署的客戶<br>
套用 **時**：第4階段之前的任何時間

<br>

****

|步驟 (s) |描述|影響|
|---|---|---|
|限制 SharePoint 2013 工作流程，在 SharePoint 線上遷移期間使用。|減少 SharePoint 2013 工作流程，並在轉換之前完成航班中的工作流程。|Inaction 可能會造成使用者混淆和問訊台通話。|


## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**適用于**： Exchange Online 客戶<br>
套用 **時**：階段9結束之前的任何時間

<br>

****

|步驟 (s) |描述|影響|
|---|---|---|
|通知外部夥伴即將進行的轉換至 Office 365 服務。|客戶必須告知其合作夥伴已啟用共用行事曆和可用性位址空間設定 (允許 Office 365) 共用空閒/忙碌資訊。 當 Exchange Online 遷移完成時，可用性設定必須進行轉換，以使用[Office 365 世界端點](/microsoft-365/enterprise/urls-and-ip-address-ranges)。|若失敗，可能會導致服務或用戶端在後續的遷移階段失敗。|
|通知使用者必要的 IMAP4/POP3/SMTP 用戶端變更。|具有裝置連線至 Microsoft 雲端 Deutschland 端點的使用者通訊協定 IMAP4 POP3，SMTP 是必要手動更新其用戶端裝置以切換至[Exchange Online 伺服器名稱](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes)的使用者。|將這種相依性傳遞給這些通訊協定的使用者，並確保在遷移期間，他們可以切換為使用 Outlook 行動或 Outlook 網頁版。 若失敗更新用戶端端點，將會在遷移使用者信箱時，對 Microsoft Cloud Deutschland 造成用戶端連線失敗。|


### <a name="exchange-online-hybrid-customers"></a>Exchange Online混合客戶

**適用于：** 使用作用中 Exchange 混合式設定與內部部署 Exchange 伺服器的所有客戶<br>
套用 **時**：第5階段之前的任何時間

Enterprise 具有 Exchange Online 和內部部署 Exchange Server 混合式部署的客戶，請執行混合式設定向導 (HCW) 和 AAD 連線，以維護及建立混合安裝。
Exchange Online混合管理員 **必須執行混合式設定向導 (HCW)** 做為這項轉換的一部分。
從 Microsoft Cloud Deutschland 轉換為 Office 365 德國地區時，系統管理員必須先于「Office 365 德國」模式重新執行 HCW 的最新組建，Exchange 遷移 (階段 5) 開始。 然後，在完成階段5時，在「Office 365 世界」模式中再次執行 HCW，以完成內部部署，並使用 Office 365 德國地區設定。 HCW 執行不能在階段5執行，請務必執行 HCW，直到階段5完成。
目錄屬性會在 Office 365 和 Azure AD 之間以透過 AAD 連線的內部部署進行同步處理。

<br>

**

|步驟 (s) |描述|影響|
|---|---|---|
|使用 Office 365 德國設定重新執行 HCW <p> _您可以在接收到 Office 365 租使用者遷移 (階段 1) 開始的訊息中心通知之後，立即啟動此活動。_|卸載及重新執行 HCW (17.0.5378.0 或以上) 從 <https://aka.ms/hybridwizard> 第5階段開始，可確保您的內部部署設定準備好使用 Microsoft Cloud Deutschland 使用者和遷移至 Office 365 德國地區的使用者來傳送和接收郵件。 <p> 在 HCW 的 [**我的 Office 365 組織** 底下的清單方塊] 中，選取 [ **Office 365 德國]。**|在階段 5 [Exchange 遷移] 開始之前，無法完成這項工作，可能會導致 NDRs 內部部署 Exchange 部署及 Office 365 之間的郵件路由。|
|保留共用信箱設定|有些混合式客戶已使用 Exchange Online 命令將雲端使用者信箱轉換成「共用」信箱。 此雲端信箱設定會寫入至信箱和本機 Exchange Online 目錄，但是它並未透過 AAD 連線同步處理回客戶的 Active directory。 結果是信箱 RemoteRecipientType 及 RemoteDisplayType 值之 Active Directory 表示的差異，以及 Exchange Online 定義為共用信箱。 <p> 客戶負責確定已使用、或將所有共用信箱正確布建 `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` `Set-RemoteMailbox -Shared` 。 請參閱此參考以瞭解如何 [在混合式環境中轉換使用者的信箱](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox)。|無法在階段 5 [Exchange Online 遷移] 之前完成此工作，可能會導致 NDRs 共用信箱，將其轉換回未授權的信箱，並失去受影響信箱的共用存取權。 [在 Exchange 混合式部署中執行目錄同步處理之後，共用信箱會意外轉換為使用者信箱](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)。 Exchange Online 遷移完成之前，不會解決此影響的影響。|


## <a name="skype-for-business-online"></a>商務用 Skype Online

<!-- before phase 7 -->

**適用** 于：商務線上客戶的 Skype<br>
套用 **時**：第7階段之前的任何時間

<br>

****

|步驟 (s) |描述|影響|
|---|---|---|
|為在德國存取商務用 Skype 的使用者部署 Teams 桌面用戶端。|遷移會將商務用 Skype 使用者移至 Microsoft Teams 以進行共同作業、呼叫和交談。 或者，部署 Microsoft Teams 的桌面用戶端，或確定可以使用支援的瀏覽器。|Inaction 將會導致 Microsoft Teams 的共同作業服務無法可用性。|
|複查並準備遷移相關的 DNS 變更。|商務用 Skype Online 之客戶擁有的 DNS 區域變更。|<ul><li>建議您將任何客戶擁有的網域 DNS 記錄的存留時間 (TTL) 更新為5分鐘，以加速 DNS 記錄的更新。 不過，與此 DNS 變更相關聯的 Microsoft 受管理轉換，可能需要在所提供的24小時變更視窗內任何時間進行。</li><li>未來可能會中斷服務。 使用者無法登入商務用 Skype，會重新導向至 Office 365 服務中已遷移的 Teams 體驗。</li></ul>|
|準備使用者和管理的訓練與準備工作，以轉換為 Microsoft Teams。|在您規劃使用者的通訊和準備工作時，從 Skype 轉換為 Teams 會順利。|<ul><li>用戶端必須注意新服務，以及如何在將其服務轉換為 Office 365 服務後使用。</li><li>在對客戶虛名網域和初始網域進行 DNS 變更之後，使用者就會登入商務用 Skype，並看到他們現在已遷移至 Teams。 這也會在背景中下載 Teams 的桌面用戶端。</li></ul>|


## <a name="mobile-device-management"></a>行動裝置管理

<!-- before phase 5 -->
**適用于：** 使用協力廠商行動裝置管理 (MDM) 解決方案的客戶<br>
套用 **時**：第5階段之前的任何時間

<br>

****

|步驟 (s) |描述|適用於|影響|
|---|---|---|---|
|針對 iOS 和 Android，針對使用者移除並重新加入其 Outlook 帳戶的使用者，準備使用者和管理訓練。|在 microsoft Cloud Deutschland 中使用信箱設定的 iOS 和 Android 帳戶的 Microsoft Outlook 可能必須移除並重新加入 Outlook 才能正確地同步處理新的 Office 365 服務設定。|適用于 iOS 和 Android 客戶的 Microsoft Outlook|先前為 Microsoft Cloud Deutschland 設定的信箱可能無法挑選新的 Office 365 服務設定，從而導致其他使用者體驗的錯誤和降級效能。 Outlook IT 系統管理員鼓勵您提供檔，以主動指示使用者移除其帳戶至 Microsoft Outlook iOS 和 Android，如果在遷移之後發生登入或同步處理郵件的問題。|
|決定遷移後是否需要重新配置。|行動裝置管理 (MDM) 解決方案可能會以端點為目標 `outlook.de` 。 在此轉換為 Office 365 服務時，用戶端設定檔應該更新為 Office 365 服務 URL `outlook.office365.com` 。|Exchange Online 和 MDM 客戶|當端點可供存取時，用戶端仍可繼續運作 `outlook.de` ，但如果無法再使用 Microsoft 雲端 Deutschland 端點，使用者將會失敗。|


## <a name="line-of-business-apps"></a>企業營運應用程式

**適用于：** 使用企業營運 (LOB) 應用程式與 Microsoft Cloud Deutschland 提供之端點的客戶<br>
套用 **時**：在階段2完成之後和階段9結束之前

如果您使用的是協力廠商服務或企業營運 (LOB) 與 Office 365 整合的應用程式，則必須解決 Microsoft Cloud Deutschland 實例所提供之端點上的任何相依性問題。 例如，如果您的 LOB 應用程式正在連線 `https://graph.microsoft.de/` ，您必須將端點變更為 `https://graph.microsoft.com/` 。 在第2階段後，您的租使用者便可使用 Microsoft Office 365 泛型服務的端點。

在遷移期間，您的組織是在階段2和階段9之間，您無法將任何協力廠商的多承租人應用程式新增至您的組織 (MTA) 。 當遷移完成階段9時，您可以繼續為您的組織新增或同意 MTA 應用程式。


| 步驟 (s)  | 描述 | 影響 |
|:-------|:-------|:-------|
| 決定遷移後是否需要重新配置。 | 與 Office 365 整合的協力廠商服務和應用程式可能會編碼為預期 Microsoft Cloud Deutschland IP 位址和 URLs。 | 必要的動作。 Inaction 可能會導致服務或用戶端軟體失敗。 |


|步驟 (s) |描述|影響|
|---|---|---|
|決定遷移後是否需要重新配置。|與 Office 365 整合的協力廠商服務和應用程式可能會編碼為預期 Microsoft Cloud Deutschland IP 位址和 URLs。|必要的動作。 Inaction 可能會導致服務或用戶端軟體失敗。|


## <a name="dynamics-365"></a>Dynamics 365

**適用于**：使用 Microsoft Dynamics 365 的客戶

<br>

****

|步驟 (s) |描述|影響|
|---|---|---|
|若為 Dynamics 365 沙箱訂閱，請務必從 Microsoft Cloud Deutschland 中的 dynamics 365 訂閱下載 dynamics SQL 實例的實際執行環境。 在沙箱遷移之前，應將最新的實際備份還原至沙箱。|遷移 Dynamics 365 需要客戶確保沙箱環境以最新的實際執行資料庫重新整理。|FastTrack 小組會協助客戶執行晾乾的執行，以驗證從 8. x 到9.1 的版本升級。|


## <a name="power-bi"></a>Power BI

**適用于**：使用 Power BI 的客戶

<br>

****

|步驟 (s) |描述|影響|
|---|---|---|
|從 Power BI 訂閱中移除不會從 Microsoft Cloud Deutschland Power BI 遷移至 Office 365 服務的物件。|遷移 Power BI 服務會要求客戶採取行動，以刪除特定的專案，例如資料集和儀表板。|管理員可能必須將下列專案從其訂閱中移除： <ul><li>Real-Time 資料集 (例如，流式傳送或推入資料集) </li><li>Power BI 內部部署資料閘道設定和資料來源 </li></ul>|


## <a name="microsoft-azure"></a>Microsoft Azure

如果您在 Microsoft Cloud Deutschland 實例中對 Office 365 和 Microsoft Azure 使用相同的 Azure Active Directory 身分識別分割區，請確定您準備好進行 Microsoft Azure 服務的客戶導向遷移。

> [!NOTE]
> 您的 Microsoft Azure 服務的遷移可能無法在您的 Office 365 租使用者達到遷移階段9之前開始，必須在遷移階段10開始之前完成。

使用 Office 365 和 Azure 資源 (（例如網路、計算和儲存) ）的客戶會執行資源的遷移到 Office 365 服務實例。 這種遷移是客戶的責任。 訊息中心文章會通知開始。 在 Office 365 服務環境中完成 Azure AD 組織之前，必須完成遷移。 如需 Azure 遷移，請參閱 azure 遷移行動手冊（ [Azure 德國遷移指南的概述](/azure/germany/germany-migration-main)）。

<br>

****

|步驟 (s) |描述|影響|
|---|---|---|
|使用您的合作夥伴，判斷哪些 Azure 服務正在使用中，並準備今後從德國遷移至 Office 365 服務租使用者。 遵循 [Azure 遷移行動手冊](/azure/germany/germany-migration-main)中所述的步驟。|<ul><li>遷移 Azure 資源是一項客戶責任，需要在規定的步驟後手動工作。 瞭解組織中所使用的服務是成功遷移 Azure 服務的關鍵。</li><li>Office 365在具有相同身分識別分割區之 Azure 訂閱的德國客戶， (組織) 必須遵循 Microsoft 指定的訂單，當他們可以開始訂閱和服務遷移時。</li></ul>|<ul><li>客戶可能會有多個 Azure 訂閱，每個包含基礎結構、服務和平臺元件的訂閱。</li><li>管理員應識別訂閱和專案關係人，以確保在此遷移事件中，可能會有提示進行遷移和驗證。</li><li>無法順利完成這些訂閱和指定時程表內的 azure 元件遷移，將會影響 Office 和 azure AD 轉換至 Office 365 服務的完成，而且可能會導致資料遺失。</li><li>訊息中心通知會通知用戶端遷移開始的點。</li></ul>|


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

- [從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)
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
