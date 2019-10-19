---
title: 設定 EOP 和 Office 365 ATP 安全、 最佳作法、 設定、 寄件者原則架構、 網域型郵件報告和符合性聲明，DomainKeys Identified Mail 的建議的最佳作法，它如何運作，執行步驟
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Exchange Online Protection (EOP) 和進階威脅防護 (ATP) 的安全性設定的最佳做法是什麼？ 什麼被建議？ 應積極地使用什麼？ 以及哪些額外讓如果您也可以使用進階威脅防護 (ATP)？
ms.openlocfilehash: b40b4189ed996e1b2f671b77602630f2a98966a5
ms.sourcegitcommit: ffdf576fbc62c4c316f6d8061d2bd973e7df9f56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2019
ms.locfileid: "37598297"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>設定 EOP 和 Office 365 ATP 安全的最佳作法

Exchange Online Protection (EOP) 是安全性 E3 Office 365 訂閱的核心。 是選擇性的且即使建議，若要購買訂閱至 Office 365 進階威脅防護 (ATP)，例如 E3 客戶。 ATP 方案 1 或 ATP 計劃 2，以便運用可用 E5 Office 365 訂閱中增加的安全性。

我們將討論兩種安全性層級，稱為建議並加強在 EOP 中，其中涵蓋如何使用這兩個層級的安全性功能的註解。 章節的開頭的電子郵件驗證和驗證，其中包括一些補救措施，以便外部 Office 365，在 DNS 中，以及保護對這些郵件的資源進行租用戶好公民的輸出郵件。 這些最佳的設定，以保護您的訂閱。


## <a name="email-authentication"></a>電子郵件驗證

SPF，DKIM、 DMARC 是縮略字寄件者原則架構、 DomainKeys Identified Mail 和網域型郵件驗證、 報表及 Conformance （相當說來話長），而且是電子郵件驗證和驗證的基礎。

