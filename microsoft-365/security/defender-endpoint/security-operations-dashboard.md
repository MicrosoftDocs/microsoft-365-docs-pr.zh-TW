---
title: Microsoft Defender 安全中心安全性運作儀表板
description: 使用儀表板來識別具有風險的裝置、追蹤服務的狀態，以及查看有關裝置及警示的統計資料和資訊。
keywords: 儀表板、警示、新、正在進行、已解決、風險、裝置風險、病毒感染、報告、統計資料、圖表、圖表、健康情況、作用中惡意程式碼偵測、威脅類別、類別、密碼 stealer、勒索軟體、入侵、威脅、低嚴重性、active 惡意程式碼
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058719"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="57593-104">Microsoft Defender 安全中心安全性運作儀表板</span><span class="sxs-lookup"><span data-stu-id="57593-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="57593-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="57593-105">**Applies to:**</span></span>
- [<span data-ttu-id="57593-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="57593-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="57593-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="57593-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57593-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="57593-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="57593-109">**安全性作業儀表板** 是指端點偵測和回應功能的所在位置。</span><span class="sxs-lookup"><span data-stu-id="57593-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="57593-110">這可讓您在需要回應動作的情況下，以高層次的方式概括顯示偵測和高光的位置。</span><span class="sxs-lookup"><span data-stu-id="57593-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="57593-111">儀表板會顯示下列專案的快照：</span><span class="sxs-lookup"><span data-stu-id="57593-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="57593-112">主動警示</span><span class="sxs-lookup"><span data-stu-id="57593-112">Active alerts</span></span>
- <span data-ttu-id="57593-113">裝置面臨危險</span><span class="sxs-lookup"><span data-stu-id="57593-113">Devices at risk</span></span>
- <span data-ttu-id="57593-114">感應器狀況</span><span class="sxs-lookup"><span data-stu-id="57593-114">Sensor health</span></span>
- <span data-ttu-id="57593-115">服務健康狀況</span><span class="sxs-lookup"><span data-stu-id="57593-115">Service health</span></span>
- <span data-ttu-id="57593-116">每日裝置報告</span><span class="sxs-lookup"><span data-stu-id="57593-116">Daily devices reporting</span></span>
- <span data-ttu-id="57593-117">主動的自動調查</span><span class="sxs-lookup"><span data-stu-id="57593-117">Active automated investigations</span></span>
- <span data-ttu-id="57593-118">自動調查統計資料</span><span class="sxs-lookup"><span data-stu-id="57593-118">Automated investigations statistics</span></span>
- <span data-ttu-id="57593-119">使用者面臨風險</span><span class="sxs-lookup"><span data-stu-id="57593-119">Users at risk</span></span>
- <span data-ttu-id="57593-120">可疑活動</span><span class="sxs-lookup"><span data-stu-id="57593-120">Suspicious activities</span></span>


![安全性作業儀表板的影像](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="57593-122">您可以探索並調查警示和裝置，以快速判斷您的網路中是否發生可疑活動，以協助您瞭解所出現的內容。</span><span class="sxs-lookup"><span data-stu-id="57593-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="57593-123">在 [ **安全性作業] 儀表板** 中，您會看到匯總的事件，以協助識別裝置上的重要事件或行為。</span><span class="sxs-lookup"><span data-stu-id="57593-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="57593-124">您也可以深入查看細微的事件和低層指示器。</span><span class="sxs-lookup"><span data-stu-id="57593-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="57593-125">它也具有可在組織整體健康狀態上提供視覺提示的可供按一下的麻將牌。</span><span class="sxs-lookup"><span data-stu-id="57593-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="57593-126">每個麻將牌都會開啟對應之概要的詳細視圖。</span><span class="sxs-lookup"><span data-stu-id="57593-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="57593-127">主動警示</span><span class="sxs-lookup"><span data-stu-id="57593-127">Active alerts</span></span>
<span data-ttu-id="57593-128">您可以從麻將牌的網路中過去30天內，查看使用中警示的總數。</span><span class="sxs-lookup"><span data-stu-id="57593-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="57593-129">警示會分組成 **新** 的和 **進行中**。</span><span class="sxs-lookup"><span data-stu-id="57593-129">Alerts are grouped into **New** and **In progress**.</span></span>

![按一下每個扇面或嚴重性，以查看過去30天的警示清單。](images/active-alerts-tile.png)

<span data-ttu-id="57593-131">每個群組會進一步歸入其對應的警示嚴重性層級。</span><span class="sxs-lookup"><span data-stu-id="57593-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="57593-132">按一下每個提醒環內的提醒數目，以查看該類別佇列的已排序視圖 () **新增** 或 **進行中** 。</span><span class="sxs-lookup"><span data-stu-id="57593-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="57593-133">如需詳細資訊，請參閱 [警示總覽](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="57593-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="57593-134">每一列都包含警示嚴重性類別及警示的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="57593-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="57593-135">您可以按一下警示，以查看其詳細的觀點。</span><span class="sxs-lookup"><span data-stu-id="57593-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="57593-136">如需詳細資訊，請參閱  [Microsoft Defender For Endpoint 警示](investigate-alerts.md) 和 [警示概述](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="57593-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="57593-137">裝置面臨危險</span><span class="sxs-lookup"><span data-stu-id="57593-137">Devices at risk</span></span>
<span data-ttu-id="57593-138">此麻將牌會顯示具有最高作用中警示數目的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="57593-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="57593-139">每個裝置的警示總數會顯示在裝置名稱旁邊的圓形中，然後再依嚴重性層級分類在磚的最低端 (將游標移至每個嚴重性列，以查看其標籤) 。</span><span class="sxs-lookup"><span data-stu-id="57593-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![危險圖上的裝置會顯示具有最高警示數目的裝置清單，以及警示嚴重性的細目](images/devices-at-risk-tile.png)

<span data-ttu-id="57593-141">按一下裝置的名稱，以查看該裝置的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="57593-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="57593-142">如需詳細資訊，請參閱 [調查 Microsoft Defender For Endpoint devices 中的裝置清單](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="57593-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="57593-143">您也可以按一下磚頂端的 [ **裝置] 清單** ，以直接移至 [ **裝置] 清單**，依作用中的警示數目排序。</span><span class="sxs-lookup"><span data-stu-id="57593-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="57593-144">如需詳細資訊，請參閱 [調查 Microsoft Defender For Endpoint devices 中的裝置清單](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="57593-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="57593-145">具有感應器問題的裝置</span><span class="sxs-lookup"><span data-stu-id="57593-145">Devices with sensor issues</span></span>
<span data-ttu-id="57593-146">**具有感應器問題的裝置** 會提供個別裝置提供感應器資料至 Microsoft Defender for Endpoint service 的功能資訊。</span><span class="sxs-lookup"><span data-stu-id="57593-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="57593-147">它會報告需要注意的裝置數量，並協助您識別有問題的裝置。</span><span class="sxs-lookup"><span data-stu-id="57593-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![具有感應器問題磚的裝置](images/atp-tile-sensor-health.png)

<span data-ttu-id="57593-149">有兩個狀態指示器可提供無法正確報告至服務之裝置的數目資訊：</span><span class="sxs-lookup"><span data-stu-id="57593-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="57593-150">設定 **錯誤**-這些裝置可能會部分向 Microsoft Defender for Endpoint service 報告感應器資料，而且可能會發生需要修正的設定錯誤。</span><span class="sxs-lookup"><span data-stu-id="57593-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="57593-151">**非** 使用中-過去一個月已停止向 Microsoft Defender for Endpoint service 報告的裝置超過7天。</span><span class="sxs-lookup"><span data-stu-id="57593-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="57593-152">當您按一下任一群組時，系統會將您導向至 [裝置] 清單，並根據您的選擇加以篩選。</span><span class="sxs-lookup"><span data-stu-id="57593-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="57593-153">如需詳細資訊，請參閱 [檢查感應器狀態](check-sensor-status.md) 和 [調查裝置](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="57593-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="57593-154">服務健康狀況</span><span class="sxs-lookup"><span data-stu-id="57593-154">Service health</span></span>
<span data-ttu-id="57593-155">**服務健康** 情況磚會通知您服務是否在使用中或發生問題。</span><span class="sxs-lookup"><span data-stu-id="57593-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![服務健康情況磚顯示服務的整體指示器](images/status-tile.png)

<span data-ttu-id="57593-157">如需服務健康情況的詳細資訊，請參閱 [檢查 Microsoft Defender For Endpoint service health](service-status.md)。</span><span class="sxs-lookup"><span data-stu-id="57593-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="57593-158">每日裝置報告</span><span class="sxs-lookup"><span data-stu-id="57593-158">Daily devices reporting</span></span>
<span data-ttu-id="57593-159">[ **每日裝置報告** ] 磚會顯示一個柱狀圖圖，表示在過去30天內，每日報告的裝置數目。</span><span class="sxs-lookup"><span data-stu-id="57593-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="57593-160">將游標移到圖形上的個別條形上，查看每天報告的實際裝置數目。</span><span class="sxs-lookup"><span data-stu-id="57593-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![每日裝置報告磚的影像](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="57593-162">主動的自動調查</span><span class="sxs-lookup"><span data-stu-id="57593-162">Active automated investigations</span></span>
<span data-ttu-id="57593-163">您可以從您網路中的最近30天開始，透過「作用中的 **自動調查** ] 磚來查看總的自動調查數目。</span><span class="sxs-lookup"><span data-stu-id="57593-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="57593-164">調查會分組成 **擱置** 中的動作， **等候裝置**， **並執行**。</span><span class="sxs-lookup"><span data-stu-id="57593-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Inmage 主動自動調查](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="57593-166">自動調查統計資料</span><span class="sxs-lookup"><span data-stu-id="57593-166">Automated investigations statistics</span></span>
<span data-ttu-id="57593-167">此麻將牌顯示過去7天內自動調查相關的統計資料。</span><span class="sxs-lookup"><span data-stu-id="57593-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="57593-168">它會顯示已完成調查的數目、成功修正調查的數目、可啟動調查的平均擱置時間、修正警示所需的平均時間、調查的警示數量，以及從一般手動調查中儲存的自動化時數。</span><span class="sxs-lookup"><span data-stu-id="57593-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![自動調查統計資料的影像](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="57593-170">您可以按一下「 **自動調查**」、「 **修正調查**」及「 **調查** 」，以流覽至「 **調查** 」頁面，並依適當的類別篩選。</span><span class="sxs-lookup"><span data-stu-id="57593-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="57593-171">這可讓您在內容中看到調查的詳細細分。</span><span class="sxs-lookup"><span data-stu-id="57593-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="57593-172">使用者面臨風險</span><span class="sxs-lookup"><span data-stu-id="57593-172">Users at risk</span></span>
<span data-ttu-id="57593-173">此磚會顯示具有最活躍警示的使用者帳戶清單，以及在高、中或低警示上看到的警示數目。</span><span class="sxs-lookup"><span data-stu-id="57593-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![風險圖中的使用者帳戶會顯示具有最高警示數目的使用者帳戶清單，以及警示嚴重性的分解。](images/atp-users-at-risk.png)

<span data-ttu-id="57593-175">按一下使用者帳戶以查看使用者帳戶的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="57593-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="57593-176">如需詳細資訊，請參閱 [調查使用者帳戶](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="57593-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="57593-177">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="57593-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="57593-178">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="57593-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="57593-179">相關主題</span><span class="sxs-lookup"><span data-stu-id="57593-179">Related topics</span></span>
- [<span data-ttu-id="57593-180">瞭解 Microsoft Defender for Endpoint 入口網站</span><span class="sxs-lookup"><span data-stu-id="57593-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="57593-181">入口網站概述</span><span class="sxs-lookup"><span data-stu-id="57593-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="57593-182">查看威脅 & 漏洞管理儀表板</span><span class="sxs-lookup"><span data-stu-id="57593-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="57593-183">查看威脅分析儀表板並採取建議的緩解動作</span><span class="sxs-lookup"><span data-stu-id="57593-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)
