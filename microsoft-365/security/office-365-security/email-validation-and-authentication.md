---
title: Microsoft 365 中的電子郵件驗證
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 系統管理員現在可以了解 EOP 如何使用電子郵件驗證 (SPF、DKIM 和 DMARC) 來協助防止詐騙、網路釣魚和垃圾郵件。
ms.openlocfilehash: 7c196b68d88187da2890cc886f646c5416ef9a11
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131070"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="6a269-103">EOP 中的電子郵件驗證</span><span class="sxs-lookup"><span data-stu-id="6a269-103">Email authentication in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6a269-104">電子郵件驗證 (又稱為電子郵件驗證) 是一組嘗試停止詐騙 (來自偽造寄件者的電子郵件訊息) 的標準。</span><span class="sxs-lookup"><span data-stu-id="6a269-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="6a269-105">在所有 Microsoft 365 組織中，EOP 會使用這些標準來驗證輸入電子郵件：</span><span class="sxs-lookup"><span data-stu-id="6a269-105">In all Microsoft 365 organizations, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="6a269-106">SPF</span><span class="sxs-lookup"><span data-stu-id="6a269-106">SPF</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [<span data-ttu-id="6a269-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="6a269-107">DKIM</span></span>](use-dkim-to-validate-outbound-email.md)

