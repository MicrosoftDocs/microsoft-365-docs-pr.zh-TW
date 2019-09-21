---
title: 管理大量郵件寄件者的安全寄件者清單
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
ms.openlocfilehash: f73cc3fc88318c4f625bf5579f73d92625624fd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078110"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="ece40-105">管理大量郵件寄件者的安全寄件者清單</span><span class="sxs-lookup"><span data-stu-id="ece40-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="ece40-106">如果您想要使用安全的寄件者清單，您應該了解 Exchange Online Protection (EOP) 和 Outlook 處理方式處理。</span><span class="sxs-lookup"><span data-stu-id="ece40-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="ece40-107">Office 365 服務會藉由檢查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，Outlook 會在使用者的安全寄件者清單中新增 RFC 5322.From 地址時遵守安全寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="ece40-107">The Office 365 service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list.</span></span> <span data-ttu-id="ece40-108">(請注意： 此服務會檢查是否有 5321.MailFrom 地址和 5322.From 地址的封鎖寄件者和網域。)</span><span class="sxs-lookup"><span data-stu-id="ece40-108">(Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="ece40-109">SMTP 郵件從地址，又稱為 RFC 5321.MailFrom 地址，是用來執行 SPF 檢查電子郵件地址和如果無法傳遞郵件，退回的郵件會傳遞至的路徑。</span><span class="sxs-lookup"><span data-stu-id="ece40-109">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="ece40-110">雖然可以指定不同的形式傳回路徑地址寄件者是根據預設，在郵件標頭中傳回路徑進入此電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ece40-110">It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="ece40-111">[從： 郵件標頭，又稱為 RFC 5322.From 地址的地址會隨即出現在郵件用戶端 Outlook 之類的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ece40-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="ece40-112">大部分的時間、 5321.MailFrom 和 5322.From 地址都相同。</span><span class="sxs-lookup"><span data-stu-id="ece40-112">Much of the time, the 5321.MailFrom and 5322.From addresses are the same.</span></span> <span data-ttu-id="ece40-113">這是一般的人對人通訊。</span><span class="sxs-lookup"><span data-stu-id="ece40-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="ece40-114">不過，當電子郵件傳送代表其他人時，會經常不同位址。</span><span class="sxs-lookup"><span data-stu-id="ece40-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="ece40-115">這通常是最常的大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ece40-115">This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="ece40-116">例如，假設航空公司 Blue Yonder Airlines 具有收起出 Margie 的旅行寄出其電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="ece40-116">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="ece40-117">您然後收到的訊息收件匣中從寄件者 blueyonder@news.blueyonderairlines.com。</span><span class="sxs-lookup"><span data-stu-id="ece40-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="ece40-118">在此情況下，5321.MailFrom 地址是 blueyonder.airlines@margiestravel.com，且 blueyonder@news.blueyonderairlines.com 5322.From 地址也就是，您在 Outlook 中看到。</span><span class="sxs-lookup"><span data-stu-id="ece40-118">In this case, 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one, you see in Outlook.</span></span> <span data-ttu-id="ece40-119">因為服務遵守區別發音 RFC 5322.From 地址，若要避免這個訊息取得篩選，您可以新增 RFC 5322.From 地址中 （如使用者） 的 Outlook 安全寄件者或如果您是在[反垃圾郵件所示設定郵件流程規則系統管理員保護](anti-spam-protection.md)區段。</span><span class="sxs-lookup"><span data-stu-id="ece40-119">Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can add the RFC 5322.From address as a safe sender in Outlook (as a user) or, if you're an administrator set up a mailflow rule as shown on the [Anti-spam Protection](anti-spam-protection.md) section.</span></span>
  

