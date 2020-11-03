---
title: 設定 Microsoft 365 Defender 中的事件優先順序
description: 瞭解如何在 Microsoft 365 Defender 中排定事件佇列中的事件優先順序
keywords: 事件, 佇列, 概覽, 裝置, 身分識別, 使用者, 信箱, 電子郵件, 事件
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846709"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="35dcc-104">設定 Microsoft 365 Defender 中的事件優先順序</span><span class="sxs-lookup"><span data-stu-id="35dcc-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="35dcc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="35dcc-105">**Applies to:**</span></span>
- <span data-ttu-id="35dcc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35dcc-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="35dcc-107">Microsoft 365 Defender 會套用關聯性分析，並將不同產品的所有相關警示和調查彙集到一個事件中。</span><span class="sxs-lookup"><span data-stu-id="35dcc-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="35dcc-108">Microsoft 365 defender 也會觸發唯一的警示，可在 Microsoft 365 Defender 跨整個房地產及產品套件的端對端可視性時，識別出惡意的活動。</span><span class="sxs-lookup"><span data-stu-id="35dcc-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="35dcc-109">如此一來，Microsoft 365 Defender narrates 更廣泛的攻擊案例，讓安全性作業分析員能夠瞭解並處理整個組織中的複雜威脅。</span><span class="sxs-lookup"><span data-stu-id="35dcc-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="35dcc-110">**事件佇列** 顯示由各裝置、使用者和信箱標示的事件集合。</span><span class="sxs-lookup"><span data-stu-id="35dcc-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="35dcc-111">可協助您設定事件優先順序及制定明智的網路安全回應決策。</span><span class="sxs-lookup"><span data-stu-id="35dcc-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![事件佇列的影像](../../media/incidents-queue.png) 

<span data-ttu-id="35dcc-113">根據預設，Microsoft 365 安全中心中的佇列會顯示最近 30 天內發生的事件，最新的事件會顯示在清單頂端，以協助您先查看最新的事件。</span><span class="sxs-lookup"><span data-stu-id="35dcc-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="35dcc-114">事件佇列顯示可自訂的欄，讓您深入了解事故或內含實體的不同特性，協助您根據事件處理的優先順序制定明智的決策。</span><span class="sxs-lookup"><span data-stu-id="35dcc-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="35dcc-115">若要深入瞭解，自動事件命名會產生以警示屬性為基礎的事件名稱，例如受影響的端點數目、受影響的使用者、偵測來源或類別。</span><span class="sxs-lookup"><span data-stu-id="35dcc-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="35dcc-116">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="35dcc-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="35dcc-117">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="35dcc-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="35dcc-118">在自動事件命名的首展之前，發生的事件，其名稱不會變更。</span><span class="sxs-lookup"><span data-stu-id="35dcc-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="35dcc-119">事件佇列也會顯示多個篩選選項，套用時，可讓您選擇執行環境中所有現有事件的廣泛整理，或決定要專注於特定案例或威脅。</span><span class="sxs-lookup"><span data-stu-id="35dcc-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="35dcc-120">在事件佇列套用篩選可協助判斷哪個事件需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="35dcc-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="35dcc-121">可用的篩選</span><span class="sxs-lookup"><span data-stu-id="35dcc-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="35dcc-122">狀態</span><span class="sxs-lookup"><span data-stu-id="35dcc-122">Status</span></span>
<span data-ttu-id="35dcc-123">您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。</span><span class="sxs-lookup"><span data-stu-id="35dcc-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="35dcc-124">嚴重性</span><span class="sxs-lookup"><span data-stu-id="35dcc-124">Severity</span></span>
<span data-ttu-id="35dcc-125">事件的嚴重性表示該事件對您的資產造成的影響。</span><span class="sxs-lookup"><span data-stu-id="35dcc-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="35dcc-126">嚴重性級別越高，影響越大，通常會需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="35dcc-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="35dcc-127">已指派給 (擁有者)</span><span class="sxs-lookup"><span data-stu-id="35dcc-127">Assigned to (owner)</span></span>
<span data-ttu-id="35dcc-128">您可以選取指派給任何人或指派給您來篩選清單。</span><span class="sxs-lookup"><span data-stu-id="35dcc-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="35dcc-129">多個警示</span><span class="sxs-lookup"><span data-stu-id="35dcc-129">Multiple alerts</span></span> 
<span data-ttu-id="35dcc-130">僅篩選查看包含多個警示的事件。</span><span class="sxs-lookup"><span data-stu-id="35dcc-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="35dcc-131">這可能表示終止鏈中較複雜或參與度更高的攻擊。</span><span class="sxs-lookup"><span data-stu-id="35dcc-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="35dcc-132">多個服務來源</span><span class="sxs-lookup"><span data-stu-id="35dcc-132">Multiple service sources</span></span> 
<span data-ttu-id="35dcc-133">篩選僅查看包含不同來源之警示的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) </span><span class="sxs-lookup"><span data-stu-id="35dcc-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365)</span></span>
### <a name="service-sources"></a><span data-ttu-id="35dcc-134">服務來源</span><span class="sxs-lookup"><span data-stu-id="35dcc-134">Service sources</span></span>
<span data-ttu-id="35dcc-135">透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。</span><span class="sxs-lookup"><span data-stu-id="35dcc-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="35dcc-136">多個類別</span><span class="sxs-lookup"><span data-stu-id="35dcc-136">Multiple categories</span></span> 
<span data-ttu-id="35dcc-137">您可以選擇只查看已對應到終止鏈多個類別且可能會造成更大的危害的事件。</span><span class="sxs-lookup"><span data-stu-id="35dcc-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="35dcc-138">類別</span><span class="sxs-lookup"><span data-stu-id="35dcc-138">Categories</span></span>
<span data-ttu-id="35dcc-139">選擇特定類別，以專注於終止鏈中的特定步驟</span><span class="sxs-lookup"><span data-stu-id="35dcc-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="35dcc-140">資料敏感度</span><span class="sxs-lookup"><span data-stu-id="35dcc-140">Data sensitivity</span></span>
<span data-ttu-id="35dcc-141">某些攻擊鎖定外洩機密敏感性資料或重要資料。</span><span class="sxs-lookup"><span data-stu-id="35dcc-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="35dcc-142">透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。</span><span class="sxs-lookup"><span data-stu-id="35dcc-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="35dcc-143">只有在開啟 Microsoft 資訊保護時才適用。</span><span class="sxs-lookup"><span data-stu-id="35dcc-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="35dcc-144">後續步驟</span><span class="sxs-lookup"><span data-stu-id="35dcc-144">Next steps</span></span>
<span data-ttu-id="35dcc-145">決定優先順序最高的事件後，便可繼續進行事件的調查工作。</span><span class="sxs-lookup"><span data-stu-id="35dcc-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="35dcc-146">調查事件</span><span class="sxs-lookup"><span data-stu-id="35dcc-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="35dcc-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="35dcc-147">Related topics</span></span>
- [<span data-ttu-id="35dcc-148">事件概觀</span><span class="sxs-lookup"><span data-stu-id="35dcc-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="35dcc-149">調查事件</span><span class="sxs-lookup"><span data-stu-id="35dcc-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="35dcc-150">管理事件</span><span class="sxs-lookup"><span data-stu-id="35dcc-150">Manage incidents</span></span>](manage-incidents.md)
