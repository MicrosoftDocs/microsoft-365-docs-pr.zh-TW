---
title: '零小時自動清除 (ZAP) '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 系統管理員可以瞭解零小時自動清除 (ZAP) 是否可以 retroactively 將 Exchange Online 信箱中已傳遞的郵件移至 [垃圾郵件] 資料夾，或 retroactively 發現為垃圾郵件或網路釣魚的隔離區。
ms.openlocfilehash: fd5186bc40d2d80097e6292d86ea113a41e0dd52
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131139"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="29d24-103">在 Exchange Online 中，以零小時自動清除 (ZAP) </span><span class="sxs-lookup"><span data-stu-id="29d24-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="29d24-104">ZAP 的基本功能</span><span class="sxs-lookup"><span data-stu-id="29d24-104">Basic features of ZAP</span></span>

<span data-ttu-id="29d24-105">在 Exchange Online 中有信箱的 Microsoft 365 組織中，零小時自動清除 (ZAP) 是一種電子郵件保護功能，retroactively 偵測並 neutralizes 已傳遞至 Exchange Online 信箱的惡意網路釣魚、垃圾郵件或惡意程式碼郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="29d24-106">ZAP 無法在獨立 Exchange Online Protection (EOP 中運作) 保護內部部署 Exchange 信箱的環境。</span><span class="sxs-lookup"><span data-stu-id="29d24-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="29d24-107">ZAP 的運作方式</span><span class="sxs-lookup"><span data-stu-id="29d24-107">How ZAP works</span></span>

<span data-ttu-id="29d24-108">垃圾郵件和惡意程式碼會在服務中即時更新。</span><span class="sxs-lookup"><span data-stu-id="29d24-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="29d24-109">不過，使用者仍然可以接收惡意郵件，但有各種原因，包括在傳遞給使用者後 weaponized 內容。</span><span class="sxs-lookup"><span data-stu-id="29d24-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="29d24-110">ZAP 會持續監控服務中垃圾郵件和惡意程式碼簽名的更新，以解決此問題。</span><span class="sxs-lookup"><span data-stu-id="29d24-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="29d24-111">ZAP 可以尋找及移除已在使用者信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="29d24-112">對使用者而言，ZAP 動作是無縫的;如果偵測到郵件並加以移動，不會通知他們。</span><span class="sxs-lookup"><span data-stu-id="29d24-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="29d24-113">[安全寄件者清單](create-safe-sender-lists-in-office-365.md)、郵件流程規則 (也稱為傳輸規則) 、收件匣規則或其他篩選，其優先順序會高於 ZAP。</span><span class="sxs-lookup"><span data-stu-id="29d24-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="29d24-114">類似于郵件流程中所發生的情況，這表示即使服務決定所傳送的郵件需求 ZAP，但由於安全寄件者設定的原因，郵件並未採取動作。</span><span class="sxs-lookup"><span data-stu-id="29d24-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="29d24-115">這是將郵件設定為略過篩選所需注意的另一個原因。</span><span class="sxs-lookup"><span data-stu-id="29d24-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="29d24-116">惡意程式碼 ZAP</span><span class="sxs-lookup"><span data-stu-id="29d24-116">Malware ZAP</span></span>

<span data-ttu-id="29d24-117">若為傳遞之後發現包含惡意程式碼的 **讀取或未讀取郵件** ，ZAP 會隔離包含惡意程式碼附件的郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="29d24-118">只有系統管理員可以從隔離區中查看和管理惡意程式碼郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="29d24-119">在反惡意程式碼原則中，預設會啟用惡意程式碼 ZAP。</span><span class="sxs-lookup"><span data-stu-id="29d24-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="29d24-120">如需詳細資訊，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="29d24-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="29d24-121">網路釣魚 ZAP</span><span class="sxs-lookup"><span data-stu-id="29d24-121">Phish ZAP</span></span>

<span data-ttu-id="29d24-122">針對傳送後識別為網路釣魚的 **讀取或未讀取郵件** ，ZAP 結果取決於針對網路釣魚電子郵件原則中設定的 **網路釣魚電子** 郵件篩選的動作。</span><span class="sxs-lookup"><span data-stu-id="29d24-122">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="29d24-123">下列清單說明網路釣魚和其可能的 ZAP 結果的可用篩選判定動作：</span><span class="sxs-lookup"><span data-stu-id="29d24-123">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="29d24-124">**新增 X-Header**， **並將主旨行前置文字**： ZAP 不會對郵件採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="29d24-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="29d24-125">**將郵件移至垃圾郵件**：將郵件移至 [垃圾郵件] 資料夾，只要信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。</span><span class="sxs-lookup"><span data-stu-id="29d24-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="29d24-126">如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="29d24-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="29d24-127">**將郵件重新導向至電子郵件地址**、 **刪除郵件**、 **隔離訊息**： ZAP 會隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="29d24-128">根據預設，反垃圾郵件原則中已啟用網路釣魚 ZAP， **網路釣魚電子郵件** 篩選決定的預設動作為 **隔離訊息**，這表示網路釣魚網站預設會隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="29d24-129">如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱 [在 Microsoft 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="29d24-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="29d24-130">垃圾郵件 ZAP</span><span class="sxs-lookup"><span data-stu-id="29d24-130">Spam ZAP</span></span>

