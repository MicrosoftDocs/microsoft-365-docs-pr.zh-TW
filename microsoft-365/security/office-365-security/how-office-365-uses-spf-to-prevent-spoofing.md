---
title: Office 365 如何使用寄件者原則架構 (SPF) 來防範詐騙
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
description: 摘要： 本文說明 Office 365 如何使用寄件者原則架構 (SPF) TXT 記錄在 DNS 中以確保目的地電子郵件系統信任自您自訂網域傳送的郵件。 這適用於從 Office 365 傳送的外寄郵件。 從 Office 365 傳送到 Office 365 內的收件者的郵件將會一律通過 SPF。
ms.openlocfilehash: 2845fc9b20b337764159d9debc04f165dcb4bf62
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076846"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="cb85b-105">Office 365 如何使用寄件者原則架構 (SPF) 來防範詐騙</span><span class="sxs-lookup"><span data-stu-id="cb85b-105">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

 <span data-ttu-id="cb85b-106">**摘要：** 本文說明 Office 365 如何使用寄件者原則架構 (SPF) TXT 記錄在 DNS 中以確保目的地電子郵件系統信任自您自訂網域傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-106">**Summary:** This article describes how Office 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain.</span></span> <span data-ttu-id="cb85b-107">這適用於從 Office 365 傳送的外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-107">This applies to outbound mail sent from Office 365.</span></span> <span data-ttu-id="cb85b-108">從 Office 365 傳送到 Office 365 內的收件者的郵件將會一律通過 SPF。</span><span class="sxs-lookup"><span data-stu-id="cb85b-108">Messages sent from Office 365 to a recipient within Office 365 will always pass SPF.</span></span> 
  
<span data-ttu-id="cb85b-109">SPF TXT 記錄會驗證送出的電子郵件的網域名稱是 DNS 記錄，以協助防止詐騙和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="cb85b-109">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent.</span></span> <span data-ttu-id="cb85b-110">SPF 所指稱的擁有者為傳送網域的寄件者的 IP 位址驗證電子郵件訊息的原點而言。</span><span class="sxs-lookup"><span data-stu-id="cb85b-110">SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cb85b-111">SPF 記錄類型已在 2014年中取代由網際網路工程任務推動小組 (IETF)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-111">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014.</span></span> <span data-ttu-id="cb85b-112">相反地，請確定在 DNS 中使用 TXT 記錄，以發佈您的 SPF 資訊。</span><span class="sxs-lookup"><span data-stu-id="cb85b-112">Instead, ensure that you use TXT records in DNS to publish your SPF information.</span></span> <span data-ttu-id="cb85b-113">本文的其餘部分會使用該字詞的 SPF TXT 記錄以方便識別。</span><span class="sxs-lookup"><span data-stu-id="cb85b-113">The rest of this article uses the term SPF TXT record for clarity.</span></span> 
  
