---
title: 反詐騙保護常見問題集
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以在 Exchange Online Protection (EOP) 中，查看有關反欺騙保護的常見問題及解答。
ms.openlocfilehash: f567c7bc0c6a6efed7621cec86c5db4e616290b7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616728"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="82d67-103">反詐騙保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="82d67-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="82d67-104">本文針對 Exchange Online 中的信箱，或獨立 Exchange Online Protection (EOP) 組織中的 Microsoft 365 組織，提供有關反欺騙保護的常見問題和解答，但沒有 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="82d67-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="82d67-105">如需反垃圾郵件保護的相關問題和解答，請參閱 [反垃圾郵件保護常見問題](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="82d67-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="82d67-106">如需有關反惡意程式碼保護的問題和解答，請參閱 [反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="82d67-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="82d67-107">Microsoft 為何選擇未驗證的垃圾輸入電子郵件？</span><span class="sxs-lookup"><span data-stu-id="82d67-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="82d67-108">Microsoft 相信，繼續允許未驗證的輸入電子郵件的風險，會高於遺失合法輸入電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="82d67-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="82d67-109">Junking 未驗證的輸入電子郵件是否導致合法的電子郵件標示為垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="82d67-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="82d67-110">當 Microsoft 在2018中啟用這項功能時，會發生一些誤報 (良好的郵件會標示為壞) 。</span><span class="sxs-lookup"><span data-stu-id="82d67-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="82d67-111">不過，隨著時間的變化，寄件者會調整為要求。</span><span class="sxs-lookup"><span data-stu-id="82d67-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="82d67-112">對於大部分的電子郵件路徑，已 misidentified 為欺騙的郵件數目會變得忽略。</span><span class="sxs-lookup"><span data-stu-id="82d67-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="82d67-113">Microsoft 本身會在將新的電子郵件驗證需求部署給客戶之前，先採用一周。</span><span class="sxs-lookup"><span data-stu-id="82d67-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="82d67-114">一開始會出現一些干擾，但慢慢的會減少。</span><span class="sxs-lookup"><span data-stu-id="82d67-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="82d67-115">是否有欺騙性智慧可用於不含 Defender for Office 365 的 Microsoft 365 客戶？</span><span class="sxs-lookup"><span data-stu-id="82d67-115">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="82d67-116">是。</span><span class="sxs-lookup"><span data-stu-id="82d67-116">Yes.</span></span> <span data-ttu-id="82d67-117">從10月2018到10月為止，具有 Exchange Online 信箱的所有組織，以及沒有 Exchange Online 信箱的獨立 EOP 組織皆可取得欺騙智慧。</span><span class="sxs-lookup"><span data-stu-id="82d67-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="82d67-118">如何向 Microsoft 回報垃圾郵件或非垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="82d67-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="82d67-119">請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="82d67-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="82d67-120">我是系統管理員，但我不知道我的電子郵件網域中的所有郵件來源！</span><span class="sxs-lookup"><span data-stu-id="82d67-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="82d67-121">請參閱 [您不知道電子郵件的所有來源](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。</span><span class="sxs-lookup"><span data-stu-id="82d67-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="82d67-122">如果我停用組織的反欺騙保護，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="82d67-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="82d67-123">我們不建議停用反欺詐防護。</span><span class="sxs-lookup"><span data-stu-id="82d67-123">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="82d67-124">停用保護將允許在您的組織中傳遞更多網路釣魚和垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="82d67-124">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="82d67-125">並非所有網路釣魚皆為欺騙性，而且不會丟失所有的冒牌郵件。</span><span class="sxs-lookup"><span data-stu-id="82d67-125">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="82d67-126">不過，您的風險會更高。</span><span class="sxs-lookup"><span data-stu-id="82d67-126">However, your risk will be higher.</span></span>

<span data-ttu-id="82d67-127">現在可以使用 [增強型連接器篩選](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ，當您的電子郵件透過另一個服務進行 EOP 之前，我們不再建議您關閉反欺騙保護。</span><span class="sxs-lookup"><span data-stu-id="82d67-127">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="82d67-128">反欺騙保護的意思是我會保護所有網路釣魚嗎？</span><span class="sxs-lookup"><span data-stu-id="82d67-128">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="82d67-129">不幸的是，不。</span><span class="sxs-lookup"><span data-stu-id="82d67-129">Unfortunately, no.</span></span> <span data-ttu-id="82d67-130">攻擊者會使用其他技術 (例如，在免費的電子郵件服務) 中已遭破壞的帳戶或帳戶。</span><span class="sxs-lookup"><span data-stu-id="82d67-130">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="82d67-131">不過，反網路釣魚保護的運作速度很好于偵測其他類型的網路釣魚方法。</span><span class="sxs-lookup"><span data-stu-id="82d67-131">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="82d67-132">EOP 中的保護層是設計一起運作，彼此上建立。</span><span class="sxs-lookup"><span data-stu-id="82d67-132">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="82d67-133">其他大型電子郵件服務會封鎖未驗證的輸入電子郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="82d67-133">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="82d67-134">幾乎所有大型的電子郵件服務都會執行傳統的 SPF、DKIM 及 DMARC 檢查。</span><span class="sxs-lookup"><span data-stu-id="82d67-134">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="82d67-135">有些服務有其他更為嚴格的檢查，但不是 EOP 來封鎖未驗證的電子郵件，並將其視為欺騙性的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="82d67-135">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="82d67-136">不過，該行業正深入瞭解未驗證電子郵件的問題，尤其是由於網路釣魚問題所導致。</span><span class="sxs-lookup"><span data-stu-id="82d67-136">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="82d67-137">我還是需要啟用高級垃圾郵件篩選器設定 "SPF record： hard fail" (_MarkAsSpamSpfRecordHardFail_) 如果我啟用反欺騙功能？</span><span class="sxs-lookup"><span data-stu-id="82d67-137">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="82d67-138">否。</span><span class="sxs-lookup"><span data-stu-id="82d67-138">No.</span></span> <span data-ttu-id="82d67-139">不再需要這種 ASF 設定。</span><span class="sxs-lookup"><span data-stu-id="82d67-139">This ASF setting is no longer required.</span></span> <span data-ttu-id="82d67-140">反欺騙保護會考慮這兩種 SPF 硬性失敗及一組更豐富的準則。</span><span class="sxs-lookup"><span data-stu-id="82d67-140">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="82d67-141">如果您已啟用反詐騙功能，並且開啟 **SPF 記錄：驗證失敗** (_MarkAsSpamSpfRecordHardFail_)，則可能會發生更多誤判。</span><span class="sxs-lookup"><span data-stu-id="82d67-141">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="82d67-142">我們建議您停用此功能，因為它幾乎不會提供偵測垃圾郵件或網路釣魚郵件的額外權益，而會產生大部分的誤報。</span><span class="sxs-lookup"><span data-stu-id="82d67-142">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="82d67-143">如需詳細資訊，請參閱 [EOP 中的高級垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="82d67-143">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="82d67-144">寄件者重新寫入架構是否有助於修正轉寄的電子郵件？</span><span class="sxs-lookup"><span data-stu-id="82d67-144">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="82d67-145">SRS 僅能修正轉寄電子郵件的部分問題。</span><span class="sxs-lookup"><span data-stu-id="82d67-145">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="82d67-146">透過重新寫入 SMTP **郵件**，SRS 可確保轉寄的郵件透過下一個目的地的 SPF。</span><span class="sxs-lookup"><span data-stu-id="82d67-146">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="82d67-147">不過，由於反欺騙是以 [寄件者 **] 或 [** DKIM-簽署] (網域中所結合的 [**發件** 人] 和 [] 或 [] （其他）) 的方式來進行反欺騙，所以無法防止 SRS 轉寄的電子郵件被標示為欺騙</span><span class="sxs-lookup"><span data-stu-id="82d67-147">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
