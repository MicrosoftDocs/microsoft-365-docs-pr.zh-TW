---
title: 支援驗證 (DKIM) 簽署的郵件中識別的網域金鑰
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: 深入瞭解 Exchange Online Protection 和 Exchange Online 中的 DKIM 已簽署郵件的驗證
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845056"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="64f55-103">支援 DKIM 簽署郵件的驗證</span><span class="sxs-lookup"><span data-stu-id="64f55-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="64f55-104">Exchange Online Protection (EOP) 和 Exchange Online 都支援功能變數名稱驗證，識別出郵件 ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件。</span><span class="sxs-lookup"><span data-stu-id="64f55-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="64f55-105">DKIM 可驗證電子郵件訊息未被其他人 *欺騙* ，而且已 *從該郵件* 所發來的網域傳送。</span><span class="sxs-lookup"><span data-stu-id="64f55-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="64f55-106">它會將電子郵件訊息與傳送電子郵件的組織緊密。</span><span class="sxs-lookup"><span data-stu-id="64f55-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="64f55-107">DKIM 驗證會自動用於所有使用 IPv6 所傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="64f55-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="64f55-108">當郵件透過 IPv4 傳送時，Microsoft 365 也會支援 DKIM。</span><span class="sxs-lookup"><span data-stu-id="64f55-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="64f55-109"> (如需有關 IPv6 支援的詳細資訊，請參閱 [支援透過 IPv6 匿名輸入電子郵件訊息](support-for-anonymous-inbound-email-messages-over-ipv6.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="64f55-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="64f55-110">DKIM 會驗證郵件頭的 DKIM-Signature 標頭中顯示的數位簽署郵件。</span><span class="sxs-lookup"><span data-stu-id="64f55-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="64f55-111">DKIM-Signature 驗證的結果會加蓋 Authentication-Results 標頭。</span><span class="sxs-lookup"><span data-stu-id="64f55-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="64f55-112">顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：</span><span class="sxs-lookup"><span data-stu-id="64f55-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="64f55-113">如需 Authentication-Results 標頭的詳細資訊，請參閱 RFC 7001 ([Message Header 欄位，表示郵件驗證狀態](https://www.rfc-editor.org/rfc/rfc7001.txt)。</span><span class="sxs-lookup"><span data-stu-id="64f55-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="64f55-114">Microsoft 的 DKIM 實施會與此 RFC 相符。</span><span class="sxs-lookup"><span data-stu-id="64f55-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="64f55-115">系統管理員可以在 DKIM 驗證的結果上，建立 Exchange [郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也稱為傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="64f55-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="64f55-116">這些郵件流程規則可讓系統管理員視需要篩選或路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="64f55-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
