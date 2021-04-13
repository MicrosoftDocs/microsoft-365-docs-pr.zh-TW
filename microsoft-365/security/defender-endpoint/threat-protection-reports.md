---
title: Microsoft Defender for Endpoint 中的威脅防護報告
description: 使用威脅防護報告追蹤警示偵測、類別和嚴重性
keywords: 警示偵測、來源、警示（依類別、警示嚴重性、警示分類、判斷）
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688978"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="1b07d-104">Microsoft Defender for Endpoint 中的威脅防護報告</span><span class="sxs-lookup"><span data-stu-id="1b07d-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1b07d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1b07d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1b07d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b07d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1b07d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b07d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="1b07d-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1b07d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1b07d-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1b07d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="1b07d-110">「威脅防護」報告提供組織中所產生之提醒的高層級資訊。</span><span class="sxs-lookup"><span data-stu-id="1b07d-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="1b07d-111">此報告包含趨勢資訊，顯示偵測來源、類別、嚴重性、狀態、分類，以及每次的通知決定。</span><span class="sxs-lookup"><span data-stu-id="1b07d-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="1b07d-112">儀表板分為兩個區段：</span><span class="sxs-lookup"><span data-stu-id="1b07d-112">The dashboard is structured into two sections:</span></span>

![威脅防護報告的影像](images/threat-protection-reports.png)

