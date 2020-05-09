---
title: 零小時自動清除（ZAP）-電子郵件保護功能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解0小時自動清除（ZAP），這是 Microsoft 365 中的電子郵件保護功能，可偵測已傳遞至 Exchange Online 的垃圾郵件、惡意程式碼或網路釣魚郵件。
ms.openlocfilehash: ba7aa74dd9152990ce327d1b1564c3246d15cbb8
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173295"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a><span data-ttu-id="1ba18-103">零小時自動清除（ZAP）-防護 Microsoft 365 中的垃圾郵件和惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="1ba18-103">Zero-hour auto purge (ZAP) - protection against spam and malware in Microsoft 365</span></span>

## <a name="overview"></a><span data-ttu-id="1ba18-104">概觀</span><span class="sxs-lookup"><span data-stu-id="1ba18-104">Overview</span></span>

<span data-ttu-id="1ba18-105">零小時自動清除（ZAP）是 Microsoft 365 中的電子郵件保護功能，retroactively 偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意網路釣魚、垃圾郵件或惡意程式碼郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-105">Zero-hour auto purge (ZAP) is an email protection feature in Microsoft 365 that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="1ba18-106">您可以使用包含 Exchange Online 信箱之任何 Microsoft 365 訂閱隨附的預設 Exchange Online Protection （EOP）的 ZAP。</span><span class="sxs-lookup"><span data-stu-id="1ba18-106">ZAP is available with the default Exchange Online Protection (EOP) that's included with any Microsoft 365 subscription that contains Exchange Online mailboxes.</span></span> <span data-ttu-id="1ba18-107">在會保護內部部署 Exchange 信箱的獨立 EOP 環境中，ZAP 無法運作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-107">ZAP doesn't work in standalone EOP environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="1ba18-108">ZAP 的運作方式</span><span class="sxs-lookup"><span data-stu-id="1ba18-108">How ZAP works</span></span>

<span data-ttu-id="1ba18-109">Microsoft 365 每天都會即時更新垃圾郵件和惡意程式碼簽名。</span><span class="sxs-lookup"><span data-stu-id="1ba18-109">Microsoft 365 updates spam and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="1ba18-110">不過，使用者仍然可以接收惡意郵件，但有各種原因，包括在傳遞給使用者後 weaponized 內容。</span><span class="sxs-lookup"><span data-stu-id="1ba18-110">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="1ba18-111">ZAP 會持續監控 Microsoft 365 垃圾郵件和惡意程式碼簽章的更新，以解決此問題。</span><span class="sxs-lookup"><span data-stu-id="1ba18-111">ZAP addresses this issue by continually monitoring updates to the Microsoft 365 spam and malware signatures.</span></span> <span data-ttu-id="1ba18-112">ZAP 可以尋找及移除已在使用者信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-112">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="1ba18-113">對使用者而言，ZAP 動作是無縫的;如果偵測到郵件並加以移動，不會通知他們。</span><span class="sxs-lookup"><span data-stu-id="1ba18-113">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="1ba18-114">[安全寄件者清單](create-safe-sender-lists-in-office-365.md)、郵件流程規則（也稱為傳輸規則）、收件匣規則或其他篩選器優先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="1ba18-114">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="1ba18-115">類似于郵件流程中所發生的情況，這表示即使服務決定所傳送的郵件需求 ZAP，但由於安全寄件者設定的原因，郵件並未採取動作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-115">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="1ba18-116">這是將郵件設定為略過篩選所需注意的另一個原因。</span><span class="sxs-lookup"><span data-stu-id="1ba18-116">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="1ba18-117">惡意程式碼 ZAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-117">Malware ZAP</span></span>

