---
title: 非法回應郵件與 EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: 非法回應郵件所傳送的郵件伺服器，通常是因為傳入的垃圾郵件自動的退回的郵件。 非法回應 DNSBL 是一份傳送非法回應郵件的 IP 位址清單。 它不是濫發垃圾郵件者清單，我們不會嘗試從非法回應 DNSBL 移除我們的伺服器。
ms.openlocfilehash: 481203e4a91f24c9ae1992dce402b0d3e951110e
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440560"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="e7eb4-105">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="e7eb4-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="e7eb4-106">非法回應郵件所傳送的郵件伺服器，通常是因為傳入的垃圾郵件自動的退回的郵件。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-106">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam.</span></span> <span data-ttu-id="e7eb4-107">因為 Exchange Online Protection (EOP) 是垃圾郵件篩選服務，我們的服務會拒絕傳送至不存在收件者及其他可疑目的地的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-107">Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service.</span></span> <span data-ttu-id="e7eb4-108">發生此情況時，EOP 產生未傳遞回報 (NDR) 郵件並傳回給「寄件者」。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-108">When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender."</span></span> <span data-ttu-id="e7eb4-109">因為濫發垃圾郵件者經常在郵件中利用偽造或無效的「寄件者」地址，NDR 所寄到的寄件者地址可能會導致非法回應郵件。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-109">Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message.</span></span> <span data-ttu-id="e7eb4-110">發生此情況時，與 EOP 網路相關聯的外寄伺服器可能會列在非法回應 DNS 封鎖清單 (DNSBL) 中。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-110">When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL).</span></span> <span data-ttu-id="e7eb4-111">非法回應 DNSBL 是一份傳送非法回應郵件的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-111">The Backscatterer DNSBL is a list of IP addresses that send backscatter messages.</span></span> <span data-ttu-id="e7eb4-112">它不是濫發垃圾郵件者清單，我們不會嘗試從非法回應 DNSBL 移除我們的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-112">It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span>

> [!TIP]
> <span data-ttu-id="e7eb4-p103">根據 Backscatterer 網站的指示，該服務的設定或用法不建議對所有傳入的郵件使用拒絕模式。而是應該在安全模式中使用。如需實作正確非法回應設定的相關資訊，請造訪 [Backscatterer.org 網站](http://www.backscatterer.org/?target=usage)。</span><span class="sxs-lookup"><span data-stu-id="e7eb4-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7eb4-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7eb4-116">Related topics</span></span>

[<span data-ttu-id="e7eb4-117">進階垃圾郵件篩選選項</span><span class="sxs-lookup"><span data-stu-id="e7eb4-117">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
