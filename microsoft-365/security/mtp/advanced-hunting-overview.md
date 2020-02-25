---
title: Microsoft 威脅防護中的進階搜捕概觀
description: 了解 Microsoft 365 中的進階搜捕查詢，以及如何使用該功能主動找出您的網路中的威脅和弱點
keywords: 進階搜尋，威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 自訂偵測、 結構描述、 kusto、 microsoft 365，Microsoft 威脅防護
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
ms.openlocfilehash: 598ef669e95081ef098dfa9cfdb5473b21b28306
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234752"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="f4cde-104">使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="f4cde-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="f4cde-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f4cde-105">**Applies to:**</span></span>
- <span data-ttu-id="f4cde-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="f4cde-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="f4cde-107">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="f4cde-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="f4cde-108">您可以主動檢查您網路中的事件，以找出相關的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="f4cde-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="f4cde-109">可靈活存取資料有助於不受限制地同時搜捕已知和潛在的威脅。</span><span class="sxs-lookup"><span data-stu-id="f4cde-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="f4cde-110">在 Microsoft 365 資訊安全中心，進階的狩獵支援從這兩個 Microsoft Defender ATP，涵蓋上架的裝置和 Office 365 ATP 中的資料、 提供電子郵件中的資料，查看資料的查詢。</span><span class="sxs-lookup"><span data-stu-id="f4cde-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="f4cde-111">若要使用進階搜捕，請[開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="f4cde-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="f4cde-112">開始使用進階搜捕</span><span class="sxs-lookup"><span data-stu-id="f4cde-112">Get started with advanced hunting</span></span>

<span data-ttu-id="f4cde-113">建議您透過數個步驟來利用進階搜捕快速啟動並執行。</span><span class="sxs-lookup"><span data-stu-id="f4cde-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="f4cde-114">學習目標</span><span class="sxs-lookup"><span data-stu-id="f4cde-114">Learning goal</span></span> | <span data-ttu-id="f4cde-115">描述</span><span class="sxs-lookup"><span data-stu-id="f4cde-115">Description</span></span> | <span data-ttu-id="f4cde-116">資源</span><span class="sxs-lookup"><span data-stu-id="f4cde-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="f4cde-117">**了解語言**</span><span class="sxs-lookup"><span data-stu-id="f4cde-117">**Get a feel for the language**</span></span> | <span data-ttu-id="f4cde-118">進階搜捕是基於 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)，支援相同的語法和運算子。</span><span class="sxs-lookup"><span data-stu-id="f4cde-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="f4cde-119">執行您的第一個查詢來開始學習查詢語言。</span><span class="sxs-lookup"><span data-stu-id="f4cde-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="f4cde-120">查詢語言概觀</span><span class="sxs-lookup"><span data-stu-id="f4cde-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="f4cde-121">**了解結構描述**</span><span class="sxs-lookup"><span data-stu-id="f4cde-121">**Understand the schema**</span></span> | <span data-ttu-id="f4cde-122">深入了解結構描述中的資料表和資料行。</span><span class="sxs-lookup"><span data-stu-id="f4cde-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="f4cde-123">這可協助您決定要在何處尋找資料，以及如何建構查詢。</span><span class="sxs-lookup"><span data-stu-id="f4cde-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="f4cde-124">結構描述參考</span><span class="sxs-lookup"><span data-stu-id="f4cde-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="f4cde-125">**使用預先定義的查詢**</span><span class="sxs-lookup"><span data-stu-id="f4cde-125">**Use predefined queries**</span></span> | <span data-ttu-id="f4cde-126">探索涵蓋不同威脅搜捕案例的預先定義查詢集合。</span><span class="sxs-lookup"><span data-stu-id="f4cde-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="f4cde-127">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="f4cde-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="f4cde-128">**最佳化查詢**</span><span class="sxs-lookup"><span data-stu-id="f4cde-128">**Optimize queries**</span></span> | <span data-ttu-id="f4cde-129">了解如何建立可結合來自電子郵件和裝置資料的高效查詢。</span><span class="sxs-lookup"><span data-stu-id="f4cde-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="f4cde-130">[查詢最佳做法](advanced-hunting-shared-queries.md)、[跨裝置和電子郵件搜捕](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="f4cde-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="f4cde-131">編寫查詢時取得協助</span><span class="sxs-lookup"><span data-stu-id="f4cde-131">Get help as you write queries</span></span>
<span data-ttu-id="f4cde-132">運用下列功能更快速地編寫查詢：</span><span class="sxs-lookup"><span data-stu-id="f4cde-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="f4cde-133">**自動建議** - 在您編寫查詢時，進階搜捕會提供建議。</span><span class="sxs-lookup"><span data-stu-id="f4cde-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="f4cde-134">**結構描述參考** - 在您的工作區域旁提供、包含資料表清單和其資料欄的結構描述參考。</span><span class="sxs-lookup"><span data-stu-id="f4cde-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="f4cde-135">如需詳細資訊，請將游標暫留在某項目上。</span><span class="sxs-lookup"><span data-stu-id="f4cde-135">For more information, hover over an item.</span></span> <span data-ttu-id="f4cde-136">按兩下某個項目，將它插入查詢編輯器。</span><span class="sxs-lookup"><span data-stu-id="f4cde-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="f4cde-137">從查詢結果深入分析</span><span class="sxs-lookup"><span data-stu-id="f4cde-137">Drilldown from query results</span></span>
<span data-ttu-id="f4cde-138">若要在查詢結果中檢視實體 (例如電腦、檔案、使用者、IP 位址和 URL) 的詳細資訊，只要按一下實體識別碼即可。</span><span class="sxs-lookup"><span data-stu-id="f4cde-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="f4cde-139">這會為 Microsoft Defender 安全性中心選取的實體開啟詳細的設定檔頁面。</span><span class="sxs-lookup"><span data-stu-id="f4cde-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="f4cde-140">從結果調整您的查詢</span><span class="sxs-lookup"><span data-stu-id="f4cde-140">Tweak your queries from the results</span></span>
<span data-ttu-id="f4cde-141">以滑鼠右鍵按一下結果集中的值，以快速強化您的查詢。</span><span class="sxs-lookup"><span data-stu-id="f4cde-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="f4cde-142">您可以使用下列選項來執行這些動作：</span><span class="sxs-lookup"><span data-stu-id="f4cde-142">You can use the options to:</span></span>

