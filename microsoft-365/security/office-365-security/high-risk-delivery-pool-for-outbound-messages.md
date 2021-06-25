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
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137712"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="36572-103">輸出傳遞集區</span><span class="sxs-lookup"><span data-stu-id="36572-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="36572-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="36572-104">**Applies to**</span></span>
- [<span data-ttu-id="36572-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="36572-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="36572-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="36572-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="36572-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36572-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="36572-108">Microsoft 365 資料中心的電子郵件伺服器可能會暫時 guilty 寄送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="36572-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="36572-109">例如，內部部署電子郵件組織中的惡意程式碼或惡意垃圾郵件攻擊，會透過 Microsoft 365 傳送輸出郵件，或 Microsoft 365 帳戶遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="36572-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="36572-110">攻擊者也會嘗試透過 Microsoft 365 轉送來轉送郵件，以避免偵測。</span><span class="sxs-lookup"><span data-stu-id="36572-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="36572-111">這些案例可能會產生協力廠商 blocklists 上受影響的 Microsoft 365 datacenter 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="36572-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="36572-112">使用這些 blocklists 的目的地電子郵件組織會拒絕來自這些郵件來源的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="36572-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="36572-113">高風險傳遞集區</span><span class="sxs-lookup"><span data-stu-id="36572-113">High-risk delivery pool</span></span>
<span data-ttu-id="36572-114">若要防止這種情況，來自決定是垃圾郵件的 Microsoft 365 datacenter 伺服器的所有輸出郵件，或超過 [服務](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)之傳送限制或 [輸出垃圾郵件原則](configure-the-outbound-spam-policy.md)的所有輸出郵件都會透過 _高風險傳遞集_ 區來傳送。</span><span class="sxs-lookup"><span data-stu-id="36572-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="36572-115">「高風險傳遞集區」是外寄電子郵件的個別 IP 位址集區，只用于傳送「低品質」郵件 (例如，垃圾郵件和 [退信攻擊](backscatter-messages-and-eop.md)) 。</span><span class="sxs-lookup"><span data-stu-id="36572-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="36572-116">使用 [高風險傳遞集區]，可防止輸出電子郵件的一般 IP 位址集區傳送垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="36572-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="36572-117">外寄電子郵件的一般 IP 位址集區維持「高品質」郵件的信譽，這會降低這些 IP 位址會出現在 IP blocklists 上的可能性。</span><span class="sxs-lookup"><span data-stu-id="36572-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="36572-118">在 blocklists 中，高風險傳遞集區中的 IP 位址會保留在 IP 上的可能性，但這是設計方式。</span><span class="sxs-lookup"><span data-stu-id="36572-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="36572-119">不會保證傳遞給預定的收件者，因為許多電子郵件組織不會接受高風險傳遞集區中的郵件。</span><span class="sxs-lookup"><span data-stu-id="36572-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="36572-120">如需詳細資訊，請參閱 [控制輸出垃圾郵件](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="36572-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36572-121">來源電子郵件網域沒有記錄，而且公用 DNS 中未定義任何 MX 記錄的郵件，無論其垃圾郵件或傳送限制，都永遠都透過高風險傳遞集區路由傳送。</span><span class="sxs-lookup"><span data-stu-id="36572-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="36572-122">退回郵件</span><span class="sxs-lookup"><span data-stu-id="36572-122">Bounce messages</span></span>

<span data-ttu-id="36572-123">輸出的高風險傳遞集區可管理所有未傳遞回報 (也稱為 NDRs、退回郵件、傳遞狀態通知或 DSNs) 的傳遞。</span><span class="sxs-lookup"><span data-stu-id="36572-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="36572-124">NDRs 中的電湧可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="36572-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="36572-125">會影響使用服務之客戶之一的電子欺騙活動。</span><span class="sxs-lookup"><span data-stu-id="36572-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="36572-126">目錄收集攻擊。</span><span class="sxs-lookup"><span data-stu-id="36572-126">A directory harvest attack.</span></span>
- <span data-ttu-id="36572-127">垃圾郵件攻擊。</span><span class="sxs-lookup"><span data-stu-id="36572-127">A spam attack.</span></span>
- <span data-ttu-id="36572-128">欺詐的電子郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="36572-128">A rogue email server.</span></span>

<span data-ttu-id="36572-129">所有這些問題都會造成服務處理的 NDRs 數量突然增加。</span><span class="sxs-lookup"><span data-stu-id="36572-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="36572-130">許多情況下，這些 NDRs 似乎是對其他電子郵件伺服器和服務 (也稱為 _[退信攻擊](backscatter-messages-and-eop.md)_) 的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="36572-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="36572-131">轉送集區</span><span class="sxs-lookup"><span data-stu-id="36572-131">Relay pool</span></span>

<span data-ttu-id="36572-132">透過特定案例中的 Microsoft 365 轉寄或轉送的郵件，將會使用特殊轉送集區傳送，因為目的地不應視為實際寄件者 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="36572-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="36572-133">請務必隔離此電子郵件流量，因為自動轉寄或轉寄電子郵件 Microsoft 365 以外的情況會有合法且不正確案例。</span><span class="sxs-lookup"><span data-stu-id="36572-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="36572-134">與高風險傳遞集區類似，中繼郵件使用個別的 IP 位址集區。</span><span class="sxs-lookup"><span data-stu-id="36572-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="36572-135">此位址集區不會發佈，因為它可能經常變更，而且不是 Microsoft 365 發佈的 SPF 記錄的一部分。</span><span class="sxs-lookup"><span data-stu-id="36572-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="36572-136">Microsoft 365 需要驗證原始寄件者是否合法，讓我們能夠滿懷信心地傳遞轉寄的郵件。</span><span class="sxs-lookup"><span data-stu-id="36572-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="36572-137">轉寄/轉送郵件應該符合下列其中一個準則，以避免使用轉送集區：</span><span class="sxs-lookup"><span data-stu-id="36572-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="36572-138">輸出寄件者位於 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中。</span><span class="sxs-lookup"><span data-stu-id="36572-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="36572-139">當郵件來自 Microsoft 365 時，SPF 會通過。</span><span class="sxs-lookup"><span data-stu-id="36572-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="36572-140">當郵件來自 Microsoft 365 時，寄件者網域上的 DKIM 會傳送。</span><span class="sxs-lookup"><span data-stu-id="36572-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="36572-141">您可以查看郵件是透過轉送集區傳送，方法是查看輸出伺服器 IP (轉送集區將會在 40.95.0.0/16 範圍內) ，或是查看 (名稱) 中的外寄伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="36572-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="36572-142">在我們可驗證寄件者的情況下，我們會使用寄件者修正配置 (SRS) 協助收件者的電子郵件系統知道轉寄的郵件來自信任的來源。</span><span class="sxs-lookup"><span data-stu-id="36572-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="36572-143">您可以深入瞭解該作業的運作方式及可執行檔動作，以協助確保傳送網域在 Office 365 中的[寄件者修正模式 (SRS) 中](/office365/troubleshoot/antispam/sender-rewriting-scheme)傳遞驗證。</span><span class="sxs-lookup"><span data-stu-id="36572-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="36572-144">若要讓 DKIM 正常運作，請確定啟用 DKIM 以傳送網域。</span><span class="sxs-lookup"><span data-stu-id="36572-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="36572-145">例如，fabrikam.com 是 contoso.com 的一部分，且是在組織的公認的網域中定義的。</span><span class="sxs-lookup"><span data-stu-id="36572-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="36572-146">如果郵件寄件者是 sender@fabrikam.com，必須啟用 DKIM 以進行 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="36572-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="36572-147">您可以閱讀如何啟用 at [DKIM，以驗證從您的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="36572-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="36572-148">若要新增自訂網域，請依照[add a domain to Microsoft 365](../../admin/setup/add-domain.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="36572-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>
