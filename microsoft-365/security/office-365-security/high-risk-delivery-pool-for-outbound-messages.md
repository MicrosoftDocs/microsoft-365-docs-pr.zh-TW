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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 瞭解如何使用傳遞集區來保護 Microsoft 365 資料中心的電子郵件伺服器信譽。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599908"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="650d8-103">輸出傳遞集區</span><span class="sxs-lookup"><span data-stu-id="650d8-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="650d8-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="650d8-104">**Applies to**</span></span>
- [<span data-ttu-id="650d8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="650d8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="650d8-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="650d8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="650d8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="650d8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="650d8-108">Microsoft 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="650d8-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="650d8-109">例如，內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Microsoft 365 傳送輸出郵件，或 Microsoft 365 帳戶遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="650d8-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="650d8-110">攻擊者也會嘗試透過 Microsoft 365 轉送來轉送郵件，以避免偵測。</span><span class="sxs-lookup"><span data-stu-id="650d8-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="650d8-111">這些案例可能會產生協力廠商 blocklists 上受影響的 Microsoft 365 datacenter 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="650d8-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="650d8-112">使用這些 blocklists 的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="650d8-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="650d8-113">高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="650d8-113">High-risk delivery pool</span></span>
<span data-ttu-id="650d8-114">若要防止這種情況，來自決定是垃圾郵件的 Microsoft 365 datacenter 伺服器的所有輸出郵件，或超過 [服務](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)之傳送限制或 [輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)的所有輸出郵件都會透過 _高風險傳遞集_ 區來傳送。</span><span class="sxs-lookup"><span data-stu-id="650d8-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="650d8-115">「高風險傳遞集區」是外寄電子郵件的個別 IP 位址集區，只用于傳送「低品質」郵件 (例如，垃圾郵件和 [退信攻擊](backscatter-messages-and-eop.md)) 。</span><span class="sxs-lookup"><span data-stu-id="650d8-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="650d8-116">使用 [高風險傳遞集區]，可防止輸出電子郵件的一般 IP 位址集區傳送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="650d8-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="650d8-117">外寄電子郵件的一般 IP 位址集區維持「高品質」郵件的信譽，這會降低這些 IP 位址會出現在 IP blocklists 上的可能性。</span><span class="sxs-lookup"><span data-stu-id="650d8-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="650d8-118">在 blocklists 中，高風險傳遞集區中的 IP 位址會保留在 IP 上的可能性，但這是設計方式。</span><span class="sxs-lookup"><span data-stu-id="650d8-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="650d8-119">不會保證傳遞給預定的收件者，因為許多電子郵件組織不會接受高風險傳遞集區中的郵件。</span><span class="sxs-lookup"><span data-stu-id="650d8-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="650d8-120">如需詳細資訊，請參閱 [控制輸出垃圾郵件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="650d8-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="650d8-121">來源電子郵件網域沒有記錄，而且公用 DNS 中未定義任何 MX 記錄的郵件，無論其垃圾郵件或傳送限制，都永遠都透過高風險傳遞集區路由傳送。</span><span class="sxs-lookup"><span data-stu-id="650d8-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="650d8-122">退回郵件</span><span class="sxs-lookup"><span data-stu-id="650d8-122">Bounce messages</span></span>

<span data-ttu-id="650d8-123">輸出的高風險傳遞集區可管理所有未傳遞回報 (也稱為 NDRs、退回郵件、傳遞狀態通知或 DSNs) 的傳遞。</span><span class="sxs-lookup"><span data-stu-id="650d8-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="650d8-124">NDRs 中的電湧可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="650d8-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="650d8-125">會影響使用服務之客戶之一的電子欺騙活動。</span><span class="sxs-lookup"><span data-stu-id="650d8-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="650d8-126">目錄收集攻擊。</span><span class="sxs-lookup"><span data-stu-id="650d8-126">A directory harvest attack.</span></span>
- <span data-ttu-id="650d8-127">垃圾郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="650d8-127">A spam attack.</span></span>
- <span data-ttu-id="650d8-128">欺詐的電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="650d8-128">A rogue email server.</span></span>

<span data-ttu-id="650d8-129">所有這些問題都會造成服務處理的 NDRs 數量突然增加。</span><span class="sxs-lookup"><span data-stu-id="650d8-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="650d8-130">許多情況下，這些 NDRs 似乎是對其他電子郵件伺服器和服務 (也稱為 _[退信攻擊](backscatter-messages-and-eop.md)_) 的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="650d8-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
