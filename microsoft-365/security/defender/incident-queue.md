---
title: 設定 Microsoft 365 Defender 中的事件優先順序
description: 瞭解如何在 Microsoft 365 Defender 中篩選事件佇列中的事件
keywords: 事件，佇列，概述，裝置，身分識別，使用者，信箱，電子郵件，事件，分析，回應
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 47d066fa20abe963f7afaa3b88cecc96fa6e87fc
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259582"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="c362c-104">設定 Microsoft 365 Defender 中的事件優先順序</span><span class="sxs-lookup"><span data-stu-id="c362c-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c362c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c362c-105">**Applies to:**</span></span>
- <span data-ttu-id="c362c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c362c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c362c-107">Microsoft 365Defender 會將相互關聯的分析和匯總相關的警報和自動調查套用到事件中。</span><span class="sxs-lookup"><span data-stu-id="c362c-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="c362c-108">Microsoft 365若 Microsoft 365 Defender 跨整個產品套件的端對端可視性，則您也會針對僅可識別為惡意的活動，觸發唯一的警示。</span><span class="sxs-lookup"><span data-stu-id="c362c-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="c362c-109">這種觀點可讓您的安全性分析更廣泛的攻擊案例，以協助他們更好地瞭解及處理整個組織中的複雜威脅。</span><span class="sxs-lookup"><span data-stu-id="c362c-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="c362c-110">[ **事件] 佇列** 顯示跨裝置、使用者和信箱建立的事件集合。</span><span class="sxs-lookup"><span data-stu-id="c362c-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="c362c-111">可協助您設定事件優先順序及制定明智的網路安全回應決策。</span><span class="sxs-lookup"><span data-stu-id="c362c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="c362c-112">您可以從事件中取得事件佇列， **& 警示 >** Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上的事件。</span><span class="sxs-lookup"><span data-stu-id="c362c-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="c362c-113">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="c362c-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

<span data-ttu-id="c362c-115">**最新的 [事件及警示**] 區段會顯示過去24小時所收到的警示和事件數目圖表。</span><span class="sxs-lookup"><span data-stu-id="c362c-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="c362c-116">根據預設，Microsoft 365 security center 中的事件佇列會顯示過去六個月所看到的事件。</span><span class="sxs-lookup"><span data-stu-id="c362c-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="c362c-117">最近的事件是在清單頂端，您可以先查看此專案。</span><span class="sxs-lookup"><span data-stu-id="c362c-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="c362c-118">事件佇列具有可自訂的欄 (選取 **[選擇欄** ]) ，可讓您深入瞭解事件或受影響的實體的不同特性。</span><span class="sxs-lookup"><span data-stu-id="c362c-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="c362c-119">這可協助您作出有關分析的事件優先順序決定。</span><span class="sxs-lookup"><span data-stu-id="c362c-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="c362c-120">如需更深入的洞察力，自動事件命名功能會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別），產生事件名稱。</span><span class="sxs-lookup"><span data-stu-id="c362c-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="c362c-121">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="c362c-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="c362c-122">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="c362c-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="c362c-123">在自動事件命名的首展之前，發生的事件，其名稱不會變更。</span><span class="sxs-lookup"><span data-stu-id="c362c-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="c362c-124">事件佇列也會公開多種篩選選項，當套用此選項時，您可以對環境中的所有現有事件執行大量的掃描，也可以決定將重點放在特定案例或威脅上。</span><span class="sxs-lookup"><span data-stu-id="c362c-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="c362c-125">在事件佇列套用篩選可協助判斷哪個事件需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="c362c-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="c362c-126">可用的篩選</span><span class="sxs-lookup"><span data-stu-id="c362c-126">Available filters</span></span>

<span data-ttu-id="c362c-127">您可以從預設的事件佇列中，選取 [ **篩選** ] 以查看篩選窗格，您可以從該窗格中查看篩選的事件集。</span><span class="sxs-lookup"><span data-stu-id="c362c-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="c362c-128">範例如下。</span><span class="sxs-lookup"><span data-stu-id="c362c-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件佇列之篩選窗格的範例":::