- [<span data-ttu-id="6a269-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="6a269-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="6a269-109">電子郵件驗證會驗證來自寄件者 (例如，laura@contoso.com) 的電子郵件訊息是否合法，以及是否來自該電子郵件網域的預期來源 (例如，contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="6a269-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="6a269-110">本文章的其餘部分說明這些技術的運作方式，以及 EOP 如何使用它們來檢查輸入電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6a269-110">The rest of this article explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="6a269-111">使用電子郵件驗證以協助避免詐騙</span><span class="sxs-lookup"><span data-stu-id="6a269-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="6a269-112">DMARC 會透過檢查郵件中的 **寄件者** 位址來防止詐騙。</span><span class="sxs-lookup"><span data-stu-id="6a269-112">DMARC prevents spoofing by examining the **From** address in messages.</span></span> <span data-ttu-id="6a269-113">**寄件者** 位址是使用者在其電子郵件用戶端中看到的寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6a269-113">The **From** address is the sender's email address that users see in their email client.</span></span> <span data-ttu-id="6a269-114">目的地電子郵件組織也可以驗證電子郵件網域是否已通過 SPF 或 DKIM。</span><span class="sxs-lookup"><span data-stu-id="6a269-114">Destination email organizations can also verify that the email domain has passed SPF or DKIM.</span></span> <span data-ttu-id="6a269-115">換句話說，網域已經過驗證，因此寄件者的電子郵件地址不會詐騙。</span><span class="sxs-lookup"><span data-stu-id="6a269-115">In other words, the domain has been authenticated and therefore the sender's email address is not spoofed.</span></span>

<span data-ttu-id="6a269-116">不過，SPF、DKIM 和 DMARC 的 DNS 記錄 (統稱為電子郵件驗證原則) 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="6a269-116">However, DNS records for SPF, DKIM, and DMARC (collectively known as email authentication policies) are optional.</span></span> <span data-ttu-id="6a269-117">具有強式電子郵件驗證原則 (例如 microsoft.com 和 skype.com) 的網域會受到保護，避免遭受詐騙。</span><span class="sxs-lookup"><span data-stu-id="6a269-117">Domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing.</span></span> <span data-ttu-id="6a269-118">但是具有較弱式電子郵件驗證原則或完全沒有原則的網域，會是詐騙的主要目標。</span><span class="sxs-lookup"><span data-stu-id="6a269-118">But domains with weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="6a269-119">截至 2018 年 3 月，Fortune 500 中只有 9% 的公司網域已發佈強式電子郵件驗證原則。</span><span class="sxs-lookup"><span data-stu-id="6a269-119">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="6a269-120">攻擊者可能會對其餘 91% 的公司進行詐騙。</span><span class="sxs-lookup"><span data-stu-id="6a269-120">The remaining 91% of companies might be spoofed by an attacker.</span></span> <span data-ttu-id="6a269-121">除非有其他的電子郵件篩選機制，否則來自這些網域中偽造寄件者的電子郵件可能會傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="6a269-121">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![財富雜誌前 500 大公司採用的 DMARC 原則](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="6a269-123">發佈強式電子郵件驗證原則的中小型公司的比例較小。</span><span class="sxs-lookup"><span data-stu-id="6a269-123">The proportion of small-to-medium sized companies that publish strong email authentication policies is smaller.</span></span> <span data-ttu-id="6a269-124">而且在北美洲和歐洲西部以外的電子郵件網域，此數字甚至會更小。</span><span class="sxs-lookup"><span data-stu-id="6a269-124">And the number is even smaller for email domains outside North America and western Europe.</span></span>

<span data-ttu-id="6a269-125">缺乏強式電子郵件驗證原則是個大問題。</span><span class="sxs-lookup"><span data-stu-id="6a269-125">Lack of strong email authentication policies is a large problem.</span></span> <span data-ttu-id="6a269-126">組織可能不了解電子郵件驗證的運作方式，但攻擊者能夠完全了解並加以利用。</span><span class="sxs-lookup"><span data-stu-id="6a269-126">W while organizations might not understand how email authentication works, attackers fully understand, and they take advantage.</span></span> <span data-ttu-id="6a269-127">因為網路釣魚疑慮，以及強式電子郵件驗證原則的採用率有限，Microsoft 使用 *隱含電子郵件驗證* 來檢查輸入電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6a269-127">Because of phishing concerns and the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="6a269-128">隱含電子郵件驗證是一般電子郵件驗證原則的延伸模組。</span><span class="sxs-lookup"><span data-stu-id="6a269-128">Implicit email authentication is an extension of regular email authentication policies.</span></span> <span data-ttu-id="6a269-129">這些延伸模組包括：寄件者信譽、寄件者歷程記錄、收件者歷程記錄、行為分析，以及其他進階技術。</span><span class="sxs-lookup"><span data-stu-id="6a269-129">These extensions include: sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="6a269-130">如果沒有來自這些延伸模組的其他信號，從未使用電子郵件驗證原則的網域傳送的郵件將被標示為詐騙。</span><span class="sxs-lookup"><span data-stu-id="6a269-130">In the absence of other signals from these extensions, messages sent from domains that don't use email authentication policies will be marked as spoof.</span></span>

<span data-ttu-id="6a269-131">若要查看 Microsoft 的一般公告，請參閱[網路釣魚的範圍第 2 部分 - Microsoft 365 中增強的反詐騙保護](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209) (英文)。</span><span class="sxs-lookup"><span data-stu-id="6a269-131">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="6a269-132">複合驗證</span><span class="sxs-lookup"><span data-stu-id="6a269-132">Composite authentication</span></span>

<span data-ttu-id="6a269-133">如果網域沒有傳統的 SPF、DKIM 和 DMARC 記錄，這些記錄檢查無法傳達足夠的驗證狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="6a269-133">If a domain doesn't have traditional SPF, DKIM, and DMARC records, those record checks don't communicate enough authentication status information.</span></span> <span data-ttu-id="6a269-134">因此，Microsoft 開發了用於隱含電子郵件驗證的演算法。</span><span class="sxs-lookup"><span data-stu-id="6a269-134">Therefore, Microsoft has developed an algorithm for implicit email authentication.</span></span> <span data-ttu-id="6a269-135">此演算法會將多個訊號組合成單一值，稱為 _複合驗證_，或簡稱為 `compauth`。</span><span class="sxs-lookup"><span data-stu-id="6a269-135">This algorithm combines multiple signals into a single value called _composite authentication_, or `compauth` for short.</span></span> <span data-ttu-id="6a269-136">系統會在郵件標頭的 **Authentication-Results** 標頭中，加上 `compauth` 值戳記。</span><span class="sxs-lookup"><span data-stu-id="6a269-136">The `compauth` value is stamped into the **Authentication-Results** header in the message headers.</span></span>

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

<span data-ttu-id="6a269-137">這些值會在 [Authentication-results 郵件標頭](anti-spam-message-headers.md#authentication-results-message-header)中說明。</span><span class="sxs-lookup"><span data-stu-id="6a269-137">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="6a269-138">系統管理員或甚至是使用者都能透過檢查郵件標題來決定 Microsoft 365 如何判斷寄件者是偽造的。</span><span class="sxs-lookup"><span data-stu-id="6a269-138">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="6a269-139">為什麼電子郵件驗證不一定能夠阻止詐騙</span><span class="sxs-lookup"><span data-stu-id="6a269-139">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="6a269-140">只依靠電子郵件驗證記錄來判斷內送郵件是否為詐騙，有下列限制：</span><span class="sxs-lookup"><span data-stu-id="6a269-140">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="6a269-141">寄件網域可能沒有所需的 DNS 記錄，或是記錄未正確設定。</span><span class="sxs-lookup"><span data-stu-id="6a269-141">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="6a269-142">來源網域具有正確設定的 DNS 記錄，但是該網域與 [寄件者] 地址中的網域不相符。</span><span class="sxs-lookup"><span data-stu-id="6a269-142">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="6a269-143">SPF 和 DKIM 不需要在 [寄件者] 地址中使用網域。</span><span class="sxs-lookup"><span data-stu-id="6a269-143">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="6a269-144">攻擊者或合法服務可以註冊網域、設定網域的 SPF 和 DKIM，以及在 [寄件者] 地址中使用完全不同的網域。</span><span class="sxs-lookup"><span data-stu-id="6a269-144">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, and use a completely different domain in the From address.</span></span> <span data-ttu-id="6a269-145">來自此網域中寄件者的郵件將會通過 SPF 和 DKIM。</span><span class="sxs-lookup"><span data-stu-id="6a269-145">Messages from senders in this domain will pass SPF and DKIM.</span></span>

<span data-ttu-id="6a269-146">複合驗證可以藉由讓無法通過電子郵件檢查的郵件通過，以解決這些限制。</span><span class="sxs-lookup"><span data-stu-id="6a269-146">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

<span data-ttu-id="6a269-147">為了簡單起見，以下範例著重於電子郵件驗證結果。</span><span class="sxs-lookup"><span data-stu-id="6a269-147">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="6a269-148">其他後端情報因素會將通過電子郵件驗證的郵件視為詐騙，或是將電子郵件驗證失敗的郵件視為合法。</span><span class="sxs-lookup"><span data-stu-id="6a269-148">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="6a269-149">例如，fabrikam.com 網域沒有 SPF、DKIM 或 DMARC 記錄。</span><span class="sxs-lookup"><span data-stu-id="6a269-149">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="6a269-150">來自 fabrikam.com 網域中寄件者的郵件無法通過複合驗證 (請記下 `compauth` 值和原因)：</span><span class="sxs-lookup"><span data-stu-id="6a269-150">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="6a269-151">如果 fabrikam.com 在沒有 DKIM 記錄的情況下設定 SPF，郵件就可以通過複合驗證。</span><span class="sxs-lookup"><span data-stu-id="6a269-151">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication.</span></span> <span data-ttu-id="6a269-152">通過 SPF 檢查的網域會與 [寄件者] 位址中的網域對應：</span><span class="sxs-lookup"><span data-stu-id="6a269-152">The domain that passed SPF checks is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="6a269-153">如果 fabrikam.com 在沒有 SPF 記錄的情況下設定 DKIM 記錄，該郵件就會通過複合驗證。</span><span class="sxs-lookup"><span data-stu-id="6a269-153">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication.</span></span> <span data-ttu-id="6a269-154">DKIM 簽章中的網域會與 [寄件者] 位址中的網域對應：</span><span class="sxs-lookup"><span data-stu-id="6a269-154">The domain in the DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="6a269-155">如果 SPF 或 DKIM 簽章中的網域與 [寄件者] 地址中的網域不相符，則該郵件無法通過複合驗證：</span><span class="sxs-lookup"><span data-stu-id="6a269-155">If the domain in SPF or the DKIM signature doesn't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="6a269-156">傳送未經驗證電子郵件的合法寄件者解決方案</span><span class="sxs-lookup"><span data-stu-id="6a269-156">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="6a269-157">Microsoft 365 會追蹤誰傳送未經驗證電子郵件到您的組織。</span><span class="sxs-lookup"><span data-stu-id="6a269-157">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="6a269-158">如果服務認為寄件者不合法，則會將來自此寄件者的郵件標示為複合驗證失敗。</span><span class="sxs-lookup"><span data-stu-id="6a269-158">If the service thinks the sender is not legitimate, it will mark messages from this sender as a composite authentication failure.</span></span> <span data-ttu-id="6a269-159">若要避免此決策，您可以使用本節中的建議。</span><span class="sxs-lookup"><span data-stu-id="6a269-159">To avoid this verdict, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="6a269-160">為您擁有的網域設定電子郵件驗證</span><span class="sxs-lookup"><span data-stu-id="6a269-160">Configure email authentication for domains you own</span></span>

<span data-ttu-id="6a269-161">您可以使用這個方法，在您擁有多個租用戶或與多個租用戶互動的案例中，解決組織內部詐騙和跨網域詐騙。</span><span class="sxs-lookup"><span data-stu-id="6a269-161">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="6a269-162">其也有助於解決跨網域詐騙，您在其中傳送郵件給 Microsoft 365 內的客戶，或其他提供者主控的第三方。</span><span class="sxs-lookup"><span data-stu-id="6a269-162">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="6a269-163">為您的網域[設定 SPF 記錄](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="6a269-163">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="6a269-164">為您的主要網域[設定 DKIM 記錄](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="6a269-164">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="6a269-165">[考量設定 DMARC 記錄](use-dmarc-to-validate-email.md)，讓網域能判斷誰是合法的寄件者。</span><span class="sxs-lookup"><span data-stu-id="6a269-165">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="6a269-166">Microsoft 不會針對 SPF、DKIM 和 DMARC 記錄提供詳細實作指南。</span><span class="sxs-lookup"><span data-stu-id="6a269-166">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="6a269-167">但是，網路上有許多可用資訊。</span><span class="sxs-lookup"><span data-stu-id="6a269-167">However, there's many information available online.</span></span> <span data-ttu-id="6a269-168">也有第三方公司可專門協助您的組織設定電子郵件驗證記錄。</span><span class="sxs-lookup"><span data-stu-id="6a269-168">There are also third party companies dedicated to helping your organization setup email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="6a269-169">您不知道電子郵件的所有來源</span><span class="sxs-lookup"><span data-stu-id="6a269-169">You don't know all sources for your email</span></span>

<span data-ttu-id="6a269-170">許多網域並不會發佈 SPF 記錄，因為它們不知道在其網域中郵件的所有電子郵件來源。</span><span class="sxs-lookup"><span data-stu-id="6a269-170">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="6a269-171">首先，發佈內含您所知道所有電子郵件來源 (尤其是貴公司流量位於何處) 的 SPF 記錄，然後發佈中性 SPF 原則 `?all`。</span><span class="sxs-lookup"><span data-stu-id="6a269-171">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="6a269-172">例如：</span><span class="sxs-lookup"><span data-stu-id="6a269-172">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="6a269-173">此範例表示來自公司基礎結構的電子郵件將會通過電子郵件驗證，但是來自不明來源的電子郵件將會回歸中性。</span><span class="sxs-lookup"><span data-stu-id="6a269-173">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="6a269-174">Microsoft 365 會將來自您公司基礎結構的輸入電子郵件視為已驗證。</span><span class="sxs-lookup"><span data-stu-id="6a269-174">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated.</span></span> <span data-ttu-id="6a269-175">來自無法識別來源的電子郵件若隱含驗證失敗，仍可能會被標示為詐騙。</span><span class="sxs-lookup"><span data-stu-id="6a269-175">Email from unidentified sources might still be marked as spoof if it fails implicit authentication.</span></span> <span data-ttu-id="6a269-176">但是，比起所有電子郵件都被 Microsoft 365 標示為詐騙郵件，這不失為一項改進。</span><span class="sxs-lookup"><span data-stu-id="6a269-176">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="6a269-177">當您開始使用 SPF 後援原則 `?all` 之後，您就可以逐漸探索及包含更多郵件來源，然後使用更嚴格的原則更新您的 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="6a269-177">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="6a269-178">使用詐騙情報來設定允許傳送未經驗證電子郵件的寄件者</span><span class="sxs-lookup"><span data-stu-id="6a269-178">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="6a269-179">您也可以使用[詐騙情報](learn-about-spoof-intelligence.md)來允許寄件者將未經驗證的郵件傳送至您的組織。</span><span class="sxs-lookup"><span data-stu-id="6a269-179">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="6a269-180">對於外部網域，詐騙使用者是 [寄件者] 地址中的網域，而傳送基礎結構是來源 IP 位址 (分成 /24 個 CIDR 範圍)，或反向 DNS (PTR) 記錄的組織網域。</span><span class="sxs-lookup"><span data-stu-id="6a269-180">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="6a269-181">在下方的螢幕擷取畫面中，來源 IP 是 131.107.18.4，PTR 記錄是 outbound.mail.protection.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="6a269-181">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="6a269-182">這會針對傳送基礎結構顯示為 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="6a269-182">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="6a269-183">若要允許此寄件者傳送未經驗證的電子郵件，請將 [否] 變更為 [是]。</span><span class="sxs-lookup"><span data-stu-id="6a269-183">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![設定反詐騙允許的寄件者](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="6a269-185">為寄件者/收件者配對建立允許項目</span><span class="sxs-lookup"><span data-stu-id="6a269-185">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="6a269-186">若要略過垃圾郵件篩選、網路釣魚篩選的某些部分，但是不略過特定寄件者的惡意程式碼篩選，請參閱[在 Microsoft 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="6a269-186">To bypass spam filtering, some parts of filtering for phishing, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="6a269-187">要求寄件者為您未擁有的網域設定電子郵件驗證</span><span class="sxs-lookup"><span data-stu-id="6a269-187">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="6a269-188">有鑑於垃圾郵件和網路釣魚問題，Microsoft 建議針對所有電子郵件組織進行電子郵件驗證。</span><span class="sxs-lookup"><span data-stu-id="6a269-188">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="6a269-189">您可以要求傳送網域中的系統管理員設定其電子郵件驗證記錄，而不是在貴組織中設定手動覆寫。</span><span class="sxs-lookup"><span data-stu-id="6a269-189">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="6a269-190">即使他們過去不需要發佈電子郵件驗證記錄，如果他們傳送電子郵件至 Microsoft，就應該這麼做。</span><span class="sxs-lookup"><span data-stu-id="6a269-190">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="6a269-191">設定 SPF 來發佈網域的傳送 IP 位址，並設定 DKIM (若可用) 來數位簽署郵件。</span><span class="sxs-lookup"><span data-stu-id="6a269-191">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="6a269-192">他們應該考慮設定 DMARC 記錄。</span><span class="sxs-lookup"><span data-stu-id="6a269-192">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="6a269-193">如果他們使用大量寄件者代表他們傳送電子郵件，則要確認 [寄件者] 地址中的網域 (如果屬於他們) 與通過 SPF 或 DMARC 的網域相符。</span><span class="sxs-lookup"><span data-stu-id="6a269-193">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="6a269-194">確認下列位置 (如果他們使用這些位置) 包含在 SPF 記錄中：</span><span class="sxs-lookup"><span data-stu-id="6a269-194">Verify the following locations (if they use them) are included in the SPF record:</span></span>

  - <span data-ttu-id="6a269-195">內部部署電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="6a269-195">On-premises email servers.</span></span>
  - <span data-ttu-id="6a269-196">軟體即服務 (SaaS) 提供者傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6a269-196">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="6a269-197">從雲端主控服務 (Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services 等等) 傳送的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6a269-197">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="6a269-198">針對 ISP 主控的小型網域，根據 ISP 的指示來設定 SPF 記錄。</span><span class="sxs-lookup"><span data-stu-id="6a269-198">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="6a269-199">雖然一開始驗證傳送網域可能會有困難，但隨著時間過去，有越來越多的電子郵件篩選器開始篩選垃圾郵件或甚至拒絕他們的電子郵件，促使他們設定正確記錄以確保更佳的傳遞。</span><span class="sxs-lookup"><span data-stu-id="6a269-199">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="6a269-200">此外，他們的參與可協助抵禦網路釣魚，並能降低組織或電子郵件傳送目標組織中網路釣魚的可能性。</span><span class="sxs-lookup"><span data-stu-id="6a269-200">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="6a269-201">基礎結構提供者 (ISP、ESP 或雲端主控服務) 的資訊</span><span class="sxs-lookup"><span data-stu-id="6a269-201">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="6a269-202">如果您主控網域的電子郵件，或提供可傳送電子郵件的主控基礎結構，您應該執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6a269-202">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="6a269-203">請確認您的客戶擁有文件，其中說明客戶應如何設定其 SPF 記錄</span><span class="sxs-lookup"><span data-stu-id="6a269-203">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="6a269-204">即使客戶未明確設定 (使用預設網域登入)，仍考慮在外寄電子郵件中簽署 DKIM 簽章。</span><span class="sxs-lookup"><span data-stu-id="6a269-204">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="6a269-205">您甚至可以使用 DKIM 簽章對電子郵件進行雙重簽署 (如果已經設定了客戶的網域，則為第一次，第二次使用您公司的 DKIM簽章)</span><span class="sxs-lookup"><span data-stu-id="6a269-205">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="6a269-206">即使您對來自您的平台的電子郵件進行驗證，也無法保證Microsoft 的可傳遞性，但至少可保證 Microsoft 不會因為郵件未經過驗證，而將它列為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="6a269-206">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

## <a name="related-links"></a><span data-ttu-id="6a269-207">相關連結</span><span class="sxs-lookup"><span data-stu-id="6a269-207">Related links</span></span>

<span data-ttu-id="6a269-208">如需服務提供者最佳作法的詳細資訊，請參閱[適用服務提供者的 M3AAWG 行動訊息最佳做法](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf) (英文)。</span><span class="sxs-lookup"><span data-stu-id="6a269-208">For more information about service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span></span>

<span data-ttu-id="6a269-209">瞭解 Office 365 如何使用 SPF 並支援 DKIM 驗證：</span><span class="sxs-lookup"><span data-stu-id="6a269-209">Learn how Office 365 uses SPF and supports DKIM validation:</span></span>

- [<span data-ttu-id="6a269-210">深入瞭解 SPF</span><span class="sxs-lookup"><span data-stu-id="6a269-210">More about SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="6a269-211">深入了解 DKIM</span><span class="sxs-lookup"><span data-stu-id="6a269-211">More about DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)
