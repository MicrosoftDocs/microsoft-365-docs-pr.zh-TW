---
title: Microsoft Defender 的 Office 365 逐步威脅防護堆疊
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: 在 Microsoft Defender 的威脅篩選堆疊中，追蹤傳入郵件的路徑，以取得 Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e892ebe04887527cf57e4ea44f67c4aaa775b228
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683292"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b4107-103">適用於 Office 365 的 Microsoft Defender 中的逐步威脅防護</span><span class="sxs-lookup"><span data-stu-id="b4107-103">Step-by-step threat protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b4107-104">適用于 Office 365 保護或篩選堆疊的 Microsoft Defender 可分為四個階段，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="b4107-104">The Microsoft Defender for Office 365 protection or filtering stack can be broken out into 4 phases, as in this article.</span></span> <span data-ttu-id="b4107-105">一般說來，傳入郵件會在傳遞之前透過所有這些階段進行傳遞，但是實際的電子郵件會受到組織的 Office 365 設定的 Defender 的制約。</span><span class="sxs-lookup"><span data-stu-id="b4107-105">Generally speaking, incoming mail passes through all of these phases before delivery, but the actual path email takes is subject to an organization's Defender for Office 365 configuration.</span></span>

> [!TIP]
> <span data-ttu-id="b4107-106">請密切關注本文結尾的所有4個階段的 *整合* 圖形，以取得 Office 365 保護！</span><span class="sxs-lookup"><span data-stu-id="b4107-106">Stay tuned till the end of this article for a *unified* graphic of all 4 phases of Defender for Office 365 protection!</span></span>

## <a name="phase-1---edge-protection"></a><span data-ttu-id="b4107-107">階段 1-Edge Protection</span><span class="sxs-lookup"><span data-stu-id="b4107-107">Phase 1 - Edge Protection</span></span>

<span data-ttu-id="b4107-108">不幸的是，已過 *嚴重* 的 Edge 區塊現在相對簡單，無法克服不良的演員。</span><span class="sxs-lookup"><span data-stu-id="b4107-108">Unfortunately, Edge blocks that were once *critical* are now relatively simple for bad actors to overcome.</span></span> <span data-ttu-id="b4107-109">經過一段時間後，就不會在這裡封鎖流量，但它仍是堆疊的重要部分。</span><span class="sxs-lookup"><span data-stu-id="b4107-109">Over time, less traffic is blocked here, but it remains an important part of the stack.</span></span>  

<span data-ttu-id="b4107-110">Edge 區塊是設計為自動。</span><span class="sxs-lookup"><span data-stu-id="b4107-110">Edge blocks are designed to be automatic.</span></span> <span data-ttu-id="b4107-111">在誤報的情況下，寄件者會收到通知，並告知如何解決他們的問題。</span><span class="sxs-lookup"><span data-stu-id="b4107-111">In the case of false positive, senders will be notified and told how to address their issue.</span></span> <span data-ttu-id="b4107-112">來自具有有限信譽的信任合作夥伴的連接器，可確保在上架新端點時，deliverability 或暫時覆寫可就地保留。</span><span class="sxs-lookup"><span data-stu-id="b4107-112">Connectors from trusted partners with limited reputation can ensure deliverability, or temporary overrides can be put in place, when onboarding new endpoints.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Office 365 的 Defender 中篩選的階段1為 Edge Protection。":::

1. <span data-ttu-id="b4107-114">**網路節流** 會限制一組特定基礎結構可提交的郵件數目，以保護 Office 365 基礎結構和客戶免受拒絕服務 (DOS) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="b4107-114">**Network throttling** protects Office 365 infrastructure and customers from Denial of Service (DOS) attacks by limiting the number of messages that can be submitted by a specific set of infrastructure.</span></span>

2. <span data-ttu-id="b4107-115">**IP 信譽及節流** 會封鎖從已知的錯誤連接 IP 位址傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-115">**IP reputation and throttling** will block messages being sent from known bad connecting IP addresses.</span></span> <span data-ttu-id="b4107-116">如果特定 IP 會在短時間內傳送許多郵件，將會受到限制。</span><span class="sxs-lookup"><span data-stu-id="b4107-116">If a specific IP sends many messages in a short period of time they will be throttled.</span></span>