<span data-ttu-id="c362c-130">此表列出可用的篩選器名稱。</span><span class="sxs-lookup"><span data-stu-id="c362c-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="c362c-131">篩選名稱</span><span class="sxs-lookup"><span data-stu-id="c362c-131">Filter name</span></span> | <span data-ttu-id="c362c-132">描述</span><span class="sxs-lookup"><span data-stu-id="c362c-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="c362c-133">指派給</span><span class="sxs-lookup"><span data-stu-id="c362c-133">Assigned to</span></span> | <span data-ttu-id="c362c-134">您可以選擇顯示指派給您或「自動化」所處理的警示。</span><span class="sxs-lookup"><span data-stu-id="c362c-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="c362c-135">類別</span><span class="sxs-lookup"><span data-stu-id="c362c-135">Categories</span></span> | <span data-ttu-id="c362c-136">選擇 [類別]，以著重顯示特定的戰術、技術或攻擊元件。</span><span class="sxs-lookup"><span data-stu-id="c362c-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="c362c-137">分類</span><span class="sxs-lookup"><span data-stu-id="c362c-137">Classification</span></span> | <span data-ttu-id="c362c-138">根據相關警示的設定分類來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="c362c-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="c362c-139">其值包括 true 警示、false 警示或未設定。</span><span class="sxs-lookup"><span data-stu-id="c362c-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="c362c-140">資料敏感度</span><span class="sxs-lookup"><span data-stu-id="c362c-140">Data sensitivity</span></span> | <span data-ttu-id="c362c-141">某些攻擊鎖定外洩機密敏感性資料或重要資料。</span><span class="sxs-lookup"><span data-stu-id="c362c-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="c362c-142">透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。</span><span class="sxs-lookup"><span data-stu-id="c362c-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="c362c-143">只有在開啟 Microsoft 資訊保護時才適用。</span><span class="sxs-lookup"><span data-stu-id="c362c-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="c362c-144">裝置群組</span><span class="sxs-lookup"><span data-stu-id="c362c-144">Device group</span></span> | <span data-ttu-id="c362c-145">依定義的裝置群組篩選。</span><span class="sxs-lookup"><span data-stu-id="c362c-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="c362c-146">調查狀態</span><span class="sxs-lookup"><span data-stu-id="c362c-146">Investigation state</span></span> | <span data-ttu-id="c362c-147">依自動調查的狀態來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="c362c-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="c362c-148">多個類別</span><span class="sxs-lookup"><span data-stu-id="c362c-148">Multiple categories</span></span> | <span data-ttu-id="c362c-149">您可以選擇只查看已對應至多個類別的事件，進而可能造成更大的損毀。</span><span class="sxs-lookup"><span data-stu-id="c362c-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="c362c-150">多個服務來源</span><span class="sxs-lookup"><span data-stu-id="c362c-150">Multiple service sources</span></span>  | <span data-ttu-id="c362c-151">篩選，只會查看包含不同來源之警示的事件， (Microsoft defender for Endpoint，Microsoft Cloud App Security，microsoft defender for Identity，microsoft defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="c362c-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="c362c-152">作業系統平臺</span><span class="sxs-lookup"><span data-stu-id="c362c-152">OS platform</span></span> | <span data-ttu-id="c362c-153">依作業系統限制事件佇列查看。</span><span class="sxs-lookup"><span data-stu-id="c362c-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="c362c-154">服務來源</span><span class="sxs-lookup"><span data-stu-id="c362c-154">Service sources</span></span> | <span data-ttu-id="c362c-155">透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。</span><span class="sxs-lookup"><span data-stu-id="c362c-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="c362c-156">嚴重性</span><span class="sxs-lookup"><span data-stu-id="c362c-156">Severity</span></span> | <span data-ttu-id="c362c-157">事件的嚴重性是指它可對資產造成的影響。</span><span class="sxs-lookup"><span data-stu-id="c362c-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="c362c-158">嚴重性越高，影響就越大，而且通常需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="c362c-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="c362c-159">狀態</span><span class="sxs-lookup"><span data-stu-id="c362c-159">Status</span></span> | <span data-ttu-id="c362c-160">您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。</span><span class="sxs-lookup"><span data-stu-id="c362c-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="c362c-161">下一步</span><span class="sxs-lookup"><span data-stu-id="c362c-161">Next step</span></span>

<span data-ttu-id="c362c-162">決定需要最高優先順序的事件後，請先選取它，然後開始進行 [分析](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="c362c-162">After you've determined which incident requires the highest priority, select it and begin your [analysis](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c362c-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c362c-163">See also</span></span>
- [<span data-ttu-id="c362c-164">事件概觀</span><span class="sxs-lookup"><span data-stu-id="c362c-164">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c362c-165">分析事件</span><span class="sxs-lookup"><span data-stu-id="c362c-165">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="c362c-166">管理事件</span><span class="sxs-lookup"><span data-stu-id="c362c-166">Manage incidents</span></span>](manage-incidents.md)