- <span data-ttu-id="f4cde-143">明確尋找選取的值 (`==`)</span><span class="sxs-lookup"><span data-stu-id="f4cde-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="f4cde-144">從查詢排除選取的值 (`!=`)</span><span class="sxs-lookup"><span data-stu-id="f4cde-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="f4cde-145">取得更多可將值新增至查詢的進階運算子，例如 `contains`、`starts with` 和 `ends with`</span><span class="sxs-lookup"><span data-stu-id="f4cde-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Microsoft Defender ATP 進階搜捕結果集的影像](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="f4cde-147">篩選查詢結果</span><span class="sxs-lookup"><span data-stu-id="f4cde-147">Filter the query results</span></span>
<span data-ttu-id="f4cde-148">顯示在右側的篩選器可提供結果集的摘要。</span><span class="sxs-lookup"><span data-stu-id="f4cde-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="f4cde-149">每個資料行都有各自的區段，列出針對該資料行找到的獨特值和執行個體數量。</span><span class="sxs-lookup"><span data-stu-id="f4cde-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="f4cde-150">選取您要包含或排除的值上的 "+" 或 "-"，然後選取 [執行查詢]\*\*\*\*，以精簡您的查詢。</span><span class="sxs-lookup"><span data-stu-id="f4cde-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![進階搜捕篩選的影像](../../media/advanced-hunting-filter.png)

<span data-ttu-id="f4cde-152">一旦套用篩選來修改查詢，然後執行查詢，結果就會相應更新。</span><span class="sxs-lookup"><span data-stu-id="f4cde-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f4cde-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="f4cde-153">Related topics</span></span>
- [<span data-ttu-id="f4cde-154">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="f4cde-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f4cde-155">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="f4cde-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f4cde-156">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="f4cde-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f4cde-157">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="f4cde-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f4cde-158">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="f4cde-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