<span data-ttu-id="cb85b-114">網域系統管理員在 DNS 中的 TXT 記錄中發佈 SPF 資訊。</span><span class="sxs-lookup"><span data-stu-id="cb85b-114">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="cb85b-115">SPF 資訊會識別已授權的輸出電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb85b-115">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="cb85b-116">目的地電子郵件系統確認郵件來自 [已授權的輸出電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb85b-116">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="cb85b-117">如果您已熟悉 SPF，或您有簡單的部署，並只需要知道要納入您的 SPF TXT 記錄，在 DNS 中運作的 Office 365，您可以移至[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-117">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Office 365, you can go to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="cb85b-118">如果您不需要是完全裝載於 Office 365 的部署或您想 SPF 的運作方式或如何疑難排解 Office 365 的 SPF，讓閱讀的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cb85b-118">If you do not have a deployment that is fully-hosted in Office 365, or you want more information about how SPF works or how to troubleshoot SPF for Office 365, keep reading.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb85b-119">先前，您必須將不同的 SPF TXT 記錄新增至您的自訂網域，如果您也使用 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="cb85b-119">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="cb85b-120">你不再需要這樣做。</span><span class="sxs-lookup"><span data-stu-id="cb85b-120">This is no longer required.</span></span> <span data-ttu-id="cb85b-121">此變更會降低 SharePoint Online 通知訊息被置於「垃圾電子郵件」資料夾的機率。</span><span class="sxs-lookup"><span data-stu-id="cb85b-121">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="cb85b-122">您不需要進行任何變更立即，但如果您收到 「 太多查閱 」 錯誤，修改您的 SPF TXT 記錄中[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)所述。</span><span class="sxs-lookup"><span data-stu-id="cb85b-122">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> 
     
## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a><span data-ttu-id="cb85b-123">若要防止詐騙及 Office 365 中的網路釣魚 SPF 的運作方式</span><span class="sxs-lookup"><span data-stu-id="cb85b-123">How SPF works to prevent spoofing and phishing in Office 365</span></span>
<span data-ttu-id="cb85b-124"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-124"></span></span>

<span data-ttu-id="cb85b-125">SPF 會決定允許寄件者的傳送代理者網域。</span><span class="sxs-lookup"><span data-stu-id="cb85b-125">SPF determines whether or not a sender is permitted to send on behalf of a domain.</span></span> <span data-ttu-id="cb85b-126">如果寄件者不允許若要這麼做，亦即，如果電子郵件失敗 SPF 檢查在接收伺服器上，在該伺服器上設定垃圾郵件原則決定如何處理郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-126">If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>
  
<span data-ttu-id="cb85b-127">每個 SPF TXT 記錄包含三個部分： 宣告很 SPF TXT 記錄，可以從您的網域，可以傳送在您的網域代理，並強制執行規則的外部網域傳送郵件的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb85b-127">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule.</span></span> <span data-ttu-id="cb85b-128">您需要有效的 SPF TXT 記錄中的所有三個。</span><span class="sxs-lookup"><span data-stu-id="cb85b-128">You need all three in a valid SPF TXT record.</span></span> <span data-ttu-id="cb85b-129">本文將告訴您如何形成 SPF TXT 記錄，並提供最佳作法來使用 Office 365 中的服務。</span><span class="sxs-lookup"><span data-stu-id="cb85b-129">This article describes how you form your SPF TXT record and provides best practices for working with the services in Office 365.</span></span> <span data-ttu-id="cb85b-130">也提供指示，說明如何使用您的網域註冊機構的 DNS 來發佈您的記錄的連結。</span><span class="sxs-lookup"><span data-stu-id="cb85b-130">Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>
  
### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="cb85b-131">SPF 基本概念： 允許從您的自訂網域傳送的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cb85b-131">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="cb85b-132"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-132"></span></span>

<span data-ttu-id="cb85b-133">請看一下 SPF 規則的基本語法：</span><span class="sxs-lookup"><span data-stu-id="cb85b-133">Take a look at the basic syntax for an SPF rule:</span></span>
  
<span data-ttu-id="cb85b-134">v = spf1 \<IP\> \<強制執行規則\></span><span class="sxs-lookup"><span data-stu-id="cb85b-134">v=spf1 \<IP\> \<enforcement rule\></span></span>
  
<span data-ttu-id="cb85b-135">例如，假設 contoso.com 有下列 SPF 規則：</span><span class="sxs-lookup"><span data-stu-id="cb85b-135">For example, let's say the following SPF rule exists for contoso.com:</span></span>
  
<span data-ttu-id="cb85b-136">v = spf1 \<#1 的 IP 位址\> \<IP 位址為 #2\> \<#3 的 IP 位址\>\<強制執行規則\></span><span class="sxs-lookup"><span data-stu-id="cb85b-136">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>
  
<span data-ttu-id="cb85b-137">在這個範例中，SPF 規則會指示接收的電子郵件伺服器，以便只接受來自網域 contoso.com 這些 IP 位址的郵件：</span><span class="sxs-lookup"><span data-stu-id="cb85b-137">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>
  
- <span data-ttu-id="cb85b-138">#1 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cb85b-138">IP address #1</span></span>
    
- <span data-ttu-id="cb85b-139">IP 位址為 #2</span><span class="sxs-lookup"><span data-stu-id="cb85b-139">IP address #2</span></span>
    
- <span data-ttu-id="cb85b-140">#3 的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cb85b-140">IP address #3</span></span>
    
<span data-ttu-id="cb85b-141">此 SPF 規則會告訴接收的電子郵件伺服器，如果郵件是從 contoso.com，但不是能從下列其中一個下列三個 IP 位址，接收伺服器應該將強制執行規則套用至郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-141">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message.</span></span> <span data-ttu-id="cb85b-142">強制執行規則通常是其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="cb85b-142">The enforcement rule is usually one of these options:</span></span>
  
- <span data-ttu-id="cb85b-143">**完全未通過。**</span><span class="sxs-lookup"><span data-stu-id="cb85b-143">**Hard fail.**</span></span> <span data-ttu-id="cb85b-144">在郵件信封中標示 '完全未通過' 的郵件，然後依照 [接收伺服器的設定垃圾郵件原則，這種類型的郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-144">Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span> 
    
- <span data-ttu-id="cb85b-145">**Fail。**</span><span class="sxs-lookup"><span data-stu-id="cb85b-145">**Soft fail.**</span></span> <span data-ttu-id="cb85b-146">標記 'fail' 郵件信封中的郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-146">Mark the message with 'soft fail' in the message envelope.</span></span> <span data-ttu-id="cb85b-147">一般而言，電子郵件伺服器設定為仍將這些郵件傳遞。</span><span class="sxs-lookup"><span data-stu-id="cb85b-147">Typically, email servers are configured to deliver these messages anyway.</span></span> <span data-ttu-id="cb85b-148">大部分使用者看不到此標記。</span><span class="sxs-lookup"><span data-stu-id="cb85b-148">Most end users do not see this mark.</span></span> 
    
- <span data-ttu-id="cb85b-149">**中性。**</span><span class="sxs-lookup"><span data-stu-id="cb85b-149">**Neutral.**</span></span> <span data-ttu-id="cb85b-150">不執行任何動作，也就是，不要將標示郵件信封。</span><span class="sxs-lookup"><span data-stu-id="cb85b-150">Do nothing, that is, do not mark the message envelope.</span></span> <span data-ttu-id="cb85b-151">這通常是僅供測試之用，而且不常使用。</span><span class="sxs-lookup"><span data-stu-id="cb85b-151">This is usually reserved for testing purposes and is rarely used.</span></span> 
    
<span data-ttu-id="cb85b-152">下列範例會顯示在不同情況下 SPF 的運作方式。</span><span class="sxs-lookup"><span data-stu-id="cb85b-152">The following examples show how SPF works in different situations.</span></span> <span data-ttu-id="cb85b-153">在下列範例中，contoso.com 是寄件者，且 woodgrovebank.com 接收者。</span><span class="sxs-lookup"><span data-stu-id="cb85b-153">In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>
  
### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="cb85b-154">範例 1： 電子郵件驗證的直接從寄件者傳送給收件者的郵件</span><span class="sxs-lookup"><span data-stu-id="cb85b-154">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="cb85b-155"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-155"></span></span>

<span data-ttu-id="cb85b-156">SPF 適合時接收來自寄件者的路徑是直接，例如：</span><span class="sxs-lookup"><span data-stu-id="cb85b-156">SPF works best when the path from sender to receiver is direct, for example:</span></span>
  
![流程圖顯示 SPF 如何驗證直接從伺服器傳送至伺服器的電子郵件。](../media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)
  
<span data-ttu-id="cb85b-158">當 woodgrovebank.com 接收郵件，如果 #1 的 IP 位址位於 contoso.com 的 SPF TXT 記錄時，郵件通過 SPF 檢查，並通過驗證。</span><span class="sxs-lookup"><span data-stu-id="cb85b-158">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>
  
### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="cb85b-159">範例 2： 詐騙的寄件者地址 SPF 檢查失敗</span><span class="sxs-lookup"><span data-stu-id="cb85b-159">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="cb85b-160"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-160"></span></span>

<span data-ttu-id="cb85b-161">假設 phisher 找到詐騙 contoso.com 的方式：</span><span class="sxs-lookup"><span data-stu-id="cb85b-161">Suppose a phisher finds a way to spoof contoso.com:</span></span>
  
![流程圖顯示 SPF 如何驗證從詐騙的伺服器所傳送之電子郵件。](../media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)
  
<span data-ttu-id="cb85b-163">因為 IP 位址 #12 不是在 contoso.com 的 SPF TXT 記錄，SPF 檢查失敗郵件和收件者可以選擇將標示為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-163">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>
  
### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="cb85b-164">範例 3: SPF 和轉寄的郵件</span><span class="sxs-lookup"><span data-stu-id="cb85b-164">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="cb85b-165"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-165"></span></span>

<span data-ttu-id="cb85b-166">SPF 有一項缺點是，它不會運作時已轉寄電子郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-166">One drawback of SPF is that it doesn't work when an email has been forwarded.</span></span> <span data-ttu-id="cb85b-167">例如，假設 woodgrovebank.com 中的使用者已將設有轉寄規則設定為將所有電子郵件傳送至 outlook.com 帳戶：</span><span class="sxs-lookup"><span data-stu-id="cb85b-167">For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>
  
![流程圖顯示 SPF 在訊息被轉送時無法驗證電子郵件。](../media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)
  
<span data-ttu-id="cb85b-169">原本在 woodgrovebank.com 傳遞 SPF 檢查的郵件，但它就會失敗 SPF 檢查於 outlook.com，因為 IP #25 不在 contoso.com 的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-169">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record.</span></span> <span data-ttu-id="cb85b-170">Outlook.com 可能再將該郵件標記為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-170">Outlook.com might then mark the message as spam.</span></span> <span data-ttu-id="cb85b-171">若要解決此問題，SPF 搭配使用與其他電子郵件驗證方法，例如 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="cb85b-171">To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>
  
### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="cb85b-172">SPF 基本概念： 包括可以代表您的網域傳送郵件的協力廠商網域</span><span class="sxs-lookup"><span data-stu-id="cb85b-172">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="cb85b-173"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-173"></span></span>

<span data-ttu-id="cb85b-174">除了 IP 位址，您也可以設定您的 SPF TXT 記錄，以包含為寄件者的網域。</span><span class="sxs-lookup"><span data-stu-id="cb85b-174">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders.</span></span> <span data-ttu-id="cb85b-175">這些被新增至的 SPF TXT 記錄做為 「 包含 」 陳述式。</span><span class="sxs-lookup"><span data-stu-id="cb85b-175">These are added to the SPF TXT record as "include" statements.</span></span> <span data-ttu-id="cb85b-176">例如，contoso.com 可能會想要包含所有來自 contoso.net 和 contoso.org 這也擁有的郵件伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb85b-176">For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns.</span></span> <span data-ttu-id="cb85b-177">若要這麼做，contoso.com 會發佈的 SPF TXT 記錄看起來如下：</span><span class="sxs-lookup"><span data-stu-id="cb85b-177">To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>
  
```
IN TXT "v=spf1 include:contoso.net include:contoso.org -all"
```

<span data-ttu-id="cb85b-178">時接收伺服器會看到此記錄在 DNS 中，它也會執行 DNS 查閱 contoso.net 然後 contoso.org 的 SPF TXT 記錄上。如果找到其他包含陳述式內 contoso.net 或 contoso.org 的記錄，它會太遵循這些。</span><span class="sxs-lookup"><span data-stu-id="cb85b-178">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="cb85b-179">以協助防止阻斷服務攻擊，DNS 查閱且單一電子郵件的最大數目為 10。</span><span class="sxs-lookup"><span data-stu-id="cb85b-179">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="cb85b-180">每個包含陳述式代表其他 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="cb85b-180">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="cb85b-181">如果郵件超過 10 個限制，郵件就會失敗 SPF。</span><span class="sxs-lookup"><span data-stu-id="cb85b-181">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="cb85b-182">一旦郵件達到此限制，接收伺服器的設定，根據寄件者可能會收到訊息，指出郵件產生 「 太多查閱 」 或 「 已超出最大躍點訊息 」 (其中情形時查閱循環及超越 DNS 逾時）。</span><span class="sxs-lookup"><span data-stu-id="cb85b-182">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="cb85b-183">如何避免此問題的秘訣，請參閱[疑難排解： Office 365 中 SPF 的最佳作法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-183">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>
  
## <a name="requirements-for-your-spf-txt-record-and-office-365"></a><span data-ttu-id="cb85b-184">您的 SPF TXT 記錄與 Office 365 的需求</span><span class="sxs-lookup"><span data-stu-id="cb85b-184">Requirements for your SPF TXT record and Office 365</span></span>
<span data-ttu-id="cb85b-185"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-185"></span></span>

<span data-ttu-id="cb85b-186">如果您會設定信箱，當您設定 Office 365，您已經建立做為合法您網域的郵件來源識別 Microsoft 郵件伺服器的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-186">If you set up mail when you set up Office 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain.</span></span> <span data-ttu-id="cb85b-187">此記錄可能看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="cb85b-187">This record probably looks like this:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="cb85b-188">如果您是完全託管 Office 365 客戶，也就是您沒有傳送輸出郵件的內部部署郵件伺服器，這是唯一的 SPF TXT 記錄，您需要發佈的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cb85b-188">If you're a fully-hosted Office 365 customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>
  
<span data-ttu-id="cb85b-189">如果您有混合式部署 （亦即，您有一些信箱在內部和部分裝載於 Office 365），或如果您是 Exchange Online Protection (EOP) 獨立版客戶 （也就是您的組織使用 EOP 來保護您在內部部署信箱），您應該將輸出的 IP 位址的每一部內部邊緣郵件伺服器新增至 DNS 中的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-189">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Office 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>
  
## <a name="form-your-spf-txt-record-for-office-365"></a><span data-ttu-id="cb85b-190">Office 365 形成 SPF TXT 記錄</span><span class="sxs-lookup"><span data-stu-id="cb85b-190">Form your SPF TXT record for Office 365</span></span>
<span data-ttu-id="cb85b-191"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-191"></span></span>

<span data-ttu-id="cb85b-192">使用本文中的語法資訊，以形成 SPF TXT 記錄的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="cb85b-192">Use the syntax information in this article to form the SPF TXT record for your custom domain.</span></span> <span data-ttu-id="cb85b-193">雖然還有其他此處未提及，這些都是最常用的語法選項使用選項。</span><span class="sxs-lookup"><span data-stu-id="cb85b-193">Although there are other syntax options that are not mentioned here, these are the most commonly used options.</span></span> <span data-ttu-id="cb85b-194">一旦您已形成記錄，您需要在網域註冊機構中更新記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-194">Once you have formed your record, you need to update the record at your domain registrar.</span></span>
  
<span data-ttu-id="cb85b-195">網域的相關的資訊您想要包含 for Office 365，請參閱[spf 所需的外部 DNS 記錄](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-195">For information about the domains you will need to include for Office 365, see [External DNS records required for SPF](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> <span data-ttu-id="cb85b-196">使用[逐步指示](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)更新您的網域註冊機構 SPF (TXT) 記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-196">Use the [step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records for your domain registrar.</span></span> <span data-ttu-id="cb85b-197">如果未列出您的註冊機構，您必須連絡這些分開，了解如何更新您的記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-197">If your registrar is not listed, you will need to contact them separately to learn how to update your record.</span></span> 
  
### <a name="spf-txt-record-syntax-for-office-365"></a><span data-ttu-id="cb85b-198">Office 365 的 SPF TXT 記錄語法</span><span class="sxs-lookup"><span data-stu-id="cb85b-198">SPF TXT record syntax for Office 365</span></span>
<span data-ttu-id="cb85b-199"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-199"></span></span>

<span data-ttu-id="cb85b-200">典型的 SPF TXT 記錄，Office 365 具有下列語法：</span><span class="sxs-lookup"><span data-stu-id="cb85b-200">A typical SPF TXT record for Office 365 has the following syntax:</span></span>
  
```
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="cb85b-201">例如：</span><span class="sxs-lookup"><span data-stu-id="cb85b-201">For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="cb85b-202">其中：</span><span class="sxs-lookup"><span data-stu-id="cb85b-202">where:</span></span>
  
- <span data-ttu-id="cb85b-203">**v = spf1**是必要。</span><span class="sxs-lookup"><span data-stu-id="cb85b-203">**v=spf1** is required.</span></span> <span data-ttu-id="cb85b-204">這會定義 TXT 記錄做為 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-204">This defines the TXT record as an SPF TXT record.</span></span> 
    
- <span data-ttu-id="cb85b-205">**ip4**指示您使用的 IP 版本 4 地址。</span><span class="sxs-lookup"><span data-stu-id="cb85b-205">**ip4** indicates that you are using IP version 4 addresses.</span></span> <span data-ttu-id="cb85b-206">**ip6**指示您使用的 IP 版本 6 位址。</span><span class="sxs-lookup"><span data-stu-id="cb85b-206">**ip6** indicates that you are using IP version 6 addresses.</span></span> <span data-ttu-id="cb85b-207">如果您使用 IPv6 位址，取代**ip4** **ip6**在本文中的範例。</span><span class="sxs-lookup"><span data-stu-id="cb85b-207">If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article.</span></span> <span data-ttu-id="cb85b-208">您也可以指定使用 CIDR 表示法，例如**ip4:192.168.0.1/26**的 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="cb85b-208">You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>
    
-  <span data-ttu-id="cb85b-209">_IP 位址_是您想要加入的 SPF TXT 記錄的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb85b-209">_IP address_ is the IP address that you want to add to the SPF TXT record.</span></span> <span data-ttu-id="cb85b-210">通常，這是您組織的外寄郵件伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="cb85b-210">Usually, this is the IP address of the outbound mail server for your organization.</span></span> <span data-ttu-id="cb85b-211">您可以列出多個輸出郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb85b-211">You can list multiple outbound mail servers.</span></span> <span data-ttu-id="cb85b-212">如需詳細資訊，請參閱[範例： SPF TXT 記錄以多個輸出內部部署信箱伺服器和 Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-212">For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>
    
-  <span data-ttu-id="cb85b-213">_網域名稱_是您想要新增為合法的寄件者的網域。</span><span class="sxs-lookup"><span data-stu-id="cb85b-213">_domain name_ is the domain you want to add as a legitimate sender.</span></span> <span data-ttu-id="cb85b-214">您應該包含 for Office 365 的網域名稱的清單，請參閱[spf 所需的外部 DNS 記錄](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-214">For a list of domain names you should include for Office 365, see [External DNS records required for SPF](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
    
- <span data-ttu-id="cb85b-215">強制執行規則通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cb85b-215">Enforcement rule is usually one of the following:</span></span>
    
  - <span data-ttu-id="cb85b-216">-all</span><span class="sxs-lookup"><span data-stu-id="cb85b-216">-all</span></span>
    
    <span data-ttu-id="cb85b-217">會指出完全未通過。</span><span class="sxs-lookup"><span data-stu-id="cb85b-217">Indicates hard fail.</span></span> <span data-ttu-id="cb85b-218">如果您知道所有授權的 IP 位址為您的網域，其清單中的 SPF TXT 記錄，並使用-all （完全未通過） 辨識符號。</span><span class="sxs-lookup"><span data-stu-id="cb85b-218">If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier.</span></span> <span data-ttu-id="cb85b-219">此外，如果您只使用 SPF，也就是您不使用 DMARC 或 DKIM，您應該使用-all 辨識符號。</span><span class="sxs-lookup"><span data-stu-id="cb85b-219">Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier.</span></span> <span data-ttu-id="cb85b-220">我們建議您一律使用此辨識符號。</span><span class="sxs-lookup"><span data-stu-id="cb85b-220">We recommend that you use always this qualifier.</span></span>
    
  - <span data-ttu-id="cb85b-221">~ 所有</span><span class="sxs-lookup"><span data-stu-id="cb85b-221">~all</span></span>
    
    <span data-ttu-id="cb85b-222">會指出 fail。</span><span class="sxs-lookup"><span data-stu-id="cb85b-222">Indicates soft fail.</span></span> <span data-ttu-id="cb85b-223">如果您不確定您有 IP 位址的完整清單，則應該使用 ~ 所有 (fail) 辨識符號。</span><span class="sxs-lookup"><span data-stu-id="cb85b-223">If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier.</span></span> <span data-ttu-id="cb85b-224">此外，如果您使用 DMARC p = 隔離或 p = 拒絕，則您可以使用 ~ 所有。</span><span class="sxs-lookup"><span data-stu-id="cb85b-224">Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all.</span></span> <span data-ttu-id="cb85b-225">否則，使用-all。</span><span class="sxs-lookup"><span data-stu-id="cb85b-225">Otherwise, use -all.</span></span>
    
  - <span data-ttu-id="cb85b-226">？ 所有</span><span class="sxs-lookup"><span data-stu-id="cb85b-226">?all</span></span>
    
    <span data-ttu-id="cb85b-227">會指出中性。</span><span class="sxs-lookup"><span data-stu-id="cb85b-227">Indicates neutral.</span></span> <span data-ttu-id="cb85b-228">測試 SPF 時，會使用這項目。</span><span class="sxs-lookup"><span data-stu-id="cb85b-228">This is used when testing SPF.</span></span> <span data-ttu-id="cb85b-229">我們不建議您實際部署中使用此辨識符號。</span><span class="sxs-lookup"><span data-stu-id="cb85b-229">We do not recommend that you use this qualifier in your live deployment.</span></span>
    
### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a><span data-ttu-id="cb85b-230">範例： SPF TXT 記錄時所要使用所有您的郵件會傳送由 Office 365</span><span class="sxs-lookup"><span data-stu-id="cb85b-230">Example: SPF TXT record to use when all of your mail is sent by Office 365</span></span>
<span data-ttu-id="cb85b-231"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-231"></span></span>

<span data-ttu-id="cb85b-232">如果您的郵件的所有傳送由 Office 365，請使用此 SPF TXT 記錄中：</span><span class="sxs-lookup"><span data-stu-id="cb85b-232">If all of your mail is sent by Office 365, use this in your SPF TXT record:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a><span data-ttu-id="cb85b-233">範例： SPF TXT 記錄以混合式案例中使用其中一個內部部署 Exchange Server 與 Office 365</span><span class="sxs-lookup"><span data-stu-id="cb85b-233">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Office 365</span></span>
<span data-ttu-id="cb85b-234"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-234"></span></span>

<span data-ttu-id="cb85b-235">在混合式環境中，如果您的內部部署 Exchange 伺服器的 IP 位址為 192.168.0.1，為了要設定以完全未通過 SPF 強制執行規則形成 SPF TXT 記錄，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cb85b-235">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>
  
```
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a><span data-ttu-id="cb85b-236">範例： SPF TXT 記錄以多個輸出內部部署郵件伺服器和 Office 365</span><span class="sxs-lookup"><span data-stu-id="cb85b-236">Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365</span></span>
<span data-ttu-id="cb85b-237"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-237"></span></span>

<span data-ttu-id="cb85b-238">如果您有多個輸出郵件伺服器，SPF TXT 記錄中包含的每部郵件伺服器的 IP 位址，並以後面加上空格分隔每個 IP 位址 」 ip4: 「 陳述式。</span><span class="sxs-lookup"><span data-stu-id="cb85b-238">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement.</span></span> <span data-ttu-id="cb85b-239">例如：</span><span class="sxs-lookup"><span data-stu-id="cb85b-239">For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a><span data-ttu-id="cb85b-240">後續步驟： 為 Office 365 設定 SPF</span><span class="sxs-lookup"><span data-stu-id="cb85b-240">Next steps: Set up SPF for Office 365</span></span>
<span data-ttu-id="cb85b-241"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-241"></span></span>

<span data-ttu-id="cb85b-242">一旦您已成形 SPF TXT 記錄，請遵循中將它新增至您的網域[設定 spf 以協助防止詐騙的 Office 365 中](set-up-spf-in-office-365-to-help-prevent-spoofing.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="cb85b-242">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span> 
  
<span data-ttu-id="cb85b-243">雖然 SPF 設計來協助防止詐騙，但是有的詐騙技術該 SPF 無法防護。</span><span class="sxs-lookup"><span data-stu-id="cb85b-243">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="cb85b-244">為了防止這些項目，設定 SPF 之後，您也應該為 Office 365 設定 DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="cb85b-244">In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365.</span></span> <span data-ttu-id="cb85b-245">若要開始使用，請參閱 [使用 DKIM 驗證從您在 Office 365 中的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-245">To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span> <span data-ttu-id="cb85b-246">接下來，請參閱[使用 DMARC 來驗證 Office 365 電子郵件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-246">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
  
## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a><span data-ttu-id="cb85b-247">疑難排解： 的 SPF Office 365 中的最佳作法</span><span class="sxs-lookup"><span data-stu-id="cb85b-247">Troubleshooting: Best practices for SPF in Office 365</span></span>
<span data-ttu-id="cb85b-248"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-248"></span></span>

<span data-ttu-id="cb85b-249">您只可以建立一個 SPF TXT 記錄的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="cb85b-249">You can only create one SPF TXT record for your custom domain.</span></span> <span data-ttu-id="cb85b-250">建立多筆記錄會導致循環配置資源這種狀況，而且 SPF 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="cb85b-250">Creating multiple records causes a round robin situation and SPF will fail.</span></span> <span data-ttu-id="cb85b-251">若要避免此問題，您可以建立每個子網域的個別的記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-251">To avoid this, you can create separate records for each subdomain.</span></span> <span data-ttu-id="cb85b-252">例如，建立一筆記錄，contoso.com 和 bulkmail.contoso.com 的另一筆記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-252">For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>
  
<span data-ttu-id="cb85b-253">如果電子郵件訊息會造成超過 10 個 DNS 查閱且該郵件會傳遞之前，將永久性錯誤，也稱為_permerror_中，以回應接收的郵件伺服器，並造成失敗 SPF 檢查郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-253">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check.</span></span> <span data-ttu-id="cb85b-254">接收伺服器也可能會以未傳遞回報 (NDR)，其中包含類似以下的錯誤回應：</span><span class="sxs-lookup"><span data-stu-id="cb85b-254">The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>
  
- <span data-ttu-id="cb85b-255">郵件超過一個躍點計數。</span><span class="sxs-lookup"><span data-stu-id="cb85b-255">The message exceeded the hop count.</span></span>
    
- <span data-ttu-id="cb85b-256">訊息需要太多查閱。</span><span class="sxs-lookup"><span data-stu-id="cb85b-256">The message required too many lookups.</span></span>
    
## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a><span data-ttu-id="cb85b-257">當您使用協力廠商網域與 Office 365 時避免 「 太多查閱 」 錯誤</span><span class="sxs-lookup"><span data-stu-id="cb85b-257">Avoiding the "too many lookups" error when you use third-party domains with Office 365</span></span>
<span data-ttu-id="cb85b-258"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-258"></span></span>

<span data-ttu-id="cb85b-259">某些協力廠商網域的 SPF TXT 記錄會直接執行 DNS 查閱且大量接收伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb85b-259">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups.</span></span> <span data-ttu-id="cb85b-260">例如，在撰寫本文時，Salesforce.com 包含 5 包含陳述式，其記錄中：</span><span class="sxs-lookup"><span data-stu-id="cb85b-260">For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>
  
```
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="cb85b-261">若要避免此錯誤，您可以實作任何人傳送大量電子郵件，例如，具有特別針對此目的使用子網域的原則。</span><span class="sxs-lookup"><span data-stu-id="cb85b-261">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose.</span></span> <span data-ttu-id="cb85b-262">然後，您會定義包含大量電子郵件的子網域不同 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-262">You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>
  
 <span data-ttu-id="cb85b-263">在某些情況下，例如 salesforce.com 範例中，您必須使用的網域中您的 SPF TXT 記錄，但在其他情況下，協力廠商可能已經建立子網域進行您要用於此目的。</span><span class="sxs-lookup"><span data-stu-id="cb85b-263">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose.</span></span> <span data-ttu-id="cb85b-264">例如，exacttarget.com 建立子網域，您需要使用您的 SPF TXT 記錄：</span><span class="sxs-lookup"><span data-stu-id="cb85b-264">For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span> 
  
```
cust-spf.exacttarget.com
```

<span data-ttu-id="cb85b-265">當您在您的 SPF TXT 記錄中包含協力廠商網域時，您需要確認與協力廠商的網域或子網域若要使用，避免執行到 10 個查閱限制。</span><span class="sxs-lookup"><span data-stu-id="cb85b-265">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>
  
## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="cb85b-266">如何檢視目前 SPF TXT 記錄，並判斷其所需要的查閱數目</span><span class="sxs-lookup"><span data-stu-id="cb85b-266">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="cb85b-267"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-267"></span></span>

<span data-ttu-id="cb85b-268">您可以使用 nslookup 來檢視您的 DNS 記錄，包括您的 SPF TXT 記錄。</span><span class="sxs-lookup"><span data-stu-id="cb85b-268">You can use nslookup to view your DNS records, including your SPF TXT record.</span></span> <span data-ttu-id="cb85b-269">或者，如果您想要的話，有許多免費的線上工具提供可用來檢視您的 SPF TXT 記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="cb85b-269">Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record.</span></span> <span data-ttu-id="cb85b-270">透過查看您的 SPF TXT 記錄，並依照的鏈結包含陳述式及重新導向，您可以決定記錄需要多少 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="cb85b-270">By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires.</span></span> <span data-ttu-id="cb85b-271">某些線上工具將偶數計數，並為您顯示這些查閱。</span><span class="sxs-lookup"><span data-stu-id="cb85b-271">Some online tools will even count and display these lookups for you.</span></span> <span data-ttu-id="cb85b-272">追蹤的此數字，將有助於避免從觸發永久性錯誤，稱為 permerror，接收伺服器從組織傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="cb85b-272">Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="cb85b-273">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="cb85b-273">For more information</span></span>
<span data-ttu-id="cb85b-274"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="cb85b-274"></span></span>

<span data-ttu-id="cb85b-275">需要協助新增 SPF TXT 記錄嗎？</span><span class="sxs-lookup"><span data-stu-id="cb85b-275">Need help adding the SPF TXT record?</span></span> <span data-ttu-id="cb85b-276">使用的更新在各種不同的受歡迎的網域註冊機構的 SPF (TXT) 記錄的[逐步指示](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)。</span><span class="sxs-lookup"><span data-stu-id="cb85b-276">[Step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records at a variety of popular domain registrars is available.</span></span> <span data-ttu-id="cb85b-277">[反垃圾郵件郵件標頭](anti-spam-message-headers.md)包含針對 SPF 檢查 Office 365 所使用的語法及標頭欄位。</span><span class="sxs-lookup"><span data-stu-id="cb85b-277">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for SPF checks.</span></span> 
  

