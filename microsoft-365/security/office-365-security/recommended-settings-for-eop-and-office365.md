---
title: EOP 和 Defender Office 365 安全性設定的 Microsoft 建議
keywords: Office 365 的安全性建議、寄件者原則架構、網域型郵件報告及符合性、DomainKeys 識別的郵件、步驟、運作方式、安全性基準、EOP 的基準、Office 365 的 Office 365 EOP、Office 365 設定 EOP、設定、設定、設定、設定、設定、安全性設定
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Exchange Online Protection (EOP) 和 Defender Office 365 安全性設定的最佳作法為何？ 目前的標準保護建議為何？ 如果您想要更嚴格，應使用哪些專案？ 此外，如果您同時使用 Office 365 的 Defender，您也會取得什麼額外內容？
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f00e1e2356839e70acafb0f98a5424a1311082e7
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793217"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>EOP 和 Microsoft Defender Office 365 security 的建議設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** 是 Microsoft 365 訂閱的安全性核心，可協助防止惡意電子郵件到達您員工的收件匣。 不過，每天都會有新的更複雜的攻擊，但通常需要改進的保護。 **Microsoft Defender Office 365** 方案1或計畫2包含其他可讓系統管理員更深入的安全性、控制和調查的功能。

雖然我們可讓安全性管理員自訂其安全性設定，但在 EOP 和 Microsoft Defender 中有兩個安全性層級，我們建議的 Office 365： **Standard** 和 **Strict**。 每個客戶的環境和需求各不相同，但我們相信這些階層的篩選將有助於防止不想要的郵件在大多數情況下抵達員工的收件匣。

若要自動將標準或嚴格設定套用至使用者，請參閱[EOP 和 Microsoft Defender for Office 365 中的預先設定安全性原則](preset-security-policies.md)。

