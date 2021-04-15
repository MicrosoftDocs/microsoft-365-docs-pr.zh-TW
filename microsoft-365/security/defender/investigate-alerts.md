---
title: 調查 Microsoft 365 Defender 中的警示
description: 調查透過裝置、使用者和信箱查看的警示。
keywords: 事件, 警示, 調查, 關聯, 攻擊, 電腦, 裝置, 使用者, 身分識別, 身分識別, 信箱, 電子郵件, 365, microsoft, m365
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
ms.openlocfilehash: 601a8674327c424592c65014793599dc19b2bcd3
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51759429"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="f0fd8-104">調查 Microsoft 365 Defender 中的警示</span><span class="sxs-lookup"><span data-stu-id="f0fd8-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f0fd8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f0fd8-105">**Applies to:**</span></span>
- <span data-ttu-id="f0fd8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0fd8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f0fd8-107">提醒是指所有的事件，並指出您環境中發生惡意或可疑事件的基礎。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="f0fd8-108">警示通常是廣泛攻擊的一部分，並提供有關事件的線索。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="f0fd8-109">在 Microsoft 365 Defender 中，相關的警示會彙集在一起，以形成事件。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="f0fd8-110">事件一定會提供更廣泛的攻擊內容，但是在需要深入分析時，調查警示會非常有用。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="f0fd8-111">使用調查中的警示頁面</span><span class="sxs-lookup"><span data-stu-id="f0fd8-111">Using alert pages in investigations</span></span>

<span data-ttu-id="f0fd8-112">在任何事件頁面的 [警示] 索引標籤中，選取警示可將您帶入個別警示頁面。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="f0fd8-113">警示頁面包含三個區段：受影響的資產、警示案例及詳細資料窗格。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![警示範例的影像頁面](../../media/new-alert-page2.png)

<span data-ttu-id="f0fd8-115">在 [提醒] 頁面中，您可以選取任何實體旁邊的三個點圖示 () **...** ，這樣您就能看到可用的動作，例如開啟特定資產頁面或執行特定的修復步驟。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="f0fd8-116">分析受影響的資產</span><span class="sxs-lookup"><span data-stu-id="f0fd8-116">Analyze affected assets</span></span>
<span data-ttu-id="f0fd8-117">「受影響的資產」區段會列出受此警示影響的信箱、裝置和使用者。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="f0fd8-118">選取任何資產卡片都會以資訊顯示詳細資料側窗格，包括有關資產的其他警示（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="f0fd8-119">追蹤警示案例中的警示角色</span><span class="sxs-lookup"><span data-stu-id="f0fd8-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="f0fd8-120">警示案例會在處理樹狀檢視中顯示與警示相關的所有資產或實體。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="f0fd8-121">當您第一次在選取的警示頁面上移動時，標題中的警示會是焦點。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="f0fd8-122">提醒文章中的資產可展開和按一下。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="f0fd8-123">它們可讓您在警示頁面的內容中採取行動，以提供額外的資訊並加速回應。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="f0fd8-124">「警示案例」區段中可能會包含一個以上的警示，在您所選取的警示之前或之後，會顯示與相同執行樹狀目錄相關的其他警示。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="f0fd8-125">在詳細資料窗格中查看更多警示資訊</span><span class="sxs-lookup"><span data-stu-id="f0fd8-125">View more alert information in the details pane</span></span>

<span data-ttu-id="f0fd8-126">[詳細資料] 窗格會先顯示選取警示的詳細資料，以及與其相關聯的詳細資料和動作。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="f0fd8-127">如果您選取預警案例中的任何受影響的資產或實體，詳細資料窗格會變更，以提供所選物件的上下文資訊和動作。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="f0fd8-128">當您選取相關實體時，[詳細資料] 窗格會變更，以顯示所選實體類型的相關資訊、可用的歷史資訊，以及直接從 [警示] 頁面採取動作的選項。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="f0fd8-129">管理警示</span><span class="sxs-lookup"><span data-stu-id="f0fd8-129">Manage alerts</span></span>

