---
title: 在 Microsoft 365 Defender 中排列事件的優先順序
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
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929291"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="a7c5a-104">在 Microsoft 365 Defender 中排列事件的優先順序</span><span class="sxs-lookup"><span data-stu-id="a7c5a-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a7c5a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a7c5a-105">**Applies to:**</span></span>
- <span data-ttu-id="a7c5a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7c5a-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="a7c5a-107">Microsoft 365 Defender 會進行相關分析，並匯總不同產品的所有相關警示與調查到單一事件。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="a7c5a-108">Microsoft 365 Defender 也會觸發唯一警示，指出只有 Microsoft 365 Defender 具有跨整個財產和產品套件的端對端可見度，才能識別活動為惡意。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="a7c5a-109">此視圖可賦予您的安全性作業分析師更大的攻擊案例，協助他們進一理解並處理整個組織的複雜威脅。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="a7c5a-110">**事件佇列** 顯示由各裝置、使用者和信箱標示的事件集合。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="a7c5a-111">可協助您設定事件優先順序及制定明智的網路安全回應決策。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![事件佇列的影像](../../media/incidents-queue.png) 

<span data-ttu-id="a7c5a-113">根據預設，Microsoft 365 資訊安全中心的佇列會顯示過去 30 天內發生的事件。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="a7c5a-114">最新的事件位於清單頂端，因此您可以先看到它。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="a7c5a-115">事件佇列公開可自訂的欄，提供您事件或包含實體的不同特性的可見度。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="a7c5a-116">這可協助針對要處理之事件的優先順序，做出明智的決策。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="a7c5a-117">為了一目了然，自動事件命名功能會依據警示屬性產生事件名稱，例如受影響的端點數目、受影響的使用者、偵測來源或類別。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="a7c5a-118">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="a7c5a-119">例如： *多個來源報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="a7c5a-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="a7c5a-120">在推出自動事件命名之前存在的事件不會變更其名稱。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="a7c5a-121">事件佇列也會公開多個篩選選項，當篩選選項適用時，您可以對環境中所有現有的事件執行廣泛的整理，或決定專注于特定案例或威脅。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="a7c5a-122">在事件佇列套用篩選可協助判斷哪個事件需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="a7c5a-123">可用的篩選</span><span class="sxs-lookup"><span data-stu-id="a7c5a-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="a7c5a-124">指派給</span><span class="sxs-lookup"><span data-stu-id="a7c5a-124">Assigned to</span></span>
<span data-ttu-id="a7c5a-125">您可以選擇顯示指派給您的提醒或由自動化處理者。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="a7c5a-126">類別</span><span class="sxs-lookup"><span data-stu-id="a7c5a-126">Categories</span></span>
<span data-ttu-id="a7c5a-127">選擇類別以專注于特定的策略、技巧或攻擊元件。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="a7c5a-128">分類</span><span class="sxs-lookup"><span data-stu-id="a7c5a-128">Classification</span></span>
<span data-ttu-id="a7c5a-129">根據相關警示的設定分類來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="a7c5a-130">這些值包括真正的警示、誤報或未設定。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="a7c5a-131">資料敏感度</span><span class="sxs-lookup"><span data-stu-id="a7c5a-131">Data sensitivity</span></span>
<span data-ttu-id="a7c5a-132">某些攻擊鎖定外洩機密敏感性資料或重要資料。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="a7c5a-133">透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="a7c5a-134">只有在開啟 Microsoft 資訊保護時才適用。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="a7c5a-135">裝置群組</span><span class="sxs-lookup"><span data-stu-id="a7c5a-135">Device group</span></span>
<span data-ttu-id="a7c5a-136">根據定義的裝置群組篩選。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="a7c5a-137">調查狀態</span><span class="sxs-lookup"><span data-stu-id="a7c5a-137">Investigation state</span></span>
<span data-ttu-id="a7c5a-138">根據自動化調查的狀態來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="a7c5a-139">多個類別</span><span class="sxs-lookup"><span data-stu-id="a7c5a-139">Multiple categories</span></span> 
<span data-ttu-id="a7c5a-140">您可以選擇只查看已對應到多個類別的事件，因此可能導致更多損害。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="a7c5a-141">多個服務來源</span><span class="sxs-lookup"><span data-stu-id="a7c5a-141">Multiple service sources</span></span> 
<span data-ttu-id="a7c5a-142">篩選以只查看含有不同來源警示的事件 (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="a7c5a-143">作業系統平臺</span><span class="sxs-lookup"><span data-stu-id="a7c5a-143">OS platform</span></span>
<span data-ttu-id="a7c5a-144">根據作業系統限制事件佇列視圖。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="a7c5a-145">服務來源</span><span class="sxs-lookup"><span data-stu-id="a7c5a-145">Service sources</span></span>
<span data-ttu-id="a7c5a-146">透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="a7c5a-147">嚴重性</span><span class="sxs-lookup"><span data-stu-id="a7c5a-147">Severity</span></span>
<span data-ttu-id="a7c5a-148">事件的嚴重性取決於事件會對您的資產造成的影響。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="a7c5a-149">嚴重性越高，影響越大，通常需要最即時的注意。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="a7c5a-150">狀態</span><span class="sxs-lookup"><span data-stu-id="a7c5a-150">Status</span></span>
<span data-ttu-id="a7c5a-151">您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="a7c5a-152">後續步驟</span><span class="sxs-lookup"><span data-stu-id="a7c5a-152">Next steps</span></span>
<span data-ttu-id="a7c5a-153">決定優先順序最高的事件後，便可繼續進行事件的調查工作。</span><span class="sxs-lookup"><span data-stu-id="a7c5a-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="a7c5a-154">調查事件</span><span class="sxs-lookup"><span data-stu-id="a7c5a-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="a7c5a-155">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a7c5a-155">See also</span></span>
- [<span data-ttu-id="a7c5a-156">事件概觀</span><span class="sxs-lookup"><span data-stu-id="a7c5a-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a7c5a-157">調查事件</span><span class="sxs-lookup"><span data-stu-id="a7c5a-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a7c5a-158">管理事件</span><span class="sxs-lookup"><span data-stu-id="a7c5a-158">Manage incidents</span></span>](manage-incidents.md)
