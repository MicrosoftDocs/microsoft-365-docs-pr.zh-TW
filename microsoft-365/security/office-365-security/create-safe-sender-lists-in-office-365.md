---
title: 建立安全寄件者清單
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
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解可用及慣用的選項，允許在 Exchange Online Protection (EOP) 中輸入郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 33f4e9ac33f7952612e8b469345e38507ece5f4b
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453738"
---
# <a name="create-safe-sender-lists-in-eop"></a><span data-ttu-id="81492-103">在 EOP 中建立安全的寄件者清單</span><span class="sxs-lookup"><span data-stu-id="81492-103">Create safe sender lists in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="81492-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="81492-104">**Applies to**</span></span>
- [<span data-ttu-id="81492-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="81492-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="81492-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="81492-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="81492-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81492-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="81492-108">如果您是使用 Exchange Online 中的信箱或獨立 Exchange Online Protection (EOP) 客戶沒有 Exchange Online 信箱的 Microsoft 365 客戶，EOP 提供多種方式，以確保使用者能夠接收來自信任寄件者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="81492-108">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP offers multiple ways of ensuring that users will receive email from trusted senders.</span></span> <span data-ttu-id="81492-109">這些選項包括 Exchange 郵件流程規則 (也稱為傳輸規則) 、Outlook 安全寄件者、IP 允許清單 (連線篩選) ，以及反垃圾郵件原則中的允許的寄件者清單或允許的網域清單。</span><span class="sxs-lookup"><span data-stu-id="81492-109">These options include Exchange mail flow rules (also known as transport rules), Outlook Safe Senders, the IP Allow List (connection filtering), and allowed sender lists or allowed domain lists in anti-spam policies.</span></span> <span data-ttu-id="81492-110">綜合，您可以將這些選項視為 _安全寄件者清單_。</span><span class="sxs-lookup"><span data-stu-id="81492-110">Collectively, you can think of these options as _safe sender lists_.</span></span>

<span data-ttu-id="81492-111">下列清單說明可用的安全寄件者清單，依從最高建議至最低建議的順序進行：</span><span class="sxs-lookup"><span data-stu-id="81492-111">The available safe sender lists are described in the following list in order from most recommended to least recommended:</span></span>

1. <span data-ttu-id="81492-112">郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="81492-112">Mail flow rules</span></span>
2. <span data-ttu-id="81492-113">Outlook 安全寄件者</span><span class="sxs-lookup"><span data-stu-id="81492-113">Outlook Safe Senders</span></span>
3. <span data-ttu-id="81492-114">IP 允許清單 (連線篩選) </span><span class="sxs-lookup"><span data-stu-id="81492-114">IP Allow List (connection filtering)</span></span>
4. <span data-ttu-id="81492-115"> (反垃圾郵件原則所允許的寄件者清單或允許的網域清單) </span><span class="sxs-lookup"><span data-stu-id="81492-115">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>

<span data-ttu-id="81492-116">郵件流程規則允許最大的彈性，以確保只允許正確的郵件。</span><span class="sxs-lookup"><span data-stu-id="81492-116">Mail flow rules allow the most flexibility to ensure that only the right messages are allowed.</span></span> <span data-ttu-id="81492-117">反垃圾郵件原則中的允許寄件者與允許的網域清單不如 IP 允許清單安全，因為寄件者的電子郵件網域很容易遭到欺騙。</span><span class="sxs-lookup"><span data-stu-id="81492-117">Allowed sender and allowed domain lists in anti-spam policies aren't as secure as the IP Allow List, because the sender's email domain is easily spoofed.</span></span> <span data-ttu-id="81492-118">不過，IP 允許清單也會帶來風險，因為從該 IP 位址傳送的 _任何_ 網域的電子郵件都會略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="81492-118">But, the IP Allow List also presents a risk, because email from _any_ domain that's sent from that IP address will bypass spam filtering.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="81492-119">請務必密切監視您使用安全寄件者清單對垃圾郵件篩選所進行的 *任何* 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="81492-119">Be careful to closely monitor *any* exceptions that you make to spam filtering using safe sender lists.</span></span>
>
> - <span data-ttu-id="81492-120">雖然您可以使用安全寄件者清單來協助誤報 (已標示為壞) 的良好電子郵件，但您應考慮使用安全寄件者清單做為暫時的解決方案，以盡可能避免使用。</span><span class="sxs-lookup"><span data-stu-id="81492-120">While you can use safe sender lists to help with false positives (good email marked as bad), you should consider the use of safe sender lists as a temporary solution that should be avoided if possible.</span></span> <span data-ttu-id="81492-121">建議您不要使用安全寄件者清單來管理誤報，因為垃圾郵件篩選例外會開啟您的組織，以進行欺騙和其他攻擊。</span><span class="sxs-lookup"><span data-stu-id="81492-121">We don't recommend managing false positives by using safe sender lists, because exceptions to spam filtering can open your organization to spoofing and other attacks.</span></span> <span data-ttu-id="81492-122">如果您堅持使用安全寄件者清單來管理誤報，您必須時刻警惕，讓主題在準備好時，讓主題 [向 Microsoft 報告訊息和](report-junk-email-messages-to-microsoft.md) 檔案。</span><span class="sxs-lookup"><span data-stu-id="81492-122">If you insist on using safe sender lists to manage false positives, you need to be vigilant and keep the topic [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md) at the ready.</span></span>
>
> - <span data-ttu-id="81492-123">若要讓網域傳送未驗證的電子郵件 (略過反欺騙保護) 但不略過反垃圾郵件和反惡意程式碼檢查，您可以將它新增至[AllowedToSpoof 安全寄件者清單](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="81492-123">To allow a domain to send unauthenticated email (bypass anti-spoofing protection) but not bypass anti-spam and anti-malware checks, you can add it to the [AllowedToSpoof safe sender list](walkthrough-spoof-intelligence-insight.md)</span></span>
>
> - <span data-ttu-id="81492-124">EOP 和 Outlook 會檢查不同的郵件內容，以判斷郵件的寄件者。</span><span class="sxs-lookup"><span data-stu-id="81492-124">EOP and Outlook inspect different message properties to determine the sender of the message.</span></span> <span data-ttu-id="81492-125">如需詳細資訊，請參閱本文稍後的「 [大量電子郵件](#considerations-for-bulk-email) 」一節的考慮。</span><span class="sxs-lookup"><span data-stu-id="81492-125">For more information, see the [Considerations for bulk email](#considerations-for-bulk-email) section later in this article.</span></span>

<span data-ttu-id="81492-126">相比之下，您也有數個選項可以封鎖使用 _封鎖的寄件者清單_ 來自特定來源的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="81492-126">In contrast, you also have several options to block email from specific sources using _blocked sender lists_.</span></span> <span data-ttu-id="81492-127">如需詳細資訊，請參閱[在 EOP 中建立封鎖寄件者清單](create-block-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="81492-127">For more information, see [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="recommended-use-mail-flow-rules"></a><span data-ttu-id="81492-128">建議的 () 使用郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="81492-128">(Recommended) Use mail flow rules</span></span>

<span data-ttu-id="81492-129">Exchange Online 和獨立 EOP 中的郵件流程規則使用條件和例外來識別郵件，以及指定應對這些郵件執行的動作。</span><span class="sxs-lookup"><span data-stu-id="81492-129">Mail flow rules in Exchange Online and standalone EOP use conditions and exceptions to identify messages, and actions to specify what should be done to those messages.</span></span> <span data-ttu-id="81492-130">如需詳細資訊，請參閱 [Mail flow rules (transport rules) In Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="81492-130">For more information, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>

<span data-ttu-id="81492-131">下列範例假設您需要 contoso.com 中的電子郵件，以略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="81492-131">The following example assumes you need email from contoso.com to skip spam filtering.</span></span> <span data-ttu-id="81492-132">若要這麼做，請設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81492-132">To do this, configure the following settings:</span></span>

1. <span data-ttu-id="81492-133">**條件**： **寄件者** \> **網域為** \> contoso.com。</span><span class="sxs-lookup"><span data-stu-id="81492-133">**Condition**: **The sender** \> **domain is** \> contoso.com.</span></span>

2. <span data-ttu-id="81492-134">設定下列其中一個設定：</span><span class="sxs-lookup"><span data-stu-id="81492-134">Configure either of the following settings:</span></span>

   - <span data-ttu-id="81492-135">**郵件流程規則條件**： **郵件頭** \> **包含下列任何字** \> **標頭名稱**： `Authentication-Results` \> **標頭值**： `dmarc=pass` 或 `dmarc=bestguesspass` 。</span><span class="sxs-lookup"><span data-stu-id="81492-135">**Mail flow rule condition**: **A message header** \> **includes any of these words** \> **Header name**: `Authentication-Results` \> **Header value**: `dmarc=pass` or `dmarc=bestguesspass`.</span></span>

     <span data-ttu-id="81492-136">此條件會檢查傳送電子郵件網域的電子郵件驗證狀態，以確定傳送網域未遭到欺騙。</span><span class="sxs-lookup"><span data-stu-id="81492-136">This condition checks the email authentication status of the sending email domain to ensure that the sending domain is not being spoofed.</span></span> <span data-ttu-id="81492-137">如需有關電子郵件驗證的詳細資訊，請參閱 [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [DKIM](use-dkim-to-validate-outbound-email.md)及 [DMARC](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="81492-137">For more information about email authentication, see [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

   - <span data-ttu-id="81492-138">**IP 允許清單**：在連線篩選原則中指定來源 IP 位址或位址範圍。</span><span class="sxs-lookup"><span data-stu-id="81492-138">**IP Allow List**: Specify the source IP address or address range in the connection filter policy.</span></span>

     <span data-ttu-id="81492-139">若寄送網域未使用電子郵件驗證，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="81492-139">Use this setting if the sending domain does not use email authentication.</span></span> <span data-ttu-id="81492-140">在 IP 允許清單中的來源 IP 位址到來時，請盡可能具有限制性。</span><span class="sxs-lookup"><span data-stu-id="81492-140">Be as restrictive as possible when it comes to the source IP addresses in the IP Allow List.</span></span> <span data-ttu-id="81492-141">建議的 IP 位址範圍為/24 或更少 () 越好。</span><span class="sxs-lookup"><span data-stu-id="81492-141">We recommend an IP address range of /24 or less (less is better).</span></span> <span data-ttu-id="81492-142">請勿使用屬於消費者服務的 IP 位址範圍 (例如，outlook.com) 或共用基礎結構。</span><span class="sxs-lookup"><span data-stu-id="81492-142">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

   > [!IMPORTANT]
   >
   > - <span data-ttu-id="81492-143">永遠不 *會將發* 件人網域的郵件流程規則設定為略過垃圾郵件篩選的條件。</span><span class="sxs-lookup"><span data-stu-id="81492-143">Never configure mail flow rules with *only* the sender domain as the condition to skip spam filtering.</span></span> <span data-ttu-id="81492-144">這樣做會 *大幅* 增加攻擊者欺騙傳送網域的可能性 (或模擬完整的電子郵件地址) 、略過所有垃圾郵件篩選，並略過寄件者驗證檢查，使郵件會到達收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="81492-144">Doing so will *significantly* increase the likelihood that attackers can spoof the sending domain (or impersonate the full email address), skip all spam filtering, and skip sender authentication checks so the message will arrive in the recipient's Inbox.</span></span>
   >
   > - <span data-ttu-id="81492-145">請勿使用您擁有的網域 (又稱為公認的網域) 或流行的網域 (例如，microsoft.com) 為郵件流程規則中的條件。</span><span class="sxs-lookup"><span data-stu-id="81492-145">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) as conditions in mail flow rules.</span></span> <span data-ttu-id="81492-146">這樣做會將其視為高風險，因為它會產生機會讓攻擊者傳送本來會進行篩選的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="81492-146">Doing so is considered high risk because it creates opportunities for attackers to send email that would otherwise be filtered.</span></span>
   >
   > - <span data-ttu-id="81492-147">如果您允許在網路位址轉譯之後的 IP 位址 (NAT) 閘道，您必須知道 NAT 集區所涉及的伺服器，才能知道您的 IP 允許清單的範圍。</span><span class="sxs-lookup"><span data-stu-id="81492-147">If you allow an IP address that's behind a network address translation (NAT) gateway, you need to know the servers that are involved in the NAT pool in order to know the scope of your IP Allow List.</span></span> <span data-ttu-id="81492-148">IP 位址和 NAT 參與者可以變更。</span><span class="sxs-lookup"><span data-stu-id="81492-148">IP addresses and NAT participants can change.</span></span> <span data-ttu-id="81492-149">您必須定期檢查您的 IP 允許清單專案，以作為標準維護程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="81492-149">You need to periodically check your IP Allow List entries as part of your standard maintenance procedures.</span></span>

3. <span data-ttu-id="81492-150">**選用的條件**：</span><span class="sxs-lookup"><span data-stu-id="81492-150">**Optional conditions**:</span></span>

   - <span data-ttu-id="81492-151">**寄件者** \>**內部/外部** \>**組織外部**：此為隱含條件，但可使用它來考慮可能未正確設定的內部部署電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="81492-151">**The sender** \> **is internal/external** \> **Outside the organization**: This condition is implicit, but it's OK to use it to account for on-premises email servers that might not be correctly configured.</span></span>

   - <span data-ttu-id="81492-152">**主語或** \> 本文主旨 **或本文包含任何這些字詞** \>\<keywords\>：如果您可以透過主旨行或郵件內文中的關鍵字或片語來進一步限制郵件，您可以使用這些字做為條件。</span><span class="sxs-lookup"><span data-stu-id="81492-152">**The subject or body** \> **subject or body includes any of these words** \> \<keywords\>: If you can further restrict the messages by keywords or phrases in the subject line or message body, you can use those words as a condition.</span></span>

4. <span data-ttu-id="81492-153">**動作**：在規則中設定這兩項動作：</span><span class="sxs-lookup"><span data-stu-id="81492-153">**Action**: Configure both of these actions in the rule:</span></span>

   <span data-ttu-id="81492-154">a.</span><span class="sxs-lookup"><span data-stu-id="81492-154">a.</span></span> <span data-ttu-id="81492-155">**修改郵件屬性** \>**將垃圾郵件信賴等級設定 (SCL)** \>**略過垃圾郵件篩選**。</span><span class="sxs-lookup"><span data-stu-id="81492-155">**Modify the message properties** \> **set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

   <span data-ttu-id="81492-156">b.</span><span class="sxs-lookup"><span data-stu-id="81492-156">b.</span></span> <span data-ttu-id="81492-157">**修改郵件屬性** \>**設定郵件頭**：**將郵件頭設定** \<CustomHeaderName\> **為值** \<CustomHeaderValue\> 。</span><span class="sxs-lookup"><span data-stu-id="81492-157">**Modify the message properties** \> **set a message header**: **Set the message header** \<CustomHeaderName\> **to the value** \<CustomHeaderValue\>.</span></span>

      <span data-ttu-id="81492-158">例如，`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`。</span><span class="sxs-lookup"><span data-stu-id="81492-158">For example, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`.</span></span> <span data-ttu-id="81492-159">如果規則中有多個網域，您可以視需要自訂標頭文字。</span><span class="sxs-lookup"><span data-stu-id="81492-159">If you have more than one domain in the rule, you can customize the header text as appropriate.</span></span>

      <span data-ttu-id="81492-160">當郵件由於郵件流程規則而略過垃圾郵件篩選時，value `SFV:SKN` 值會在 **X-Forefront-Antispam-Report** 標頭中戳。</span><span class="sxs-lookup"><span data-stu-id="81492-160">When a message skips spam filtering due to a mail flow rule, the value `SFV:SKN` value is stamped in the **X-Forefront-Antispam-Report** header.</span></span> <span data-ttu-id="81492-161">如果郵件來自 IP 允許清單上的來源， `IPV:CAL` 也會新增此值。</span><span class="sxs-lookup"><span data-stu-id="81492-161">If the message is from a source that's on the IP Allow List, the value `IPV:CAL` is also added.</span></span> <span data-ttu-id="81492-162">這些值可協助您進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="81492-162">These values can help you with troubleshooting.</span></span>

![EAC 中的郵件流程規則設定，以略過垃圾郵件篩選。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a><span data-ttu-id="81492-164">使用 Outlook 安全寄件者</span><span class="sxs-lookup"><span data-stu-id="81492-164">Use Outlook Safe Senders</span></span>

> [!CAUTION]
> <span data-ttu-id="81492-165">這種方法會帶來極高的風險，讓攻擊者成功將電子郵件傳遞至收件匣，否則會加以篩選。不過，使用者的安全寄件者或安全網域清單不會防止惡意程式碼或高可信度網路釣魚郵件被篩選出來。</span><span class="sxs-lookup"><span data-stu-id="81492-165">This method creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered; however, the user's Safe Senders or Safe Domains lists don't prevent malware or high confidence phishing messages from being filtered.</span></span>

<span data-ttu-id="81492-166">使用者或系統管理員可以將寄件者電子郵件地址新增至信箱中的安全寄件者清單，而不是組織設定。</span><span class="sxs-lookup"><span data-stu-id="81492-166">Instead of an organizational setting, users or admins can add the sender email addresses to the Safe Senders list in the mailbox.</span></span> <span data-ttu-id="81492-167">如需相關指示，請參閱 [在 Office 365 中設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="81492-167">For instructions, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span> <span data-ttu-id="81492-168">在大多數情況下，這不是必要的，因為寄件者會略過部分的篩選堆疊。</span><span class="sxs-lookup"><span data-stu-id="81492-168">This is not desirable in most situations since senders will bypass parts of the filtering stack.</span></span> <span data-ttu-id="81492-169">雖然您信任寄件者，但仍然可以危及寄件者，並會傳送惡意內容。</span><span class="sxs-lookup"><span data-stu-id="81492-169">Although you trust the sender, the sender can still be compromised and send malicious content.</span></span> <span data-ttu-id="81492-170">您最好讓篩選器執行每封郵件檢查所需的動作，然後在篩選器有錯誤時， [向 Microsoft 報告 false 肯定/負數](report-junk-email-messages-to-microsoft.md) 。</span><span class="sxs-lookup"><span data-stu-id="81492-170">It is best that you let our filters do what is needed to check every message and then [report the false positive/negative to Microsoft](report-junk-email-messages-to-microsoft.md) if our filters got it wrong.</span></span> <span data-ttu-id="81492-171">略過篩選堆疊也會干擾 [ZAP](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="81492-171">Bypassing the filtering stack also interferes with [ZAP](zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="81492-172">當郵件因使用者的安全寄件者清單而略過垃圾郵件篩選時， **X-Forefront-Antispam-Report** 標頭欄位將會包含此值 `SFV:SFE` ，表示已略過篩選垃圾郵件、欺騙和網路釣魚。</span><span class="sxs-lookup"><span data-stu-id="81492-172">When messages skip spam filtering due to a user's Safe Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:SFE`, which indicates that filtering for spam, spoof, and phishing were bypassed.</span></span>

## <a name="use-the-ip-allow-list"></a><span data-ttu-id="81492-173">使用 IP 允許清單</span><span class="sxs-lookup"><span data-stu-id="81492-173">Use the IP Allow List</span></span>

<span data-ttu-id="81492-174">如先前所述，您無法使用郵件流程規則，下一個最佳選項是將來源電子郵件伺服器或伺服器新增至連線篩選原則中的 IP 允許清單。</span><span class="sxs-lookup"><span data-stu-id="81492-174">If you can't use mail flow rules as previously described, the next best option is to add the source email server or servers to the IP Allow List in the connection filter policy.</span></span> <span data-ttu-id="81492-175">如需詳細資訊，請參閱 [Configure connection 篩選 IN EOP](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="81492-175">For details, see [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

<span data-ttu-id="81492-176">**附註**：</span><span class="sxs-lookup"><span data-stu-id="81492-176">**Notes**:</span></span>

- <span data-ttu-id="81492-177">請務必將允許的 IP 位址數目維持在最低限度，以免盡可能避免使用整個 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="81492-177">It's important that you keep the number of allowed IP addresses to a minimum, so avoid using entire IP address ranges whenever possible.</span></span>

- <span data-ttu-id="81492-178">請勿使用屬於消費者服務的 IP 位址範圍 (例如，outlook.com) 或共用基礎結構。</span><span class="sxs-lookup"><span data-stu-id="81492-178">Do not use IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures.</span></span>

- <span data-ttu-id="81492-179">請定期查看 IP 允許清單中的專案，並移除您不再需要的專案。</span><span class="sxs-lookup"><span data-stu-id="81492-179">Regularly review the entries in the IP Allow List and remove the entries that you no longer need.</span></span>

> [!CAUTION]
> <span data-ttu-id="81492-180">若未進行其他驗證，像是郵件流程規則，來自 IP 允許清單來源的電子郵件會略過垃圾郵件篩選和寄件者驗證 (SPF、DKIM、DMARC) 檢查。</span><span class="sxs-lookup"><span data-stu-id="81492-180">Without additional verification like mail flow rules, email from sources in the IP Allow List skips spam filtering and sender authentication (SPF, DKIM, DMARC) checks.</span></span> <span data-ttu-id="81492-181">這會帶來極高的駭客成功將電子郵件傳遞至收件匣的高風險，否則會加以篩選。不過，IP 允許清單並不會防止惡意程式碼或高可信度網路釣魚郵件被篩選出來。</span><span class="sxs-lookup"><span data-stu-id="81492-181">This creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered; however, the IP Allow List doesn't prevent malware or high confidence phishing messages from being filtered.</span></span>

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a><span data-ttu-id="81492-182">使用允許的寄件者清單或允許的網域清單</span><span class="sxs-lookup"><span data-stu-id="81492-182">Use allowed sender lists or allowed domain lists</span></span>

<span data-ttu-id="81492-183">最不可取的選項是使用反垃圾郵件原則中的允許寄件者清單或允許的網域清單。</span><span class="sxs-lookup"><span data-stu-id="81492-183">The least desirable option is to use the allowed sender list or allowed domain list in anti-spam policies.</span></span> <span data-ttu-id="81492-184">您應 *盡可能* 避免此選項，因為寄件者略過所有垃圾郵件、欺騙和網路釣魚防護，而寄件者驗證 (SPF、DKIM、DMARC) 。</span><span class="sxs-lookup"><span data-stu-id="81492-184">You should avoid this option *if at all possible* because senders bypass all spam, spoof, and phishing protection, and sender authentication (SPF, DKIM, DMARC).</span></span> <span data-ttu-id="81492-185">這個方法最適合用來進行暫時測試。</span><span class="sxs-lookup"><span data-stu-id="81492-185">This method is best used for temporary testing only.</span></span> <span data-ttu-id="81492-186">您可以在 EOP 主題中的 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md) 中找到詳細步驟。</span><span class="sxs-lookup"><span data-stu-id="81492-186">The detailed steps can be found in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md) topic.</span></span>

<span data-ttu-id="81492-187">這兩個清單的上限大約是1000個專案;不過，您只可以將30個專案輸入入口網站。</span><span class="sxs-lookup"><span data-stu-id="81492-187">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="81492-188">您必須使用 PowerShell 來新增超過30個專案。</span><span class="sxs-lookup"><span data-stu-id="81492-188">You must use PowerShell to add more than 30 entries.</span></span>

> [!CAUTION]
>
> - <span data-ttu-id="81492-189">這種方法會帶來極高的風險，讓攻擊者成功將電子郵件傳遞至收件匣，否則會加以篩選。不過，允許的寄件者或允許的網域清單不會防止惡意程式碼或高可信度網路釣魚郵件被篩選出來。</span><span class="sxs-lookup"><span data-stu-id="81492-189">This method creates a high risk of attackers successfully delivering email to the Inbox that would otherwise be filtered; however, the allowed senders or allowed domains lists don't prevent malware or high confidence phishing messages from being filtered.</span></span>
>
> - <span data-ttu-id="81492-190">請勿使用您擁有的網域 (又稱為公認的網域) 或流行的網域 (例如，允許的網域清單中的 microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="81492-190">Do not use domains you own (also known as accepted domains) or popular domains (for example, microsoft.com) in allowed domain lists.</span></span>

## <a name="considerations-for-bulk-email"></a><span data-ttu-id="81492-191">大量電子郵件的考慮</span><span class="sxs-lookup"><span data-stu-id="81492-191">Considerations for bulk email</span></span>

<span data-ttu-id="81492-192">標準 SMTP 電子郵件由「郵件信封」(Message Envelope) 和郵件內容組成。</span><span class="sxs-lookup"><span data-stu-id="81492-192">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="81492-193">郵件信封包含在 SMTP 伺服器之間傳輸及傳遞郵件所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="81492-193">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="81492-194">郵件內容包含統稱為 (「郵件標頭」) 的郵件標頭欄位和郵件內容。</span><span class="sxs-lookup"><span data-stu-id="81492-194">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="81492-195">RFC 5321 會說明郵件信封，而 RFC 5322 中說明郵件頭。</span><span class="sxs-lookup"><span data-stu-id="81492-195">The message envelope is described in RFC 5321, and the message header is described in RFC 5322.</span></span> <span data-ttu-id="81492-196">收件者永遠不會看到實際的郵件信封，因為它是由郵件傳輸程式所產生，而且實際上不是郵件的一部分。</span><span class="sxs-lookup"><span data-stu-id="81492-196">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="81492-197">此 `5321.MailFrom` 位址 (也稱為「 **郵件來自** 位址」、「P1 寄件者」或「信封寄件者」) 是在郵件的 SMTP 傳輸中使用的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="81492-197">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="81492-198">這個電子郵件地址通常會記錄在郵件頭的 [傳回 **路徑** 標頭] 欄位中 (不過，寄件者可能會指定不同的傳回 **路徑** 電子郵件地址) 。</span><span class="sxs-lookup"><span data-stu-id="81492-198">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span> <span data-ttu-id="81492-199">如果無法傳遞郵件，表示未傳遞回報的收件者 (也稱為 NDR 或退回郵件) 。</span><span class="sxs-lookup"><span data-stu-id="81492-199">If the message can't be delivered, it's the recipient for the non-delivery report (also known as an NDR or bounce message).</span></span>

- <span data-ttu-id="81492-200">`5322.From` (也稱為 **from** address 或 P2 sender) 是電子郵件地址 **的收** 件者標頭欄位，也就是顯示在電子郵件客戶程式中的寄件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="81492-200">The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span>

<span data-ttu-id="81492-201">通常， `5321.MailFrom` 與 `5322.From` 位址 (人員對人員通訊) 相同。</span><span class="sxs-lookup"><span data-stu-id="81492-201">Frequently, the `5321.MailFrom` and `5322.From` addresses are the same (person-to-person communication).</span></span> <span data-ttu-id="81492-202">不過，當您代表其他人傳送電子郵件時，位址可能會不同。</span><span class="sxs-lookup"><span data-stu-id="81492-202">However, when email is sent on behalf of someone else, the addresses can be different.</span></span> <span data-ttu-id="81492-203">這通常是大量電子郵件訊息的情形。</span><span class="sxs-lookup"><span data-stu-id="81492-203">This happens most often for bulk email messages.</span></span>

<span data-ttu-id="81492-204">例如，假設「藍色 Yonder 航空公司」已雇用瑪姬旅行社傳送電子郵件廣告。</span><span class="sxs-lookup"><span data-stu-id="81492-204">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="81492-205">您在 [收件匣] 中收到的訊息具有下列屬性：</span><span class="sxs-lookup"><span data-stu-id="81492-205">The message you receive in your Inbox has the following properties:</span></span>

- <span data-ttu-id="81492-206">`5321.MailFrom`位址是 blueyonder.airlines@margiestravel.com。</span><span class="sxs-lookup"><span data-stu-id="81492-206">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="81492-207">`5322.From`位址是 blueyonder@news.blueyonderairlines.com，這是您在 Outlook 中看到的內容。</span><span class="sxs-lookup"><span data-stu-id="81492-207">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="81492-208">EOP 中的反垃圾郵件原則中的安全寄件者清單和安全網域清單僅檢查 `5322.From` 位址，這類似使用該位址的 Outlook 安全寄件者 `5322.From` 。</span><span class="sxs-lookup"><span data-stu-id="81492-208">Safe sender lists and safe domain lists in anti-spam policies in EOP inspect only the `5322.From` addresses, this is similar to Outlook Safe Senders that uses the `5322.From` address.</span></span>

<span data-ttu-id="81492-209">若要防止郵件被篩選，您可以採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="81492-209">To prevent this message from being filtered, you can take the following steps:</span></span>

- <span data-ttu-id="81492-210">新增 blueyonder@news.blueyonderairlines.com (`5322.From`) 為 Outlook 安全寄件者的位址。</span><span class="sxs-lookup"><span data-stu-id="81492-210">Add blueyonder@news.blueyonderairlines.com (the `5322.From` address) as an Outlook Safe Sender.</span></span>

- <span data-ttu-id="81492-211">[使用郵件流程規則](#recommended-use-mail-flow-rules) ，條件是尋找來自 blueyonder@news.blueyonderairlines.com (`5322.From` 位址、Blueyonder.airlines@margiestravel.com (`5321.MailFrom`) 或兩者的郵件。</span><span class="sxs-lookup"><span data-stu-id="81492-211">[Use a mail flow rule](#recommended-use-mail-flow-rules) with a condition that looks for messages from blueyonder@news.blueyonderairlines.com (the `5322.From` address, blueyonder.airlines@margiestravel.com (the `5321.MailFrom`), or both.</span></span>

<span data-ttu-id="81492-212">如需詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="81492-212">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>
