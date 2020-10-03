---
title: Microsoft 對於 EOP 和 Office 365 ATP 安全性設定、建議、寄件者原則架構、網域型郵件報告及符合性的建議、DomainKeys 識別的郵件、步驟、運作方式、安全性基準、EOP 的基準，以及 ATP 的基準，設定 ATP，設定 EOP，設定 ATP，設定 EOP，安全性設定
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Exchange Online Protection (EOP) 和高級威脅防護 (ATP) 安全性設定的最佳作法為何？ 目前的標準保護建議為何？ 如果您想要更嚴格，應使用哪些專案？ 此外，如果您同時使用高級威脅防護 (ATP) ，您也會得到哪些額外功能？
ms.openlocfilehash: af0e295b9b9ed7e71747556909cb181aa5af4833
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350804"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP 和 Office 365 ATP 安全性的建議設定

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP) ** 是 Microsoft 365 訂閱的安全性核心，可協助阻止惡意電子郵件到達您員工的收件匣。 不過，每天都會有新的更複雜的攻擊，但通常需要改進的保護。 **Office 365 高級威脅防護 (ATP) ** ATP Plan 1 或 ATP 方案2包含其他功能，可提供系統管理員更多層的安全性、控制和調查。

雖然我們可讓安全性管理員自訂其安全性設定，但我們建議的 EOP 和 Office 365 ATP 有兩個安全性層級： **Standard** 和 **Strict**。 每個客戶的環境和需求各不相同，但我們相信這些階層的篩選將有助於防止不想要的郵件在大多數情況下抵達員工的收件匣。

若要自動將標準或嚴格設定套用至使用者，請參閱 [EOP 和 Office 365 ATP 中的預先設定安全性原則](preset-security-policies.md)。

