---
title: 大量投訴層級值、大宗郵件寄件者、BCL 層級、BCL 的運作方式、BCL 分級、反垃圾郵件標頭、大宗郵件篩選、停止大宗郵件
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 瞭解 Office 365 中的大量規范層級（BCL）值。
ms.openlocfilehash: aa839fc1bcab141fe71c76e7f27b4f6bb23048b2
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030147"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="69dfe-103">Office 365 中的大量投訴層級（BCL）</span><span class="sxs-lookup"><span data-stu-id="69dfe-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="69dfe-104">大量的寄件者會因傳送模式、內容建立和收件者購買慣例而異。</span><span class="sxs-lookup"><span data-stu-id="69dfe-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="69dfe-105">有些是很好的大宗郵件傳送，可將相關的郵件傳送至訂閱者。</span><span class="sxs-lookup"><span data-stu-id="69dfe-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="69dfe-106">這些郵件會從收件者中產生少量的投訴。</span><span class="sxs-lookup"><span data-stu-id="69dfe-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="69dfe-107">其他大宗郵件傳送程式會傳送近類似垃圾郵件的未主動訊息，並從收件者產生許多投訴。</span><span class="sxs-lookup"><span data-stu-id="69dfe-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="69dfe-108">大宗郵件寄件者的郵件稱為大宗郵件或灰階郵件。</span><span class="sxs-lookup"><span data-stu-id="69dfe-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="69dfe-109">若要辨別來自不同類型大宗郵件的郵件，來自大宗郵件傳送至 Office 365 的輸入電子郵件（Exchange Online 或獨立 Exchange Online Protection （EOP）（未使用 Exchange Online 信箱），則會獲增值至X 標頭中的郵件。</span><span class="sxs-lookup"><span data-stu-id="69dfe-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers to Office 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="69dfe-110">BCL 類似于[垃圾郵件信賴等級（SCL）](spam-confidence-levels.md) ，用來識別郵件為垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="69dfe-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="69dfe-111">較高的 BCL 表示大宗郵件可能會產生抱怨（因此可能是垃圾郵件）。</span><span class="sxs-lookup"><span data-stu-id="69dfe-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="69dfe-112">Microsoft 會同時使用內部和協力廠商來源來識別大宗郵件，並決定適當的 BCL。</span><span class="sxs-lookup"><span data-stu-id="69dfe-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="69dfe-113">垃圾郵件篩選會將郵件標示為以 BCL 閾值（預設值或您指定的值）為基礎的**電子郵件**，並對郵件採取指定的動作（預設動作會將郵件傳遞至收件者的 [垃圾郵件] 資料夾）。</span><span class="sxs-lookup"><span data-stu-id="69dfe-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="69dfe-114">如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)和[垃圾郵件和大量電子郵件有什麼不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="69dfe-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="69dfe-115">下表說明 BCL 閾值。</span><span class="sxs-lookup"><span data-stu-id="69dfe-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="69dfe-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="69dfe-116">**BCL**</span></span>|<span data-ttu-id="69dfe-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="69dfe-117">**Description**</span></span>|
|<span data-ttu-id="69dfe-118">0</span><span class="sxs-lookup"><span data-stu-id="69dfe-118">0</span></span>|<span data-ttu-id="69dfe-119">郵件並非來自大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="69dfe-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="69dfe-120">1、2、3</span><span class="sxs-lookup"><span data-stu-id="69dfe-120">1, 2, 3</span></span>|<span data-ttu-id="69dfe-121">郵件來自產生少量投訴的大量寄件者。</span><span class="sxs-lookup"><span data-stu-id="69dfe-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="69dfe-122">4、5、6、7</span><span class="sxs-lookup"><span data-stu-id="69dfe-122">4, 5, 6, 7</span></span>|<span data-ttu-id="69dfe-123">郵件來自大量寄件者，該寄件者會產生混和數目的投訴。</span><span class="sxs-lookup"><span data-stu-id="69dfe-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="69dfe-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="69dfe-124">8, 9</span></span>|<span data-ttu-id="69dfe-125">郵件來自大量寄件者，其會產生大量的投訴。</span><span class="sxs-lookup"><span data-stu-id="69dfe-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
