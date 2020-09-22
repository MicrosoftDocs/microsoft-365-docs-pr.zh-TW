---
title: 支援 DKIM 簽署郵件的驗證
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
ms.openlocfilehash: e2e91fe426348487fa4dfa8ef929d2d8129ffddc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202134"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="895f7-103">支援 DKIM 簽署郵件的驗證</span><span class="sxs-lookup"><span data-stu-id="895f7-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="895f7-104">Exchange Online Protection (EOP) 和 Exchange Online 支援網域機碼的輸入驗證識別郵件 ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件。</span><span class="sxs-lookup"><span data-stu-id="895f7-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="895f7-105">DKIM 是一種方法，用來驗證郵件是由其來源的網域所傳送，且沒有其他人冒充。</span><span class="sxs-lookup"><span data-stu-id="895f7-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="895f7-106">它會將電子郵件訊息與負責傳送電子郵件的組織緊密聯繫。</span><span class="sxs-lookup"><span data-stu-id="895f7-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="895f7-107">DKIM 驗證會自動用於透過 IPv6 通訊傳送的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="895f7-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="895f7-108">在 IPv4 傳送郵件時，Microsoft 365 現在也會支援 DKIM。</span><span class="sxs-lookup"><span data-stu-id="895f7-108">Microsoft 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="895f7-109"> (如需有關 IPv6 支援的詳細資訊，請參閱 [支援透過 IPv6 匿名輸入電子郵件訊息](support-for-anonymous-inbound-email-messages-over-ipv6.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="895f7-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="895f7-p102">DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：</span><span class="sxs-lookup"><span data-stu-id="895f7-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="895f7-113">系統管理員可以建立 Exchange [郵件流程規則](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也稱為傳輸規則) DKIM 驗證的結果，以視需要篩選或路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="895f7-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
