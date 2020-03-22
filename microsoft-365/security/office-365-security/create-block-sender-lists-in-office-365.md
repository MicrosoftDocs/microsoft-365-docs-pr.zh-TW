---
title: 在 Office 365 中建立封鎖的寄件者清單
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
- MET150s
description: 系統管理員可以深入瞭解 Office 365 和 EOP 中可用的選項，以封鎖輸入郵件。
ms.openlocfilehash: a588c9c869dae39ab60fc7ad68b6496f57ae015a
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893859"
---
# <a name="create-blocked-sender-lists-in-office-365"></a><span data-ttu-id="12498-103">在 Office 365 中建立封鎖的寄件者清單</span><span class="sxs-lookup"><span data-stu-id="12498-103">Create blocked sender lists in Office 365</span></span>

<span data-ttu-id="12498-104">如果您是 Office 365 客戶的信箱位於 Exchange Online 或獨立 Exchange Online Protection （EOP）客戶，但沒有 Exchange Online 信箱，EOP 會提供多種方式，封鎖來自不想要的寄件者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="12498-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP offers multiple ways of blocking email from unwanted senders.</span></span> <span data-ttu-id="12498-105">這些選項包括 Outlook 封鎖的寄件者、封鎖的寄件者清單或反垃圾郵件原則中的封鎖網域清單、Exchange 郵件流程規則（也稱為傳輸規則）和 IP 封鎖清單（連線篩選）。</span><span class="sxs-lookup"><span data-stu-id="12498-105">These options include Outlook Blocked Senders, blocked sender lists or blocked domain lists in anti-spam policies, Exchange mail flow rules (also known as transport rules), and the IP Block List (connection filtering).</span></span> <span data-ttu-id="12498-106">綜合，您可以將這些選項視為_封鎖的寄件者清單_。</span><span class="sxs-lookup"><span data-stu-id="12498-106">Collectively, you can think of these options as _blocked sender lists_.</span></span>

<span data-ttu-id="12498-107">封鎖寄件者的最佳方法會因影響範圍而異。</span><span class="sxs-lookup"><span data-stu-id="12498-107">The best method to block senders varies on the scope of impact.</span></span> <span data-ttu-id="12498-108">針對單一使用者，正確的解決方案可能是 Outlook 封鎖的寄件者。</span><span class="sxs-lookup"><span data-stu-id="12498-108">For a single user, the right solution could be Outlook Blocked Senders.</span></span> <span data-ttu-id="12498-109">對於許多使用者而言，其中一個其他選項更適合。</span><span class="sxs-lookup"><span data-stu-id="12498-109">For many users, one of the other options would be more appropriate.</span></span> <span data-ttu-id="12498-110">下列選項依影響範圍及廣度排名。</span><span class="sxs-lookup"><span data-stu-id="12498-110">The following options are ranked by both impact scope and breadth.</span></span> <span data-ttu-id="12498-111">清單從窄到寬，但閱讀完整建議的*詳細*資料。</span><span class="sxs-lookup"><span data-stu-id="12498-111">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

