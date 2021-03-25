---
title: 郵件流程圖
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 合規性中心內郵件流程儀表板中的郵件流程地圖，以視覺化和追蹤郵件如何透過連接器傳送或從其組織傳送，而不使用連接器。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204928"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="ec928-103">安全性 & 規範中心內的郵件流程地圖</span><span class="sxs-lookup"><span data-stu-id="ec928-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec928-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="ec928-104">**Applies to**</span></span>
- [<span data-ttu-id="ec928-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ec928-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ec928-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="ec928-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ec928-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec928-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ec928-108">[安全性 & 合規性中心](https://protection.office.com)的 [郵件流程儀表板](mail-flow-insights-v2.md)中的 **郵件流程地圖**，可提供郵件透過您的組織流動的洞察力。</span><span class="sxs-lookup"><span data-stu-id="ec928-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="ec928-109">您可以使用此資訊來瞭解模式、識別異常，並在發生問題時修正問題。</span><span class="sxs-lookup"><span data-stu-id="ec928-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![安全性 & 規範中心內郵件流程儀表板中的郵件流程對應構件](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="ec928-111">根據預設，構件會顯示上一天的郵件流程模式，稱為「 *Sankey* 圖表」圖表。</span><span class="sxs-lookup"><span data-stu-id="ec928-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="ec928-112">您可以使用向左箭號及向右箭號向右箭號 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) 來顯示不同天的資訊。</span><span class="sxs-lookup"><span data-stu-id="ec928-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="ec928-113">每個不同的色彩都代表不同輸入或輸出連接器上的郵件流程 (或不使用連接器) 。</span><span class="sxs-lookup"><span data-stu-id="ec928-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="ec928-114">如果您將游標懸停在特定色彩上，就會針對該類型的連接器顯示郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ec928-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="ec928-115">郵件流程地圖的報表檢視</span><span class="sxs-lookup"><span data-stu-id="ec928-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="ec928-116">按一下 [ **郵件流程地圖** ] 小工具，將會帶您前往 **郵件流程地圖** 報告。</span><span class="sxs-lookup"><span data-stu-id="ec928-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="ec928-117">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="ec928-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="ec928-118">**顯示資料：概述**：這基本上是更大的小工具視圖。</span><span class="sxs-lookup"><span data-stu-id="ec928-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="ec928-119">如果您將游標懸停在特定色彩上，就會針對該類型的連接器顯示郵件數目。</span><span class="sxs-lookup"><span data-stu-id="ec928-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![郵件流程地圖報告中的概覽視圖](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="ec928-121">**顯示資料：詳細資料**：此視圖顯示連接器和目的地網域的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ec928-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="ec928-122">會列出上方寄件者和收件者網域，其餘部分則放入 **其他** 人。</span><span class="sxs-lookup"><span data-stu-id="ec928-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="ec928-123">如果您將游標懸停在特定的色彩及區段上，就會顯示訊息的數目。</span><span class="sxs-lookup"><span data-stu-id="ec928-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![郵件流程地圖報告中的詳細資料檢視](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="ec928-125">如果您按一下報表檢視中的 [ **篩選器** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="ec928-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ec928-126">若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [ **要求下載**]。</span><span class="sxs-lookup"><span data-stu-id="ec928-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="ec928-127">相關的洞察力會顯示在郵件流程地圖底下（如果有的話） (例如， [修正可能的郵件迴圈洞察力](mfi-mail-loop-insight.md)) 。</span><span class="sxs-lookup"><span data-stu-id="ec928-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="ec928-128">郵件流程地圖的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="ec928-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="ec928-129">如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ec928-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="ec928-130">**Date**</span><span class="sxs-lookup"><span data-stu-id="ec928-130">**Date**</span></span>
- <span data-ttu-id="ec928-131">**類別**</span><span class="sxs-lookup"><span data-stu-id="ec928-131">**Category**</span></span>
- <span data-ttu-id="ec928-132">**連接器/協力廠商服務提供者**</span><span class="sxs-lookup"><span data-stu-id="ec928-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="ec928-133">**寄件者/收件者網域**</span><span class="sxs-lookup"><span data-stu-id="ec928-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="ec928-134">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="ec928-134">**Message count**</span></span>

<span data-ttu-id="ec928-135">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="ec928-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ec928-136">如果您選取某列，則會在浮出控制項中顯示類似的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="ec928-136">If you select a row, similar details are shown in a flyout:</span></span>

![從郵件流程地圖的詳細資料表格中彈出詳細資料](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="ec928-138">若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [ **要求下載**]。</span><span class="sxs-lookup"><span data-stu-id="ec928-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="ec928-139">若要回到 [報告] 視圖，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="ec928-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec928-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ec928-140">See also</span></span>

<span data-ttu-id="ec928-141">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="ec928-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