**附注**：必須在信箱上啟用垃圾郵件規則，篩選才能正常運作。 它預設為啟用，但是如果篩選似乎不在運作中，您應該加以檢查。 如需詳細資訊，請參閱[在 Office 365中設定 Exchange Online 信箱的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。

本文說明預設設定，也是建議的標準和嚴格設定，以協助保護您的使用者。

> [!TIP]
> Office 365 Advanced 威脅防護建議的設定分析器 (ORCA) 模組 PowerShell 可協助您 (系統管理員) 找到這些設定的目前值。 具體說來， **ORCAReport** Cmdlet 會產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。 您可以在中下載 ORCA 模組 <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾郵件、反惡意程式碼和反網路釣魚保護

反垃圾郵件、反惡意程式碼和反網路釣魚都是可由系統管理員設定的 EOP 功能。 建議您遵循下列標準或嚴格設定。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾郵件原則設定

若要建立及設定反垃圾郵件原則，請參閱 [在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**垃圾郵件** 偵測動作 <br/><br/> _SpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**高信賴的垃圾郵件** 偵測動作 <br/><br/> _HighConfidenceSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**網路釣魚電子郵件** 偵測動作 <br/><br/> _PhishSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**高信賴網路釣魚電子郵件** 偵測動作 <br/><br/> _HighConfidencePhishAction_|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|**大量電子郵件** 偵測動作 <br/><br/> _BulkSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**將郵件移至 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <br/><br/> `Quarantine`||
|大量電子郵件閾值 <br/><br/> _BulkThreshold_|7 |6 |4 |如需詳細資訊，請參閱 [Office 365 中的大量投訴層級 (BCL) ](bulk-complaint-level-values.md)。|
|隔離保留期間 <br/><br/> _QuarantineRetentionPeriod_|15 天|30 天|30 天||
|**安全性秘訣** <br/><br/> _InlineSafetyTipsEnabled_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|允許的寄件者 <br/><br/> _AllowedSenders_|無|無|無||
|允許的寄件者網域 <br/><br/> _AllowedSenderDomains_|無|無|無|在 [允許的寄件者] 清單) 新增您擁有 (_公認網域_ 的網域是一種非常糟糕的主意。 攻擊者可以傳送您本來會加以篩選的電子郵件。 <br/><br/> 在 [**反垃圾郵件設定**] 頁面的 [安全性 & 規範中心] 中，使用[哄騙智慧](learn-about-spoof-intelligence.md)，以查看組織的電子郵件網域中的所有收件者電子郵件地址或外部網域中的欺騙寄件者電子郵件地址。|
|封鎖的寄件者 <br/><br/> _BlockedSenders_|無|無|無||
|封鎖的寄件者網域 <br/><br/> _BlockedSenderDomains_|無|無|無||
|**啟用使用者垃圾郵件通知** <br/><br/> _EnableEndUserSpamNotifications_|已停用 <br/><br/> `$false`|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`||
|**每 (天傳送一次使用者垃圾郵件通知) ** <br/><br/> _EndUserSpamNotificationFrequency_|3天|3天|3天||
|**垃圾郵件 ZAP** <br/><br/> _SpamZapEnabled_|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`||
|**網路釣魚 ZAP** <br/><br/> _PhishZapEnabled_|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`|已啟用 <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|開啟|開啟|開啟|此設定僅適用于 PowerShell。|
|

有些其他的高級垃圾郵件篩選 (反垃圾郵件原則中的 ASF) 設定，但不是已被取代。 有關這些功能之折舊時程表的詳細資訊，將在本文之外進行傳遞。

建議您為**標準**和**嚴格**的層次 **，關閉這些**ASF 設定。 如需 ASF 設定的詳細資訊，請參閱 [Office 365 中的高級垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)。

****

|安全性功能名稱|留言|
|---|---|
| (_IncreaseScoreWithImageLinks_) **的遠端網站影像連結**||
|URL (_IncreaseScoreWithNumericIps_ **中的數位 IP 位址**) ||
|**UL 重新導向至其他埠** (_IncreaseScoreWithRedirectToOtherPort_) ||
|**.Biz 或. info 網站的 URL** (_IncreaseScoreWithBizOrInfoUrls_) ||
|**空郵件** (_MarkAsSpamEmptyMessages_) ||
|**在 HTML (MarkAsSpamJavaScriptInHtml 中 JavaScript 或 VBScript**) _MarkAsSpamJavaScriptInHtml_||
|HTML (_MarkAsSpamFramesInHtml_ **中的框架或 IFrame 標記**) ||
|HTML (_MarkAsSpamObjectTagsInHtml_ **中的物件標記**) ||
|**在 HTML (MarkAsSpamEmbedTagsInHtml 中嵌入標記**) _MarkAsSpamEmbedTagsInHtml_||
|HTML (_MarkAsSpamFormTagsInHtml_ **中的表單標記**) ||
|HTML (_MarkAsSpamWebBugsInHtml_ **中的 Web 臭蟲**) ||
|套用**機密的單字清單** (_MarkAsSpamSensitiveWordList_) ||
|**SPF 記錄： hard fail** (_MarkAsSpamSpfRecordHardFail_) ||
|**條件式寄件者識別碼篩選： hard fail** (_MarkAsSpamFromAddressAuthFail_) ||
|**NDR 退信攻擊** (_MarkAsSpamNdrBackscatter_) ||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 輸出垃圾郵件原則設定

若要建立及設定輸出垃圾郵件原則，請參閱 [在 Office 365 中設定輸出垃圾郵件篩選](configure-the-outbound-spam-policy.md)。

如需服務中預設傳送限制的詳細資訊，請參閱傳送 [限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**每位使用者的收件者數目上限：外部每小時限制** <br/><br/> _RecipientLimitExternalPerHour_|0|500|400|預設值0表示使用服務預設值。|
|**每位使用者的收件者數目上限：每小時內部的限制** <br/><br/> _RecipientLimitInternalPerHour_|0|1000|800|預設值0表示使用服務預設值。|
|**每位使用者的收件者數目上限：每日限制** <br/><br/> _RecipientLimitPerDay_|0|1000|800|預設值0表示使用服務預設值。|
|**使用者超過限制時的動作** <br/><br/> _ActionWhenThresholdReached_|**限制使用者傳送郵件，直到下列日期為止** <br/><br/> `BlockUserForToday`|**限制使用者傳送郵件** <br/><br/> `BlockUser`|**限制使用者傳送郵件** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反惡意程式碼原則設定

若要建立及設定反惡意程式碼原則，請參閱 [在 Office 365 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**您是否要在郵件被隔離時通知收件者？** <br/><br/> _Action_|否 <br/><br/> _DeleteMessage_|否 <br/><br/> _DeleteMessage_|否 <br/><br/> _DeleteMessage_|如果電子郵件附件中偵測到惡意程式碼，則會隔離郵件，而且只能由系統管理員加以發行。|
|**常見附件類型篩選** <br/><br/> _EnableFileFilter_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|此設定會隔離包含以檔案類型為基礎的可執行附件的郵件，不論附件內容為何。|
|**惡意程式碼零小時自動清除** <br/><br/> _ZapEnabled_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|通知未傳遞郵件的**內部寄件者** <br/><br/> _EnableInternalSenderNotifications_|停用 <br/><br/> `$false`|停用 <br/><br/> `$false`|停用 <br/><br/> `$false`||
|通知未傳遞郵件的**外部寄件者** <br/><br/> _EnableExternalSenderNotifications_|停用 <br/><br/> `$false`|停用 <br/><br/> `$false`|停用 <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP 預設的反網路釣魚原則設定

如需這些設定的詳細資訊，請參閱 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。 若要設定這些設定，請參閱 [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**啟用反欺騙保護** <br/><br/> _EnableAntispoofEnforcement_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用未經驗證的寄件者** <br/><br/> _EnableUnauthenticatedSender_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|會在 Outlook 中為未識別的欺騙寄件者將問號 (？ ) 加入寄件者的相片。 如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md)。|
|**如果電子郵件是由不允許哄騙您網域的人所傳送** <br/><br/> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件** <br/><br/> `Quarantine`|此設定適用于 [欺騙性智慧](learn-about-spoof-intelligence.md)中封鎖的寄件者。|
|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 高級威脅防護安全性

其他安全性好處附帶 Office 365 的「高級威脅防護 (ATP) 訂閱。 如需最新的新聞和資訊，您可以查看 [Office 365 ATP 的新功能](whats-new-in-office-365-atp.md)。

> [!IMPORTANT]
>
> - 預設 ATP 反網路釣魚原則為所有收件者提供 [欺騙保護](set-up-anti-phishing-policies.md#spoof-settings) 。 不過，預設原則中並未設定或啟用特定寄件者或寄件者網域的可用 [類比保護](#impersonation-settings-in-atp-anti-phishing-policies) 設定。 若要啟用模擬保護，請設定預設原則或建立其他 ATP 反網路釣魚原則。
>
> - 沒有預設的安全連結原則或安全附件原則，可自動保護組織中的所有收件者。 若要取得保護，您必須建立至少一個安全連結原則及安全附件原則。
>
> - [SharePoint、OneDrive 和 Microsoft 團隊](atp-for-spo-odb-and-teams.md) 防護和 [安全檔](safe-docs.md) 保護的 ATP，不會對安全連結原則產生任何依賴性。

如果您的訂閱包含 Office 365 ATP，或是您已購買 Office 365 ATP 做為附加元件，請設定下列標準或嚴格設定。

### <a name="atp-anti-phishing-policy-settings"></a>ATP 反網路釣魚原則設定

EOP 客戶如先前所述，取得基本的反網路釣魚，但是 Office 365 ATP 包含更多的功能和控制，可協助防範、偵測和修正攻擊。 若要建立及設定這些原則，請參閱 [在 Office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的類比設定

如需這些設定的詳細資訊，請參閱 [ATP 反網路釣魚原則中的類比設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)。 若要設定這些設定，請參閱 [設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|受保護的使用者： **新增要保護的使用者** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|關閉 <br/><br/> `$false` <br/><br/> 無|開啟 <br/><br/> `$true` <br/><br/> \<list of users\>|開啟 <br/><br/> `$true` <br/><br/> \<list of users\>|根據您的組織，建議您將使用者新增 (郵件寄件者) 在重要角色中。 在內部，受保護的寄件者可能是 CEO、CFO 及其他資深領導人。 外部、受保護的寄件者可以包含理事會成員或董事會的董事。|
|受保護的網域： **自動包含我擁有的網域** <br/><br/> _EnableOrganizationDomainsProtection_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|受保護的網域： **包括自訂網域** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|關閉 <br/><br/> `$false` <br/><br/> 無|開啟 <br/><br/> `$true` <br/><br/> \<list of domains\>|開啟 <br/><br/> `$true` <br/><br/> \<list of domains\>|根據您的組織，建議您將網域新增 (寄件者網域) ，但經常與您互動。|
|受保護的使用者： **如果模仿的使用者傳送電子郵件** <br/><br/> _TargetedUserProtectionAction_|**不要套用任何動作** <br/><br/> `NoAction`|**隔離郵件** <br/><br/> `Quarantine`|**隔離郵件** <br/><br/> `Quarantine`||
|受保護的網域： **如果類比網域傳送電子郵件** <br/><br/> _TargetedDomainProtectionAction_|**不要套用任何動作** <br/><br/> `NoAction`|**隔離郵件** <br/><br/> `Quarantine`|**隔離郵件** <br/><br/> `Quarantine`||
|**顯示類比使用者的秘訣** <br/><br/> _EnableSimilarUsersSafetyTips_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**顯示類比網域的秘訣** <br/><br/> _EnableSimilarDomainsSafetyTips_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**顯示不尋常字元的秘訣** <br/><br/> _EnableUnusualCharactersSafetyTips_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用信箱智慧？** <br/><br/> _EnableMailboxIntelligence_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用信箱智慧型類比保護？** <br/><br/> _EnableMailboxIntelligenceProtection_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**如果由信箱智慧保護的類比使用者傳送電子郵件** <br/><br/> _MailboxIntelligenceProtectionAction_|**不要套用任何動作** <br/><br/> `NoAction`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件** <br/><br/> `Quarantine`||
|**受信任的寄件者** <br/><br/> _ExcludedSenders_|無|無|無|根據您的組織，我們建議新增因模擬而不正確地標示為網路釣魚的使用者，而不是其他篩選器。|
|**信任的網域** <br/><br/> _ExcludedDomains_|無|無|無|根據您的組織，我們建議新增因模擬而不正確地標示為網路釣魚的網域，而不是其他篩選器。|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的欺騙設定

請注意，這些是 [EOP 中的反垃圾郵件原則設定](#eop-anti-spam-policy-settings)中所提供的相同設定。

****

|安全性功能名稱|標準版|嚴格|留言|
|---|---|---|---|
|**啟用反欺騙保護** <br/><br/> _EnableAntispoofEnforcement_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**啟用未經驗證的寄件者** <br/><br/> _EnableUnauthenticatedSender_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|會在 Outlook 中為未識別的欺騙寄件者將問號 (？ ) 加入寄件者的相片。 如需詳細資訊，請參閱 [反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md)。|
|**如果電子郵件是由不允許哄騙您網域的人所傳送** <br/><br/> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <br/><br/> `MoveToJmf`|**隔離郵件** <br/><br/> `Quarantine`|此設定適用于 [欺騙性智慧](learn-about-spoof-intelligence.md)中封鎖的寄件者。|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>ATP 反網路釣魚原則中的高級設定

如需此設定的詳細資訊，請參閱 [ATP 反網路釣魚原則中的高級網路釣魚閥](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)值。 若要設定此設定，請參閱 [設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**高級網路釣魚臨界值** <br/><br/> _PhishThresholdLevel_|**1-標準** <br/><br/> `1`|**2-嚴格** <br/><br/> `2`|**3-更嚴格** <br/><br/> `3`||
|

### <a name="safe-links-settings"></a>安全連結設定

Office 365 中的安全連結包含全域設定，這些設定適用于所有包含在使用中安全連結原則中的使用者，以及每個安全連結原則特有的設定。 如需詳細資訊，請參閱 [Office 365 ATP 中的安全連結](atp-safe-links.md)。

#### <a name="global-settings-for-safe-links"></a>安全連結的通用設定

若要設定這些設定，請參閱 [設定 Office 365 ATP 中安全連結的通用設定](configure-global-settings-for-safe-links.md)。

在 PowerShell 中，您可以使用這些 [設定的 AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) Cmdlet。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**使用下列專案中的安全連結： Office 365 應用程式** <br/><br/> _EnableSafeLinksForO365Clients_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|在支援的 Office 365 desktop 和 mobile (iOS 和 Android) app 中使用 ATP 安全連結。 如需詳細資訊，請參閱 [Office 365 應用程式的安全連結設定](atp-safe-links.md#safe-links-settings-for-office-365-apps)。|
|**使用者按一下安全連結時請勿追蹤** <br/><br/> _TrackClicks_|開啟 <br/><br/> `$false`|關閉 <br/><br/> `$true`|關閉 <br/><br/> `$true`|關閉此設定 (將 _TrackClicks_ 設定為 `$true`) 在支援的 Office 365 應用程式中追蹤使用者按一下。|
|**不要讓使用者點擊至原始 URL 的安全連結** <br/><br/> _AllowClickThrough_|開啟 <br/><br/> `$false`|開啟 <br/><br/> `$false`|開啟 <br/><br/> `$false`|開啟此設定 (將 _AllowClickThrough_ 設定為 `$false`) ，可防止在支援的 Office 365 應用程式中，依序按一下至原始 URL。|
|

#### <a name="safe-links-policy-settings"></a>安全連結原則設定

若要設定這些設定，請參閱 [設定 Office 365 ATP 中的安全連結原則](set-up-atp-safe-links-policies.md)。

在 PowerShell 中，您可以使用這些設定的 [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) 和 [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) Cmdlet。

**附注**：如前文所述，沒有預設的安全連結原則。 [預設] 欄中的值是您建立的新安全連結原則中的預設值。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**選取郵件中未知可能惡意 URLs 的動作** <br/><br/> _IsEnabled_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**選取 Microsoft 小組中未知或可能惡意的 URLs 的動作** <br/><br/> _EnableSafeLinksForTeams_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**針對可疑的連結和指向檔案的連結套用即時 URL 掃描** <br/><br/> _ScanUrls_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**等待 URL 掃描完成再傳遞郵件** <br/><br/> _DeliverMessageAfterScan_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**對組織內傳送的電子郵件套用安全連結** <br/><br/> _EnableForInternalSenders_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**不要追蹤使用者點選** <br/><br/> _DoNotTrackUserClicks_|關閉 <br/><br/> `$false`|關閉 <br/><br/> `$false`|關閉 <br/><br/> `$false`|關閉此設定 (將 _DoNotTrackUserClicks_ 設定為 `$false`) 追蹤使用者按一下。|
|**不允許使用者點選原始 URL** <br/><br/> _DoNotAllowClickThrough_|關閉 <br/><br/> `$false`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟此設定 (將 _DoNotAllowClickThrough_ 設定為 `$true`) ，可防止依序按一下原始 URL。|
|

### <a name="safe-attachments-settings"></a>安全附件設定

Office 365 中的安全附件包括與安全附件原則無關聯的全域設定，以及每個安全連結原則特有的設定。 如需詳細資訊，請參閱 [Office 365 ATP 中的安全附件](atp-safe-attachments.md)。

#### <a name="global-settings-for-safe-attachments"></a>安全附件的通用設定

若要設定這些設定，請參閱在[microsoft 365 E5 中](safe-docs.md)[開啟 SharePoint、OneDrive 和 Microsoft 小組](turn-on-atp-for-spo-odb-and-teams.md)和安全檔的 ATP。

在 PowerShell 中，您可以使用這些 [設定的 AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) Cmdlet。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP** <br/><br/> _EnableATPForSPOTeamsODB_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|**開啟 Office 用戶端的安全檔**<bt/><br/> _EnableSafeDocs_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|此設定僅適用于 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權。 如需詳細資訊，請參閱 [Office 365 中的安全檔 [高級威脅防護](safe-docs.md)]。|
|**即使安全檔識別為惡意檔案，也允許人員按一下受保護的檢視**<bt/><br/> _AllowSafeDocsOpen_|關閉 <br/><br/> `$false`|關閉 <br/><br/> `$false`|此設定與安全檔相關。|
|

#### <a name="safe-attachments-policy-settings"></a>安全附件原則設定

若要設定這些設定，請參閱 [設定 Office 365 ATP 中的安全附件原則](set-up-atp-safe-attachments-policies.md)。

在 PowerShell 中，您可以使用這些設定的 [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) 和 [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) Cmdlet。

**附注**：如前文所述，沒有預設的安全附件原則。 [預設] 欄中的值是您建立的新安全附件原則中的預設值。

****

|安全性功能名稱|預設|標準版|嚴格|留言|
|---|:---:|:---:|:---:|---|
|**安全附件未知的惡意程式碼回應** <br/><br/> _Action_|封鎖 <br/><br/> `Block`|封鎖 <br/><br/> `Block`|封鎖 <br/><br/> `Block`||
|**偵測時重新導向附件** ： **啟用重新導向** <br/><br/> _Redirect_ <br/><br/> _RedirectAddress_|Off，但沒有指定電子郵件地址。 <br/><br/> `$true` <br/><br/> 無|，然後指定電子郵件地址。 <br/><br/> `$true` <br/><br/> 電子郵件地址|，然後指定電子郵件地址。 <br/><br/> `$true` <br/><br/> 電子郵件地址|將郵件重新導向至安全性管理員以進行審閱。|
|**如果惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍。** <br/><br/> _ActionOnError_|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`|開啟 <br/><br/> `$true`||
|

## <a name="related-articles"></a>相關文章

- 您在尋找 **Exchange 郵件流程規則的最佳作法 (又稱為傳輸規則**) ？ 請參閱 [在 Exchange Online 中設定郵件流程規則的最佳作法](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 系統管理員和使用者可以提交誤報 (已標示為錯誤) 和漏報的錯誤電子郵件， (錯誤的電子郵件) Microsoft 進行分析。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

- 使用下列連結可取得如何設定[EOP 服務](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)的**資訊，以及****設定** [Office 365 的高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)。 請不要忘記「[防範 Office 365 威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」中的有用指示。

- 您可以在[這裡](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)的 GPO/內部部署選項上找到**Windows 的安全性基準**，[以取得 Intune](https://docs.microsoft.com/intune/protect/security-baselines)型安全性。 最後， [您可以在](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)Microsoft Defender 高級威脅防護 (ATP) 與 microsoft Intune 安全性基準之間進行比較。
