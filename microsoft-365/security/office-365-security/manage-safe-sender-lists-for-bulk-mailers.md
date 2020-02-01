---
title: 管理大量郵件寄件者的安全寄件者清單
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理方式處理。 服務會藉由檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，Outlook 會在使用者的安全寄件者清單中新增 RFC 5322.From 地址時遵守安全寄件者和網域。 (請注意： 此服務會檢查是否有 5321.MailFrom 地址和 5322.From 地址的封鎖寄件者和網域。)
ms.openlocfilehash: aaede7cab2e640603c20804f4015e19f61b6c2f3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598940"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="af4da-105">管理大量郵件寄件者的安全寄件者清單</span><span class="sxs-lookup"><span data-stu-id="af4da-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="af4da-106">如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理方式處理。</span><span class="sxs-lookup"><span data-stu-id="af4da-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="af4da-107">Office 365 服務遵守區別發音安全寄件者和網域藉由檢查`RFC 5321.MailFrom`地址和`RFC 5322.From`時 Outlook 新增處理`RFC 5322.From`至使用者的安全寄件者清單的地址。</span><span class="sxs-lookup"><span data-stu-id="af4da-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="af4da-108">(附註： 此服務會檢查兩者`5321.MailFrom`地址和`5322.From`封鎖寄件者和網域的地址。)</span><span class="sxs-lookup"><span data-stu-id="af4da-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="af4da-109">`SMTP MAIL FROM`地址，又稱為`RFC 5321.MailFrom address`，是用來執行 SPF 檢查電子郵件地址和如果無法傳遞郵件，退回的郵件會傳遞至的路徑。</span><span class="sxs-lookup"><span data-stu-id="af4da-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="af4da-110">它是放入此電子郵件地址`Return-Path`預設郵件標頭，但有可能的寄件者指定不同`Return-Path`地址。</span><span class="sxs-lookup"><span data-stu-id="af4da-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="af4da-111">`From:`地址的郵件標頭，又稱為`RFC 5322.From`位址，是會顯示在郵件用戶端 Outlook 之類的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="af4da-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="af4da-112">最多的時間，`5321.MailFrom`和`5322.From`都是相同的地址。</span><span class="sxs-lookup"><span data-stu-id="af4da-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="af4da-113">這是一般的人對人通訊。</span><span class="sxs-lookup"><span data-stu-id="af4da-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="af4da-114">不過，當電子郵件傳送代表其他人時，會經常不同位址。</span><span class="sxs-lookup"><span data-stu-id="af4da-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="af4da-115">這通常是最常的大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="af4da-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="af4da-116">例如，假設 Blue Yonder Airlines 已僱用 Margie 的旅行寄出其電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="af4da-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="af4da-117">您然後收到的訊息收件匣中從寄件者 blueyonder@news.blueyonderairlines.com。</span><span class="sxs-lookup"><span data-stu-id="af4da-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="af4da-118">在此範例中：</span><span class="sxs-lookup"><span data-stu-id="af4da-118">In this example:</span></span>

- <span data-ttu-id="af4da-119">`5321.MailFrom`地址是 blueyonder.airlines@margiestravel.com。</span><span class="sxs-lookup"><span data-stu-id="af4da-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="af4da-120">`5322.From`地址為 blueyonder@news.blueyonderairlines.com，也就是您會看到在 Outlook 中。</span><span class="sxs-lookup"><span data-stu-id="af4da-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="af4da-121">若要避免這個訊息篩選，您可以：</span><span class="sxs-lookup"><span data-stu-id="af4da-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="af4da-122">**以使用者身分**： 新增`RFC 5322.From`為在 Outlook 中的安全寄件者的地址。</span><span class="sxs-lookup"><span data-stu-id="af4da-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="af4da-123">**身為系統管理員**： 設定[郵件流程規則](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)（也稱為傳輸規則）。</span><span class="sxs-lookup"><span data-stu-id="af4da-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
