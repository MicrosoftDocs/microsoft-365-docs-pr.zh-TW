---
title: 反垃圾郵件保護常見問題集
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以在 Exchange Online Protection (EOP) 中查看有關反垃圾郵件保護的常見問題及解答。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae91e1184d8b95b936065f785b3c6bfecf9f250f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204879"
---
# <a name="anti-spam-protection-faq"></a>反垃圾郵件保護常見問題集

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本主題提供 Exchange Online 中的信箱、獨立 Exchange Online Protection (EOP) 組織中的 Microsoft 365 組織的反惡意程式碼保護的常見問題和解答，但沒有 Exchange Online 信箱。

如需有關隔離區的問題與解答，請參閱[隔離常見問題集](quarantine-faq.md)。

如需有關反惡意程式碼保護的問題和解答，請參閱 [反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)。

如需反欺騙保護的相關問題和解答，請參閱 [反欺騙保護常見問題](anti-spoofing-protection-faq.md)。

## <a name="by-default-what-happens-to-a-spam-detected-message"></a>依預設，偵測到垃圾郵件會發生什麼情況？

若 **為輸入郵件：** 大部分的垃圾郵件是透過連線篩選刪除，這是根據來源電子郵件伺服器的 IP 位址。 反垃圾郵件原則 (又稱為垃圾郵件篩選原則或內容篩選原則) 會以垃圾郵件、大量或網路釣魚形式檢查和分類郵件。 依預設，歸類為垃圾郵件或大量的郵件會傳遞至收件者的 [垃圾郵件] 資料夾，並會隔離分類為網路釣魚的郵件。 您可以修改預設的反垃圾郵件原則 (套用至所有收件者) ，也可以以更嚴格的使用者群組設定來建立自訂反垃圾郵件原則 (例如，您可以隔離傳送給主管的垃圾郵件) 。 如需詳細資訊，請參閱 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md) 和 [建議的反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

> [!IMPORTANT]
> 在 EOP 保護內部部署信箱的混合部署中，您必須在內部部署 Exchange 組織中設定兩個 Exchange 郵件流程規則 (，也稱為傳輸規則) ，以偵測新增至郵件的 EOP 垃圾郵件篩選標頭。 如需詳細資訊，請參閱[設定獨立版 EOP 將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

 **輸出郵件：** 郵件是透過 [高風險傳遞集](high-risk-delivery-pool-for-outbound-messages.md) 區路由傳送，或是傳回給寄件者的未傳遞回報 (也稱為 NDR 或退回郵件) 。 如需輸出垃圾郵件保護的詳細資訊，請參閱 [輸出垃圾郵件控制](outbound-spam-controls.md)。

## <a name="whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>哪一天是垃圾郵件變種，服務是如何處理的？

零天垃圾郵件變種是一種最近產生的垃圾郵件變種，永遠不會被捕獲或分析，所以反垃圾郵件篩選器還沒有任何可供您偵測的資訊。 在垃圾郵件分析員取得並分析零天的垃圾郵件樣本（如果它符合垃圾郵件分類準則）之後，我們會更新反垃圾郵件篩選器以偵測它，而且不會再視為「零一天」。

**附注：** 如果您收到的郵件可能是零天的垃圾郵件變種，為了協助我們改善服務，請使用 [報表訊息和](report-junk-email-messages-to-microsoft.md)檔案中所述的其中一種方法，將郵件提交給 microsoft。

## <a name="do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>是否需要設定服務以提供反垃圾郵件保護？

在您註冊服務並新增您的網域之後，就會自動啟用垃圾郵件篩選。 根據預設，垃圾郵件篩選功能會針對混合環境) 中的獨立 EOP 獨立客戶，調整您不需要任何其他設定 (的保護。 以管理員身分，您可以編輯預設的垃圾郵件篩選設定，以最符合組織的需求。 為了獲得更多細微性，您也可以建立反垃圾郵件原則和輸出的反垃圾郵件原則，套用至組織中的指定使用者、群組或網域。 自訂原則一律優先於預設原則，但您可以變更自訂原則的優先順序 (亦即執行順序)。

如需詳細資訊，請參閱下列主題：

[EOP 和 Microsoft Defender for Office 365 安全性的建議設定](recommended-settings-for-eop-and-office365.md)

[在 EOP 中設定連線篩選](configure-the-connection-filter-policy.md)

[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)

[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)

## <a name="if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>如果我對反垃圾郵件原則進行變更，請在將變更儲存至其之後所需的時間，才會生效？

最多可能需要1小時，變更才會生效。

## <a name="is-bulk-email-filtering-automatically-enabled"></a>是否自動啟用大量電子郵件篩選？

是。 如需大量電子郵件的詳細資訊，請參閱 [垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。

## <a name="does-the-service-provide-url-filtering"></a>服務是否提供 URL 篩選？

是的，服務具有 URL 篩選器，可檢查郵件中的 URLs。 如果偵測到與已知垃圾郵件或惡意內容相關聯的 URLs，郵件會標示為垃圾郵件。

## <a name="how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>使用服務的客戶如何才能將非垃圾郵件) 的郵件傳送給「假負數 (垃圾郵件) 和誤報 (？

客戶可以透過多種方式將垃圾郵件與非垃圾郵件提交給 Microsoft 以進行分析。 如需詳細資訊，請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。

## <a name="can-i-get-spam-reports"></a>我是否可以取得垃圾郵件報告？

是，例如，您可以在 Microsoft 365 系統管理中心取得垃圾郵件偵測報告。 報告內容會將呈現垃圾郵件唯一的郵件的樹木。 如需報告的詳細資訊，請參閱下列連結：

Exchange Online 客戶：[在 Exchange Online 中監控、報告和執行郵件追蹤](/exchange/monitoring/monitoring) (部分機器翻譯)

獨立 EOP 客戶： [在 Exchange Online Protection 中報告和郵件追蹤](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>某人傳送給我訊息，但找不到。 我懷疑它可能被偵測為垃圾郵件。 是否有可用來找出的工具？

有的，郵件追蹤工具可讓您追蹤透過此服務的電子郵件，以了解這些電子郵件的處理情形。 如需關於如何使用郵件追蹤工具來查出郵件為何被標示為垃圾郵件的詳細資訊，請參閱[郵件是否被標示為垃圾郵件？](/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam) (部分機器翻譯)

## <a name="will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>如果我的使用者已傳送輸出垃圾郵件，服務節流是否會) 我的郵件 (速率限制？

如果在特定時間範圍內通過服務從使用者傳送的郵件超過一半 (例如，每小時) ，則會將使用者判斷為垃圾郵件。 EOP 會封鎖使用者傳送郵件。 在大多數情況下，系統若判定輸出郵件是垃圾郵件，則會透過高風險傳遞集區進行路由傳送，以減少正常的輸出 IP 集區被新增至封鎖清單的可能性。

您可以在寄件者被禁止對外傳送垃圾郵件時，傳送通知到指定的電子郵件地址。 如需此設定的相關資訊，請參閱[設定輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) (部分機器翻譯)。

## <a name="can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>是否可以搭配 Exchange Online 使用協力廠商的反垃圾郵件和反惡意程式碼提供者？

是。 雖然我們建議您將 MX 記錄指向 Microsoft，但我們意識到有正當的商業原因可將電子郵件路由傳送至 Microsoft first 以外的地方。

- **輸入**：變更您的 MX 記錄以指向協力廠商提供者，然後將郵件重新導向至 EOP 進行其他處理。 如需詳細資訊，請參閱 [在 Exchange Online 中針對連接器的增強型篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- **輸出**：設定從 Microsoft 365 到目的地協力廠商提供者的智慧主機路由。

## <a name="does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>Microsoft 是否有任何有關如何保護自己免受網頁仿冒騙局的保護的檔？

是。 如需詳細資訊，請參閱在 [網際網路上保護您的隱私權](https://support.microsoft.com/help/4091455)

## <a name="are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>垃圾郵件和惡意程式碼是否會進行調查，以供誰傳送或轉接至法律強制執行實體？

此服務著重于垃圾郵件和惡意程式碼偵測和移除，雖然我們有時候可能會調查特別危險或破壞的垃圾郵件或攻擊活動，並爭取 perpetrators。 這可能包括使用法律和數位犯罪單位來減少垃圾郵件傳送者 botnet，封鎖垃圾郵件傳送者使用服務 (（如果他們使用它來傳送輸出的電子郵件) ），並將有關法律強制訴訟的資訊傳遞給法律強制性。

## <a name="what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>您可以使用哪一組最佳的輸出郵件做法，以確保已傳遞郵件？

下列所述的指導方針是傳送輸出電子郵件訊息的最佳作法。

- **來源電子郵件網域應在 DNS 中解析。**

  例如，如果寄件者為 user@fabrikam，網域 fabrikam 會解析為 IP 位址192.0.43.10。

  如果傳送端網域在 DNS 中沒有 A 記錄與 MX 記錄，則無論郵件的內容是否為垃圾郵件訊息，此服務都會透過其較高風險傳遞集區來路由傳送郵件。 如需較高風險傳遞集區的詳細資訊，請參閱[高風險傳遞集區的外寄郵件](high-risk-delivery-pool-for-outbound-messages.md) (部分機器翻譯)。

- **輸出郵件 eserver 應有反向 DNS (PTR) 專案。**

  例如，如果電子郵件來源 IP 位址是192.0.43.10，則反向 DNS 專案應該是 `43-10.any.icann.org` 。 '

- **HELO/EHLO 與 MAIL FROM 命令應一致，且以網域名稱而非 IP 位址的形式存在。**

  HELO/EHLO 命令應設定成符合傳送端 IP 位址的反向 DNS，讓網域在郵件標頭的各個部分間都能保持相同。

- **確實 DNS 中已設定適當的 SPF 記錄。**

  SPF 記錄是一項驗證機制，可驗證從某個網域傳送的郵件是否真的來自該網域而不是詐騙郵件。如需 SPF 記錄的詳細資訊，請參閱下列連結：

  [設定 SPF 以協助防止詐騙 ](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [網域常見問題集](../../admin/setup/domains-faq.yml#how-can-i-validate-spf-records-for-my-domain) (部分機器翻譯)

- **使用 DKIM 簽署電子郵件時，應以寬鬆的規範簽署。**

  如果寄件者要使用 Domain Keys Identified Mail (DKIM) 簽署其郵件，並且要透過此服務傳送輸出郵件，他們應使用寬鬆的標頭規範演算法進行簽署。若使用嚴格的標頭規範進行簽署，簽章可能會在通過此服務時失效。

- **網域擁有者應在 WHOIS 資料庫中具有正確的資訊。**

  如此可識別網域的擁有者，以及如何輸入可靠的母公司、連絡點與名稱伺服器來連絡這些擁有者。

- **若為大量郵件寄件者，[寄件者:]名稱應該反映郵件的傳送者是誰，而郵件的主旨行應該顯示郵件內容的簡短摘要。**

  郵件內文應明確指出所提供的優惠、服務或產品。 例如，如果寄件者為 Contoso 公司寄出大量郵件，其電子郵件的 [寄件者] 與 [主旨] 應類似如下：

  > From:marketing@contoso.com <br> 主旨：聖誕節商品最新型錄！

  以下是說明性不足的錯誤範例：

  > From:user@hotmail.com <br> 主旨：型錄

- **如果傳送大量郵件給眾多收件者，且郵件屬於電子報格式，則應於郵件的最下方提供取消訂閱的方式。**

  取消訂閱選項應類似如下：

  > 本郵件由 sender@fabrikam.com 傳送給 example@contoso.com。 更新設定檔/電子郵件地址 |立即移除與 **SafeUnsubscribe** &trade; |隱私權原則

- **如果傳送大量電子郵件，則應使用雙重加入確認程序來執行清單的取得。如果您是大量郵件的寄件者，雙重加入確認程序會是業界的最佳做法。**

  採用雙重加入確認程序時，使用者必須執行兩個動作，才能註冊行銷郵件：

  1. 首先，使用者必須點選原先未勾選的核取方塊，表示他們選擇要進一步接收行銷者提供的產品服務或電子郵件訊息。

  2. 其次，行銷者會將確認電子郵件傳送至使用者提供的電子郵件地址，要求使用者點選具有時效性的連結，以完成確認動作。

  使用雙重加入確認程序，大量電子郵件寄件者可建立良好聲譽。

- **大量郵件寄件者應建立清楚透明的內容，以示負責：**

  1. 在請收件者將寄件者加入通訊錄的用語中，應明確指出這個加入動作並不保證郵件可以成功送達。

  2. 在郵件內文中建構重新導向連結時，請使用一致的連結樣式。

  3. 不要傳送龐大的影像或附件，或是純由影像呈現的郵件。

  4. 使用追蹤像素 (Web Bug 或指標) 時，請在您的公眾隱私權或 P3P 設定中明確指出有這些項目存在。

- **格式化輸出退回郵件。**

  產生傳遞狀態通知郵件時 (也稱為未傳遞回報、NDRs 或退回郵件) ，寄件者應該遵循 [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt)中所指定的反彈格式。

- **移除因使用者不存在而使郵件退回的電子郵件地址。**

  如果您收到 NDR，指出某電子郵件地址已不再使用，請從您的清單中移除不存在的電子郵件別名。電子郵件地址會隨時間變更，而且使用者有時會棄之不用。

- **使用 Hotmail 的智慧型網路資料服務 (SNDS) 程式。**

  Hotmail 使用名為智慧型網路資料服務的程式，供寄件者查看使用者所提交的投訴。SNDS 是對 Hotmail 傳遞問題進行疑難排解時的主要入口網站。