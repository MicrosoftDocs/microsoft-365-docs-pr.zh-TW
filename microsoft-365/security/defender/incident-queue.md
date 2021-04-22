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
ms.openlocfilehash: c3efff1e7ebb3a5e868ede018512d12cf38e38fc
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939703"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5b2fa-104">設定 Microsoft 365 Defender 中的事件優先順序</span><span class="sxs-lookup"><span data-stu-id="5b2fa-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5b2fa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5b2fa-105">**Applies to:**</span></span>
- <span data-ttu-id="5b2fa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b2fa-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5b2fa-107">Microsoft 365 Defender 會將關聯性分析和匯總相關的警示和自動調查套用到事件中。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="5b2fa-108">除了 Microsoft 365 Defender 跨整個產品套件的端對端知名度時，microsoft 365 Defender 也會針對活動，觸發唯一警示。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="5b2fa-109">這種觀點可讓您的安全性分析更廣泛的攻擊案例，以協助他們更好地瞭解及處理整個組織中的複雜威脅。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="5b2fa-110">[ **事件] 佇列** 顯示跨裝置、使用者和信箱建立的事件集合。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="5b2fa-111">可協助您設定事件優先順序及制定明智的網路安全回應決策。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="5b2fa-112">您可以從事件中取得事件佇列 **& 警示 >** Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上的事件。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

<span data-ttu-id="5b2fa-114">根據預設，Microsoft 365 security center 中的事件佇列會顯示過去六個月所看到的事件。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-114">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="5b2fa-115">最近的事件是在清單頂端，您可以先查看此專案。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="5b2fa-116">事件佇列具有可自訂的欄 (選取 **[選擇欄** ]) ，可讓您深入瞭解事件或受影響的實體的不同特性。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="5b2fa-117">這可協助您作出有關分析的事件優先順序決定。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-117">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="5b2fa-118">如需更深入的洞察力，自動事件命名功能會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別），產生事件名稱。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="5b2fa-119">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="5b2fa-120">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="5b2fa-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="5b2fa-121">在自動事件命名的首展之前，發生的事件，其名稱不會變更。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="5b2fa-122">事件佇列也會公開多種篩選選項，當套用此選項時，您可以對環境中的所有現有事件執行大量的掃描，也可以決定將重點放在特定案例或威脅上。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="5b2fa-123">在事件佇列套用篩選可協助判斷哪個事件需要立即處理。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="5b2fa-124">可用的篩選</span><span class="sxs-lookup"><span data-stu-id="5b2fa-124">Available filters</span></span>

<span data-ttu-id="5b2fa-125">您可以從預設的事件佇列中，選取 [ **篩選** ] 以查看篩選窗格，您可以從該窗格中查看篩選的事件集。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="5b2fa-126">範例如下。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件佇列之篩選窗格的範例":::

<span data-ttu-id="5b2fa-128">此表列出可用的篩選器名稱。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="5b2fa-129">篩選名稱</span><span class="sxs-lookup"><span data-stu-id="5b2fa-129">Filter name</span></span> | <span data-ttu-id="5b2fa-130">描述</span><span class="sxs-lookup"><span data-stu-id="5b2fa-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5b2fa-131">指派給</span><span class="sxs-lookup"><span data-stu-id="5b2fa-131">Assigned to</span></span> | <span data-ttu-id="5b2fa-132">您可以選擇顯示指派給您或「自動化」所處理的警示。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="5b2fa-133">類別</span><span class="sxs-lookup"><span data-stu-id="5b2fa-133">Categories</span></span> | <span data-ttu-id="5b2fa-134">選擇 [類別]，以著重顯示特定的戰術、技術或攻擊元件。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="5b2fa-135">分類</span><span class="sxs-lookup"><span data-stu-id="5b2fa-135">Classification</span></span> | <span data-ttu-id="5b2fa-136">根據相關警示的設定分類來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="5b2fa-137">其值包括 true 警示、false 警示或未設定。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="5b2fa-138">資料敏感度</span><span class="sxs-lookup"><span data-stu-id="5b2fa-138">Data sensitivity</span></span> | <span data-ttu-id="5b2fa-139">某些攻擊鎖定外洩機密敏感性資料或重要資料。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="5b2fa-140">透過套用篩選來查看事件是否涉及敏感性資料，您可以快速判斷敏感性資訊是否已遭入侵，並優先處理這些事件。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="5b2fa-141">只有在開啟 Microsoft 資訊保護時才適用。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="5b2fa-142">裝置群組</span><span class="sxs-lookup"><span data-stu-id="5b2fa-142">Device group</span></span> | <span data-ttu-id="5b2fa-143">依定義的裝置群組篩選。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="5b2fa-144">調查狀態</span><span class="sxs-lookup"><span data-stu-id="5b2fa-144">Investigation state</span></span> | <span data-ttu-id="5b2fa-145">依自動調查的狀態來篩選事件。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="5b2fa-146">多個類別</span><span class="sxs-lookup"><span data-stu-id="5b2fa-146">Multiple categories</span></span> | <span data-ttu-id="5b2fa-147">您可以選擇只查看已對應至多個類別的事件，進而可能造成更大的損毀。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="5b2fa-148">多個服務來源</span><span class="sxs-lookup"><span data-stu-id="5b2fa-148">Multiple service sources</span></span>  | <span data-ttu-id="5b2fa-149">篩選，只會查看包含不同來源之警示的事件， (Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender for Identity、Microsoft Defender for Office 365) 。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="5b2fa-150">作業系統平臺</span><span class="sxs-lookup"><span data-stu-id="5b2fa-150">OS platform</span></span> | <span data-ttu-id="5b2fa-151">依作業系統限制事件佇列查看。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="5b2fa-152">服務來源</span><span class="sxs-lookup"><span data-stu-id="5b2fa-152">Service sources</span></span> | <span data-ttu-id="5b2fa-153">透過選擇特定來源，便可專注於包含來自至少一個所選來源警示的事件。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="5b2fa-154">嚴重性</span><span class="sxs-lookup"><span data-stu-id="5b2fa-154">Severity</span></span> | <span data-ttu-id="5b2fa-155">事件的嚴重性是指它可對資產造成的影響。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="5b2fa-156">嚴重性越高，影響就越大，而且通常需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="5b2fa-157">狀態</span><span class="sxs-lookup"><span data-stu-id="5b2fa-157">Status</span></span> | <span data-ttu-id="5b2fa-158">您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="5b2fa-159">下一步</span><span class="sxs-lookup"><span data-stu-id="5b2fa-159">Next step</span></span>

<span data-ttu-id="5b2fa-160">決定需要最高優先順序的事件後，請先選取它，然後開始進行 [分析](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="5b2fa-160">After you've determined which incident requires the highest priority, select it and begin your [analysis](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5b2fa-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b2fa-161">See also</span></span>
- [<span data-ttu-id="5b2fa-162">事件概觀</span><span class="sxs-lookup"><span data-stu-id="5b2fa-162">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5b2fa-163">分析事件</span><span class="sxs-lookup"><span data-stu-id="5b2fa-163">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5b2fa-164">管理事件</span><span class="sxs-lookup"><span data-stu-id="5b2fa-164">Manage incidents</span></span>](manage-incidents.md)
