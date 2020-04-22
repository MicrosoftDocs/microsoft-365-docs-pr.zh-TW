---
title: Microsoft 365 如何使用寄件者原則架構（SPF）來防止欺騙
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: 摘要：本文說明 Microsoft 365 如何在 DNS 中使用寄件者原則架構（SPF） TXT 記錄，以確保目的地電子郵件系統信任從您的自訂網域傳送的郵件。 這適用于從 Microsoft 365 傳送的輸出郵件。 從 Microsoft 365 傳送給 Microsoft 365 內之收件者的郵件，將永遠會透過 SPF。
ms.openlocfilehash: d73fb881b8395c6c1383cca70e506694795f1364
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633987"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a>Microsoft 365 如何使用寄件者原則架構（SPF）來防止欺騙

 **摘要：** 本文說明 Microsoft 365 如何使用 DNS 中的寄件者原則架構（SPF） TXT 記錄，以確保目的地電子郵件系統信任從您的自訂網域傳送的郵件。 這適用于從 Microsoft 365 傳送的輸出郵件。 從 Microsoft 365 傳送給 Microsoft 365 內之收件者的郵件，將永遠會透過 SPF。

SPF TXT 記錄是一種 DNS 記錄，可驗證電子郵件的來源網域名稱，有助於防止詐騙和網路釣魚。 SPF 藉由驗證寄件者的 IP 位址對照傳送網域的擁有者，來驗證電子郵件的來源。

> [!NOTE]
> 在 2014 年，SPF 記錄類型已被網際網路工程任務推動小組 (IETF) 所取代。 因此，確保您在 DNS 中使用 TXT 記錄來發佈您的 SPF 資訊。 為了清晰明瞭，本文的其餘部分會使用 SPF TXT 記錄一詞。