3. <span data-ttu-id="b4107-117">**網域信譽** 會封鎖所有從已知的錯誤網域傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-117">**Domain reputation** will block any messages being sent from a known bad domain.</span></span>

4. <span data-ttu-id="b4107-118">**目錄型 edge 篩選** 封鎖會嘗試透過 SMTP 來收集組織的目錄資訊。</span><span class="sxs-lookup"><span data-stu-id="b4107-118">**Directory-based edge filtering** blocks attempts to harvest an organization's directory information through SMTP.</span></span>

5. <span data-ttu-id="b4107-119">**退信攻擊偵測** 可防止 NDRs) 的無效未傳遞回報 (攻擊組織。</span><span class="sxs-lookup"><span data-stu-id="b4107-119">**Backscatter detection** prevents an organization from being attacked through invalid non-delivery reports (NDRs).</span></span>

6. <span data-ttu-id="b4107-120">**針對連接器的增強篩選功能** 會保留驗證資訊，即使流量透過另一個裝置進入 Office 365 為止也是一樣。</span><span class="sxs-lookup"><span data-stu-id="b4107-120">**Enhanced filtering for connectors** preserves authentication information even when traffic passes through another device before it reaches Office 365.</span></span> <span data-ttu-id="b4107-121">這可提升篩選堆疊的精確度，包括啟發式叢集、反欺騙和反網路釣魚機器教學模型，即使在複雜或混合式路由案例中也是一樣。</span><span class="sxs-lookup"><span data-stu-id="b4107-121">This improves filtering stack accuracy, including heuristic clustering, anti-spoofing, and anti-phishing machine learning models, even when in complex or hybrid routing scenarios.</span></span>

## <a name="phase-2---sender-intelligence"></a><span data-ttu-id="b4107-122">階段 2-寄件者情報</span><span class="sxs-lookup"><span data-stu-id="b4107-122">Phase 2 - Sender Intelligence</span></span>

<span data-ttu-id="b4107-123">寄件者智慧中的功能對於捕捉垃圾郵件、大量、模仿和未經授權的欺騙性郵件很重要，也會考慮網路釣魚偵測。</span><span class="sxs-lookup"><span data-stu-id="b4107-123">Features in sender intelligence are critical for catching spam, bulk, impersonation, and unauthorized spoof messages, and also factor into phish detection.</span></span> <span data-ttu-id="b4107-124">大多數的功能都是可個別設定的。</span><span class="sxs-lookup"><span data-stu-id="b4107-124">Most of these features are individually configurable.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="MDO 中篩選的階段2是寄件者智慧。":::

1. <span data-ttu-id="b4107-126">當帳戶具有反常行為時，會產生「**帳戶洩漏偵測**」和「警示」。</span><span class="sxs-lookup"><span data-stu-id="b4107-126">**Account compromise detection** triggers and alerts are raised when an account has anomalous behavior, consistent with compromise.</span></span> <span data-ttu-id="b4107-127">在某些情況下，使用者帳戶會遭到封鎖，並避免傳送任何後續的電子郵件訊息，直到組織的安全性運作小組解決問題為止。</span><span class="sxs-lookup"><span data-stu-id="b4107-127">In some cases, the user account is blocked and prevented from sending any further email messages until the issue is resolved by an organization's security operations team.</span></span>

2. <span data-ttu-id="b4107-128">**電子郵件驗證** 會包含客戶設定的方法和方法在雲端中設定的方法，其目的是為了確保寄件者獲得授權、可信的郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-128">**Email Authentication** involves both customer configured methods and methods set up in the Cloud, aimed at ensuring that senders are authorized, authentic mailers.</span></span> <span data-ttu-id="b4107-129">這些方法會抵禦哄騙。</span><span class="sxs-lookup"><span data-stu-id="b4107-129">These methods resist spoofing.</span></span>
    - <span data-ttu-id="b4107-130">**SPF** 可以根據 DNS TXT 記錄來拒絕郵件，這些記錄會列出可代表組織傳送郵件的 IP 位址和伺服器。</span><span class="sxs-lookup"><span data-stu-id="b4107-130">**SPF** can reject mails based on DNS TXT records that list IP addresses and servers allowed to send mail on the organization's behalf.</span></span>
    - <span data-ttu-id="b4107-131">**DKIM** 提供可驗證寄件者的加密簽名。</span><span class="sxs-lookup"><span data-stu-id="b4107-131">**DKIM** provides an encrypted signature that authenticates the sender.</span></span>
    - <span data-ttu-id="b4107-132">**DMARC** 可讓系統管理員在其網域中以必要的方式標示 SPF 和 DKIM，並強制執行這兩項技術的結果。</span><span class="sxs-lookup"><span data-stu-id="b4107-132">**DMARC** lets admins mark SPF and DKIM as required in their domain and enforces alignment between the results of these two technologies.</span></span>
    - <span data-ttu-id="b4107-133">**弧線** 不是由客戶設定，但是會在 DMARC 上建立，以在記錄驗證鏈時，與郵寄清單中的轉寄一起使用。</span><span class="sxs-lookup"><span data-stu-id="b4107-133">**ARC** is not customer configured, but builds on DMARC to work with forwarding in mailing lists, while recording an authentication chain.</span></span>

3. <span data-ttu-id="b4107-134">**欺騙性智慧** 可將允許其篩選為「哄騙」的 (，也就是代表另一個帳戶傳送郵件，或從模仿組織或已知外部網域的惡意寄件者) 郵寄清單的轉送。</span><span class="sxs-lookup"><span data-stu-id="b4107-134">**Spoof intelligence** is capable of filtering those allowed to 'spoof' (that is, those sending mail on behalf of another account, or forwarding for a mailing list) from malicious senders who imitate organizational or known external domains.</span></span> <span data-ttu-id="b4107-135">它會將合法的「代表」郵件分開，以欺騙傳送垃圾郵件和網路釣魚郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="b4107-135">It separates legitimate 'on behalf of' mail from senders who spoof to deliver spam and phishing messages.</span></span>

    <span data-ttu-id="b4107-136">組織內的 **欺騙智慧** 偵測並封鎖來自組織內網域的欺騙嘗試。</span><span class="sxs-lookup"><span data-stu-id="b4107-136">**Intra-org spoof intelligence** detects and blocks spoof attempts from a domain within the organization.</span></span>

4. <span data-ttu-id="b4107-137">**跨網域的欺騙智慧** 偵測並封鎖來自組織外部網域的欺騙嘗試。</span><span class="sxs-lookup"><span data-stu-id="b4107-137">**Cross-domain spoof intelligence** detects and blocks spoof attempts from a domain outside of the organization.</span></span>

5. <span data-ttu-id="b4107-138">**大量篩選** 可讓系統管理員設定大量信賴層級 (BCL) 指出郵件是否從大量寄件者傳送。</span><span class="sxs-lookup"><span data-stu-id="b4107-138">**Bulk filtering** lets admins configure a bulk confidence level (BCL) indicating whether the message was sent from a bulk sender.</span></span> <span data-ttu-id="b4107-139">系統管理員可以使用反垃圾郵件原則中的大量滑塊，決定將大宗郵件視為垃圾郵件的層級。</span><span class="sxs-lookup"><span data-stu-id="b4107-139">Administrators can use the Bulk Slider in the Antispam policy to decide what level of bulk mail to treat as spam.</span></span>

6. <span data-ttu-id="b4107-140">**信箱智慧** 從標準使用者電子郵件行為。</span><span class="sxs-lookup"><span data-stu-id="b4107-140">**Mailbox intelligence** learns from standard user email behaviors.</span></span> <span data-ttu-id="b4107-141">它會利用使用者的通訊圖來偵測寄件者，其是否只顯示為使用者通常會與其通訊，但實際上為惡意的人。</span><span class="sxs-lookup"><span data-stu-id="b4107-141">It leverages a user's communication graph to detect when a sender only appears to be someone the user usually communicates with, but is actually malicious.</span></span> <span data-ttu-id="b4107-142">此方法會偵測模擬。</span><span class="sxs-lookup"><span data-stu-id="b4107-142">This method detects impersonation.</span></span>

7. <span data-ttu-id="b4107-143">**信箱智慧** 模擬會根據每個使用者的個人寄件者地圖，啟用或停用增強的模仿結果。</span><span class="sxs-lookup"><span data-stu-id="b4107-143">**Mailbox intelligence impersonation** enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="b4107-144">啟用此功能時，會協助識別模擬。</span><span class="sxs-lookup"><span data-stu-id="b4107-144">When enabled, this feature helps to identify impersonation.</span></span>

8. <span data-ttu-id="b4107-145">**使用者** 模擬可讓系統管理員建立可能模仿的高價值目標清單。</span><span class="sxs-lookup"><span data-stu-id="b4107-145">**User impersonation** allows an admin to create a list of high value targets likely to be impersonated.</span></span> <span data-ttu-id="b4107-146">如果郵件到達的位置，寄件者的名稱和位址似乎與受保護的高價值帳戶相同，則會標記或標記郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-146">If a mail arrives where the sender only appears to have the same name and address as the protected high value account, the mail is marked or tagged.</span></span> <span data-ttu-id="b4107-147"> (例如，trα *tracye@contoso.com*) 的 *cye@contoso .com* 。</span><span class="sxs-lookup"><span data-stu-id="b4107-147">(For example, *trαcye@contoso.com* for *tracye@contoso.com*).</span></span>

9. <span data-ttu-id="b4107-148">**網域** 模擬會偵測與收件者網域類似的網域，並嘗試看起來像是內部網域。</span><span class="sxs-lookup"><span data-stu-id="b4107-148">**Domain impersonation** detects domains that are similar to the recipient's domain and that attempt to look like an internal domain.</span></span> <span data-ttu-id="b4107-149">例如，此類比 tracye@liw *tracye@litware.com* 的 *αre* 。</span><span class="sxs-lookup"><span data-stu-id="b4107-149">For example, this impersonation *tracye@liwαre.com* for *tracye@litware.com*.</span></span>

## <a name="phase-3---content-filtering"></a><span data-ttu-id="b4107-150">階段 3-內容篩選</span><span class="sxs-lookup"><span data-stu-id="b4107-150">Phase 3 - Content Filtering</span></span>

<span data-ttu-id="b4107-151">在這個階段中，篩選堆疊會開始處理郵件的特定內容，包括其超連結和附件。</span><span class="sxs-lookup"><span data-stu-id="b4107-151">In this phase the filtering stack begins to handle the specific contents of the mail, including its hyperlinks and attachments.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="MDO 中篩選的階段3是內容篩選。":::

1. <span data-ttu-id="b4107-153">**傳輸規則** (也稱為郵件流程規則或 Exchange 傳輸規則，) 可讓系統管理員在郵件符合相同範圍的情況時採取大量的動作。</span><span class="sxs-lookup"><span data-stu-id="b4107-153">**Transport rules** (also known as mail flow rules or Exchange transport rules) allow an admin to take a wide range of actions when an equally wide range of conditions are met for a message.</span></span> <span data-ttu-id="b4107-154">所有流經您組織的郵件都會針對已啟用的郵件流程規則/傳輸規則進行評估。</span><span class="sxs-lookup"><span data-stu-id="b4107-154">All messages that flow through your organization are evaluated against the enabled mail flow rules / transport rules.</span></span>

2. <span data-ttu-id="b4107-155">**Microsoft Defender 防毒軟體** 和兩個 *協力廠商防病毒引擎* 都是用來偵測附件中的所有已知惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="b4107-155">**Microsoft Defender Antivirus** and two *third-party Antivirus engines* are used to detect all known malware in attachments.</span></span>

3. <span data-ttu-id="b4107-156">防病毒 (AV) 引擎也可用於 true 輸入所有附件，所以 **類型封鎖** 可以封鎖 admin 所指定類型的所有附件。</span><span class="sxs-lookup"><span data-stu-id="b4107-156">The anti-virus (AV) engines are also used to true-type all attachments, so that **Type blocking** can block all attachments of types the admin specifies.</span></span>

4. <span data-ttu-id="b4107-157">每當 Microsoft Defender Office 365 偵測到惡意附件時，檔案的雜湊及其作用中內容的雜湊會新增至 Exchange Online Protection (EOP) 信譽。</span><span class="sxs-lookup"><span data-stu-id="b4107-157">Whenever Microsoft Defender for Office 365 detects a malicious attachment, the file's hash, and a hash of its active content, are added to Exchange Online Protection (EOP) reputation.</span></span> <span data-ttu-id="b4107-158">**附件信譽封鎖** 會透過 MSAV 雲端通話，封鎖所有 Office 365 和端點上的檔案。</span><span class="sxs-lookup"><span data-stu-id="b4107-158">**Attachment reputation blocking** will block that file across all Office 365, and on endpoints, through MSAV cloud calls.</span></span>

5. <span data-ttu-id="b4107-159">**啟發式** 叢集可根據傳遞試探法判斷檔案是否可疑。</span><span class="sxs-lookup"><span data-stu-id="b4107-159">**Heuristic clustering** can determine that a file is suspicious based on delivery heuristics.</span></span> <span data-ttu-id="b4107-160">當發現可疑附件時，整個活動會暫停，而且檔案會進行沙箱化。</span><span class="sxs-lookup"><span data-stu-id="b4107-160">When a suspicious attachment is found, the entire campaign pauses, and the file is sandboxed.</span></span> <span data-ttu-id="b4107-161">若發現有惡意的檔案，則會封鎖整個活動。</span><span class="sxs-lookup"><span data-stu-id="b4107-161">If the file is found to be malicious, the entire campaign is blocked.</span></span>

6. <span data-ttu-id="b4107-162">**Machine 教學模型** 會作用於標頭、正文內容及郵件 URLs，以偵測網路釣魚企圖。</span><span class="sxs-lookup"><span data-stu-id="b4107-162">**Machine learning models** act on the header, body content, and URLs of a message to detect phishing attempts.</span></span>

7. <span data-ttu-id="b4107-163">Microsoft 使用 URL 沙箱中的信譽，以及 **url 信譽封鎖** 中協力廠商摘要的 url 聲譽，以封鎖任何具有已知惡意 URL 的郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-163">Microsoft uses a determination of reputation from URL sandboxing as well as URL reputation from third party feeds in **URL reputation blocking**, to block any message with a known malicious URL.</span></span>

8. <span data-ttu-id="b4107-164">**內容試探法** 可使用機器學習模型，根據郵件本文內的結構和字頻率，偵測可疑的郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-164">**Content heuristics** can detect suspicious messages based on structure and word frequency within the body of the message, using machine learning models.</span></span>

9. <span data-ttu-id="b4107-165">**安全附件** 會沙箱 Office 365 客戶的所有適用于 Defender 的附件，使用動態分析來偵測出永不出現威脅。</span><span class="sxs-lookup"><span data-stu-id="b4107-165">**Safe Attachments** sandboxes every attachment for Defender for Office 365 customers, using dynamic analysis to detect never-before seen threats.</span></span>

10. <span data-ttu-id="b4107-166">**連結的內容引爆** 會將電子郵件中的每個 URL 連結到一個附件，並在傳遞時以非同步方式沙箱處理該檔案。</span><span class="sxs-lookup"><span data-stu-id="b4107-166">**Linked content detonation** treats every URL linking to a file in an email as an attachment, asynchronously sandboxing the file at the time of delivery.</span></span>

11. <span data-ttu-id="b4107-167">當上游反網路釣魚技術發現郵件或 URL 可疑時，便會發生 **URL 引爆**。</span><span class="sxs-lookup"><span data-stu-id="b4107-167">**URL Detonation** happens when upstream anti-phishing technology finds a message or URL to be suspicious.</span></span> <span data-ttu-id="b4107-168">URL 引爆會在傳遞時，沙箱訊息中的 URLs。</span><span class="sxs-lookup"><span data-stu-id="b4107-168">URL detonation sandboxes the URLs in the message at the time of delivery.</span></span>

## <a name="phase-4---post-delivery-protection"></a><span data-ttu-id="b4107-169">階段 4-投遞後保護</span><span class="sxs-lookup"><span data-stu-id="b4107-169">Phase 4 - Post-Delivery Protection</span></span>

<span data-ttu-id="b4107-170">最後一個階段是在郵件或檔傳遞時，作用於位於各種信箱和檔案中的郵件，以及出現在用戶端（如 Microsoft Teams）中的連結。</span><span class="sxs-lookup"><span data-stu-id="b4107-170">The last stage takes place after mail or file delivery, acting on mail that is in various mailboxes and files and links that appear in clients like Microsoft Teams.</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Office 365 中，篩選的階段4是傳遞後的保護。":::

1. <span data-ttu-id="b4107-172">**安全連結** 是 Office 365 的時按一下保護的 Defender。</span><span class="sxs-lookup"><span data-stu-id="b4107-172">**Safe Links** is Defender for Office 365's time-of-click protection.</span></span> <span data-ttu-id="b4107-173">每封郵件中的每個 URL 都會換行，指向 Microsoft 安全連結伺服器。</span><span class="sxs-lookup"><span data-stu-id="b4107-173">Every URL in every message is wrapped to point to Microsoft Safe Links servers.</span></span> <span data-ttu-id="b4107-174">當按一下 URL 時，會將使用者重新導向至目標網站之前，檢查其最新的信譽。</span><span class="sxs-lookup"><span data-stu-id="b4107-174">When a URL is clicked it is checked against the latest reputation, before the user is redirected to the target site.</span></span> <span data-ttu-id="b4107-175">URL 會以非同步方式沙箱化，以更新其信譽。</span><span class="sxs-lookup"><span data-stu-id="b4107-175">The URL is asynchronously sandboxed to update its reputation.</span></span>

2. <span data-ttu-id="b4107-176">**以零小時自動清除 (ZAP) 網路釣魚** retroactively 會偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意網路釣魚郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-176">**Zero-Hour Auto-purge (ZAP) for phishing** retroactively detects and neutralizes malicious phishing messages that have already been delivered to Exchange Online mailboxes.</span></span>

3. <span data-ttu-id="b4107-177">retroactively **惡意** 代碼會偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意惡意程式碼郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-177">**ZAP for malware** retroactively detects and neutralizes malicious malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

4. <span data-ttu-id="b4107-178">**網路釣魚** retroactively 的 ZAP 偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="b4107-178">**ZAP for phishing** retroactively detects and neutralizes malicious spam messages that have already been delivered to Exchange Online mailboxes.</span></span>

5. <span data-ttu-id="b4107-179">[**活動] 視圖** 可讓系統管理員看到重要的攻擊、更快速且更徹底的攻擊，而不是任何小組都可以進行「自動化」。</span><span class="sxs-lookup"><span data-stu-id="b4107-179">**Campaign Views** let administrators see the big picture of an attack, faster and more completely, than any team could without automation.</span></span> <span data-ttu-id="b4107-180">Microsoft 利用整個服務中大量的反網路釣魚、反垃圾郵件和反惡意程式碼，協助識別市場活動，然後讓系統管理員可以從開始到結尾（包括目標、影響和流程）進行調查，也可以在可下載的活動中使用。</span><span class="sxs-lookup"><span data-stu-id="b4107-180">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns, and then allows admins to investigate them from start to end, including targets, impacts, and flows, that are also available in a downloadable campaign write-up.</span></span>

6. <span data-ttu-id="b4107-181">**報告郵件增益集** 可讓使用者輕鬆報告誤報 (良好的電子郵件、誤標示為 *壞*) 或 false 不利 (錯誤電子郵件標示為 *良好* 的 Microsoft 進行進一步分析) 。</span><span class="sxs-lookup"><span data-stu-id="b4107-181">**The Report Message add-ins** enable people to easily report false positives (good email, mistakenly marked as *bad*) or false negatives (bad email marked as *good*) to Microsoft for further analysis.</span></span>

7. <span data-ttu-id="b4107-182">**Office 用戶端的安全連結**，可在 Office 用戶端（如 Word、PowerPoint 及 Excel）中提供相同的安全連結時間和即時防護。</span><span class="sxs-lookup"><span data-stu-id="b4107-182">**Safe Links for Office clients** offers the same Safe Links time-of-click protection, natively, inside of Office clients like Word, PowerPoint, and Excel.</span></span>

8. <span data-ttu-id="b4107-183">對 **OneDrive、SharePoint 和 Teams 的保護，** 可為 OneDrive、SharePoint 和 Microsoft Teams 等惡意檔案提供相同的安全附件防護。</span><span class="sxs-lookup"><span data-stu-id="b4107-183">**Protection for OneDrive, SharePoint, and Teams** offers the same Safe Attachments protection against malicious files, natively, inside of OneDrive, SharePoint, and Microsoft Teams.</span></span>

9. <span data-ttu-id="b4107-184">當選取指向檔案的 URL 後，傳遞傳遞時， **連結的內容引爆** 會顯示警告頁面，直到檔案的沙箱處理完成，並且找到安全的 url 為止。</span><span class="sxs-lookup"><span data-stu-id="b4107-184">When a URL that points to a file is selected post delivery, **linked content detonation** displays a warning page until the sandboxing of the file is complete, and the URL is found to be safe.</span></span>

## <a name="the-filtering-stack-diagram"></a><span data-ttu-id="b4107-185">篩選堆疊圖表</span><span class="sxs-lookup"><span data-stu-id="b4107-185">The filtering stack diagram</span></span>

<span data-ttu-id="b4107-186">最後的圖表 (，與組成它之圖表的所有部分) *在產品成長及開發時可能會有所變更*。</span><span class="sxs-lookup"><span data-stu-id="b4107-186">The final diagram (as with all parts of the diagram composing it) *is subject to change as the product grows and develops*.</span></span> <span data-ttu-id="b4107-187">在此頁面上加上書簽，如果您需要在更新後要求，請使用您在底部所看到的 **意見** 反應選項。</span><span class="sxs-lookup"><span data-stu-id="b4107-187">Bookmark this page and use the **feedback** option you'll find at the bottom if you need to ask after updates.</span></span> <span data-ttu-id="b4107-188">針對您的記錄，這是以順序顯示所有階段的堆疊：</span><span class="sxs-lookup"><span data-stu-id="b4107-188">For your records, this is the the stack with all the phases in order:</span></span>

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="MDO 中篩選的所有階段，順序為1到4。":::

## <a name="more-information"></a><span data-ttu-id="b4107-190">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b4107-190">More information</span></span>

<span data-ttu-id="b4107-191">您 **現在** 是否需要為 Office 365 \* 設定 Microsoft Defender？</span><span class="sxs-lookup"><span data-stu-id="b4107-191">Do you need to set up Microsoft Defender for Office 365 \***right now** _?</span></span> <span data-ttu-id="b4107-192">使用此堆疊（_now \* [）逐步開始](protect-against-threats.md) 保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="b4107-192">Use this stack, _now\*, with [this step-by-step](protect-against-threats.md) to start protecting your organization.</span></span>

<span data-ttu-id="b4107-193">*特別感謝從 MSFTTracyP 及檔撰寫小組到此內容的 Giulian Garruba*。</span><span class="sxs-lookup"><span data-stu-id="b4107-193">*Special thanks from MSFTTracyP and the docs writing team to Giulian Garruba for this content*.</span></span>
