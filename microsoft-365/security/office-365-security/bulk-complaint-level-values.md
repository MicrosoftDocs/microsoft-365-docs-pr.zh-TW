---
title: 大量投訴層級值
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解大量抱怨層級 (BCL) Exchange Online Protection (EOP) 中所用的值。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537940"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="acb4f-103">EOP 中的大量投訴層級 (BCL) </span><span class="sxs-lookup"><span data-stu-id="acb4f-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="acb4f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="acb4f-104">**Applies to**</span></span>
- [<span data-ttu-id="acb4f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="acb4f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="acb4f-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="acb4f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="acb4f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acb4f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="acb4f-108">在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織若沒有 Exchange Online 信箱，EOP 會指派大量的投訴等級 (BCL) 到大宗郵件傳送的輸入郵件。</span><span class="sxs-lookup"><span data-stu-id="acb4f-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="acb4f-109">BCL 會新增至 X 標頭中的郵件，類似于 [垃圾郵件信賴等級 (SCL) ](spam-confidence-levels.md) ，用來識別郵件為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="acb4f-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="acb4f-110">較高的 BCL 表示大宗郵件可能會產生抱怨 (，因此很可能是) 的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="acb4f-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="acb4f-111">Microsoft 會同時使用內部和協力廠商來源來識別大宗郵件，並決定適當的 BCL。</span><span class="sxs-lookup"><span data-stu-id="acb4f-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="acb4f-112">大量的寄件者會因傳送模式、內容建立和收件者購買慣例而異。</span><span class="sxs-lookup"><span data-stu-id="acb4f-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="acb4f-113">良好的大宗郵件傳送會透過相關的內容傳送至其訂閱者。</span><span class="sxs-lookup"><span data-stu-id="acb4f-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="acb4f-114">這些郵件會從收件者中產生少量的投訴。</span><span class="sxs-lookup"><span data-stu-id="acb4f-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="acb4f-115">其他大宗郵件傳送程式會傳送近類似垃圾郵件的未主動訊息，並從收件者產生許多投訴。</span><span class="sxs-lookup"><span data-stu-id="acb4f-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="acb4f-116">大宗郵件寄件者的郵件，稱為大宗郵件或灰階郵件。</span><span class="sxs-lookup"><span data-stu-id="acb4f-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="acb4f-117">垃圾郵件篩選會將郵件標示為以 BCL 閾值為基礎的 **電子郵件** (預設值或您指定的值) 並對郵件採取指定的動作 (預設動作會將郵件傳遞至收件者的 [垃圾郵件] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="acb4f-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="acb4f-118">如需詳細資訊，請參閱 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md) 和 [垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="acb4f-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="acb4f-119">您可以使用 [承租人允許/封鎖] 清單，設定大宗郵件篩選的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="acb4f-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="acb4f-120">來自指定網域中寄件者的郵件，不會收到反垃圾郵件原則中 **大量電子** 郵件篩選判定的動作。</span><span class="sxs-lookup"><span data-stu-id="acb4f-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="acb4f-121">如需詳細資訊，請參閱 [管理承租人 Allow/封鎖清單](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="acb4f-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="acb4f-122">下表說明 BCL 閾值。</span><span class="sxs-lookup"><span data-stu-id="acb4f-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="acb4f-123">BCL</span><span class="sxs-lookup"><span data-stu-id="acb4f-123">BCL</span></span>|<span data-ttu-id="acb4f-124">描述</span><span class="sxs-lookup"><span data-stu-id="acb4f-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="acb4f-125">0</span><span class="sxs-lookup"><span data-stu-id="acb4f-125">0</span></span>|<span data-ttu-id="acb4f-126">郵件並非來自大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="acb4f-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="acb4f-127">1、2、3</span><span class="sxs-lookup"><span data-stu-id="acb4f-127">1, 2, 3</span></span>|<span data-ttu-id="acb4f-128">郵件來自產生少量投訴的大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="acb4f-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="acb4f-129">4、5、6、7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="acb4f-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="acb4f-130">郵件來自大量寄件者，該寄件者會產生混和數目的投訴。</span><span class="sxs-lookup"><span data-stu-id="acb4f-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="acb4f-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="acb4f-131">8, 9</span></span>|<span data-ttu-id="acb4f-132">郵件來自大量寄件者，其會產生大量的投訴。</span><span class="sxs-lookup"><span data-stu-id="acb4f-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="acb4f-133"><sup>\*</sup> 這是反垃圾郵件原則中使用的預設臨界值。</span><span class="sxs-lookup"><span data-stu-id="acb4f-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
