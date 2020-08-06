---
title: 郵件流程地圖
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用安全性 & 合規性中心內郵件流程儀表板中的郵件流程地圖，以視覺化和追蹤郵件如何透過連接器傳送或從其組織傳送，而不使用連接器。
ms.openlocfilehash: 2996227de3e0141635522ada4e41f2e8e65e9040
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577672"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="496b7-103">安全性 & 規範中心內的郵件流程地圖</span><span class="sxs-lookup"><span data-stu-id="496b7-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="496b7-104">安全性 & 合規性中心的[郵件流程儀表板](mail-flow-insights-v2.md)中的**郵件流程地圖**，可提供郵件透過您的組織流動的洞察力。</span><span class="sxs-lookup"><span data-stu-id="496b7-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="496b7-105">您可以使用此資訊來瞭解模式、識別異常，並在發生問題時修正問題。</span><span class="sxs-lookup"><span data-stu-id="496b7-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![安全性 & 規範中心內郵件流程儀表板中的郵件流程對應構件](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="496b7-107">根據預設，構件會顯示上一天的郵件流程模式，稱為「 *Sankey*圖表」圖表。</span><span class="sxs-lookup"><span data-stu-id="496b7-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="496b7-108">您可以使用向左箭號及向右箭號向右箭號 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) 來顯示不同天的資訊。</span><span class="sxs-lookup"><span data-stu-id="496b7-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="496b7-109">每個不同的色彩都代表不同輸入或輸出連接器上的郵件流程 (或不使用連接器) 。</span><span class="sxs-lookup"><span data-stu-id="496b7-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="496b7-110">如果您將游標懸停在特定色彩上，就會針對該類型的連接器顯示郵件數目。</span><span class="sxs-lookup"><span data-stu-id="496b7-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="496b7-111">郵件流程地圖的報表檢視</span><span class="sxs-lookup"><span data-stu-id="496b7-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="496b7-112">按一下 [**郵件流程地圖**] 小工具，將會帶您前往**郵件流程地圖**報告。</span><span class="sxs-lookup"><span data-stu-id="496b7-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="496b7-113">報表檢視提供下列圖表：</span><span class="sxs-lookup"><span data-stu-id="496b7-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="496b7-114">**顯示資料：概述**：這基本上是更大的小工具視圖。</span><span class="sxs-lookup"><span data-stu-id="496b7-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="496b7-115">如果您將游標懸停在特定色彩上，就會針對該類型的連接器顯示郵件數目。</span><span class="sxs-lookup"><span data-stu-id="496b7-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![郵件流程地圖報告中的概覽視圖](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="496b7-117">**顯示資料：詳細資料**：此視圖顯示連接器和目的地網域的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="496b7-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="496b7-118">會列出上方寄件者和收件者網域，其餘部分則放入**其他**人。</span><span class="sxs-lookup"><span data-stu-id="496b7-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="496b7-119">如果您將游標懸停在特定的色彩及區段上，就會顯示訊息的數目。</span><span class="sxs-lookup"><span data-stu-id="496b7-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![郵件流程地圖報告中的詳細資料檢視](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="496b7-121">如果您按一下報表檢視中的 [**篩選器**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="496b7-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="496b7-122">若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [**要求下載**]。</span><span class="sxs-lookup"><span data-stu-id="496b7-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="496b7-123">相關的洞察力會顯示在郵件流程地圖底下（如果有的話） (例如，[修正可能的郵件迴圈洞察力](mfi-mail-loop-insight.md)) 。</span><span class="sxs-lookup"><span data-stu-id="496b7-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="496b7-124">郵件流程地圖的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="496b7-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="496b7-125">如果您按一下報表檢視中的 [**查看詳細資料] 表格**，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="496b7-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="496b7-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="496b7-126">**Date**</span></span>
- <span data-ttu-id="496b7-127">**類別**</span><span class="sxs-lookup"><span data-stu-id="496b7-127">**Category**</span></span>
- <span data-ttu-id="496b7-128">**連接器/協力廠商服務提供者**</span><span class="sxs-lookup"><span data-stu-id="496b7-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="496b7-129">**寄件者/收件者網域**</span><span class="sxs-lookup"><span data-stu-id="496b7-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="496b7-130">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="496b7-130">**Message count**</span></span>

<span data-ttu-id="496b7-131">如果您按一下 [詳細資料] 表格視圖中的 [**篩選**]，您可以指定具有**開始日期**和**結束日期**的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="496b7-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="496b7-132">如果您選取某列，則會在浮出控制項中顯示類似的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="496b7-132">If you select a row, similar details are shown in a flyout:</span></span>

![從郵件流程地圖的詳細資料表格中彈出詳細資料](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="496b7-134">若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [**要求下載**]。</span><span class="sxs-lookup"><span data-stu-id="496b7-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="496b7-135">若要回到 [報告] 視圖，請按一下 [**查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="496b7-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="496b7-136">請參閱</span><span class="sxs-lookup"><span data-stu-id="496b7-136">See also</span></span>

<span data-ttu-id="496b7-137">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱[Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="496b7-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