1. <span data-ttu-id="12498-112">Outlook 封鎖的寄件者（儲存于每個信箱的封鎖寄件者清單）</span><span class="sxs-lookup"><span data-stu-id="12498-112">Outlook Blocked Senders (the Blocked Senders list that's stored in each mailbox)</span></span>

2. <span data-ttu-id="12498-113">封鎖的寄件者清單或封鎖的網域清單（反垃圾郵件原則）</span><span class="sxs-lookup"><span data-stu-id="12498-113">Blocked sender lists or blocked domain lists (anti-spam policies)</span></span>

3. <span data-ttu-id="12498-114">Mai 流程規則</span><span class="sxs-lookup"><span data-stu-id="12498-114">Mai flow rules</span></span>

4. <span data-ttu-id="12498-115">IP 封鎖清單（連線篩選）</span><span class="sxs-lookup"><span data-stu-id="12498-115">The IP Block List (connection filtering)</span></span>

> [!NOTE]
> <span data-ttu-id="12498-116">雖然您可以使用全組織的封鎖設定來處理虛假的否定（未接的垃圾郵件），您也應該將這些郵件提交給 Microsoft 進行分析。</span><span class="sxs-lookup"><span data-stu-id="12498-116">While you can use organization-wide block settings to address false negatives (missed spam), you should also submit those messages to Microsoft for analysis.</span></span> <span data-ttu-id="12498-117">使用封鎖清單來管理 false 負片會大幅增加您的管理額外負荷。</span><span class="sxs-lookup"><span data-stu-id="12498-117">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="12498-118">如果您使用封鎖清單來轉移未接的垃圾郵件，您必須在準備時保留將[垃圾郵件、非垃圾郵件和網路釣魚詐騙郵件提交給 Microsoft 進行分析](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)的主題。</span><span class="sxs-lookup"><span data-stu-id="12498-118">If you use block lists to deflect missed spam, you need to keep the topic for [submitting spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), at the ready.</span></span>

<span data-ttu-id="12498-119">相比之下，您也可以使用_安全寄件者清單_，讓您有數個選項永遠允許來自特定來源的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="12498-119">In contrast, you also have several options to always allow email from specific sources using _safe sender lists_.</span></span> <span data-ttu-id="12498-120">如需詳細資訊，請參閱[在 Office 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="12498-120">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="12498-121">使用 Outlook 封鎖的寄件者</span><span class="sxs-lookup"><span data-stu-id="12498-121">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="12498-122">當只有少量的使用者收到不想要的電子郵件時，使用者或系統管理員可以將寄件者電子郵件地址新增至信箱中的封鎖寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="12498-122">When only a small number of users received unwanted email, users or admins can add the sender email addresses to the Blocked Senders list in the mailbox.</span></span> <span data-ttu-id="12498-123">如需相關指示，請參閱[在 Office 365 中設定 Exchange Online 信箱上的垃圾郵件設定](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="12498-123">For instructions, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

<span data-ttu-id="12498-124">當郵件因使用者的封鎖寄件者清單而成功封鎖時， **X-Forefront-Antispam-Report**標頭欄位將會包含`SFV:BLK`此值。</span><span class="sxs-lookup"><span data-stu-id="12498-124">When messages are successfully blocked due to a user's Blocked Senders list, the **X-Forefront-Antispam-Report** header field will contain the value `SFV:BLK`.</span></span>

> [!NOTE]
> <span data-ttu-id="12498-125">如果不想要的郵件是來自可信和辨識來源的簡報，請從電子郵件取消訂閱，以停止使用者接收郵件。</span><span class="sxs-lookup"><span data-stu-id="12498-125">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from receiving the messages.</span></span>

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a><span data-ttu-id="12498-126">使用封鎖的寄件者清單或封鎖的網域清單</span><span class="sxs-lookup"><span data-stu-id="12498-126">Use blocked sender lists or blocked domain lists</span></span>

<span data-ttu-id="12498-127">當多個使用者受到影響時，範圍會變寬，所以下一個最佳選項是反垃圾郵件原則中的封鎖寄件者清單或封鎖的網域清單。</span><span class="sxs-lookup"><span data-stu-id="12498-127">When multiple users are affected, the scope is wider, so the next best option is blocked sender lists or blocked domain lists in anti-spam policies.</span></span> <span data-ttu-id="12498-128">來自清單寄件者的郵件會標示為**垃圾**郵件，而您針對**垃圾郵件**篩選判定所設定的動作會針對郵件採取。</span><span class="sxs-lookup"><span data-stu-id="12498-128">Messages from senders on the lists are marked as **Spam**, and the action that you've configured for the **Spam** filter verdict is taken on the message.</span></span> <span data-ttu-id="12498-129">如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="12498-129">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="12498-130">這兩個清單的上限大約是1000個專案;不過，您只可以將30個專案輸入入口網站。</span><span class="sxs-lookup"><span data-stu-id="12498-130">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="12498-131">您必須使用 PowerShell 來新增超過30個專案。</span><span class="sxs-lookup"><span data-stu-id="12498-131">You need to use PowerShell to add more than 30 entries.</span></span>

## <a name="use-mail-flow-rules"></a><span data-ttu-id="12498-132">使用郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="12498-132">Use mail flow rules</span></span>

<span data-ttu-id="12498-133">如果您需要封鎖傳送給特定使用者或整個組織內的郵件，您可以使用郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="12498-133">If you need to block messages that are sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="12498-134">郵件流程規則比封鎖寄件者清單或封鎖的寄件者網域清單更為靈活，因為它們也可以在不想要的郵件中尋找關鍵字或其他屬性。</span><span class="sxs-lookup"><span data-stu-id="12498-134">Mail flow rules are more flexible than block sender lists or blocked sender domain lists because they can also look for keywords or other properties in the unwanted messages.</span></span>

<span data-ttu-id="12498-135">不論您用來識別郵件的條件或例外情況為何，您可以將動作設定為將郵件的垃圾郵件信賴等級（SCL）設定為9，這會將郵件標示為**高信賴的垃圾**郵件。</span><span class="sxs-lookup"><span data-stu-id="12498-135">Regardless of the conditions or exceptions that you use to identify the messages, you configure the action to set the spam confidence level (SCL) of the message to 9, which marks the message a **High confidence spam**.</span></span> <span data-ttu-id="12498-136">如需詳細資訊，請參閱[使用郵件流程規則設定郵件中的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="12498-136">For more information, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12498-137">您可以輕鬆地建立*過於*嚴格的規則，所以請務必只使用特別的準則來識別您想要封鎖的郵件。</span><span class="sxs-lookup"><span data-stu-id="12498-137">It's easy to create rules that are *overly* aggressive, so it's important that you identify only the messages you want to block using using very specific criteria.</span></span> <span data-ttu-id="12498-138">此外，請務必啟用規則的審計，並測試規則的結果，以確保所有內容如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="12498-138">Also, be sure to enable auditing on the rule and test the results of the rule to ensure everything works as expected.</span></span>

## <a name="use-the-ip-block-list"></a><span data-ttu-id="12498-139">使用 IP 封鎖清單</span><span class="sxs-lookup"><span data-stu-id="12498-139">Use the IP Block List</span></span>

<span data-ttu-id="12498-140">當您無法使用其他其中一個選項來封鎖寄件者時，*只*應該使用連線篩選原則中的 IP 封鎖清單。</span><span class="sxs-lookup"><span data-stu-id="12498-140">When it's not possible to use one of the other options to block a sender, *only then* should you use the IP Block List in the connection filter policy.</span></span> <span data-ttu-id="12498-141">如需詳細資訊，請參閱[設定連線篩選原則](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="12498-141">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="12498-142">務必將封鎖的 Ip 數目維持在最小值，因此*不*建議封鎖整個 IP 位址範圍。</span><span class="sxs-lookup"><span data-stu-id="12498-142">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="12498-143">您應*特別*避免新增屬於消費者服務（例如，outlook.com）或共用基礎結構的 IP 位址範圍，並確定您檢查封鎖的 ip 地址清單以作為定期維護的一部分。</span><span class="sxs-lookup"><span data-stu-id="12498-143">You should *especially* avoid adding IP address ranges that belong to consumer services (for example, outlook.com) or shared infrastructures, and also ensure that you review the list of blocked IP addresses as part of regular maintenance.</span></span>
