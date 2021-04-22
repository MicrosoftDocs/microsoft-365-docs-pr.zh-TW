---
title: 分析 Microsoft 365 Defender 中的警示
description: 分析透過裝置、使用者和信箱查看的警示。
keywords: 事件、警示、調查、分析、回應、關聯、攻擊、電腦、裝置、使用者、身分識別、身分識別、信箱、電子郵件、365、microsoft、m365
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
ms.openlocfilehash: 18b4df6a2dbb22235d6781f1430f7a75e319fbcf
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939539"
---
# <a name="analyze-alerts-in-microsoft-365-defender"></a><span data-ttu-id="6f2f4-104">分析 Microsoft 365 Defender 中的警示</span><span class="sxs-lookup"><span data-stu-id="6f2f4-104">Analyze alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6f2f4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6f2f4-105">**Applies to:**</span></span>
- <span data-ttu-id="6f2f4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f2f4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6f2f4-107">提醒是指所有的事件，並指出您環境中發生惡意或可疑事件的基礎。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="6f2f4-108">警示通常是廣泛攻擊的一部分，並提供有關事件的線索。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="6f2f4-109">在 Microsoft 365 Defender 中，相關的警示會彙集在一起，以形成 [事件](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="6f2f4-110">事件一定會提供更廣泛的攻擊內容，不過，當需要深入分析時，分析警示可能很重要。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="6f2f4-111">[ **警示] 佇列** 會顯示目前的警示集。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="6f2f4-112">您可以從 **事件 & 警示** 中取得警示佇列，以在 Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) 的快速啟動上 > 警示。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="警示佇列的範例":::

<span data-ttu-id="6f2f4-114">來自不同 Microsoft security 解決方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 及 Microsoft 365 Defender）的警示會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="6f2f4-115">根據預設，Microsoft 365 security center 中的 [提醒] 佇列會顯示過去30天的新和進行中的警示。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="6f2f4-116">最新的警示是在清單頂端，您可以先查看它。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="6f2f4-117">您可以從預設的 [提醒] 佇列中，選取 [ **篩選** ]，以查看 **篩選** 窗格，您可以從中指定提醒的子集。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="6f2f4-118">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="警示佇列之篩選窗格的範例":::

<span data-ttu-id="6f2f4-120">您可以根據這些準則來篩選警示：</span><span class="sxs-lookup"><span data-stu-id="6f2f4-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="6f2f4-121">嚴重性</span><span class="sxs-lookup"><span data-stu-id="6f2f4-121">Severity</span></span>
- <span data-ttu-id="6f2f4-122">狀態</span><span class="sxs-lookup"><span data-stu-id="6f2f4-122">Status</span></span>
- <span data-ttu-id="6f2f4-123">類別</span><span class="sxs-lookup"><span data-stu-id="6f2f4-123">Category</span></span>
- <span data-ttu-id="6f2f4-124">偵測來源</span><span class="sxs-lookup"><span data-stu-id="6f2f4-124">Detection source</span></span>
- <span data-ttu-id="6f2f4-125">標記</span><span class="sxs-lookup"><span data-stu-id="6f2f4-125">Tags</span></span>
- <span data-ttu-id="6f2f4-126">原則</span><span class="sxs-lookup"><span data-stu-id="6f2f4-126">Policy</span></span>
- <span data-ttu-id="6f2f4-127">受影響資產</span><span class="sxs-lookup"><span data-stu-id="6f2f4-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="6f2f4-128">分析警示</span><span class="sxs-lookup"><span data-stu-id="6f2f4-128">Analyze an alert</span></span>

<span data-ttu-id="6f2f4-129">若要查看 [主要提醒] 頁面，請選取警示的名稱。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="6f2f4-130">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 安全性中心內警示的詳細資料頁面範例":::

<span data-ttu-id="6f2f4-132">您也可以從 [**管理警示**] 窗格中選取 [**開啟主要警示] 頁面** 動作。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="6f2f4-133">警示頁面是由下列區段所組成：</span><span class="sxs-lookup"><span data-stu-id="6f2f4-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="6f2f4-134">警示案例</span><span class="sxs-lookup"><span data-stu-id="6f2f4-134">Alert story</span></span>
- <span data-ttu-id="6f2f4-135">採取 (包括受影響資產的動作) </span><span class="sxs-lookup"><span data-stu-id="6f2f4-135">Actions taken (including impacted assets)</span></span>
- <span data-ttu-id="6f2f4-136">相關事件</span><span class="sxs-lookup"><span data-stu-id="6f2f4-136">Related events</span></span>
- <span data-ttu-id="6f2f4-137">摘要詳細資料</span><span class="sxs-lookup"><span data-stu-id="6f2f4-137">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 安全性中心內警示的詳細資料頁面範例":::

<span data-ttu-id="6f2f4-139">在 [提醒] 頁面中，您可以選取任何實體旁的省略號 () **...** ]，以查看可用的動作，例如開啟特定資產頁面或採取特定的修復步驟。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-139">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the specific asset page or taking specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="6f2f4-140">分析受影響的資產</span><span class="sxs-lookup"><span data-stu-id="6f2f4-140">Analyze affected assets</span></span>

