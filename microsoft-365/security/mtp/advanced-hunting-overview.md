---
title: Microsoft 威脅防護中的進階搜捕概觀
description: 了解 Microsoft 365 中的進階搜捕查詢，以及如何使用該功能主動找出您的網路中的威脅和弱點
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，自訂偵測，schema，kusto，microsoft 365，Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: dc91b97f48d6a5ca76c405e4c1006dceb9dc0b34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929025"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="afd3b-104">使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="afd3b-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="afd3b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="afd3b-105">**Applies to:**</span></span>
- <span data-ttu-id="afd3b-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="afd3b-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="afd3b-107">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="afd3b-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="afd3b-108">您可以主動檢查您網路中的事件，以找出相關的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="afd3b-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="afd3b-109">可靈活存取資料有助於不受限制地同時搜捕已知和潛在的威脅。</span><span class="sxs-lookup"><span data-stu-id="afd3b-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="afd3b-110">您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="afd3b-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="afd3b-111">這些規則會自動執行，以檢查和回應各種事件和系統狀態，包括可疑的入侵活動和設定不當的電腦。</span><span class="sxs-lookup"><span data-stu-id="afd3b-111">These rules run automatically to check for and respond to various events and system states, including suspected breach activity and misconfigured machines.</span></span>

<span data-ttu-id="afd3b-112">在 Microsoft 365 的安全性中心，「高級搜尋」支援查詢可查看各種工作區中的資料，包括來自 Microsoft Defender ATP 的裝置、電子郵件、應用程式和身分識別的資料、Office 365 ATP、Microsoft Cloud App Security 和 AzureAtp。</span><span class="sxs-lookup"><span data-stu-id="afd3b-112">In the Microsoft 365 security center, advanced hunting supports queries that look into data from various workspaces, including data about devices, emails, apps, and identities from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="afd3b-113">若要使用進階搜捕，請[開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="afd3b-113">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="afd3b-114">開始使用進階搜捕</span><span class="sxs-lookup"><span data-stu-id="afd3b-114">Get started with advanced hunting</span></span>

<span data-ttu-id="afd3b-115">建議您透過數個步驟來利用進階搜捕快速啟動並執行。</span><span class="sxs-lookup"><span data-stu-id="afd3b-115">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="afd3b-116">學習目標</span><span class="sxs-lookup"><span data-stu-id="afd3b-116">Learning goal</span></span> | <span data-ttu-id="afd3b-117">描述</span><span class="sxs-lookup"><span data-stu-id="afd3b-117">Description</span></span> | <span data-ttu-id="afd3b-118">資源</span><span class="sxs-lookup"><span data-stu-id="afd3b-118">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="afd3b-119">**了解語言**</span><span class="sxs-lookup"><span data-stu-id="afd3b-119">**Get a feel for the language**</span></span> | <span data-ttu-id="afd3b-120">進階搜捕是基於 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)，支援相同的語法和運算子。</span><span class="sxs-lookup"><span data-stu-id="afd3b-120">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="afd3b-121">執行您的第一個查詢來開始學習查詢語言。</span><span class="sxs-lookup"><span data-stu-id="afd3b-121">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="afd3b-122">查詢語言概觀</span><span class="sxs-lookup"><span data-stu-id="afd3b-122">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="afd3b-123">**瞭解如何使用查詢結果**</span><span class="sxs-lookup"><span data-stu-id="afd3b-123">**Learn how to use the query results**</span></span> | <span data-ttu-id="afd3b-124">深入瞭解圖表和您可以查看或匯出結果的各種方式。</span><span class="sxs-lookup"><span data-stu-id="afd3b-124">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="afd3b-125">探索如何快速調整查詢，並深入瞭解如何取得更豐富的資訊。</span><span class="sxs-lookup"><span data-stu-id="afd3b-125">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="afd3b-126">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="afd3b-126">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="afd3b-127">**了解結構描述**</span><span class="sxs-lookup"><span data-stu-id="afd3b-127">**Understand the schema**</span></span> | <span data-ttu-id="afd3b-128">深入了解結構描述中的資料表和資料行。</span><span class="sxs-lookup"><span data-stu-id="afd3b-128">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="afd3b-129">這可協助您決定要在何處尋找資料，以及如何建構查詢。</span><span class="sxs-lookup"><span data-stu-id="afd3b-129">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="afd3b-130">結構描述參考</span><span class="sxs-lookup"><span data-stu-id="afd3b-130">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="afd3b-131">**運用預先定義的查詢**</span><span class="sxs-lookup"><span data-stu-id="afd3b-131">**Leverage predefined queries**</span></span> | <span data-ttu-id="afd3b-132">探索涵蓋不同威脅搜捕案例的預先定義查詢集合。</span><span class="sxs-lookup"><span data-stu-id="afd3b-132">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="afd3b-133">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="afd3b-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md) |
| <span data-ttu-id="afd3b-134">**最佳化查詢**</span><span class="sxs-lookup"><span data-stu-id="afd3b-134">**Optimize queries**</span></span> | <span data-ttu-id="afd3b-135">了解如何建立可結合來自電子郵件和裝置資料的高效查詢。</span><span class="sxs-lookup"><span data-stu-id="afd3b-135">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="afd3b-136">- [查詢最佳作法](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="afd3b-136">- [Query best practices](advanced-hunting-shared-queries.md)</span></span> <br><span data-ttu-id="afd3b-137">- [跨裝置和電子郵件進行搜尋](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="afd3b-137">- [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span> |
| <span data-ttu-id="afd3b-138">**建立自訂偵測規則**</span><span class="sxs-lookup"><span data-stu-id="afd3b-138">**Create custom detection rules**</span></span> | <span data-ttu-id="afd3b-139">瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動套用回應動作。</span><span class="sxs-lookup"><span data-stu-id="afd3b-139">Understand how you can use advanced hunting queries to trigger alerts and apply response actions automatically.</span></span> | <span data-ttu-id="afd3b-140">- [自訂偵測簡介](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="afd3b-140">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="afd3b-141">- [自訂偵測規則](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="afd3b-141">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="afd3b-142">編寫查詢時取得協助</span><span class="sxs-lookup"><span data-stu-id="afd3b-142">Get help as you write queries</span></span>
<span data-ttu-id="afd3b-143">運用下列功能更快速地編寫查詢：</span><span class="sxs-lookup"><span data-stu-id="afd3b-143">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="afd3b-144">**Autosuggest** --當您撰寫查詢時，高級搜尋會提供 IntelliSense 的建議。</span><span class="sxs-lookup"><span data-stu-id="afd3b-144">**Autosuggest** — as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="afd3b-145">**結構描述參考** - 在您的工作區域旁提供、包含資料表清單和其資料欄的結構描述參考。</span><span class="sxs-lookup"><span data-stu-id="afd3b-145">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="afd3b-146">如需詳細資訊，請將游標暫留在某項目上。</span><span class="sxs-lookup"><span data-stu-id="afd3b-146">For more information, hover over an item.</span></span> <span data-ttu-id="afd3b-147">按兩下某個項目，將它插入查詢編輯器。</span><span class="sxs-lookup"><span data-stu-id="afd3b-147">Double-click an item to insert it to the query editor.</span></span>


## <a name="related-topics"></a><span data-ttu-id="afd3b-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="afd3b-148">Related topics</span></span>
- [<span data-ttu-id="afd3b-149">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="afd3b-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="afd3b-150">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="afd3b-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="afd3b-151">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="afd3b-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="afd3b-152">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="afd3b-152">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="afd3b-153">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="afd3b-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="afd3b-154">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="afd3b-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="afd3b-155">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="afd3b-155">Custom detections overview</span></span>](custom-detections-overview.md)