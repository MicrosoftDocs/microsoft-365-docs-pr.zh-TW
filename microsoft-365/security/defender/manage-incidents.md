---
title: 管理 Microsoft 365 Defender 中的事件
description: 了解如何指派及更新狀態
keywords: 事件、事件、分析、回應、警示、關聯警示、指派、更新、狀態、管理、分類、microsoft、365、m365
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
ms.openlocfilehash: 09c391d6b02e1273f55070283a6e11454f677114
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299998"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="907d1-104">管理 Microsoft 365 Defender 中的事件</span><span class="sxs-lookup"><span data-stu-id="907d1-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="907d1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="907d1-105">**Applies to:**</span></span>
- <span data-ttu-id="907d1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="907d1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="907d1-107">事件管理對於確保威脅已包含並加以解決非常重要。</span><span class="sxs-lookup"><span data-stu-id="907d1-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="907d1-108">您可以在 Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上，管理事件 **& 警示 > 事件**。</span><span class="sxs-lookup"><span data-stu-id="907d1-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="907d1-109">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="907d1-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="事件佇列的範例":::

<span data-ttu-id="907d1-111">您可以透過下列方式管理您的事件：</span><span class="sxs-lookup"><span data-stu-id="907d1-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="907d1-112">變更事件名稱</span><span class="sxs-lookup"><span data-stu-id="907d1-112">Change the incident name</span></span>
- <span data-ttu-id="907d1-113">新增事件標記。</span><span class="sxs-lookup"><span data-stu-id="907d1-113">Add incident tags.</span></span>
- <span data-ttu-id="907d1-114">指派事件給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="907d1-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="907d1-115">解決這些問題</span><span class="sxs-lookup"><span data-stu-id="907d1-115">Resolve them</span></span> 
- <span data-ttu-id="907d1-116">設定它的分類和決定</span><span class="sxs-lookup"><span data-stu-id="907d1-116">Set its classification and determination</span></span>
- <span data-ttu-id="907d1-117">新增批註。</span><span class="sxs-lookup"><span data-stu-id="907d1-117">Add comments.</span></span>

<span data-ttu-id="907d1-118">您可以從「 **管理事件** 」窗格中管理事件的事件。</span><span class="sxs-lookup"><span data-stu-id="907d1-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="907d1-119">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="907d1-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件的管理事件窗格範例":::

<span data-ttu-id="907d1-121">您可以從下列專案上的 **管理事件** 連結，顯示此窗格：</span><span class="sxs-lookup"><span data-stu-id="907d1-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="907d1-122">事件佇列中事件的屬性窗格。</span><span class="sxs-lookup"><span data-stu-id="907d1-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="907d1-123">事件的 **摘要** 頁面。</span><span class="sxs-lookup"><span data-stu-id="907d1-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="907d1-124">在分析您想要將警示從某個事件移動到另一個事件的情況下，您也可以在 [ **警示** ] 索引標籤中執行這項操作，進而建立一個包含所有相關警示的較大或較小的事件。</span><span class="sxs-lookup"><span data-stu-id="907d1-124">In cases where, while analyzing you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="907d1-125">編輯事件名稱</span><span class="sxs-lookup"><span data-stu-id="907d1-125">Edit the incident name</span></span>

<span data-ttu-id="907d1-126">Microsoft 365Defender 會根據警示屬性（如受影響的端點數目、受影響的使用者、偵測來源或類別）自動指派名稱。</span><span class="sxs-lookup"><span data-stu-id="907d1-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="907d1-127">這可讓您快速瞭解事件的範圍。</span><span class="sxs-lookup"><span data-stu-id="907d1-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="907d1-128">例如：多 *個來源所報告之多個端點上的多階段事件。*</span><span class="sxs-lookup"><span data-stu-id="907d1-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="907d1-129">您可以在 [**管理事件**] 窗格上的 [**事件名稱**] 欄位中編輯事件名稱。</span><span class="sxs-lookup"><span data-stu-id="907d1-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="907d1-130">在自動事件命名功能的展示中所發生的事件，會保留其名稱。</span><span class="sxs-lookup"><span data-stu-id="907d1-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="907d1-131">新增事件標籤</span><span class="sxs-lookup"><span data-stu-id="907d1-131">Add incident tags</span></span>

