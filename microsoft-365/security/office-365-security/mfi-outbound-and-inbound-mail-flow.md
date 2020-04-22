---
title: 輸出和輸入郵件流程
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 系統管理員可以在安全性與合規性中心中的郵件流程儀表板了解輸出和輸入郵件流程小工具。
ms.openlocfilehash: a1070783f60edf2de62d78c3094e9c20e3dd26f3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635193"
---
# <a name="outbound-and-inbound-mail-flow"></a><span data-ttu-id="4ba9b-103">輸出和輸入郵件流程</span><span class="sxs-lookup"><span data-stu-id="4ba9b-103">Outbound and inbound mail flow</span></span>

<span data-ttu-id="4ba9b-104">**輸出和輸入郵件流程**小工具會將**連接器報告**和先前的 **TLS 概觀報告**集中在一個位置。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-104">The **Outbound and inbound mail flow** widget combines the information from the **Connector Report** and the former **TLS Overview Report** in one place.</span></span>

![安全性與合規性中心內郵件流程儀表板的輸出和輸入郵件流程報告](../../media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

<span data-ttu-id="4ba9b-106">小工具中的資訊會與 Office 365 中的連接器和 TLS 郵件保護相關。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-106">The information in the widget is related to connectors and TLS message protection in Office 365.</span></span> <span data-ttu-id="4ba9b-107">如需相關資訊，請參閱這些主題：</span><span class="sxs-lookup"><span data-stu-id="4ba9b-107">For more information, see these topics:</span></span>

- [<span data-ttu-id="4ba9b-108">使用 Office 365 中的連接器設定郵件流程</span><span class="sxs-lookup"><span data-stu-id="4ba9b-108">Configure mail flow using connectors in Office 365</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [<span data-ttu-id="4ba9b-109">Exchange Online 如何使用 TLS 來保護 Office 365 中的電子郵件連線</span><span class="sxs-lookup"><span data-stu-id="4ba9b-109">How Exchange Online uses TLS to secure email connections in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="4ba9b-110">傳輸中郵件保護 (使用 TLS)</span><span class="sxs-lookup"><span data-stu-id="4ba9b-110">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="4ba9b-111">**輸出和輸入郵件流程**構件會顯示在您的組織中傳遞郵件時，用於連線的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-111">The **Outbound and inbound mail flow** widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="4ba9b-112">與其他電子郵件服務建立的連線，若兩端都提供 TLS，則會由 TLS 進行加密。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-112">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="4ba9b-113">小工具會提供上一週的郵件流程快照。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-113">The widget offers a snapshot of the last week of mail flow.</span></span> <span data-ttu-id="4ba9b-114">當您按一下 [檢視詳細資料]\*\*\*\* 時，**傳輸中郵件保護 (使用 TLS)** 彈出頁面會針對進入和離開您組織的郵件顯示 TLS 保護。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-114">When you click **View Details**, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![安全性與合規性中心內的傳輸中郵件保護 (使用 TLS) 彈出畫面](../../media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

<span data-ttu-id="4ba9b-116">目前，TLS 1.2 是 Office 365 提供的最安全 TLS 版本。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-116">Currently, TLS 1.2 is the most secure version of TLS that's offered by Office 365.</span></span> <span data-ttu-id="4ba9b-117">通常，您必須知道用於合規性稽核的 TLS 加密為何。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-117">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="4ba9b-118">您可能與來源和目的地電子郵件伺服器都沒有直接關係 (您沒有，Microsoft 也沒有)，因此您沒有許多選項可改善那些伺服器使用的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-118">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="4ba9b-119">不過，您可以使用 [連接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)，以確保在您電子郵件伺服器與 Office 365 之間傳送的郵件是使用最適合的 TLS 保護。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-119">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Office 365.</span></span> <span data-ttu-id="4ba9b-120">在 Microsoft 365 和您自己的電子郵件伺服器之間或屬於合作夥伴的伺服器之間的郵件流程，通常比一般郵件更為重要且敏感，所以您會想要對這些郵件套用額外的安全性和 vigilance。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-120">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span> <span data-ttu-id="4ba9b-121">您可以升級或修正您自己的電子郵件伺服器，以改善正在使用的 TLS 加密，或連絡合作夥伴來執行此相同動作。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-121">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="4ba9b-122">**連接器報告**會顯示使用 Microsoft 365 連接器之郵件的郵件流程數量和 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-122">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

## <a name="connector-report"></a><span data-ttu-id="4ba9b-123">連接器報告</span><span class="sxs-lookup"><span data-stu-id="4ba9b-123">Connector report</span></span>

<span data-ttu-id="4ba9b-124">當您從 [**傳輸中受保護的郵件] （透過 TLS）** 浮出控制項中按一下 [**連接器報告**] 連結時，報告會顯示從您的組織中使用連接器來傳遞及傳送之郵件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-124">When you click on the **Connector Report** link from the **Message protected in transit (by TLS)** flyout, the report displays information about messages that are delivered to and from your organization using connectors.</span></span> <span data-ttu-id="4ba9b-125">您可以使用您自己的電子郵件伺服器與 Microsoft 365 或您的夥伴的伺服器和 Office 365 之間的連接器。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-125">You use connectors between your own email servers and Microsoft 365 or your partner's servers and Office 365.</span></span> <span data-ttu-id="4ba9b-126">這會提供每個連接器的郵件量，以及用於連線的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-126">The message volume for each connector and the TLS encryption for the connection is available.</span></span> <span data-ttu-id="4ba9b-127">此外，您也可以在未使用連接器的情況下，查看在 Microsoft 365 中傳送或接收的郵件資料。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-127">In addition, you can also view data for messages that were sent or received in Microsoft 365 without using a connector.</span></span>

<span data-ttu-id="4ba9b-128">[郵件流程]\*\*\*\* 檢視會顯示過去一周內透過連接器進行的郵件量。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-128">The **Mail Flow** view shows the volume of messages through the connector for the past week.</span></span> <span data-ttu-id="4ba9b-129">若要變更日期範圍，請選取 [篩選]\*\*\*\*，您可以在此將範圍增加到最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-129">You can change the date range by selecting **Filter** where you can increase the range to a maximum of 30 days.</span></span> <span data-ttu-id="4ba9b-130">[**所有郵件流程**] 視圖會透過所有連接器顯示組織中的所有郵件流程。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-130">The **All Mail Flow** view shows all mail flow to and from your organization through all connectors.</span></span> <span data-ttu-id="4ba9b-131">您可以按照名稱在下拉式功能表中選取特定的連接器。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-131">You can select a specific connector by name in the drop down menu.</span></span>

<span data-ttu-id="4ba9b-132">您可以從下拉式清單中選取 [TLS 使用狀況]\*\*\*\* 檢視，以查看透過連接器進行的 TLS 郵件保護細項。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-132">You can select the **TLS usage** view from the drop down to see the breakdown of TLS protection for messages through the connector.</span></span> <span data-ttu-id="4ba9b-133">就像 **TLS 概觀報告**一樣，此檢視會顯示不同 TLS 版本的百分比。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-133">As with the **TLS Overview Report** report, this view shows the percentage of the different TLS versions.</span></span> <span data-ttu-id="4ba9b-134">在 TLS 1.0 連線中，您必須先將電子郵件伺服器或合作夥伴的伺服器升級或修正，以避免 Office 365 終將不支援 TLS 1.0 的問題。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-134">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Office 365.</span></span> <span data-ttu-id="4ba9b-135">如需詳細資訊，請參閱[關於 Office 365 中加密的技術參考細節](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-135">For more information, see [Technical reference details about encryption in Office 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption).</span></span>

<span data-ttu-id="4ba9b-136">深入解析會指向連接器，協助您注意到連接器的潛在 TLS 加密問題。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-136">Insights point to connectors to help draw your attention to potential TLS encryption problems for the connector.</span></span> <span data-ttu-id="4ba9b-137">這些深入解析為：**沒有 TLS 超過 25%**，或 **TLS 1.0 高於 50%**。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-137">The insights are: **No TLS is over 25%** or **TLS 1.0 is above 50%**.</span></span> <span data-ttu-id="4ba9b-138">如果您看到這些深入見解，您需要調查與連接器相關聯的電子郵件伺服器，或與合作夥伴組織聯繫。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-138">If you see these insights, you need to investigate your email servers that are associated with the connector, or reach out to your partner organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ba9b-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4ba9b-139">See also</span></span>

<span data-ttu-id="4ba9b-140">如需郵件流量儀表板中其他郵件流程深入解析之詳細資訊，請參閱[安全性與合規性中心中郵件流程深入解析](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-140">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
