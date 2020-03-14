---
title: Microsoft 對於 EOP 和 Office 365 ATP 安全性設定、建議、寄件者原則架構、網域型郵件報告及符合性的建議、DomainKeys 識別的郵件、步驟、運作方式、安全性基準、EOP 的基準ATP 的基準，設定 atp，設定 EOP，設定 ATP，設定 EOP，安全性設定
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
ms.openlocfilehash: b7c98fe4b362a5be72be9e103a2602cd4954e028
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42632941"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP 和 Office 365 ATP 安全性的建議設定

**Exchange Online Protection （EOP）** 是 Office 365 訂閱的安全性核心，可協助防止惡意電子郵件到達您員工的收件匣。 不過，每天都會有新的更複雜的攻擊，但通常需要改進的保護。 **Office 365 高級威脅防護（ATP）** ATP Plan 1 或 ATP 方案2包含其他功能，可提供系統管理員更多層的安全性、控制和調查。

雖然我們可讓安全性管理員自訂其安全性設定，但我們建議的 EOP 和 Office 365 ATP 有兩個安全性層級： **Standard**和**Strict**。 每個客戶的環境和需求各不相同，但我們相信這些等級的郵件篩選設定可協助避免不想要的郵件在大多數情況下抵達員工的收件匣。

> [!IMPORTANT]
> 必須在信箱上啟用垃圾郵件設定，篩選才能正確運作。 預設會啟用此功能，但如果篩選似乎不在運作中，則應該加以檢查。 請閱讀[Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)以瞭解詳細資訊。 

本主題說明這些 Microsoft 建議的設定，以協助保護您的 Office 365 使用者。

> [!TIP]
> 您可以下載一個新的 PowerShell 模組，它稱為 Office 365 Advanced 威脅防護建議的設定分析器（ORCA），協助決定這些設定。 當您在租使用者中以系統管理員身分執行時，ORCAReport 將協助產生反垃圾郵件、反網路釣魚和其他郵件衛生設定的評估。 您可以在下列位置https://www.powershellgallery.com/packages/ORCA/下載此模組。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>EOP 中的反垃圾郵件、反惡意程式碼和反網路釣魚保護

反垃圾郵件、反惡意程式碼和反網路釣魚是可由系統管理員設定的 EOP 功能。 建議採用下列設定。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾郵件原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|垃圾郵件偵測動作|將郵件移至 [垃圾郵件] 資料夾|隔離郵件||
|高信賴的垃圾郵件偵測動作|隔離郵件|隔離郵件||
|網路釣魚電子郵件偵測動作|隔離郵件|隔離郵件||
|高信賴網路釣魚電子郵件偵測動作|隔離郵件|隔離郵件||
|大量電子郵件偵測動作|將郵件移至 [垃圾郵件] 資料夾|隔離郵件||
|將大量電子郵件閾值設定為|6 |4 |預設值是目前的7，但建議您將其變更為6。 如需詳細資訊，請參閱[大量投訴層級值](bulk-complaint-level-values.md)。|
|隔離保留期間|30 天|30 天||
|安全性秘訣|開啟|開啟||
|允許的寄件者|無|無||
|允許的寄件者網域|無|無|不需要將您擁有的網域（也稱為「_公認的網域_」）新增至允許的寄件者清單。 實際上，它會被認為是高風險，因為它會為不良的演員帶來機會，以傳送您本來會加以篩選的郵件。在 [**反垃圾郵件設定**] 頁面上，使用 [安全性 & 規範中心] 中的 [[哄騙情報](learn-about-spoof-intelligence.md)]，檢查所有哄騙為組織中的網域或欺騙外部網域的寄件者。|
|封鎖的寄件者|無|無||
|封鎖的寄件者網域|無|無||
|使用者的垃圾郵件通知頻率|已啟用|已啟用|3天|
|自動清除零小時|開啟|開啟|針對垃圾郵件和網路釣魚 ZAP|
|MarkAsSpamBulkMail|開啟|開啟|此設定僅適用于 PowerShell|

反垃圾郵件原則（稱為「高級垃圾郵件篩選（ASF）」）中有其他幾個參數正在被取代。 有關這些功能之折舊時程表的詳細資訊，將在本主題外傳遞。

建議您為標準和嚴格的層次 **，關閉這些**設定：

