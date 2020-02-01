---
title: 反垃圾郵件保護常見問題集
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: 本主題提供有關反垃圾郵件保護的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection (EOP) 客戶。
ms.openlocfilehash: 9be51b4967a558aec254262052d7c01446a7d643
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599870"
---
# <a name="anti-spam-protection-faq"></a>反垃圾郵件保護常見問題集

本主題提供有關反垃圾郵件保護的常見問題與解答。這些解答適用於 Microsoft Exchange Online 及 Exchange Online Protection (EOP) 客戶。

> [!TIP]
> 如需有關安全寄件者清單與封鎖寄件者清單的問題與解答，請參閱[Exchange Online 安全寄件者和封鎖寄件者清單](safe-sender-and-blocked-sender-lists-faq.md) (部分機器翻譯)。 如需有關隔離區的問題與解答，請參閱[隔離常見問題集](quarantine-faq.md)。

 **問：偵測到的垃圾郵件預設會受到怎麼樣的處理？**

答： **若為輸入郵件：** 大部分的垃圾郵件是由連線篩選根據寄件者 IP 位址予以刪除。然後服務就會檢查郵件的內容。依預設，依內容篩選出的垃圾郵件會傳送至收件者的 [垃圾郵件] 資料夾。您可以變更此動作。例如，您可以設定內容篩選原則，選擇將垃圾郵件訊息傳送至隔離區。

