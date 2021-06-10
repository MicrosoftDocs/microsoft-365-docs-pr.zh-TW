---
title: EOP 如何驗證寄件者位址以避免網路釣魚
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 和 Outlook 所接受或拒絕的電子郵件地址類型，以協助防止網路釣魚。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203503"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>EOP 如何驗證寄件者位址以避免網路釣魚

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

網路釣魚攻擊是對任何電子郵件組織造成的持續威脅。 除了使用 [冒牌 (偽造) 寄件者電子郵件地址](anti-spoofing-protection.md)，攻擊者通常會使用來自于網際網路標準的「寄件者」位址值。 為了協助防止此類型的網路釣魚，Exchange Online Protection (EOP) 和 Outlook 現在要求輸入郵件包括 RFC 相容的來源位址（如本文所述）。 此強制已于2017年11月啟用。

**附註**：

- 如果您定期收到的電子郵件來自于本文所述的位址錯誤的組織，請鼓勵這些組織更新他們的電子郵件伺服器，以遵守新式安全性標準。

- 「傳送代理者」和「郵寄清單」使用的相關寄件者欄位 () 不會受到這些需求的影響。 如需詳細資訊，請參閱下列博客文章： [當我們參考電子郵件的「寄件者」時，這是什麼意思？](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email)。

## <a name="an-overview-of-email-message-standards"></a>電子郵件訊息標準的概覽

標準 SMTP 電子郵件由「郵件信封」(Message Envelope) 和郵件內容組成。 郵件信封包含在 SMTP 伺服器之間傳輸及傳遞郵件所需的資訊。 郵件內容包含統稱為 (「郵件標頭」) 的郵件標頭欄位和郵件內容。 [Rfc 5321](https://tools.ietf.org/html/rfc5321)會說明郵件信封，而[rfc 5322](https://tools.ietf.org/html/rfc5322)中說明郵件頭。 收件者永遠不會看到實際的郵件信封，因為它是由郵件傳輸程式所產生，而且實際上不是郵件的一部分。

- 此 `5321.MailFrom` 位址 (也稱為「 **郵件來自** 位址」、「P1 寄件者」或「信封寄件者」) 是在郵件的 SMTP 傳輸中使用的電子郵件地址。 這個電子郵件地址通常會記錄在郵件頭的 [傳回 **路徑** 標頭] 欄位中 (不過，寄件者可能會指定不同的傳回 **路徑** 電子郵件地址) 。

- `5322.From` (也稱為 from address 或 P2 sender) 是電子郵件地址 **的收** 件者標頭欄位，也就是顯示在電子郵件客戶程式中的寄件者電子郵件地址。 [寄件者] 位址是本文中需求的重點。

「寄件者」位址會在多個 Rfc (中詳細定義，例如 RFC 5322 區段3.2.3、3.4 及3.4.1，以及 [rfc 3696](https://tools.ietf.org/html/rfc3696)) 。 定址的情況有許多變化，且被視為有效或無效。 為了簡化，我們建議您遵循下列格式及定義：

`From: "Display Name" <EmailAddress>`

- **顯示名稱**：說明電子郵件地址擁有者的選用片語。

  - 建議您永遠以雙引號括住顯示名稱 ( ") 如圖所示。 如果顯示名稱包含逗號，則 _必須_ 在每個 RFC 5322 的雙引號內加上單引號。
  - 如果 [寄件者] 位址包含顯示名稱，則 EmailAddress 值必須用角括弧括住 (< >) 如圖所示。
  - Microsoft 強烈建議您在顯示名稱和電子郵件地址之間插入空格。

- **EmailAddress**：電子郵件地址使用下列格式 `local-part@domain` ：

  - **本機部分**：識別與位址相關聯之信箱的字串。 此值在網域內是唯一的。 通常會使用信箱擁有人的使用者名稱或 GUID。
  - **domain**：主控電子郵件地址的本機部分所識別之信箱的電子郵件伺服器的完整功能變數名稱 (FQDN) 。

  以下是 EmailAddress 值的一些額外考慮：

  - 只有一個電子郵件地址。
  - 建議您不要以空格分隔角括弧。
  - 不要在電子郵件地址後包含其他文字。

## <a name="examples-of-valid-and-invalid-from-addresses"></a>有效和無效寄件者位址的範例

下列寄件者的電子郵件地址是有效的：

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` 因為角括弧和電子郵件地址之間有空格，所以不建議 (。 ) 

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` 不建議使用 (因為顯示名稱不是以雙引號括住。 ) 

下列寄件者電子郵件地址無效：

- **沒有寄件者位址**：部分自動化郵件不包含寄件者位址。 過去，當 Microsoft 365 或 Outlook .com 收到沒有寄件者位址的郵件時，此服務會新增下列預設值： address，使郵件可傳送：

  `From: <>`

  現在，已不再接受來自位址為空白的郵件。

- `From: Microsoft 365 sender@contoso.com` (顯示名稱已存在，但是電子郵件地址不是以角括弧括住。 ) 

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (的電子郵件地址後的文字。 ) 

- `From: Sender, Example <sender.example@contoso.com>` (顯示名稱包含逗點，但沒有以雙引號括住。 ) 

- `From: "Microsoft 365 <sender@contoso.com>"` (整個值都錯誤地用雙引號括住。 ) 

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (顯示名稱已存在，但是電子郵件地址不是以角括弧括住。 ) 

- `From: Microsoft 365<sender@contoso.com>` (顯示名稱和左邊的角括弧之間沒有空格。 ) 

- `From: "Microsoft 365"<sender@contoso.com>` (的右雙引號和左邊的角括弧之間沒有空格。 ) 

## <a name="suppress-auto-replies-to-your-custom-domain"></a>抑制您的自訂網域的自動回復

您無法使用此值 `From: <>` 來抑制自動回復。 相反地，您必須為您的自訂網域設定空的 MX 記錄。 自動回復 (和所有回復) 會以自然抑制，因為回應伺服器無法傳送郵件的發行位址。

- 選擇無法接收電子郵件的電子郵件網域。 例如，如果您的主要網域是 contoso.com，您可以選擇 [noreply.contoso.com]。

- 此網域的 null MX 記錄是由單一句點所組成。

例如：

```text
noreply.contoso.com IN MX .
```

如需設定 MX 記錄的詳細資訊，請參閱[在 Microsoft 365 的任何 DNS 主機服務提供者中建立 dns 記錄](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。

如需有關發佈 null MX 的詳細資訊，請參閱 [RFC 7505](https://tools.ietf.org/html/rfc7505)。

## <a name="override-from-address-enforcement"></a>從位址強制覆寫

若要略過輸入電子郵件的寄件者位址需求，您可以使用 IP 允許清單 (連線篩選) 或郵件流程規則 (也稱為 transport rules) 如[Microsoft 365 中的建立安全寄件者清單中](create-safe-sender-lists-in-office-365.md)所述。

您無法覆寫從 Microsoft 365 傳送之外寄電子郵件的寄件者位址需求。 此外，Outlook .com 將不允許任何類型的覆寫，甚至是透過支援。

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>在 Microsoft 365 中防止及防禦 cybercrimes 的其他方式

如需如何強化組織抵禦網路釣魚、垃圾郵件、資料違例及其他威脅的詳細資訊，請參閱[保護商務方案 Microsoft 365 的前10種方式](../../admin/security-and-compliance/secure-your-business-data.md)。