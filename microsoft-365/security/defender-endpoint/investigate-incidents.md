---
title: 調查 Microsoft Defender for Endpoint 中的事件
description: 請參閱相關聯的警示、管理事件，以及查看警示中繼資料，以協助您調查事件。
keywords: 調查、事件、警示、中繼資料、風險、偵測來源、受影響的裝置、模式、關聯性
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0b52b6f9b457dbe1a5984c3d68c7077f7037d498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845075"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4cbc6-104">調查 Microsoft Defender for Endpoint 中的事件</span><span class="sxs-lookup"><span data-stu-id="4cbc6-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4cbc6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4cbc6-105">**Applies to:**</span></span>
- [<span data-ttu-id="4cbc6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4cbc6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4cbc6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cbc6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="4cbc6-108">調查影響網路的事件、瞭解其含義，以及對照證據進行分析。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="4cbc6-109">當您調查事件時，您會看到：</span><span class="sxs-lookup"><span data-stu-id="4cbc6-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="4cbc6-110">事件詳細資料</span><span class="sxs-lookup"><span data-stu-id="4cbc6-110">Incident details</span></span>
- <span data-ttu-id="4cbc6-111">事件批註和動作</span><span class="sxs-lookup"><span data-stu-id="4cbc6-111">Incident comments and actions</span></span>
- <span data-ttu-id="4cbc6-112">索引標籤 (警示、裝置、調查、證據、圖形) </span><span class="sxs-lookup"><span data-stu-id="4cbc6-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="4cbc6-113">分析事件詳細資料</span><span class="sxs-lookup"><span data-stu-id="4cbc6-113">Analyze incident details</span></span> 
<span data-ttu-id="4cbc6-114">按一下事件以查看 [ **事件] 窗格**。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="4cbc6-115">選取 [ **開啟事件] 頁面** ，查看事件詳細資料和相關資訊 (警示、裝置、調查、證據、圖形) 。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![事件 details1 的影像](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="4cbc6-117">警示</span><span class="sxs-lookup"><span data-stu-id="4cbc6-117">Alerts</span></span>
<span data-ttu-id="4cbc6-118">您可以調查警示，並查看其在事件中如何連結在一起。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="4cbc6-119">根據下列原因，將警示分組到事件：</span><span class="sxs-lookup"><span data-stu-id="4cbc6-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="4cbc6-120">自動調查-自動調查會在調查原始警示時觸發連結的警示</span><span class="sxs-lookup"><span data-stu-id="4cbc6-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="4cbc6-121">檔特性-與警示相關聯的檔案具有類似的特性</span><span class="sxs-lookup"><span data-stu-id="4cbc6-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="4cbc6-122">手動關聯-手動連結通知的使用者</span><span class="sxs-lookup"><span data-stu-id="4cbc6-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="4cbc6-123">Proximate time-警示在特定時間範圍內的相同裝置上觸發</span><span class="sxs-lookup"><span data-stu-id="4cbc6-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="4cbc6-124">同一個檔案-與警示相關聯的檔案完全相同</span><span class="sxs-lookup"><span data-stu-id="4cbc6-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="4cbc6-125">同一個 URL-觸發警示的 URL 完全相同</span><span class="sxs-lookup"><span data-stu-id="4cbc6-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![[警示] 索引標籤與 [事件詳細資料] 頁面，顯示預警在該事件中的相互關聯原因。](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="4cbc6-127">您也可以管理警示，並查看警示中繼資料及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="4cbc6-128">如需詳細資訊，請參閱 [調查警示](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="4cbc6-129">裝置</span><span class="sxs-lookup"><span data-stu-id="4cbc6-129">Devices</span></span>
<span data-ttu-id="4cbc6-130">您也可以調查指定之事件的一部分或相關的裝置。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="4cbc6-131">如需詳細資訊，請參閱 [調查裝置](investigate-machines.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![[事件詳細資料] 頁面中的 [裝置影像] 索引標籤](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="4cbc6-133">調查</span><span class="sxs-lookup"><span data-stu-id="4cbc6-133">Investigations</span></span>
<span data-ttu-id="4cbc6-134">選取 [ **調查** ]，查看系統所啟動的所有自動調查，以回應事件警示。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![[事件詳細資料] 頁面中的 [調查] 索引標籤](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="4cbc6-136">透過證據</span><span class="sxs-lookup"><span data-stu-id="4cbc6-136">Going through the evidence</span></span>
<span data-ttu-id="4cbc6-137">Microsoft Defender for Endpoint 會自動調查事件中的所有受支援事件和可疑實體，以提供 autoresponse 及重要檔案、程式、服務等相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="4cbc6-138">每個分析的實體都會標示為已感染、已修正或可疑。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![[事件詳細資料] 頁面中的 [證據] 索引標籤](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="4cbc6-140">視覺化關聯的 cybersecurity 威脅</span><span class="sxs-lookup"><span data-stu-id="4cbc6-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="4cbc6-141">Microsoft Defender for Endpoint 會將威脅資訊匯總到事件中，讓您可以看到來自各種資料點的模式和關聯性。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="4cbc6-142">您可以透過 incident graph 查看這類關聯。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="4cbc6-143">事件圖形</span><span class="sxs-lookup"><span data-stu-id="4cbc6-143">Incident graph</span></span>
<span data-ttu-id="4cbc6-144">**Graph** 告訴 cybersecurity 攻擊的故事。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="4cbc6-145">例如，它會顯示進入點，在哪個裝置上觀察到損損或活動的指示器。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="4cbc6-146">等。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-146">etc.</span></span>

![事件圖形的影像](images/atp-incident-graph-tab.png)

<span data-ttu-id="4cbc6-148">您可以按一下事件圖上的圓圈，以查看惡意檔案的詳細資料、相關聯的檔案偵測，以及在全球範圍內有多少個實例（如果有的話），如果有，則表示您的組織中有多少個實例。</span><span class="sxs-lookup"><span data-stu-id="4cbc6-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![事件詳細資料的影像](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="4cbc6-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="4cbc6-150">Related topics</span></span>
- [<span data-ttu-id="4cbc6-151">事件佇列</span><span class="sxs-lookup"><span data-stu-id="4cbc6-151">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="4cbc6-152">調查 Microsoft Defender for Endpoint 中的事件</span><span class="sxs-lookup"><span data-stu-id="4cbc6-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="4cbc6-153">管理 Microsoft Defender for Endpoint 事件</span><span class="sxs-lookup"><span data-stu-id="4cbc6-153">Manage Microsoft Defender for Endpoint incidents</span></span>](/microsoft-365/security/defender-endpoint/manage-incidents)
