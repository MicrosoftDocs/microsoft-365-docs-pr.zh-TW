---
title: 寄件者原則架構 (SPF) 如何防止欺騙
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解 Microsoft 365 如何使用寄件者原則框架 (的 SPF) TXT 記錄，以確保目的地電子郵件系統信任從您的自訂網域傳送的郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b6b79957f84e660fe952f88dab18d8934937d875
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167524"
---
# <a name="how-microsoft-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="38ebb-103">Microsoft 365 如何使用寄件者原則架構 (SPF) 來防止詐騙</span><span class="sxs-lookup"><span data-stu-id="38ebb-103">How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="38ebb-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="38ebb-104">**Applies to**</span></span>
- [<span data-ttu-id="38ebb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="38ebb-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="38ebb-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="38ebb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="38ebb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38ebb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="38ebb-108">**摘要：** 本文說明 Microsoft 365 如何使用 DNS 中的寄件者原則框架 (SPF) TXT 記錄，以確保目的地電子郵件系統信任從您的自訂網域傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="38ebb-108">**Summary:** This article describes how Microsoft 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="38ebb-109">這適用于從 Microsoft 365 傳送的輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="38ebb-109">This applies to outbound mail sent from Microsoft 365.</span></span> <span data-ttu-id="38ebb-110">從 Microsoft 365 傳送給 Microsoft 365 內之收件者的郵件，將永遠會透過 SPF。</span><span class="sxs-lookup"><span data-stu-id="38ebb-110">Messages sent from Microsoft 365 to a recipient within Microsoft 365 will always pass SPF.</span></span>

<span data-ttu-id="38ebb-111">SPF TXT 記錄是一種 DNS 記錄，可驗證電子郵件的來源網域名稱，有助於防止詐騙和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="38ebb-111">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent.</span></span> <span data-ttu-id="38ebb-112">SPF 藉由驗證寄件者的 IP 位址對照傳送網域的擁有者，來驗證電子郵件的來源。</span><span class="sxs-lookup"><span data-stu-id="38ebb-112">SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span>

> [!NOTE]
> <span data-ttu-id="38ebb-113">在 2014 年，SPF 記錄類型已被網際網路工程任務推動小組 (IETF) 所取代。</span><span class="sxs-lookup"><span data-stu-id="38ebb-113">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014.</span></span> <span data-ttu-id="38ebb-114">因此，確保您在 DNS 中使用 TXT 記錄來發佈您的 SPF 資訊。</span><span class="sxs-lookup"><span data-stu-id="38ebb-114">Instead, ensure that you use TXT records in DNS to publish your SPF information.</span></span> <span data-ttu-id="38ebb-115">為了清晰明瞭，本文的其餘部分會使用 SPF TXT 記錄一詞。</span><span class="sxs-lookup"><span data-stu-id="38ebb-115">The rest of this article uses the term SPF TXT record for clarity.</span></span>

<span data-ttu-id="38ebb-116">網域系統管理員會在 DNS 的 TXT 記錄中發佈 SPF。</span><span class="sxs-lookup"><span data-stu-id="38ebb-116">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="38ebb-117">SPF 資訊可識別已獲授權的外寄電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="38ebb-117">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="38ebb-118">目的電子郵件系統會驗證郵件來自於已獲授權的外寄電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="38ebb-118">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="38ebb-119">如果您已熟悉 SPF，或您有簡單的部署，但只需要知道要在 Microsoft 365 的 DNS 中包含的 SPF TXT 記錄，您可以在 [microsoft 365 中設定 spf 以協助防止欺騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-119">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Microsoft 365, you can go to [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="38ebb-120">[！附注] 如果您沒有在 Microsoft 365 中完全裝載的部署，或是您想要瞭解 SPF 如何運作的詳細資訊，或如何疑難排解 Microsoft 365 的 SPF，請繼續閱讀。</span><span class="sxs-lookup"><span data-stu-id="38ebb-120">If you do not have a deployment that is fully-hosted in Microsoft 365, or you want more information about how SPF works or how to troubleshoot SPF for Microsoft 365, keep reading.</span></span>

> [!NOTE]
> <span data-ttu-id="38ebb-121">以往，如果您也使用 SharePoint Online，則必須新增不同的 SPF TXT 記錄至您的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="38ebb-121">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="38ebb-122">你不再需要這樣做。</span><span class="sxs-lookup"><span data-stu-id="38ebb-122">This is no longer required.</span></span> <span data-ttu-id="38ebb-123">此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。</span><span class="sxs-lookup"><span data-stu-id="38ebb-123">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="38ebb-124">您不需要立即進行任何變更，但是如果您收到「太多查閱」錯誤，請修改您的 SPF TXT 記錄，如 [Set UP SPF In Microsoft 365 中所述，以協助防止欺騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-124">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>

## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-microsoft-365"></a><span data-ttu-id="38ebb-125">SPF 如何運作，以避免 Microsoft 365 中的欺騙和網路釣魚</span><span class="sxs-lookup"><span data-stu-id="38ebb-125">How SPF works to prevent spoofing and phishing in Microsoft 365</span></span>
<span data-ttu-id="38ebb-126"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-126"><a name="HowSPFWorks"> </a></span></span>

<span data-ttu-id="38ebb-127">SPF 決定是否允許寄件者代表網域傳送。</span><span class="sxs-lookup"><span data-stu-id="38ebb-127">SPF determines whether or not a sender is permitted to send on behalf of a domain.</span></span> <span data-ttu-id="38ebb-128">如果不允許收件者這麼做，也就是說，如果電子郵件未通過接收伺服器上的 SPF 檢查，則在該伺服器上設定的垃圾郵件原則會決定該郵件的處理方式。</span><span class="sxs-lookup"><span data-stu-id="38ebb-128">If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>

<span data-ttu-id="38ebb-129">每個 SPF TXT 記錄都包含三個部分：屬於 SPF TXT 記錄的宣告、能夠從您的網域及可代表您網域傳送的外部網域傳送郵件的 IP 位址，以及強制規則。</span><span class="sxs-lookup"><span data-stu-id="38ebb-129">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="38ebb-130">有效的 SPF TXT 記錄需要具備這三個部分。</span><span class="sxs-lookup"><span data-stu-id="38ebb-130">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="38ebb-131">本文說明您如何形成 SPF TXT 記錄，並提供使用 Microsoft 365 中服務的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="38ebb-131">This article describes how you form your SPF TXT record and provides best practices for working with the services in Microsoft 365.</span></span> <span data-ttu-id="38ebb-132">此外，也提供與網域註冊機構一起努力將記錄發佈到 DNS 的相關指示的連結。</span><span class="sxs-lookup"><span data-stu-id="38ebb-132">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>

### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="38ebb-133">SPF 基本概念：能夠從您的自訂網域傳送的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="38ebb-133">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="38ebb-134"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-134"><a name="SPFBasicsIPaddresses"> </a></span></span>

<span data-ttu-id="38ebb-135">查看 SPF 規則的基本語法：</span><span class="sxs-lookup"><span data-stu-id="38ebb-135">Take a look at the basic syntax for an SPF rule:</span></span>

<span data-ttu-id="38ebb-136">v = spf1 \<IP\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="38ebb-136">v=spf1 \<IP\> \<enforcement rule\></span></span>

<span data-ttu-id="38ebb-137">例如，假設 contoso.com 有下列 SPF 規則：</span><span class="sxs-lookup"><span data-stu-id="38ebb-137">For example, let's say the following SPF rule exists for contoso.com:</span></span>

<span data-ttu-id="38ebb-138">v = spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\>\<enforcement rule\></span><span class="sxs-lookup"><span data-stu-id="38ebb-138">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>

<span data-ttu-id="38ebb-139">在此範例中，SPF 規則會指示接收電子郵件伺服器僅接受來自 contoso.com 網域的下列 IP 位址的郵件：</span><span class="sxs-lookup"><span data-stu-id="38ebb-139">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>

- <span data-ttu-id="38ebb-140">IP 位址 #1</span><span class="sxs-lookup"><span data-stu-id="38ebb-140">IP address #1</span></span>

- <span data-ttu-id="38ebb-141">IP 位址 #2</span><span class="sxs-lookup"><span data-stu-id="38ebb-141">IP address #2</span></span>

- <span data-ttu-id="38ebb-142">IP 位址 #3</span><span class="sxs-lookup"><span data-stu-id="38ebb-142">IP address #3</span></span>

<span data-ttu-id="38ebb-143">此 SPF 規則會告訴接收電子郵件伺服器，如果郵件來自 contoso.com，而不是來自這三個 IP 位址之一，則接收伺服器應將強制規則套用至該郵件。</span><span class="sxs-lookup"><span data-stu-id="38ebb-143">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message.</span></span> <span data-ttu-id="38ebb-144">強制規則通常為下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="38ebb-144">The enforcement rule is usually one of these options:</span></span>

- <span data-ttu-id="38ebb-145">**封鎖性失敗。**</span><span class="sxs-lookup"><span data-stu-id="38ebb-145">**Hard fail.**</span></span> <span data-ttu-id="38ebb-146">在郵件信封中將此郵件標示為「封鎖性失敗」，然後遵循接收伺服器針對這類郵件設定的垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="38ebb-146">Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span>

- <span data-ttu-id="38ebb-147">**非封鎖性失敗。**</span><span class="sxs-lookup"><span data-stu-id="38ebb-147">**Soft fail.**</span></span> <span data-ttu-id="38ebb-148">在郵件信封中將此郵件標示為「非封鎖性失敗」。</span><span class="sxs-lookup"><span data-stu-id="38ebb-148">Mark the message with 'soft fail' in the message envelope.</span></span> <span data-ttu-id="38ebb-149">通常電子郵件伺服器會設定為無論如何都會傳遞這些郵件。</span><span class="sxs-lookup"><span data-stu-id="38ebb-149">Typically, email servers are configured to deliver these messages anyway.</span></span> <span data-ttu-id="38ebb-150">大部分的使用者都不會看到此標記。</span><span class="sxs-lookup"><span data-stu-id="38ebb-150">Most end users do not see this mark.</span></span>

- <span data-ttu-id="38ebb-151">**中性。**</span><span class="sxs-lookup"><span data-stu-id="38ebb-151">**Neutral.**</span></span> <span data-ttu-id="38ebb-152">不執行任何動作，也就是不要標示郵件信封。</span><span class="sxs-lookup"><span data-stu-id="38ebb-152">Do nothing, that is, do not mark the message envelope.</span></span> <span data-ttu-id="38ebb-153">這通常會為了進行測試而保留，但很少使用。</span><span class="sxs-lookup"><span data-stu-id="38ebb-153">This is usually reserved for testing purposes and is rarely used.</span></span>

<span data-ttu-id="38ebb-154">下列範例顯示 SPF 在不同情況下的運作方式。</span><span class="sxs-lookup"><span data-stu-id="38ebb-154">The following examples show how SPF works in different situations.</span></span> <span data-ttu-id="38ebb-155">在這些範例中，contoso.com 是寄件者，而 woodgrovebank.com 是接收者。</span><span class="sxs-lookup"><span data-stu-id="38ebb-155">In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>

### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="38ebb-156">範例 1：直接從寄件者傳送到接收者之訊息的電子郵件驗證</span><span class="sxs-lookup"><span data-stu-id="38ebb-156">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="38ebb-157"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-157"><a name="spfExample1"> </a></span></span>

<span data-ttu-id="38ebb-158">從寄件者到接收者的路徑是直接路徑時，SPF 的效果最好，例如：</span><span class="sxs-lookup"><span data-stu-id="38ebb-158">SPF works best when the path from sender to receiver is direct, for example:</span></span>

![此圖顯示 SPF 如何驗證直接從伺服器傳送至伺服器的電子郵件。](../../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)

<span data-ttu-id="38ebb-160">當 woodgrovebank.com 收到訊息時，如果 IP 位址 #1 位於 contoso.com 的 SPF TXT 記錄中，則訊息會通過 SPF 檢查並經過驗證。</span><span class="sxs-lookup"><span data-stu-id="38ebb-160">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>

### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="38ebb-161">範例2：偽造的寄件者位址未通過 SPF 檢查</span><span class="sxs-lookup"><span data-stu-id="38ebb-161">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="38ebb-162"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-162"><a name="spfExample2"> </a></span></span>

<span data-ttu-id="38ebb-163">假設網路釣魚者找到欺騙 contoso.com 的方法：</span><span class="sxs-lookup"><span data-stu-id="38ebb-163">Suppose a phisher finds a way to spoof contoso.com:</span></span>

![此圖顯示 SPF 如何驗證從偽造的伺服器所傳送的電子郵件。](../../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)

<span data-ttu-id="38ebb-165">由於 IP 位址 #12 不在 contoso.com 的 SPF TXT 記錄中，所以郵件無法通過 SPF 檢查，而接收者可選擇將其標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="38ebb-165">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>

### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="38ebb-166">範例3：SPF 和轉寄的訊息</span><span class="sxs-lookup"><span data-stu-id="38ebb-166">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="38ebb-167"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-167"><a name="spfExample3"> </a></span></span>

<span data-ttu-id="38ebb-168">SPF 的其中一個缺點就是已轉寄電子郵件時就無法運作。</span><span class="sxs-lookup"><span data-stu-id="38ebb-168">One drawback of SPF is that it doesn't work when an email has been forwarded.</span></span> <span data-ttu-id="38ebb-169">例如，假設 woodgrovebank.com 的使用者已設定轉寄規則，以將所有電子郵件傳送到 outlook.com 帳戶：</span><span class="sxs-lookup"><span data-stu-id="38ebb-169">For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>

![此圖顯示 SPF 在訊息被轉送時無法驗證電子郵件。](../../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)

<span data-ttu-id="38ebb-171">這封郵件原先在 woodgrovebank.com 通過 SPF 檢查，但在 outlook.com 未通過 SPF 檢查，因為 IP #25 不在 contoso.com 的 SPF TXT 記錄中。</span><span class="sxs-lookup"><span data-stu-id="38ebb-171">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record.</span></span> <span data-ttu-id="38ebb-172">Outlook.com 接著可能會將郵件標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="38ebb-172">Outlook.com might then mark the message as spam.</span></span> <span data-ttu-id="38ebb-173">若要解決此問題，請將 SPF 與其他電子郵件驗證方法 (例如 DKIM 和 DMARC) 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="38ebb-173">To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>

### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="38ebb-174">SPF 基本概念：包括可代表您的網域傳送郵件的第三方網域</span><span class="sxs-lookup"><span data-stu-id="38ebb-174">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="38ebb-175"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-175"><a name="SPFBasicsIncludes"> </a></span></span>

<span data-ttu-id="38ebb-176">除了 IP 位址以外，您也可以將 SPF TXT 記錄設定為包含網域作為寄件者。</span><span class="sxs-lookup"><span data-stu-id="38ebb-176">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders.</span></span> <span data-ttu-id="38ebb-177">這些網域會以 "include" 陳述式形式新增到 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-177">These are added to the SPF TXT record as "include" statements.</span></span> <span data-ttu-id="38ebb-178">例如，contoso.com 可能想包含來自 contoso.net 及其從屬 contoso.org 的郵件伺服器的所有 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="38ebb-178">For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns.</span></span> <span data-ttu-id="38ebb-179">為了這麼做，contoso.com 會發佈類似以下的 SPF TXT 記錄：</span><span class="sxs-lookup"><span data-stu-id="38ebb-179">To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>

```text
v=spf1 include:contoso.net include:contoso.org -all
```

<span data-ttu-id="38ebb-180">當接收伺服器在 DNS 中看到此記錄時，也會在 contoso.net 的 SPF TXT 記錄上執行 DNS 查閱，然後再針對 contoso.org 執行 DNS 查閱。如果在 contoso.net 或 contoso.org 的記錄內發現額外的 include 陳述式，也會遵循上述動作。</span><span class="sxs-lookup"><span data-stu-id="38ebb-180">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="38ebb-181">為了防止拒絕服務攻擊，單一電子郵件的 DNS 查閱上限為 10。</span><span class="sxs-lookup"><span data-stu-id="38ebb-181">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="38ebb-182">每個 include 陳述式都代表一個額外的 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="38ebb-182">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="38ebb-183">如果訊息超過 10 個限制，該訊息便無法通過 SPF。</span><span class="sxs-lookup"><span data-stu-id="38ebb-183">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="38ebb-184">當訊息達到此限制 (視接收伺服器的設定方式而定)，寄件者可能會收到一則訊息，指出訊息產生「太多查閱」，或「已超過郵件的最大躍點計數」(這可能發生於查閱執行迴圈並超越 DNS 逾時的時候)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-184">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="38ebb-185">如需如何避免這種情況的秘訣，請參閱 [疑難排解： Microsoft 365 中 SPF 的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-185">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="requirements-for-your-spf-txt-record-and-microsoft-365"></a><span data-ttu-id="38ebb-186">您的 SPF TXT 記錄和 Microsoft 365 的需求</span><span class="sxs-lookup"><span data-stu-id="38ebb-186">Requirements for your SPF TXT record and Microsoft 365</span></span>
<span data-ttu-id="38ebb-187"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-187"><a name="SPFReqsinO365"> </a></span></span>

<span data-ttu-id="38ebb-188">如果您在設定 Microsoft 365 時設定郵件，您已建立 SPF TXT 記錄，將 Microsoft 郵件伺服器識別為您的網域合法的郵件來源。</span><span class="sxs-lookup"><span data-stu-id="38ebb-188">If you set up mail when you set up Microsoft 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="38ebb-189">此記錄如下所示：</span><span class="sxs-lookup"><span data-stu-id="38ebb-189">This record probably looks like this:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="38ebb-190">如果您是完全主控的客戶，也就是沒有任何內部部署郵件伺服器傳送輸出郵件，這是您需要為 Office 365 發行的唯一 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-190">If you're a fully-hosted customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>

<span data-ttu-id="38ebb-191">如果您有混合式部署 (，也就是您的某些信箱內部部署和部分主控于 Microsoft 365) ，或者如果您是 Exchange Online Protection (EOP) 獨立客戶 (也就是說，您的組織使用 EOP 來保護您的內部部署信箱) ，您應該將每個內部部署 edge 郵件伺服器的輸出 IP 位址新增至 DNS 中的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-191">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Microsoft 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>

## <a name="form-your-spf-txt-record-for-microsoft-365"></a><span data-ttu-id="38ebb-192">套用 Microsoft 365 的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="38ebb-192">Form your SPF TXT record for Microsoft 365</span></span>
<span data-ttu-id="38ebb-193"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-193"><a name="FormYourSPF"> </a></span></span>

<span data-ttu-id="38ebb-194">使用本文中的語法資訊，構成自訂網域的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-194">Use the syntax information in this article to form the SPF TXT record for your custom domain.</span></span> <span data-ttu-id="38ebb-195">雖然還有其他此處未提及的語法選項，以下是最常使用的選項。</span><span class="sxs-lookup"><span data-stu-id="38ebb-195">Although there are other syntax options that are not mentioned here, these are the most commonly used options.</span></span> <span data-ttu-id="38ebb-196">一旦您已形成記錄，您需要在網域註冊機構中更新記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-196">Once you have formed your record, you need to update the record at your domain registrar.</span></span>

<span data-ttu-id="38ebb-197">如需您需要在 Microsoft 365 中包含的網域相關資訊，請參閱 [SPF 所需的外部 DNS 記錄](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-197">For information about the domains you will need to include for Microsoft 365, see [External DNS records required for SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span> <span data-ttu-id="38ebb-198">使用[逐步指示](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam)來更新您網域註冊機構的 SPF (TXT) 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-198">Use the [step-by-step instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for updating SPF (TXT) records for your domain registrar.</span></span>

### <a name="spf-txt-record-syntax-for-microsoft-365"></a><span data-ttu-id="38ebb-199">Microsoft 365 的 SPF TXT 記錄語法</span><span class="sxs-lookup"><span data-stu-id="38ebb-199">SPF TXT record syntax for Microsoft 365</span></span>
<span data-ttu-id="38ebb-200"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-200"><a name="SPFSyntaxO365"> </a></span></span>

<span data-ttu-id="38ebb-201">Microsoft 365 的一般 SPF TXT 記錄具有下列語法：</span><span class="sxs-lookup"><span data-stu-id="38ebb-201">A typical SPF TXT record for Microsoft 365 has the following syntax:</span></span>

```text
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="38ebb-202">例如：</span><span class="sxs-lookup"><span data-stu-id="38ebb-202">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="38ebb-203">其中：</span><span class="sxs-lookup"><span data-stu-id="38ebb-203">where:</span></span>

- <span data-ttu-id="38ebb-204">**v=spf1** 是必要的。</span><span class="sxs-lookup"><span data-stu-id="38ebb-204">**v=spf1** is required.</span></span> <span data-ttu-id="38ebb-205">這會將 TXT 記錄定義為 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-205">This defines the TXT record as an SPF TXT record.</span></span>

- <span data-ttu-id="38ebb-206">**ip4** 表示您正在使用 IP 版本 4 位址。</span><span class="sxs-lookup"><span data-stu-id="38ebb-206">**ip4** indicates that you are using IP version 4 addresses.</span></span> <span data-ttu-id="38ebb-207">**ip6** 表示您正在使用 IP 版本 6 位址。</span><span class="sxs-lookup"><span data-stu-id="38ebb-207">**ip6** indicates that you are using IP version 6 addresses.</span></span> <span data-ttu-id="38ebb-208">如果您使用 IPv6 IP 位址，請將本文範例中的 **ip4** 換成 **ip6**。</span><span class="sxs-lookup"><span data-stu-id="38ebb-208">If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article.</span></span> <span data-ttu-id="38ebb-209">您也可以使用 CIDR 表示法來指定 IP 位址範圍，例如 **ip4:192.168.0.1/26**。</span><span class="sxs-lookup"><span data-stu-id="38ebb-209">You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>

- <span data-ttu-id="38ebb-210">「IP 位址」是您要新增至 SPF TXT 記錄的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="38ebb-210">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="38ebb-211">通常，這是貴組織的外寄郵件伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="38ebb-211">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="38ebb-212">您可以列出多個外寄郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="38ebb-212">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="38ebb-213">如需詳細資訊，請參閱 [範例：多個輸出內部部署郵件伺服器和 Microsoft 365 的 SPF TXT 記錄](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-213">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>

- <span data-ttu-id="38ebb-214">「網域名稱」是您要新增為合法寄件者的網域。</span><span class="sxs-lookup"><span data-stu-id="38ebb-214">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="38ebb-215">如需您應為 Microsoft 365 包含的功能變數名稱清單，請參閱 [SPF 所需的外部 DNS 記錄](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-215">For a list of domain names you should include for Microsoft 365, see [External DNS records required for SPF](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records).</span></span>

- <span data-ttu-id="38ebb-216">強制規則通常為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="38ebb-216">Enforcement rule is usually one of the following:</span></span>

  - <span data-ttu-id="38ebb-217">-all</span><span class="sxs-lookup"><span data-stu-id="38ebb-217">-all</span></span>

    <span data-ttu-id="38ebb-218">表示封鎖性失敗。</span><span class="sxs-lookup"><span data-stu-id="38ebb-218">Indicates hard fail.</span></span> <span data-ttu-id="38ebb-219">如果您知道您網域的所有授權 IP 位址，請在 SPF TXT 記錄中列出這些位址，並使用 -all (封鎖性失敗) 限定詞。</span><span class="sxs-lookup"><span data-stu-id="38ebb-219">If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier.</span></span> <span data-ttu-id="38ebb-220">此外，如果您只使用 SPF，也就是您使用的不是 DMARC 或 DKIM，則應該使用 -all 限定詞。</span><span class="sxs-lookup"><span data-stu-id="38ebb-220">Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier.</span></span> <span data-ttu-id="38ebb-221">建議您一律使用這個限定詞。</span><span class="sxs-lookup"><span data-stu-id="38ebb-221">We recommend that you use always this qualifier.</span></span>

  - <span data-ttu-id="38ebb-222">~all</span><span class="sxs-lookup"><span data-stu-id="38ebb-222">~all</span></span>

    <span data-ttu-id="38ebb-223">表示非封鎖性失敗。</span><span class="sxs-lookup"><span data-stu-id="38ebb-223">Indicates soft fail.</span></span> <span data-ttu-id="38ebb-224">如果您不確定是否有完整的 IP 位址清單，則應該使用 ~all (非封鎖性失敗) 限定詞。</span><span class="sxs-lookup"><span data-stu-id="38ebb-224">If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier.</span></span> <span data-ttu-id="38ebb-225">此外，如果您使用 p=quarantine 或 p=reject 的 DMARC，則可使用 ~ all。</span><span class="sxs-lookup"><span data-stu-id="38ebb-225">Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all.</span></span> <span data-ttu-id="38ebb-226">否則，使用 -all。</span><span class="sxs-lookup"><span data-stu-id="38ebb-226">Otherwise, use -all.</span></span>

  - <span data-ttu-id="38ebb-227">?all</span><span class="sxs-lookup"><span data-stu-id="38ebb-227">?all</span></span>

    <span data-ttu-id="38ebb-228">表示中性。</span><span class="sxs-lookup"><span data-stu-id="38ebb-228">Indicates neutral.</span></span> <span data-ttu-id="38ebb-229">這在測試 SPF 時使用。</span><span class="sxs-lookup"><span data-stu-id="38ebb-229">This is used when testing SPF.</span></span> <span data-ttu-id="38ebb-230">不建議您在即時部署中使用此限定詞。</span><span class="sxs-lookup"><span data-stu-id="38ebb-230">We do not recommend that you use this qualifier in your live deployment.</span></span>

### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-microsoft-365"></a><span data-ttu-id="38ebb-231">範例： Microsoft 365 傳送所有郵件時使用的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="38ebb-231">Example: SPF TXT record to use when all of your mail is sent by Microsoft 365</span></span>
<span data-ttu-id="38ebb-232"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-232"><a name="ExampleSPFNoSP"> </a></span></span>

<span data-ttu-id="38ebb-233">如果所有的郵件都是由 Microsoft 365 傳送，請在您的 SPF TXT 記錄中使用此功能：</span><span class="sxs-lookup"><span data-stu-id="38ebb-233">If all of your mail is sent by Microsoft 365, use this in your SPF TXT record:</span></span>

```text
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-microsoft-365"></a><span data-ttu-id="38ebb-234">範例：具有一個內部部署 Exchange Server 和 Microsoft 365 的混合式案例的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="38ebb-234">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Microsoft 365</span></span>
<span data-ttu-id="38ebb-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-235"><a name="ExampleSPFHybridOneExchangeServer"> </a></span></span>

<span data-ttu-id="38ebb-236">在混合式環境中，如果內部部署 Exchange Server 的 IP 位址是 192.168.0.1，若要將 SPF 強制規則設為封鎖性失敗，請構成如下所示的 SPF TXT 記錄：</span><span class="sxs-lookup"><span data-stu-id="38ebb-236">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>

```text
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-microsoft-365"></a><span data-ttu-id="38ebb-237">範例：多個輸出內部部署郵件伺服器和 Microsoft 365 的 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="38ebb-237">Example: SPF TXT record for multiple outbound on-premises mail servers and Microsoft 365</span></span>
<span data-ttu-id="38ebb-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-238"><a name="ExampleSPFMultipleMailServerO365"> </a></span></span>

<span data-ttu-id="38ebb-239">如果您有多部外寄郵件伺服器，請將每部郵件伺服器的 IP 位址包含在 SPF TXT 記錄中，並使用一個空格再加上 "ip4:" 陳述式來分隔每個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="38ebb-239">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement.</span></span> <span data-ttu-id="38ebb-240">例如：</span><span class="sxs-lookup"><span data-stu-id="38ebb-240">For example:</span></span>

```text
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-microsoft-365"></a><span data-ttu-id="38ebb-241">後續步驟：設定 Microsoft 365 的 SPF</span><span class="sxs-lookup"><span data-stu-id="38ebb-241">Next steps: Set up SPF for Microsoft 365</span></span>
<span data-ttu-id="38ebb-242"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-242"><a name="SPFNextSteps"> </a></span></span>

<span data-ttu-id="38ebb-243">一旦您已制定 SPF TXT 記錄，請遵循在 [Microsoft 365 中設定 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 中的步驟，協助防止哄騙將其新增至您的網域。</span><span class="sxs-lookup"><span data-stu-id="38ebb-243">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span>

<span data-ttu-id="38ebb-244">雖然 SPF 的設計訴求是要協助防止詐騙，但是有 SPF 無法防護的詐騙技術。</span><span class="sxs-lookup"><span data-stu-id="38ebb-244">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="38ebb-245">為了避免這些情況，在您設定 SPF 之後，您也應該設定 DKIM 和 DMARC for Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="38ebb-245">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Microsoft 365.</span></span> <span data-ttu-id="38ebb-246">若要開始使用，請參閱 [使用 DKIM 驗證從 Microsoft 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-246">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Microsoft 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="38ebb-247">接下來，請參閱[在 Microsoft 365 中使用 DMARC 來驗證電子郵件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-247">Next, see [Use DMARC to validate email in Microsoft 365](use-dmarc-to-validate-email.md).</span></span>

## <a name="troubleshooting-best-practices-for-spf-in-microsoft-365"></a><span data-ttu-id="38ebb-248">疑難排解： Microsoft 365 中 SPF 的最佳作法</span><span class="sxs-lookup"><span data-stu-id="38ebb-248">Troubleshooting: Best practices for SPF in Microsoft 365</span></span>
<span data-ttu-id="38ebb-249"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-249"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="38ebb-250">您只能為您的自訂網域建立一筆 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-250">You can only create one SPF TXT record for your custom domain.</span></span> <span data-ttu-id="38ebb-251">建立多筆記錄會導致循環配置情況，且 SPF 會失敗。</span><span class="sxs-lookup"><span data-stu-id="38ebb-251">Creating multiple records causes a round robin situation and SPF will fail.</span></span> <span data-ttu-id="38ebb-252">若要避免這種情況，您可以為每個子網域建立不同的記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-252">To avoid this, you can create separate records for each subdomain.</span></span> <span data-ttu-id="38ebb-253">例如，為 contoso.com 建立一筆記錄，並為 bulkmail.contoso.com 建立另一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-253">For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>

<span data-ttu-id="38ebb-254">如果電子郵件在傳遞前造成超過 10 個 DNS 查閱，則接收郵件伺服器將會以永久性錯誤 (也稱為 permerror) 回應，並導致該郵件未通過 SPF 檢查。</span><span class="sxs-lookup"><span data-stu-id="38ebb-254">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check.</span></span> <span data-ttu-id="38ebb-255">接收伺服器也可能會以包含類似以下錯誤的未傳遞回報 (NDR) 回應：</span><span class="sxs-lookup"><span data-stu-id="38ebb-255">The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>

- <span data-ttu-id="38ebb-256">郵件超過躍點計數。</span><span class="sxs-lookup"><span data-stu-id="38ebb-256">The message exceeded the hop count.</span></span>

- <span data-ttu-id="38ebb-257">郵件需要太多查閱。</span><span class="sxs-lookup"><span data-stu-id="38ebb-257">The message required too many lookups.</span></span>

## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-microsoft-365"></a><span data-ttu-id="38ebb-258">在使用協力廠商網域與 Microsoft 365 時，避免出現「太多查閱」錯誤</span><span class="sxs-lookup"><span data-stu-id="38ebb-258">Avoiding the "too many lookups" error when you use third-party domains with Microsoft 365</span></span>
<span data-ttu-id="38ebb-259"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-259"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="38ebb-260">第三方網域的部分 SPF TXT 記錄會引導接收伺服器直接執行大量 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="38ebb-260">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups.</span></span> <span data-ttu-id="38ebb-261">例如，在撰寫本文時，Salesforce.com 在其記錄中包含 5 個 include 陳述式：</span><span class="sxs-lookup"><span data-stu-id="38ebb-261">For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>

```text
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="38ebb-262">為了避免此錯誤，您可以在任何人傳送大量電子郵件時實作原則，例如必須特別為此目的使用子網域。</span><span class="sxs-lookup"><span data-stu-id="38ebb-262">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose.</span></span> <span data-ttu-id="38ebb-263">然後為包含大量電子郵件的子網域定義不同的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-263">You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>

 <span data-ttu-id="38ebb-264">在某些情況下 (例如 salesforce.com 範例)，您必須在 SPF TXT 記錄中使用此網域，但是在其他情況下，第三方可能已經建立了子網域供您用於此目的。</span><span class="sxs-lookup"><span data-stu-id="38ebb-264">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose.</span></span> <span data-ttu-id="38ebb-265">例如，exacttarget.com 已建立了您必須用於 SPF TXT 記錄的子網域：</span><span class="sxs-lookup"><span data-stu-id="38ebb-265">For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span>

```text
cust-spf.exacttarget.com
```

<span data-ttu-id="38ebb-266">當您在 SPF TXT 記錄中包含第三方網域時，您必須向第三方確認要使用哪個網域或子網域，以避免遇到 10 個查閱限制。</span><span class="sxs-lookup"><span data-stu-id="38ebb-266">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>

## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="38ebb-267">如何檢視您目前的 SPF TXT 記錄，並決定其所需的查閱數目</span><span class="sxs-lookup"><span data-stu-id="38ebb-267">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="38ebb-268"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-268"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="38ebb-269">您可以使用 nslookup 來檢視您的 DNS 記錄，包括您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="38ebb-269">You can use nslookup to view your DNS records, including your SPF TXT record.</span></span> <span data-ttu-id="38ebb-270">或者，如果想要，有許多免費的線上工具可讓您用來檢視 SPF TXT 記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="38ebb-270">Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record.</span></span> <span data-ttu-id="38ebb-271">查看您的 SPF TXT 記錄並遵循 include 陳述式和重新導向鏈，即可決定記錄需要多少個 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="38ebb-271">By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires.</span></span> <span data-ttu-id="38ebb-272">有些線上工具甚至會為您計算並顯示這些查閱。</span><span class="sxs-lookup"><span data-stu-id="38ebb-272">Some online tools will even count and display these lookups for you.</span></span> <span data-ttu-id="38ebb-273">追蹤此數字有助於防止從貴組織傳送的郵件觸發來自接收伺服器的永久性錯誤 (稱為 permerror)。</span><span class="sxs-lookup"><span data-stu-id="38ebb-273">Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="38ebb-274">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="38ebb-274">For more information</span></span>
<span data-ttu-id="38ebb-275"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="38ebb-275"><a name="SPFTroubleshoot"> </a></span></span>

<span data-ttu-id="38ebb-276">需要新增 SPF TXT 記錄的說明嗎？</span><span class="sxs-lookup"><span data-stu-id="38ebb-276">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="38ebb-277">閱讀此文章 [：在任何 dns 主機服務提供者（適用于 microsoft 365）上建立 dns 記錄](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) ，以取得與 microsoft 365 中的自訂網域使用的寄件者原則架構的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="38ebb-277">Read the article [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider#add-a-txt-record-for-spf-to-help-prevent-email-spam) for detailed information about usage of Sender Policy Framework with your custom domain in Microsoft 365.</span></span> <span data-ttu-id="38ebb-278">[反垃圾郵件訊息標頭](anti-spam-message-headers.md) 包含 Microsoft 365 用於 SPF 檢查的語法及標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="38ebb-278">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for SPF checks.</span></span>


