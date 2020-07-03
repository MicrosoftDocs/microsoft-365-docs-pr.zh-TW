---
title: 使用 DMARC 來驗證電子郵件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: 了解如何設定以網域為基礎的訊息驗證、報告和符合性 (DMARC) 來驗證從貴組織傳送的訊息。
ms.openlocfilehash: adc213ec5c47184f997a812425e53a61d7ac2da3
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016318"
---
# <a name="use-dmarc-to-validate-email"></a>使用 DMARC 來驗證電子郵件

以網域為基礎的郵件驗證、報告和一致性 ([DMARC](https://dmarc.org)) 搭配寄件者原則架構 (SPF) 和網域金鑰識別郵件 (DKIM) 來驗證郵件寄件者，並確保目的地電子郵件系統信任您網域傳送的郵件。 搭配 SPF 和 DKIM 來實作 DMARC 可提供額外保護，防範詐騙和網路釣魚電子郵件。 DMARC 可協助接收方郵件系統決定如何處理未通過 SPF 或 DKIM 檢查的您網域傳送的郵件。

> [!TIP]
> 請造訪 [Microsoft 情報安全性聯盟 (MISA)](https://www.microsoft.com/misapartnercatalog) 目錄，以檢視為 Microsoft 365 提供 DMARC 報告的協力廠商。

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a>SPF 和 DMARC 如何共同運作以在 Microsoft 365 中保護電子郵件？

 電子郵件訊息可能包含多個建立者或寄件者地址。 這些地址可用於不同用途。 例如以下地址：

- **「郵件寄件者」地址**：識別寄件者，並指定如果郵件傳遞發生任何問題時要傳送回傳通知的位置 (如未傳遞通知)。 這會顯示在電子郵件訊息的信封部分，而且通常不會由電子郵件應用程式顯示。 這有時稱為 5321.MailFrom 地址或反向路徑地址。

- **「寄件者」地址**：由您的郵件應用程式顯示為寄件者地址的地址。 此地址可識別電子郵件的作者。 也就是負責撰寫郵件的使用者或系統信箱。 這有時稱為 5322.From 地址。

SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:

```text
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S:
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S:
S: https://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

在此文字記錄中，寄件者地址如下：

- 郵件寄件者地址 (5321.MailFrom): phish@phishing.contoso.com

- 寄件者地址 (5322.From): security@woodgrovebank.com

If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.

When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.

## <a name="what-is-a-dmarc-txt-record"></a>什麼是 DMARC TXT 記錄？

Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.

Microsoft 的 DMARC TXT 記錄看起來如下：

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

Microsoft 會將其 DMARC 報告傳送給協力廠商 [Agari](https://agari.com)。 Agari 會收集並分析 DMARC 報告。 請造訪 [MISA 目錄](https://www.microsoft.com/misapartnercatalog)，以檢視更多為 Microsoft 365 提供 DMARC 報告的協力廠商。

## <a name="implement-dmarc-for-inbound-mail"></a>為輸入郵件實作 DMARC

You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a>為 Microsoft 365 的輸出郵件實作 DMARC

If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

 If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:

- [步驟 1：找出您網域的郵件有效來源](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [步驟 2：為網域設定 SPF](#step-2-set-up-spf-for-your-domain)

- [步驟 3：為自訂網域設定 DKIM](#step-3-set-up-dkim-for-your-custom-domain)

- [步驟 4：為網域形成 DMARC TXT 記錄](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a>步驟 1：找出您網域的郵件有效來源

If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:

- 哪些 IP 位址會從我的網域傳送郵件？

- 針對由第三方代表我所傳送的郵件，5321.MailFrom 和 5322.From 網域相符嗎？

### <a name="step-2-set-up-spf-for-your-domain"></a>步驟 2：為網域設定 SPF

現在您有所有有效寄件者的清單，您可以按照步驟[設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。

例如，假設 contoso.com 從 Exchange Online 傳送郵件，其為 IP 位址為 192.168.0.1 的內部部署 Exchange 伺服器和 IP 位址為 192.168.100.100 的 Web 應用程式，則 SPF TXT 記錄呈現如下：

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

最佳作法是，請確定 SPF TXT 記錄包括第三方寄件者。

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a>步驟 3：為自訂網域設定 DKIM

Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.

If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Microsoft 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.

有關為網域設定 DKIM 的相關指示，包括如何為第三方寄件者設定 DKIM 以避免詐騙網域，請參閱 [使用 DKIM 驗證從您的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a>步驟 4：為網域形成 DMARC TXT 記錄

Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365. Form the DMARC TXT record for your domain in the format:

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

其中：

- *網域*是您想要保護的網域。 根據預設，記錄會保護該網域及所有子網域的郵件。 例如，如果您指定 \_dmarc.contoso.com，DMARC 會保護此網域及所有子網域的郵件，例如 housewares.contoso.com 或 plumbing.contoso.com。

- *TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.

- *pct=100* 指出這項規則應 100% 用於電子郵件。

- *policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.

如需使用選項的相關資訊，請參閱[在 Microsoft 365 中實作 DMARC 的最佳作法](#best-practices-for-implementing-dmarc-in-microsoft-365)以熟悉概念。

範例:

- 原則設為 [無]

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- 原則設為 [隔離]

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- 原則設為 [拒絕]

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a>在 Microsoft 365 中實作 DMARC 的最佳作法

You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.

1. 監控實作 DMARC 的影響

    Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.

    You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.

2. 要求外部郵件系統隔離未通過 DMARC 的郵件

    When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.

3. 要求外部郵件系統不接受未通過 DMARC 的郵件

    The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a>Microsoft 365 如何處理未通過 DMARC 的輸出電子郵件

如果郵件從 Microsoft 365 輸出且未通過 DMARC，而您已將原則設為 p=隔離或 p=拒絕，則該郵件會透過[輸出郵件的較高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)路由傳送。 輸出電子郵件不可覆寫。

If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a>Microsoft 365 如何處理未通過 DMARC 的輸入電子郵件

如果傳送伺服器的 DMARC 原則是 `p=reject`，則 EOP 會將郵件標示為詐騙郵件，而不是拒絕此郵件。 換句話說，針對輸入電子郵件，Microsoft 365 會以相同的方式處理 `p=reject` 和 `p=quarantine`。 系統管理員可以定義對[防網路釣魚原則](set-up-anti-phishing-policies.md)內分類為詐騙的郵件執行的動作。

Microsoft 365 如此設定，是因為某些合法的電子郵件可能無法通過 DMARC。 比方說，如果郵件傳送至郵寄清單，然後再將郵件轉送至清單中的所有參與者，則此郵件可能無法通過 DMARC。 如果 Microsoft 365 拒絕這些郵件，可能會遺失合法的電子郵件，而且無法再擷取回來。 相反地，這些郵件仍無法通過 DMARC，但其會標示為垃圾郵件而不會被拒絕。 如有需要，使用者仍可在收件匣中透過下列方法取得這些郵件：

- 使用者使用電子郵件用戶端來個別新增安全寄件者。

- 系統管理員可更新[詐騙情報](learn-about-spoof-intelligence.md)報告，以允許詐騙郵件。

- 系統管理員為所有使用者建立 Exchange 郵件流程規則 (也稱為傳輸規則)，以允許這些特定寄件者的郵件。

如需詳細資訊，請參閱[建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a>Microsoft 365 如何使用已驗證接收鏈結 (ARC)

所有 Microsoft 365 中託管的信箱現在都將取得 ARC 帶來的改良式郵件傳送，以及增強式反詐騙防護的權益。 當電子郵件從原始伺服器路由傳送到收件者信箱時，ARC 會保留來自所有參與中繼或躍點的電子郵件驗證結果。 在 ARC 之前，透過電子郵件路由傳送中的中繼所執行的修改，(例如轉寄規則或自動簽署)，可能在郵件到達收件者信箱時導致 DMARC 失敗。 使用 ARC，Microsoft 365 可利用其驗證結果的加密保留確認電子郵件寄件者。

Microsoft 身為 ARC密封者，因此 Microsoft 365 目前是使用 ARC 來確認驗證結果，但計畫在未來新增協力廠商 ARC 密封者的支援。

## <a name="troubleshooting-your-dmarc-implementation"></a>對 DMARC 實作進行疑難排解

如果您已設定網域的 MX 記錄，其中 EOP 並非第一個項目，則不會針對您的網域強制 DMARC 失敗。

如果您是客戶，且您網域的主要 MX 記錄並未指向 EOP，則您不會取得 DMARC 的效益。 比方說，如果您將 MX 記錄指向內部部署郵件伺服器，並使用連接器將電子郵件路由傳送至 EOP，則不適用 DMARC。 在此案例中，接收方網域是您其中一個公認的網域，但 EOP 不是主要的 MX。 例如，假設 contoso.com 將其 MX 指向本身，並使用 EOP 作為次要 MX 記錄，contoso.com 的 MX 記錄會如下所示：

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

所有或大部分的電子郵件首先會路由至 mail.contoso.com，因為它是主要的 MX，然後才會將郵件路由至 EOP。 在某些情況下，您甚至可能不會將 EOP 列為 MX 記錄，而只要接上連接器來傳送電子郵件。 EOP 不一定需要是第一個項目，DMARC 驗證也可完成。 它只是可確保驗證，因為我們無法確定所有內部部署/非 O365 伺服器將執行 DMARC 檢查。  設定 DMARC TXT 記錄時，就能為客戶的網域 (非伺服器) 強制執行 DMARC，但實際上執行強制執行是由接收端伺服器執行。  如果您將 EOP 設定為接收端伺服器，則 EOP 會執行 DMARC 強制執行。

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="DMARC 的疑難排解圖形，由 Daniel Mande 提供":::

## <a name="for-more-information"></a>相關資訊

Want more information about DMARC? These resources can help.

- [反垃圾郵件訊息標頭](anti-spam-message-headers.md) 包含 Microsoft 365 針對 DMARC 檢查所使用的語法及標頭欄位。

- 從 M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG (傳訊、惡意程式碼、行動裝置反不當使用工作群組) 參與 <sup>DMARC 訓練系列課程</sup>。

- 在 [dmarcian](https://space.dmarcian.com/deployment/) 使用檢查清單。

- 直接前往來源 [DMARC.org](https://dmarc.org)。

## <a name="see-also"></a>請參閱

[Microsoft 365 如何使用寄件者原則架構 (SPF) 來防止詐騙](how-office-365-uses-spf-to-prevent-spoofing.md)

[在 Microsoft 365 中設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[使用 DKIM 驗證從您在 Microsoft 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)
