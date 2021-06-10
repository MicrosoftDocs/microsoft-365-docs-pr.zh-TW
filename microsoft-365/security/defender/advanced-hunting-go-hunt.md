---
title: 取得實體的相關資訊以進行搜尋
description: 瞭解如何使用「移到搜尋」工具，使用高級搜尋快速查詢實體或事件的相關資訊。
keywords: 高級搜尋、事件、資料透視、實體、搜尋、相關事件、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、Microsoft 365 Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952653"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="0c692-104">使用 go 搜尋快速尋找實體或事件資訊</span><span class="sxs-lookup"><span data-stu-id="0c692-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0c692-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0c692-105">**Applies to:**</span></span>
- <span data-ttu-id="0c692-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c692-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="0c692-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0c692-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0c692-108">使用 [ *尋找* ] [搜尋] 動作，您可以使用強大查詢的 [高級搜尋](advanced-hunting-overview.md) 功能，快速調查事件及各種實體類型。</span><span class="sxs-lookup"><span data-stu-id="0c692-108">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="0c692-109">此巨集指令會自動執行高級搜尋查詢，以尋找所選取事件或實體的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0c692-109">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="0c692-110">每當顯示事件或實體詳細資料時，就會在安全性中心的各個區段中使用「 *繼續搜尋* 」動作。</span><span class="sxs-lookup"><span data-stu-id="0c692-110">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="0c692-111">例如，您可以使用下列各節的「 *繼續搜尋* 」：</span><span class="sxs-lookup"><span data-stu-id="0c692-111">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="0c692-112">在 [ [事件] 頁面](investigate-incidents.md#summary)中，您可以查看使用者、裝置及其他許多與事件相關聯之實體的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0c692-112">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="0c692-113">當您選取實體時，您會收到額外的資訊，以及您在該實體上可以採取的各種動作。</span><span class="sxs-lookup"><span data-stu-id="0c692-113">As you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="0c692-114">在下列範例中，會選取一個信箱，顯示信箱的詳細資料，也就是尋找該信箱的詳細資訊的選項。</span><span class="sxs-lookup"><span data-stu-id="0c692-114">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![使用 [搜尋] 選項顯示信箱詳細資料的影像](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="0c692-116">在 [事件] 頁面中，您也可以在 [證據] 索引標籤下存取實體清單。選取其中一個實體時，會提供一個選項，以快速尋找該實體的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0c692-116">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![在 [證據] 索引標籤中，以 [搜尋] 選項顯示選取檔案的影像](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="0c692-118">當您查看裝置的時程表時，您可以選取時程表中的事件，以查看有關該事件的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="0c692-118">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="0c692-119">選取事件後，您可以在 [高級搜尋] 中取得搜尋其他相關事件的選項。</span><span class="sxs-lookup"><span data-stu-id="0c692-119">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![顯示 [搜尋] 選項的事件詳細資料的影像](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="0c692-121">選取 [ **搜尋** ] 或 [ **搜尋相關的事件** ] 會傳送不同的查詢，視您是否已選取實體或事件而定。</span><span class="sxs-lookup"><span data-stu-id="0c692-121">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="0c692-122">查詢實體資訊</span><span class="sxs-lookup"><span data-stu-id="0c692-122">Query for entity information</span></span>
<span data-ttu-id="0c692-123">當您使用「 *搜尋* 以查詢使用者、裝置或任何其他類型的實體」的相關資訊時，查詢會檢查涉及該實體之任何事件的所有相關架構資料表。</span><span class="sxs-lookup"><span data-stu-id="0c692-123">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="0c692-124">若要讓結果保持可管理，查詢的範圍會設定為與過去30天（包含實體並與該事件相關聯）的最早活動的時段。</span><span class="sxs-lookup"><span data-stu-id="0c692-124">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="0c692-125">以下是裝置的 go 搜尋查詢範例：</span><span class="sxs-lookup"><span data-stu-id="0c692-125">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="0c692-126">支援的實體類型</span><span class="sxs-lookup"><span data-stu-id="0c692-126">Supported entity types</span></span>
<span data-ttu-id="0c692-127">您可以在選取下列任何實體類型之後，使用 [ *搜尋* ]：</span><span class="sxs-lookup"><span data-stu-id="0c692-127">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="0c692-128">檔案</span><span class="sxs-lookup"><span data-stu-id="0c692-128">Files</span></span>
- <span data-ttu-id="0c692-129">電子郵件</span><span class="sxs-lookup"><span data-stu-id="0c692-129">Emails</span></span>
- <span data-ttu-id="0c692-130">電子郵件聚簇</span><span class="sxs-lookup"><span data-stu-id="0c692-130">Email clusters</span></span>
- <span data-ttu-id="0c692-131">信箱</span><span class="sxs-lookup"><span data-stu-id="0c692-131">Mailboxes</span></span>
- <span data-ttu-id="0c692-132">使用者</span><span class="sxs-lookup"><span data-stu-id="0c692-132">Users</span></span>
- <span data-ttu-id="0c692-133">裝置</span><span class="sxs-lookup"><span data-stu-id="0c692-133">Devices</span></span>
- <span data-ttu-id="0c692-134">IP 位址</span><span class="sxs-lookup"><span data-stu-id="0c692-134">IP addresses</span></span>
- <span data-ttu-id="0c692-135">URL</span><span class="sxs-lookup"><span data-stu-id="0c692-135">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="0c692-136">事件資訊的查詢</span><span class="sxs-lookup"><span data-stu-id="0c692-136">Query for event information</span></span>
<span data-ttu-id="0c692-137">當您使用「 *搜尋* 以查詢」時程表事件的相關資訊時，查詢會檢查所選事件時間四周其他事件的所有相關架構資料表。</span><span class="sxs-lookup"><span data-stu-id="0c692-137">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="0c692-138">例如，下列查詢會列出在相同裝置上的相同時段內發生的各種架構表格事件：</span><span class="sxs-lookup"><span data-stu-id="0c692-138">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="0c692-139">調整查詢</span><span class="sxs-lookup"><span data-stu-id="0c692-139">Adjust the query</span></span>
<span data-ttu-id="0c692-140">您可以使用一些 [查詢語言](advanced-hunting-query-language.md)的知識，將查詢調整為您的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="0c692-140">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="0c692-141">例如，您可以調整此線，它會決定時間範圍的大小：</span><span class="sxs-lookup"><span data-stu-id="0c692-141">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="0c692-142">除了修改查詢以取得更相關的結果之外，您還可以：</span><span class="sxs-lookup"><span data-stu-id="0c692-142">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="0c692-143">以圖表形式查看結果</span><span class="sxs-lookup"><span data-stu-id="0c692-143">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="0c692-144">建立自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="0c692-144">Create a custom detection rule</span></span>](custom-detection-rules.md)

>[!NOTE]
><span data-ttu-id="0c692-145">本文中的部分表格可能無法在 Microsoft Defender for Endpoint 中使用。</span><span class="sxs-lookup"><span data-stu-id="0c692-145">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0c692-146">使用更多資料來源[開啟 Microsoft 365 Defender](m365d-enable.md)以搜尋威脅。</span><span class="sxs-lookup"><span data-stu-id="0c692-146">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="0c692-147">您可以遵循[從 microsoft defender for endpoint 遷移高級搜尋查詢](advanced-hunting-migrate-from-mde.md)中的步驟，將您的高級搜尋工作流程從 microsoft defender for endpoint 移至 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="0c692-147">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c692-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="0c692-148">Related topics</span></span>
- [<span data-ttu-id="0c692-149">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="0c692-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0c692-150">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="0c692-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0c692-151">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="0c692-151">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="0c692-152">自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="0c692-152">Custom detection rules</span></span>](custom-detection-rules.md)
