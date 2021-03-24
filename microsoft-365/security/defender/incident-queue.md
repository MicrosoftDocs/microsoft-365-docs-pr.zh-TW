---
title: 設定 Microsoft 365 Defender 中的事件優先順序
description: 瞭解如何在 Microsoft 365 Defender 中篩選事件佇列中的事件
keywords: 事件, 佇列, 概覽, 裝置, 身分識別, 使用者, 信箱, 電子郵件, 事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057272"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1fe55-104">設定 Microsoft 365 Defender 中的事件優先順序</span><span class="sxs-lookup"><span data-stu-id="1fe55-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1fe55-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1fe55-105">**Applies to:**</span></span>
- <span data-ttu-id="1fe55-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fe55-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="1fe55-107">Microsoft 365 Defender 會套用關聯性分析，並將不同產品的所有相關警示和調查彙集到一個事件中。</span><span class="sxs-lookup"><span data-stu-id="1fe55-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="1fe55-108">Microsoft 365 defender 也會觸發唯一的警示，可在 Microsoft 365 Defender 跨整個房地產及產品套件的端對端可視性時，識別出惡意的活動。</span><span class="sxs-lookup"><span data-stu-id="1fe55-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="1fe55-109">此視圖讓安全性分析分析員成為廣泛的攻擊案例，可協助他們更好地瞭解及處理整個組織中的複雜威脅。</span><span class="sxs-lookup"><span data-stu-id="1fe55-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="1fe55-110">**事件佇列** 顯示由各裝置、使用者和信箱標示的事件集合。</span><span class="sxs-lookup"><span data-stu-id="1fe55-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="1fe55-111">可協助您設定事件優先順序及制定明智的網路安全回應決策。</span><span class="sxs-lookup"><span data-stu-id="1fe55-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![事件佇列的影像](../../media/incidents-queue.png) 

