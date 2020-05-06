---
title: 退信攻擊與 EOP
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
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解退信攻擊和 Microsoft Exchange Online Protection （EOP）
ms.openlocfilehash: 14460b75920b053461722b5a129d785fb6952a5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035589"
---
# <a name="backscatter-and-eop"></a><span data-ttu-id="4c4d6-103">退信攻擊與 EOP</span><span class="sxs-lookup"><span data-stu-id="4c4d6-103">Backscatter and EOP</span></span>

<span data-ttu-id="4c4d6-104">*退信攻擊*是您接收到未傳送之郵件的未傳遞回報（也稱為 NDRs 或退回的郵件）。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="4c4d6-105">垃圾郵件傳送者（哄騙）其郵件的寄件者位址，通常會使用實際的電子郵件地址，使其郵件成為信譽。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="4c4d6-106">因此，垃圾郵件製造者不可避免傳送郵件給不存在的收件者（垃圾郵件是高容量作業）時，目的地電子郵件伺服器實質上會欺騙您將 NDR 中無法傳遞的郵件傳回寄件者： address 中的偽造寄件者。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="4c4d6-107">Exchange Online Protection （EOP）會盡一切努力識別 dubious 來源中的郵件，並以無訊息方式丟棄郵件，而不會產生 NDR。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-107">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="4c4d6-108">不過，根據整個服務流動大量電子郵件的情況，EOP 會無意間傳送退信攻擊的可能性。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="4c4d6-109">Backscatterer.org 維護負責傳送退信攻擊之電子郵件伺服器的封鎖清單（也稱為 DNS 封鎖清單或 DNSBL），而 EOP 伺服器可能會出現在此清單中。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="4c4d6-110">不過，我們不會嘗試從 Backscatterer.org 封鎖清單中移除自己，因為它不是垃圾郵件傳送者的清單（由其自有的許可）。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="4c4d6-111">Backscatter.org 網站（<http://www.backscatterer.org/?target=usage>）建議使用其服務，以在安全模式中檢查內送電子郵件，而不是拒絕模式（大型電子郵件服務幾乎永遠會傳送某些退信攻擊）。</span><span class="sxs-lookup"><span data-stu-id="4c4d6-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
