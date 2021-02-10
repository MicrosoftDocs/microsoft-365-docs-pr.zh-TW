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
description: 系統管理員可以瞭解 Exchange Online Protection (EOP) 和 Outlook.com 所接受或拒絕的電子郵件地址類型，以協助防止網路釣魚。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167512"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="5458c-103">EOP 如何驗證寄件者位址以避免網路釣魚</span><span class="sxs-lookup"><span data-stu-id="5458c-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5458c-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="5458c-104">**Applies to**</span></span>
- [<span data-ttu-id="5458c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5458c-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="5458c-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="5458c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="5458c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5458c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5458c-108">網路釣魚攻擊是對任何電子郵件組織造成的持續威脅。</span><span class="sxs-lookup"><span data-stu-id="5458c-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="5458c-109">除了使用 [冒牌 (偽造) 寄件者電子郵件地址](anti-spoofing-protection.md)，攻擊者通常會使用來自于網際網路標準的「寄件者」位址值。</span><span class="sxs-lookup"><span data-stu-id="5458c-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="5458c-110">為了協助防止此類型的網路釣魚，Exchange Online Protection (EOP) 和 Outlook.com 現在要求輸入郵件包含與 RFC 相容的來源位址（如本文所述）。</span><span class="sxs-lookup"><span data-stu-id="5458c-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="5458c-111">此強制已于2017年11月啟用。</span><span class="sxs-lookup"><span data-stu-id="5458c-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="5458c-112">**附註**：</span><span class="sxs-lookup"><span data-stu-id="5458c-112">**Notes**:</span></span>

- <span data-ttu-id="5458c-113">如果您定期收到的電子郵件來自于本文所述的位址錯誤的組織，請鼓勵這些組織更新他們的電子郵件伺服器，以遵守新式安全性標準。</span><span class="sxs-lookup"><span data-stu-id="5458c-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="5458c-114">「傳送代理者」和「郵寄清單」使用的相關寄件者欄位 () 不會受到這些需求的影響。</span><span class="sxs-lookup"><span data-stu-id="5458c-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="5458c-115">如需詳細資訊，請參閱下列博客文章： [當我們參考電子郵件的「寄件者」時，這是什麼意思？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)。</span><span class="sxs-lookup"><span data-stu-id="5458c-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="5458c-116">電子郵件訊息標準的概覽</span><span class="sxs-lookup"><span data-stu-id="5458c-116">An overview of email message standards</span></span>

<span data-ttu-id="5458c-117">標準 SMTP 電子郵件由「郵件信封」(Message Envelope) 和郵件內容組成。</span><span class="sxs-lookup"><span data-stu-id="5458c-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="5458c-118">郵件信封包含在 SMTP 伺服器之間傳輸及傳遞郵件所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="5458c-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="5458c-119">郵件內容包含統稱為 (「郵件標頭」) 的郵件標頭欄位和郵件內容。</span><span class="sxs-lookup"><span data-stu-id="5458c-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="5458c-120">[Rfc 5321](https://tools.ietf.org/html/rfc5321)會說明郵件信封，而[rfc 5322](https://tools.ietf.org/html/rfc5322)中說明郵件頭。</span><span class="sxs-lookup"><span data-stu-id="5458c-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="5458c-121">收件者永遠不會看到實際的郵件信封，因為它是由郵件傳輸程式所產生，而且實際上不是郵件的一部分。</span><span class="sxs-lookup"><span data-stu-id="5458c-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="5458c-122">此 `5321.MailFrom` 位址 (也稱為「 **郵件來自** 位址」、「P1 寄件者」或「信封寄件者」) 是在郵件的 SMTP 傳輸中使用的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5458c-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="5458c-123">這個電子郵件地址通常會記錄在郵件頭的 [傳回 **路徑** 標頭] 欄位中 (不過，寄件者可能會指定不同的傳回 **路徑** 電子郵件地址) 。</span><span class="sxs-lookup"><span data-stu-id="5458c-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="5458c-124">`5322.From` (也稱為 from address 或 P2 sender) 是電子郵件地址 **的收** 件者標頭欄位，也就是顯示在電子郵件客戶程式中的寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5458c-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="5458c-125">[寄件者] 位址是本文中需求的重點。</span><span class="sxs-lookup"><span data-stu-id="5458c-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="5458c-126">「寄件者」位址會在多個 Rfc (中詳細定義，例如 RFC 5322 區段3.2.3、3.4 及3.4.1，以及 [rfc 3696](https://tools.ietf.org/html/rfc3696)) 。</span><span class="sxs-lookup"><span data-stu-id="5458c-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="5458c-127">定址的情況有許多變化，且被視為有效或無效。</span><span class="sxs-lookup"><span data-stu-id="5458c-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="5458c-128">為了簡化，我們建議您遵循下列格式及定義：</span><span class="sxs-lookup"><span data-stu-id="5458c-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="5458c-129">**顯示名稱**：說明電子郵件地址擁有者的選用片語。</span><span class="sxs-lookup"><span data-stu-id="5458c-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="5458c-130">建議您永遠以雙引號括住顯示名稱 ( ") 如圖所示。</span><span class="sxs-lookup"><span data-stu-id="5458c-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="5458c-131">如果顯示名稱包含逗號，則 _必須_ 在每個 RFC 5322 的雙引號內加上單引號。</span><span class="sxs-lookup"><span data-stu-id="5458c-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="5458c-132">如果 [寄件者] 位址包含顯示名稱，則 EmailAddress 值必須括在角括弧 ( # A2) （如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="5458c-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="5458c-133">Microsoft 強烈建議您在顯示名稱和電子郵件地址之間插入空格。</span><span class="sxs-lookup"><span data-stu-id="5458c-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="5458c-134">**EmailAddress**：電子郵件地址使用下列格式 `local-part@domain` ：</span><span class="sxs-lookup"><span data-stu-id="5458c-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="5458c-135">**本機部分**：識別與位址相關聯之信箱的字串。</span><span class="sxs-lookup"><span data-stu-id="5458c-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="5458c-136">此值在網域內是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5458c-136">This value is unique within the domain.</span></span> <span data-ttu-id="5458c-137">通常會使用信箱擁有人的使用者名稱或 GUID。</span><span class="sxs-lookup"><span data-stu-id="5458c-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="5458c-138">**domain**：主控電子郵件地址的本機部分所識別之信箱的電子郵件伺服器的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="5458c-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="5458c-139">以下是 EmailAddress 值的一些額外考慮：</span><span class="sxs-lookup"><span data-stu-id="5458c-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="5458c-140">只有一個電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="5458c-140">Only one email address.</span></span>
  - <span data-ttu-id="5458c-141">建議您不要以空格分隔角括弧。</span><span class="sxs-lookup"><span data-stu-id="5458c-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="5458c-142">不要在電子郵件地址後包含其他文字。</span><span class="sxs-lookup"><span data-stu-id="5458c-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="5458c-143">有效和無效寄件者位址的範例</span><span class="sxs-lookup"><span data-stu-id="5458c-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="5458c-144">下列寄件者的電子郵件地址是有效的：</span><span class="sxs-lookup"><span data-stu-id="5458c-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="5458c-145">`From: < sender@contoso.com >` 因為角括弧和電子郵件地址之間有空格，所以不建議 (。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="5458c-146">`From: Microsoft 365 <sender@contoso.com>` 不建議使用 (因為顯示名稱不是以雙引號括住。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="5458c-147">下列寄件者電子郵件地址無效：</span><span class="sxs-lookup"><span data-stu-id="5458c-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="5458c-148">**沒有寄件者位址**：部分自動化郵件不包含寄件者位址。</span><span class="sxs-lookup"><span data-stu-id="5458c-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="5458c-149">過去，當 Microsoft 365 或 Outlook.com 收到沒有寄件者位址的郵件時，此服務會新增下列預設值： address，使郵件可傳送：</span><span class="sxs-lookup"><span data-stu-id="5458c-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="5458c-150">現在，已不再接受來自位址為空白的郵件。</span><span class="sxs-lookup"><span data-stu-id="5458c-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="5458c-151">`From: Microsoft 365 sender@contoso.com` (顯示名稱已存在，但是電子郵件地址不是以角括弧括住。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="5458c-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (的電子郵件地址後的文字。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="5458c-153">`From: Sender, Example <sender.example@contoso.com>` (顯示名稱包含逗點，但沒有以雙引號括住。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="5458c-154">`From: "Microsoft 365 <sender@contoso.com>"` (整個值都錯誤地用雙引號括住。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="5458c-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (顯示名稱已存在，但是電子郵件地址不是以角括弧括住。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="5458c-156">`From: Microsoft 365<sender@contoso.com>` (顯示名稱和左邊的角括弧之間沒有空格。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="5458c-157">`From: "Microsoft 365"<sender@contoso.com>` (的右雙引號和左邊的角括弧之間沒有空格。 ) </span><span class="sxs-lookup"><span data-stu-id="5458c-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="5458c-158">抑制您的自訂網域的自動回復</span><span class="sxs-lookup"><span data-stu-id="5458c-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="5458c-159">您無法使用此值 `From: <>` 來抑制自動回復。</span><span class="sxs-lookup"><span data-stu-id="5458c-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="5458c-160">相反地，您必須為您的自訂網域設定空的 MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="5458c-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="5458c-161">自動回復 (和所有回復) 會以自然抑制，因為回應伺服器無法傳送郵件的發行位址。</span><span class="sxs-lookup"><span data-stu-id="5458c-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="5458c-162">選擇無法接收電子郵件的電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="5458c-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="5458c-163">例如，如果您的主要網域是 contoso.com，您可以選擇 [noreply.contoso.com]。</span><span class="sxs-lookup"><span data-stu-id="5458c-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="5458c-164">此網域的 null MX 記錄是由單一句點所組成。</span><span class="sxs-lookup"><span data-stu-id="5458c-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="5458c-165">例如：</span><span class="sxs-lookup"><span data-stu-id="5458c-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="5458c-166">如需設定 MX 記錄的詳細資訊，請參閱 [在 Microsoft 365 的任何 DNS 主機服務提供者中建立 dns 記錄](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="5458c-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="5458c-167">如需有關發佈 null MX 的詳細資訊，請參閱 [RFC 7505](https://tools.ietf.org/html/rfc7505)。</span><span class="sxs-lookup"><span data-stu-id="5458c-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="5458c-168">從位址強制覆寫</span><span class="sxs-lookup"><span data-stu-id="5458c-168">Override From address enforcement</span></span>

<span data-ttu-id="5458c-169">若要略過輸入電子郵件的寄件者位址需求，您可以使用 IP 允許清單 (連線篩選) 或郵件流程規則 (也稱為 transport rules) 如在 [Microsoft 365 中建立安全的寄件者清單中](create-safe-sender-lists-in-office-365.md)所述。</span><span class="sxs-lookup"><span data-stu-id="5458c-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="5458c-170">您無法覆寫從 Microsoft 365 傳送的輸出電子郵件的寄件者位址需求。</span><span class="sxs-lookup"><span data-stu-id="5458c-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="5458c-171">此外，Outlook.com 將不允許任何類型的覆寫（甚至是透過支援）。</span><span class="sxs-lookup"><span data-stu-id="5458c-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="5458c-172">在 Microsoft 365 中防止及防禦 cybercrimes 的其他方式</span><span class="sxs-lookup"><span data-stu-id="5458c-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="5458c-173">如需如何強化組織抵禦網路釣魚、垃圾郵件、資料違例及其他威脅的詳細資訊，請參閱 [保護 Microsoft 365 for business 方案的前10種方式](../../admin/security-and-compliance/secure-your-business-data.md)。</span><span class="sxs-lookup"><span data-stu-id="5458c-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
