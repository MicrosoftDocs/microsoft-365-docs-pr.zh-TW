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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a059c4dd1f09bc5101f5ebb027c92e6551ca8dd6
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430418"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="c168a-104">使用 Microsoft 威脅防護中的進階搜捕功能主動尋找威脅</span><span class="sxs-lookup"><span data-stu-id="c168a-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c168a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c168a-105">**Applies to:**</span></span>
- <span data-ttu-id="c168a-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="c168a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c168a-107">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="c168a-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="c168a-108">您可以主動檢查您網路中的事件，以找出威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="c168a-108">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="c168a-109">對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。</span><span class="sxs-lookup"><span data-stu-id="c168a-109">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="c168a-110">您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="c168a-110">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="c168a-111">這些規則會自動執行，以檢查是否有可疑的破壞活動、錯誤設定的機器及其他發現的回應。</span><span class="sxs-lookup"><span data-stu-id="c168a-111">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="c168a-112">這項功能類似于 [Microsoft DEFENDER ATP 中的高級搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="c168a-112">This capability is similar to [advanced hunting in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="c168a-113">可在 Microsoft 365 的安全性中心使用此功能，可支援從下列專案中檢查更廣泛資料集的查詢：</span><span class="sxs-lookup"><span data-stu-id="c168a-113">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="c168a-114">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="c168a-114">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="c168a-115">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="c168a-115">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="c168a-116">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c168a-116">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c168a-117">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="c168a-117">Azure Advanced Threat Protection</span></span>

<span data-ttu-id="c168a-118">若要使用進階搜捕，請[開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="c168a-118">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="c168a-119">開始使用進階搜捕</span><span class="sxs-lookup"><span data-stu-id="c168a-119">Get started with advanced hunting</span></span>

<span data-ttu-id="c168a-120">我們建議您逐步完成一些步驟，快速開始使用高級搜尋。</span><span class="sxs-lookup"><span data-stu-id="c168a-120">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="c168a-121">學習目標</span><span class="sxs-lookup"><span data-stu-id="c168a-121">Learning goal</span></span> | <span data-ttu-id="c168a-122">描述</span><span class="sxs-lookup"><span data-stu-id="c168a-122">Description</span></span> | <span data-ttu-id="c168a-123">資源</span><span class="sxs-lookup"><span data-stu-id="c168a-123">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="c168a-124">**瞭解語言**</span><span class="sxs-lookup"><span data-stu-id="c168a-124">**Learn the language**</span></span> | <span data-ttu-id="c168a-125">「高級搜尋」是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。</span><span class="sxs-lookup"><span data-stu-id="c168a-125">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="c168a-126">執行您的第一個查詢來開始學習查詢語言。</span><span class="sxs-lookup"><span data-stu-id="c168a-126">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="c168a-127">查詢語言概觀</span><span class="sxs-lookup"><span data-stu-id="c168a-127">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="c168a-128">**瞭解如何使用查詢結果**</span><span class="sxs-lookup"><span data-stu-id="c168a-128">**Learn how to use the query results**</span></span> | <span data-ttu-id="c168a-129">深入瞭解圖表和您可以查看或匯出結果的各種方式。</span><span class="sxs-lookup"><span data-stu-id="c168a-129">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="c168a-130">探索您如何快速調整查詢、深入查看以取得更豐富的資訊，以及採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="c168a-130">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="c168a-131">- [使用查詢結果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-131">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="c168a-132">- [對查詢結果採取動作](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-132">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="c168a-133">**了解結構描述**</span><span class="sxs-lookup"><span data-stu-id="c168a-133">**Understand the schema**</span></span> | <span data-ttu-id="c168a-134">深入了解結構描述中的資料表和資料行。</span><span class="sxs-lookup"><span data-stu-id="c168a-134">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="c168a-135">瞭解在建立查詢時要尋找資料的位置。</span><span class="sxs-lookup"><span data-stu-id="c168a-135">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="c168a-136">- [架構參考](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-136">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="c168a-137">- [從 Microsoft Defender ATP 轉換](advanced-hunting-migrate-from-mdatp.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-137">- [Transition from Microsoft Defender ATP](advanced-hunting-migrate-from-mdatp.md)</span></span> |
| <span data-ttu-id="c168a-138">**取得專家秘訣和範例**</span><span class="sxs-lookup"><span data-stu-id="c168a-138">**Get expert tips and examples**</span></span> | <span data-ttu-id="c168a-139">透過 Microsoft 專家的指南訓練。</span><span class="sxs-lookup"><span data-stu-id="c168a-139">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="c168a-140">探索涵蓋不同威脅搜捕案例的預先定義查詢集合。</span><span class="sxs-lookup"><span data-stu-id="c168a-140">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="c168a-141">- [取得專家訓練](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-141">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="c168a-142">- [使用共用查詢](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-142">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="c168a-143">- [開始搜尋](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-143">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="c168a-144">- [尋找跨裝置、電子郵件、應用程式和身分識別的威脅](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-144">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="c168a-145">**優化查詢並處理錯誤**</span><span class="sxs-lookup"><span data-stu-id="c168a-145">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="c168a-146">瞭解如何建立高效且無錯誤的查詢。</span><span class="sxs-lookup"><span data-stu-id="c168a-146">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="c168a-147">- [查詢最佳作法](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-147">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="c168a-148">- [處理錯誤](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-148">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="c168a-149">**建立自訂偵測規則**</span><span class="sxs-lookup"><span data-stu-id="c168a-149">**Create custom detection rules**</span></span> | <span data-ttu-id="c168a-150">瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="c168a-150">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="c168a-151">- [自訂偵測簡介](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-151">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="c168a-152">- [自訂偵測規則](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="c168a-152">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="c168a-153">取得存取權</span><span class="sxs-lookup"><span data-stu-id="c168a-153">Get access</span></span>
<span data-ttu-id="c168a-154">若要使用高級搜尋或其他 [Microsoft 威脅防護](microsoft-threat-protection.md) 功能，您在 Azure Active Directory 中需要有適當的角色。</span><span class="sxs-lookup"><span data-stu-id="c168a-154">To use advanced hunting or other [Microsoft Threat Protection](microsoft-threat-protection.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="c168a-155">此外，您可以使用 Microsoft Defender ATP 中的角色型存取控制 (RBAC) 設定所決定的端點資料存取。</span><span class="sxs-lookup"><span data-stu-id="c168a-155">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender ATP.</span></span> [<span data-ttu-id="c168a-156">閱讀管理 Microsoft 威脅防護存取的相關資訊</span><span class="sxs-lookup"><span data-stu-id="c168a-156">Read about managing access to Microsoft Threat Protection</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="c168a-157">資料新鮮度和更新頻率</span><span class="sxs-lookup"><span data-stu-id="c168a-157">Data freshness and update frequency</span></span>
<span data-ttu-id="c168a-158">「高級搜尋」資料可以分類成兩種不同的類型，每個不同的合併。</span><span class="sxs-lookup"><span data-stu-id="c168a-158">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="c168a-159">**事件或活動資料**--填入有關警示、安全性事件、系統事件及例行評估的表格。</span><span class="sxs-lookup"><span data-stu-id="c168a-159">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="c168a-160">[！注意] 高級搜尋幾乎會在收集成功的感應器成功傳送至對應的雲端服務之後立即接收這類資料。</span><span class="sxs-lookup"><span data-stu-id="c168a-160">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="c168a-161">例如，您可以在工作站或網域控制站上的狀況良好感應器上查詢事件資料，使其在 Microsoft Defender ATP 和 Azure ATP 上可用之後幾乎可以立即查詢。</span><span class="sxs-lookup"><span data-stu-id="c168a-161">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender ATP and Azure ATP.</span></span>
- <span data-ttu-id="c168a-162">**實體資料**—以使用者和裝置的相關資訊填入資料表。</span><span class="sxs-lookup"><span data-stu-id="c168a-162">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="c168a-163">此資料來自相對靜態資料來源和動態來源，例如 Active Directory 專案和事件記錄。</span><span class="sxs-lookup"><span data-stu-id="c168a-163">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="c168a-164">若要提供全新的資料，每隔15分鐘更新一次所有新資訊的資料表，新增可能不會填滿的資料列。</span><span class="sxs-lookup"><span data-stu-id="c168a-164">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="c168a-165">每24小時都會合並資料，以插入記錄，其中包含每個實體的最新、最全面的資料集。</span><span class="sxs-lookup"><span data-stu-id="c168a-165">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="c168a-166">時區</span><span class="sxs-lookup"><span data-stu-id="c168a-166">Time zone</span></span>
<span data-ttu-id="c168a-167">「高級搜尋」中的時間資訊是在 UTC 時區。</span><span class="sxs-lookup"><span data-stu-id="c168a-167">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c168a-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="c168a-168">Related topics</span></span>
- [<span data-ttu-id="c168a-169">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="c168a-169">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c168a-170">取得專家訓練</span><span class="sxs-lookup"><span data-stu-id="c168a-170">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="c168a-171">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="c168a-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c168a-172">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="c168a-172">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c168a-173">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="c168a-173">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c168a-174">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="c168a-174">Custom detections overview</span></span>](custom-detections-overview.md)

