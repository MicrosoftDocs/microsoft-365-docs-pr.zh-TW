---
title: 建立封鎖寄件者清單
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
description: 系統管理員可以瞭解可用及慣用的選項，以封鎖 Exchange Online Protection (EOP) 中的輸入郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c844378a19ba7995cbd616f615e8a84994f9bf26
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624075"
---
# <a name="create-blocked-sender-lists-in-eop"></a><span data-ttu-id="97c75-103">在 EOP 中建立封鎖的寄件者清單</span><span class="sxs-lookup"><span data-stu-id="97c75-103">Create blocked sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97c75-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="97c75-104">**Applies to**</span></span>
- [<span data-ttu-id="97c75-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="97c75-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="97c75-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="97c75-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="97c75-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97c75-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="97c75-108">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，EOP 提供多種方式，封鎖來自有害寄件者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="97c75-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="97c75-109">這些選項包括反垃圾郵件原則中 Outlook 封鎖的寄件者]、[封鎖的寄件者清單] 或 [封鎖的功能變數名稱] 清單、Exchange 郵件流程規則 (也稱為傳輸規則) ，以及 IP 封鎖清單 (連線篩選) 。</span><span class="sxs-lookup"><span data-stu-id="97c75-109">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="97c75-110">綜合，您可以將這些選項視為 _封鎖的寄件者清單_。</span><span class="sxs-lookup"><span data-stu-id="97c75-110">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="97c75-111">封鎖寄件者的最佳方法會因影響範圍而異。</span><span class="sxs-lookup"><span data-stu-id="97c75-111">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="97c75-112">針對單一使用者，正確的解決方案可能會 Outlook 封鎖的寄件者。</span><span class="sxs-lookup"><span data-stu-id="97c75-112">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="97c75-113">對於許多使用者而言，其中一個其他選項更適合。</span><span class="sxs-lookup"><span data-stu-id="97c75-113">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="97c75-114">下列選項依影響範圍及廣度排名。</span><span class="sxs-lookup"><span data-stu-id="97c75-114">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="97c75-115">清單從窄到寬，但閱讀完整建議的 *詳細* 資料。</span><span class="sxs-lookup"><span data-stu-id="97c75-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="97c75-116">Outlook封鎖的寄件者 (儲存于每個信箱中的封鎖寄件者清單) </span><span class="sxs-lookup"><span data-stu-id="97c75-116">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="97c75-117"> (反垃圾郵件原則所封鎖的寄件者清單或封鎖的網域清單) </span><span class="sxs-lookup"><span data-stu-id="97c75-117">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="97c75-118">郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="97c75-118">Mail flow rules</span></span>

4. <span data-ttu-id="97c75-119">IP 封鎖清單 (連線篩選) </span><span class="sxs-lookup"><span data-stu-id="97c75-119">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="97c75-120">雖然您可以使用全組織的封鎖設定來處理誤報 (未接的垃圾郵件) ，您也應該將這些郵件提交給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="97c75-120">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="97c75-121">使用封鎖清單來管理 false 負片會大幅增加您的管理額外負荷。</span><span class="sxs-lookup"><span data-stu-id="97c75-121">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="97c75-122">如果您使用封鎖清單來轉移未接的垃圾郵件，您必須在準備時讓主題向 [Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md) 檔案。</span><span class="sxs-lookup"><span data-stu-id="97c75-122">If you use block lists to deflect missed spam, you need to keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>