網域系統管理員會在 DNS 的 TXT 記錄中發佈 SPF。 SPF 資訊可識別已獲授權的外寄電子郵件伺服器。 目的電子郵件系統會驗證郵件來自於已獲授權的外寄電子郵件伺服器。 如果您已熟悉 SPF，或您有簡單的部署，但只需要知道要在 Microsoft 365 的 DNS 中包含的 SPF TXT 記錄，您可以在[microsoft 365 中設定 spf 以協助防止欺騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 [！附注] 如果您沒有在 Microsoft 365 中完全裝載的部署，或是您想要瞭解 SPF 如何運作的詳細資訊，或如何疑難排解 Microsoft 365 的 SPF，請繼續閱讀。

> [!NOTE]
> 以往，如果您也使用 SharePoint Online，則必須新增不同的 SPF TXT 記錄至您的自訂網域。 你不再需要這樣做。 此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。 您不需要立即進行任何變更，但是如果您收到「太多查閱」錯誤，請修改您的 SPF TXT 記錄，如[Set UP SPF In Microsoft 365 中所述，以協助防止欺騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a>SPF 如何運作，以避免 Microsoft 365 中的欺騙和網路釣魚
<a name="HowSPFWorks"> </a>

SPF 決定是否允許寄件者代表網域傳送。 如果不允許收件者這麼做，也就是說，如果電子郵件未通過接收伺服器上的 SPF 檢查，則在該伺服器上設定的垃圾郵件原則會決定該郵件的處理方式。

每個 SPF TXT 記錄都包含三個部分：屬於 SPF TXT 記錄的宣告、能夠從您的網域及可代表您網域傳送的外部網域傳送郵件的 IP 位址，以及強制規則。 有效的 SPF TXT 記錄需要具備這三個部分。 本文說明您如何形成 SPF TXT 記錄，並提供使用 Microsoft 365 中服務的最佳作法。 此外，也提供與網域註冊機構一起努力將記錄發佈到 DNS 的相關指示的連結。

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a>SPF 基本概念：能夠從您的自訂網域傳送的 IP 位址
<a name="SPFBasicsIPaddresses"> </a>

查看 SPF 規則的基本語法：

v=spf1 \<IP\> \<強制規則\>

例如，假設 contoso.com 有下列 SPF 規則：

v=spf1 \<IP 位址 #1\> \<IP 位址 #2\> \<IP 位址 #3\> \<強制規則\>

在此範例中，SPF 規則會指示接收電子郵件伺服器僅接受來自 contoso.com 網域的下列 IP 位址的郵件：

- IP 位址 #1

- IP 位址 #2

- IP 位址 #3

此 SPF 規則會告訴接收電子郵件伺服器，如果郵件來自 contoso.com，而不是來自這三個 IP 位址之一，則接收伺服器應將強制規則套用至該郵件。 強制規則通常為下列其中一個選項：

- **封鎖性失敗。** 在郵件信封中將此郵件標示為「封鎖性失敗」，然後遵循接收伺服器針對這類郵件設定的垃圾郵件原則。

- **非封鎖性失敗。** 在郵件信封中將此郵件標示為「非封鎖性失敗」。 通常電子郵件伺服器會設定為無論如何都會傳遞這些郵件。 大部分的使用者都不會看到此標記。

- **中性。** 不執行任何動作，也就是不要標示郵件信封。 這通常會為了進行測試而保留，但很少使用。

下列範例顯示 SPF 在不同情況下的運作方式。 在這些範例中，contoso.com 是寄件者，而 woodgrovebank.com 是接收者。

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a>範例 1：直接從寄件者傳送到接收者之訊息的電子郵件驗證
<a name="spfExample1"> </a>

從寄件者到接收者的路徑是直接路徑時，SPF 的效果最好，例如：

![此圖顯示 SPF 如何驗證直接從伺服器傳送至伺服器的電子郵件。](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

當 woodgrovebank.com 收到訊息時，如果 IP 位址 #1 位於 contoso.com 的 SPF TXT 記錄中，則訊息會通過 SPF 檢查並經過驗證。

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a>範例2：偽造的寄件者位址未通過 SPF 檢查
<a name="spfExample2"> </a>

假設網路釣魚者找到欺騙 contoso.com 的方法：

![此圖顯示 SPF 如何驗證從偽造的伺服器所傳送的電子郵件。](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

由於 IP 位址 #12 不在 contoso.com 的 SPF TXT 記錄中，所以郵件無法通過 SPF 檢查，而接收者可選擇將其標示為垃圾郵件。

### <a name="example-3-spf-and-forwarded-messages"></a>範例3：SPF 和轉寄的訊息
<a name="spfExample3"> </a>

SPF 的其中一個缺點就是已轉寄電子郵件時就無法運作。 例如，假設 woodgrovebank.com 的使用者已設定轉寄規則，以將所有電子郵件傳送到 outlook.com 帳戶：

![此圖顯示 SPF 在訊息被轉送時無法驗證電子郵件。](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

這封郵件原先在 woodgrovebank.com 通過 SPF 檢查，但在 outlook.com 未通過 SPF 檢查，因為 IP #25 不在 contoso.com 的 SPF TXT 記錄中。 Outlook.com 接著可能會將郵件標示為垃圾郵件。 若要解決此問題，請將 SPF 與其他電子郵件驗證方法 (例如 DKIM 和 DMARC) 搭配使用。

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a>SPF 基本概念：包括可代表您的網域傳送郵件的第三方網域
<a name="SPFBasicsIncludes"> </a>

除了 IP 位址以外，您也可以將 SPF TXT 記錄設定為包含網域作為寄件者。 這些網域會以 "include" 陳述式形式新增到 SPF TXT 記錄。 例如，contoso.com 可能想包含來自 contoso.net 及其從屬 contoso.org 的郵件伺服器的所有 IP 位址。 為了這麼做，contoso.com 會發佈類似以下的 SPF TXT 記錄：

```text
v=spf1 include:contoso.net include:contoso.org -all
```

當接收伺服器在 DNS 中看到此記錄時，也會在 contoso.net 的 SPF TXT 記錄上執行 DNS 查閱，然後再針對 contoso.org 執行 DNS 查閱。如果在 contoso.net 或 contoso.org 的記錄內發現額外的 include 陳述式，也會遵循上述動作。 為了防止拒絕服務攻擊，單一電子郵件的 DNS 查閱上限為 10。 每個 include 陳述式都代表一個額外的 DNS 查閱。 如果訊息超過 10 個限制，該訊息便無法通過 SPF。 當訊息達到此限制 (視接收伺服器的設定方式而定)，寄件者可能會收到一則訊息，指出訊息產生「太多查閱」，或「已超過郵件的最大躍點計數」(這可能發生於查閱執行迴圈並超越 DNS 逾時的時候)。 如需如何避免這種情況的秘訣，請參閱[疑難排解： Microsoft 365 中 SPF 的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a>您的 SPF TXT 記錄和 Microsoft 365 的需求
<a name="SPFReqsinO365"> </a>

如果您在設定 Microsoft 365 時設定郵件，您已建立 SPF TXT 記錄，將 Microsoft 郵件伺服器識別為您的網域合法的郵件來源。 此記錄如下所示：

```text
v=spf1 include:spf.protection.outlook.com -all
```

如果您是完全主控的客戶，也就是沒有任何內部部署郵件伺服器傳送輸出郵件，這是您需要為 Office 365 發行的唯一 SPF TXT 記錄。

如果您有混合式部署（也就是，您的某些信箱在內部部署和部分主控于 Microsoft 365 中，或者如果您是 Exchange Online Protection （EOP）獨立客戶（亦即，您的組織使用 EOP 來保護您的內部部署信箱），則應該將每個內部部署 edge 郵件伺服器的輸出 IP 位址新增至 DNS 中的 SPF TXT 記錄。

## <a name="form-your-spf-txt-record-for-microsoft-365"></a>套用 Microsoft 365 的 SPF TXT 記錄
<a name="FormYourSPF"> </a>

使用本文中的語法資訊，構成自訂網域的 SPF TXT 記錄。 雖然還有其他此處未提及的語法選項，以下是最常使用的選項。 一旦您已形成記錄，您需要在網域註冊機構中更新記錄。

如需您需要在 Microsoft 365 中包含的網域相關資訊，請參閱[SPF 所需的外部 DNS 記錄](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)。 使用[逐步指示](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam)來更新您網域註冊機構的 SPF (TXT) 記錄。

### <a name="spf-txt-record-syntax-for-microsoft-365"></a>Microsoft 365 的 SPF TXT 記錄語法
<a name="SPFSyntaxO365"> </a>

Microsoft 365 的一般 SPF TXT 記錄具有下列語法：

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

例如：

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

其中：

- **v=spf1** 是必要的。 這會將 TXT 記錄定義為 SPF TXT 記錄。

- **ip4** 表示您正在使用 IP 版本 4 位址。 **ip6** 表示您正在使用 IP 版本 6 位址。 如果您使用 IPv6 IP 位址，請將本文範例中的 **ip4** 換成 **ip6**。 您也可以使用 CIDR 表示法來指定 IP 位址範圍，例如 **ip4:192.168.0.1/26**。

- 「IP 位址」__ 是您要新增至 SPF TXT 記錄的 IP 位址。 通常，這是貴組織的外寄郵件伺服器的 IP 位址。 您可以列出多個外寄郵件伺服器。 如需詳細資訊，請參閱[範例：多個輸出內部部署郵件伺服器和 Microsoft 365 的 SPF TXT 記錄](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)。

- 「網域名稱」__ 是您要新增為合法寄件者的網域。 如需您應為 Microsoft 365 包含的功能變數名稱清單，請參閱[SPF 所需的外部 DNS 記錄](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records)。

- 強制規則通常為下列其中一項：

  - -all

    表示封鎖性失敗。 如果您知道您網域的所有授權 IP 位址，請在 SPF TXT 記錄中列出這些位址，並使用 -all (封鎖性失敗) 限定詞。 此外，如果您只使用 SPF，也就是您使用的不是 DMARC 或 DKIM，則應該使用 -all 限定詞。 建議您一律使用這個限定詞。

  - ~all

    表示非封鎖性失敗。 如果您不確定是否有完整的 IP 位址清單，則應該使用 ~all (非封鎖性失敗) 限定詞。 此外，如果您使用 p=quarantine 或 p=reject 的 DMARC，則可使用 ~ all。 否則，使用 -all。

  - ?all

    表示中性。 這在測試 SPF 時使用。 不建議您在即時部署中使用此限定詞。

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a>範例： Microsoft 365 傳送所有郵件時使用的 SPF TXT 記錄
<a name="ExampleSPFNoSP"> </a>

如果所有的郵件都是由 Microsoft 365 傳送，請在您的 SPF TXT 記錄中使用此功能：

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a>範例：具有一個內部部署 Exchange Server 和 Microsoft 365 的混合式案例的 SPF TXT 記錄
<a name="ExampleSPFHybridOneExchangeServer"> </a>

在混合式環境中，如果內部部署 Exchange Server 的 IP 位址是 192.168.0.1，若要將 SPF 強制規則設為封鎖性失敗，請構成如下所示的 SPF TXT 記錄：

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a>範例：多個輸出內部部署郵件伺服器和 Microsoft 365 的 SPF TXT 記錄
<a name="ExampleSPFMultipleMailServerO365"> </a>

如果您有多部外寄郵件伺服器，請將每部郵件伺服器的 IP 位址包含在 SPF TXT 記錄中，並使用一個空格再加上 "ip4:" 陳述式來分隔每個 IP 位址。 例如：

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a>後續步驟：設定 Microsoft 365 的 SPF
<a name="SPFNextSteps"> </a>

一旦您已制定 SPF TXT 記錄，請遵循在[Microsoft 365 中設定 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)中的步驟，協助防止哄騙將其新增至您的網域。

雖然 SPF 的設計訴求是要協助防止詐騙，但是有 SPF 無法防護的詐騙技術。 為了避免這些情況，在您設定 SPF 之後，您也應該設定 DKIM 和 DMARC for Microsoft 365。 若要開始使用，請參閱[使用 DKIM 驗證從 Microsoft 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。 接下來，請參閱[使用 DMARC 驗證 Microsoft 365 中的電子郵件](use-dmarc-to-validate-email.md)。

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a>疑難排解： Microsoft 365 中 SPF 的最佳作法
<a name="SPFTroubleshoot"> </a>

您只能為您的自訂網域建立一筆 SPF TXT 記錄。 建立多筆記錄會導致循環配置情況，且 SPF 會失敗。 若要避免這種情況，您可以為每個子網域建立不同的記錄。 例如，為 contoso.com 建立一筆記錄，並為 bulkmail.contoso.com 建立另一筆記錄。

如果電子郵件在傳遞前造成超過 10 個 DNS 查閱，則接收郵件伺服器將會以永久性錯誤 (也稱為 permerror__) 回應，並導致該郵件未通過 SPF 檢查。 接收伺服器也可能會以包含類似以下錯誤的未傳遞回報 (NDR) 回應：

- 郵件超過躍點計數。

- 郵件需要太多查閱。

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a>在使用協力廠商網域與 Microsoft 365 時，避免出現「太多查閱」錯誤
<a name="SPFTroubleshoot"> </a>

第三方網域的部分 SPF TXT 記錄會引導接收伺服器直接執行大量 DNS 查閱。 例如，在撰寫本文時，Salesforce.com 在其記錄中包含 5 個 include 陳述式：

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

為了避免此錯誤，您可以在任何人傳送大量電子郵件時實作原則，例如必須特別為此目的使用子網域。 然後為包含大量電子郵件的子網域定義不同的 SPF TXT 記錄。

 在某些情況下 (例如 salesforce.com 範例)，您必須在 SPF TXT 記錄中使用此網域，但是在其他情況下，第三方可能已經建立了子網域供您用於此目的。 例如，exacttarget.com 已建立了您必須用於 SPF TXT 記錄的子網域：

```text
cust-spf.exacttarget.com
```

當您在 SPF TXT 記錄中包含第三方網域時，您必須向第三方確認要使用哪個網域或子網域，以避免遇到 10 個查閱限制。

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a>如何檢視您目前的 SPF TXT 記錄，並決定其所需的查閱數目
<a name="SPFTroubleshoot"> </a>

您可以使用 nslookup 來檢視您的 DNS 記錄，包括您的 SPF TXT 記錄。 或者，如果想要，有許多免費的線上工具可讓您用來檢視 SPF TXT 記錄的內容。 查看您的 SPF TXT 記錄並遵循 include 陳述式和重新導向鏈，即可決定記錄需要多少個 DNS 查閱。 有些線上工具甚至會為您計算並顯示這些查閱。 追蹤此數字有助於防止從貴組織傳送的郵件觸發來自接收伺服器的永久性錯誤 (稱為 permerror)。

## <a name="for-more-information"></a>如需詳細資訊
<a name="SPFTroubleshoot"> </a>

需要新增 SPF TXT 記錄的說明嗎？ 閱讀此文章[：在任何 dns 主機服務提供者（適用于 microsoft 365）上建立 dns 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam)，以取得與 microsoft 365 中的自訂網域使用的寄件者原則架構的詳細資訊。 [反垃圾郵件訊息標頭](anti-spam-message-headers.md)包含 Microsoft 365 用於 SPF 檢查的語法及標頭欄位。


