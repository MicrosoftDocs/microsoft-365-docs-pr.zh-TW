---
title: Microsoft 建議用於透過 EOP 和 Office 365 ATP 的安全性設定的建議，寄件者原則架構、 網域型郵件報告和符合性聲明，DomainKeys Identified Mail 步驟，它如何運作，等
ms.author: tracyp
author: MSFTTracyP
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
description: Exchange Online Protection (EOP) 和進階威脅防護 (ATP) 的安全性設定的最佳做法是什麼？ 標準保護目前建議是什麼？ 如果您想要更嚴格應該使用什麼？ 以及哪些額外讓如果您也可以使用進階威脅防護 (ATP)？
ms.openlocfilehash: d49f465aa66cd3c720e83b28569da2770300067e
ms.sourcegitcommit: 2de2faea7da80712f448e35c2d6c425944013b7e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2019
ms.locfileid: "39204253"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>EOP 和 Office 365 ATP 安全的建議的設定

**Exchange Online Protection (EOP)** 是 Office 365 訂閱的安全性的核心，並協助防止惡意電子郵件送達您的員工的收件匣。 但與 [新增]，更複雜的攻擊新興的每一天，改善的保護，通常需要。 **Office 365 進階的威脅防護 (ATP)** ATP 方案 1 或 ATP 計劃 2 包含額外的功能，可讓系統管理員層級的安全性、 控制項和調查越多。

雖然我們讓安全性系統管理員可以自訂其安全性設定，有兩個 EOP 和建議的 Office 365 ATP 中的安全性層級：**一般**] 及 [**嚴格]**。 每個客戶環境和需求不同，但我們認為郵件篩選設定這些層級可協助防止垃圾的郵件進入您的員工在大多數情況下的收件匣。

本主題說明這些 Microsoft 建議的設定，以協助保護您的 Office 365 使用者。

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>反垃圾郵件、 反惡意程式碼，並在 EOP 中的反網路釣魚保護

反垃圾郵件、 反惡意程式碼，並反網路釣魚是由系統管理員可設定的 EOP 功能。 我們建議下列設定。

### <a name="eop-anti-spam-policy-settings"></a>EOP 反垃圾郵件原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|垃圾郵件偵測巨集指令|將郵件移至垃圾郵件] 資料夾|隔離郵件||
|高信賴度垃圾郵件偵測巨集指令|隔離郵件|隔離郵件||
|網路釣魚電子郵件偵測巨集指令|隔離郵件|隔離郵件||
|高信賴度 Phish 電子郵件偵測巨集指令|隔離郵件|隔離郵件||
|大量電子郵件偵測巨集指令|將郵件移至垃圾郵件] 資料夾|隔離郵件||
|將大量電子郵件閾值設定為|6|4||
|隔離保留期限|30 天|30 天||
|安全提示|開啟|開啟||
|允許寄件者|無|無||
|允許寄件者網域|無|無|新增您自己 （也稱為_公認的網域_） 的允許寄件者清單則不需要的網域。 事實上，則會視為高風險，因為它會建立不佳動作項目到所傳送的郵件，否則會篩選出的機會。使用[詐騙智慧](learn-about-spoof-intelligence.md)安全性 & 合規性中心，在**反垃圾郵件設定**] 頁面上，檢閱所有寄件者是詐騙任一屬於您組織的網域或詐騙的外部網域。|
|封鎖的寄件者|無|無||
|封鎖的寄件者網域|無|無||
|使用者垃圾郵件通知頻率|已啟用|已啟用|3 天|
|零小時自動清除|開啟|開啟|垃圾郵件和 Phish ZAP|
|MarkAsSpamBulkMail|開啟|開啟|此設定只有在 PowerShell|

有數個其他參數呼叫進階垃圾郵件篩選器的反垃圾郵件原則中，會在撰寫本文時被取代。 我們建議的設定，這些是以將其**關閉**標準和嚴格層級：

|安全性功能名稱|
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
|MarkAsSpamSpfRecordHardFail|

#### <a name="eop-outbound-spam-filter-policy-settings"></a>EOP 輸出垃圾郵件篩選原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|輸出垃圾郵件原則的收件者限制-外部每小時的限制|400|500||
|輸出垃圾郵件原則的收件者限制-內部每小時的限制|800|1000||
|輸出垃圾郵件原則的收件者限制-每日的限制|800|1000||
|當使用者超過限制時的動作|禁止使用者傳送郵件|禁止使用者傳送郵件||

### <a name="eop-anti-malware-policy-settings"></a>EOP 反惡意程式碼原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|惡意程式碼偵測回應|否|否|如果電子郵件附件中偵測到惡意程式碼時，郵件會被隔離，並可釋放只能由系統管理員。|
|「 一般附件類型篩選器 」 封鎖可疑的檔案類型|開啟|開啟||
|惡意程式碼零時差自動清除|開啟|開啟||
|通知內部寄件者的未傳遞的郵件|停用|停用||
|外部的寄件者的未傳遞的郵件通知|停用|停用||