<span data-ttu-id="97c75-123">相比之下，您也可以使用 _安全寄件者清單_，讓您有數個選項永遠允許來自特定來源的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="97c75-123">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="97c75-124">如需詳細資訊，請參閱[建立安全寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="97c75-124">For more information, see [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="email-message-basics"></a><span data-ttu-id="97c75-125">電子郵件訊息基礎</span><span class="sxs-lookup"><span data-stu-id="97c75-125">Email message basics</span></span>

<span data-ttu-id="97c75-126">標準 SMTP 電子郵件由「郵件信封」(Message Envelope) 和郵件內容組成。</span><span class="sxs-lookup"><span data-stu-id="97c75-126">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="97c75-127">郵件信封包含在 SMTP 伺服器之間傳輸及傳遞郵件所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="97c75-127">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="97c75-128">郵件內容包含統稱為 (「郵件標頭」) 的郵件標頭欄位和郵件內容。</span><span class="sxs-lookup"><span data-stu-id="97c75-128">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="97c75-129">RFC 5321 會說明郵件信封，而 RFC 5322 中說明郵件頭。</span><span class="sxs-lookup"><span data-stu-id="97c75-129">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="97c75-130">收件者永遠不會看到實際的郵件信封，因為它是由郵件傳輸程式所產生，而且實際上不是郵件的一部分。</span><span class="sxs-lookup"><span data-stu-id="97c75-130">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="97c75-131">此 `5321.MailFrom` 位址 (也稱為「 **郵件來自** 位址」、「P1 寄件者」或「信封寄件者」) 是在郵件的 SMTP 傳輸中使用的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="97c75-131">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="97c75-132">這個電子郵件地址通常會記錄在郵件頭的 [傳回 **路徑** 標頭] 欄位中 (不過，寄件者可能會指定不同的傳回 **路徑** 電子郵件地址) 。</span><span class="sxs-lookup"><span data-stu-id="97c75-132">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="97c75-133">如果無法傳遞郵件，表示未傳遞回報的收件者 (也稱為 NDR 或退回郵件) 。</span><span class="sxs-lookup"><span data-stu-id="97c75-133">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="97c75-134">`5322.From` (也稱為 **from** address 或 P2 sender) 是電子郵件地址 **的收** 件者標頭欄位，也就是顯示在電子郵件客戶程式中的寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="97c75-134">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="97c75-135">通常， `5321.MailFrom` 與 `5322.From` 位址 (人員對人員通訊) 相同。</span><span class="sxs-lookup"><span data-stu-id="97c75-135">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="97c75-136">不過，當您代表其他人傳送電子郵件時，位址可能會不同。</span><span class="sxs-lookup"><span data-stu-id="97c75-136">However, when email is sent on behalf of someone else, the addresses can be different.</span></span>

<span data-ttu-id="97c75-137">EOP 中，封鎖的寄件者清單和封鎖的網域清單會檢查 `5321.MailFrom` 和 `5322.From` 位址。</span><span class="sxs-lookup"><span data-stu-id="97c75-137">Blocked sender lists and blocked domain lists in anti-spam policies in EOP inspect both the `5321.MailFrom` and `5322.From` addresses.</span></span> <span data-ttu-id="97c75-138">Outlook封鎖的寄件者只會使用 `5322.From` 位址。</span><span class="sxs-lookup"><span data-stu-id="97c75-138">Outlook Blocked Senders only uses the `5322.From` address.</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="97c75-139">使用 Outlook 封鎖的寄件者</span><span class="sxs-lookup"><span data-stu-id="97c75-139">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="97c75-140">當只有少量的使用者收到不想要的電子郵件時，使用者或系統管理員可以將寄件者電子郵件地址新增至信箱中的封鎖寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="97c75-140">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="97c75-141">如需相關指示，請參閱[Configure 垃圾郵件 settings on Exchange Online 信箱](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="97c75-141">For instructions, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="97c75-142">當郵件因使用者的封鎖寄件者清單而成功封鎖時， **X-Forefront-Antispam-Report** 標頭欄位將會包含此值 `SFV:BLK` 。</span><span class="sxs-lookup"><span data-stu-id="97c75-142">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="97c75-143">如果不想要的郵件是來自可信和辨識來源的簡報，請從電子郵件取消訂閱，以停止使用者接收郵件。</span><span class="sxs-lookup"><span data-stu-id="97c75-143">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="97c75-144">使用封鎖的寄件者清單或封鎖的網域清單</span><span class="sxs-lookup"><span data-stu-id="97c75-144">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="97c75-145">當多個使用者受到影響時，範圍會變寬，所以下一個最佳選項是反垃圾郵件原則中的封鎖寄件者清單或封鎖的網域清單。</span><span class="sxs-lookup"><span data-stu-id="97c75-145">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="97c75-146">來自清單寄件者的郵件會標示為 **高信賴的垃圾郵件**，而您針對 **高信賴垃圾郵件** 篩選器判定所設定的動作會針對郵件採取。</span><span class="sxs-lookup"><span data-stu-id="97c75-146">Messages from senders on the lists are marked as **High confidence spam**, and the action that you've configured for the **High confidence spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="97c75-147">如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="97c75-147">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="97c75-148">這兩個清單的上限大約是1000個專案。</span><span class="sxs-lookup"><span data-stu-id="97c75-148">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="97c75-149">使用郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="97c75-149">Use mail flow rules</span></span>

<span data-ttu-id="97c75-150">如果您需要封鎖傳送給特定使用者或整個組織內的郵件，您可以使用郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="97c75-150">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="97c75-151">郵件流程規則比封鎖寄件者清單或封鎖的寄件者網域清單更為靈活，因為它們也可以在不想要的郵件中尋找關鍵字或其他屬性。</span><span class="sxs-lookup"><span data-stu-id="97c75-151">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="97c75-152">不論您用來識別郵件的條件或例外情況為何，您可以將動作設定為將郵件的垃圾郵件信賴等級 (SCL) 設定為9，這會將郵件標示為 **高信賴的垃圾** 郵件。</span><span class="sxs-lookup"><span data-stu-id="97c75-152">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="97c75-153">如需詳細資訊，請參閱 [使用郵件流程規則設定郵件中的 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。</span><span class="sxs-lookup"><span data-stu-id="97c75-153">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97c75-154">您可以輕鬆地建立 *過於* 嚴格的規則，所以請務必只使用特別的準則來識別您想要封鎖的郵件。</span><span class="sxs-lookup"><span data-stu-id="97c75-154">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="97c75-155">此外，請務必啟用規則的審計，並測試規則的結果，以確保所有內容如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="97c75-155">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="97c75-156">使用 IP 封鎖清單</span><span class="sxs-lookup"><span data-stu-id="97c75-156">Use the IP Block List</span></span>

<span data-ttu-id="97c75-157">當您無法使用其他其中一個選項來封鎖寄件者時， *只* 應該使用連線篩選原則中的 IP 封鎖清單。</span><span class="sxs-lookup"><span data-stu-id="97c75-157">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="97c75-158">如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="97c75-158">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="97c75-159">務必將封鎖的 Ip 數目維持在最小值，因此 *不* 建議封鎖整個 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="97c75-159">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="97c75-160">您應該 *特別* 避免新增屬於消費者服務 (的 IP 位址範圍，例如 outlook.com) 或共用基礎結構，也可以確保您檢查封鎖的 IP 位址清單以作為定期維護的一部分。</span><span class="sxs-lookup"><span data-stu-id="97c75-160">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
