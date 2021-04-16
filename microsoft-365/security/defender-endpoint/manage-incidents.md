---
title: 管理 Microsoft Defender for Endpoint 事件
description: 指派事件、更新其狀態或設定其分類，以管理事件。
keywords: 事件、管理、指派、狀態、分類、true 警示、錯誤警示
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
ms.openlocfilehash: abb538972b48f8790286c0a546eecdd69fc83fb5
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862136"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="50df9-104">管理 Microsoft Defender for Endpoint 事件</span><span class="sxs-lookup"><span data-stu-id="50df9-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50df9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="50df9-105">**Applies to:**</span></span>
- [<span data-ttu-id="50df9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="50df9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="50df9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50df9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="50df9-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="50df9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="50df9-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="50df9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="50df9-110">管理事件是每個 cybersecurity 作業的重要部分。</span><span class="sxs-lookup"><span data-stu-id="50df9-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="50df9-111">您可以從 [ **事件] 佇列** 或 [ **事件管理] 窗格** 中選取事件，以管理事件。</span><span class="sxs-lookup"><span data-stu-id="50df9-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="50df9-112">從 [ **事件] 佇列** 中選取事件，會顯示 **事件管理窗格** ，您可以在其中開啟「事件」頁面以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="50df9-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![事件管理窗格的影像](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="50df9-114">您可以指派事件給您自己、變更狀態和分類、重新命名或批註，以追蹤其進度。</span><span class="sxs-lookup"><span data-stu-id="50df9-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="50df9-115">更深入瞭解時，系統會根據受影響的端點數目、受影響的使用者、偵測來源或類別等警示屬性，自動產生事件名稱。</span><span class="sxs-lookup"><span data-stu-id="50df9-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="50df9-116">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="50df9-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="50df9-117">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="50df9-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="50df9-118">自動事件命名的首次展示中已存在的事件，會保留其名稱。</span><span class="sxs-lookup"><span data-stu-id="50df9-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![事件詳細資料頁面的影像](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="50df9-120">指派事件</span><span class="sxs-lookup"><span data-stu-id="50df9-120">Assign incidents</span></span>
<span data-ttu-id="50df9-121">若尚未指派事件，您可以選取 [ **指派給我** ] 指派給您自己的事件。</span><span class="sxs-lookup"><span data-stu-id="50df9-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="50df9-122">這樣做不僅表示您承擔該事件的擁有權，還包括所有與該事件相關的警示。</span><span class="sxs-lookup"><span data-stu-id="50df9-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="50df9-123">設定狀態和分類</span><span class="sxs-lookup"><span data-stu-id="50df9-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="50df9-124">事件狀態</span><span class="sxs-lookup"><span data-stu-id="50df9-124">Incident status</span></span>
<span data-ttu-id="50df9-125">您可以在調查進行的過程中變更事件的狀態來將事件分類 (例如：**作用中** 或 **已解決**)。</span><span class="sxs-lookup"><span data-stu-id="50df9-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="50df9-126">這可協助您組織及管理小組回應事件的方式。</span><span class="sxs-lookup"><span data-stu-id="50df9-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="50df9-127">例如，SoC 分析員可以查看一天的緊急 **主動** 事件，並決定將其指派給自己進行調查。</span><span class="sxs-lookup"><span data-stu-id="50df9-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="50df9-128">或者，您的 SoC 分析員可能會將事件 **設定為已** 修正的事件。</span><span class="sxs-lookup"><span data-stu-id="50df9-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="50df9-129">分類</span><span class="sxs-lookup"><span data-stu-id="50df9-129">Classification</span></span>
<span data-ttu-id="50df9-130">您可以選擇不要設定分類，或決定將事件指定為 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="50df9-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="50df9-131">這樣做可協助小組查看模式及深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="50df9-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="50df9-132">新增註解</span><span class="sxs-lookup"><span data-stu-id="50df9-132">Add comments</span></span>
<span data-ttu-id="50df9-133">您可以新增註解及檢視與事件相關的歷史活動，以查看先前所做的變更。</span><span class="sxs-lookup"><span data-stu-id="50df9-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="50df9-134">對警示進行變更或新增註解時，便會記錄在 [註解和記錄] 區段中。</span><span class="sxs-lookup"><span data-stu-id="50df9-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="50df9-135">新增的註解會立即顯示在窗格中。</span><span class="sxs-lookup"><span data-stu-id="50df9-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="50df9-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="50df9-136">Related topics</span></span>
- [<span data-ttu-id="50df9-137">事件佇列</span><span class="sxs-lookup"><span data-stu-id="50df9-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="50df9-138">查看及組織事件佇列</span><span class="sxs-lookup"><span data-stu-id="50df9-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="50df9-139">調查事件</span><span class="sxs-lookup"><span data-stu-id="50df9-139">Investigate incidents</span></span>](investigate-incidents.md)