### <a name="eop-anti-phishing-policy-settings"></a>EOP 反網路釣魚原則設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|啟用反詐騙保護|開啟|開啟||
|啟用未驗證的寄件者 （標記）|開啟|開啟||
|如果由具有不允許詐騙網域的人所傳送電子郵件|將郵件移至 [收件者的垃圾郵件資料夾|隔離郵件||

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 進階威脅防護安全性

其他安全性優點隨附於 Office 365 進階威脅防護 (ATP) 訂閱。 最新的新聞和資訊，您可以請參閱[What's new in Office 365 ATP](whats-new-in-office-365-atp.md)。

Office 365 ATP 包含安全附件和安全連結原則防止傳遞，潛在惡意附件的電子郵件，並讓使用者從按一下具有潛在危險性的 Url。

> [!IMPORTANT]
> 進階的反網路釣魚是下列其中一個 Office 365 ATP 訂閱的優點。 雖然預設會啟用它，您***必須***設定至少一個反網路釣魚原則，才可開始篩選郵件。 忘記要設定防網路釣魚原則可能會公開風險的電子郵件使用者。 請務必設定防網路釣魚原則之後新增 Office 365 ATP 訂用帳戶。

如果您已新增 Office 365 ATP 訂閱至 EOP，設定下列設定。

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP 防網路釣魚原則設定

EOP 客戶取得基本反網路釣魚如先前所述，但 Office 365 ATP 包含更多的功能和控制項可協助防止、 偵測及修復的攻擊。

|模擬的安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|（編輯模擬原則）將使用者加入保護|開啟|開啟|取決於您的組織，但是我們建議在主要角色新增使用者。 就內部而言，這些可能是您 CEO、 CFO，以及其他資深領導人。 外部，這些可以加入會議的成員] 或 [您的 director 面板。|
|（編輯模擬原則）會自動包含我所擁有的網域|開啟|開啟||
|（編輯模擬原則）包含自訂的網域|開啟|開啟|取決於您的組織，但是我們建議您最常互動，不屬於您新增的網域。|
|如果您指定模擬使用者所傳送電子郵件|隔離郵件|隔離郵件||
|如果您指定模擬網域所傳送電子郵件|隔離郵件|隔離郵件||
|顯示提示模擬使用者|開啟|開啟||
|顯示提示模擬的網域|開啟|開啟||
|顯示提示不尋常的字元|開啟|開啟||
|啟用信箱智慧|開啟|開啟||
|啟用信箱智慧基礎模擬保護|開啟|開啟||
|如果受保護的信箱智慧模擬使用者所傳送的電子郵件|將郵件移至 [收件者的垃圾郵件資料夾|隔離郵件||
|（編輯模擬原則）新增信任的寄件者及網域|無|無|取決於您的組織，但建議您新增為由於模擬只有且不是 [其他篩選器的釣魚程式的使用者或不正確地取得標示的網域。|

|詐騙安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|啟用反詐騙保護|開啟|開啟||
|啟用未驗證的寄件者 （標記）|開啟|開啟||
|如果由具有不允許詐騙網域的人所傳送電子郵件|將郵件移至 [收件者的垃圾郵件資料夾|隔離郵件||
|EnableAuthenticationSafetyTip|True|True|此設定只有在 PowerShell|
|EnableAuthenticationSoftPassSafetyTip|False|True|此設定只有在 PowerShell|
|EnableSuspiciousSafetyTip|False|True|此設定只有在 PowerShell|
|TreatSoftPassAsAuthenticated|對|錯|此設定只有在 PowerShell|

|進階的設定安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|進階的網路釣魚臨界值|2-積極|3-更積極||

### <a name="safe-links-settings"></a>安全連結設定

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|使用 Office 365 應用程式、 Office 中的 ATP 安全連結 for iOS 和 Android|已啟用|已啟用|這屬於 ATP 安全連結原則套用至整個組織|
不會追蹤當使用者按一下 [安全連結|停用|停用|這屬於 ATP 安全連結原則套用至整個組織|
|不要讓使用者按一下原始 url 的安全連結|已啟用|已啟用|這屬於 ATP 安全連結原則套用至整個組織|
|巨集指令在郵件中的未知潛在的惡意 url|開啟|開啟||
|適用於即時 URL 掃描可疑連結以及指向檔案的連結|已啟用|已啟用||
|等待掃描完成後，將郵件傳送 URL|已啟用|已啟用||
|套用至組織內傳送的電子郵件的安全連結|已啟用|已啟用||

### <a name="safe-attachments"></a>安全附件

|安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的 ATP|已啟用|已啟用||
|ATP 安全附件未知惡意程式碼回應|封鎖|封鎖||
|偵測時重新導向附件|已啟用|已啟用|用知道如何判斷附件為惡意程式碼或非安全性系統管理員重新導向至電子郵件地址|
|ATP 安全附件回應如果惡意程式碼掃描附件的逾時或錯誤，就會發生|已啟用|已啟用||

## <a name="miscellaneous-settings"></a>其他設定

這些設定涵蓋的功能不一定符合上述的特定類別的範圍。 某些設定位於外部安全性 & 合規性中心。

安全性功能名稱|標準|嚴格|留言|
|---------|---------|---------|---------|
|[在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|是|是||
|[使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)|是|是||
|[在 Office 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)|是|是|使用巨集指令 = 隔離標準，以及動作的嚴格 = 拒絕。|
|部署報告郵件附加元件，以改善使用者報告的可疑的電子郵件|是|是||
|排程惡意軟體和垃圾郵件報告|是|是||
|自動轉寄至外部網域應該不允許或監視|是|是||
|應啟用整合的稽核|是|是||
|IMAP 連線到信箱|停用|停用||
|POP 信箱連線能力|停用|停用||
|SMTP 驗證送出至信箱|停用|停用||
|EWS 連線到信箱|停用|停用||
|PowerShell 的連線|停用|停用||
|Whitelist 寄件者盡可能使用詐騙智慧|是|是||
|目錄架構邊緣封鎖 (DBEB)|已啟用|已啟用|網域類型 = 代表性頁面|
|[設定所有的系統管理員帳戶的多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|已啟用|已啟用||