<span data-ttu-id="907d1-132">您可以將自訂標記新增至事件，例如標示具有共同特性的事件群組。</span><span class="sxs-lookup"><span data-stu-id="907d1-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="907d1-133">您可以稍後針對所有包含特定標記的事件，篩選事件佇列。</span><span class="sxs-lookup"><span data-stu-id="907d1-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="907d1-134">當您開始輸入時，您可以選擇從選取的標記清單中進行選取。</span><span class="sxs-lookup"><span data-stu-id="907d1-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="907d1-135">指派事件</span><span class="sxs-lookup"><span data-stu-id="907d1-135">Assign incidents</span></span>

<span data-ttu-id="907d1-136">若尚未指派事件，您可以選取 [ **指派給** ] 並指定使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="907d1-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="907d1-137">這樣做會指派事件的擁有權及與其相關聯的所有警示。</span><span class="sxs-lookup"><span data-stu-id="907d1-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="907d1-138">解決事件</span><span class="sxs-lookup"><span data-stu-id="907d1-138">Resolve incident</span></span>

<span data-ttu-id="907d1-139">如果事件已經修正，請選取 [ **解決事件** ]，將切換移至右邊。</span><span class="sxs-lookup"><span data-stu-id="907d1-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="907d1-140">請注意，解決事件也會解決與該事件相關的所有連結和主動警示。</span><span class="sxs-lookup"><span data-stu-id="907d1-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="907d1-141">未解析的事件會顯示為作用 **中。**</span><span class="sxs-lookup"><span data-stu-id="907d1-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="907d1-142">設定分類和決定</span><span class="sxs-lookup"><span data-stu-id="907d1-142">Set the classification and determination</span></span>

<span data-ttu-id="907d1-143">「事件分類」是指從 [ **分類** ] 欄位設定的是 true 警示或假警示。</span><span class="sxs-lookup"><span data-stu-id="907d1-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="907d1-144">如果是真正的警示，您也應該指定其 **判斷** 欄位所使用的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="907d1-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="907d1-145">指定威脅類型可協助安全小組看到威脅模式，並採取行動以保護組織。</span><span class="sxs-lookup"><span data-stu-id="907d1-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="907d1-146">新增註解</span><span class="sxs-lookup"><span data-stu-id="907d1-146">Add comments</span></span>

<span data-ttu-id="907d1-147">您可以使用 [ **批註** ] 欄位，將多個批註新增至事件。</span><span class="sxs-lookup"><span data-stu-id="907d1-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="907d1-148">每個評論都會新增至事件的歷史事件。</span><span class="sxs-lookup"><span data-stu-id="907d1-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="907d1-149">您可以在 [**摘要**] 頁面上，看到 [**批註和記錄**] 連結中的事件批註和記錄。</span><span class="sxs-lookup"><span data-stu-id="907d1-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="907d1-150">後續步驟</span><span class="sxs-lookup"><span data-stu-id="907d1-150">Next steps</span></span>

<span data-ttu-id="907d1-151">針對新的事件，開始進行 [調查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="907d1-151">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="907d1-152">若為處理中的事件，請繼續進行 [調查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="907d1-152">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="907d1-153">若為解決的事件，請執行 [事件後檢查](first-incident-post.md)。</span><span class="sxs-lookup"><span data-stu-id="907d1-153">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="907d1-154">請參閱</span><span class="sxs-lookup"><span data-stu-id="907d1-154">See also</span></span>

- [<span data-ttu-id="907d1-155">事件概觀</span><span class="sxs-lookup"><span data-stu-id="907d1-155">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="907d1-156">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="907d1-156">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="907d1-157">調查事件</span><span class="sxs-lookup"><span data-stu-id="907d1-157">Investigate incidents</span></span>](investigate-incidents.md)
