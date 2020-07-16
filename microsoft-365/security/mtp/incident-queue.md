---
title: 設定 Microsoft 威脅防護事件的優先順序
description: 瞭解如何在 Microsoft 威脅防護中依事件佇列設定事件優先順序
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d827484a440b291bccd45b58e977fbcb280680f2
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148133"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="7286f-104">設定 Microsoft 威脅防護事件的優先順序</span><span class="sxs-lookup"><span data-stu-id="7286f-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="7286f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7286f-105">**Applies to:**</span></span>
- <span data-ttu-id="7286f-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="7286f-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="7286f-107">Microsoft 威脅防護會套用相關分析，並將來自不同產品的所有相關警示和調查匯總到單一事件。</span><span class="sxs-lookup"><span data-stu-id="7286f-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="7286f-108">Microsoft 威脅防護也會觸發活動的獨特警示，這些活動只會在 Microsoft 威脅防護對整個資產和產品套件有端對端可見度時識別為惡意。</span><span class="sxs-lookup"><span data-stu-id="7286f-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="7286f-109">如此一來，Microsoft 威脅防護能對攻擊案例進行更廣泛的描述，讓安全性作業分析師了解及處理組織中的複雜威脅。</span><span class="sxs-lookup"><span data-stu-id="7286f-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="7286f-110">**事件佇列**顯示由各裝置、使用者和信箱標示的事件集合。</span><span class="sxs-lookup"><span data-stu-id="7286f-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="7286f-111">可協助您設定事件優先順序及制定明智的網路安全回應決策。</span><span class="sxs-lookup"><span data-stu-id="7286f-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![事件佇列的影像](../../media/incidents-queue.png) 

<span data-ttu-id="7286f-113">根據預設，Microsoft 365 安全中心中的佇列會顯示最近 30 天內發生的事件，最新的事件會顯示在清單頂端，以協助您先查看最新的事件。</span><span class="sxs-lookup"><span data-stu-id="7286f-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="7286f-114">事件佇列顯示可自訂的欄，讓您深入了解事故或內含實體的不同特性，協助您根據事件處理的優先順序制定明智的決策。</span><span class="sxs-lookup"><span data-stu-id="7286f-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="7286f-115">如需更深入的可見度、自動事件命名，目前在公開預覽中，會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別）產生事件名稱。</span><span class="sxs-lookup"><span data-stu-id="7286f-115">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="7286f-116">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="7286f-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="7286f-117">例如：多*個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="7286f-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="7286f-118">在自動事件命名的首展之前，發生的事件，其名稱不會變更。</span><span class="sxs-lookup"><span data-stu-id="7286f-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="7286f-119">深入瞭解[開啟預覽功能](preview.md#turn-on-preview-features)。</span><span class="sxs-lookup"><span data-stu-id="7286f-119">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

<span data-ttu-id="7286f-120">事件佇列也會顯示多個篩選選項，套用時，可讓您選擇執行環境中所有現有事件的廣泛整理，或決定要專注於特定案例或威脅。</span><span class="sxs-lookup"><span data-stu-id="7286f-120">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="7286f-121">在事件佇列套用篩選可協助判斷哪個事件需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="7286f-121">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="7286f-122">可用的篩選</span><span class="sxs-lookup"><span data-stu-id="7286f-122">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="7286f-123">狀態</span><span class="sxs-lookup"><span data-stu-id="7286f-123">Status</span></span>
<span data-ttu-id="7286f-124">您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。</span><span class="sxs-lookup"><span data-stu-id="7286f-124">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="7286f-125">嚴重性</span><span class="sxs-lookup"><span data-stu-id="7286f-125">Severity</span></span>
<span data-ttu-id="7286f-126">事件的嚴重性表示該事件對您的資產造成的影響。</span><span class="sxs-lookup"><span data-stu-id="7286f-126">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="7286f-127">嚴重性級別越高，影響越大，通常會需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="7286f-127">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="7286f-128">已指派給 (擁有者)</span><span class="sxs-lookup"><span data-stu-id="7286f-128">Assigned to (owner)</span></span>
<span data-ttu-id="7286f-129">您可以選取指派給任何人或指派給您來篩選清單。</span><span class="sxs-lookup"><span data-stu-id="7286f-129">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="7286f-130">多個警示</span><span class="sxs-lookup"><span data-stu-id="7286f-130">Multiple alerts</span></span> 
<span data-ttu-id="7286f-131">僅篩選查看包含多個警示的事件。</span><span class="sxs-lookup"><span data-stu-id="7286f-131">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="7286f-132">這可能表示終止鏈中較複雜或參與度更高的攻擊。</span><span class="sxs-lookup"><span data-stu-id="7286f-132">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="7286f-133">多個服務來源</span><span class="sxs-lookup"><span data-stu-id="7286f-133">Multiple service sources</span></span> 
<span data-ttu-id="7286f-134">僅篩選查看包含來自不同來源的警示 (Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP、Office 365 ATP) 的事件</span><span class="sxs-lookup"><span data-stu-id="7286f-134">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="7286f-135">服務來源</span><span class="sxs-lookup"><span data-stu-id="7286f-135">Service sources</span></span>
<span data-ttu-id="7286f-136">透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。</span><span class="sxs-lookup"><span data-stu-id="7286f-136">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="7286f-137">多個類別</span><span class="sxs-lookup"><span data-stu-id="7286f-137">Multiple categories</span></span> 
<span data-ttu-id="7286f-138">您可以選擇只查看已對應到終止鏈多個類別且可能會造成更大的危害的事件。</span><span class="sxs-lookup"><span data-stu-id="7286f-138">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="7286f-139">類別</span><span class="sxs-lookup"><span data-stu-id="7286f-139">Categories</span></span>
<span data-ttu-id="7286f-140">選擇特定類別，以專注於終止鏈中的特定步驟</span><span class="sxs-lookup"><span data-stu-id="7286f-140">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="7286f-141">資料敏感度</span><span class="sxs-lookup"><span data-stu-id="7286f-141">Data sensitivity</span></span>
<span data-ttu-id="7286f-142">某些攻擊鎖定外洩機密敏感性資料或重要資料。</span><span class="sxs-lookup"><span data-stu-id="7286f-142">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="7286f-143">透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。</span><span class="sxs-lookup"><span data-stu-id="7286f-143">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="7286f-144">只有在開啟 Microsoft 資訊保護時才適用。</span><span class="sxs-lookup"><span data-stu-id="7286f-144">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="7286f-145">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7286f-145">Next steps</span></span>
<span data-ttu-id="7286f-146">決定優先順序最高的事件後，便可繼續進行事件的調查工作。</span><span class="sxs-lookup"><span data-stu-id="7286f-146">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="7286f-147">調查事件</span><span class="sxs-lookup"><span data-stu-id="7286f-147">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="7286f-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="7286f-148">Related topics</span></span>
- [<span data-ttu-id="7286f-149">事件概觀</span><span class="sxs-lookup"><span data-stu-id="7286f-149">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="7286f-150">調查事件</span><span class="sxs-lookup"><span data-stu-id="7286f-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="7286f-151">管理事件</span><span class="sxs-lookup"><span data-stu-id="7286f-151">Manage incidents</span></span>](manage-incidents.md)
