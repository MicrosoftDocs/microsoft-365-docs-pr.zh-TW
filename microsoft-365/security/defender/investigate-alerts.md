---
title: 調查 Microsoft 365 Defender 中的警示
description: 調查透過裝置、使用者和信箱查看的警示。
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
ms.openlocfilehash: a6e11aea14a7b8d99c0098b68951790328ec593e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782906"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="f2963-104">調查 Microsoft 365 Defender 中的警示</span><span class="sxs-lookup"><span data-stu-id="f2963-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f2963-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f2963-105">**Applies to:**</span></span>
- <span data-ttu-id="f2963-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2963-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f2963-107">提醒是指所有的事件，並指出您環境中發生惡意或可疑事件的基礎。</span><span class="sxs-lookup"><span data-stu-id="f2963-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="f2963-108">警示通常是廣泛攻擊的一部分，並提供有關事件的線索。</span><span class="sxs-lookup"><span data-stu-id="f2963-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="f2963-109">在 Microsoft 365 Defender 中，會將相關的警示彙集在一起，以形成[事件](incidents-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f2963-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="f2963-110">事件一定會提供更廣泛的攻擊內容，不過，當需要深入分析時，分析警示可能很重要。</span><span class="sxs-lookup"><span data-stu-id="f2963-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="f2963-111">[ **警示] 佇列** 會顯示目前的警示集。</span><span class="sxs-lookup"><span data-stu-id="f2963-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="f2963-112">您可以在 [Microsoft 365 安全性中心] 的 [快速啟動] ([security.microsoft.com](https://security.microsoft.com)) ] 中，從事件中取得警示佇列 **& 警示 > 警示**。</span><span class="sxs-lookup"><span data-stu-id="f2963-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="警示佇列的範例":::

<span data-ttu-id="f2963-114">來自不同 microsoft security 解決方案（如 microsoft defender for Endpoint、microsoft defender for Office 365 和 Microsoft 365 Defender）的警示會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="f2963-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="f2963-115">根據預設，Microsoft 365 security center 中的 [警示] 佇列會顯示過去30天的 [新增] 和 [進度] 警示。</span><span class="sxs-lookup"><span data-stu-id="f2963-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="f2963-116">最新的警示是在清單頂端，您可以先查看它。</span><span class="sxs-lookup"><span data-stu-id="f2963-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="f2963-117">您可以從預設的 [提醒] 佇列中，選取 [ **篩選** ]，以查看 **篩選** 窗格，您可以從中指定提醒的子集。</span><span class="sxs-lookup"><span data-stu-id="f2963-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="f2963-118">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="f2963-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="警示佇列之篩選窗格的範例":::

<span data-ttu-id="f2963-120">您可以根據這些準則來篩選警示：</span><span class="sxs-lookup"><span data-stu-id="f2963-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="f2963-121">嚴重性</span><span class="sxs-lookup"><span data-stu-id="f2963-121">Severity</span></span>
- <span data-ttu-id="f2963-122">狀態</span><span class="sxs-lookup"><span data-stu-id="f2963-122">Status</span></span>
- <span data-ttu-id="f2963-123">Category</span><span class="sxs-lookup"><span data-stu-id="f2963-123">Category</span></span>
- <span data-ttu-id="f2963-124">偵測來源</span><span class="sxs-lookup"><span data-stu-id="f2963-124">Detection source</span></span>
- <span data-ttu-id="f2963-125">標記</span><span class="sxs-lookup"><span data-stu-id="f2963-125">Tags</span></span>
- <span data-ttu-id="f2963-126">原則</span><span class="sxs-lookup"><span data-stu-id="f2963-126">Policy</span></span>
- <span data-ttu-id="f2963-127">受影響資產</span><span class="sxs-lookup"><span data-stu-id="f2963-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="f2963-128">分析警示</span><span class="sxs-lookup"><span data-stu-id="f2963-128">Analyze an alert</span></span>

<span data-ttu-id="f2963-129">若要查看 [主要提醒] 頁面，請選取警示的名稱。</span><span class="sxs-lookup"><span data-stu-id="f2963-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="f2963-130">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="f2963-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 安全性中心內警示的詳細資料頁面範例":::

<span data-ttu-id="f2963-132">您也可以從 [**管理警示**] 窗格中選取 [**開啟主要警示] 頁面** 動作。</span><span class="sxs-lookup"><span data-stu-id="f2963-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="f2963-133">警示頁面是由下列區段所組成：</span><span class="sxs-lookup"><span data-stu-id="f2963-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="f2963-134">警示案例，這是以時間順序與此警示相關的事件及警示鏈</span><span class="sxs-lookup"><span data-stu-id="f2963-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="f2963-135">摘要詳細資料</span><span class="sxs-lookup"><span data-stu-id="f2963-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 安全性中心內警示的詳細資料頁面範例":::

<span data-ttu-id="f2963-137">在 [警示] 頁面中，您可以選取任何實體旁的省略號 () **...** ]，以查看可用的動作，例如開啟警示頁面或將警示連結至另一個事件。</span><span class="sxs-lookup"><span data-stu-id="f2963-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="f2963-138">警示來源</span><span class="sxs-lookup"><span data-stu-id="f2963-138">Alert sources</span></span>
<span data-ttu-id="f2963-139">Microsoft 365Defender 警示可能來自 microsoft defender for Endpoint、microsoft defender for Office 365 和 Microsoft Cloud App Security 等解決方案。</span><span class="sxs-lookup"><span data-stu-id="f2963-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="f2963-140">您可能會注意到警示中帶有前置字元的警示。</span><span class="sxs-lookup"><span data-stu-id="f2963-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="f2963-141">下表提供指導方針，可協助您瞭解根據警示上的前置字母，警示來源的對應。</span><span class="sxs-lookup"><span data-stu-id="f2963-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="f2963-142">預置的 Guid 只是針對整合的經驗，例如整合的警示佇列、整合的提醒頁面、整合調查和整合事件。</span><span class="sxs-lookup"><span data-stu-id="f2963-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="f2963-143">預先符不會變更警示的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f2963-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="f2963-144">GUID 的唯一變更是預置的元件。</span><span class="sxs-lookup"><span data-stu-id="f2963-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="f2963-145">警示來源</span><span class="sxs-lookup"><span data-stu-id="f2963-145">Alert source</span></span> | <span data-ttu-id="f2963-146">預先符</span><span class="sxs-lookup"><span data-stu-id="f2963-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="f2963-147">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2963-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="f2963-148">範例：`fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="f2963-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="f2963-149">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2963-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="f2963-150">`da` 或 `ed` 自訂偵測警示</span><span class="sxs-lookup"><span data-stu-id="f2963-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="f2963-151">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2963-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="f2963-152">範例：`aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="f2963-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="f2963-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f2963-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="f2963-154">範例：`ca123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="f2963-154">Example: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 



### <a name="analyze-affected-assets"></a><span data-ttu-id="f2963-155">分析受影響的資產</span><span class="sxs-lookup"><span data-stu-id="f2963-155">Analyze affected assets</span></span>

<span data-ttu-id="f2963-156">[ **採取的動作** ] 區段包含受影響的資產清單，例如信箱、裝置，以及受此警示影響的使用者。</span><span class="sxs-lookup"><span data-stu-id="f2963-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="f2963-157">您也可以選取 [**操作中心] 中** 的 [查看]，以在 [Microsoft 365 安全性中心] 中查看重要訊息 **中心** 的 [**記錄**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="f2963-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="f2963-158">追蹤警示案例中的警示角色</span><span class="sxs-lookup"><span data-stu-id="f2963-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="f2963-159">警示案例會在處理樹狀檢視中顯示與警示相關的所有資產或實體。</span><span class="sxs-lookup"><span data-stu-id="f2963-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="f2963-160">當您第一次在選取的警示頁面上移動時，標題中的警示會是焦點。</span><span class="sxs-lookup"><span data-stu-id="f2963-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="f2963-161">提醒文章中的資產可展開和按一下。</span><span class="sxs-lookup"><span data-stu-id="f2963-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="f2963-162">它們可讓您在警示頁面的內容中採取動作，以提供額外的資訊並加速您的回應。</span><span class="sxs-lookup"><span data-stu-id="f2963-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="f2963-163">「警示案例」區段中可能會包含一個以上的警示，在您所選取的警示之前或之後，會顯示與相同執行樹狀目錄相關的其他警示。</span><span class="sxs-lookup"><span data-stu-id="f2963-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="f2963-164">在 [詳細資料] 頁面上查看其他警示資訊</span><span class="sxs-lookup"><span data-stu-id="f2963-164">View more alert information on the details page</span></span>

<span data-ttu-id="f2963-165">[詳細資料] 頁面會顯示所選警示的詳細資料，以及與其相關聯的詳細資料和動作。</span><span class="sxs-lookup"><span data-stu-id="f2963-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="f2963-166">如果您選取預警案例中的任何受影響的資產或實體，[詳細資料] 頁面會變更，以提供所選物件的上下文資訊和動作。</span><span class="sxs-lookup"><span data-stu-id="f2963-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="f2963-167">當您選取相關實體時，[詳細資料] 頁面會變更，以顯示所選實體類型的相關資訊、可用的歷史資訊，以及直接從 [警示] 頁面對此實體採取動作的選項。</span><span class="sxs-lookup"><span data-stu-id="f2963-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="f2963-168">管理警示</span><span class="sxs-lookup"><span data-stu-id="f2963-168">Manage alerts</span></span>

<span data-ttu-id="f2963-169">若要管理警示，請在其所在列的 [警示] 佇列中選取警示，以查看 [ **管理警示** ] 窗格。</span><span class="sxs-lookup"><span data-stu-id="f2963-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="f2963-170">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="f2963-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="警示摘要窗格的範例":::

<span data-ttu-id="f2963-172">[ **管理警示** ] 窗格可讓您指定：</span><span class="sxs-lookup"><span data-stu-id="f2963-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="f2963-173">警示狀態 (新的，已解決，正在進行中) 。</span><span class="sxs-lookup"><span data-stu-id="f2963-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="f2963-174">警示的分類 (未設定、True 警示、False 警示) 。</span><span class="sxs-lookup"><span data-stu-id="f2963-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="f2963-175">針對分類為 true 的警示，在 [ **判斷** ] 欄位中，警示的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="f2963-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="f2963-176">警示上的批註。</span><span class="sxs-lookup"><span data-stu-id="f2963-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="f2963-177">透過使用標記來管理提醒的一種方式。</span><span class="sxs-lookup"><span data-stu-id="f2963-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="f2963-178">Microsoft Defender for Office 365 的標籤功能會逐漸向內進行，而且目前在預覽中。</span><span class="sxs-lookup"><span data-stu-id="f2963-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="f2963-179">目前，已修改的標籤名稱只會套用至更新 *後* 所建立的警示。</span><span class="sxs-lookup"><span data-stu-id="f2963-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="f2963-180">在修改之前產生的警示將不會反映已更新的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="f2963-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="f2963-181">您也可以從這個窗格執行下列額外的動作：</span><span class="sxs-lookup"><span data-stu-id="f2963-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="f2963-182">開啟 [主要提醒] 頁面</span><span class="sxs-lookup"><span data-stu-id="f2963-182">Open the main alert page</span></span>
- <span data-ttu-id="f2963-183">諮詢 Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="f2963-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="f2963-184">查看提交</span><span class="sxs-lookup"><span data-stu-id="f2963-184">View submission</span></span>
- <span data-ttu-id="f2963-185">連結至另一個事件</span><span class="sxs-lookup"><span data-stu-id="f2963-185">Link to another incident</span></span>
- <span data-ttu-id="f2963-186">在時程表中查看警示</span><span class="sxs-lookup"><span data-stu-id="f2963-186">See the alert in a timeline</span></span>
- <span data-ttu-id="f2963-187">建立隱藏規則</span><span class="sxs-lookup"><span data-stu-id="f2963-187">Create a suppression rule</span></span>

<span data-ttu-id="f2963-188">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="f2963-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Microsoft 365 安全性中心內警示上的動作範例":::

<span data-ttu-id="f2963-190">其他動作的清單取決於警示類型。</span><span class="sxs-lookup"><span data-stu-id="f2963-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="f2963-191">解決警示</span><span class="sxs-lookup"><span data-stu-id="f2963-191">Resolve an alert</span></span>

<span data-ttu-id="f2963-192">當您完成對警示的分析而且可以解決後，請移至 [ **管理警示** ] 窗格中的警示，並將 it 狀態標示為 [ **已解決** ]，然後將其歸類為 **錯誤警示** 或 **True 警示**。</span><span class="sxs-lookup"><span data-stu-id="f2963-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="f2963-193">若為 true 警示，請在 **判斷** 欄位中指定警示的威脅類型。</span><span class="sxs-lookup"><span data-stu-id="f2963-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="f2963-194">分類提醒並指定其決定可協助調整 Microsoft 365 Defender，以提供更真實的警示及較少的虛假警示。</span><span class="sxs-lookup"><span data-stu-id="f2963-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2963-195">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f2963-195">Next steps</span></span>

<span data-ttu-id="f2963-196">視需要進行處理內事件，繼續進行 [調查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="f2963-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2963-197">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f2963-197">See also</span></span>

- [<span data-ttu-id="f2963-198">事件概觀</span><span class="sxs-lookup"><span data-stu-id="f2963-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f2963-199">管理事件</span><span class="sxs-lookup"><span data-stu-id="f2963-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="f2963-200">調查事件</span><span class="sxs-lookup"><span data-stu-id="f2963-200">Investigate incidents</span></span>](investigate-incidents.md)
