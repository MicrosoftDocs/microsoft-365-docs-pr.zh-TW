---
title: 輸出郵件的高風險傳遞集區
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 瞭解高風險傳遞集區如何用來保護 Microsoft 365 資料中心的電子郵件伺服器信譽。
ms.openlocfilehash: 7fb4788361534335be1e07bae44ed7511bebe434
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638031"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="031a8-103">輸出郵件的高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="031a8-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="031a8-104">Microsoft 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="031a8-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="031a8-105">例如，在內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Microsoft 365 傳送輸出郵件，或遭到受損的 Microsoft 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="031a8-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="031a8-106">這些案例會產生出現在協力廠商封鎖清單上之受影響的 Microsoft 365 datacenter 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="031a8-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="031a8-107">使用這些封鎖清單的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="031a8-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="031a8-108">若要防止這種情況，所有來自 Microsoft 365 datacenter server 但決定為垃圾郵件的外寄郵件，或超過[服務](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)之傳送限制或[輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)的所有外寄郵件都會透過_高風險傳遞集_區來傳送。</span><span class="sxs-lookup"><span data-stu-id="031a8-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="031a8-109">「高風險傳遞集區」是僅用於傳送「低品質」郵件（例如，垃圾郵件和[退信攻擊](backscatter-messages-and-eop.md)）的外寄電子郵件的次要 IP 位址集區。</span><span class="sxs-lookup"><span data-stu-id="031a8-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="031a8-110">使用 [高風險傳遞集區]，可防止輸出電子郵件的一般 IP 位址集區傳送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="031a8-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="031a8-111">外寄電子郵件的一般 IP 位址集區維持「高品質」郵件的信譽，這會降低這些 IP 位址會出現在 IP 封鎖清單上的可能性。</span><span class="sxs-lookup"><span data-stu-id="031a8-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="031a8-112">在此情況下，高風險傳遞集區中的 IP 位址會保留在 IP 封鎖清單上，但這是由設計所組成。</span><span class="sxs-lookup"><span data-stu-id="031a8-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="031a8-113">不會保證傳遞給預定的收件者，因為許多電子郵件組織不會接受高風險傳遞集區中的郵件。</span><span class="sxs-lookup"><span data-stu-id="031a8-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="031a8-114">如需詳細資訊，請參閱[控制輸出垃圾郵件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="031a8-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="031a8-115">來源電子郵件網域沒有記錄，而且公用 DNS 中未定義任何 MX 記錄的郵件，無論其垃圾郵件或傳送限制，都永遠都透過高風險傳遞集區路由傳送。</span><span class="sxs-lookup"><span data-stu-id="031a8-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="031a8-116">退回郵件</span><span class="sxs-lookup"><span data-stu-id="031a8-116">Bounce messages</span></span>

<span data-ttu-id="031a8-117">輸出的高風險傳遞集區可管理所有未傳遞回報的傳遞（也稱為 NDRs、退回郵件、傳遞狀態通知或 DSNs）。</span><span class="sxs-lookup"><span data-stu-id="031a8-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="031a8-118">NDRs 中的電湧可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="031a8-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="031a8-119">會影響使用服務之客戶之一的電子欺騙活動。</span><span class="sxs-lookup"><span data-stu-id="031a8-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="031a8-120">目錄收集攻擊。</span><span class="sxs-lookup"><span data-stu-id="031a8-120">A directory harvest attack.</span></span>

- <span data-ttu-id="031a8-121">垃圾郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="031a8-121">A spam attack.</span></span>

- <span data-ttu-id="031a8-122">欺詐的電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="031a8-122">A rogue email server.</span></span>

<span data-ttu-id="031a8-123">所有這些問題都會造成服務處理的 NDRs 數量突然增加。</span><span class="sxs-lookup"><span data-stu-id="031a8-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="031a8-124">許多情況下，這些 NDRs 似乎是對其他電子郵件伺服器和服務（也稱為_[退信攻擊](backscatter-messages-and-eop.md)_）的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="031a8-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
