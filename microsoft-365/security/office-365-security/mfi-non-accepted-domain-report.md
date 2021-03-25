---
title: 郵件流程儀表板中的「不公認的網域」報告
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
description: 系統管理員可以瞭解如何使用 [安全性 & 合規性中心內的郵件流程儀表板中的 [非公認的網域報告]，監控來自內部部署組織中的寄件者網域未設定 Microsoft 365 的郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204555"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="876d4-103">安全性 & 規範中心內的非公認網域報告</span><span class="sxs-lookup"><span data-stu-id="876d4-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="876d4-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="876d4-104">**Applies to**</span></span>
- [<span data-ttu-id="876d4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="876d4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="876d4-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="876d4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="876d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="876d4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="876d4-108">在 [Security & 合規性中心](https://protection.office.com)的 [郵件流程儀表板](mail-flow-insights-v2.md)中，**未接受的網域** 報告會顯示來自內部部署電子郵件組織之郵件的相關資訊，而寄件者的網域並未設定為 Microsoft 365 組織中公認的網域。</span><span class="sxs-lookup"><span data-stu-id="876d4-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="876d4-109">如果我們有資料證明這些郵件的目的是惡意的，Microsoft 365 可能會節流這些郵件。</span><span class="sxs-lookup"><span data-stu-id="876d4-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="876d4-110">因此，請務必瞭解所發生的情況，並修正問題。</span><span class="sxs-lookup"><span data-stu-id="876d4-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![安全性 & 規範中心內，郵件流程儀表板中的非公認網域小工具](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="876d4-112">不接受之網域報告的報表檢視</span><span class="sxs-lookup"><span data-stu-id="876d4-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="876d4-113">按一下 [ **非公認的網域** ] 小工具上的圖表，將會帶您前往 **非公認的網域** 報告。</span><span class="sxs-lookup"><span data-stu-id="876d4-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="876d4-114">依預設，會顯示所有受影響連接器的活動。</span><span class="sxs-lookup"><span data-stu-id="876d4-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="876d4-115">如果您按一下 [ **顯示資料**]，您可以從下拉式清單中選取特定的連接器。</span><span class="sxs-lookup"><span data-stu-id="876d4-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="876d4-116">如果您將滑鼠停留在圖表中的資料點 (day) 上，您會看到連接器的郵件總數。</span><span class="sxs-lookup"><span data-stu-id="876d4-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![不接受的網域報告中的報表檢視](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="876d4-118">非公認網域報告的詳細資料表格視圖</span><span class="sxs-lookup"><span data-stu-id="876d4-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="876d4-119">如果您按一下報表檢視中的 [ **查看詳細資料] 表格** ，會顯示下列資訊：</span><span class="sxs-lookup"><span data-stu-id="876d4-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="876d4-120">**Date**</span><span class="sxs-lookup"><span data-stu-id="876d4-120">**Date**</span></span>
- <span data-ttu-id="876d4-121">**輸入連接器名稱**</span><span class="sxs-lookup"><span data-stu-id="876d4-121">**Inbound connector name**</span></span>
- <span data-ttu-id="876d4-122">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="876d4-122">**Sender domain**</span></span>
- <span data-ttu-id="876d4-123">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="876d4-123">**Message count**</span></span>
- <span data-ttu-id="876d4-124">**範例郵件**：郵件 IDs 受影響郵件的範例。</span><span class="sxs-lookup"><span data-stu-id="876d4-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="876d4-125">如果您按一下 [詳細資料] 表格視圖中的 [ **篩選** ]，您可以指定具有 **開始日期** 和 **結束日期** 的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="876d4-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="876d4-126">若要將特定日期範圍的報告傳送至一或多個收件者，請按一下 [ **要求下載**]。</span><span class="sxs-lookup"><span data-stu-id="876d4-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="876d4-127">當您選取表格中的一列時，會出現一個快顯視窗，其中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="876d4-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="876d4-128">**Date**</span><span class="sxs-lookup"><span data-stu-id="876d4-128">**Date**</span></span>
- <span data-ttu-id="876d4-129">**輸入連接器名稱**</span><span class="sxs-lookup"><span data-stu-id="876d4-129">**Inbound connector name**</span></span>
- <span data-ttu-id="876d4-130">**寄件者網域**</span><span class="sxs-lookup"><span data-stu-id="876d4-130">**Sender domain**</span></span>
- <span data-ttu-id="876d4-131">**訊息計數**</span><span class="sxs-lookup"><span data-stu-id="876d4-131">**Message count**</span></span>
- <span data-ttu-id="876d4-132">**範例郵件**：您可以按一下 [ **View sample messages** ]，以查看受影響郵件之範例的 [郵件追蹤](message-trace-scc.md) 結果。</span><span class="sxs-lookup"><span data-stu-id="876d4-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![在 [非公認的網域] 報告中，選取 [詳細資料表格] 視圖中的列之後的詳細資料彈出列表](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="876d4-134">若要回到 [報告] 視圖，請按一下 [ **查看報告**]。</span><span class="sxs-lookup"><span data-stu-id="876d4-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="876d4-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="876d4-135">Related topics</span></span>

<span data-ttu-id="876d4-136">如需郵件流程儀表板中其他真知灼見的詳細資訊，請參閱 [Security & 合規性中心中的郵件流程洞察力](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="876d4-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
