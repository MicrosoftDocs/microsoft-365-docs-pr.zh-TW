---
title: 非法回應郵件與 EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: 非法回應郵件都會自動的退回的郵件傳送至偽造的電子郵件地址。 非法回應 DNSBL 識別傳送非法回應郵件 （其中可能包含許多合法電子郵件來源） 的伺服器。 因為它不是濫發垃圾郵件者清單中，我們不會嘗試從非法回應 DNSBL 移除自誇。
ms.openlocfilehash: 3dc83c303e861c8762f2276de521e1b550ae2e59
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599730"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="7d092-105">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="7d092-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="7d092-106">*非法回應郵件*是未傳遞回報 （也稱為 Ndr 或退回的郵件） 您會收到未傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="7d092-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="7d092-107">濫發垃圾郵件者冶 （詐騙） [從： 地址，他們的郵件，以及它們通常會使用實際電子郵件地址來強化可信度到他們的郵件。</span><span class="sxs-lookup"><span data-stu-id="7d092-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="7d092-108">因此，當他們無可不存在的收件者傳送郵件 （垃圾郵件是在大量作業），在目的地電子郵件伺服器可能盡責回應與 NDR，傳送給在 [從偽造寄件者： 地址。</span><span class="sxs-lookup"><span data-stu-id="7d092-108">So, when they inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server might dutifully respond with an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="7d092-109">Exchange Online Protection (EOP) 會盡一切努力來找出並以無訊息方式捨棄可疑的來源訊息而不會產生 NDR。</span><span class="sxs-lookup"><span data-stu-id="7d092-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="7d092-110">但是，根據流經服務真正的大量電子郵件，永遠 EOP 會不小心傳送非法回應郵件的可能性。</span><span class="sxs-lookup"><span data-stu-id="7d092-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="7d092-111">Backscatterer.org 維護已負責傳送非法回應郵件與 EOP 伺服器的伺服器可能會出現在此清單的電子郵件的封鎖清單 （也就是 DNS 封鎖清單或 DNSBL）。</span><span class="sxs-lookup"><span data-stu-id="7d092-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="7d092-112">但是，我們不會嘗試移除自誇從 Backscatterer.org 封鎖清單，因為它不是濫發垃圾郵件者 （依自己的許可） 的清單。</span><span class="sxs-lookup"><span data-stu-id="7d092-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="7d092-113">根據 Backscatter.or 網站 (`http://www.backscatterer.org/?target=usage`)，這些建議使用其服務來檢查在安全的模式，而不是拒絕模式中的內送電子郵件 （大型的電子郵件服務幾乎總是傳送某些非法回應郵件）。</span><span class="sxs-lookup"><span data-stu-id="7d092-113">According to the Backscatter.or website (`http://www.backscatterer.org/?target=usage`), they recommend using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
