---
title: 使用搜尋取得實體的相關資訊
description: 瞭解如何使用搜尋工具來快速查詢實體或事件的相關相關資訊，以使用進一次搜尋。
keywords: 進層搜尋、事件、樞紐、實體、搜尋、相關事件、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365、Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929500"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="a8503-104">使用搜尋快速搜尋實體或活動資訊</span><span class="sxs-lookup"><span data-stu-id="a8503-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a8503-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="a8503-105">**Applies to:**</span></span>
- <span data-ttu-id="a8503-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8503-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a8503-107">有了 *搜尋動作* ，您可以使用功能強大的查詢型進一步搜尋功能，快速調查事件 [及](advanced-hunting-overview.md) 各種實體類型。</span><span class="sxs-lookup"><span data-stu-id="a8503-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="a8503-108">此動作會自動執行進一步搜尋查詢，以尋找所選事件或實體的相關相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a8503-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="a8503-109">每當 *顯示事件* 或實體詳細資料時，可在安全性中心的各個區段使用搜尋動作。</span><span class="sxs-lookup"><span data-stu-id="a8503-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="a8503-110">例如，您可以使用下列 *各* 節中的搜尋功能：</span><span class="sxs-lookup"><span data-stu-id="a8503-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="a8503-111">您可以在 [事件頁面中](investigate-incidents.md#incident-overview)，查看與事件相關的使用者、裝置及許多其他實體詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a8503-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="a8503-112">當您選取實體時，您取得其他資訊，以及您可針對該實體執行的各種動作。</span><span class="sxs-lookup"><span data-stu-id="a8503-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="a8503-113">在下面的範例中，已選取一個信箱，其中顯示該信箱的詳細資訊，以及尋找信箱詳細資訊的選項。</span><span class="sxs-lookup"><span data-stu-id="a8503-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![顯示信箱詳細資料與搜尋選項的影像](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="a8503-115">在事件頁面中，您也可以存取證據分頁下的實體清單。選取其中一個實體，即可提供快速搜尋該實體相關資訊的選項。</span><span class="sxs-lookup"><span data-stu-id="a8503-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![顯示已選取檔案的影像，以及證據中之搜尋選項](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="a8503-117">檢視裝置的時程表時，您可以選取時程表中的事件，以檢視該事件的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a8503-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="a8503-118">選取事件後，您可以選擇在進一次搜尋中尋找其他相關的事件。</span><span class="sxs-lookup"><span data-stu-id="a8503-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![顯示活動詳細資料與搜尋選項的影像](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="a8503-120">選取 **搜尋** 或 **搜尋相關** 事件會依據您是否選取實體或事件，而傳遞不同的查詢。</span><span class="sxs-lookup"><span data-stu-id="a8503-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="a8503-121">實體資訊的查詢</span><span class="sxs-lookup"><span data-stu-id="a8503-121">Query for entity information</span></span>
<span data-ttu-id="a8503-122">使用 *搜尋來* 查詢使用者、裝置或任何其他實體類型相關資訊時，查詢會檢查所有涉及該實體之事件的相關架構資料表。</span><span class="sxs-lookup"><span data-stu-id="a8503-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="a8503-123">若要讓結果易於管理，查詢的範圍會與過去 30 天內與實體相關且與事件相關聯的最早活動期間左右。</span><span class="sxs-lookup"><span data-stu-id="a8503-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="a8503-124">以下是裝置搜尋查詢的範例：</span><span class="sxs-lookup"><span data-stu-id="a8503-124">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="a8503-125">支援的實體類型</span><span class="sxs-lookup"><span data-stu-id="a8503-125">Supported entity types</span></span>
<span data-ttu-id="a8503-126">選取以下 *任何實體類型* 後，就可以使用搜尋：</span><span class="sxs-lookup"><span data-stu-id="a8503-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="a8503-127">檔案</span><span class="sxs-lookup"><span data-stu-id="a8503-127">Files</span></span>
- <span data-ttu-id="a8503-128">電子郵件</span><span class="sxs-lookup"><span data-stu-id="a8503-128">Emails</span></span>
- <span data-ttu-id="a8503-129">電子郵件組</span><span class="sxs-lookup"><span data-stu-id="a8503-129">Email clusters</span></span>
- <span data-ttu-id="a8503-130">信箱</span><span class="sxs-lookup"><span data-stu-id="a8503-130">Mailboxes</span></span>
- <span data-ttu-id="a8503-131">使用者</span><span class="sxs-lookup"><span data-stu-id="a8503-131">Users</span></span>
- <span data-ttu-id="a8503-132">裝置</span><span class="sxs-lookup"><span data-stu-id="a8503-132">Devices</span></span>
- <span data-ttu-id="a8503-133">IP 位址</span><span class="sxs-lookup"><span data-stu-id="a8503-133">IP addresses</span></span>
- <span data-ttu-id="a8503-134">URL</span><span class="sxs-lookup"><span data-stu-id="a8503-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="a8503-135">事件資訊的查詢</span><span class="sxs-lookup"><span data-stu-id="a8503-135">Query for event information</span></span>
<span data-ttu-id="a8503-136">使用 *搜尋來* 查詢時程表事件相關資訊時，查詢會檢查所有與所選事件期間相關的架構資料表，以尋找其他事件。</span><span class="sxs-lookup"><span data-stu-id="a8503-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="a8503-137">例如，下列查詢會列出相同裝置上同一時期發生各種架構資料表中的事件：</span><span class="sxs-lookup"><span data-stu-id="a8503-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="a8503-138">調整查詢</span><span class="sxs-lookup"><span data-stu-id="a8503-138">Adjust the query</span></span>
<span data-ttu-id="a8503-139">具備查詢語言 [相關知識後](advanced-hunting-query-language.md)，就可以根據自己的喜好調整查詢。</span><span class="sxs-lookup"><span data-stu-id="a8503-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="a8503-140">例如，您可以調整此線，這決定時間視窗的大小：</span><span class="sxs-lookup"><span data-stu-id="a8503-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="a8503-141">除了修改查詢以取得更相關的結果，您也可以：</span><span class="sxs-lookup"><span data-stu-id="a8503-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="a8503-142">以圖表查看結果</span><span class="sxs-lookup"><span data-stu-id="a8503-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="a8503-143">建立自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="a8503-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="a8503-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="a8503-144">Related topics</span></span>
- [<span data-ttu-id="a8503-145">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="a8503-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a8503-146">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="a8503-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a8503-147">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="a8503-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="a8503-148">自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="a8503-148">Custom detection rules</span></span>](custom-detection-rules.md)
