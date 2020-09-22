---
title: 輸出傳遞集區
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 瞭解如何使用傳遞集區來保護 Microsoft 365 資料中心的電子郵件伺服器信譽。
ms.openlocfilehash: b3016be7c1887536fe3e742b5ab4ec598b6a5f89
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201486"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="95570-103">輸出傳遞集區</span><span class="sxs-lookup"><span data-stu-id="95570-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="95570-104">Microsoft 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="95570-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="95570-105">例如，在內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Microsoft 365 傳送輸出郵件，或遭到受損的 Microsoft 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="95570-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="95570-106">攻擊者也會嘗試透過 Microsoft 365 轉寄來轉送郵件，以避免偵測。</span><span class="sxs-lookup"><span data-stu-id="95570-106">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="95570-107">這些案例會產生出現在協力廠商封鎖清單上之受影響的 Microsoft 365 datacenter 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="95570-107">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="95570-108">使用這些封鎖清單的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="95570-108">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="95570-109">高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="95570-109">High-risk delivery pool</span></span>
<span data-ttu-id="95570-110">若要防止這種情況，所有來自 Microsoft 365 datacenter server 但決定為垃圾郵件的外寄郵件，或超過 [服務](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) 之傳送限制或 [輸出垃圾郵件原則](configure-the-outbound-spam-policy.md) 的所有外寄郵件都會透過 _高風險傳遞集_區來傳送。</span><span class="sxs-lookup"><span data-stu-id="95570-110">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="95570-111">「高風險傳遞集區」是外寄電子郵件的個別 IP 位址集區，只用于傳送「低品質」郵件 (例如，垃圾郵件和 [退信攻擊](backscatter-messages-and-eop.md)) 。</span><span class="sxs-lookup"><span data-stu-id="95570-111">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="95570-112">使用 [高風險傳遞集區]，可防止輸出電子郵件的一般 IP 位址集區傳送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="95570-112">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="95570-113">外寄電子郵件的一般 IP 位址集區維持「高品質」郵件的信譽，這會降低這些 IP 位址會出現在 IP 封鎖清單上的可能性。</span><span class="sxs-lookup"><span data-stu-id="95570-113">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="95570-114">在此情況下，高風險傳遞集區中的 IP 位址會保留在 IP 封鎖清單上，但這是由設計所組成。</span><span class="sxs-lookup"><span data-stu-id="95570-114">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="95570-115">不會保證傳遞給預定的收件者，因為許多電子郵件組織不會接受高風險傳遞集區中的郵件。</span><span class="sxs-lookup"><span data-stu-id="95570-115">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="95570-116">如需詳細資訊，請參閱 [控制輸出垃圾郵件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="95570-116">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="95570-117">來源電子郵件網域沒有記錄，而且公用 DNS 中未定義任何 MX 記錄的郵件，無論其垃圾郵件或傳送限制，都永遠都透過高風險傳遞集區路由傳送。</span><span class="sxs-lookup"><span data-stu-id="95570-117">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="95570-118">退回郵件</span><span class="sxs-lookup"><span data-stu-id="95570-118">Bounce messages</span></span>

<span data-ttu-id="95570-119">輸出的高風險傳遞集區可管理所有未傳遞回報 (也稱為 NDRs、退回郵件、傳遞狀態通知或 DSNs) 的傳遞。</span><span class="sxs-lookup"><span data-stu-id="95570-119">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="95570-120">NDRs 中的電湧可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="95570-120">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="95570-121">會影響使用服務之客戶之一的電子欺騙活動。</span><span class="sxs-lookup"><span data-stu-id="95570-121">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="95570-122">目錄收集攻擊。</span><span class="sxs-lookup"><span data-stu-id="95570-122">A directory harvest attack.</span></span>
- <span data-ttu-id="95570-123">垃圾郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="95570-123">A spam attack.</span></span>
- <span data-ttu-id="95570-124">欺詐的電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="95570-124">A rogue email server.</span></span>

<span data-ttu-id="95570-125">所有這些問題都會造成服務處理的 NDRs 數量突然增加。</span><span class="sxs-lookup"><span data-stu-id="95570-125">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="95570-126">許多情況下，這些 NDRs 似乎是對其他電子郵件伺服器和服務 (也稱為 _[退信攻擊](backscatter-messages-and-eop.md)_) 的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="95570-126">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="95570-127">轉送集區</span><span class="sxs-lookup"><span data-stu-id="95570-127">Relay pool</span></span>

<span data-ttu-id="95570-128">轉寄或轉送到 Microsoft 365 的郵件會以特殊轉送集區傳送，因為最後目的地不應該將 Microsoft 365 視為實際寄件者。</span><span class="sxs-lookup"><span data-stu-id="95570-128">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="95570-129">請務必隔離此流量，因為 autoforwarding 或將電子郵件轉送至 Microsoft 365 時，有合法和不正確案例。</span><span class="sxs-lookup"><span data-stu-id="95570-129">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="95570-130">與高風險傳遞集區類似，中繼郵件使用個別的 IP 位址集區。</span><span class="sxs-lookup"><span data-stu-id="95570-130">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="95570-131">此位址集區不會發佈，因為它可能經常變更。</span><span class="sxs-lookup"><span data-stu-id="95570-131">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="95570-132">Microsoft 365 需要驗證原始寄件者是否合法，讓我們可以自信地傳遞轉寄的郵件。</span><span class="sxs-lookup"><span data-stu-id="95570-132">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="95570-133">為了做到這一點，電子郵件驗證 (SPF、DKIM 及) DMARC，都必須傳遞給我們的郵件。</span><span class="sxs-lookup"><span data-stu-id="95570-133">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="95570-134">在我們可驗證寄件者的情況下，我們會使用寄件者修正，協助接收器知道轉寄的郵件來自信任的來源。</span><span class="sxs-lookup"><span data-stu-id="95570-134">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="95570-135">您可以深入瞭解該作業的運作方式及可執行檔動作，以協助確保傳送網域在 [寄件者修正模式中 (SRS) ](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)中的驗證。</span><span class="sxs-lookup"><span data-stu-id="95570-135">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
