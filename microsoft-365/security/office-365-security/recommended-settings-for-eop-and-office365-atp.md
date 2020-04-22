---
title: Microsoft 對於 EOP 和 Office 365 ATP 安全性設定、建議、寄件者原則架構、網域型郵件報告及符合性的建議、DomainKeys 識別的郵件、步驟、運作方式、安全性基準、EOP 的基準、ATP、setup ATP、設定 EOP、設定 ATP、設定 EOP、安全性設定
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Exchange Online Protection （EOP）和高級威脅防護（ATP）安全性設定的最佳作法為何？ 目前的標準保護建議為何？ 如果您想要更嚴格，應使用哪些專案？ 此外，如果您同時使用高級威脅防護（ATP），您也可以取得哪些額外功能？
ms.openlocfilehash: 9755fccb482dc294da7a0747310776314c739139
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634409"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP 和 Office 365 ATP 安全性的建議設定

**Exchange Online Protection （EOP）** 是 Microsoft 365 訂閱的安全性核心，可協助防止惡意電子郵件到達您員工的收件匣。 不過，每天都會有新的更複雜的攻擊，但通常需要改進的保護。 **Office 365 高級威脅防護（ATP）** ATP Plan 1 或 ATP 方案2包含其他功能，可提供系統管理員更多層的安全性、控制和調查。

雖然我們可讓安全性管理員自訂其安全性設定，但我們建議的 EOP 和 Office 365 ATP 有兩個安全性層級： **Standard**和**Strict**。 每個客戶的環境和需求各不相同，但我們相信這些等級的郵件篩選設定可協助避免不想要的郵件在大多數情況下抵達員工的收件匣。

