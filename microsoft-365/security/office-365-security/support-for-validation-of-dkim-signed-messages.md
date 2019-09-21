---
title: 支援 DKIM 簽署郵件的驗證
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
description: 了解的驗證的 DKIM 簽署郵件在 Exchange Online Protection 和 Exchange Online
ms.openlocfilehash: 75c104af4b3e6126bac37024de2c7f6ab337a028
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078235"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="22e79-103">支援 DKIM 簽署郵件的驗證</span><span class="sxs-lookup"><span data-stu-id="22e79-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="22e79-104">Exchange Online Protection (EOP) 和 Exchange Online 支援輸入的驗證的網域金鑰 Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 郵件。</span><span class="sxs-lookup"><span data-stu-id="22e79-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="22e79-105">DKIM 會驗證郵件已傳送從它說來自網域並不詐騙由其他人的方法。</span><span class="sxs-lookup"><span data-stu-id="22e79-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="22e79-106">它會繫結負責將它傳送的組織將電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="22e79-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="22e79-107">透過 IPv6 通訊傳送的所有郵件，會自動使用 DKIM 驗證。</span><span class="sxs-lookup"><span data-stu-id="22e79-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="22e79-108">Office 365 現在還可以支援 DKIM，透過 IPv4 傳送郵件時。</span><span class="sxs-lookup"><span data-stu-id="22e79-108">Office 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="22e79-109">（如需 IPv6 支援的詳細資訊，請參閱[支援透過 IPv6 的匿名輸入的電子郵件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。）</span><span class="sxs-lookup"><span data-stu-id="22e79-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>
  
<span data-ttu-id="22e79-p102">DKIM 會驗證郵件標頭的 DKIM 簽章標頭中顯示的數位簽署郵件。DKIM 簽章驗證的結果會在符合 RFC 7001 的 Authentication-Results 標頭中加上戳記 ([用於指出郵件驗證狀態的郵件標頭欄位](https://www.rfc-editor.org/rfc/rfc7001.txt))。顯示的郵件標頭文字類似下列文字 (寄件者為 contoso.com)：</span><span class="sxs-lookup"><span data-stu-id="22e79-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
<span data-ttu-id="22e79-113">系統管理員可以建立 Exchange[郵件流程規則](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)（也稱為傳輸規則） 來篩選在 DKIM 驗證結果上，或將郵件路由傳送做為所需。</span><span class="sxs-lookup"><span data-stu-id="22e79-113">Admins can create Exchange [mail flow rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span> 
  

