---
title: 垃圾郵件信賴等級
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解在 Exchange Online Protection (EOP) 中套用至郵件的垃圾郵件信賴等級 (SCL) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203460"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="e9a78-103">EOP 中的垃圾郵件信賴等級 (SCL) </span><span class="sxs-lookup"><span data-stu-id="e9a78-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="e9a78-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="e9a78-104">**Applies to**</span></span>
- [<span data-ttu-id="e9a78-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e9a78-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e9a78-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="e9a78-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e9a78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9a78-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e9a78-108">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，輸入郵件會透過 EOP 中的垃圾郵件篩選，並獲指派垃圾郵件分數。</span><span class="sxs-lookup"><span data-stu-id="e9a78-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="e9a78-109">該分數對應于個別垃圾郵件信賴等級， (SCL) 新增至 X 標頭中的郵件。</span><span class="sxs-lookup"><span data-stu-id="e9a78-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="e9a78-110">較高的 SCL 表示郵件可能是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e9a78-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="e9a78-111">EOP 會根據 SCL 對郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="e9a78-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="e9a78-112">下表說明 SCL 的含義和郵件所採取的預設動作。</span><span class="sxs-lookup"><span data-stu-id="e9a78-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="e9a78-113">如需根據垃圾郵件篩選判定，可對郵件採取之動作的詳細資訊，請參閱在 [EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a78-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="e9a78-114">SCL</span><span class="sxs-lookup"><span data-stu-id="e9a78-114">SCL</span></span>|<span data-ttu-id="e9a78-115">定義</span><span class="sxs-lookup"><span data-stu-id="e9a78-115">Definition</span></span>|<span data-ttu-id="e9a78-116">預設動作</span><span class="sxs-lookup"><span data-stu-id="e9a78-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="e9a78-117">-1</span><span class="sxs-lookup"><span data-stu-id="e9a78-117">-1</span></span>|<span data-ttu-id="e9a78-118">郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="e9a78-118">The message skipped spam filtering.</span></span> <span data-ttu-id="e9a78-119">例如，郵件來自安全寄件者、傳送至安全收件者，或是來自 IP 允許清單上的電子郵件來源伺服器。</span><span class="sxs-lookup"><span data-stu-id="e9a78-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="e9a78-120">如需詳細資訊，請參閱 [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a78-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="e9a78-121">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="e9a78-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="e9a78-122">0、1</span><span class="sxs-lookup"><span data-stu-id="e9a78-122">0, 1</span></span>|<span data-ttu-id="e9a78-123">垃圾郵件篩選決定郵件不是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="e9a78-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="e9a78-124">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="e9a78-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="e9a78-125">5，6</span><span class="sxs-lookup"><span data-stu-id="e9a78-125">5, 6</span></span>|<span data-ttu-id="e9a78-126">垃圾郵件篩選標示郵件為 **垃圾** 郵件</span><span class="sxs-lookup"><span data-stu-id="e9a78-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="e9a78-127">將郵件傳遞至收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e9a78-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="e9a78-128">9 </span><span class="sxs-lookup"><span data-stu-id="e9a78-128">9</span></span>|<span data-ttu-id="e9a78-129">垃圾郵件篩選標示郵件為 **高信賴垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="e9a78-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="e9a78-130">將郵件傳遞至收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e9a78-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="e9a78-131">您會注意到 SCL 2、3、4、7和8不是由垃圾郵件篩選使用。</span><span class="sxs-lookup"><span data-stu-id="e9a78-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="e9a78-132">您可以使用郵件流程規則（也稱為傳輸規則）) 來加蓋郵件上的 SCL 的 (。</span><span class="sxs-lookup"><span data-stu-id="e9a78-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="e9a78-133">如果您使用郵件流程規則來設定 SCL，則值5或6會觸發垃圾郵件的垃圾郵件篩選 **動作，而** 值7、8或9會觸發垃圾郵件篩選動作，以取得 **高信賴的垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="e9a78-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="e9a78-134">如需詳細資訊，請參閱[使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a78-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="e9a78-135">類似 SCL，大量投訴層級 (BCL) 識別錯誤的大量電子郵件 (也稱為 _灰色郵件_) 。</span><span class="sxs-lookup"><span data-stu-id="e9a78-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="e9a78-136">BCL 高，表示大量郵件訊息更容易引發抱怨 (因此更可能是垃圾郵件)。</span><span class="sxs-lookup"><span data-stu-id="e9a78-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="e9a78-137">您可以在反垃圾郵件原則中設定 BCL 閾值。</span><span class="sxs-lookup"><span data-stu-id="e9a78-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="e9a78-138">如需詳細資訊，請參閱 [設定 EOP 中的反垃圾郵件原則](configure-your-spam-filter-policies.md)、 [大量投訴層級 (BCL) ) ](bulk-complaint-level-values.md)，以及 [垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a78-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="e9a78-139">![LinkedIn 學習 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **新增至 Microsoft 365** 的簡短圖示？</span><span class="sxs-lookup"><span data-stu-id="e9a78-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="e9a78-140">探索適用于 **Microsoft 365 系統管理員和 IT 專業人員** 的免費影片課程，並 LinkedIn 的知識。</span><span class="sxs-lookup"><span data-stu-id="e9a78-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
