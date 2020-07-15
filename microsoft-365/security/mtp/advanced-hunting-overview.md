---
title: 概覽-高級搜尋
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7bda309dbb1b601c77b6fb34ff9b8be14d5638d
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138275"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="bebcc-104">使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="bebcc-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="bebcc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bebcc-105">**Applies to:**</span></span>
- <span data-ttu-id="bebcc-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bebcc-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="bebcc-107">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="bebcc-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="bebcc-108">您可以主動檢查您網路中的事件，以找出相關的指標和實體。</span><span class="sxs-lookup"><span data-stu-id="bebcc-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="bebcc-109">可靈活存取資料有助於不受限制地同時搜捕已知和潛在的威脅。</span><span class="sxs-lookup"><span data-stu-id="bebcc-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="bebcc-110">您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="bebcc-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="bebcc-111">自動執行這些規則，以檢查各種活動和系統狀態，包括可疑的破壞活動和錯誤配置的電腦。</span><span class="sxs-lookup"><span data-stu-id="bebcc-111">These rules run automatically to check for and respond to various events and system states, including suspected breach activity and misconfigured machines.</span></span>

<span data-ttu-id="bebcc-112">在 Microsoft 365 的安全性中心，「高級搜尋」支援查詢可查看各種工作區中的資料，包括來自 Microsoft Defender ATP 的裝置、電子郵件、應用程式和身分識別的資料、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP。</span><span class="sxs-lookup"><span data-stu-id="bebcc-112">In the Microsoft 365 security center, advanced hunting supports queries that look into data from various workspaces, including data about devices, emails, apps, and identities from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="bebcc-113">若要使用進階搜捕，請[開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="bebcc-113">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="bebcc-114">開始使用進階搜捕</span><span class="sxs-lookup"><span data-stu-id="bebcc-114">Get started with advanced hunting</span></span>

<span data-ttu-id="bebcc-115">建議您透過數個步驟來利用進階搜捕快速啟動並執行。</span><span class="sxs-lookup"><span data-stu-id="bebcc-115">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="bebcc-116">學習目標</span><span class="sxs-lookup"><span data-stu-id="bebcc-116">Learning goal</span></span> | <span data-ttu-id="bebcc-117">描述</span><span class="sxs-lookup"><span data-stu-id="bebcc-117">Description</span></span> | <span data-ttu-id="bebcc-118">資源</span><span class="sxs-lookup"><span data-stu-id="bebcc-118">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="bebcc-119">**了解語言**</span><span class="sxs-lookup"><span data-stu-id="bebcc-119">**Get a feel for the language**</span></span> | <span data-ttu-id="bebcc-120">「高級搜尋」是以[Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。</span><span class="sxs-lookup"><span data-stu-id="bebcc-120">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="bebcc-121">執行您的第一個查詢來開始學習查詢語言。</span><span class="sxs-lookup"><span data-stu-id="bebcc-121">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="bebcc-122">查詢語言概觀</span><span class="sxs-lookup"><span data-stu-id="bebcc-122">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="bebcc-123">**瞭解如何使用查詢結果**</span><span class="sxs-lookup"><span data-stu-id="bebcc-123">**Learn how to use the query results**</span></span> | <span data-ttu-id="bebcc-124">深入瞭解圖表和您可以查看或匯出結果的各種方式。</span><span class="sxs-lookup"><span data-stu-id="bebcc-124">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="bebcc-125">探索如何快速調整查詢，並深入瞭解如何取得更豐富的資訊。</span><span class="sxs-lookup"><span data-stu-id="bebcc-125">Explore how you can quickly tweak queries and drill down to get richer information.</span></span> | [<span data-ttu-id="bebcc-126">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="bebcc-126">Work with query results</span></span>](advanced-hunting-query-results.md) |
| <span data-ttu-id="bebcc-127">**了解結構描述**</span><span class="sxs-lookup"><span data-stu-id="bebcc-127">**Understand the schema**</span></span> | <span data-ttu-id="bebcc-128">深入了解結構描述中的資料表和資料行。</span><span class="sxs-lookup"><span data-stu-id="bebcc-128">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="bebcc-129">這可協助您決定要在何處尋找資料，以及如何建構查詢。</span><span class="sxs-lookup"><span data-stu-id="bebcc-129">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="bebcc-130">結構描述參考</span><span class="sxs-lookup"><span data-stu-id="bebcc-130">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="bebcc-131">**運用預先定義的查詢**</span><span class="sxs-lookup"><span data-stu-id="bebcc-131">**Leverage predefined queries**</span></span> | <span data-ttu-id="bebcc-132">探索涵蓋不同威脅搜捕案例的預先定義查詢集合。</span><span class="sxs-lookup"><span data-stu-id="bebcc-132">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="bebcc-133">- [使用共用查詢](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="bebcc-133">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="bebcc-134">- [開始搜尋](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="bebcc-134">- [Go hunt](advanced-hunting-go-hunt.md)</span></span> |
| <span data-ttu-id="bebcc-135">**最佳化查詢**</span><span class="sxs-lookup"><span data-stu-id="bebcc-135">**Optimize queries**</span></span> | <span data-ttu-id="bebcc-136">了解如何建立可結合來自電子郵件和裝置資料的高效查詢。</span><span class="sxs-lookup"><span data-stu-id="bebcc-136">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="bebcc-137">- [查詢最佳作法](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="bebcc-137">- [Query best practices](advanced-hunting-shared-queries.md)</span></span> <br><span data-ttu-id="bebcc-138">- [跨裝置和電子郵件進行搜尋](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="bebcc-138">- [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span> |
| <span data-ttu-id="bebcc-139">**建立自訂偵測規則**</span><span class="sxs-lookup"><span data-stu-id="bebcc-139">**Create custom detection rules**</span></span> | <span data-ttu-id="bebcc-140">瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動套用回應動作。</span><span class="sxs-lookup"><span data-stu-id="bebcc-140">Understand how you can use advanced hunting queries to trigger alerts and apply response actions automatically.</span></span> | <span data-ttu-id="bebcc-141">- [自訂偵測簡介](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bebcc-141">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="bebcc-142">- [自訂偵測規則](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="bebcc-142">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="bebcc-143">取得存取權</span><span class="sxs-lookup"><span data-stu-id="bebcc-143">Get access</span></span>
<span data-ttu-id="bebcc-144">若要使用高級搜尋或其他[Microsoft 威脅防護](microsoft-threat-protection.md)功能，您必須在 Azure AD 中獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="bebcc-144">To use advanced hunting or other [Microsoft Threat Protection](microsoft-threat-protection.md) capabilities, you need to be assigned an appropriate role in Azure AD.</span></span> <span data-ttu-id="bebcc-145">請注意，在 Microsoft Defender ATP 中，以角色為基礎的存取控制設定會影響對端點資料的存取。</span><span class="sxs-lookup"><span data-stu-id="bebcc-145">Note that your access to endpoint data is influenced by role-based access control settings in Microsoft Defender ATP.</span></span> [<span data-ttu-id="bebcc-146">閱讀管理 Microsoft 威脅防護存取的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bebcc-146">Read about managing access to Microsoft Threat Protection</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="bebcc-147">資料新鮮度和更新頻率</span><span class="sxs-lookup"><span data-stu-id="bebcc-147">Data freshness and update frequency</span></span>
<span data-ttu-id="bebcc-148">「高級搜尋」資料可以分類成兩種不同的類型，每個不同的合併。</span><span class="sxs-lookup"><span data-stu-id="bebcc-148">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="bebcc-149">**事件或活動資料**--填入有關警示、安全性事件、系統事件及例行評估的表格。</span><span class="sxs-lookup"><span data-stu-id="bebcc-149">**Event or activity data** — populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="bebcc-150">[！注意] 高級搜尋幾乎會在收集成功的感應器成功傳送至對應的雲端服務之後立即接收這類資料。</span><span class="sxs-lookup"><span data-stu-id="bebcc-150">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="bebcc-151">例如，您可以在工作站或網域控制站上的狀況良好感應器上開始查詢事件資料，使其能在 Microsoft Defender ATP 和 Azure ATP 上的使用中立即開始。</span><span class="sxs-lookup"><span data-stu-id="bebcc-151">For example, you can start to query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender ATP and Azure ATP.</span></span>
- <span data-ttu-id="bebcc-152">**實體資料**—使用使用者和裝置的整合式資訊來填入資料表。</span><span class="sxs-lookup"><span data-stu-id="bebcc-152">**Entity data** — populates tables with consolidated information about users and devices.</span></span> <span data-ttu-id="bebcc-153">此資料來自相對靜態資料來源（例如 Active Directory 專案）和動態來源，例如事件記錄。</span><span class="sxs-lookup"><span data-stu-id="bebcc-153">This data comes from both relatively static data sources, such as Active Directory entries, and dynamic sources, such as event logs.</span></span> <span data-ttu-id="bebcc-154">若要提供新的資料，每15分鐘更新一次表格中的任何新資訊，新增可能不會填滿的資料列。</span><span class="sxs-lookup"><span data-stu-id="bebcc-154">To provide fresh data, tables are updated every 15 minutes with any new information, adding rows that might not be fully populated.</span></span> <span data-ttu-id="bebcc-155">每24小時都會合並資料，以插入記錄，其中包含每個實體的最新、最全面的資料集。</span><span class="sxs-lookup"><span data-stu-id="bebcc-155">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bebcc-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="bebcc-156">Related topics</span></span>
- [<span data-ttu-id="bebcc-157">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="bebcc-157">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bebcc-158">使用查詢結果工作</span><span class="sxs-lookup"><span data-stu-id="bebcc-158">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="bebcc-159">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="bebcc-159">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bebcc-160">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="bebcc-160">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bebcc-161">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="bebcc-161">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bebcc-162">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="bebcc-162">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="bebcc-163">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="bebcc-163">Custom detections overview</span></span>](custom-detections-overview.md)
