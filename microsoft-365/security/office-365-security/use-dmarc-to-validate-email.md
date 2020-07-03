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
# <a name="use-dmarc-to-validate-email"></a><span data-ttu-id="182e6-103">使用 DMARC 來驗證電子郵件</span><span class="sxs-lookup"><span data-stu-id="182e6-103">Use DMARC to validate email</span></span>

<span data-ttu-id="182e6-104">以網域為基礎的郵件驗證、報告和一致性 ([DMARC](https://dmarc.org)) 搭配寄件者原則架構 (SPF) 和網域金鑰識別郵件 (DKIM) 來驗證郵件寄件者，並確保目的地電子郵件系統信任您網域傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-104">Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain.</span></span> <span data-ttu-id="182e6-105">搭配 SPF 和 DKIM 來實作 DMARC 可提供額外保護，防範詐騙和網路釣魚電子郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-105">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="182e6-106">DMARC 可協助接收方郵件系統決定如何處理未通過 SPF 或 DKIM 檢查的您網域傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-106">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span>

> [!TIP]
> <span data-ttu-id="182e6-107">請造訪 [Microsoft 情報安全性聯盟 (MISA)](https://www.microsoft.com/misapartnercatalog) 目錄，以檢視為 Microsoft 365 提供 DMARC 報告的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="182e6-107">Visit the [Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog) catalog to view third-party vendors offering DMARC reporting for Microsoft 365.</span></span>

## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-microsoft-365"></a><span data-ttu-id="182e6-108">SPF 和 DMARC 如何共同運作以在 Microsoft 365 中保護電子郵件？</span><span class="sxs-lookup"><span data-stu-id="182e6-108">How do SPF and DMARC work together to protect email in Microsoft 365?</span></span>

 <span data-ttu-id="182e6-109">電子郵件訊息可能包含多個建立者或寄件者地址。</span><span class="sxs-lookup"><span data-stu-id="182e6-109">An email message may contain multiple originator, or sender, addresses.</span></span> <span data-ttu-id="182e6-110">這些地址可用於不同用途。</span><span class="sxs-lookup"><span data-stu-id="182e6-110">These addresses are used for different purposes.</span></span> <span data-ttu-id="182e6-111">例如以下地址：</span><span class="sxs-lookup"><span data-stu-id="182e6-111">For example, consider these addresses:</span></span>

- <span data-ttu-id="182e6-112">**「郵件寄件者」地址**：識別寄件者，並指定如果郵件傳遞發生任何問題時要傳送回傳通知的位置 (如未傳遞通知)。</span><span class="sxs-lookup"><span data-stu-id="182e6-112">**"Mail From" address**: Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices.</span></span> <span data-ttu-id="182e6-113">這會顯示在電子郵件訊息的信封部分，而且通常不會由電子郵件應用程式顯示。</span><span class="sxs-lookup"><span data-stu-id="182e6-113">This appears in the envelope portion of an email message and is not usually displayed by your email application.</span></span> <span data-ttu-id="182e6-114">這有時稱為 5321.MailFrom 地址或反向路徑地址。</span><span class="sxs-lookup"><span data-stu-id="182e6-114">This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>

- <span data-ttu-id="182e6-115">**「寄件者」地址**：由您的郵件應用程式顯示為寄件者地址的地址。</span><span class="sxs-lookup"><span data-stu-id="182e6-115">**"From" address**: The address displayed as the From address by your mail application.</span></span> <span data-ttu-id="182e6-116">此地址可識別電子郵件的作者。</span><span class="sxs-lookup"><span data-stu-id="182e6-116">This address identifies the author of the email.</span></span> <span data-ttu-id="182e6-117">也就是負責撰寫郵件的使用者或系統信箱。</span><span class="sxs-lookup"><span data-stu-id="182e6-117">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="182e6-118">這有時稱為 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="182e6-118">This is sometimes called the 5322.From address.</span></span>

<span data-ttu-id="182e6-119">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain.</span><span class="sxs-lookup"><span data-stu-id="182e6-119">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain.</span></span> <span data-ttu-id="182e6-120">Normally, SPF checks are only performed against the 5321.MailFrom address.</span><span class="sxs-lookup"><span data-stu-id="182e6-120">Normally, SPF checks are only performed against the 5321.MailFrom address.</span></span> <span data-ttu-id="182e6-121">This means that the 5322.From address is not authenticated when you use SPF by itself.</span><span class="sxs-lookup"><span data-stu-id="182e6-121">This means that the 5322.From address is not authenticated when you use SPF by itself.</span></span> <span data-ttu-id="182e6-122">This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address.</span><span class="sxs-lookup"><span data-stu-id="182e6-122">This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address.</span></span> <span data-ttu-id="182e6-123">For example, consider this SMTP transcript:</span><span class="sxs-lookup"><span data-stu-id="182e6-123">For example, consider this SMTP transcript:</span></span>

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

<span data-ttu-id="182e6-124">在此文字記錄中，寄件者地址如下：</span><span class="sxs-lookup"><span data-stu-id="182e6-124">In this transcript, the sender addresses are as follows:</span></span>

- <span data-ttu-id="182e6-125">郵件寄件者地址 (5321.MailFrom): phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="182e6-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>

- <span data-ttu-id="182e6-126">寄件者地址 (5322.From): security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="182e6-126">From address (5322.From): security@woodgrovebank.com</span></span>

<span data-ttu-id="182e6-127">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="182e6-127">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com.</span></span> <span data-ttu-id="182e6-128">If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes.</span><span class="sxs-lookup"><span data-stu-id="182e6-128">If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes.</span></span> <span data-ttu-id="182e6-129">Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com.</span><span class="sxs-lookup"><span data-stu-id="182e6-129">Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com.</span></span> <span data-ttu-id="182e6-130">With SPF alone, the validity of woodgrovebank.com was never authenticated.</span><span class="sxs-lookup"><span data-stu-id="182e6-130">With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>

<span data-ttu-id="182e6-131">When you use DMARC, the receiving server also performs a check against the From address.</span><span class="sxs-lookup"><span data-stu-id="182e6-131">When you use DMARC, the receiving server also performs a check against the From address.</span></span> <span data-ttu-id="182e6-132">In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span><span class="sxs-lookup"><span data-stu-id="182e6-132">In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>

## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="182e6-133">什麼是 DMARC TXT 記錄？</span><span class="sxs-lookup"><span data-stu-id="182e6-133">What is a DMARC TXT record?</span></span>

<span data-ttu-id="182e6-134">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing.</span><span class="sxs-lookup"><span data-stu-id="182e6-134">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing.</span></span> <span data-ttu-id="182e6-135">You publish DMARC TXT records in DNS.</span><span class="sxs-lookup"><span data-stu-id="182e6-135">You publish DMARC TXT records in DNS.</span></span> <span data-ttu-id="182e6-136">DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain.</span><span class="sxs-lookup"><span data-stu-id="182e6-136">DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain.</span></span> <span data-ttu-id="182e6-137">The DMARC TXT record identifies authorized outbound email servers.</span><span class="sxs-lookup"><span data-stu-id="182e6-137">The DMARC TXT record identifies authorized outbound email servers.</span></span> <span data-ttu-id="182e6-138">Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span><span class="sxs-lookup"><span data-stu-id="182e6-138">Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>

<span data-ttu-id="182e6-139">Microsoft 的 DMARC TXT 記錄看起來如下：</span><span class="sxs-lookup"><span data-stu-id="182e6-139">Microsoft's DMARC TXT record looks something like this:</span></span>

```text
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1"
```

<span data-ttu-id="182e6-140">Microsoft 會將其 DMARC 報告傳送給協力廠商 [Agari](https://agari.com)。</span><span class="sxs-lookup"><span data-stu-id="182e6-140">Microsoft sends its DMARC reports to [Agari](https://agari.com), a third party.</span></span> <span data-ttu-id="182e6-141">Agari 會收集並分析 DMARC 報告。</span><span class="sxs-lookup"><span data-stu-id="182e6-141">Agari collects and analyzes DMARC reports.</span></span> <span data-ttu-id="182e6-142">請造訪 [MISA 目錄](https://www.microsoft.com/misapartnercatalog)，以檢視更多為 Microsoft 365 提供 DMARC 報告的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="182e6-142">Please visit the [MISA catalog](https://www.microsoft.com/misapartnercatalog) to view more third-party vendors offering DMARC reporting for Microsoft 365.</span></span>

## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="182e6-143">為輸入郵件實作 DMARC</span><span class="sxs-lookup"><span data-stu-id="182e6-143">Implement DMARC for inbound mail</span></span>

<span data-ttu-id="182e6-144">You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="182e6-144">You don't have to do a thing to set up DMARC for mail that you receive in Microsoft 365.</span></span> <span data-ttu-id="182e6-145">We've taken care of everything for you.</span><span class="sxs-lookup"><span data-stu-id="182e6-145">We've taken care of everything for you.</span></span> <span data-ttu-id="182e6-146">If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</span><span class="sxs-lookup"><span data-stu-id="182e6-146">If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Microsoft 365 handles inbound email that fails DMARC](#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</span></span>

## <a name="implement-dmarc-for-outbound-mail-from-microsoft-365"></a><span data-ttu-id="182e6-147">為 Microsoft 365 的輸出郵件實作 DMARC</span><span class="sxs-lookup"><span data-stu-id="182e6-147">Implement DMARC for outbound mail from Microsoft 365</span></span>

<span data-ttu-id="182e6-148">If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization.</span><span class="sxs-lookup"><span data-stu-id="182e6-148">If you use Microsoft 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization.</span></span> <span data-ttu-id="182e6-149">SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail.</span><span class="sxs-lookup"><span data-stu-id="182e6-149">SPF is already set up for you and Microsoft 365 automatically generates a DKIM signature for your outgoing mail.</span></span> <span data-ttu-id="182e6-150">For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="182e6-150">For more information about this signature, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

 <span data-ttu-id="182e6-151">If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail.</span><span class="sxs-lookup"><span data-stu-id="182e6-151">If you have a custom domain or you are using on-premises Exchange servers in addition to Microsoft 365, you need to manually implement DMARC for your outbound mail.</span></span> <span data-ttu-id="182e6-152">Implementing DMARC for your custom domain includes these steps:</span><span class="sxs-lookup"><span data-stu-id="182e6-152">Implementing DMARC for your custom domain includes these steps:</span></span>

- [<span data-ttu-id="182e6-153">步驟 1：找出您網域的郵件有效來源</span><span class="sxs-lookup"><span data-stu-id="182e6-153">Step 1: Identify valid sources of mail for your domain</span></span>](#step-1-identify-valid-sources-of-mail-for-your-domain)

- [<span data-ttu-id="182e6-154">步驟 2：為網域設定 SPF</span><span class="sxs-lookup"><span data-stu-id="182e6-154">Step 2: Set up SPF for your domain</span></span>](#step-2-set-up-spf-for-your-domain)

- [<span data-ttu-id="182e6-155">步驟 3：為自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="182e6-155">Step 3: Set up DKIM for your custom domain</span></span>](#step-3-set-up-dkim-for-your-custom-domain)

- [<span data-ttu-id="182e6-156">步驟 4：為網域形成 DMARC TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="182e6-156">Step 4: Form the DMARC TXT record for your domain</span></span>](#step-4-form-the-dmarc-txt-record-for-your-domain)

### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="182e6-157">步驟 1：找出您網域的郵件有效來源</span><span class="sxs-lookup"><span data-stu-id="182e6-157">Step 1: Identify valid sources of mail for your domain</span></span>

<span data-ttu-id="182e6-158">If you have already set up SPF then you have already gone through this exercise.</span><span class="sxs-lookup"><span data-stu-id="182e6-158">If you have already set up SPF then you have already gone through this exercise.</span></span> <span data-ttu-id="182e6-159">However, for DMARC, there are additional considerations.</span><span class="sxs-lookup"><span data-stu-id="182e6-159">However, for DMARC, there are additional considerations.</span></span> <span data-ttu-id="182e6-160">When identifying sources of mail for your domain there are two questions you need to answer:</span><span class="sxs-lookup"><span data-stu-id="182e6-160">When identifying sources of mail for your domain there are two questions you need to answer:</span></span>

- <span data-ttu-id="182e6-161">哪些 IP 位址會從我的網域傳送郵件？</span><span class="sxs-lookup"><span data-stu-id="182e6-161">What IP addresses send messages from my domain?</span></span>

- <span data-ttu-id="182e6-162">針對由第三方代表我所傳送的郵件，5321.MailFrom 和 5322.From 網域相符嗎？</span><span class="sxs-lookup"><span data-stu-id="182e6-162">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>

### <a name="step-2-set-up-spf-for-your-domain"></a><span data-ttu-id="182e6-163">步驟 2：為網域設定 SPF</span><span class="sxs-lookup"><span data-stu-id="182e6-163">Step 2: Set up SPF for your domain</span></span>

<span data-ttu-id="182e6-164">現在您有所有有效寄件者的清單，您可以按照步驟[設定 SPF 以協助防止詐騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="182e6-164">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

<span data-ttu-id="182e6-165">例如，假設 contoso.com 從 Exchange Online 傳送郵件，其為 IP 位址為 192.168.0.1 的內部部署 Exchange 伺服器和 IP 位址為 192.168.100.100 的 Web 應用程式，則 SPF TXT 記錄呈現如下：</span><span class="sxs-lookup"><span data-stu-id="182e6-165">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>

```text
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="182e6-166">最佳作法是，請確定 SPF TXT 記錄包括第三方寄件者。</span><span class="sxs-lookup"><span data-stu-id="182e6-166">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>

### <a name="step-3-set-up-dkim-for-your-custom-domain"></a><span data-ttu-id="182e6-167">步驟 3：為自訂網域設定 DKIM</span><span class="sxs-lookup"><span data-stu-id="182e6-167">Step 3: Set up DKIM for your custom domain</span></span>

<span data-ttu-id="182e6-168">Once you have set up SPF, you need to set up DKIM.</span><span class="sxs-lookup"><span data-stu-id="182e6-168">Once you have set up SPF, you need to set up DKIM.</span></span> <span data-ttu-id="182e6-169">DKIM lets you add a digital signature to email messages in the message header.</span><span class="sxs-lookup"><span data-stu-id="182e6-169">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="182e6-170">If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail.</span><span class="sxs-lookup"><span data-stu-id="182e6-170">If you do not set up DKIM and instead allow Microsoft 365 to use the default DKIM configuration for your domain, DMARC may fail.</span></span> <span data-ttu-id="182e6-171">This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain.</span><span class="sxs-lookup"><span data-stu-id="182e6-171">This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain.</span></span> <span data-ttu-id="182e6-172">This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span><span class="sxs-lookup"><span data-stu-id="182e6-172">This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>

<span data-ttu-id="182e6-173">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email.</span><span class="sxs-lookup"><span data-stu-id="182e6-173">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email.</span></span> <span data-ttu-id="182e6-174">To avoid this, you need to set up DKIM for your domain specifically with that third-party sender.</span><span class="sxs-lookup"><span data-stu-id="182e6-174">To avoid this, you need to set up DKIM for your domain specifically with that third-party sender.</span></span> <span data-ttu-id="182e6-175">This allows Microsoft 365 to authenticate email from this 3rd-party service.</span><span class="sxs-lookup"><span data-stu-id="182e6-175">This allows Microsoft 365 to authenticate email from this 3rd-party service.</span></span> <span data-ttu-id="182e6-176">However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you.</span><span class="sxs-lookup"><span data-stu-id="182e6-176">However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you.</span></span> <span data-ttu-id="182e6-177">This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span><span class="sxs-lookup"><span data-stu-id="182e6-177">This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Microsoft 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>

<span data-ttu-id="182e6-178">有關為網域設定 DKIM 的相關指示，包括如何為第三方寄件者設定 DKIM 以避免詐騙網域，請參閱 [使用 DKIM 驗證從您的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="182e6-178">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

### <a name="step-4-form-the-dmarc-txt-record-for-your-domain"></a><span data-ttu-id="182e6-179">步驟 4：為網域形成 DMARC TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="182e6-179">Step 4: Form the DMARC TXT record for your domain</span></span>

<span data-ttu-id="182e6-180">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="182e6-180">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Microsoft 365.</span></span> <span data-ttu-id="182e6-181">Form the DMARC TXT record for your domain in the format:</span><span class="sxs-lookup"><span data-stu-id="182e6-181">Form the DMARC TXT record for your domain in the format:</span></span>

```text
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; p=policy; pct=100"
```

<span data-ttu-id="182e6-182">其中：</span><span class="sxs-lookup"><span data-stu-id="182e6-182">where:</span></span>

- <span data-ttu-id="182e6-183">*網域*是您想要保護的網域。</span><span class="sxs-lookup"><span data-stu-id="182e6-183">*domain* is the domain you want to protect.</span></span> <span data-ttu-id="182e6-184">根據預設，記錄會保護該網域及所有子網域的郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-184">By default, the record protects mail from the domain and all subdomains.</span></span> <span data-ttu-id="182e6-185">例如，如果您指定 \_dmarc.contoso.com，DMARC 會保護此網域及所有子網域的郵件，例如 housewares.contoso.com 或 plumbing.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="182e6-185">For example, if you specify \_dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span>

- <span data-ttu-id="182e6-186">*TTL* should always be the equivalent of one hour.</span><span class="sxs-lookup"><span data-stu-id="182e6-186">*TTL* should always be the equivalent of one hour.</span></span> <span data-ttu-id="182e6-187">The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span><span class="sxs-lookup"><span data-stu-id="182e6-187">The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span>

- <span data-ttu-id="182e6-188">*pct=100* 指出這項規則應 100% 用於電子郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-188">*pct=100* indicates that this rule should be used for 100% of email.</span></span>

- <span data-ttu-id="182e6-189">*policy* specifies what policy you want the receiving server to follow if DMARC fails.</span><span class="sxs-lookup"><span data-stu-id="182e6-189">*policy* specifies what policy you want the receiving server to follow if DMARC fails.</span></span> <span data-ttu-id="182e6-190">You can set the policy to none, quarantine, or reject.</span><span class="sxs-lookup"><span data-stu-id="182e6-190">You can set the policy to none, quarantine, or reject.</span></span>

<span data-ttu-id="182e6-191">如需使用選項的相關資訊，請參閱[在 Microsoft 365 中實作 DMARC 的最佳作法](#best-practices-for-implementing-dmarc-in-microsoft-365)以熟悉概念。</span><span class="sxs-lookup"><span data-stu-id="182e6-191">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Microsoft 365](#best-practices-for-implementing-dmarc-in-microsoft-365).</span></span>

<span data-ttu-id="182e6-192">範例:</span><span class="sxs-lookup"><span data-stu-id="182e6-192">Examples:</span></span>

- <span data-ttu-id="182e6-193">原則設為 [無]</span><span class="sxs-lookup"><span data-stu-id="182e6-193">Policy set to none</span></span>

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- <span data-ttu-id="182e6-194">原則設為 [隔離]</span><span class="sxs-lookup"><span data-stu-id="182e6-194">Policy set to quarantine</span></span>

    ```text
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- <span data-ttu-id="182e6-195">原則設為 [拒絕]</span><span class="sxs-lookup"><span data-stu-id="182e6-195">Policy set to reject</span></span>

    ```text
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

<span data-ttu-id="182e6-196">Once you have formed your record, you need to update the record at your domain registrar.</span><span class="sxs-lookup"><span data-stu-id="182e6-196">Once you have formed your record, you need to update the record at your domain registrar.</span></span> <span data-ttu-id="182e6-197">For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="182e6-197">For instructions on adding the DMARC TXT record to your DNS records for Microsoft 365, see [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

## <a name="best-practices-for-implementing-dmarc-in-microsoft-365"></a><span data-ttu-id="182e6-198">在 Microsoft 365 中實作 DMARC 的最佳作法</span><span class="sxs-lookup"><span data-stu-id="182e6-198">Best practices for implementing DMARC in Microsoft 365</span></span>

<span data-ttu-id="182e6-199">You can implement DMARC gradually without impacting the rest of your mail flow.</span><span class="sxs-lookup"><span data-stu-id="182e6-199">You can implement DMARC gradually without impacting the rest of your mail flow.</span></span> <span data-ttu-id="182e6-200">Create and implement a roll out plan that follows these steps.</span><span class="sxs-lookup"><span data-stu-id="182e6-200">Create and implement a roll out plan that follows these steps.</span></span> <span data-ttu-id="182e6-201">Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span><span class="sxs-lookup"><span data-stu-id="182e6-201">Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>

1. <span data-ttu-id="182e6-202">監控實作 DMARC 的影響</span><span class="sxs-lookup"><span data-stu-id="182e6-202">Monitor the impact of implementing DMARC</span></span>

    <span data-ttu-id="182e6-203">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain.</span><span class="sxs-lookup"><span data-stu-id="182e6-203">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain.</span></span> <span data-ttu-id="182e6-204">A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none).</span><span class="sxs-lookup"><span data-stu-id="182e6-204">A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none).</span></span> <span data-ttu-id="182e6-205">Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span><span class="sxs-lookup"><span data-stu-id="182e6-205">Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span>

    <span data-ttu-id="182e6-206">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure.</span><span class="sxs-lookup"><span data-stu-id="182e6-206">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure.</span></span> <span data-ttu-id="182e6-207">However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM.</span><span class="sxs-lookup"><span data-stu-id="182e6-207">However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM.</span></span> <span data-ttu-id="182e6-208">As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't.</span><span class="sxs-lookup"><span data-stu-id="182e6-208">As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't.</span></span> <span data-ttu-id="182e6-209">You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems.</span><span class="sxs-lookup"><span data-stu-id="182e6-209">You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems.</span></span> <span data-ttu-id="182e6-210">You'll also begin to see how many fraudulent messages are being sent, and from where.</span><span class="sxs-lookup"><span data-stu-id="182e6-210">You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>

2. <span data-ttu-id="182e6-211">要求外部郵件系統隔離未通過 DMARC 的郵件</span><span class="sxs-lookup"><span data-stu-id="182e6-211">Request that external mail systems quarantine mail that fails DMARC</span></span>

    <span data-ttu-id="182e6-212">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy.</span><span class="sxs-lookup"><span data-stu-id="182e6-212">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy.</span></span> <span data-ttu-id="182e6-213">A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine).</span><span class="sxs-lookup"><span data-stu-id="182e6-213">A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine).</span></span> <span data-ttu-id="182e6-214">By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span><span class="sxs-lookup"><span data-stu-id="182e6-214">By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>

3. <span data-ttu-id="182e6-215">要求外部郵件系統不接受未通過 DMARC 的郵件</span><span class="sxs-lookup"><span data-stu-id="182e6-215">Request that external mail systems not accept messages that fail DMARC</span></span>

    <span data-ttu-id="182e6-216">The final step is implementing a reject policy.</span><span class="sxs-lookup"><span data-stu-id="182e6-216">The final step is implementing a reject policy.</span></span> <span data-ttu-id="182e6-217">A reject policy is a DMARC TXT record that has its policy set to reject (p=reject).</span><span class="sxs-lookup"><span data-stu-id="182e6-217">A reject policy is a DMARC TXT record that has its policy set to reject (p=reject).</span></span> <span data-ttu-id="182e6-218">When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span><span class="sxs-lookup"><span data-stu-id="182e6-218">When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span>

## <a name="how-microsoft-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="182e6-219">Microsoft 365 如何處理未通過 DMARC 的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="182e6-219">How Microsoft 365 handles outbound email that fails DMARC</span></span>

<span data-ttu-id="182e6-220">如果郵件從 Microsoft 365 輸出且未通過 DMARC，而您已將原則設為 p=隔離或 p=拒絕，則該郵件會透過[輸出郵件的較高風險傳遞集區](high-risk-delivery-pool-for-outbound-messages.md)路由傳送。</span><span class="sxs-lookup"><span data-stu-id="182e6-220">If a message is outbound from Microsoft 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> <span data-ttu-id="182e6-221">輸出電子郵件不可覆寫。</span><span class="sxs-lookup"><span data-stu-id="182e6-221">There is no override for outbound email.</span></span>

<span data-ttu-id="182e6-222">If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service.</span><span class="sxs-lookup"><span data-stu-id="182e6-222">If you publish a DMARC reject policy (p=reject), no other customer in Microsoft 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service.</span></span> <span data-ttu-id="182e6-223">However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service.</span><span class="sxs-lookup"><span data-stu-id="182e6-223">However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Microsoft 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service.</span></span> <span data-ttu-id="182e6-224">This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span><span class="sxs-lookup"><span data-stu-id="182e6-224">This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>

## <a name="how-microsoft-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="182e6-225">Microsoft 365 如何處理未通過 DMARC 的輸入電子郵件</span><span class="sxs-lookup"><span data-stu-id="182e6-225">How Microsoft 365 handles inbound email that fails DMARC</span></span>

<span data-ttu-id="182e6-226">如果傳送伺服器的 DMARC 原則是 `p=reject`，則 EOP 會將郵件標示為詐騙郵件，而不是拒絕此郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-226">If the DMARC policy of the sending server is `p=reject`, EOP marks the message as spoof instead of rejecting it.</span></span> <span data-ttu-id="182e6-227">換句話說，針對輸入電子郵件，Microsoft 365 會以相同的方式處理 `p=reject` 和 `p=quarantine`。</span><span class="sxs-lookup"><span data-stu-id="182e6-227">In other words, for inbound email, Microsoft 365 treats `p=reject` and `p=quarantine` the same way.</span></span> <span data-ttu-id="182e6-228">系統管理員可以定義對[防網路釣魚原則](set-up-anti-phishing-policies.md)內分類為詐騙的郵件執行的動作。</span><span class="sxs-lookup"><span data-stu-id="182e6-228">Admins can define the action to take on messages classified as spoof within the [anti-phishing policy](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="182e6-229">Microsoft 365 如此設定，是因為某些合法的電子郵件可能無法通過 DMARC。</span><span class="sxs-lookup"><span data-stu-id="182e6-229">Microsoft 365 is configured like this because some legitimate email may fail DMARC.</span></span> <span data-ttu-id="182e6-230">比方說，如果郵件傳送至郵寄清單，然後再將郵件轉送至清單中的所有參與者，則此郵件可能無法通過 DMARC。</span><span class="sxs-lookup"><span data-stu-id="182e6-230">For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants.</span></span> <span data-ttu-id="182e6-231">如果 Microsoft 365 拒絕這些郵件，可能會遺失合法的電子郵件，而且無法再擷取回來。</span><span class="sxs-lookup"><span data-stu-id="182e6-231">If Microsoft 365 rejected these messages, people could lose legitimate email and have no way to retrieve it.</span></span> <span data-ttu-id="182e6-232">相反地，這些郵件仍無法通過 DMARC，但其會標示為垃圾郵件而不會被拒絕。</span><span class="sxs-lookup"><span data-stu-id="182e6-232">Instead, these messages will still fail DMARC but they will be marked as spam and not rejected.</span></span> <span data-ttu-id="182e6-233">如有需要，使用者仍可在收件匣中透過下列方法取得這些郵件：</span><span class="sxs-lookup"><span data-stu-id="182e6-233">If desired, users can still get these messages in their inbox through these methods:</span></span>

- <span data-ttu-id="182e6-234">使用者使用電子郵件用戶端來個別新增安全寄件者。</span><span class="sxs-lookup"><span data-stu-id="182e6-234">Users add safe senders individually by using their email client.</span></span>

- <span data-ttu-id="182e6-235">系統管理員可更新[詐騙情報](learn-about-spoof-intelligence.md)報告，以允許詐騙郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-235">Administrators can update the [Spoof Intelligence](learn-about-spoof-intelligence.md) reporting to allow the spoof.</span></span>

- <span data-ttu-id="182e6-236">系統管理員為所有使用者建立 Exchange 郵件流程規則 (也稱為傳輸規則)，以允許這些特定寄件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-236">Administrators create an Exchange mail flow rule (also known as a transport rule) for all users that allows messages for those particular senders.</span></span>

<span data-ttu-id="182e6-237">如需詳細資訊，請參閱[建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="182e6-237">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="how-microsoft-365-utilizes-authenticated-received-chain-arc"></a><span data-ttu-id="182e6-238">Microsoft 365 如何使用已驗證接收鏈結 (ARC)</span><span class="sxs-lookup"><span data-stu-id="182e6-238">How Microsoft 365 utilizes Authenticated Received Chain (ARC)</span></span>

<span data-ttu-id="182e6-239">所有 Microsoft 365 中託管的信箱現在都將取得 ARC 帶來的改良式郵件傳送，以及增強式反詐騙防護的權益。</span><span class="sxs-lookup"><span data-stu-id="182e6-239">All hosted mailboxes in Microsoft 365 will now gain the benefit of ARC with improved deliverability of messages and enhanced anti-spoofing protection.</span></span> <span data-ttu-id="182e6-240">當電子郵件從原始伺服器路由傳送到收件者信箱時，ARC 會保留來自所有參與中繼或躍點的電子郵件驗證結果。</span><span class="sxs-lookup"><span data-stu-id="182e6-240">ARC preserves the email authentication results from all participating intermediaries, or hops, when an email is routed from the originating server to the recipient mailbox.</span></span> <span data-ttu-id="182e6-241">在 ARC 之前，透過電子郵件路由傳送中的中繼所執行的修改，(例如轉寄規則或自動簽署)，可能在郵件到達收件者信箱時導致 DMARC 失敗。</span><span class="sxs-lookup"><span data-stu-id="182e6-241">Before ARC, modifications performed by intermediaries in email routing, like forwarding rules or automatic signatures, could cause DMARC failures by the time the email reached the recipient mailbox.</span></span> <span data-ttu-id="182e6-242">使用 ARC，Microsoft 365 可利用其驗證結果的加密保留確認電子郵件寄件者。</span><span class="sxs-lookup"><span data-stu-id="182e6-242">With ARC, the cryptographic preservation of the authentication results allows Microsoft 365 to verify the authenticity of an email's sender.</span></span>

<span data-ttu-id="182e6-243">Microsoft 身為 ARC密封者，因此 Microsoft 365 目前是使用 ARC 來確認驗證結果，但計畫在未來新增協力廠商 ARC 密封者的支援。</span><span class="sxs-lookup"><span data-stu-id="182e6-243">Microsoft 365 currently utilizes ARC to verify authentication results when Microsoft is the ARC Sealer, but plan to add support for third party ARC sealers in the future.</span></span>

## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="182e6-244">對 DMARC 實作進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="182e6-244">Troubleshooting your DMARC implementation</span></span>

<span data-ttu-id="182e6-245">如果您已設定網域的 MX 記錄，其中 EOP 並非第一個項目，則不會針對您的網域強制 DMARC 失敗。</span><span class="sxs-lookup"><span data-stu-id="182e6-245">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span>

<span data-ttu-id="182e6-246">如果您是客戶，且您網域的主要 MX 記錄並未指向 EOP，則您不會取得 DMARC 的效益。</span><span class="sxs-lookup"><span data-stu-id="182e6-246">If you're a customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC.</span></span> <span data-ttu-id="182e6-247">比方說，如果您將 MX 記錄指向內部部署郵件伺服器，並使用連接器將電子郵件路由傳送至 EOP，則不適用 DMARC。</span><span class="sxs-lookup"><span data-stu-id="182e6-247">For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector.</span></span> <span data-ttu-id="182e6-248">在此案例中，接收方網域是您其中一個公認的網域，但 EOP 不是主要的 MX。</span><span class="sxs-lookup"><span data-stu-id="182e6-248">In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX.</span></span> <span data-ttu-id="182e6-249">例如，假設 contoso.com 將其 MX 指向本身，並使用 EOP 作為次要 MX 記錄，contoso.com 的 MX 記錄會如下所示：</span><span class="sxs-lookup"><span data-stu-id="182e6-249">For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>

```text
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

<span data-ttu-id="182e6-250">所有或大部分的電子郵件首先會路由至 mail.contoso.com，因為它是主要的 MX，然後才會將郵件路由至 EOP。</span><span class="sxs-lookup"><span data-stu-id="182e6-250">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP.</span></span> <span data-ttu-id="182e6-251">在某些情況下，您甚至可能不會將 EOP 列為 MX 記錄，而只要接上連接器來傳送電子郵件。</span><span class="sxs-lookup"><span data-stu-id="182e6-251">In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email.</span></span> <span data-ttu-id="182e6-252">EOP 不一定需要是第一個項目，DMARC 驗證也可完成。</span><span class="sxs-lookup"><span data-stu-id="182e6-252">EOP does not have to be the first entry for DMARC validation to be done.</span></span> <span data-ttu-id="182e6-253">它只是可確保驗證，因為我們無法確定所有內部部署/非 O365 伺服器將執行 DMARC 檢查。</span><span class="sxs-lookup"><span data-stu-id="182e6-253">It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.</span></span>  <span data-ttu-id="182e6-254">設定 DMARC TXT 記錄時，就能為客戶的網域 (非伺服器) 強制執行 DMARC，但實際上執行強制執行是由接收端伺服器執行。</span><span class="sxs-lookup"><span data-stu-id="182e6-254">DMARC is eligible to be enforced for a customer's domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.</span></span>  <span data-ttu-id="182e6-255">如果您將 EOP 設定為接收端伺服器，則 EOP 會執行 DMARC 強制執行。</span><span class="sxs-lookup"><span data-stu-id="182e6-255">If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>

:::image type="content" source="../../media/Tp_DMARCTroublehoot.png" alt-text="DMARC 的疑難排解圖形，由 Daniel Mande 提供":::

## <a name="for-more-information"></a><span data-ttu-id="182e6-257">相關資訊</span><span class="sxs-lookup"><span data-stu-id="182e6-257">For more information</span></span>

<span data-ttu-id="182e6-258">Want more information about DMARC?</span><span class="sxs-lookup"><span data-stu-id="182e6-258">Want more information about DMARC?</span></span> <span data-ttu-id="182e6-259">These resources can help.</span><span class="sxs-lookup"><span data-stu-id="182e6-259">These resources can help.</span></span>

- <span data-ttu-id="182e6-260">[反垃圾郵件訊息標頭](anti-spam-message-headers.md) 包含 Microsoft 365 針對 DMARC 檢查所使用的語法及標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="182e6-260">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DMARC checks.</span></span>

- <span data-ttu-id="182e6-261">從 M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG (傳訊、惡意程式碼、行動裝置反不當使用工作群組) 參與 <sup>DMARC 訓練系列課程</sup>。</span><span class="sxs-lookup"><span data-stu-id="182e6-261">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>

- <span data-ttu-id="182e6-262">在 [dmarcian](https://space.dmarcian.com/deployment/) 使用檢查清單。</span><span class="sxs-lookup"><span data-stu-id="182e6-262">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>

- <span data-ttu-id="182e6-263">直接前往來源 [DMARC.org](https://dmarc.org)。</span><span class="sxs-lookup"><span data-stu-id="182e6-263">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>

## <a name="see-also"></a><span data-ttu-id="182e6-264">請參閱</span><span class="sxs-lookup"><span data-stu-id="182e6-264">See also</span></span>

[<span data-ttu-id="182e6-265">Microsoft 365 如何使用寄件者原則架構 (SPF) 來防止詐騙</span><span class="sxs-lookup"><span data-stu-id="182e6-265">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

[<span data-ttu-id="182e6-266">在 Microsoft 365 中設定 SPF 以協助防止詐騙</span><span class="sxs-lookup"><span data-stu-id="182e6-266">Set up SPF in Microsoft 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

[<span data-ttu-id="182e6-267">使用 DKIM 驗證從您在 Microsoft 365 中的自訂網域傳送的輸出電子郵件</span><span class="sxs-lookup"><span data-stu-id="182e6-267">Use DKIM to validate outbound email sent from your custom domain in Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md)
