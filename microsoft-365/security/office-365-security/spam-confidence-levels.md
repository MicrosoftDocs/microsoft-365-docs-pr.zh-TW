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
description: 在本文中，系統管理員可以瞭解垃圾郵件信賴等級（SCL）如何判斷郵件的 likeliness 為垃圾郵件。
ms.openlocfilehash: 9448b1fd99878dbb85bc8699afc0719bc62dd951
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035245"
---
# <a name="spam-confidence-level-scl-in-office-365"></a><span data-ttu-id="f8a54-103">Office 365 中的垃圾郵件信賴等級（SCL）</span><span class="sxs-lookup"><span data-stu-id="f8a54-103">Spam confidence level (SCL) in Office 365</span></span>

<span data-ttu-id="f8a54-104">當 Microsoft 365 （Exchange Online 或獨立 Exchange online Protection （EOP）（沒有 Exchange Online 信箱）收到輸入電子郵件訊息時，郵件會透過垃圾郵件篩選功能，並被指派垃圾郵件分數。</span><span class="sxs-lookup"><span data-stu-id="f8a54-104">When Microsoft 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) receives an inbound email message, the message goes through spam filtering, and is assigned a spam score.</span></span> <span data-ttu-id="f8a54-105">該分數對應于個別垃圾郵件信賴等級（SCL），它會新增至 X 標頭中的郵件。</span><span class="sxs-lookup"><span data-stu-id="f8a54-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="f8a54-106">較高的 SCL 表示郵件可能是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="f8a54-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="f8a54-107">服務會根據 SCL 的郵件採取動作。</span><span class="sxs-lookup"><span data-stu-id="f8a54-107">The service takes action on the message based on the SCL.</span></span>

<span data-ttu-id="f8a54-108">下表說明 SCL 的含義和郵件所採取的預設動作。</span><span class="sxs-lookup"><span data-stu-id="f8a54-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="f8a54-109">如需根據垃圾郵件篩選判定，可對郵件採取之動作的詳細資訊，請參閱 Configure the anti-spam[原則 In Office 365](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f8a54-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

||||
|:---:|---|---|
|<span data-ttu-id="f8a54-110">**SCL**</span><span class="sxs-lookup"><span data-stu-id="f8a54-110">**SCL**</span></span>|<span data-ttu-id="f8a54-111">**定義**</span><span class="sxs-lookup"><span data-stu-id="f8a54-111">**Definition**</span></span>|<span data-ttu-id="f8a54-112">**預設動作**</span><span class="sxs-lookup"><span data-stu-id="f8a54-112">**Default action**</span></span>|
|<span data-ttu-id="f8a54-113">-1</span><span class="sxs-lookup"><span data-stu-id="f8a54-113">-1</span></span>|<span data-ttu-id="f8a54-114">郵件略過垃圾郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="f8a54-114">The message skipped spam filtering.</span></span> <span data-ttu-id="f8a54-115">例如，郵件來自安全寄件者、傳送至安全收件者，或是來自 IP 允許清單上的電子郵件來源伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8a54-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="f8a54-116">如需詳細資訊，請參閱[在 Office 365 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f8a54-116">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="f8a54-117">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="f8a54-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f8a54-118">0、1</span><span class="sxs-lookup"><span data-stu-id="f8a54-118">0, 1</span></span>|<span data-ttu-id="f8a54-119">垃圾郵件篩選決定郵件不是垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="f8a54-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="f8a54-120">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="f8a54-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f8a54-121">5，6</span><span class="sxs-lookup"><span data-stu-id="f8a54-121">5, 6</span></span>|<span data-ttu-id="f8a54-122">垃圾郵件篩選標示郵件為**垃圾**郵件</span><span class="sxs-lookup"><span data-stu-id="f8a54-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="f8a54-123">將郵件傳遞至收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f8a54-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="f8a54-124">9 </span><span class="sxs-lookup"><span data-stu-id="f8a54-124">9</span></span>|<span data-ttu-id="f8a54-125">垃圾郵件篩選標示郵件為**高信賴垃圾郵件**</span><span class="sxs-lookup"><span data-stu-id="f8a54-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="f8a54-126">將郵件傳遞至收件者的 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f8a54-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="f8a54-127">您會注意到 SCL 2、3、4、7和8不是由垃圾郵件篩選使用。</span><span class="sxs-lookup"><span data-stu-id="f8a54-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="f8a54-128">您可以使用郵件流程規則（也稱為傳輸規則）來標記郵件上的 SCL。</span><span class="sxs-lookup"><span data-stu-id="f8a54-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="f8a54-129">如果您使用郵件流程規則來設定 SCL，則值5或6會觸發垃圾郵件的垃圾郵件篩選**動作，而**值7、8或9會觸發垃圾郵件篩選動作，以取得**高信賴的垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="f8a54-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="f8a54-130">如需詳細資訊，請參閱[使用郵件流程規則在郵件中設定垃圾郵件信賴等級 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f8a54-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="f8a54-131">類似 SCL，大量投訴層級（BCL）會識別錯誤的大量大量電子郵件（也稱為_灰色郵件_）。</span><span class="sxs-lookup"><span data-stu-id="f8a54-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="f8a54-132">較高的 BCL 表示大宗郵件訊息很可能會產生抱怨（因此可能是垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="f8a54-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="f8a54-133">您可以在反垃圾郵件原則中設定 BCL 閾值。</span><span class="sxs-lookup"><span data-stu-id="f8a54-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="f8a54-134">如需詳細資訊，請參閱設定 office 365 中的[反垃圾郵件原則](configure-your-spam-filter-policies.md)、[大量投訴層級（BCL）中的 office 365）](bulk-complaint-level-values.md)，以及[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。</span><span class="sxs-lookup"><span data-stu-id="f8a54-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in Office 365)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

||
|:-----|
|<span data-ttu-id="f8a54-135">![LinkedIn Learning 的短圖示](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="f8a54-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**</span></span>         <span data-ttu-id="f8a54-136">探索適用于**Microsoft 365 系統管理員和 IT 專業人員**的免費影片課程，並 LinkedIn 的知識。</span><span class="sxs-lookup"><span data-stu-id="f8a54-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
