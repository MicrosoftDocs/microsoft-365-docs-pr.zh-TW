---
title: 新增透過 IPv6 支援匿名輸入電子郵件
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何在 Exchange Online 和 Exchange Online Protection 的 IPv6 來源中設定匿名輸入電子郵件的支援。
ms.openlocfilehash: fbbcba3631c7b2a7060f07011c119ee973fdf4af
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818706"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="42603-103">在 Microsoft 365 中新增對 IPv6 匿名輸入電子郵件的支援</span><span class="sxs-lookup"><span data-stu-id="42603-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="42603-104">Microsoft 365 組織若有 Exchange Online 信箱和獨立 Exchange Online Protection （EOP）組織，但沒有 Exchange Online 信箱的電子郵件支援透過 IPv6 的匿名輸入電子郵件。</span><span class="sxs-lookup"><span data-stu-id="42603-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="42603-105">來源 IPv6 電子郵件伺服器必須符合下列兩項需求：</span><span class="sxs-lookup"><span data-stu-id="42603-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="42603-106">來源 IPv6 位址必須具有有效的反向 DNS 查詢（PTR）記錄，允許目的地從 IPv6 位址中尋找功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="42603-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="42603-107">寄件者必須通過 SPF 驗證 (定義於 [RFC 7208](https://tools.ietf.org/html/rfc7208)) 或 [DKIM 驗證](https://dkim.org/) (定義於 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt))。</span><span class="sxs-lookup"><span data-stu-id="42603-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="42603-108">在您的組織可以透過 IPv6 接收匿名的輸入電子郵件之前，系統管理員必須先聯繫 Microsoft 支援人員，並要求。</span><span class="sxs-lookup"><span data-stu-id="42603-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="42603-109">如需如何開啟支援要求的指示，請參閱[聯繫支援人員以取得商務產品-系統管理](../../admin/contact-support-for-business-products.md)說明。</span><span class="sxs-lookup"><span data-stu-id="42603-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="42603-110">在您的組織中啟用匿名輸入 IPv6 郵件支援之後，郵件會透過服務提供的一般郵件篩選功能。</span><span class="sxs-lookup"><span data-stu-id="42603-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="42603-111">疑難排解</span><span class="sxs-lookup"><span data-stu-id="42603-111">Troubleshooting</span></span>

- <span data-ttu-id="42603-112">如果來源電子郵件伺服器沒有 IPv6 反向 DNS 查閱記錄，郵件將會因下列錯誤而拒絕：</span><span class="sxs-lookup"><span data-stu-id="42603-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="42603-113">450 4.7.25 服務無法使用，傳送 IPv6 位址 [2a01：111： f200：2004：： 240] 必須具有反向 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="42603-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="42603-114">如果寄件者未通過 SPF 或 DKIM 驗證，郵件將會因下列錯誤而拒絕：</span><span class="sxs-lookup"><span data-stu-id="42603-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="42603-115">450 4.7.26 服務無法使用。傳送的郵件 IPv6 [2a01：111： f200：2004：： 240] 必須通過 SPF 或 DKIM 驗證。</span><span class="sxs-lookup"><span data-stu-id="42603-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="42603-116">如果您在加入宣告之前嘗試接收匿名 IPv6 郵件，郵件將會因下列錯誤而拒絕：</span><span class="sxs-lookup"><span data-stu-id="42603-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="42603-117">550 5.2.1 服務無法使用，[contoso.com] 不接受透過 IPv6 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="42603-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="42603-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="42603-118">Related topics</span></span>

[<span data-ttu-id="42603-119">支援 DKIM 簽署郵件的驗證</span><span class="sxs-lookup"><span data-stu-id="42603-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)