<span data-ttu-id="6f2f4-141">[ **採取的動作** ] 區段包含受影響的資產清單，例如信箱、裝置，以及受此警示影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-141">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="6f2f4-142">您也可以在 [重要訊息中心] 中選取 [**查看**]，以在 Microsoft 365 的 [安全性中心 **] 中查看 [** **記錄**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-142">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="6f2f4-143">追蹤警示案例中的警示角色</span><span class="sxs-lookup"><span data-stu-id="6f2f4-143">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="6f2f4-144">警示案例會在處理樹狀檢視中顯示與警示相關的所有資產或實體。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-144">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="6f2f4-145">當您第一次在選取的警示頁面上移動時，標題中的警示會是焦點。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-145">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="6f2f4-146">提醒文章中的資產可展開和按一下。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-146">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="6f2f4-147">它們可讓您在警示頁面的內容中採取動作，以提供額外的資訊並加速您的回應。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-147">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="6f2f4-148">「警示案例」區段中可能會包含一個以上的警示，在您所選取的警示之前或之後，會顯示與相同執行樹狀目錄相關的其他警示。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-148">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="6f2f4-149">在 [詳細資料] 頁面上查看其他警示資訊</span><span class="sxs-lookup"><span data-stu-id="6f2f4-149">View more alert information on the details page</span></span>

<span data-ttu-id="6f2f4-150">[詳細資料] 頁面會顯示所選警示的詳細資料，以及與其相關聯的詳細資料和動作。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-150">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="6f2f4-151">如果您選取預警案例中的任何受影響的資產或實體，[詳細資料] 頁面會變更，以提供所選物件的上下文資訊和動作。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-151">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="6f2f4-152">當您選取相關實體時，[詳細資料] 頁面會變更，以顯示所選實體類型的相關資訊、可用的歷史資訊，以及直接從 [警示] 頁面對此實體採取動作的選項。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-152">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="6f2f4-153">管理警示</span><span class="sxs-lookup"><span data-stu-id="6f2f4-153">Manage alerts</span></span>

<span data-ttu-id="6f2f4-154">若要管理警示，請在其所在列的 [警示] 佇列中選取警示，以查看 [ **管理警示** ] 窗格。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-154">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="6f2f4-155">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-155">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="警示摘要窗格的範例":::

<span data-ttu-id="6f2f4-157">[ **管理警示** ] 窗格可讓您指定：</span><span class="sxs-lookup"><span data-stu-id="6f2f4-157">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="6f2f4-158">警示狀態 (新的，已解決，正在進行中) 。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-158">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="6f2f4-159">警示的分類 (未設定、True 警示、False 警示) 。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-159">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="6f2f4-160">針對分類為 true 的警示，在 [ **判斷** ] 欄位中，警示的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-160">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="6f2f4-161">警示上的批註。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-161">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="6f2f4-162">透過使用標記來管理提醒的一種方式。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-162">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="6f2f4-163">Microsoft Defender for Office 365 的標記功能會逐漸增加，而且目前在預覽中。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-163">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="6f2f4-164">目前，已修改的標籤名稱只會套用至更新 *後* 所建立的警示。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-164">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="6f2f4-165">在修改之前產生的警示將不會反映已更新的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-165">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="6f2f4-166">您也可以從這個窗格執行下列額外的動作：</span><span class="sxs-lookup"><span data-stu-id="6f2f4-166">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="6f2f4-167">開啟 [主要提醒] 頁面</span><span class="sxs-lookup"><span data-stu-id="6f2f4-167">Open the main alert page</span></span>
- <span data-ttu-id="6f2f4-168">諮詢 Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="6f2f4-168">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="6f2f4-169">查看提交</span><span class="sxs-lookup"><span data-stu-id="6f2f4-169">View submission</span></span>
- <span data-ttu-id="6f2f4-170">連結至另一個事件</span><span class="sxs-lookup"><span data-stu-id="6f2f4-170">Link to another incident</span></span>
- <span data-ttu-id="6f2f4-171">在時程表中查看警示</span><span class="sxs-lookup"><span data-stu-id="6f2f4-171">See the alert in a timeline</span></span>
- <span data-ttu-id="6f2f4-172">建立隱藏規則</span><span class="sxs-lookup"><span data-stu-id="6f2f4-172">Create a suppression rule</span></span>

<span data-ttu-id="6f2f4-173">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-173">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Microsoft 365 安全性中心內警示的動作範例":::

<span data-ttu-id="6f2f4-175">其他動作的清單取決於警示類型。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-175">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="6f2f4-176">解決警示</span><span class="sxs-lookup"><span data-stu-id="6f2f4-176">Resolve an alert</span></span>

<span data-ttu-id="6f2f4-177">當您完成對警示的分析而且可以解決後，請移至 [ **管理警示** ] 窗格中的警示，並將 it 狀態標示為 [ **已解決** ]，然後將其歸類為 **錯誤警示** 或 **True 警示**。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-177">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="6f2f4-178">若為 true 警示，請在 **判斷** 欄位中指定警示的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-178">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="6f2f4-179">分類提醒並指定其判斷，可協助調整 Microsoft 365 Defender，以提供更真實的警示及較少的虛假警示。</span><span class="sxs-lookup"><span data-stu-id="6f2f4-179">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f2f4-180">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6f2f4-180">See also</span></span>

- [<span data-ttu-id="6f2f4-181">事件概觀</span><span class="sxs-lookup"><span data-stu-id="6f2f4-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6f2f4-182">管理事件</span><span class="sxs-lookup"><span data-stu-id="6f2f4-182">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="6f2f4-183">分析事件</span><span class="sxs-lookup"><span data-stu-id="6f2f4-183">Analyze incidents</span></span>](investigate-incidents.md)
