---
title: 疑難排解傳送至 Microsoft 365 的郵件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: 本文提供嘗試將電子郵件傳送至 Microsoft 365 收件匣的寄件者疑難排解資訊，以及大量郵遞至客戶的最佳作法。
ms.openlocfilehash: 89fd6d11cca0d7689203948922b27e46ae2c602a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631142"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>將疑難排解郵件傳送至 Office 365

本文提供嘗試將電子郵件傳送至 Microsoft 365 收件匣的寄件者疑難排解資訊，以及大量郵遞至客戶的最佳作法。

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>疑難排解常見的郵件傳遞至 Office 365 的問題

選擇其中一個經常發生的問題。

- [您是否正在管理您的 IP 和網域的傳送信譽？](#are-you-managing-your-ip-and-domains-sending-reputation)

- [您從新的 IP 位址送出電子郵件嗎？](#are-you-sending-email-from-new-ip-addresses)

- [確認已正確設定 DNS](#confirm-that-your-dns-is-set-up-correctly)

- [確定您未以無法路由傳送的 IP 形式刊登廣告](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [傳送電子郵件給 Office 365 中的使用者時，收到未傳遞回報（NDR）](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [進入在 EOP 中收件者的 [垃圾郵件] 資料夾中的電子郵件](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [EOP 傳輸來自我的 IP 位址的流量](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>您是否正在管理您的 IP 和網域的傳送信譽？

EOP 篩選技術的設計是為了提供 Microsoft 365 的反垃圾郵件保護，以及其他 Microsoft 產品（如 Exchange Server、Microsoft Office Outlook 和 Windows Live Mail）。 我們也會利用 SPF、DKIM 及 DMARC;電子郵件驗證技術，可協助您驗證傳送電子郵件的網域是否獲得授權，以解決哄騙和網路釣魚問題。 EOP 篩選會受到許多與傳送 IP、網域、驗證、清單準確性、投訴率、內容等等相關的因素所影響。 其中一個主要因素是降低寄件者的信譽，並提供電子郵件的能力為垃圾郵件的投訴率。

### <a name="are-you-sending-email-from-new-ip-addresses"></a>您從新的 IP 位址送出電子郵件嗎？

先前未用來傳送電子郵件的 IP 位址，通常不會在我們的系統中建立任何信譽。 因此，來自新 Ip 的電子郵件很可能會遇到傳遞問題。 一旦 IP 已具備未傳送垃圾郵件的信譽，EOP 通常會允許更佳的電子郵件傳遞體驗。

在現有的 SPF 記錄中驗證的網域所新增的新 Ip，通常會有額外的優點，可繼承某些網域的傳送信譽。 如果您的網域有良好的送出信譽，新的 Ip 可能會經歷較短的起步時間。 新的 IP 可以預計會在數個星期內完全 ramped，也可以更快，視數量、清單準確性和垃圾郵件投訴率而定。

### <a name="confirm-that-your-dns-is-set-up-correctly"></a>確認已正確設定 DNS

如需如何建立及維護 DNS 記錄的指示（包括郵件路由所需的 MX 記錄），您必須聯繫您的 DNS 主機服務提供者。

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>確定您未以無法路由傳送的 IP 形式刊登廣告

我們可能不會接受寄件者的電子郵件，而不是寄件者進行反向 DNS 查閱。 在某些情況下，合法寄件者會在嘗試開啟與 EOP 的連線時，宣告自身，將其自我宣告為非網際網路可路由傳送的 IP。 保留用於私人（不可路由傳送）網路的 IP 位址包括：

- 192.168.0.0/16 （或 192.168.0.0-192.168.255.255）

- 10.0.0.0/8 （或 10.0.0.0-10.255.255.255）

- 172.16.0.0/11 （或 172.16.0.0-172.31.255.255）

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>傳送電子郵件給 Office 365 中的使用者時，收到未傳遞回報（NDR）

有些傳遞問題是由 Microsoft 封鎖的寄件者的 IP 位址，或是因為先前的垃圾郵件，將使用者帳戶識別為封鎖的寄件者的結果。 如果您認為您已接收到錯誤 NDR，請先遵循 NDR 訊息中的任何指示來解決問題。

如需您收到之錯誤的詳細資訊，請參閱 Exchange Online 中的[電子郵件未傳遞](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)回報中的錯誤代碼清單。

 例如，如果您收到下列 NDR，它表示 Microsoft 已封鎖傳送 IP 位址。

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

若要從此清單要求移除，您可以[使用取消列出入口網站，將您自己從 [封鎖的寄件者] 清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>進入在 EOP 中收件者的 [垃圾郵件] 資料夾中的電子郵件

如果郵件被 EOP 錯誤地辨識為垃圾郵件，您可以使用收件者將此錯誤的郵件提交給 Microsoft 垃圾郵件分析小組，該小組會評估和分析郵件。 我們可以根據分析的結果調整全服務的垃圾郵件內容篩選規則，以便允許郵件通行。 您可以使用電子郵件將不應該歸類為垃圾郵件的郵件提交給 Microsoft。 這麼做時，請務必使用下列程序中的步驟。

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>使用電子郵件將誤報郵件提交給 Microsoft 垃圾郵件分析小組

1. 儲存您想要提交成非垃圾郵件的郵件。

2. 建立新的空白郵件，然後在其中附加非垃圾郵件。

    您可以視需要附加多個非垃圾郵件。

3. 複製原始郵件的主旨行並貼到新郵件的主旨行中。

    > [!IMPORTANT]
    > 將新郵件的內文保留空白。

4. 將新郵件傳送到 [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com)。

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>EOP 傳輸來自我的 IP 位址的流量

如果您收到來自 EOP 的 NDR，指出您的 IP 位址正由 EOP 節流，例如：

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

您接收到 NDR，因為已偵測到 IP 位址有可疑的活動，而且在進一步評估時會暫時加以限制。 如果懷疑是透過評估加以清除，則會很快解除此限制。

### <a name="i-cant-receive-email-from-senders-in-office-365"></a>我無法從 Office 365 中的寄件者接收電子郵件

 若要從我們的使用者接收郵件，請確定您的網路允許來自 EOP 在我們資料中心使用的 IP 位址的連線。 如需詳細資訊，請參閱[Exchange Online PROTECTION IP 位址](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>大量電子郵件至 Microsoft 365 使用者的最佳作法

如果您經常對 Microsoft 365 使用者執行大量電子郵件行銷活動，並想確保您的電子郵件能夠以安全且及時的方式送達，請遵循本節中的秘訣。

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>確定 [寄件者：] 名稱會反映郵件的寄件者

主旨應該是郵件內容的簡短摘要，郵件內文應該清楚並簡潔指出產品的功能、服務或產品。 例如：

正確：

> 寄件者： marketing@shoppershandbag.com <br/> 主旨：耶誕節季節的更新目錄！

不正確：

> 寄件者： someone@outlook.com <br/> 主旨：型錄

讓使用者更輕鬆地知道您是誰和您正在做什麼時，您將無法透過大多數垃圾郵件篩選器進行傳遞的難度。

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>在行銷活動電子郵件中永遠包含取消訂閱選項

市場宣傳電子郵件（特別是電子報）應始終包含一種從今後電子郵件取消訂閱的方式。 例如：

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

某些寄件者包含此選項的方式是要求收件者將電子郵件傳送至使用中「退訂」的特定別名。 以上的按一下範例並不可取。 如果您選擇要求收件者傳送郵件，請確定當他們按一下此連結時，會預先填入所有必要的欄位。

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>使用雙加入宣告行銷電子郵件或電子報註冊的選項

如果您的公司需要或鼓勵使用者註冊其連絡人資訊，以便存取您的產品或服務，建議採用這種行業最佳作法。 有些公司使其在註冊過程中自動為其使用者註冊行銷電子郵件或電子新聞稿，但這會被視為電子郵件篩選世界的可疑行銷作法。

在註冊過程中，如果「是，請傳送您的簡報」或「是，請傳送我的特價產品」核取方塊預設為選取狀態。預設會選取 [您要傳送給我的特殊產品] 核取方塊。

 建議您改為使用雙重加入宣告選項，也就是說預設會取消選取 [行銷電子郵件或電子報] 的核取方塊。 此外，在提交註冊表單之後，會透過 URL 將驗證電子郵件傳送給使用者，以允許使用者確認他們接收行銷電子郵件的決策。

 這可協助確保只會註冊要接收行銷電子郵件的使用者，進而清除傳送公司的任何可疑電子郵件行銷慣例。

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>確定電子郵件訊息內容透明且可追蹤

同樣重要的是，電子郵件的傳送方式也是其所包含的內容。 建立電子郵件內容時，請使用下列最佳作法，以確保電子郵件篩選服務不會標記您的電子郵件：

- 當電子郵件訊息要求收件者將寄件者新增至通訊錄時，應明確指出這類動作不是傳遞的保證。

- 包含在郵件本文內的重新導向應該類似且一致，而且不會有多個變化。 在此內容中的重新導向是指離郵件的任何東西，例如連結和檔。 如果您有大量的廣告或取消訂閱連結，或更新設定檔連結，它們都應該指向相同的網域。 例如：

  正確：

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  不正確：

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- 避免使用大型圖像和附件的內容，或完全由圖像組成的郵件。

- 您的公開隱私權或 P3P 設定應明確指出追蹤圖元的存在（web 臭蟲或信標）。

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>移除資料庫中不正確的電子郵件別名

資料庫中任何建立回彈的電子郵件別名都不是必要的，而是讓您的外寄電子郵件面臨進一步透過電子郵件篩選服務審查的風險。 確定您的電子郵件資料庫是最新的。