> [!IMPORTANT]
> 針對 EOP 獨立客戶：為確保 [將郵件移至垃圾郵件資料夾]**** 動作能夠在內部部署信箱中運作，您必須在內部部署伺服器上設定兩項 Exchange 郵件流程規則 (也稱為傳輸規則)，以偵測由 EOP 新增的垃圾郵件標頭。 如需詳細資訊，請參閱[確定垃圾郵件路由傳送至每一個使用者的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

 **若為輸出郵件：** 郵件已透過較高風險傳遞集區路由傳送或已退回並未傳遞，在此情況下，寄件者應該會收到傳遞狀態通知 (DSN) 郵件，從中得知此郵件無法傳遞。

 **問：什麼是零時差垃圾郵件變體以及服務處理的方式為何？**

答： 零時差垃圾郵件變體是第一代垃圾郵件變體，從前從未擷取或分析過的變體，因此垃圾郵件內容篩選器尚無任何可供偵測的資訊。 一旦零時差垃圾郵件樣本由垃圾郵件分析人員擷取和分析之後，如果符合垃圾郵件分類條件，則垃圾郵件內容篩選器將會更新以進行偵測，並且不再視為「零時差」。 (**請注意：** 如果您收到一封電子郵件，可能是零時差垃圾郵件變體，為協助我們改進服務，請使用[向 Microsoft 提交垃圾郵件、非垃圾郵件及網路釣魚詐騙郵件進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md) (英文) 中所述的其中一種方法，將郵件提交給 Microsoft，以供分析。)

 **問：我是否需要將此服務設定為提供反垃圾郵件保護？**

答：在您註冊此服務並新增自己的網域後，此服務即會透過預設的反垃圾郵件原則對整個公司啟用垃圾郵件篩選功能。預設的原則已調整為無須進行任何額外設定 (除了針對 EOP 獨立版客戶提及的上述例外狀況)，即可保護您。如果您是系統管理員，您可以編輯預設的反垃圾郵件原則，使其確切符合貴組織的需求。若要提高精確性，您也可以建立自訂的內容篩選原則，並套用至組織中指定的使用者、群組或網域。自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。

如需設定反垃圾郵件原則的相關資訊，請參閱下列主題：

[設定連線篩選原則](configure-the-connection-filter-policy.md) (英文)

[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)

[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) (部分機器翻譯)

 **問：如果我對反垃圾郵件原則進行變更並儲存變更，這些變更經過多久才會生效？**

答：最多可能需要 1 小時，變更才會生效。

 **問：大量電子郵件篩選功能是否會自動啟用？**

答： 根據預設，系統會為新客戶啟用 **大宗郵件**進階垃圾郵件篩選選項。 對於遷移而來的客戶，此設定將會與您的 FOPE 組態相符。 如需大宗郵件的詳細資訊，請參閱[垃圾郵件與大宗郵件有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md) (部分機器翻譯)

 **問：此服務是否提供 URL 篩選？**

答：是，此服務有 URL 篩選器可檢查郵件內的 URL。如果偵測到與已知垃圾郵件或惡意內容相關聯的 URL，則會將郵件標示為垃圾郵件。

 **問：客戶可以如何使用此服務將誤判正常 (是垃圾郵件) 和誤判 (非垃圾郵件) 的郵件傳送給 Microsoft？**

答： 客戶可以透過多種方式將垃圾郵件與非垃圾郵件提交給 Microsoft 以進行分析。 如需詳細資訊，請參閱[將垃圾郵件、非垃圾郵件與網路釣魚詐騙郵件提交給 Microsoft 進行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md) (英文)。

 **問：我是否可以取得垃圾郵件報告？**

答： 是，例如，您可以在 Microsoft 365 系統管理中心取得垃圾郵件偵測報告。 報告內容會將呈現垃圾郵件唯一的郵件的樹木。 如需報告的詳細資訊，請參閱下列連結：

Exchange Online 客戶：[在 Exchange Online 中監控、報告和執行郵件追蹤](https://docs.microsoft.com/exchange/monitoring/monitoring) (部分機器翻譯)

Exchange Online Protection 客戶：[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md) (部分機器翻譯)

 **問：有人寄郵件給我，但我找不到。我懷疑該郵件可能被當成垃圾郵件。是否有工具可讓我查明？**

答： 有的，郵件追蹤工具可讓您追蹤透過此服務的電子郵件，以了解這些電子郵件的處理情形。 如需關於如何使用郵件追蹤工具來查出郵件為何被標示為垃圾郵件的詳細資訊，請參閱[郵件是否被標示為垃圾郵件？](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam) (部分機器翻譯)

 **問：如果我的使用者對外傳送垃圾郵件，此服務是否會對我的郵件進行節流 (速率限制)？**

答： 如果 Office 365 判定在特定時間範圍內 (例如每小時)，使用者透過服務傳送的郵件中有一半以上是垃圾郵件，系統將封鎖該使用者傳送郵件。 在大多數情況下，系統若判定輸出郵件是垃圾郵件，則會透過高風險傳遞集區進行路由傳送，以減少正常的輸出 IP 集區被新增至封鎖清單的可能性。

您可以在寄件者被禁止對外傳送垃圾郵件時，傳送通知到指定的電子郵件地址。 如需此設定的相關資訊，請參閱[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) (部分機器翻譯)。

 **問：我是否可以將 Exchange Online 搭配第三方反垃圾郵件和反惡意程式碼提供者來使用？**

答： 可以，您可以設定其他垃圾郵件和惡意程式碼篩選服務來保護 Exchange Online 信箱。 若要對輸入郵件執行此動作，您必須將 MX 記錄變更為指向協力廠商提供者，以將電子郵件重新導向至協力廠商提供者，然後將郵件重新導向至 EOP 進行其他處理。 若要對輸出郵件執行此動作，請將郵件傳遞目的地設定為協力廠商提供者 (智慧主機)。

 **問：Microsoft 是否有任何關於如何自我保護以免於網路釣魚詐騙的文件？**

答： 有的，請參閱[保護您在網際網路上的隱私權](https://support.microsoft.com/help/4091455)

 **問：是否會調查垃圾郵件與惡意程式碼郵件的傳送人，或是將其轉交給執法單位？**

答：雖然我們偶爾會調查特別危險或具破壞性的垃圾郵件或攻擊行動，並追捕其幕後黑手，但此服務的重心主要放在偵測及移除垃圾郵件與惡意程式碼。這之中牽涉到與法律和數位犯罪單位合作打擊濫發垃圾郵件者所控制的殭屍網路 (Botnet)、阻止濫發垃圾郵件者使用服務 (如果他們使用服務來傳送輸出電子郵件)，以及將資訊轉交給執法單位以起訴犯罪行為。

 **問：對外傳送電子郵件時有哪些最佳做法，可確保我的郵件都能順利傳遞？**

答：以下提供的指導方針，是對外傳送電子郵件時的最佳做法。

1. **電子郵件的傳送端網域應在 DNS 中獲得解析。**

    例如，如果寄件者是 user@example.com，網域 example.com 會解析為 IP 位址 192.0.43.10。 如果傳送端網域在 DNS 中沒有 A 記錄與 MX 記錄，則無論郵件的內容是否為垃圾郵件訊息，此服務都會透過其較高風險傳遞集區來路由傳送郵件。 如需較高風險傳遞集區的詳細資訊，請參閱[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md) (部分機器翻譯)。

2. **輸出郵件伺服器的傳送端 IP 位址應具有反向 DNS (PTR) 項目。**

    例如，如果從 IP 位址 192.0.43.10 傳送，此 IP 的反向 DNS 項目是 43-10.any.icann.org。

3. **HELO/EHLO 與 MAIL FROM 命令應一致，且以網域名稱而非 IP 位址的形式存在。**

    HELO/EHLO 命令應設定成符合傳送端 IP 位址的反向 DNS，讓網域在郵件標頭的各個部分間都能保持相同。

4. **確實 DNS 中已設定適當的 SPF 記錄。**

    SPF 記錄是一項驗證機制，可驗證從某個網域傳送的郵件是否真的來自該網域而不是詐騙郵件。如需 SPF 記錄的詳細資訊，請參閱下列連結：

    [在 Office 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

    [網域常見問題集](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) (部分機器翻譯)

5. **使用 DKIM 簽署電子郵件時，應以寬鬆的規範簽署。**

    如果寄件者要使用 Domain Keys Identified Mail (DKIM) 簽署其郵件，並且要透過此服務傳送輸出郵件，他們應使用寬鬆的標頭規範演算法進行簽署。若使用嚴格的標頭規範進行簽署，簽章可能會在通過此服務時失效。

6. **網域擁有者應在 WHOIS 資料庫中具有正確的資訊。**

    如此可識別網域的擁有者，以及如何輸入可靠的母公司、連絡點與名稱伺服器來連絡這些擁有者。

7. **若為大量郵件寄件者，[寄件者:]名稱應該反映郵件的傳送者是誰，而郵件的主旨行應該顯示郵件內容的簡短摘要。**

    郵件內文應明確指出所提供的優惠、服務或產品。 例如，如果寄件者為 Contoso 公司寄出大量郵件，其電子郵件的 [寄件者] 與 [主旨] 應類似如下：

    From:marketing@contoso.com

    主旨：聖誕節商品最新型錄！

    以下是說明性不足的錯誤範例：

    From:user@hotmail.com

    主旨：型錄

8. **如果傳送大量郵件給眾多收件者，且郵件屬於電子報格式，則應於郵件的最下方提供取消訂閱的方式。**

    取消訂閱選項應類似如下：

    本郵件由 sender@fabrikam.com 傳送給 example@contoso.com。更新個人資料/電子郵件地址 | 使用 **SafeUnsubscribe** 立即取消訂閱 | 隱私權原則

9. **如果傳送大量電子郵件，則應使用雙重加入確認程序來執行清單的取得。如果您是大量郵件的寄件者，雙重加入確認程序會是業界的最佳做法。**

    採用雙重加入確認程序時，使用者必須執行兩個動作，才能註冊行銷郵件：

   1. 首先，使用者必須點選原先未勾選的核取方塊，表示他們選擇要進一步接收行銷者提供的產品服務或電子郵件訊息。

   2. 其次，行銷者會將確認電子郵件傳送至使用者提供的電子郵件地址，要求使用者點選具有時效性的連結，以完成確認動作。

      使用雙重加入確認程序，大量電子郵件寄件者可建立良好聲譽。

10. **大量郵件寄件者應建立清楚透明的內容，以示負責：**

    1. 在請收件者將寄件者加入通訊錄的用語中，應明確指出這個加入動作並不保證郵件可以成功送達。

    2. 在郵件內文中建構重新導向連結時，請使用一致的連結樣式。

    3. 不要傳送龐大的影像或附件，或是純由影像呈現的郵件。

    4. 使用追蹤像素 (Web Bug 或指標) 時，請在您的公眾隱私權或 P3P 設定中明確指出有這些項目存在。

11. **讓輸出的傳遞狀態通知有適當的格式。**

    在產生傳遞狀態通知訊息時，寄件者應遵循 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt) 中指定的退回格式。

12. **移除因使用者不存在而使郵件退回的電子郵件地址。**

    如果您收到 NDR，指出某電子郵件地址已不再使用，請從您的清單中移除不存在的電子郵件別名。電子郵件地址會隨時間變更，而且使用者有時會棄之不用。

13. **使用 Hotmail 的智慧型網路資料服務 (SNDS) 程式。**

    Hotmail 使用名為智慧型網路資料服務的程式，供寄件者查看使用者所提交的投訴。SNDS 是對 Hotmail 傳遞問題進行疑難排解時的主要入口網站。

## <a name="for-more-information"></a>如需詳細資訊

[Office 365 電子郵件的反垃圾郵件保護](anti-spam-protection.md) (部分機器翻譯)

[Exchange Online 中的安全寄件者和封鎖寄件者清單](safe-sender-and-blocked-sender-lists-faq.md) (部分機器翻譯)

[反垃圾郵件訊息標頭](anti-spam-message-headers.md)

[非法回應郵件與 EOP](backscatter-messages-and-eop.md)
