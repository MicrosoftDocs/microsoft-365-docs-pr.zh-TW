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
description: 系統管理員可以深入瞭解 Exchange Online Protection (EOP) 中所用的大量規范層級 (BCL) 數值。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289889"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="746b5-103">EOP 中的大量投訴層級 (BCL) </span><span class="sxs-lookup"><span data-stu-id="746b5-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="746b5-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="746b5-104">**Applies to**</span></span>
- [<span data-ttu-id="746b5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="746b5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="746b5-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="746b5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="746b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="746b5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="746b5-108">在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱時，EOP 會指派大量相容層級 (BCL) 至來自大宗郵件寄件者的輸入郵件。</span><span class="sxs-lookup"><span data-stu-id="746b5-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="746b5-109">BCL 會新增至 X 標頭中的郵件，類似于 [垃圾郵件信賴等級 (SCL) ](spam-confidence-levels.md) ，用來識別郵件為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="746b5-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="746b5-110">較高的 BCL 表示大宗郵件可能會產生抱怨 (，因此很可能是) 的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="746b5-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="746b5-111">Microsoft 會同時使用內部和協力廠商來源來識別大宗郵件，並決定適當的 BCL。</span><span class="sxs-lookup"><span data-stu-id="746b5-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="746b5-112">大量的寄件者會因傳送模式、內容建立和收件者購買慣例而異。</span><span class="sxs-lookup"><span data-stu-id="746b5-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="746b5-113">良好的大宗郵件傳送會透過相關的內容傳送至其訂閱者。</span><span class="sxs-lookup"><span data-stu-id="746b5-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="746b5-114">這些郵件會從收件者中產生少量的投訴。</span><span class="sxs-lookup"><span data-stu-id="746b5-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="746b5-115">其他大宗郵件傳送程式會傳送近類似垃圾郵件的未主動訊息，並從收件者產生許多投訴。</span><span class="sxs-lookup"><span data-stu-id="746b5-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="746b5-116">大宗郵件寄件者的郵件，稱為大宗郵件或灰階郵件。</span><span class="sxs-lookup"><span data-stu-id="746b5-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="746b5-117">垃圾郵件篩選會將郵件標示為以 BCL 閾值為基礎的 **電子郵件** (預設值或您指定的值) 並對郵件採取指定的動作 (預設動作會將郵件傳遞至收件者的 [垃圾郵件] 資料夾) 。</span><span class="sxs-lookup"><span data-stu-id="746b5-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="746b5-118">如需詳細資訊，請參閱 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md) 和 [垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="746b5-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="746b5-119">下表說明 BCL 閾值。</span><span class="sxs-lookup"><span data-stu-id="746b5-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="746b5-120">BCL</span><span class="sxs-lookup"><span data-stu-id="746b5-120">BCL</span></span>|<span data-ttu-id="746b5-121">描述</span><span class="sxs-lookup"><span data-stu-id="746b5-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="746b5-122">0</span><span class="sxs-lookup"><span data-stu-id="746b5-122">0</span></span>|<span data-ttu-id="746b5-123">郵件並非來自大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="746b5-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="746b5-124">1、2、3</span><span class="sxs-lookup"><span data-stu-id="746b5-124">1, 2, 3</span></span>|<span data-ttu-id="746b5-125">郵件來自產生少量投訴的大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="746b5-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="746b5-126">4、5、6、7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="746b5-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="746b5-127">郵件來自大量寄件者，該寄件者會產生混和數目的投訴。</span><span class="sxs-lookup"><span data-stu-id="746b5-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="746b5-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="746b5-128">8, 9</span></span>|<span data-ttu-id="746b5-129">郵件來自大量寄件者，其會產生大量的投訴。</span><span class="sxs-lookup"><span data-stu-id="746b5-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="746b5-130"><sup>\*</sup> 這是反垃圾郵件原則中使用的預設臨界值。</span><span class="sxs-lookup"><span data-stu-id="746b5-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
