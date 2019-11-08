---
title: 支援透過 IPv6 的匿名輸入電子郵件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: 了解如何設定 Exchange Online Protection 和 Exchange Online 來源 IPv6 的匿名郵件的支援。
ms.openlocfilehash: c29c1fa450ca2a2e213930c4f4a394aaf462e31d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031988"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="84ca3-103">支援透過 IPv6 的匿名輸入電子郵件</span><span class="sxs-lookup"><span data-stu-id="84ca3-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="84ca3-104">Exchange Online Protection (EOP) 和 Exchange Online 均可支援透過 IPv6 通訊接收來自未透過傳輸層安全性 (TLS) 傳送郵件之寄件者的匿名輸入電子郵件。</span><span class="sxs-lookup"><span data-stu-id="84ca3-104">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS).</span></span> <span data-ttu-id="84ca3-105">您可以選擇集來向 Microsoft 支援服務要求這項功能，藉由開啟 Microsoft 365 系統管理中心，透過 IPv6 接收訊息[https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)、 [**支援**，，然後按一下 [**新增服務要求**)。</span><span class="sxs-lookup"><span data-stu-id="84ca3-105">You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Microsoft 365 admin center at [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicking **Support**, and then clicking **New service request**).</span></span> <span data-ttu-id="84ca3-106">如果您未選擇加入 IPv6，則會繼續透過 IPv4 接收郵件。</span><span class="sxs-lookup"><span data-stu-id="84ca3-106">If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="84ca3-107">透過 IPv6 將郵件傳輸至服務的寄件者必須符合下列兩項需求：</span><span class="sxs-lookup"><span data-stu-id="84ca3-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="84ca3-108">傳送 IPv6 地址必須具備有效的 PTR 記錄 (傳送 IPv6 地址的 [反向 DNS 記錄](https://en.wikipedia.org/wiki/Reverse_DNS_lookup))。</span><span class="sxs-lookup"><span data-stu-id="84ca3-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="84ca3-109">寄件者必須通過 SPF 驗證 (定義於 [RFC 7208](https://tools.ietf.org/html/rfc7208)) 或 [DKIM 驗證](https://dkim.org/) (定義於 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt))。</span><span class="sxs-lookup"><span data-stu-id="84ca3-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="84ca3-110">選擇加入 IPv6 之前，不論您的組態為何，符合這些需求都是必要的。</span><span class="sxs-lookup"><span data-stu-id="84ca3-110">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6.</span></span> <span data-ttu-id="84ca3-111">若已符合這兩項需求，郵件就會通過經歷此服務所提供的正常電子郵件篩選。</span><span class="sxs-lookup"><span data-stu-id="84ca3-111">If both requirements are met, the message will go through normal email message filtering provided by the service.</span></span> <span data-ttu-id="84ca3-112">如果一或其他不符合，郵件會遭到拒絕以其中一個下列 450 回應：</span><span class="sxs-lookup"><span data-stu-id="84ca3-112">If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="84ca3-113">如果您未選擇透過 IPv6 接收郵件，而寄件者藉由手動連線到郵件伺服器以試圖強制透過 IPv6 傳送郵件，則此郵件會遭到拒絕並出現類似下面的 550 回應：</span><span class="sxs-lookup"><span data-stu-id="84ca3-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="84ca3-114">相關資訊</span><span class="sxs-lookup"><span data-stu-id="84ca3-114">For more information</span></span>

[<span data-ttu-id="84ca3-115">支援 DKIM 簽署郵件的驗證</span><span class="sxs-lookup"><span data-stu-id="84ca3-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

