---
title: 郵件流程儀表板中的輸出和輸入郵件流程洞察力
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 系統管理員可以在安全性 & 合規性中心的郵件流程儀表板中瞭解輸出和輸入郵件流程的洞察力。
ms.openlocfilehash: cff7c3a14b62475903729f4528652f192c2da09f
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877666"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="dc019-103">安全性 & 規範中心內的輸出和輸入郵件流程洞察力</span><span class="sxs-lookup"><span data-stu-id="dc019-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dc019-104">[安全性 & 合規性中心](https://protection.office.com)內的 [郵件流程儀表板](mail-flow-insights-v2.md)中的 **輸出和輸入郵件流程** 洞察力，結合了 [連接器報告](view-mail-flow-reports.md#connector-report)中的資訊和舊的 **TLS 總覽報告** 中的一個位置。</span><span class="sxs-lookup"><span data-stu-id="dc019-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="dc019-105">在您的組織中傳遞郵件時，構件會顯示用來進行連線的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="dc019-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="dc019-106">與其他電子郵件服務建立的連線，若兩端都提供 TLS，則會由 TLS 進行加密。</span><span class="sxs-lookup"><span data-stu-id="dc019-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="dc019-107">小工具會提供上一週的郵件流程快照。</span><span class="sxs-lookup"><span data-stu-id="dc019-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![安全性 & 規範中心內的郵件流程儀表板中的輸出和輸入郵件流程構件](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="dc019-109">小工具中的資訊與 Microsoft 365 中的連接器和 TLS 郵件保護有關。</span><span class="sxs-lookup"><span data-stu-id="dc019-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="dc019-110">如需相關資訊，請參閱這些主題：</span><span class="sxs-lookup"><span data-stu-id="dc019-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="dc019-111">使用連接器設定郵件流程</span><span class="sxs-lookup"><span data-stu-id="dc019-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="dc019-112">Exchange Online 如何使用 TLS 來保護電子郵件連線</span><span class="sxs-lookup"><span data-stu-id="dc019-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="dc019-113">Microsoft 365 中有關加密的技術參考詳細資料</span><span class="sxs-lookup"><span data-stu-id="dc019-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="dc019-114">傳輸中郵件保護 (使用 TLS)</span><span class="sxs-lookup"><span data-stu-id="dc019-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="dc019-115">當您按一下小工具上的 [ **查看詳細資料** ] 時， **在傳輸中 (TLS)** 浮出的郵件會向您顯示進入及離開組織之訊息的 TLS 保護。</span><span class="sxs-lookup"><span data-stu-id="dc019-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![在您按一下輸出和輸入的電子郵件小工具上的 [查看詳細資料] 之後， (以 TLS) 浮出的方式保護的郵件](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="dc019-117">目前，TLS 1.2 是 Microsoft 365 提供的最安全 TLS 版本。</span><span class="sxs-lookup"><span data-stu-id="dc019-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="dc019-118">通常，您必須知道用於合規性稽核的 TLS 加密為何。</span><span class="sxs-lookup"><span data-stu-id="dc019-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="dc019-119">您可能與來源和目的地電子郵件伺服器都沒有直接關係 (您沒有，Microsoft 也沒有)，因此您沒有許多選項可改善那些伺服器使用的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="dc019-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="dc019-120">不過，您可以使用 [連接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) ，以確保您的電子郵件伺服器和 Microsoft 365 之間傳送的郵件可使用的最佳 TLS 保護。</span><span class="sxs-lookup"><span data-stu-id="dc019-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="dc019-121">在 Microsoft 365 和您自己的電子郵件伺服器之間或屬於合作夥伴的伺服器之間的郵件流程，通常比一般郵件更為重要且敏感，所以您會想要對這些郵件套用額外的安全性和 vigilance。</span><span class="sxs-lookup"><span data-stu-id="dc019-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="dc019-122">您可以升級或修正您自己的電子郵件伺服器，以改善正在使用的 TLS 加密，或連絡合作夥伴來執行此相同動作。</span><span class="sxs-lookup"><span data-stu-id="dc019-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="dc019-123">**連接器報告** 會顯示使用 Microsoft 365 連接器之郵件的郵件流程數量和 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="dc019-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="dc019-124">您可以按一下 [ **連接器報告** ] 連結，以移至 [連接器報告](view-mail-flow-reports.md#connector-report)。</span><span class="sxs-lookup"><span data-stu-id="dc019-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="dc019-125">如果偵測到相關聯的條件， **連接器報告** 頁面上可能會提供下列深入瞭解：</span><span class="sxs-lookup"><span data-stu-id="dc019-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="dc019-126">**輸入的協力廠商連接器查看大量 TLS 1.0 郵件流程**</span><span class="sxs-lookup"><span data-stu-id="dc019-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="dc019-127">**輸入 OnPremises 連接器查看大量 TLS 1.0 郵件流程**</span><span class="sxs-lookup"><span data-stu-id="dc019-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="dc019-128">針對 TLS 1.0 連線，您實際上需要將您的電子郵件伺服器或夥伴的伺服器升級或修復，以避免 Microsoft 365 中的 TLS 1.0 支援最後已被取代的任何問題。</span><span class="sxs-lookup"><span data-stu-id="dc019-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc019-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dc019-129">See also</span></span>

<span data-ttu-id="dc019-130">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="dc019-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
