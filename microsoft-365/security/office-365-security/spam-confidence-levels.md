---
title: 垃圾郵件信賴等級
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
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解在 Exchange Online Protection (EOP) 中套用至郵件的垃圾郵件信賴等級 (SCL) 。
ms.openlocfilehash: 7e8d706f89c5b16bd34ad074498e011dc5d74093
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656536"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="1b645-103">EOP 中的垃圾郵件信賴等級 (SCL) </span><span class="sxs-lookup"><span data-stu-id="1b645-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="1b645-104">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，輸入郵件會透過 EOP 中的垃圾郵件篩選，並獲指派垃圾郵件分數。</span><span class="sxs-lookup"><span data-stu-id="1b645-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="1b645-105">該分數對應于個別垃圾郵件信賴等級， (SCL) 新增至 X 標頭中的郵件。</span><span class="sxs-lookup"><span data-stu-id="1b645-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="1b645-106">較高的 SCL 表示郵件可能是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="1b645-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="1b645-107">EOP 會根據 SCL 對郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="1b645-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="1b645-108">下表說明 SCL 的含義和郵件所採取的預設動作。</span><span class="sxs-lookup"><span data-stu-id="1b645-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="1b645-109">如需根據垃圾郵件篩選判定，可對郵件採取之動作的詳細資訊，請參閱在[EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1b645-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="1b645-110">SCL</span><span class="sxs-lookup"><span data-stu-id="1b645-110">SCL</span></span>|<span data-ttu-id="1b645-111">定義</span><span class="sxs-lookup"><span data-stu-id="1b645-111">Definition</span></span>|<span data-ttu-id="1b645-112">預設動作</span><span class="sxs-lookup"><span data-stu-id="1b645-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="1b645-113">-1</span><span class="sxs-lookup"><span data-stu-id="1b645-113">-1</span></span>|<span data-ttu-id="1b645-114">郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="1b645-114">The message skipped spam filtering.</span></span> <span data-ttu-id="1b645-115">例如，郵件來自安全寄件者、傳送至安全收件者，或是來自 IP 允許清單上的電子郵件來源伺服器。</span><span class="sxs-lookup"><span data-stu-id="1b645-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="1b645-116">如需詳細資訊，請參閱[在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1b645-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="1b645-117">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="1b645-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="1b645-118">0、1</span><span class="sxs-lookup"><span data-stu-id="1b645-118">0, 1</span></span>|<span data-ttu-id="1b645-119">垃圾郵件篩選決定郵件不是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="1b645-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="1b645-120">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="1b645-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="1b645-121">5，6</span><span class="sxs-lookup"><span data-stu-id="1b645-121">5, 6</span></span>|<span data-ttu-id="1b645-122">垃圾郵件篩選標示郵件為**垃圾**郵件</span><span class="sxs-lookup"><span data-stu-id="1b645-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="1b645-123">將郵件傳遞至收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1b645-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="1b645-124">9 </span><span class="sxs-lookup"><span data-stu-id="1b645-124">9</span></span>|<span data-ttu-id="1b645-125">垃圾郵件篩選標示郵件為**高信賴垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="1b645-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="1b645-126">將郵件傳遞至收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="1b645-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="1b645-127">您會注意到 SCL 2、3、4、7和8不是由垃圾郵件篩選使用。</span><span class="sxs-lookup"><span data-stu-id="1b645-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="1b645-128">您可以使用郵件流程規則（也稱為傳輸規則）) 來加蓋郵件上的 SCL 的 (。</span><span class="sxs-lookup"><span data-stu-id="1b645-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="1b645-129">如果您使用郵件流程規則來設定 SCL，則值5或6會觸發垃圾郵件的垃圾郵件篩選**動作，而**值7、8或9會觸發垃圾郵件篩選動作，以取得**高信賴的垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="1b645-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="1b645-130">如需詳細資訊，請參閱[使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1b645-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="1b645-131">類似 SCL，大量投訴層級 (BCL) 識別錯誤的大量電子郵件 (也稱為_灰色郵件_) 。</span><span class="sxs-lookup"><span data-stu-id="1b645-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="1b645-132">較高的 BCL 表示大宗郵件訊息很可能會產生抱怨 (，因此很可能是) 的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="1b645-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="1b645-133">您可以在反垃圾郵件原則中設定 BCL 閾值。</span><span class="sxs-lookup"><span data-stu-id="1b645-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="1b645-134">如需詳細資訊，請參閱[設定 EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)、[大量投訴層級 (BCL) ) ](bulk-complaint-level-values.md)，以及[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="1b645-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="1b645-135">![LinkedIn 學習 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增至 Microsoft 365**的簡短圖示？</span><span class="sxs-lookup"><span data-stu-id="1b645-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="1b645-136">探索適用于**Microsoft 365 系統管理員和 IT 專業人員**的免費影片課程，並 LinkedIn 的知識。</span><span class="sxs-lookup"><span data-stu-id="1b645-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