|安全性功能名稱|註解|
|---------|---------|
|IncreaseScoreWithImageLinks||
|IncreaseScoreWithNumericIps||
|IncreaseScoreWithRedirectToOtherPort||
|IncreaseScoreWithBizOrInfoUrls||
|MarkAsSpamEmptyMessages||
|MarkAsSpamJavaScriptInHtml||
|MarkAsSpamFramesInHtml||
|MarkAsSpamObjectTagsInHtml||
|MarkAsSpamEmbedTagsInHtml||
|MarkAsSpamFormTagsInHtml||
|MarkAsSpamWebBugsInHtml||
|MarkAsSpamSensitiveWordList||
|MarkAsSpamFromAddressAuthFail||
|MarkAsSpamNdrBackscatter||
|MarkAsSpamSpfRecordHardFail||

#### <a name="eop-outbound-spam-filter-policy-settings"></a>EOP 輸出垃圾郵件篩選原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|輸出垃圾郵件原則收件者限制-外部每小時限制|500|400||
|輸出垃圾郵件原則收件者限制-內部小時限制|1000|800||
|輸出垃圾郵件原則收件者限制-每日限制|1000|800||
|使用者超過限制時的動作|限制使用者傳送郵件|限制使用者傳送郵件||

### <a name="eop-anti-malware-policy-settings"></a>EOP 反惡意程式碼原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|惡意程式碼偵測回應|否|否|如果在電子郵件附件中偵測到惡意程式碼，將會隔離郵件，而且只能由系統管理員加以發行。|
|「通用附件類型篩選」，用於封鎖可疑檔案類型|開啟|開啟||
|惡意程式碼零小時自動清除|開啟|開啟||
|通知未傳遞郵件的內部寄件者|停用|停用||
|通知未傳遞郵件的外部寄件者|停用|停用||

### <a name="eop-anti-phishing-policy-settings"></a>EOP 反網路釣魚原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|啟用反欺騙保護|開啟|開啟||
|啟用未經驗證的寄件者（標記）|開啟|開啟||
|如果電子郵件是由不允許哄騙您網域的人所傳送|將郵件移至收件者的 [垃圾郵件] 資料夾|隔離郵件||

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 高級威脅防護安全性

其他的安全性好處來自 Office 365 高級威脅防護（ATP）訂閱。 如需最新的新聞和資訊，您可以查看[Office 365 ATP 的新功能](whats-new-in-office-365-atp.md)。

Office 365 ATP 包含安全附件和安全連結原則，可防止電子郵件遭受潛在惡意附件的傳遞，並防止使用者按一下潛在的不安全 URLs。

> [!IMPORTANT]
> 高級反網路釣魚是 Office 365 ATP 訂閱的其中一個優點。 雖然預設會啟用它，但您***必須***先設定至少一個反網路釣魚原則，才能開始篩選郵件。 忘記設定反網路釣魚原則可能會將使用者暴露于危險的電子郵件。 在您新增 Office 365 ATP 訂閱後，請務必設定您的反網路釣魚原則。

如果您已將 Office 365 ATP 訂閱新增至您的 EOP，請設定下列設定。

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP 反網路釣魚原則設定

EOP 客戶如先前所述，取得基本的反網路釣魚，但是 Office 365 ATP 包含更多的功能和控制，可協助防範、偵測和修正攻擊。

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
|EnableSuspiciousSafetyTip|False|True|此設定僅適用于 PowerShell|
|TreatSoftPassAsAuthenticated|True|False|此設定僅適用于 PowerShell|


|高級設定安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|高級網路釣魚臨界值|2-嚴格|3-更嚴格||

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

- 將可疑的郵件、可疑的垃圾郵件、網路釣魚詐騙或 URLs 傳送給 Microsoft 進行掃描。 請使用[本文](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)中的系統**管理報送**方向。

- 使用下列連結可取得如何設定[EOP 服務](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)的**資訊，以及****設定** [Office 365 的高級威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)。 （請不要忘記「防禦[Office 365 中的威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」中有説明的指示。）

- 在這裡，您可以在[此處](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines)找到 GPO/內部部署選項的安全性基準，並在[這裡](https://docs.microsoft.com/intune/protect/security-baselines)找到 Intune 型安全性的**安全性基準**。 最後，您可以在[這裡](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)找到 Microsoft Defender 高級威脅防護（ATP）與 Windows Intune 安全性基準之間的比較。
