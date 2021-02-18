---
title: EOP 中的退信攻擊
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: '在本文中，您將瞭解退信攻擊和 Microsoft Exchange Online Protection (EOP) '
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286966"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="50b63-103">EOP 中的退信攻擊</span><span class="sxs-lookup"><span data-stu-id="50b63-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="50b63-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="50b63-104">**Applies to**</span></span>
- [<span data-ttu-id="50b63-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="50b63-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="50b63-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="50b63-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="50b63-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50b63-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="50b63-108">*退信攻擊* 是未傳遞回報 (也稱為 NDRs 或退回郵件，) 您收到您未傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="50b63-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="50b63-109">垃圾郵件竊取 () 其郵件的寄件者位址，而且經常會使用實際的電子郵件地址來為其郵件的信譽。</span><span class="sxs-lookup"><span data-stu-id="50b63-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="50b63-110">因此，垃圾郵件製造者不可避免傳送郵件給非現有的收件者 (垃圾郵件是高容量作業) 時，目的地電子郵件伺服器實質上會欺騙您將 NDR 中無法傳遞的郵件，傳回寄件者： address 中的偽造寄件者。</span><span class="sxs-lookup"><span data-stu-id="50b63-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="50b63-111">在使用 Exchange Online 中的信箱或獨立 Exchange Online (Protection 中的 Microsoft 365 組織中，EOP) 不含 Exchange Online 信箱的組織，EOP 會盡一切努力識別 dubious 來源中的郵件，並無任何產生 NDR。</span><span class="sxs-lookup"><span data-stu-id="50b63-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="50b63-112">不過，根據整個服務流動大量電子郵件的情況，EOP 會無意間傳送退信攻擊的可能性。</span><span class="sxs-lookup"><span data-stu-id="50b63-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="50b63-113">Backscatterer.org 會維護封鎖清單 (也稱為 DNS 封鎖清單或 DNSBL) 的電子郵件伺服器負責傳送退信攻擊，而 EOP 伺服器可能會出現在此清單中。</span><span class="sxs-lookup"><span data-stu-id="50b63-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="50b63-114">不過，我們不會嘗試從 Backscatterer.org 封鎖清單中移除自己，因為它不是自己的許可) 所 (的垃圾郵件者清單。</span><span class="sxs-lookup"><span data-stu-id="50b63-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="50b63-115">Backscatter.org 網站 (<http://www.backscatterer.org/?target=usage>) 建議使用其服務，以在安全模式中檢查內送電子郵件，而不是以「拒絕」模式， (較大型的電子郵件服務幾乎總會傳送部分退信攻擊) 。</span><span class="sxs-lookup"><span data-stu-id="50b63-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
