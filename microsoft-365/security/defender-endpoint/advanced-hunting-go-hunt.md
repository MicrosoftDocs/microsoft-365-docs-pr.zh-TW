---
title: 取得實體的相關資訊以進行搜尋
description: 瞭解如何使用「搜尋工具」，使用高級搜尋快速查詢實體或事件的相關資訊。
keywords: 高級搜尋、事件、資料透視、實體、搜尋、相關事件、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-maave
author: martyav
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fe3c204fe49f008cf5d9dd18b5066fa91dc6196
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060239"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="98d7c-104">使用 go 搜尋快速尋找實體或事件資訊</span><span class="sxs-lookup"><span data-stu-id="98d7c-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98d7c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="98d7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="98d7c-106">適用於端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="98d7c-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="98d7c-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="98d7c-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98d7c-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="98d7c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


<span data-ttu-id="98d7c-109">使用 [ *尋找* ] [搜尋] 動作，您可以使用強大查詢的 [高級搜尋](advanced-hunting-overview.md) 功能，快速調查事件及各種實體類型。</span><span class="sxs-lookup"><span data-stu-id="98d7c-109">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="98d7c-110">此巨集指令會自動執行高級搜尋查詢，以尋找所選取事件或實體的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="98d7c-110">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="98d7c-111">每當顯示事件或實體詳細資料時，就會在安全性中心的各個區段中使用「 *繼續搜尋* 」動作。</span><span class="sxs-lookup"><span data-stu-id="98d7c-111">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="98d7c-112">例如，您可以使用下列各節的「 *繼續搜尋* 」：</span><span class="sxs-lookup"><span data-stu-id="98d7c-112">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="98d7c-113">在 [ [事件] 頁面](investigate-incidents.md)中，您可以查看使用者、裝置及其他許多與事件相關聯之實體的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="98d7c-113">In the [incident page](investigate-incidents.md), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="98d7c-114">當您選取實體時，您會收到額外的資訊，以及您在該實體上可以採取的各種動作。</span><span class="sxs-lookup"><span data-stu-id="98d7c-114">When you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="98d7c-115">在下列範例中，會選取一個裝置，顯示裝置的詳細資訊，也就是尋找裝置相關詳細資訊的選項。</span><span class="sxs-lookup"><span data-stu-id="98d7c-115">In the example below, a device is selected, showing details about the device as well the option to hunt for more information about the device.</span></span>

    ![使用 [尋找搜尋] 選項顯示裝置詳細資料的影像](./images/go-hunt-device.png)

- <span data-ttu-id="98d7c-117">在 [事件] 頁面中，您也可以在 [證據] 索引標籤下存取實體清單。選取其中一個實體時，會提供一個選項，以快速尋找該實體的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="98d7c-117">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![在 [證據] 索引標籤中，顯示選取之 url 與 [搜尋] 選項的影像](./images/go-hunt-evidence-url.png)

- <span data-ttu-id="98d7c-119">當您查看裝置的時程表時，您可以選取時程表中的事件，以查看有關該事件的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="98d7c-119">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="98d7c-120">選取事件後，您可以在 [高級搜尋] 中取得搜尋其他相關事件的選項。</span><span class="sxs-lookup"><span data-stu-id="98d7c-120">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![顯示 [搜尋] 選項的事件詳細資料的影像](./images/go-hunt-event.png)

<span data-ttu-id="98d7c-122">選取 [ **搜尋** ] 或 [ **搜尋相關的事件** ] 會傳送不同的查詢，視您是否已選取實體或事件而定。</span><span class="sxs-lookup"><span data-stu-id="98d7c-122">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="98d7c-123">查詢實體資訊</span><span class="sxs-lookup"><span data-stu-id="98d7c-123">Query for entity information</span></span>

<span data-ttu-id="98d7c-124">當您使用「 *搜尋* 以查詢使用者、裝置或任何其他類型的實體」的相關資訊時，查詢會檢查涉及該實體之任何事件的所有相關架構資料表。</span><span class="sxs-lookup"><span data-stu-id="98d7c-124">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="98d7c-125">若要讓結果保持可管理，查詢的範圍會設定為與過去30天（包含實體並與該事件相關聯）的最早活動的時段。</span><span class="sxs-lookup"><span data-stu-id="98d7c-125">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="98d7c-126">以下是裝置的 go 搜尋查詢範例：</span><span class="sxs-lookup"><span data-stu-id="98d7c-126">Here is an example of the go hunt query for a device:</span></span>

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

### <a name="supported-entity-types"></a><span data-ttu-id="98d7c-127">支援的實體類型</span><span class="sxs-lookup"><span data-stu-id="98d7c-127">Supported entity types</span></span>

<span data-ttu-id="98d7c-128">您可以在選取下列任何實體類型之後，使用 [ *搜尋* ]：</span><span class="sxs-lookup"><span data-stu-id="98d7c-128">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="98d7c-129">檔案</span><span class="sxs-lookup"><span data-stu-id="98d7c-129">Files</span></span>
- <span data-ttu-id="98d7c-130">使用者</span><span class="sxs-lookup"><span data-stu-id="98d7c-130">Users</span></span>
- <span data-ttu-id="98d7c-131">裝置</span><span class="sxs-lookup"><span data-stu-id="98d7c-131">Devices</span></span>
- <span data-ttu-id="98d7c-132">IP 位址</span><span class="sxs-lookup"><span data-stu-id="98d7c-132">IP addresses</span></span>
- <span data-ttu-id="98d7c-133">URL</span><span class="sxs-lookup"><span data-stu-id="98d7c-133">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="98d7c-134">事件資訊的查詢</span><span class="sxs-lookup"><span data-stu-id="98d7c-134">Query for event information</span></span>

<span data-ttu-id="98d7c-135">當您使用「 *搜尋* 以查詢」時程表事件的相關資訊時，查詢會檢查所選事件時間四周其他事件的所有相關架構資料表。</span><span class="sxs-lookup"><span data-stu-id="98d7c-135">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="98d7c-136">例如，下列查詢會列出在相同裝置上的相同時段內發生的各種架構表格事件：</span><span class="sxs-lookup"><span data-stu-id="98d7c-136">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected RegistryValueSet event
let selectedEventTimestamp = datetime(2020-10-06T21:40:25.3466868Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "a305b52049c4658ec63ae8b55becfe5954c654a4"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="98d7c-137">調整查詢</span><span class="sxs-lookup"><span data-stu-id="98d7c-137">Adjust the query</span></span>

<span data-ttu-id="98d7c-138">您可以使用一些 [查詢語言](advanced-hunting-query-language.md)的知識，將查詢調整為您的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="98d7c-138">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="98d7c-139">例如，您可以調整此線，它會決定時間範圍的大小：</span><span class="sxs-lookup"><span data-stu-id="98d7c-139">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="98d7c-140">除了修改查詢以取得更相關的結果之外，您還可以：</span><span class="sxs-lookup"><span data-stu-id="98d7c-140">In addition to modifying the query to get more relevant results, you can also:</span></span>

- [<span data-ttu-id="98d7c-141">以圖表形式查看結果</span><span class="sxs-lookup"><span data-stu-id="98d7c-141">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="98d7c-142">建立自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="98d7c-142">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="98d7c-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="98d7c-143">Related topics</span></span>

- [<span data-ttu-id="98d7c-144">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="98d7c-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98d7c-145">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="98d7c-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="98d7c-146">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="98d7c-146">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="98d7c-147">自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="98d7c-147">Custom detection rules</span></span>](custom-detection-rules.md)