> [!IMPORTANT]
> 必須在信箱上啟用垃圾郵件規則，篩選才能正常運作。 它預設為啟用，但是如果篩選似乎不在運作中，您應該加以檢查。 如需詳細資訊，請參閱[在 Office 365中設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

本主題說明這些 Microsoft 建議的設定，以協助保護您的使用者。

> [!TIP]
> 您可以下載一個新的 PowerShell 模組，它稱為 Office 365 Advanced 威脅防護建議的設定分析器（ORCA），協助決定這些設定。 當您在租使用者中以系統管理員身分執行時，ORCAReport 將協助產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。 您可以在下列位置https://www.powershellgallery.com/packages/ORCA/下載此模組。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾郵件、反惡意程式碼和反網路釣魚保護

反垃圾郵件、反惡意程式碼和反網路釣魚是可由系統管理員設定的 EOP 功能。 建議採用下列設定。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾郵件原則設定

若要建立及設定反垃圾郵件原則，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

| 安全性功能名稱 | 標準 | 嚴格 | 留言 |
|---|---|---|---|
|**垃圾郵件**偵測動作 <br/><br/> _SpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**高信賴的垃圾郵件**偵測動作 <br/><br/> _HighConfidenceSpamAction_|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**網路釣魚電子郵件**偵測動作 <br/><br/> _PhishSpamAction_|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**高信賴網路釣魚電子郵件**偵測動作 <br/><br/> _HighConfidencePhishAction_|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**大量電子郵件**偵測動作 <br/><br/> _BulkSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|大量電子郵件閾值 <br/><br/> _BulkThreshold_|6 |4 |預設值是目前的7，但建議您將其變更為6。 如需詳細資訊，請參閱[Office 365 中的大量投訴等級（BCL）](bulk-complaint-level-values.md)。|
|隔離保留期間 <br/><br/> _QuarantineRetentionPeriod_|30 天|30 天||
|**安全性秘訣** <br/><br/> _InlineSafetyTipsEnabled_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|允許的寄件者 <br/><br/> _AllowedSenders_|無|無||
|允許的寄件者網域 <br/><br/> _AllowedSenderDomains_|無|無|不需要將您擁有的網域（也稱為「_公認的網域_」）新增至允許的寄件者清單。 實際上，它會被認為是高風險，因為它會為不良的演員帶來機會，以傳送您本來會加以篩選的郵件。在 [**反垃圾郵件設定**] 頁面的 [安全性 & 規範中心] 中，使用[哄騙智慧](learn-about-spoof-intelligence.md)，以查看組織的電子郵件網域中的所有收件者電子郵件地址或外部網域中的欺騙寄件者電子郵件地址。|
|封鎖的寄件者 <br/><br/> _BlockedSenders_|無|無||
|封鎖的寄件者網域 <br/><br/> _BlockedSenderDomains_|無|無||
|**啟用使用者垃圾郵件通知** <br/><br/> _EnableEndUserSpamNotifications_|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`||
|**傳送使用者垃圾郵件通知頻率（天）** <br/><br/> _EndUserSpamNotificationFrequency_|3天|3天||
|**垃圾郵件 ZAP** <br/><br/> _SpamZapEnabled_|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`||
|**網路釣魚 ZAP** <br/><br/> _PhishZapEnabled_|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|開啟|開啟|此設定僅適用于 PowerShell。|

反垃圾郵件原則中有其他幾個高級垃圾郵件篩選器（ASF）設定已被取代。 有關這些功能之折舊時程表的詳細資訊，將在本主題外傳遞。

建議您為**標準**和**嚴格**的層次 **，關閉這些**ASF 設定。 如需 ASF 設定的詳細資訊，請參閱[Office 365 中的高級垃圾郵件篩選器（ASF）設定](advanced-spam-filtering-asf-options.md)。

| 安全性功能名稱 | 註解 |
|----|---|
|**遠端網站的影像連結**（_IncreaseScoreWithImageLinks_）||
|**URL 中的數位 IP 位址**（_IncreaseScoreWithNumericIps_）||
|**UL 重新導向至其他埠**（_IncreaseScoreWithRedirectToOtherPort_）||
|**.Biz 或. 資訊網站的 URL** （_IncreaseScoreWithBizOrInfoUrls_）||
|**空白郵件**（_MarkAsSpamEmptyMessages_）||
|**HTML 中的 JavaScript 或 VBScript** （_MarkAsSpamJavaScriptInHtml_）||
|**HTML 中的框架或 IFrame 標記**（_MarkAsSpamFramesInHtml_）||
|**HTML 中的物件標記**（_MarkAsSpamObjectTagsInHtml_）||
|**在 HTML 中嵌入標記**（_MarkAsSpamEmbedTagsInHtml_）||
|HTML （_MarkAsSpamFormTagsInHtml_）**中的表單標記**||
|**HTML 中的 Web 臭蟲**（_MarkAsSpamWebBugsInHtml_）||
|套用**敏感字清單**（_MarkAsSpamSensitiveWordList_）||
|**SPF 記錄： hard fail** （_MarkAsSpamSpfRecordHardFail_）||
|**條件式寄件者識別碼篩選： hard fail** （_MarkAsSpamFromAddressAuthFail_）||
|**NDR 退信攻擊**（_MarkAsSpamNdrBackscatter_）||

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 輸出垃圾郵件原則設定

若要建立及設定輸出垃圾郵件原則，請參閱[在 Office 365 中設定輸出垃圾郵件篩選](configure-the-outbound-spam-policy.md)。

| 安全性功能名稱 | 標準 | 嚴格 | 留言 |
|---|---|---|---|
|**每位使用者的收件者數目上限：外部每小時限制** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**每位使用者的收件者數目上限：每小時內部的限制** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**每位使用者的收件者數目上限：每日限制** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**使用者超過限制時的動作** <br/><br/> _ActionWhenThresholdReached_|**限制使用者傳送郵件** <br/><br/> `BlockUser`|**限制使用者傳送郵件** <br/><br/> `BlockUser`||

### <a name="eop-anti-malware-policy-settings"></a>EOP 反惡意程式碼原則設定

若要建立及設定反惡意程式碼原則，請參閱[在 Office 365 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

| 安全性功能名稱 | 標準 | 嚴格 | 留言 |
|---|---|---|---|
|**您是否要在郵件被隔離時通知收件者？** <br/><br/> _動作_|否 <br/><br/> _DeleteMessage_|否 <br/><br/> _DeleteMessage_|如果電子郵件附件中偵測到惡意程式碼，則會隔離郵件，而且只能由系統管理員加以發行。|
|**常見附件類型篩選** <br/><br/> _EnableFileFilter_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|此設定會隔離包含以檔案類型為基礎的可執行附件的郵件，不論附件內容為何。|
|**惡意程式碼零小時自動清除** <br/><br/> _ZapEnabled_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|通知未傳遞郵件的**內部寄件者** <br/><br/> _EnableInternalSenderNotifications_|停用 <br/><br/> `$false`|停用 <br/><br/> `$false`||
|通知未傳遞郵件的**外部寄件者** <br/><br/> _EnableExternalSenderNotifications_|停用 <br/><br/> `$false`|停用 <br/><br/> `$false`||

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 預設的反網路釣魚原則設定

您只能在 Office 365 組織中使用 Exchange Online 信箱來設定這些設定。 若要設定這些設定，請參閱[在 EOP 中設定預設的反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

| 安全性功能名稱 | 標準 | 嚴格 | 留言 |
|---|---|---|---|
|**啟用反欺騙保護** <br/><br/> _EnableAntispoofEnforcement_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用未經驗證的寄件者** <br/><br/> _EnableUnauthenticatedSender_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|將問號（？）新增至 Outlook 中的寄件者相片，以取得未識別的欺騙寄件者。 如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md)。|
|**如果電子郵件是由不允許哄騙您網域的人所傳送** <br/><br/> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件** <br/><br/> `Quarantine`|這適用于[哄騙情報](learn-about-spoof-intelligence.md)中已封鎖的寄件者。|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 高級威脅防護安全性

其他的安全性好處來自 Office 365 高級威脅防護（ATP）訂閱。 如需最新的新聞和資訊，您可以查看[Office 365 ATP 的新功能](whats-new-in-office-365-atp.md)。

Office 365 ATP 包含安全附件和安全連結原則，可防止電子郵件遭受潛在惡意附件的傳遞，並防止使用者按一下潛在的不安全 URLs。

> [!IMPORTANT]
> 高級反網路釣魚是 Office 365 ATP 訂閱的其中一個優點。 雖然預設會啟用它，但您***必須***先設定至少一個反網路釣魚原則，才能開始篩選郵件。 忘記設定反網路釣魚原則可能會將使用者暴露于危險的電子郵件。 在您新增 Office 365 ATP 訂閱後，請務必設定您的反網路釣魚原則。

如果您已將 Office 365 ATP 訂閱新增至您的 EOP，請設定下列設定。

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP 反網路釣魚原則設定

EOP 客戶如先前所述，取得基本的反網路釣魚，但是 Office 365 ATP 包含更多的功能和控制，可協助防範、偵測和修正攻擊。 若要建立及設定這些原則，請參閱[在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

|類比安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|（編輯類比原則）新增要保護的使用者|開啟|開啟|取決於您的組織，但建議您在重要角色中新增使用者。 在內部，這些可能是您 CEO、CFO 和其他資深領導人。 您可以在外部加入委員會成員或董事會。|
|（編輯類比原則）自動包含我擁有的網域|開啟|開啟||
|（編輯類比原則）包含自訂網域|開啟|開啟|取決於您的組織，但建議您新增您不擁有的網域。|
|如果您指定的模仿使用者傳送電子郵件|隔離郵件|隔離郵件||
|如果您指定的模仿網域傳送電子郵件|隔離郵件|隔離郵件||
|顯示類比使用者的秘訣|開啟|開啟||
|顯示類比網域的秘訣|開啟|開啟||
|顯示不尋常字元的秘訣|開啟|開啟||
|啟用信箱智慧|開啟|開啟||
|啟用信箱智慧型類比保護|開啟|開啟||
|如果由信箱智慧保護的類比使用者傳送電子郵件|將郵件移至收件者的 [垃圾郵件] 資料夾|隔離郵件||
|（編輯類比原則）新增信任的寄件者和網域|無|無|取決於您的組織，但建議您新增不正確地將其標記為網路釣魚網路的使用者或網域，因為它只會類比而非其他篩選器。|

|欺騙安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|啟用反欺騙保護|開啟|開啟||
|啟用未經驗證的寄件者（標記）|開啟|開啟||
|如果電子郵件是由不允許哄騙您網域的人所傳送|將郵件移至收件者的 [垃圾郵件] 資料夾|隔離郵件||

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的類比設定

| 安全性功能名稱 | 標準 | 嚴格 | 留言 |
|---|---|---|---|
|受保護的使用者：**新增要保護的使用者** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|開啟 <br/><br/> `$true` <br/><br/> \<使用者清單\>|開啟 <br/><br/> `$true` <br/><br/> \<使用者清單\>|取決於您的組織，但建議您在重要角色中新增使用者。 在內部，這些可能是您 CEO、CFO 和其他資深領導人。 您可以在外部加入委員會成員或董事會。|
|受保護的網域：**自動包含我擁有的網域** <br/><br/> _EnableOrganizationDomainsProtection_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|受保護的網域：**包括自訂網域** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|開啟 <br/><br/> `$true` <br/><br/> \<網域清單\>|開啟 <br/><br/> `$true` <br/><br/> \<網域清單\>|取決於您的組織，但建議您新增您經常與其互動的網域。|
|受保護的使用者：**如果模仿的使用者傳送電子郵件** <br/><br/> _TargetedUserProtectionAction_|**隔離郵件** <br/><br/> `Quarantine`|**隔離郵件** <br/><br/> `Quarantine`||
|受保護的網域：**如果類比網域傳送電子郵件** <br/><br/> _TargetedUserProtectionAction_|**隔離郵件** <br/><br/> `Quarantine`|**隔離郵件** <br/><br/> `Quarantine`||
|**顯示類比使用者的秘訣** <br/><br/> _EnableSimilarUsersSafetyTips_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**顯示類比網域的秘訣** <br/><br/> _EnableSimilarDomainsSafetyTips_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**顯示不尋常字元的秘訣** <br/><br/> _EnableUnusualCharactersSafetyTips_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用信箱智慧？** <br/><br/> _EnableMailboxIntelligence_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用信箱智慧型類比保護？** <br/><br/> _EnableMailboxIntelligenceProtection_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**如果由信箱智慧保護的類比使用者傳送電子郵件** <br/><br/> _MailboxIntelligenceProtectionAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件** <br/><br/> `Quarantine`||
|**受信任的寄件者** <br/><br/> _ExcludedSenders_|無|無|視您的組織而定，我們建議新增因模擬而不正確地標示為網路釣魚網路的使用者，而不是其他篩選器。|
|**信任的網域** <br/><br/> _ExcludedDomains_|無|無|視您的組織而定，我們建議新增因模擬而不正確地標示為網路釣魚網路的網域，而不是其他篩選器。|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的欺騙設定

請注意，這些是[EOP 中的反垃圾郵件原則設定](#eop-anti-spam-policy-settings)中所提供的相同設定。

| 安全性功能名稱 | 標準 | 嚴格 | 留言 |
|---|---|---|---|
|**啟用反欺騙保護** <br/><br/> _EnableAntispoofEnforcement_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用未經驗證的寄件者** <br/><br/> _EnableUnauthenticatedSender_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|將問號（？）新增至 Outlook 中的寄件者相片，以取得未識別的欺騙寄件者。 如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md)。|
|**如果電子郵件是由不允許哄騙您網域的人所傳送** <br/><br/> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件** <br/><br/> `Quarantine`|這適用于[哄騙情報](learn-about-spoof-intelligence.md)中已封鎖的寄件者。|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的高級設定

| 安全性功能名稱 | 標準 | 嚴格 | 留言 |
|---|---|---|---|
|**高級網路釣魚臨界值** <br/><br/> _PhishThresholdLevel_|**2-嚴格** <br/><br/> `2`|**3-更嚴格** <br/><br/> `3`||

### <a name="safe-links-settings"></a>安全連結設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|在 Office 365 應用程式中使用 ATP 安全連結，Office for iOS 和 Android|已啟用|已啟用|這屬於適用于整個組織的 ATP 安全連結原則|
使用者按一下安全連結時請勿追蹤|停用|停用|這適用于適用于整個組織的原則，以及適用于特定收件者的任何原則|
|不要讓使用者點擊至原始 URL 的安全連結|已啟用|已啟用|這適用于適用于整個組織的原則，以及適用于特定收件者的任何原則|
|郵件中未知可能惡意 URLs 的動作|開啟|開啟||
|針對可疑的連結和指向檔案的連結套用即時 URL 掃描|已啟用|已啟用||
|等待 URL 掃描完成再傳遞郵件|已啟用|已啟用||
|對組織內傳送的電子郵件套用安全連結|已啟用|已啟用||

### <a name="safe-attachments"></a>安全附件

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP|已啟用|已啟用||
|ATP 安全附件未知的惡意程式碼回應|封鎖|封鎖||
|在偵測時重新導向附件|已啟用|已啟用|重新導向安全系統管理員的電子郵件地址，以瞭解如何判斷附件是否為惡意程式碼|
|當惡意程式碼掃描附件超時或發生錯誤時，ATP 安全附件回應|已啟用|已啟用||

## <a name="related-topics"></a>相關主題

- 您在尋找**Exchange 郵件流程/Exchange 傳輸規則**的最佳作法嗎？ 如需詳細資訊，請參閱[本文](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop)。

- 系統管理員和使用者可以將誤報（良好的電子郵件標記為壞）和誤報（允許的錯誤電子郵件）提交給 Microsoft 進行分析。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

- 使用下列連結可取得如何設定[EOP 服務](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)的**資訊，以及****設定** [Office 365 的高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)。 （請不要忘記「防禦[Office 365 中的威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」中有説明的指示。）

- 在這裡，您可以在[此處](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)找到 GPO/內部部署選項的安全性基準，並在[這裡](https://docs.microsoft.com/intune/protect/security-baselines)找到 Intune 型安全性的**安全性基準**。 最後，您可以在[這裡](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)找到 Microsoft Defender 高級威脅防護（ATP）與 Windows Intune 安全性基準之間的比較。