<span data-ttu-id="1ba18-118">若為傳遞之後發現包含惡意程式碼的**讀取或未讀取郵件**，ZAP 會隔離包含惡意程式碼附件的郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-118">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="1ba18-119">只有系統管理員可以從隔離區中查看和管理惡意程式碼郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-119">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="1ba18-120">在反惡意程式碼原則中，預設會啟用惡意程式碼 ZAP。</span><span class="sxs-lookup"><span data-stu-id="1ba18-120">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="1ba18-121">如需詳細資訊，請參閱[在 Microsoft 365 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba18-121">For more information, see [Configure anti-malware policies in Microsoft 365](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="1ba18-122">網路釣魚 ZAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-122">Phish ZAP</span></span>

<span data-ttu-id="1ba18-123">針對傳送後識別為網路釣魚的**讀取或未讀取郵件**，ZAP 結果取決於針對網路釣魚電子郵件原則中設定的**網路釣魚電子**郵件篩選的動作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-123">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="1ba18-124">下列清單說明網路釣魚和其可能的 ZAP 結果的可用篩選判定動作：</span><span class="sxs-lookup"><span data-stu-id="1ba18-124">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="1ba18-125">**新增 X-Header**，**並將主旨行前置文字**： ZAP 不會對郵件採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-125">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="1ba18-126">**將郵件移至垃圾郵件**：只要信箱上啟用垃圾郵件規則（預設為啟用），ZAP 就會將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1ba18-126">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1ba18-127">如需詳細資訊，請參閱[在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba18-127">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="1ba18-128">**將郵件重新導向至電子郵件地址**、**刪除郵件**、**隔離訊息**： ZAP 會隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-128">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="1ba18-129">只有系統管理員可以查看和管理網路釣魚隔離的郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-129">Only admins can view and manage phish quarantined messages.</span></span>

<span data-ttu-id="1ba18-130">根據預設，反垃圾郵件原則中已啟用網路釣魚 ZAP，**網路釣魚電子郵件**篩選決定的預設動作為**隔離訊息**，這表示網路釣魚網站預設會隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-130">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="1ba18-131">如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱[在 Microsoft 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba18-131">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="1ba18-132">垃圾郵件 ZAP</span><span class="sxs-lookup"><span data-stu-id="1ba18-132">Spam ZAP</span></span>

<span data-ttu-id="1ba18-133">針對傳送後被識別為垃圾郵件的**未讀取郵件**，ZAP 結果取決於針對**垃圾**郵件篩選決定在適用的反垃圾郵件原則中所設定的動作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-133">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="1ba18-134">下列清單說明了垃圾郵件及其可能的 ZAP 結果的可用篩選：</span><span class="sxs-lookup"><span data-stu-id="1ba18-134">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="1ba18-135">**新增 X-Header**，**並將主旨行前置文字**： ZAP 不會對郵件採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-135">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="1ba18-136">**將郵件移至垃圾郵件**：只要信箱上啟用垃圾郵件規則（預設為啟用），ZAP 就會將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1ba18-136">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1ba18-137">如需詳細資訊，請參閱[在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba18-137">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="1ba18-138">**將郵件重新導向至電子郵件地址**、**刪除郵件**、**隔離訊息**： ZAP 會隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-138">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="1ba18-139">使用者可以查看和管理自己的垃圾郵件隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-139">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="1ba18-140">根據預設，反垃圾郵件原則中已啟用垃圾郵件 ZAP，**垃圾**郵件篩選判定的預設動作是**將郵件移至垃圾郵件資料夾**，這表示垃圾郵件 ZAP 預設會將**未讀取**的郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1ba18-140">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="1ba18-141">如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱[在 Microsoft 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba18-141">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a><span data-ttu-id="1ba18-142">Office 365 高級威脅防護（ATP）的 ZAP 考慮</span><span class="sxs-lookup"><span data-stu-id="1ba18-142">ZAP considerations for Office 365 Advanced Threat Protection (ATP)</span></span>

<span data-ttu-id="1ba18-143">在[動態傳遞](dynamic-delivery-and-previewing.md)掃描的處理常式中，或惡意程式碼篩選已使用**惡意程式碼警示文字 .txt**檔取代附件的情況下，ZAP 將不會隔離任何郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-143">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="1ba18-144">如果針對這些類型的郵件接收網路釣魚或垃圾郵件信號，而且反垃圾郵件原則中的篩選判定會設定為對郵件採取某些動作（移至 [垃圾郵件]、[重新導向]、[刪除] 隔離），則 ZAP 會預設為「移至垃圾郵件」動作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-144">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="1ba18-145">如何查看 ZAP 是否已移動您的郵件</span><span class="sxs-lookup"><span data-stu-id="1ba18-145">How to see if ZAP moved your message</span></span>

<span data-ttu-id="1ba18-146">若要判斷 ZAP 是否已移動您的郵件，您可以使用[威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)或[威脅總管 (及即時偵測)](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba18-146">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="1ba18-147">請注意，在系統動作中，不會在 Exchange 信箱審計記錄檔中記錄 ZAP。</span><span class="sxs-lookup"><span data-stu-id="1ba18-147">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="1ba18-148">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="1ba18-148">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="1ba18-149">將合法郵件移至 [垃圾郵件] 資料夾時會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="1ba18-149">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="1ba18-150">您應遵循正常的報告處理常式來[誤報](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba18-150">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="1ba18-151">郵件會從 [收件匣] 移至 [垃圾郵件] 資料夾，其唯一原因是服務已判斷郵件是垃圾郵件或惡意的。</span><span class="sxs-lookup"><span data-stu-id="1ba18-151">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="1ba18-152">使用隔離資料夾而非 [垃圾郵件] 資料夾時該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="1ba18-152">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="1ba18-153">根據本主題稍早所述的設定反垃圾郵件原則，ZAP 會對郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-153">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="1ba18-154">如果我使用安全寄件者、郵件流程規則或允許/封鎖的寄件者清單，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="1ba18-154">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="1ba18-155">安全寄件者、郵件流程規則或封鎖及允許組織設定會優先。</span><span class="sxs-lookup"><span data-stu-id="1ba18-155">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="1ba18-156">因為服務正在執行您設定的工作，所以這些郵件會從 ZAP 中排除。</span><span class="sxs-lookup"><span data-stu-id="1ba18-156">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="1ba18-157">這是將郵件設定為略過篩選所需注意的另一個原因。</span><span class="sxs-lookup"><span data-stu-id="1ba18-157">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="1ba18-158">如果郵件移至另一個資料夾（例如收件匣規則），該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="1ba18-158">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="1ba18-159">只要郵件尚未刪除，或是尚未套用相同或更強的動作，ZAP 仍可運作。</span><span class="sxs-lookup"><span data-stu-id="1ba18-159">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="1ba18-160">例如，如果網路釣魚原則設定為 [隔離]，而且使用者或系統管理員已經 junked 電子郵件，則隔離會採取動作隔離檔案。</span><span class="sxs-lookup"><span data-stu-id="1ba18-160">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="does-zap-change-the-message-header"></a><span data-ttu-id="1ba18-161">ZAP 是否會變更郵件頭？</span><span class="sxs-lookup"><span data-stu-id="1ba18-161">Does ZAP change the message header?</span></span>

<span data-ttu-id="1ba18-162">ZAP 動作不會對郵件頭進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="1ba18-162">A ZAP action does not make any changes to the message header.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="1ba18-163">ZAP 如何影響信箱的保留狀態？</span><span class="sxs-lookup"><span data-stu-id="1ba18-163">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="1ba18-164">ZAP 不會隔離保留信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="1ba18-164">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="1ba18-165">根據為反垃圾郵件原則中的垃圾郵件或網路釣魚所設定的動作，ZAP 可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1ba18-165">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="1ba18-166">如需 Exchange Online 中的保留的詳細資訊，請參閱[Exchange online 中的 In-Place 保留和訴訟暫](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)止。</span><span class="sxs-lookup"><span data-stu-id="1ba18-166">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
