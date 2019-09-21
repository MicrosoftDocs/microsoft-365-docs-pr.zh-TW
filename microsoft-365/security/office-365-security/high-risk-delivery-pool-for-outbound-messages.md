---
title: 高風險傳遞集區的外寄郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 當客戶的電子郵件系統已經受到惡意程式碼或惡意垃圾郵件攻擊，且它傳送到託管的篩選服務的輸出垃圾郵件時，這可能導致各別列出協力廠商區塊上的 Office 365 資料中心伺服器的 IP 位址列出。
ms.openlocfilehash: 5b9241dead5b40e9f216ecd3023d6f8b86fb0205
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076851"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="18f2a-103">高風險傳遞集區的外寄郵件</span><span class="sxs-lookup"><span data-stu-id="18f2a-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="18f2a-104">當客戶的電子郵件系統已經受到惡意程式碼或惡意垃圾郵件攻擊，且它傳送到託管的篩選服務的輸出垃圾郵件時，這可能導致各別列出協力廠商區塊上的 Office 365 資料中心伺服器的 IP 位址列出。</span><span class="sxs-lookup"><span data-stu-id="18f2a-104">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists.</span></span> <span data-ttu-id="18f2a-105">執行動作的目的伺服器不使用託管的篩選服務，但不要使用這些封鎖清單，拒絕從任何已新增至這些清單託管篩選 IP 位址傳送的所有電子郵件。</span><span class="sxs-lookup"><span data-stu-id="18f2a-105">Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists.</span></span> <span data-ttu-id="18f2a-106">為避免這種情況，超出垃圾郵件閾值的所有外寄郵件傳送到高風險傳遞集區。</span><span class="sxs-lookup"><span data-stu-id="18f2a-106">To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool.</span></span> <span data-ttu-id="18f2a-107">此次要的外寄電子郵件集區只能用來傳送郵件，可能的低品質。</span><span class="sxs-lookup"><span data-stu-id="18f2a-107">This secondary outbound email pool is only used to send messages that may be of low quality.</span></span> <span data-ttu-id="18f2a-108">這有助於防止其餘的網路傳送更有可能導致傳送的 IP 位址遭到封鎖的郵件。</span><span class="sxs-lookup"><span data-stu-id="18f2a-108">This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="18f2a-109">使用專用的高風險傳遞集區可協助確保標準輸出集區僅傳送已知的高品質的郵件。</span><span class="sxs-lookup"><span data-stu-id="18f2a-109">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality.</span></span> <span data-ttu-id="18f2a-110">使用此次要 IP 集區可協助降低新增至封鎖清單的一般的輸出 IP 集區的機率。</span><span class="sxs-lookup"><span data-stu-id="18f2a-110">Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list.</span></span> <span data-ttu-id="18f2a-111">要放在封鎖清單上的高風險傳遞集區的可能性會維持風險。</span><span class="sxs-lookup"><span data-stu-id="18f2a-111">The possibility of the high-risk delivery pool being placed on a blocked list remains a risk.</span></span> <span data-ttu-id="18f2a-112">這是預設的設計。</span><span class="sxs-lookup"><span data-stu-id="18f2a-112">This is by design.</span></span>
  
<span data-ttu-id="18f2a-113">在傳送網域出具有任何地址記錄 （A 記錄），可讓您網域的 IP 位址和任何 MX 記錄，可將郵件導向至 DNS 中應收到特別網域之郵件伺服器，郵件會一律透過路由傳送無論其垃圾郵件處理高風險傳遞集區。</span><span class="sxs-lookup"><span data-stu-id="18f2a-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="18f2a-114">了解傳遞狀態通知 (DSN) 郵件</span><span class="sxs-lookup"><span data-stu-id="18f2a-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="18f2a-115">讓輸出的高風險傳遞集區可管理所有 「 被退回 」 或 「 失敗 」 (DSN) 郵件的傳遞。</span><span class="sxs-lookup"><span data-stu-id="18f2a-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="18f2a-116">DSN 郵件激增的可能原因包括下列：</span><span class="sxs-lookup"><span data-stu-id="18f2a-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="18f2a-117">詐騙活動影響到使用服務的其中一位客戶</span><span class="sxs-lookup"><span data-stu-id="18f2a-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="18f2a-118">目錄搜集攻擊</span><span class="sxs-lookup"><span data-stu-id="18f2a-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="18f2a-119">垃圾郵件攻擊</span><span class="sxs-lookup"><span data-stu-id="18f2a-119">A spam attack</span></span>
    
- <span data-ttu-id="18f2a-120">惡意 SMTP 伺服器</span><span class="sxs-lookup"><span data-stu-id="18f2a-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="18f2a-121">所有這些問題都可能導致服務處理的 DSN 郵件數量突然增多。</span><span class="sxs-lookup"><span data-stu-id="18f2a-121">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service.</span></span> <span data-ttu-id="18f2a-122">許多時候，這些 DSN 郵件看起來會對其他電子郵件伺服器和服務的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="18f2a-122">Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="18f2a-123">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="18f2a-123">For more information</span></span>

[<span data-ttu-id="18f2a-124">設定輸出垃圾郵件原則</span><span class="sxs-lookup"><span data-stu-id="18f2a-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="18f2a-125">反垃圾郵件保護常見問題集</span><span class="sxs-lookup"><span data-stu-id="18f2a-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