<span data-ttu-id="f0fd8-130">當您完成調查提醒後，您可以回到您已開始的警示，將警示的狀態標示為 [已解決]，然後將其歸類為「錯誤警示」或「True 警示」。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="f0fd8-131">分類提醒可協助調整您的產品，以提供更真實的警示及不太虛假的提醒。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="f0fd8-132">透過使用標記來管理提醒的一種方式。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="f0fd8-133">Microsoft Defender for Office 365 的標記功能會逐漸推出，而且目前在預覽中。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="f0fd8-134">目前，已修改的標籤名稱只會套用至更新 *後* 所建立的警示。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="f0fd8-135">修改之前產生的警示不會反映已更新的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="f0fd8-136">管理整合的提醒佇列</span><span class="sxs-lookup"><span data-stu-id="f0fd8-136">Manage the unified alert queue</span></span>

<span data-ttu-id="f0fd8-137">在 [事件] 下選取 [Microsoft 365 安全性中心] 導覽窗格中的警示 & 警示會帶您前往整合提醒佇列。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="f0fd8-138">來自不同 Microsoft security 解決方案（如 Microsoft Defender for Endpoint、Microsoft Defender for Office 365 及 Microsoft 365 Defender）的警示會顯示在此區段中。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![[範例警示] 頁面的圖像](../../media/unified-alert-queue.png)

<span data-ttu-id="f0fd8-140">[警示] 佇列顯示網路中已標示的警示清單。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="f0fd8-141">根據預設，佇列會顯示過去30天內看到的警示。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="f0fd8-142">最新的警示會顯示在清單的頂端，可協助您先看到最近的警示。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="f0fd8-143">在啟動時，[整合的提醒] 佇列只會有7天的 Microsoft Defender for Office 365 的可用警示。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="f0fd8-144">佇列將繼續隨著時間建立。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-144">The queue will continue to build over time.</span></span> <span data-ttu-id="f0fd8-145">如果您需要在啟動 [整合提醒] 佇列之前，對提醒進行分類，請使用 [安全性與合規性中心](https://protection.office.com/viewalerts)中的 [警示] 佇列。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="f0fd8-146">在上方導覽中，您可以：</span><span class="sxs-lookup"><span data-stu-id="f0fd8-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="f0fd8-147">套用篩選</span><span class="sxs-lookup"><span data-stu-id="f0fd8-147">Apply filters</span></span>
- <span data-ttu-id="f0fd8-148">自訂欄以新增或移除欄</span><span class="sxs-lookup"><span data-stu-id="f0fd8-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="f0fd8-149">匯出資料</span><span class="sxs-lookup"><span data-stu-id="f0fd8-149">Export data</span></span>

<span data-ttu-id="f0fd8-150">您也可以根據不同的準則來篩選警示：</span><span class="sxs-lookup"><span data-stu-id="f0fd8-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="f0fd8-151">嚴重性</span><span class="sxs-lookup"><span data-stu-id="f0fd8-151">Severity</span></span>
- <span data-ttu-id="f0fd8-152">狀態</span><span class="sxs-lookup"><span data-stu-id="f0fd8-152">Status</span></span>
- <span data-ttu-id="f0fd8-153">類別</span><span class="sxs-lookup"><span data-stu-id="f0fd8-153">Category</span></span>
- <span data-ttu-id="f0fd8-154">偵測來源</span><span class="sxs-lookup"><span data-stu-id="f0fd8-154">Detection source</span></span>
- <span data-ttu-id="f0fd8-155">原則</span><span class="sxs-lookup"><span data-stu-id="f0fd8-155">Policy</span></span>
- <span data-ttu-id="f0fd8-156">受影響資產</span><span class="sxs-lookup"><span data-stu-id="f0fd8-156">Impacted assets</span></span>
- <span data-ttu-id="f0fd8-157">第一個活動</span><span class="sxs-lookup"><span data-stu-id="f0fd8-157">First activity</span></span>
- <span data-ttu-id="f0fd8-158">最後一個活動</span><span class="sxs-lookup"><span data-stu-id="f0fd8-158">Last activity</span></span>


<span data-ttu-id="f0fd8-159">若要開始調查事件，請參閱[Microsoft 365 Defender 中的調查事件](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="f0fd8-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="f0fd8-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f0fd8-160">See also</span></span>

- [<span data-ttu-id="f0fd8-161">事件概觀</span><span class="sxs-lookup"><span data-stu-id="f0fd8-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f0fd8-162">調查事件</span><span class="sxs-lookup"><span data-stu-id="f0fd8-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f0fd8-163">管理事件</span><span class="sxs-lookup"><span data-stu-id="f0fd8-163">Manage incidents</span></span>](manage-incidents.md)