這些方法處理從 Office 365 的外寄電子郵件，並從您網域的電子郵件的說明目的系統信任時才有效。 它們只最佳作法我們將涵蓋牽涉到*外部*Office 365 的 DNS 中所做的組態。 如需特定組態步驟，請參閱[電子郵件驗證與驗證](https://docs.microsoft.com/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing)] 區段中的安全性與合規性的資料表的內容。


|安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|[建立 SPF 記錄](https://docs.microsoft.com/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | 是        |    是     |   -      |
|[設定 DKIM 簽章的網域](https://docs.microsoft.com/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  是       |    是     |  -       |
|[拒絕] 或 [隔離] 動作與實作 DMARC](https://docs.microsoft.com/office365/securitycompliance/use-dmarc-to-validate-email)     |   是      |     是    |   使用巨集指令 = 無建議，以及動作的加強 = 拒絕。     |

> [!IMPORTANT]
> 若要使用的安全性角色和權限，請務必您有 Office 365 或安全性與合規性中心的正確的角色。 如果您是在 Azure Active Directory*安全性系統管理員*、 Office 365 中的*全域系統管理員*或 Exchange Online/Exchange Online Powershell 中的*Exchange Online 組織管理員*，您正在準備就緒。

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>反垃圾郵件、 反惡意程式碼，並反網路釣魚

反垃圾郵件和反惡意程式碼是 EOP 功能。 垃圾郵件篩選，在 Office 365 中的預設會掃描所有郵件，並將垃圾郵件信賴等級 (SCL) 數字至每個信箱的值。 只以釐清，其目的是為了列舉如何以內的篩選器是，郵件是 （或未） 垃圾郵件。 低值，例如-1 為非垃圾郵件從安全寄件者及陸地使用者收件匣中的。 高分數，例如 7、 8 或 9 是高度可疑或已知濫發垃圾郵件者和使用者的垃圾郵件，或系統管理員存取隔離的標題。

惡意程式碼篩選也是在 Office 365 中的預設。 例如反垃圾郵件篩選，反惡意軟體篩選器處理的內送和外寄郵件。 在這兩種情況下此保護可以設定為最適，由系統管理員。

網路釣魚篩選根據預設，在 Office 365 中，但應該設定為最適。 以下是我們會建議的防網路釣魚 in EOP。

### <a name="anti-spam"></a>反垃圾郵件

|安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|隔離保留期限    |   是      |     是    |   30 天   |
|使用者垃圾郵件通知頻率   |   是      |     是    |   3 天   |
|應啟用零小時 Autopurge   |   是      |     是    |   True  |
|垃圾郵件偵測動作應該傳送給 | JMF | 隔離 | - |
|高信賴度垃圾郵件偵測動作應該傳送給 | 隔離 | 隔離| - |
|大量偵測動作應該設定為 | JMF | 隔離 | - |
|將大量電子郵件閾值設定為 | 6 | 4 | - |
|應啟用安全提示| True | True | - |
|啟用使用者垃圾郵件通知| 是 | False | - |
|允許寄件者 | 無 | 無 | - |
|允許寄件者網域 | 無 | 無 | - |
|封鎖的寄件者 | 無 | 無 | - |
|封鎖的寄件者網域 | 無 | 無 | - |
|輸出垃圾郵件原則 RRL | 500 | 500 | - |

建議**關閉**，建議和積極等級：

|安全性功能名稱  |
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|

建議使用建議和積極的層級中**開啟**：

|安全性功能名稱  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>反惡意程式碼

|安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|設定內部來源的惡意程式碼通知 |是 |是 |- |
|停用 [通知外部寄件者的惡意程式碼偵測 |是 |是 |- |
|使用 「 一般附件類型篩選器 」 封鎖可疑的檔案類型 | 是 |是 |- |
|惡意程式碼 ZAP |True |True |- |
|惡意程式碼巨集指令 |封鎖 |封鎖 |- |

### <a name="anti-phishing"></a>反網路釣魚

|安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|零小時 Autopurge 應啟用-Phish| True | True | - | 
|應設 phish 偵測巨集指令 | 隔離-要求 | 隔離-系統管理員 | - |
|高信賴度 Phish 偵測動作應該設定為 | 隔離-系統管理員 | 隔離-系統管理員 | - |
|EnableMailboxIntelligence | True | True | - |
|EnableSimilarUsersSafetyTips | True | True | - |
|EnableSimilarDomainsSafetyTips | True | True | - |
|EnableUnusualCharactersSafetyTips | True | True | - |
|TargetedUserProtectionAction |NoAction |封鎖 | - |
|MailboxIntelligenceProtectionAction |NoAction |封鎖 | - |
|TargetedDomainProtectionAction |NoAction |封鎖 | - |
|AuthenticationFailAction |MoveToJmf |隔離 | - |
|AntiSpoofEnforcementType |高 |高 | - |
|EnableAuthenticationSafetyTip |False |是 | - |
|EnableAntiSpoofEnforcement |True |True | - |
|EnableUnauthenticatedSender |True |True | - |
|EnableAuthenticationSoftPassSafetyTip |False |是 | - |
|TreatSoftPassAsAuthenticated |是 |False | - |
|EnableSuspiciousSafetyTip |True |True | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Office 365 進階威脅防護 (ATP) 的安全性

更早版本，我可以說過它已鼓勵新增 Office 365 ATP 計劃 1 或將更多完全實現 ATP 計劃 2 的 E3 訂閱。 進階的反網路釣魚原因是其中一個原因。 啟用根據預設，反網路釣魚***必須***使用操作原則設定。 忘記要設定防網路釣魚原則會公開使用者風險，請務必步驟 2 之後，新增 ATP 訂用帳戶。

> [!IMPORTANT]
>  如果您有 E5 訂閱，您目前已[ATP 計劃 2](https://products.office.com/exchange/advance-threat-protection)。 當您想要了解[what's new in ATP](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff)，請檢查此連結。

### <a name="advanced-anti-phishing"></a>進階的反網路釣魚

網路釣魚會嘗試誤認為聲譽良好的公司或目的竊取像是信用卡號碼，或電腦或裝置的 pin 碼或密碼的個人資訊的人員。 網路釣魚可以包含：

- **詐騙**，spoofers 嘗試傳送代表特定目標的郵件中的網域 (例如，ellar@2020contoso.com 嘗試傳送郵件的 ellar@2020litware.com （案例電子郵件的驗證方法可以幫助阻止）。 

- **模擬**，郵件所在收到其寄件者是以視覺方式類似 （或酷似） 至目標網域或使用者名稱。 壞動作項目在這裡，模擬特定的使用者名稱，或偽裝為 [從目標網域傳送郵件。 以下是 pretense 網域： ellar@2020|itware.com，並以下的 pretense 使用者： ellα r@2020litware.com （一下密切來捕捉網域與使用者模擬這些範例中的網域和使用者名稱）。

如果您已新增 Office 365 ATP 訂閱至 EOP，請務必設定下列設定。

|安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|若要設定進階網路釣魚的臨界值 | 2 | 4 | - |
|啟用反模擬保護 | 是 | 是 | - |
|啟用反模擬原則中的信箱智慧 | 是 | 是 | - |
|啟用信箱智慧基礎模擬保護 | 是 | 是 | - |
|應網域模擬巨集指令 | JMF | 隔離 | - |
|使用者模擬動作應該是 | JMF | Qurantine | - |
|信箱智慧基礎模擬保護動作應該是 |提示  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>安全連結和安全附件

 ATP 包含安全附件和安全連結原則防止傳遞，潛在惡意附件的電子郵件，並讓使用者從按一下與出差具有潛在危險性的 url。

#### <a name="safe-links"></a>安全連結

|安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|ATP 安全連結應該追蹤使用者點選為了回應 |是 |是 |- |
|Office 應用程式應該啟用 ATP 安全連結 |是 |是 |- |
|ATP 安全連結應啟用內部網域 |是 |是 |- |
|ATP 安全連結應該套用即時 URL 掃描可疑連結以及指向檔案的連結。 |是 |是 |- |
|ATP 安全連結應等待傳遞郵件之前，要完成掃描的 URL。 |是 |是 |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>安全附件

|安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|ATP 安全附件原則動作應該是 |隔離 |隔離 |- |
|應啟用 ATP 保護 OneDrive、 SharePoint 和 microsoft Teams |是 |是 |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>其他設定

這些設定涵蓋的功能不一定符合上述的特定類別的範圍。 您也可能會發現部分 1 關閉設定以下。

安全性功能名稱  |建議使用 |積極  |註解  |
|---------|---------|---------|---------|
|建立 SPF 記錄 |是 |是 |- |
|設定 DKIM 簽章的網域 |是 |是 |- |
|拒絕] 或 [隔離] 動作與實作網域型郵件報告和符合性聲明 (DMARC) |動作 = 無 |動作 = 拒絕 | |
|部署報告郵件附加元件，以改善使用者報告的可疑的電子郵件 |是 |是 |- |
|排程惡意軟體和垃圾郵件報告 |是 |是 |- |
|應該不允許或監視自動-fowarding 至外部網域 |- |是 |- |
|應啟用整合的稽核 |是 |是 |- |
|在不需要，應停用 IMAP |- |停用 |- |
|在不需要，應停用 POP |- |停用 |- |
|SMTP 驗證提交應該關閉此功能時不需要的應用程式 |- |停用 |- |
|EWS 應該停用 |- |停用 |- |
|PowerShell |- |停用 |- |
|設定寄件者原則架構，以完全未通過 |-all |-all |- |
|Whitelist 寄件者盡可能使用詐騙智慧 |是 |是 |- |
|目錄架構邊緣封鎖 (DBEB) |已啟用 |已啟用 |網域類型 = 代表性頁面 |