<span data-ttu-id="29d24-131">針對傳送後被識別為垃圾郵件的 **未讀取郵件** ，ZAP 結果取決於針對 **垃圾** 郵件篩選決定在適用的反垃圾郵件原則中所設定的動作。</span><span class="sxs-lookup"><span data-stu-id="29d24-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="29d24-132">下列清單說明了垃圾郵件及其可能的 ZAP 結果的可用篩選：</span><span class="sxs-lookup"><span data-stu-id="29d24-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="29d24-133">**新增 X-Header**， **並將主旨行前置文字**： ZAP 不會對郵件採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="29d24-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="29d24-134">**將郵件移至垃圾郵件**：將郵件移至 [垃圾郵件] 資料夾，只要信箱上已啟用垃圾郵件規則 (預設會啟用該信箱) 。</span><span class="sxs-lookup"><span data-stu-id="29d24-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="29d24-135">如需詳細資訊，請參閱 [在 Microsoft 365 中的 Exchange Online 信箱上設定垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="29d24-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="29d24-136">**將郵件重新導向至電子郵件地址**、 **刪除郵件**、 **隔離訊息**： ZAP 會隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="29d24-137">使用者可以查看和管理自己的垃圾郵件隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="29d24-138">根據預設，反垃圾郵件原則中已啟用垃圾郵件 ZAP， **垃圾** 郵件篩選判定的預設動作是 **將郵件移至垃圾郵件資料夾**，這表示垃圾郵件 ZAP 預設會將 **未讀取** 的郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="29d24-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="29d24-139">如需設定垃圾郵件篩選 verdicts 的詳細資訊，請參閱 [在 Microsoft 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="29d24-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="29d24-140">Microsoft Defender for Office 365 的 ZAP 考慮</span><span class="sxs-lookup"><span data-stu-id="29d24-140">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="29d24-141">在安全附件掃描中，ZAP 不會隔離 [動態傳遞](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) 的處理常式中的任何郵件，或者 EOP 惡意程式碼篩選已以 **惡意程式碼 Text.txt警示** 取代附件的郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="29d24-142">如果針對這些類型的郵件接收網路釣魚或垃圾郵件信號，而且反垃圾郵件原則中的篩選判定會設定為對郵件採取某些動作 (移至 [垃圾郵件]、[重新導向]、[刪除] 或 [隔離]) 然後，ZAP 會預設為「移至垃圾郵件」動作。</span><span class="sxs-lookup"><span data-stu-id="29d24-142">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="29d24-143">如何查看 ZAP 是否已移動您的郵件</span><span class="sxs-lookup"><span data-stu-id="29d24-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="29d24-144">若要判斷 ZAP 是否已移動您的郵件，您可以使用[威脅防護狀態報告](view-email-security-reports.md#threat-protection-status-report)或[威脅總管 (及即時偵測)](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="29d24-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="29d24-145">請注意，在系統動作中，不會在 Exchange 信箱審計記錄檔中記錄 ZAP。</span><span class="sxs-lookup"><span data-stu-id="29d24-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="29d24-146">ZAP FAQ</span><span class="sxs-lookup"><span data-stu-id="29d24-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="29d24-147">將合法郵件移至 [垃圾郵件] 資料夾時會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="29d24-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="29d24-148">您應遵循正常的報告處理常式來 [誤報](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="29d24-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="29d24-149">郵件會從 [收件匣] 移至 [垃圾郵件] 資料夾，其唯一原因是服務已判斷郵件是垃圾郵件或惡意的。</span><span class="sxs-lookup"><span data-stu-id="29d24-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="29d24-150">使用隔離資料夾而非 [垃圾郵件] 資料夾時該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="29d24-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="29d24-151">根據本主題稍早所述的設定反垃圾郵件原則，ZAP 會對郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="29d24-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="29d24-152">如果我使用安全寄件者、郵件流程規則或允許/封鎖的寄件者清單，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="29d24-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="29d24-153">安全寄件者、郵件流程規則或封鎖及允許組織設定會優先。</span><span class="sxs-lookup"><span data-stu-id="29d24-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="29d24-154">因為服務正在執行您設定的工作，所以這些郵件會從 ZAP 中排除。</span><span class="sxs-lookup"><span data-stu-id="29d24-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="29d24-155">這是將郵件設定為略過篩選所需注意的另一個原因。</span><span class="sxs-lookup"><span data-stu-id="29d24-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="29d24-156">當郵件移至另一個資料夾 (例如收件匣規則) 時，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="29d24-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="29d24-157">只要郵件尚未刪除，或是尚未套用相同或更強的動作，ZAP 仍可運作。</span><span class="sxs-lookup"><span data-stu-id="29d24-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="29d24-158">例如，如果反網路釣魚原則設定為 [隔離]，且郵件已經在垃圾郵件中，則 ZAP 會採取動作隔離郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-158">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="29d24-159">ZAP 如何影響信箱的保留狀態？</span><span class="sxs-lookup"><span data-stu-id="29d24-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="29d24-160">ZAP 不會隔離保留信箱中的郵件。</span><span class="sxs-lookup"><span data-stu-id="29d24-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="29d24-161">根據為反垃圾郵件原則中的垃圾郵件或網路釣魚所設定的動作，ZAP 可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="29d24-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="29d24-162">如需 Exchange Online 中的保留的詳細資訊，請參閱 [Exchange online 中的 In-Place 保留和訴訟暫](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)止。</span><span class="sxs-lookup"><span data-stu-id="29d24-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