> [!NOTE]
> 信箱必須啟用垃圾郵件規則，篩選才能正確運作。 它預設為啟用，但是如果篩選似乎不在運作中，您應該加以檢查。 如需詳細資訊，請參閱[設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

本文說明預設設定，也是建議的標準和嚴格設定，以協助保護您的使用者。 這些表格包含 Microsoft 365 security center 中的設定，以及 PowerShell (Exchange Online PowerShell 或獨立 Exchange Online Protection，但沒有 PowerShell 信箱的組織 Exchange Online。

> [!TIP]
> Office 365 的高級威脅防護建議的設定分析器 (ORCA) 模組 PowerShell 可協助您 (系統管理員) 找到這些設定的目前值。 具體說來， **ORCAReport** Cmdlet 會產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。 您可以在中下載 ORCA 模組 <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾郵件、反惡意程式碼和反網路釣魚保護

反垃圾郵件、反惡意程式碼和反網路釣魚都是可由系統管理員設定的 EOP 功能。 建議您遵循下列標準或嚴格設定。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾郵件原則設定

若要建立及設定反垃圾郵件原則，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**垃圾郵件** 偵測動作 <p> _SpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**高信賴的垃圾郵件** 偵測動作 <p> _HighConfidenceSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**網路釣魚** 偵測動作 <p> _PhishSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**高信賴網路釣魚** 偵測動作 <p> _HighConfidencePhishAction_|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**大量** 偵測動作 <p> _BulkSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**大量電子郵件閾值** <p> _BulkThreshold_|7 |6 |4 |如需詳細資訊，請參閱 [EOP 中的大量投訴層級 (BCL) ](bulk-complaint-level-values.md)。|
|_MarkAsSpamBulkMail_|開啟|開啟|開啟|此設定僅適用于 PowerShell。|
|**保留這數天內的垃圾郵件** <p> _QuarantineRetentionPeriod_|15 天|30 天|30 天||
|**啟用垃圾郵件安全提示** <p> _InlineSafetyTipsEnabled_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`||
|允許的寄件者 <p> _AllowedSenders_|無|無|無||
|允許的寄件者網域 <p> _AllowedSenderDomains_|無|無|無|將網域新增至允許的寄件者清單是一種非常壞的主意。 攻擊者可以傳送您本來會加以篩選的電子郵件。 <p> 使用 [ [偽造智慧真知灼見](learn-about-spoof-intelligence.md) ] 和 [ [承租人允許/封鎖] 清單](tenant-allow-block-list.md) ，以查看組織的電子郵件網域中的所有收件者電子郵件地址或外部網域中的欺騙寄件者電子郵件地址中的所有寄件者。|
|封鎖的寄件者 <p> _BlockedSenders_|無|無|無||
|封鎖的寄件者網域 <p> _BlockedSenderDomains_|無|無|無||
|**啟用使用者垃圾郵件通知** <p> _EnableEndUserSpamNotifications_|已停用 <p> `$false`|已啟用 <p> `$true`|已啟用 <p> `$true`||
|**每 (天傳送一次使用者垃圾郵件通知)** <p> _EndUserSpamNotificationFrequency_|3天|3天|3天||
|為網路釣魚郵件啟用零小時自動清除 (ZAP)  <p> _PhishZapEnabled_|已啟用 <p> `$true`|已啟用 <p> `$true`|已啟用 <p> `$true`||
|啟用用於垃圾郵件的 ZAP <p> _SpamZapEnabled_|已啟用 <p> `$true`|已啟用 <p> `$true`|已啟用 <p> `$true`||
|

在反垃圾郵件原則中，有許多高級垃圾郵件篩選 (ASF) 設定不會被取代。 有關這些功能之折舊時程表的詳細資訊，將在本文之外進行傳遞。

建議 **您為****標準** 和 **嚴格** 的層級保留下列 ASF 設定。 如需有關 ASF 設定的詳細資訊，請參閱 [EOP 中的高級垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)。

<br>

****

|安全性功能名稱|Comment|
|---|---|
| (_IncreaseScoreWithImageLinks_) **的遠端網站影像連結**||
|URL (_IncreaseScoreWithNumericIps_ **中的數位 IP 位址**) ||
|**URL 重新導向到其他埠** (_IncreaseScoreWithRedirectToOtherPort_) ||
|**.Biz 或. info 網站的連結** (_IncreaseScoreWithBizOrInfoUrls_) ||
|**空郵件** (_MarkAsSpamEmptyMessages_) ||
|**在 HTML (MarkAsSpamEmbedTagsInHtml 中嵌入標記**) ||
|**在 HTML (MarkAsSpamJavaScriptInHtml 中 JavaScript 或 VBScript**) ||
|HTML (_MarkAsSpamFormTagsInHtml_ **中的表單標記**) ||
|HTML (_MarkAsSpamFramesInHtml_ **中的 Frame 或 iframe 標記**) ||
|HTML (_MarkAsSpamWebBugsInHtml_ **中的 Web 臭蟲**) ||
|HTML (_MarkAsSpamObjectTagsInHtml_ **中的物件標記**) ||
| (_MarkAsSpamSensitiveWordList_ 的 **機密字**) ||
|**SPF 記錄： hard fail** (_MarkAsSpamSpfRecordHardFail_) ||
|**寄件者識別碼篩選硬性失敗** (_MarkAsSpamFromAddressAuthFail_) ||
|**退信攻擊** (_MarkAsSpamNdrBackscatter_) ||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 輸出垃圾郵件原則設定

若要建立及設定輸出垃圾郵件原則，請參閱 [在 EOP 中設定輸出垃圾郵件篩選](configure-the-outbound-spam-policy.md)。

如需服務中預設傳送限制的詳細資訊，請參閱傳送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**設定外部郵件限制** <p> _RecipientLimitExternalPerHour_|0|500|400|預設值0表示使用服務預設值。|
|**設定內部郵件限制** <p> _RecipientLimitInternalPerHour_|0|1000|800|預設值0表示使用服務預設值。|
|**設定每日郵件限制** <p> _RecipientLimitPerDay_|0|1000|800|預設值0表示使用服務預設值。|
|**對達到郵件限制的使用者施加限制** <p> _ActionWhenThresholdReached_|**限制使用者在下一天前傳送郵件** <p> `BlockUserForToday`|**限制使用者傳送郵件** <p> `BlockUser`|**限制使用者傳送郵件** <p> `BlockUser`||
|**自動轉送規則** <p> _AutoForwardingMode_|**自動系統控制** <p> `Automatic`|**自動系統控制** <p> `Automatic`|**自動系統控制** <p> `Automatic`|
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反惡意程式碼原則設定

若要建立及設定反惡意程式碼原則，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**將郵件隔離為惡意程式碼時通知收件者** <p> _Action_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|否 <p> _DeleteMessage_|如果電子郵件附件中偵測到惡意程式碼，則會隔離郵件，而且只能由系統管理員加以發行。|
|**啟用常見附件篩選器** <p> _EnableFileFilter_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`|此設定會隔離包含以檔案類型為基礎的可執行附件的郵件，不論附件內容為何。|
|**為惡意程式碼啟用零小時自動清除** <p> _ZapEnabled_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`||
|**將郵件隔離為惡意程式碼時通知內部寄件者** <p> _EnableInternalSenderNotifications_|已停用 <p> `$false`|已停用 <p> `$false`|已停用 <p> `$false`||
|**將郵件隔離為惡意程式碼時通知外部寄件者** <p> _EnableExternalSenderNotifications_|已停用 <p> `$false`|已停用 <p> `$false`|已停用 <p> `$false`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP 反網路釣魚原則設定

如需這些設定的詳細資訊，請參閱 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。 若要設定這些設定，請參閱 [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**啟用欺騙情報** <p> _EnableSpoofIntelligence_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`||
|**如果偵測到電子郵件為欺騙** <p> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件** <p> `Quarantine`|此設定適用于已自動封鎖的欺騙寄件者，如在「[租使用者允許/封鎖」清單](tenant-allow-block-list.md)中的[欺騙智慧真知灼見](learn-about-spoof-intelligence.md)或手動封鎖中所示。|
|**顯示未驗證寄件者取得 (？ ) 以取得欺騙** <p> _EnableUnauthenticatedSender_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`|在 Outlook 中為未識別的欺騙寄件者新增問號 (？ ) 到寄件者的相片。 如需詳細資訊，請參閱[防網路釣魚原則中的詐騙](set-up-anti-phishing-policies.md)。|
|**顯示 "via" 標記** <p> _EnableViaTag_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`|透過 chris@contoso.com 透過 fabrikam.com) 的 [寄件者] **或 [寄件者位址]** 中的網域，將透過 (標記新增至 [寄件者] 位址。 <p> 如果您無法使用此設定，則會使用 [  **顯示 (？ ) 針對組織中未驗證的寄件者進行欺騙** 設定）來控制此設定。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender Office 365 安全性

其他的安全性好處是 Microsoft Defender 的 Office 365 訂閱。 如需最新的新聞和資訊，您可以查看[Office 365 的 Defender 新增功能](whats-new-in-defender-for-office-365.md)。

> [!IMPORTANT]
>
> - Office 365 的 Microsoft Defender 中的預設反網路釣魚原則為所有收件者提供[欺騙保護](set-up-anti-phishing-policies.md#spoof-settings)和信箱智慧。 不過，預設原則中並未設定或啟用其他可用的模擬 [保護](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高級設定](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。 若要啟用所有保護功能，請修改預設的反網路釣魚原則，或建立其他的反網路釣魚原則。
>
> - 沒有預設的安全連結原則或安全附件原則，可自動保護組織中的所有收件者。 若要取得保護，您必須建立至少一個安全連結原則及安全附件原則。
>
> - [SharePoint、OneDrive 和 Microsoft Teams](mdo-for-spo-odb-and-teams.md)保護和[安全檔](safe-docs.md)保護的安全附件，不會對安全連結原則產生任何依賴性。

如果您的訂閱包含用於 Office 365 的 Microsoft defender，或您已購買 Office 365 做為附加元件的 defender，請設定下列標準或嚴格設定。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則設定

EOP 客戶會如先前所述，取得基本的反網路釣魚，但 Office 365 的 Microsoft Defender 包含更多的功能和控制，可協助防範、偵測和修正攻擊。 若要建立及設定這些原則，請參閱[在 Office 365 中設定 Defender 的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的模擬設定

如需這些設定的詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的模仿設定 Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要設定這些設定，請參閱[在 Office 365 中設定 Defender 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|受保護的使用者 (寄件者) ： **讓使用者能夠加以保護** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|關閉 <p> `$false` <p> 無|開啟 <p> `$true` <p> \<list of users\>|開啟 <p> `$true` <p> \<list of users\>|根據您的組織，建議您將使用者新增 (郵件寄件者) 在重要角色中。 在內部，受保護的寄件者可能是 CEO、CFO 及其他資深領導人。 外部、受保護的寄件者可以包含理事會成員或董事會的董事。|
|受保護的使用者： **如果偵測到郵件為模仿的使用者** <p> _TargetedUserProtectionAction_|**不要套用任何動作** <p> `NoAction`|**隔離郵件** <p> `Quarantine`|**隔離郵件** <p> `Quarantine`||
|受保護的網域： **包括我擁有的網域** <p> _EnableOrganizationDomainsProtection_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|受保護的網域： **包括自訂網域** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|關閉 <p> `$false` <p> 無|開啟 <p> `$true` <p> \<list of domains\>|開啟 <p> `$true` <p> \<list of domains\>|根據您的組織，建議您將網域新增 (寄件者網域) ，但經常與您互動。|
|受保護的網域： **如果偵測到郵件為類比網域** <p> _TargetedDomainProtectionAction_|**不要套用任何動作** <p> `NoAction`|**隔離郵件** <p> `Quarantine`|**隔離郵件** <p> `Quarantine`||
|**新增受信任的寄件者與網域** <p> _ExcludedSenders_ <p> _ExcludedDomains_|無|無|無|根據您的組織，我們建議新增錯誤辨識為類比嘗試的寄件者或網域。|
|**啟用信箱智慧** <p> _EnableMailboxIntelligence_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`||
|**啟用智慧以進行類比保護** <p> _EnableMailboxIntelligenceProtection_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`|此設定允許透過信箱智慧進行類比偵測的指定動作。|
|**如果信箱智慧偵測和模仿使用者** <p> _MailboxIntelligenceProtectionAction_|**不要套用任何動作** <p> `NoAction`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件** <p> `Quarantine`||
|**顯示使用者模擬安全提示** <p> _EnableSimilarUsersSafetyTips_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**顯示網域模擬安全提示** <p> _EnableSimilarDomainsSafetyTips_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**顯示使用者模擬不尋常的字元安全提示** <p> _EnableUnusualCharactersSafetyTips_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的欺騙設定

請注意，這些是 [EOP 中的反垃圾郵件原則設定](#eop-anti-spam-policy-settings)中所提供的相同設定。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**啟用欺騙情報** <p> _EnableSpoofIntelligence_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`||
|**如果偵測到電子郵件為欺騙** <p> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件** <p> `Quarantine`|此設定適用于已自動封鎖的欺騙寄件者，如在「[租使用者允許/封鎖」清單](tenant-allow-block-list.md)中的[欺騙智慧真知灼見](learn-about-spoof-intelligence.md)或手動封鎖中所示。|
|**顯示未驗證寄件者取得 (？ ) 以取得欺騙** <p> _EnableUnauthenticatedSender_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`|在 Outlook 中為未識別的欺騙寄件者新增問號 (？ ) 到寄件者的相片。 如需詳細資訊，請參閱[防網路釣魚原則中的詐騙](set-up-anti-phishing-policies.md)。|
|**顯示 "via" 標記** <p> _EnableViaTag_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`|透過 chris@contoso.com 透過 fabrikam.com) 的 [寄件者] **或 [寄件者位址]** 中的網域，將透過 (標記新增至 [寄件者] 位址。 <p> 如果您無法使用此設定，則會使用 [  **顯示 (？ ) 針對組織中未驗證的寄件者進行欺騙** 設定）來控制此設定。|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的高級設定

如需此設定的詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的高級網路釣魚閥值 Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要設定此設定，請參閱[設定 Office 365 的 Defender 中的反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**網路釣魚電子郵件閾值** <p> _PhishThresholdLevel_|**1-標準** <p> `1`|**2-嚴格** <p> `2`|**3-更嚴格** <p> `3`||
|

### <a name="safe-links-settings"></a>安全連結設定

Office 365 的 Defender 中的安全連結包含全域設定，這些設定適用于包含在使用中安全連結原則中的所有使用者，以及每個安全連結原則特有的設定。 如需詳細資訊，請參閱[Office 365 的 Defender 安全連結](safe-links.md)。

#### <a name="global-settings-for-safe-links"></a>安全連結的通用設定

若要設定這些設定，請參閱[設定 Office 365 的 Defender 中安全連結的通用設定](configure-global-settings-for-safe-links.md)。

在 PowerShell 中，您可以使用這些 [設定的 AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) Cmdlet。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**使用下列專案中的安全連結： Office 365 應用程式** <p> _EnableSafeLinksForO365Clients_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`|在支援的 Office 365 桌面和行動 (iOS 和 Android) 應用程式中使用安全連結。 如需詳細資訊，請參閱[Office 365 應用程式的安全連結設定](safe-links.md#safe-links-settings-for-office-365-apps)。|
|**當使用者在 Office 365 應用程式中按一下受保護的連結時，請勿追蹤** <p> _TrackClicks_|開啟 <p> `$false`|關閉 <p> `$true`|關閉 <p> `$true`|關閉此設定 (將 _TrackClicks_ 設定為 `$true`) 追蹤使用者在支援 Office 365 應用程式中的按一下。|
|**請勿讓使用者在 Office 365 應用程式中，按原始 URL。** <p> _AllowClickThrough_|開啟 <p> `$false`|開啟 <p> `$false`|開啟 <p> `$false`|開啟此設定 (將 _AllowClickThrough_ 設定為 `$false`) ，可防止在支援的 Office 365 應用程式中，依序按一下至原始 URL。|
|

#### <a name="safe-links-policy-settings"></a>安全連結原則設定

若要設定這些設定，請參閱[在 Microsoft Defender 中為 Office 365 設定安全連結原則](set-up-safe-links-policies.md)。

在 PowerShell 中，您可以使用這些設定的 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) 和 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) Cmdlet。

> [!NOTE]
> 如先前所述，沒有預設的安全連結原則。 [預設] 欄中的值是您建立的新安全連結原則中的預設值。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**選取郵件中未知可能惡意 URLs 的動作** <p> _IsEnabled_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**選取 Microsoft Teams 內未知或可能惡意的 URLs 的動作** <p> _EnableSafeLinksForTeams_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**針對可疑的連結和指向檔案的連結套用即時 URL 掃描** <p> _ScanUrls_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**等待 URL 掃描完成再傳遞郵件** <p> _DeliverMessageAfterScan_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**對組織內傳送的電子郵件套用安全連結** <p> _EnableForInternalSenders_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**不要追蹤使用者點選** <p> _DoNotTrackUserClicks_|關閉 <p> `$false`|關閉 <p> `$false`|關閉 <p> `$false`|關閉此設定 (將 _DoNotTrackUserClicks_ 設定為 `$false`) 追蹤使用者按一下。|
|**不允許使用者點選原始 URL** <p> _DoNotAllowClickThrough_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`|開啟此設定 (將 _DoNotAllowClickThrough_ 設定為 `$true`) ，可防止依序按一下原始 URL。|
|

### <a name="safe-attachments-settings"></a>安全附件設定

Microsoft Defender for Office 365 中的安全附件包括與安全附件原則無關聯的全域設定，以及每個安全連結原則特有的設定。 如需詳細資訊，請參閱[Office 365 的 Defender 安全附件](safe-attachments.md)。

#### <a name="global-settings-for-safe-attachments"></a>安全附件的通用設定

若要設定這些設定，請參閱開啟[Microsoft 365 E5 中](safe-docs.md) [SharePoint、OneDrive 及 Microsoft Teams 和安全檔的安全附件](turn-on-mdo-for-spo-odb-and-teams.md)。

在 PowerShell 中，您可以使用這些 [設定的 AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) Cmdlet。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**針對 SharePoint、OneDrive 和 Microsoft Teams 開啟適用於 Office 365 的 Defender** <p> _EnableATPForSPOTeamsODB_|開啟 <p> `$true`|開啟 <p> `$true`||
|**開啟 Office 用戶端的安全檔** <p> _EnableSafeDocs_|開啟 <p> `$true`|開啟 <p> `$true`|此設定僅可用於 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權。 如需詳細資訊，請參閱[適用于 Microsoft Defender 的安全檔 Office 365](safe-docs.md)。|
|**即使安全檔識別為惡意檔案，也允許人員按一下受保護的檢視** <p> _AllowSafeDocsOpen_|關閉 <p> `$false`|關閉 <p> `$false`|此設定與安全檔相關。|
|

#### <a name="safe-attachments-policy-settings"></a>安全附件原則設定

若要設定這些設定，請參閱[設定 Office 365 的 Defender 中的安全附件原則](set-up-safe-attachments-policies.md)。

在 PowerShell 中，您可以使用這些設定的 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) 和 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) Cmdlet。

> [!NOTE]
> 如先前所述，沒有預設的安全附件原則。 [預設] 欄中的值是您建立的新安全附件原則中的預設值。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|Comment|
|---|:---:|:---:|:---:|---|
|**安全附件未知的惡意程式碼回應** <p> _Action_|封鎖 <p> `Block`|封鎖 <p> `Block`|封鎖 <p> `Block`||
|**偵測時重新導向附件** ： **啟用重新導向** <p> _Redirect_ <p> _RedirectAddress_|Off，但沒有指定電子郵件地址。 <p> `$true` <p> 無|，然後指定電子郵件地址。 <p> `$true` <p> 電子郵件地址|，然後指定電子郵件地址。 <p> `$true` <p> 電子郵件地址|將郵件重新導向至安全性管理員以進行審閱。|
|**如果惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍。** <p> _ActionOnError_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`||
|

## <a name="related-articles"></a>相關文章

- 您在尋找 **Exchange 郵件流程規則 (也稱為 transport rules**) 的最佳作法？ 請參閱[在 Exchange Online 中設定郵件流程規則的最佳作法](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 系統管理員和使用者可以提交誤報 (已標示為錯誤) 和漏報的錯誤電子郵件， (錯誤的電子郵件) Microsoft 進行分析。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

- 若要瞭解如何 **設定** [EOP 服務](/exchange/standalone-eop/set-up-your-eop-service)的相關資訊，請使用下列連結 **，並為** [Office 365 設定 Microsoft Defender](defender-for-office-365.md)。 請不要忘記「[防範 Office 365 中威脅](protect-against-threats.md)的有用指示。

- 您可以在以下位置找到 **Windows 的安全性基準**：[何處可以取得安全性基準？](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)針對 GPO/內部部署選項，以及 [使用安全性基線，設定 intune 中 Windows 10 裝置](/intune/protect/security-baselines)以供 intune 使用的安全性。 最後，在[比較 microsoft defender for endpoint 和 Windows Intune 安全性基準](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)時，可使用 microsoft defender for endpoint 和 Microsoft Intune 安全性基準之間的比較。