<span data-ttu-id="1b07d-114">區段</span><span class="sxs-lookup"><span data-stu-id="1b07d-114">Section</span></span> | <span data-ttu-id="1b07d-115">說明</span><span class="sxs-lookup"><span data-stu-id="1b07d-115">Description</span></span> 
:---|:---
<span data-ttu-id="1b07d-116">1</span><span class="sxs-lookup"><span data-stu-id="1b07d-116">1</span></span> | <span data-ttu-id="1b07d-117">警示趨勢</span><span class="sxs-lookup"><span data-stu-id="1b07d-117">Alerts trends</span></span>
<span data-ttu-id="1b07d-118">第</span><span class="sxs-lookup"><span data-stu-id="1b07d-118">2</span></span> | <span data-ttu-id="1b07d-119">警示摘要</span><span class="sxs-lookup"><span data-stu-id="1b07d-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="1b07d-120">警示趨勢</span><span class="sxs-lookup"><span data-stu-id="1b07d-120">Alert trends</span></span>
<span data-ttu-id="1b07d-121">根據預設，警示趨勢會顯示30天期間的警示資訊，最後一整天結束。</span><span class="sxs-lookup"><span data-stu-id="1b07d-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="1b07d-122">若要深入瞭解組織中發生的趨勢，您可以調整顯示的時段，以微調報告期間。</span><span class="sxs-lookup"><span data-stu-id="1b07d-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="1b07d-123">若要調整時段，請從下拉式選項中選取時間範圍：</span><span class="sxs-lookup"><span data-stu-id="1b07d-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="1b07d-124">30 天</span><span class="sxs-lookup"><span data-stu-id="1b07d-124">30 days</span></span>
- <span data-ttu-id="1b07d-125">3 個月</span><span class="sxs-lookup"><span data-stu-id="1b07d-125">3 months</span></span>
- <span data-ttu-id="1b07d-126">6 個月</span><span class="sxs-lookup"><span data-stu-id="1b07d-126">6 months</span></span>
- <span data-ttu-id="1b07d-127">自訂</span><span class="sxs-lookup"><span data-stu-id="1b07d-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="1b07d-128">這些篩選器只適用于警示趨勢區段。</span><span class="sxs-lookup"><span data-stu-id="1b07d-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="1b07d-129">它不會影響「警示摘要」區段。</span><span class="sxs-lookup"><span data-stu-id="1b07d-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="1b07d-130">警示摘要</span><span class="sxs-lookup"><span data-stu-id="1b07d-130">Alert summary</span></span>
<span data-ttu-id="1b07d-131">當警示趨勢顯示趨勢警示資訊時，警示摘要會顯示目前日期範圍內的警示資訊。</span><span class="sxs-lookup"><span data-stu-id="1b07d-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="1b07d-132">警示摘要可讓您向下流覽至已套用對應篩選的特定警示佇列。</span><span class="sxs-lookup"><span data-stu-id="1b07d-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="1b07d-133">例如，按一下 [偵測對應卡] 中的 EDR 列時，會透過結果顯示警示佇列，只顯示來自 EDR 偵測產生的警示。</span><span class="sxs-lookup"><span data-stu-id="1b07d-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="1b07d-134">在 [摘要] 區段中反映的資料範圍是在目前日期之前的180天。</span><span class="sxs-lookup"><span data-stu-id="1b07d-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="1b07d-135">例如，如果今天的日期是2019年11月5日，則 [摘要] 區段中的資料將會反映從5月5日開始，2019到11月5日（2019）的數位。</span><span class="sxs-lookup"><span data-stu-id="1b07d-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="1b07d-136">在 [趨勢] 區段上套用的篩選不會在 [摘要] 區段上套用。</span><span class="sxs-lookup"><span data-stu-id="1b07d-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="1b07d-137">警示屬性</span><span class="sxs-lookup"><span data-stu-id="1b07d-137">Alert attributes</span></span>
<span data-ttu-id="1b07d-138">報告是由顯示下列警示屬性的卡片所組成：</span><span class="sxs-lookup"><span data-stu-id="1b07d-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="1b07d-139">**偵測來源**：顯示感應器及偵測技術的相關資訊，這些技術可提供 Microsoft Defender for Endpoint 以觸發提醒的資料。</span><span class="sxs-lookup"><span data-stu-id="1b07d-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="1b07d-140">**威脅類別**：顯示觸發警示的威脅或攻擊活動類型，指出安全性作業的可能焦點區域。</span><span class="sxs-lookup"><span data-stu-id="1b07d-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="1b07d-141">**嚴重性**：顯示警示的嚴重性層級，指出組織威脅的整體潛在影響，以及解決這些威脅的回應層級。</span><span class="sxs-lookup"><span data-stu-id="1b07d-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="1b07d-142">**狀態**：顯示警示的解決狀態，指出手動警示回應的效率，以及自動修正 (啟用) 。</span><span class="sxs-lookup"><span data-stu-id="1b07d-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="1b07d-143">**分類 & 判斷**：顯示如何在解決問題時進行分類警示、是否已將郵件分類為實際威脅 (true 警示) 或不正確的偵測 (false 警示) 。</span><span class="sxs-lookup"><span data-stu-id="1b07d-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="1b07d-144">這些卡片也會顯示已解決的警示，可提供更多深入資訊，如找到的實際威脅類型或偵測到的合法活動。</span><span class="sxs-lookup"><span data-stu-id="1b07d-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="1b07d-145">篩選資料</span><span class="sxs-lookup"><span data-stu-id="1b07d-145">Filter data</span></span>

<span data-ttu-id="1b07d-146">使用提供的篩選，以包含或排除具有特定屬性的警示。</span><span class="sxs-lookup"><span data-stu-id="1b07d-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="1b07d-147">這些篩選器適用于報告中的 **所有** 卡片。</span><span class="sxs-lookup"><span data-stu-id="1b07d-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="1b07d-148">例如，若要顯示僅限高嚴重性警示的資料：</span><span class="sxs-lookup"><span data-stu-id="1b07d-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="1b07d-149">在 [**篩選 > 嚴重性**] 底下，選取 [**高**]</span><span class="sxs-lookup"><span data-stu-id="1b07d-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="1b07d-150">確定已取消選取 [ **嚴重性** ] 底下的其他所有選項。</span><span class="sxs-lookup"><span data-stu-id="1b07d-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="1b07d-151">選取 **套用**。</span><span class="sxs-lookup"><span data-stu-id="1b07d-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="1b07d-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="1b07d-152">Related topic</span></span>
- [<span data-ttu-id="1b07d-153">裝置健康情況和符合性報告</span><span class="sxs-lookup"><span data-stu-id="1b07d-153">Device health and compliance report</span></span>](machine-reports.md)
