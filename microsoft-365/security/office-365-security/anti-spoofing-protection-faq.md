---
title: 反欺騙保護常見問題
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 在 Exchange Online 和獨立 Exchange Online Protection （EOP）中，系統管理員有關反欺騙保護的常見問題與解答。
ms.openlocfilehash: b39e48fd57b899e6296d40ab10aac265cb4165a3
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529842"
---
# <a name="anti-spoofing-protection-faq-in-office-365"></a><span data-ttu-id="160dd-103">Office 365 中的反欺騙保護常見問題</span><span class="sxs-lookup"><span data-stu-id="160dd-103">Anti-spoofing protection FAQ in Office 365</span></span>

<span data-ttu-id="160dd-104">本主題針對沒有 Exchange Online 信箱的 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶中的信箱，提供 Office 365 客戶的反欺騙保護的常見問題及解答。</span><span class="sxs-lookup"><span data-stu-id="160dd-104">This topic provides frequently asked questions and answers about anti-spoofing protection for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

<span data-ttu-id="160dd-105">如需反垃圾郵件保護的相關問題和解答，請參閱[反垃圾郵件保護常見問題](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="160dd-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="160dd-106">如需有關反惡意程式碼保護的問題和解答，請參閱[Office 365 中的反惡意程式碼保護常見問題](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="160dd-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ in Office 365](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="160dd-107">Microsoft 為何選擇未驗證的垃圾輸入電子郵件？</span><span class="sxs-lookup"><span data-stu-id="160dd-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="160dd-108">因為網路釣魚攻擊的影響，而且電子郵件驗證已超過15年，所以 Microsoft 相信繼續允許未驗證的輸入電子郵件的風險，會高於遺失合法輸入電子郵件的風險。</span><span class="sxs-lookup"><span data-stu-id="160dd-108">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="160dd-109">Junking 未驗證的輸入電子郵件是否導致合法的電子郵件標示為垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="160dd-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="160dd-110">當 Microsoft 在2018中啟用這項功能時，發生一些誤報（良好的郵件標示為壞）。</span><span class="sxs-lookup"><span data-stu-id="160dd-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="160dd-111">不過，隨著時間的變化，寄件者會調整為新的寄件者驗證需求，而 misidentified 為欺騙的郵件數目會變得可以忽略大多數的電子郵件路徑。</span><span class="sxs-lookup"><span data-stu-id="160dd-111">However, over time, senders adjusted to the new sender authentication requirements, and the number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="160dd-112">Microsoft 本身會在將新的電子郵件驗證需求部署給客戶之前，先採用一周。</span><span class="sxs-lookup"><span data-stu-id="160dd-112">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="160dd-113">一開始會出現一些干擾，但慢慢的會減少。</span><span class="sxs-lookup"><span data-stu-id="160dd-113">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-office-365-customers-without-atp"></a><span data-ttu-id="160dd-114">是否有欺騙性智慧可供沒有 ATP 的 Office 365 客戶使用？</span><span class="sxs-lookup"><span data-stu-id="160dd-114">Is spoof intelligence available to Office 365 customers without ATP?</span></span>

<span data-ttu-id="160dd-115">是。</span><span class="sxs-lookup"><span data-stu-id="160dd-115">Yes.</span></span> <span data-ttu-id="160dd-116">從10月2018到10月為止，所有包含 Exchange Online 信箱和獨立 EOP 組織的組織皆可使用欺騙智慧，而不需要 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="160dd-116">As of October 2018, spoof intelligence is available to all organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="160dd-117">反欺騙技術最初是部署到具有 Office 365 企業版 E5 訂閱的組織，或其訂閱的 Office 365 高級威脅防護（ATP）附加元件。</span><span class="sxs-lookup"><span data-stu-id="160dd-117">Anti-spoofing technology was initially deployed to organizations that had Office 365 Enterprise E5 subscriptions or the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="160dd-118">如何向 Microsoft 回報垃圾郵件或非垃圾郵件？</span><span class="sxs-lookup"><span data-stu-id="160dd-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="160dd-119">請參閱[回報訊息和檔案至 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="160dd-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="160dd-120">我是系統管理員，但我不知道我的電子郵件網域中的所有郵件來源！</span><span class="sxs-lookup"><span data-stu-id="160dd-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="160dd-121">請參閱[您不知道電子郵件的所有來源](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)。</span><span class="sxs-lookup"><span data-stu-id="160dd-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="160dd-122">如果我停用組織的反欺騙保護，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="160dd-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="160dd-123">我們不建議這樣做，因為您將會暴露在更多未篩選出的網路釣魚及垃圾郵件中。</span><span class="sxs-lookup"><span data-stu-id="160dd-123">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="160dd-124">並非所有的網路釣魚都是詐騙，也不是所有詐騙郵件都會遺漏。</span><span class="sxs-lookup"><span data-stu-id="160dd-124">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="160dd-125">不過，比起啟用反詐騙功能的客戶，您的風險較高。</span><span class="sxs-lookup"><span data-stu-id="160dd-125">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>

<span data-ttu-id="160dd-126">現在可以使用[增強型連接器篩選](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)功能，如果您的 MX 記錄指向另一部伺服器或服務，然後再將電子郵件傳遞至 EOP，我們就不再建議您關閉反欺騙保護。</span><span class="sxs-lookup"><span data-stu-id="160dd-126">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended that you turn off anti-spoofing protection if your MX record points to another server or service before delivering email to EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="160dd-127">反欺騙保護的意思是我會保護所有網路釣魚嗎？</span><span class="sxs-lookup"><span data-stu-id="160dd-127">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="160dd-128">不幸的是，不。</span><span class="sxs-lookup"><span data-stu-id="160dd-128">Unfortunately, no.</span></span> <span data-ttu-id="160dd-129">攻擊者可採用其他技術（例如，在免費電子郵件服務中已遭破壞的帳戶或帳戶）進行調整。</span><span class="sxs-lookup"><span data-stu-id="160dd-129">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="160dd-130">不過，反網路釣魚保護的運作速度很好于偵測其他類型的網路釣魚方法。</span><span class="sxs-lookup"><span data-stu-id="160dd-130">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="160dd-131">Office 365 中的保護層是設計一起運作，彼此上建立。</span><span class="sxs-lookup"><span data-stu-id="160dd-131">The protection layers in Office 365 are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="160dd-132">其他大型電子郵件服務會封鎖未驗證的輸入電子郵件嗎？</span><span class="sxs-lookup"><span data-stu-id="160dd-132">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="160dd-133">幾乎所有大型的電子郵件服務都會執行傳統的 SPF、DKIM 及 DMARC 檢查。</span><span class="sxs-lookup"><span data-stu-id="160dd-133">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="160dd-134">有些服務會有其他更為嚴格的檢查，但不像 Office 365 那樣可以封鎖未驗證的電子郵件，並將其視為欺騙性的郵件。</span><span class="sxs-lookup"><span data-stu-id="160dd-134">Some services have other, more strict checks, but few go as far as Office 365 to block unauthenticated email and treat them as as spoofed messages.</span></span> <span data-ttu-id="160dd-135">不過，該行業正深入瞭解未驗證電子郵件的問題，尤其是由於網路釣魚問題所導致。</span><span class="sxs-lookup"><span data-stu-id="160dd-135">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="160dd-136">如果我啟用反欺騙，仍然需要啟用高級垃圾郵件篩選器設定「SPF 記錄：硬失敗」（_MarkAsSpamSpfRecordHardFail_）？</span><span class="sxs-lookup"><span data-stu-id="160dd-136">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="160dd-137">否。</span><span class="sxs-lookup"><span data-stu-id="160dd-137">No.</span></span> <span data-ttu-id="160dd-138">這種 ASF 設定不再是必要的，因為反欺騙不僅會考慮 SPF hard 失敗，還會有更多更豐富的準則。</span><span class="sxs-lookup"><span data-stu-id="160dd-138">This ASF setting no longer required because anti-spoofing not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="160dd-139">如果您已啟用反詐騙功能，並且開啟 **SPF 記錄：驗證失敗** (_MarkAsSpamSpfRecordHardFail_)，則可能會發生更多誤判。</span><span class="sxs-lookup"><span data-stu-id="160dd-139">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="160dd-140">我們建議您停用此功能，因為它幾乎不會提供偵測垃圾郵件或網路釣魚郵件的額外權益，而會產生大部分的誤報。</span><span class="sxs-lookup"><span data-stu-id="160dd-140">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="160dd-141">如需詳細資訊，請參閱 [Office 365 中的進階垃圾郵件篩選 (ASF) 設定](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="160dd-141">For more information, see [Advanced Spam Filter (ASF) settings in Office 365](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="160dd-142">寄件者重新寫入架構是否有助於修正轉寄的電子郵件？</span><span class="sxs-lookup"><span data-stu-id="160dd-142">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="160dd-143">SRS 僅能修正轉寄電子郵件的部分問題。</span><span class="sxs-lookup"><span data-stu-id="160dd-143">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="160dd-144">透過重新寫入 SMTP**郵件**，SRS 可確保轉寄的郵件透過下一個目的地的 SPF。</span><span class="sxs-lookup"><span data-stu-id="160dd-144">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="160dd-145">不過，由於反欺騙是以「**寄件者」和「** DKIM-簽署」網域（或其他信號）結合的 [**發件**人] 位址而定，所以無法防止 SRS 轉寄的電子郵件被標示為欺騙。</span><span class="sxs-lookup"><span data-stu-id="160dd-145">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
