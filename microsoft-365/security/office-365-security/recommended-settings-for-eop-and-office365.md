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
ms.openlocfilehash: 67d1b133e0d0ac7e622ed0bfdbfd17214608d77a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083545"
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

本文說明預設設定，也是建議的標準和嚴格設定，以協助保護您的使用者。 這些表格包含 Microsoft 365 Defender 入口網站中的設定，以及 PowerShell (Exchange Online PowerShell 或獨立 Exchange Online Protection 的組織，PowerShell 沒有 Exchange Online 信箱) 。

> [!TIP]
> Office 365 的高級威脅防護建議的設定分析器 (ORCA) 模組 PowerShell 可協助您 (系統管理員) 找到這些設定的目前值。 具體說來， **ORCAReport** Cmdlet 會產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。 您可以在中下載 ORCA 模組 <https://www.powershellgallery.com/packages/ORCA/> 。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾郵件、反惡意程式碼和反網路釣魚保護

反垃圾郵件、反惡意程式碼和反網路釣魚都是可由系統管理員設定的 EOP 功能。 建議您遵循下列標準或嚴格設定。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾郵件原則設定

若要建立及設定反垃圾郵件原則，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**大量電子郵件閾值 & 垃圾郵件屬性**||||
|**大量電子郵件閾值** <p> _BulkThreshold_|7 |6 |4 |如需詳細資訊，請參閱 [EOP 中的大量投訴層級 (BCL) ](bulk-complaint-level-values.md)。|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|此設定僅適用于 PowerShell。|
|**增加垃圾郵件分數** 設定|關閉|關閉|關閉|所有這些設定都是「高級垃圾郵件篩選」的一部分 (ASF) 。 如需詳細資訊，請參閱本文的 [反垃圾郵件原則區段中的 ASF 設定](#asf-settings-in-anti-spam-policies) 。|
|**標記為垃圾郵件** 設定|關閉|關閉|關閉|這些設定大多都是 ASF 的一部分。 如需詳細資訊，請參閱本文的 [反垃圾郵件原則區段中的 ASF 設定](#asf-settings-in-anti-spam-policies) 。|
|**包含特定語言** <p> _EnableLanguageBlockList_ <p> _LanguageBlockList_|**關閉** <p> `$false` <p> 空白|**關閉** <p> `$false` <p> 空白|**關閉** <p> `$false` <p> 空白|我們沒有此設定的特別建議。 您可以根據您的業務需求，封鎖特定語言的郵件。|
|**從這些國家/地區** <p> _EnableRegionBlockList_ <p> _RegionBlockList_|**關閉** <p> `$false` <p> 空白|**關閉** <p> `$false` <p> 空白|**關閉** <p> `$false` <p> 空白|我們沒有此設定的特別建議。 您可以根據您的業務需求，封鎖特定國家/地區的郵件。|
|**測試模式** (_TestModeAction_) |**無**|**無**|**無**|此設定是 ASF 的一部分。 如需詳細資訊，請參閱本文的 [反垃圾郵件原則區段中的 ASF 設定](#asf-settings-in-anti-spam-policies) 。|
|**Actions**|||||
|**垃圾郵件** 偵測動作 <p> _SpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**高信賴的垃圾郵件** 偵測動作 <p> _HighConfidenceSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**網路釣魚** 偵測動作 <p> _PhishSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**高信賴網路釣魚** 偵測動作 <p> _HighConfidencePhishAction_|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**大量** 偵測動作 <p> _BulkSpamAction_|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件**   將郵件傳送到隔離信箱，而不是傳送給預定的收件者。 <p> `Quarantine`||
|**保留這數天內的垃圾郵件** <p> _QuarantineRetentionPeriod_|15 天|30 天|30 天||
|**啟用垃圾郵件安全提示** <p> _InlineSafetyTipsEnabled_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|為網路釣魚郵件啟用零小時自動清除 (ZAP)  <p> _PhishZapEnabled_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|啟用垃圾郵件的 ZAP <p> _SpamZapEnabled_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|**啟用使用者垃圾郵件通知** <p> _EnableEndUserSpamNotifications_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|**每 (天傳送一次使用者垃圾郵件通知)** <p> _EndUserSpamNotificationFrequency_|3天|3天|3天||
|**允許 & 封鎖清單**|||||
|允許的寄件者 <p> _AllowedSenders_|無|無|無||
|允許的寄件者網域 <p> _AllowedSenderDomains_|無|無|無|將網域新增至允許的寄件者清單是一種非常壞的主意。 攻擊者可以傳送您本來會加以篩選的電子郵件。 <p> 使用 [ [偽造智慧真知灼見](learn-about-spoof-intelligence.md) ] 和 [ [承租人允許/封鎖] 清單](tenant-allow-block-list.md) ，以查看組織的電子郵件網域中的所有收件者電子郵件地址或外部網域中的欺騙寄件者電子郵件地址中的所有寄件者。|
|封鎖的寄件者 <p> _BlockedSenders_|無|無|無||
|封鎖的寄件者網域 <p> _BlockedSenderDomains_|無|無|無||
|

#### <a name="asf-settings-in-anti-spam-policies"></a>反垃圾郵件原則中的 ASF 設定

在反垃圾郵件原則中，有許多高級垃圾郵件篩選 (ASF) 設定不會被取代。 有關這些功能之折舊時程表的詳細資訊，將在本文之外進行傳遞。

建議 **您為****標準** 和 **嚴格** 的層級保留下列 ASF 設定。 如需有關 ASF 設定的詳細資訊，請參閱 [EOP 中的高級垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)。

<br>

****

|安全性功能名稱|註解|
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
|**測試模式** (_TestModeAction_) |針對支援 **測試** 為動作的 ASF 設定，您可以將測試模式動作設定為 [ **無**]、[ **新增預設 X-Header 文字**] 或 [ **傳送 Bcc 郵件** (] `None` 或 [) ] `AddXHeader` `BccMessage` 。 如需詳細資訊，請參閱 [Enable、disable 或 TEST ASF settings](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)。|
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP 輸出垃圾郵件原則設定

若要建立及設定輸出垃圾郵件原則，請參閱 [在 EOP 中設定輸出垃圾郵件篩選](configure-the-outbound-spam-policy.md)。

如需服務中預設傳送限制的詳細資訊，請參閱傳送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**設定外部郵件限制** <p> _RecipientLimitExternalPerHour_|0|500|400|預設值0表示使用服務預設值。|
|**設定內部郵件限制** <p> _RecipientLimitInternalPerHour_|0|1000|800|預設值0表示使用服務預設值。|
|**設定每日郵件限制** <p> _RecipientLimitPerDay_|0|1000|800|預設值0表示使用服務預設值。|
|**對達到郵件限制的使用者施加限制** <p> _ActionWhenThresholdReached_|**限制使用者在下一天前傳送郵件** <p> `BlockUserForToday`|**限制使用者傳送郵件** <p> `BlockUser`|**限制使用者傳送郵件** <p> `BlockUser`||
|**自動轉送規則** <p> _AutoForwardingMode_|**自動系統控制** <p> `Automatic`|**自動系統控制** <p> `Automatic`|**自動系統控制** <p> `Automatic`|
|**將超過這些限制的輸出郵件複本傳送給這些使用者和群組** <p> _BccSuspiciousOutboundMail_ <p> _BccSuspiciousOutboundAdditionalRecipients_|未選取 <p> `$false` <p> 空白|未選取 <p> `$false` <p> 空白|未選取 <p> `$false` <p> 空白|我們沒有此設定的特別建議。 <p> 此設定僅適用于預設輸出垃圾郵件原則。 在您建立的自訂輸出垃圾郵件原則中無法運作。|
|**如果寄件者因傳送輸出垃圾郵件而遭到封鎖，請通知這些使用者和群組** <p> _NotifyOutboundSpam_ <p> _NotifyOutboundSpamRecipients_|未選取 <p> `$false` <p> 空白|未選取 <p> `$false` <p> 空白|未選取 <p> `$false` <p> 空白|名為「**使用者限制于傳送電子郵件** 的預設 [警示原則](../../compliance/alert-policies.md)」已將電子郵件通知傳送給 **TenantAdmins** (**Global admins**) 群組中的使用者，因為超出原則中的限制。 **強烈建議您在輸出垃圾郵件原則中使用警示原則，而不是此設定，以通知系統管理員和其他使用者**。 如需相關指示，請參閱 [確認限制使用者的警示設定](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。|
|

### <a name="eop-anti-malware-policy-settings"></a>EOP 反惡意程式碼原則設定

若要建立及設定反惡意程式碼原則，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**保護設定**|||||
|**啟用常見附件篩選器** <p> _EnableFileFilter_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`|此設定會隔離包含以檔案類型為基礎的可執行附件的郵件，不論附件內容為何。|
|**為惡意程式碼啟用零小時自動清除** <p> _ZapEnabled_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|**收件者通知**|||||
|**將郵件隔離為惡意程式碼時通知收件者** <p> _Action_|未選取 <p> _DeleteMessage_|未選取 <p> _DeleteMessage_|未選取 <p> _DeleteMessage_|如果電子郵件附件中偵測到惡意程式碼，則會隔離郵件，而且只能由系統管理員加以發行。|
|**寄件者通知**|||||
|**將郵件隔離為惡意程式碼時通知內部寄件者** <p> _EnableInternalSenderNotifications_|未選取 <p> `$false`|未選取 <p> `$false`|未選取 <p> `$false`||
|**將郵件隔離為惡意程式碼時通知外部寄件者** <p> _EnableExternalSenderNotifications_|未選取 <p> `$false`|未選取 <p> `$false`|未選取 <p> `$false`||
|**系統管理員通知**|||||
|**通知系統管理員來自內部寄件者的未傳遞郵件** <p> _EnableInternalSenderAdminNotifications_ <p> _InternalSenderAdminAddress_|未選取 <p> `$false`|未選取 <p> `$false`|未選取 <p> `$false`|我們沒有此設定的特別建議。|
|**通知系統管理員來自外部寄件者的未傳遞郵件** <p> _EnableExternalSenderAdminNotifications_ <p> _ExternalSenderAdminAddress_|未選取 <p> `$false`|未選取 <p> `$false`|未選取 <p> `$false`|我們沒有此設定的特別建議。|
|**自訂通知**||||對於這些設定，我們沒有具體的建議。|
|**使用自訂的通知文字** <p> _CustomNotifications_|未選取 <p> `$false`|未選取 <p> `$false`|未選取 <p> `$false`||
|**來源名稱** <p> _CustomFromName_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**寄件者地址** <p> _CustomFromAddress_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**自訂來自內部寄件者的郵件通知**||||只有當 **郵件隔離為惡意** 代碼或已選取 [ **通知系統管理員從內部寄件者未傳遞的郵件** ] 時，才會使用這些設定。|
|**主旨** <p> _CustomInternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**訊息** <p> _CustomInternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**自訂來自外部寄件者的郵件通知**||||只有當 **郵件隔離為惡意** 代碼或已選取 **外部寄件者的未傳遞郵件通知系統管理員** 時，才會使用這些設定。|
|**主旨** <p> _CustomExternalSubject_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|**訊息** <p> _CustomExternalBody_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP 反網路釣魚原則設定

如需這些設定的詳細資訊，請參閱 [欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。 若要設定這些設定，請參閱 [在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**網路釣魚閥值 & 保護**|||||
|**啟用欺騙情報** <p> _EnableSpoofIntelligence_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|**Actions**|||||
|**如果偵測到郵件為欺騙** <p> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件** <p> `Quarantine`|此設定適用于已自動封鎖的欺騙寄件者，如在「[租使用者允許/封鎖」清單](tenant-allow-block-list.md)中的[欺騙智慧真知灼見](learn-about-spoof-intelligence.md)或手動封鎖中所示。|
|**顯示第一個連絡人安全提示** <p> _EnableFirstContactSafetyTips_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`|如需詳細資訊，請參閱[第一個連絡人安全提示](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**顯示未驗證寄件者取得 (？ ) 以取得欺騙** <p> _EnableUnauthenticatedSender_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`|在 Outlook 中為未識別的欺騙寄件者新增問號 (？ ) 到寄件者的相片。 如需詳細資訊，請參閱未 [驗證寄件者](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**顯示 "via" 標記** <p> _EnableViaTag_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`|透過 chris@contoso.com 透過 fabrikam.com) 的 [寄件者] **或 [寄件者位址]** 中的網域，將透過 (標記新增至 [寄件者] 位址。 <p> 如需詳細資訊，請參閱未 [驗證寄件者](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender Office 365 安全性

其他的安全性好處是 Microsoft Defender 的 Office 365 訂閱。 如需最新的新聞和資訊，您可以查看[Office 365 的 Defender 新增功能](whats-new-in-defender-for-office-365.md)。

> [!IMPORTANT]
>
> - Office 365 的 Microsoft Defender 中的預設反網路釣魚原則為所有收件者提供[欺騙保護](set-up-anti-phishing-policies.md#spoof-settings)和信箱智慧。 不過，預設原則中並未設定或啟用其他可用的模擬 [保護](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 功能和 [高級設定](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。 若要啟用所有保護功能，請修改預設的反網路釣魚原則，或建立其他的反網路釣魚原則。
>
> - 沒有預設的保管庫連結原則或保管庫附件原則，可自動保護組織中的所有收件者。 若要取得保護，您必須建立至少一個保管庫連結原則及保管庫附件原則。
>
> - [保管庫 SharePoint、OneDrive 及 Microsoft Teams](mdo-for-spo-odb-and-teams.md)保護和[保管庫檔](safe-docs.md)保護的附件，對保管庫連結原則沒有任何相依性的依賴性。

如果您的訂閱包含用於 Office 365 的 Microsoft defender，或您已購買 Office 365 做為附加元件的 defender，請設定下列標準或嚴格設定。

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則設定

EOP 客戶會如先前所述，取得基本的反網路釣魚，但 Office 365 的 Defender 包含更多的功能和控制，可協助防範、偵測和修正攻擊。 若要建立及設定這些原則，請參閱[在 Office 365 中設定 Defender 的反網路釣魚原則](configure-mdo-anti-phishing-policies.md)。

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的高級設定

如需此設定的詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的高級網路釣魚閥值 Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要設定此設定，請參閱[設定 Office 365 的 Defender 中的反網路釣魚原則](configure-mdo-anti-phishing-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**網路釣魚電子郵件閾值** <p> _PhishThresholdLevel_|**1-標準** <p> `1`|**2-嚴格** <p> `2`|**3-更嚴格** <p> `3`||
|

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender 中 Office 365 的反網路釣魚原則中的模擬設定

如需這些設定的詳細資訊，請參閱[Microsoft Defender 的反網路釣魚原則中的模仿設定 Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。 若要設定這些設定，請參閱[在 Office 365 中設定 Defender 中的反網路釣魚原則](configure-mdo-anti-phishing-policies.md)。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**網路釣魚閥值 & 保護**|||||
|**讓使用者能夠保護** (類比的使用者保護) <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|未選取 <p> `$false` <p> 無|已選取 <p> `$true` <p> \<list of users\>|已選取 <p> `$true` <p> \<list of users\>|建議您在主要角色) 中新增使用者 (郵件寄件者。 在內部，受保護的寄件者可能是 CEO、CFO 及其他資深領導人。 外部、受保護的寄件者可以包含理事會成員或董事會的董事。|
|**啟用網域來保護** (類比的網域保護) |未選取|已選取|已選取||
|**包含我擁有的網域** <p> _EnableOrganizationDomainsProtection_|關閉 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|**包含自訂網域** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|關閉 <p> `$false` <p> 無|已選取 <p> `$true` <p> \<list of domains\>|已選取 <p> `$true` <p> \<list of domains\>|建議您不擁有的網域 (寄件者網域) 新增，但您經常與您互動。|
|**新增受信任的寄件者與網域** <p> _ExcludedSenders_ <p> _ExcludedDomains_|無|無|無|根據您的組織，我們建議新增錯誤辨識為類比嘗試的寄件者或網域。|
|**啟用信箱智慧** <p> _EnableMailboxIntelligence_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|**啟用智慧以進行類比保護** <p> _EnableMailboxIntelligenceProtection_|關閉 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`|此設定允許透過信箱智慧進行類比偵測的指定動作。|
|**Actions**|||||
|**如果偵測到郵件為模仿的使用者** <p> _TargetedUserProtectionAction_|**不要套用任何動作** <p> `NoAction`|**隔離郵件** <p> `Quarantine`|**隔離郵件** <p> `Quarantine`||
|**如果偵測到郵件為類比網域** <p> _TargetedDomainProtectionAction_|**不要套用任何動作** <p> `NoAction`|**隔離郵件** <p> `Quarantine`|**隔離郵件** <p> `Quarantine`||
|**如果信箱智慧偵測和模仿使用者** <p> _MailboxIntelligenceProtectionAction_|**不要套用任何動作** <p> `NoAction`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件** <p> `Quarantine`||
|**顯示使用者模擬安全提示** <p> _EnableSimilarUsersSafetyTips_|關閉 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|**顯示網域模擬安全提示** <p> _EnableSimilarDomainsSafetyTips_|關閉 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|**顯示使用者模擬不尋常的字元安全提示** <p> _EnableUnusualCharactersSafetyTips_|關閉 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>EOP Microsoft Defender 中 Office 365 的反網路釣魚原則設定

這些是 [EOP 中的反垃圾郵件原則設定](#eop-anti-spam-policy-settings)中所提供的相同設定。

欺騙設定是相互關聯的，但是 [**顯示第一個連絡人安全提示**] 設定對哄騙設定沒有相依的依賴性。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**網路釣魚閥值 & 保護**|||||
|**啟用欺騙情報** <p> _EnableSpoofIntelligence_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|**Actions**|||||
|**如果偵測到郵件為欺騙** <p> _AuthenticationFailAction_|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**將郵件移至收件者的 [垃圾郵件] 資料夾** <p> `MoveToJmf`|**隔離郵件** <p> `Quarantine`|此設定適用于已自動封鎖的欺騙寄件者，如在「[租使用者允許/封鎖」清單](tenant-allow-block-list.md)中的[欺騙智慧真知灼見](learn-about-spoof-intelligence.md)或手動封鎖中所示。|
|**顯示第一個連絡人安全提示** <p> _EnableFirstContactSafetyTips_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`|如需詳細資訊，請參閱[第一個連絡人安全提示](set-up-anti-phishing-policies.md#first-contact-safety-tip)。|
|**顯示未驗證寄件者取得 (？ ) 以取得欺騙** <p> _EnableUnauthenticatedSender_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`|在 Outlook 中為未識別的欺騙寄件者新增問號 (？ ) 到寄件者的相片。 如需詳細資訊，請參閱未 [驗證寄件者](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|**顯示 "via" 標記** <p> _EnableViaTag_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`|透過 chris@contoso.com 透過 fabrikam.com) 的 [寄件者] **或 [寄件者位址]** 中的網域，將透過 (標記新增至 [寄件者] 位址。 <p> 如需詳細資訊，請參閱未 [驗證寄件者](set-up-anti-phishing-policies.md#unauthenticated-sender)。|
|

### <a name="safe-attachments-settings"></a>保管庫附件設定

保管庫Microsoft Defender for Office 365 中的附件包含與保管庫附件原則沒有關系的全域設定，以及每個保管庫連結原則特有的設定。 如需詳細資訊，請參閱[保管庫的 Defender Office 365 附件](safe-attachments.md)。

#### <a name="global-settings-for-safe-attachments"></a>保管庫附件的全域設定

若要設定這些設定，請參閱在保管庫中[開啟 SharePoint、OneDrive 及 Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)及[Microsoft 365 E5 檔](safe-docs.md)的保管庫附件。

在 PowerShell 中，您可以使用這些 [設定的 AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) Cmdlet。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**針對 SharePoint、OneDrive 和 Microsoft Teams 開啟適用於 Office 365 的 Defender** <p> _EnableATPForSPOTeamsODB_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`||
|**開啟 Office 用戶端的保管庫檔** <p> _EnableSafeDocs_|關閉 <p> `$false`|開啟 <p> `$true`|開啟 <p> `$true`|這項功能只有 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權才能使用且有意義。 如需詳細資訊，請參閱[保管庫的 Microsoft Defender 檔 Office 365](safe-docs.md)。|
|**即使保管庫檔識別為惡意檔案，也可讓使用者依序按一下 [受保護的檢視]** <p> _AllowSafeDocsOpen_|關閉 <p> `$false`|關閉 <p> `$false`|關閉 <p> `$false`|此設定與保管庫檔相關。|
|

#### <a name="safe-attachments-policy-settings"></a>保管庫附件原則設定

若要設定這些設定，請參閱[設定保管庫的 Defender Office 365 附件原則](set-up-safe-attachments-policies.md)。

在 PowerShell 中，您可以使用這些設定的 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) 和 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) Cmdlet。

> [!NOTE]
> 如先前所述，沒有預設的保管庫附件原則。 [預設] 欄中的值是您建立的新保管庫附件原則中的預設值。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**保管庫附件未知的惡意程式碼回應** <p> _Action_|**關閉** <p> `Block`|**封鎖** <p> `Block`|**封鎖** <p> `Block`||
|**以偵測到的附件重新導向附件** ： **啟用重新導向** <p> _Redirect_ <p> _RedirectAddress_|未選取，且未指定電子郵件地址。 <p> `$true` <p> 無|已選取，並指定電子郵件地址。 <p> `$true` <p> 電子郵件地址|已選取，並指定電子郵件地址。 <p> `$true` <p> 電子郵件地址|將郵件重新導向至安全性管理員以進行審閱。|
|**如果掃描無法完成 (超時或錯誤，請套用保管庫附件偵測回應)** <p> _ActionOnError_|已選取 <p> `$true`|已選取 <p> `$true`|已選取 <p> `$true`||
|

### <a name="safe-links-settings"></a>保管庫連結設定

保管庫Office 365 的 Defender 中的連結包含全域設定，這些設定適用于所有包含在使用中保管庫連結原則的使用者，以及每個保管庫連結原則特有的設定。 如需詳細資訊，請參閱[保管庫的 Defender 連結 Office 365](safe-links.md)。

#### <a name="global-settings-for-safe-links"></a>保管庫連結的全域設定

若要設定這些設定，請參閱[設定保管庫的 Defender 中連結的通用設定 Office 365](configure-global-settings-for-safe-links.md)。

在 PowerShell 中，您可以使用這些 [設定的 AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) Cmdlet。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**封鎖下列 URL** <p> _ExcludedUrls_|空白 <p> `$null`|空白 <p> `$null`|空白 <p> `$null`|我們沒有此設定的特別建議。 <p> 如需詳細資訊，請參閱[保管庫連結的「封鎖下列 URLs」清單](safe-links.md#block-the-following-urls-list-for-safe-links)。
|**使用 Office 365 應用程式中的保管庫連結** <p> _EnableSafeLinksForO365Clients_|開啟 <p> `$true`|開啟 <p> `$true`|開啟 <p> `$true`|使用支援的 Office 365 桌面和行動 (iOS 和 Android) 應用程式中保管庫連結。 如需詳細資訊，請參閱[保管庫連結設定 Office 365 應用程式](safe-links.md#safe-links-settings-for-office-365-apps)。|
|**當使用者在 Office 365 應用程式中按一下受保護的連結時，請勿追蹤** <p> _TrackClicks_|開啟 <p> `$false`|關閉 <p> `$true`|關閉 <p> `$true`|關閉此設定 (將 _TrackClicks_ 設定為 `$true`) 追蹤使用者在支援 Office 365 應用程式中的按一下。|
|**請勿讓使用者在 Office 365 應用程式中，按原始 URL。** <p> _AllowClickThrough_|開啟 <p> `$false`|開啟 <p> `$false`|開啟 <p> `$false`|開啟此設定 (將 _AllowClickThrough_ 設定為 `$false`) ，可防止在支援的 Office 365 應用程式中，依序按一下至原始 URL。|
|

#### <a name="safe-links-policy-settings"></a>保管庫連結原則設定

若要設定這些設定，請參閱[在 Microsoft Defender 中設定 Office 365 的保管庫連結原則](set-up-safe-links-policies.md)。

在 PowerShell 中，您可以使用這些設定的 [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) 和 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) Cmdlet。

> [!NOTE]
> 如前文所述，沒有預設的保管庫連結原則。 [預設] 欄中的值是您建立的新保管庫連結原則中的預設值。

<br>

****

|安全性功能名稱|預設|標準版|嚴格|註解|
|---|:---:|:---:|:---:|---|
|**保護設定**|||||
|**選取郵件中未知可能惡意 URLs 的動作** <p> _IsEnabled_|**關閉** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`||
|**選取 Microsoft Teams 內未知或可能惡意的 URLs 的動作** <p> _EnableSafeLinksForTeams_|**關閉** <p> `$false`|**On** <p> `$true`|**On** <p> `$true`|從2020年3月起，這項功能只是在預覽中，且僅適用 Microsoft Teams 技術採用計畫的成員 (點擊) 。|
|**針對可疑的連結和指向檔案的連結套用即時 URL 掃描** <p> _ScanUrls_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|**等待 URL 掃描完成再傳遞郵件** <p> _DeliverMessageAfterScan_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|**套用保管庫連結至組織內傳送的電子郵件** <p> _EnableForInternalSenders_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`||
|**不要追蹤使用者點選** <p> _DoNotTrackUserClicks_|未選取 <p> `$false`|未選取 <p> `$false`|未選取 <p> `$false`|關閉此設定 (將 _DoNotTrackUserClicks_ 設定為 `$false`) 追蹤使用者按一下。|
|**不要讓使用者依序按一下原始 URL** <p> _DoNotAllowClickThrough_|未選取 <p> `$false`|已選取 <p> `$true`|已選取 <p> `$true`|開啟此設定 (將 _DoNotAllowClickThrough_ 設定為 `$true`) ，可防止依序按一下原始 URL。|
|**在通知和警告頁面上顯示組織商標** <p> _EnableOrganizationBranding_|未選取 <p> `$false`|未選取 <p> `$false`|未選取 <p> `$false`|我們沒有此設定的特別建議。 <p> 在您開啟此設定之前，您必須遵循[自訂群組織的 Microsoft 365 主題](../../admin/setup/customize-your-organization-theme.md)中的指示，以上傳公司徽標。|
|**不重新寫入下列 URLs** <p> _DoNotRewriteUrls_|未選取 <p> `$false`|未選取 <p> `$true`|未選取 <p> `$true`|我們沒有此設定的特別建議。 如需詳細資訊，請參閱[保管庫連結原則中的「不要重新寫入下列 URLs」清單](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)。|
|**通知**|||||
|**您要如何通知使用者？**|**使用預設通知文字**|**使用預設通知文字**|**使用預設通知文字**|我們沒有此設定的特別建議。 <p> 您可以選取 [ **使用自訂通知文字** (_CustomNotificationText_ ]) 輸入要使用的自訂通知文字。 您也可以選取 [**使用 Microsoft 翻譯工具以進行自動當地語系化** (_UseTranslatedNotificationText_) 將自訂通知文字轉譯為使用者語言。
|

## <a name="related-articles"></a>相關文章

- 您在尋找 **Exchange 郵件流程規則 (也稱為 transport rules**) 的最佳作法？ 請參閱[在 Exchange Online 中設定郵件流程規則的最佳作法](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)。

- 系統管理員和使用者可以提交誤報 (已標示為錯誤) 和漏報的錯誤電子郵件， (錯誤的電子郵件) Microsoft 進行分析。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

- 若要瞭解如何 **設定** [EOP 服務](/exchange/standalone-eop/set-up-your-eop-service)的相關資訊，請使用下列連結 **，並為** [Office 365 設定 Microsoft Defender](defender-for-office-365.md)。 請不要忘記「[防範 Office 365 中威脅](protect-against-threats.md)的有用指示。

- 您可以在以下位置找到 **Windows 的安全性基準**：[何處可以取得安全性基準？](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)針對 GPO/內部部署選項，以及 [使用安全性基線，設定 intune 中 Windows 10 裝置](/intune/protect/security-baselines)以供 intune 使用的安全性。 最後，在[比較 microsoft defender for endpoint 和 Windows Intune 安全性基準](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)時，可使用 microsoft defender for endpoint 和 Microsoft Intune 安全性基準之間的比較。
