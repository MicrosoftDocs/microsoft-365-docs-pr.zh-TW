---
title: 查看及組織事件佇列
ms.reviewer: ''
description: 請參閱事件清單，並瞭解如何套用篩選來限制清單，並取得更具焦點的視圖。
keywords: view，組織，事件，匯總，調查，佇列，ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56fd5aa10cf30e7bdcad213a68430b460e65647c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844211"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="9786c-104">查看和組織 Microsoft Defender for Endpoint 事件佇列</span><span class="sxs-lookup"><span data-stu-id="9786c-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9786c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9786c-105">**Applies to:**</span></span>
- [<span data-ttu-id="9786c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9786c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9786c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9786c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9786c-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="9786c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9786c-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="9786c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="9786c-110">[ **事件] 佇列** 顯示從您網路中的裝置標記的事件集合。</span><span class="sxs-lookup"><span data-stu-id="9786c-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="9786c-111">可協助您設定事件優先順序及制定明智的網路安全回應決策。</span><span class="sxs-lookup"><span data-stu-id="9786c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="9786c-112">根據預設，佇列會顯示過去30天內所看到的事件，最新的事件會顯示在清單的頂端，以協助您先看到最近的事件。</span><span class="sxs-lookup"><span data-stu-id="9786c-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="9786c-113">您可以從數個選項中選擇自訂事件佇列視圖。</span><span class="sxs-lookup"><span data-stu-id="9786c-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="9786c-114">您可以在上方導覽上進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="9786c-114">On the top navigation you can:</span></span>
- <span data-ttu-id="9786c-115">自訂欄以新增或移除欄</span><span class="sxs-lookup"><span data-stu-id="9786c-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="9786c-116">修改每頁查看的專案數</span><span class="sxs-lookup"><span data-stu-id="9786c-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="9786c-117">選取每頁顯示的專案</span><span class="sxs-lookup"><span data-stu-id="9786c-117">Select the items to show per page</span></span>
- <span data-ttu-id="9786c-118">批次-選取要指派的事件</span><span class="sxs-lookup"><span data-stu-id="9786c-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="9786c-119">在頁面間流覽</span><span class="sxs-lookup"><span data-stu-id="9786c-119">Navigate between pages</span></span>
- <span data-ttu-id="9786c-120">套用篩選</span><span class="sxs-lookup"><span data-stu-id="9786c-120">Apply filters</span></span>

![事件佇列的影像](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="9786c-122">排序及篩選事件佇列</span><span class="sxs-lookup"><span data-stu-id="9786c-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="9786c-123">您可以套用下列篩選器來限制事件清單，並取得更具焦點的視圖。</span><span class="sxs-lookup"><span data-stu-id="9786c-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="9786c-124">嚴重性</span><span class="sxs-lookup"><span data-stu-id="9786c-124">Severity</span></span>

<span data-ttu-id="9786c-125">事件嚴重性</span><span class="sxs-lookup"><span data-stu-id="9786c-125">Incident severity</span></span> | <span data-ttu-id="9786c-126">描述</span><span class="sxs-lookup"><span data-stu-id="9786c-126">Description</span></span>
:---|:---
<span data-ttu-id="9786c-127">高</span><span class="sxs-lookup"><span data-stu-id="9786c-127">High</span></span> </br><span data-ttu-id="9786c-128"> (Red) </span><span class="sxs-lookup"><span data-stu-id="9786c-128">(Red)</span></span> | <span data-ttu-id="9786c-129">威脅常常與高級持續威脅 (APT) 相關聯。</span><span class="sxs-lookup"><span data-stu-id="9786c-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="9786c-130">因為這些事件可能會對裝置造成損毀，所以會指出高風險。</span><span class="sxs-lookup"><span data-stu-id="9786c-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="9786c-131">中</span><span class="sxs-lookup"><span data-stu-id="9786c-131">Medium</span></span> </br><span data-ttu-id="9786c-132"> (橙色) </span><span class="sxs-lookup"><span data-stu-id="9786c-132">(Orange)</span></span> | <span data-ttu-id="9786c-133">組織中極少看到的威脅，例如反常登錄變更、可疑檔案的執行，以及常見攻擊階段的觀察行為。</span><span class="sxs-lookup"><span data-stu-id="9786c-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="9786c-134">低</span><span class="sxs-lookup"><span data-stu-id="9786c-134">Low</span></span> </br><span data-ttu-id="9786c-135"> (黃色) </span><span class="sxs-lookup"><span data-stu-id="9786c-135">(Yellow)</span></span> | <span data-ttu-id="9786c-136">與流行惡意程式碼和駭客攻擊相關的威脅，不一定表示組織的高級威脅。</span><span class="sxs-lookup"><span data-stu-id="9786c-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="9786c-137">參考</span><span class="sxs-lookup"><span data-stu-id="9786c-137">Informational</span></span> </br><span data-ttu-id="9786c-138"> (灰色) </span><span class="sxs-lookup"><span data-stu-id="9786c-138">(Grey)</span></span> | <span data-ttu-id="9786c-139">資訊性事件可能不會被視為對網路有害，但很有可能會讓追蹤。</span><span class="sxs-lookup"><span data-stu-id="9786c-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="9786c-140">指派給</span><span class="sxs-lookup"><span data-stu-id="9786c-140">Assigned to</span></span>
<span data-ttu-id="9786c-141">您可以選取指派給任何人或指派給您來篩選清單。</span><span class="sxs-lookup"><span data-stu-id="9786c-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="9786c-142">Category</span><span class="sxs-lookup"><span data-stu-id="9786c-142">Category</span></span>
<span data-ttu-id="9786c-143">根據 cybersecurity kill 鏈所在階段的描述來分類事件。</span><span class="sxs-lookup"><span data-stu-id="9786c-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="9786c-144">此視圖可協助威脅分析人員判斷根據內容部署的優先順序、緊急性和對應的回應策略。</span><span class="sxs-lookup"><span data-stu-id="9786c-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="9786c-145">狀態</span><span class="sxs-lookup"><span data-stu-id="9786c-145">Status</span></span>
<span data-ttu-id="9786c-146">您可以根據事件狀態來限制顯示的事件清單，以查看哪些事件為作用中或已解決。</span><span class="sxs-lookup"><span data-stu-id="9786c-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="9786c-147">資料敏感度</span><span class="sxs-lookup"><span data-stu-id="9786c-147">Data sensitivity</span></span>
<span data-ttu-id="9786c-148">使用此篩選器顯示包含敏感度標籤的事件。</span><span class="sxs-lookup"><span data-stu-id="9786c-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="9786c-149">事件命名</span><span class="sxs-lookup"><span data-stu-id="9786c-149">Incident naming</span></span>

<span data-ttu-id="9786c-150">若要深入瞭解事件的範圍，事件名稱會根據警示屬性（如受到影響的端點數目、受影響的使用者、偵測來源或類別）自動產生。</span><span class="sxs-lookup"><span data-stu-id="9786c-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="9786c-151">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="9786c-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="9786c-152">在自動事件命名的首次推出之前，發生的事件會保留其名稱。</span><span class="sxs-lookup"><span data-stu-id="9786c-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="9786c-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9786c-153">See also</span></span>
- [<span data-ttu-id="9786c-154">事件佇列</span><span class="sxs-lookup"><span data-stu-id="9786c-154">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="9786c-155">管理事件</span><span class="sxs-lookup"><span data-stu-id="9786c-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="9786c-156">調查事件</span><span class="sxs-lookup"><span data-stu-id="9786c-156">Investigate incidents</span></span>](investigate-incidents.md)

