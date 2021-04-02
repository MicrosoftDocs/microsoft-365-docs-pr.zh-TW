---
title: Microsoft Defender ATP 中的高級搜尋概述
description: 在 Microsoft Defender ATP 中使用威脅搜尋功能來建立查詢，以找出網路的威脅和弱點
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp、搜尋、查詢、遙測、自訂偵測、架構、kusto、時區、UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4883a4f04f06774d02aa0d942edc841867eb36b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499514"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a><span data-ttu-id="65945-104">使用高級搜尋主動搜尋威脅</span><span class="sxs-lookup"><span data-stu-id="65945-104">Proactively hunt for threats with advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65945-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="65945-105">**Applies to:**</span></span>
- [<span data-ttu-id="65945-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="65945-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="65945-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="65945-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="65945-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="65945-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="65945-109">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="65945-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="65945-110">您可以主動檢查您網路中的事件，以找出威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="65945-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="65945-111">對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。</span><span class="sxs-lookup"><span data-stu-id="65945-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="65945-112">觀賞這段影片，快速流覽高級搜尋，以及可讓您快速入門的簡短教學課程。</span><span class="sxs-lookup"><span data-stu-id="65945-112">Watch this video for a quick overview of advanced hunting and a short tutorial that will get you started fast.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

<span data-ttu-id="65945-113">您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="65945-113">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="65945-114">這些規則會自動執行，以檢查是否有可疑的破壞活動、錯誤設定的機器及其他發現的回應。</span><span class="sxs-lookup"><span data-stu-id="65945-114">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

>[!TIP]
><span data-ttu-id="65945-115">[在 Microsoft 威脅防護中使用高級搜尋](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview)，以搜尋使用來自 Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 及 microsoft Defender 身分識別的資料的威脅。</span><span class="sxs-lookup"><span data-stu-id="65945-115">Use [advanced hunting in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview) to hunt for threats using data from Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> [<span data-ttu-id="65945-116">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65945-116">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="65945-117">開始使用進階搜捕</span><span class="sxs-lookup"><span data-stu-id="65945-117">Get started with advanced hunting</span></span>

<span data-ttu-id="65945-118">請逐步執行下列步驟，以提升您的高級搜尋知識。</span><span class="sxs-lookup"><span data-stu-id="65945-118">Go through the following steps to ramp up your advanced hunting knowledge.</span></span>

<span data-ttu-id="65945-119">建議您透過數個步驟來利用進階搜捕快速啟動並執行。</span><span class="sxs-lookup"><span data-stu-id="65945-119">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="65945-120">學習目標</span><span class="sxs-lookup"><span data-stu-id="65945-120">Learning goal</span></span> | <span data-ttu-id="65945-121">描述</span><span class="sxs-lookup"><span data-stu-id="65945-121">Description</span></span> | <span data-ttu-id="65945-122">資源</span><span class="sxs-lookup"><span data-stu-id="65945-122">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="65945-123">**瞭解語言**</span><span class="sxs-lookup"><span data-stu-id="65945-123">**Learn the language**</span></span> | <span data-ttu-id="65945-124">「高級搜尋」是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。</span><span class="sxs-lookup"><span data-stu-id="65945-124">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="65945-125">執行您的第一個查詢來開始學習查詢語言。</span><span class="sxs-lookup"><span data-stu-id="65945-125">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="65945-126">查詢語言概觀</span><span class="sxs-lookup"><span data-stu-id="65945-126">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="65945-127">**瞭解如何使用查詢結果**</span><span class="sxs-lookup"><span data-stu-id="65945-127">**Learn how to use the query results**</span></span> | <span data-ttu-id="65945-128">深入瞭解圖表和您可以查看或匯出結果的各種方式。</span><span class="sxs-lookup"><span data-stu-id="65945-128">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="65945-129">探索如何快速調整查詢，並深入瞭解如何取得更豐富的資訊。</span><span class="sxs-lookup"><span data-stu-id="65945-129">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="65945-130">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="65945-130">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="65945-131">**了解結構描述**</span><span class="sxs-lookup"><span data-stu-id="65945-131">**Understand the schema**</span></span> | <span data-ttu-id="65945-132">深入了解結構描述中的資料表和資料行。</span><span class="sxs-lookup"><span data-stu-id="65945-132">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="65945-133">瞭解在建立查詢時要尋找資料的位置。</span><span class="sxs-lookup"><span data-stu-id="65945-133">Learn where to look for data when constructing your queries.</span></span> | [<span data-ttu-id="65945-134">結構描述參考</span><span class="sxs-lookup"><span data-stu-id="65945-134">Schema reference</span></span>](advanced-hunting-schema-reference.md) |
| <span data-ttu-id="65945-135">**使用預先定義的查詢**</span><span class="sxs-lookup"><span data-stu-id="65945-135">**Use predefined queries**</span></span> | <span data-ttu-id="65945-136">探索涵蓋不同威脅搜捕案例的預先定義查詢集合。</span><span class="sxs-lookup"><span data-stu-id="65945-136">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="65945-137">共用查詢</span><span class="sxs-lookup"><span data-stu-id="65945-137">Shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="65945-138">**優化查詢並處理錯誤**</span><span class="sxs-lookup"><span data-stu-id="65945-138">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="65945-139">瞭解如何建立高效且無錯誤的查詢。</span><span class="sxs-lookup"><span data-stu-id="65945-139">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="65945-140">- [查詢最佳作法](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="65945-140">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="65945-141">- [處理錯誤](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="65945-141">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="65945-142">**取得最完整的覆蓋範圍**</span><span class="sxs-lookup"><span data-stu-id="65945-142">**Get the most complete coverage**</span></span> | <span data-ttu-id="65945-143">使用 [審核設定] 為您的組織提供更佳的資料覆蓋率。</span><span class="sxs-lookup"><span data-stu-id="65945-143">Use audit settings to provide better data coverage for your organization.</span></span> | <span data-ttu-id="65945-144">- [延伸高級搜尋範圍](advanced-hunting-extend-data.md)</span><span class="sxs-lookup"><span data-stu-id="65945-144">- [Extend advanced hunting coverage](advanced-hunting-extend-data.md)</span></span> |
| <span data-ttu-id="65945-145">**執行快速調查**</span><span class="sxs-lookup"><span data-stu-id="65945-145">**Run a quick investigation**</span></span> | <span data-ttu-id="65945-146">快速執行高級搜尋查詢，以調查可疑活動。</span><span class="sxs-lookup"><span data-stu-id="65945-146">Quickly run an advanced hunting query to investigate suspicious activity.</span></span> | <span data-ttu-id="65945-147">- [使用 *go 搜尋* 快速尋找實體或事件資訊](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="65945-147">- [Quickly hunt for entity or event information with *go hunt*](advanced-hunting-go-hunt.md)</span></span> |
| <span data-ttu-id="65945-148">**包含威脅和位址受到威脅**</span><span class="sxs-lookup"><span data-stu-id="65945-148">**Contain threats and address compromises**</span></span> | <span data-ttu-id="65945-149">隔離檔、限制應用程式執行及其他動作以回應攻擊</span><span class="sxs-lookup"><span data-stu-id="65945-149">Respond to attacks by quarantining files, restricting app execution, and other actions</span></span> | <span data-ttu-id="65945-150">- [對高級搜尋查詢結果採取動作](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="65945-150">- [Take action on advanced hunting query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="65945-151">**建立自訂偵測規則**</span><span class="sxs-lookup"><span data-stu-id="65945-151">**Create custom detection rules**</span></span> | <span data-ttu-id="65945-152">瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="65945-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="65945-153">- [自訂偵測簡介](overview-custom-detections.md)</span><span class="sxs-lookup"><span data-stu-id="65945-153">- [Custom detections overview](overview-custom-detections.md)</span></span><br><span data-ttu-id="65945-154">- [自訂偵測規則](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="65945-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="65945-155">資料新鮮度和更新頻率</span><span class="sxs-lookup"><span data-stu-id="65945-155">Data freshness and update frequency</span></span>

<span data-ttu-id="65945-156">「高級搜尋」資料可以分類成兩種不同的類型，每個不同的合併。</span><span class="sxs-lookup"><span data-stu-id="65945-156">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="65945-157">**事件或活動資料**--填入有關警示、安全性事件、系統事件及例行評估的表格。</span><span class="sxs-lookup"><span data-stu-id="65945-157">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="65945-158">「高級搜尋」幾乎會在收集成功的感應器成功傳輸至端點後立即接收這類資料。</span><span class="sxs-lookup"><span data-stu-id="65945-158">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to Defender for Endpoint.</span></span>
- <span data-ttu-id="65945-159">**實體資料**—使用使用者和裝置的整合式資訊來填入資料表。</span><span class="sxs-lookup"><span data-stu-id="65945-159">**Entity data**—populates tables with consolidated information about users and devices.</span></span> <span data-ttu-id="65945-160">此資料來自相對靜態資料來源和動態來源，例如 Active Directory 專案和事件記錄。</span><span class="sxs-lookup"><span data-stu-id="65945-160">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="65945-161">若要提供全新的資料，每隔15分鐘更新一次所有新資訊的資料表，新增可能不會填滿的資料列。</span><span class="sxs-lookup"><span data-stu-id="65945-161">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="65945-162">每24小時都會合並資料，以插入記錄，其中包含每個實體的最新、最全面的資料集。</span><span class="sxs-lookup"><span data-stu-id="65945-162">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="65945-163">時區</span><span class="sxs-lookup"><span data-stu-id="65945-163">Time zone</span></span>

<span data-ttu-id="65945-164">高級搜尋中的時間資訊目前在 UTC 時區內。</span><span class="sxs-lookup"><span data-stu-id="65945-164">Time information in advanced hunting is currently in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="65945-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="65945-165">Related topics</span></span>

- [<span data-ttu-id="65945-166">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="65945-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65945-167">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="65945-167">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="65945-168">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="65945-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="65945-169">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="65945-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="65945-170">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="65945-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="65945-171">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="65945-171">Custom detections overview</span></span>](overview-custom-detections.md)