<span data-ttu-id="1fe55-113">根據預設，Microsoft 365 security center 中的佇列會顯示過去30天內看到的事件。</span><span class="sxs-lookup"><span data-stu-id="1fe55-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="1fe55-114">最近的事件是在清單頂端，您可以先查看此專案。</span><span class="sxs-lookup"><span data-stu-id="1fe55-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="1fe55-115">事件佇列公開可自訂的欄，可讓您深入瞭解事件或所包含之實體的不同特性。</span><span class="sxs-lookup"><span data-stu-id="1fe55-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="1fe55-116">這可協助您作出決定要處理之事件優先順序的相關決定。</span><span class="sxs-lookup"><span data-stu-id="1fe55-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="1fe55-117">如需更深入的洞察力，自動事件命名功能會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別），產生事件名稱。</span><span class="sxs-lookup"><span data-stu-id="1fe55-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="1fe55-118">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="1fe55-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="1fe55-119">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="1fe55-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="1fe55-120">在自動事件命名的首展之前，發生的事件，其名稱不會變更。</span><span class="sxs-lookup"><span data-stu-id="1fe55-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="1fe55-121">事件佇列也會公開多種篩選選項，當套用此選項時，您可以對環境中的所有現有事件執行大量的掃描，也可以決定將重點放在特定案例或威脅上。</span><span class="sxs-lookup"><span data-stu-id="1fe55-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="1fe55-122">在事件佇列套用篩選可協助判斷哪個事件需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="1fe55-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="1fe55-123">可用的篩選</span><span class="sxs-lookup"><span data-stu-id="1fe55-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="1fe55-124">指派給</span><span class="sxs-lookup"><span data-stu-id="1fe55-124">Assigned to</span></span>
<span data-ttu-id="1fe55-125">您可以選擇顯示指派給您或「自動化」所處理的警示。</span><span class="sxs-lookup"><span data-stu-id="1fe55-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="1fe55-126">Categories</span><span class="sxs-lookup"><span data-stu-id="1fe55-126">Categories</span></span>
<span data-ttu-id="1fe55-127">選擇 [類別]，以著重顯示特定的戰術、技術或攻擊元件。</span><span class="sxs-lookup"><span data-stu-id="1fe55-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="1fe55-128">分類</span><span class="sxs-lookup"><span data-stu-id="1fe55-128">Classification</span></span>
<span data-ttu-id="1fe55-129">根據相關警示的設定分類來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="1fe55-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="1fe55-130">其值包括 true 警示、false 警示或未設定。</span><span class="sxs-lookup"><span data-stu-id="1fe55-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="1fe55-131">資料敏感度</span><span class="sxs-lookup"><span data-stu-id="1fe55-131">Data sensitivity</span></span>
<span data-ttu-id="1fe55-132">某些攻擊鎖定外洩機密敏感性資料或重要資料。</span><span class="sxs-lookup"><span data-stu-id="1fe55-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="1fe55-133">透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。</span><span class="sxs-lookup"><span data-stu-id="1fe55-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="1fe55-134">只有在開啟 Microsoft 資訊保護時才適用。</span><span class="sxs-lookup"><span data-stu-id="1fe55-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="1fe55-135">裝置群組</span><span class="sxs-lookup"><span data-stu-id="1fe55-135">Device group</span></span>
<span data-ttu-id="1fe55-136">依定義的裝置群組篩選。</span><span class="sxs-lookup"><span data-stu-id="1fe55-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="1fe55-137">調查狀態</span><span class="sxs-lookup"><span data-stu-id="1fe55-137">Investigation state</span></span>
<span data-ttu-id="1fe55-138">依自動調查的狀態來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="1fe55-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="1fe55-139">多個類別</span><span class="sxs-lookup"><span data-stu-id="1fe55-139">Multiple categories</span></span> 
<span data-ttu-id="1fe55-140">您可以選擇只查看已對應至多個類別的事件，進而可能造成更大的損毀。</span><span class="sxs-lookup"><span data-stu-id="1fe55-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="1fe55-141">多個服務來源</span><span class="sxs-lookup"><span data-stu-id="1fe55-141">Multiple service sources</span></span> 
<span data-ttu-id="1fe55-142">篩選，只會查看包含不同來源之警示的事件， (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="1fe55-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="1fe55-143">作業系統平臺</span><span class="sxs-lookup"><span data-stu-id="1fe55-143">OS platform</span></span>
<span data-ttu-id="1fe55-144">依作業系統限制事件佇列查看。</span><span class="sxs-lookup"><span data-stu-id="1fe55-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="1fe55-145">服務來源</span><span class="sxs-lookup"><span data-stu-id="1fe55-145">Service sources</span></span>
<span data-ttu-id="1fe55-146">透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。</span><span class="sxs-lookup"><span data-stu-id="1fe55-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="1fe55-147">嚴重性</span><span class="sxs-lookup"><span data-stu-id="1fe55-147">Severity</span></span>
<span data-ttu-id="1fe55-148">事件的嚴重性是指它可對資產造成的影響。</span><span class="sxs-lookup"><span data-stu-id="1fe55-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="1fe55-149">嚴重性越高，影響就越大，而且通常需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="1fe55-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="1fe55-150">狀態</span><span class="sxs-lookup"><span data-stu-id="1fe55-150">Status</span></span>
<span data-ttu-id="1fe55-151">您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。</span><span class="sxs-lookup"><span data-stu-id="1fe55-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="1fe55-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1fe55-152">Next steps</span></span>
<span data-ttu-id="1fe55-153">決定優先順序最高的事件後，便可繼續進行事件的調查工作。</span><span class="sxs-lookup"><span data-stu-id="1fe55-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="1fe55-154">調查事件</span><span class="sxs-lookup"><span data-stu-id="1fe55-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="1fe55-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1fe55-155">See also</span></span>
- [<span data-ttu-id="1fe55-156">事件概觀</span><span class="sxs-lookup"><span data-stu-id="1fe55-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1fe55-157">調查事件</span><span class="sxs-lookup"><span data-stu-id="1fe55-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="1fe55-158">管理事件</span><span class="sxs-lookup"><span data-stu-id="1fe55-158">Manage incidents</span></span>](manage-incidents.md)
