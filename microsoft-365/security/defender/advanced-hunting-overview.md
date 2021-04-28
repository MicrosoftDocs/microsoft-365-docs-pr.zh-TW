---
title: 概覽-高級搜尋
description: 了解 Microsoft 365 中的進階搜捕查詢，以及如何使用該功能主動找出您的網路中的威脅和弱點
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、Microsoft 365 Defender、microsoft 365、m365、search、查詢、遙測、自訂偵測、架構、kusto
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: f43d3bf9575f00649a2b5015a8be16351bebd11b
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073958"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="14a24-104">使用 Microsoft 365 Defender 中的高級搜尋主動搜尋威脅</span><span class="sxs-lookup"><span data-stu-id="14a24-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="14a24-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="14a24-105">**Applies to:**</span></span>
- <span data-ttu-id="14a24-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14a24-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="14a24-107">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="14a24-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="14a24-108">您可以[在實驗室環境中評估](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 或[在生產環境中執行試驗專案](m365d-pilot.md?ocid=cx-evalpilot)。</span><span class="sxs-lookup"><span data-stu-id="14a24-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="14a24-109">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="14a24-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="14a24-110">您可以主動檢查您網路中的事件，以找出威脅指示器和實體。</span><span class="sxs-lookup"><span data-stu-id="14a24-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="14a24-111">對資料的靈活存取可對已知和潛在的威脅進行無限制的搜尋。</span><span class="sxs-lookup"><span data-stu-id="14a24-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="14a24-112">您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="14a24-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="14a24-113">這些規則會自動執行，以檢查是否有可疑的破壞活動、錯誤設定的機器及其他發現的回應。</span><span class="sxs-lookup"><span data-stu-id="14a24-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="14a24-114">這項功能類似于 [Microsoft Defender For Endpoint 中的高級搜尋](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="14a24-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="14a24-115">可在 Microsoft 365 的安全性中心使用此功能，可支援從下列專案中檢查更廣泛資料集的查詢：</span><span class="sxs-lookup"><span data-stu-id="14a24-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="14a24-116">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="14a24-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="14a24-117">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="14a24-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="14a24-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="14a24-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="14a24-119">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="14a24-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="14a24-120">若要使用高級搜尋，請 [開啟 Microsoft 365 Defender](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="14a24-120">To use advanced hunting, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="14a24-121">開始使用進階搜捕</span><span class="sxs-lookup"><span data-stu-id="14a24-121">Get started with advanced hunting</span></span>

<span data-ttu-id="14a24-122">我們建議您逐步完成一些步驟，快速開始使用高級搜尋。</span><span class="sxs-lookup"><span data-stu-id="14a24-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="14a24-123">學習目標</span><span class="sxs-lookup"><span data-stu-id="14a24-123">Learning goal</span></span> | <span data-ttu-id="14a24-124">描述</span><span class="sxs-lookup"><span data-stu-id="14a24-124">Description</span></span> | <span data-ttu-id="14a24-125">資源</span><span class="sxs-lookup"><span data-stu-id="14a24-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="14a24-126">**瞭解語言**</span><span class="sxs-lookup"><span data-stu-id="14a24-126">**Learn the language**</span></span> | <span data-ttu-id="14a24-127">「高級搜尋」是以 [Kusto 查詢語言](/azure/kusto/query/)為基礎，支援相同的語法及運算子。</span><span class="sxs-lookup"><span data-stu-id="14a24-127">Advanced hunting is based on [Kusto query language](/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="14a24-128">執行您的第一個查詢來開始學習查詢語言。</span><span class="sxs-lookup"><span data-stu-id="14a24-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="14a24-129">查詢語言概觀</span><span class="sxs-lookup"><span data-stu-id="14a24-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="14a24-130">**瞭解如何使用查詢結果**</span><span class="sxs-lookup"><span data-stu-id="14a24-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="14a24-131">深入瞭解圖表和您可以查看或匯出結果的各種方式。</span><span class="sxs-lookup"><span data-stu-id="14a24-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="14a24-132">探索您如何快速調整查詢、深入查看以取得更豐富的資訊，以及採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="14a24-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="14a24-133">- [使用查詢結果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br /> <span data-ttu-id="14a24-134">- [對查詢結果採取動作](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="14a24-135">**了解結構描述**</span><span class="sxs-lookup"><span data-stu-id="14a24-135">**Understand the schema**</span></span> | <span data-ttu-id="14a24-136">深入了解結構描述中的資料表和資料行。</span><span class="sxs-lookup"><span data-stu-id="14a24-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="14a24-137">瞭解在建立查詢時要尋找資料的位置。</span><span class="sxs-lookup"><span data-stu-id="14a24-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="14a24-138">- [架構參考](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span> <br /><span data-ttu-id="14a24-139">- [從 Microsoft Defender for Endpoint 轉換](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md)</span></span> |
| <span data-ttu-id="14a24-140">**取得專家秘訣和範例**</span><span class="sxs-lookup"><span data-stu-id="14a24-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="14a24-141">透過 Microsoft 專家的指南訓練。</span><span class="sxs-lookup"><span data-stu-id="14a24-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="14a24-142">探索涵蓋不同威脅搜捕案例的預先定義查詢集合。</span><span class="sxs-lookup"><span data-stu-id="14a24-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="14a24-143">- [取得專家訓練](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span> <br /><span data-ttu-id="14a24-144">- [使用共用查詢](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span> <br /><span data-ttu-id="14a24-145">- [開始搜尋](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span> <br /><span data-ttu-id="14a24-146">- [尋找跨裝置、電子郵件、應用程式和身分識別的威脅](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="14a24-147">**優化查詢並處理錯誤**</span><span class="sxs-lookup"><span data-stu-id="14a24-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="14a24-148">瞭解如何建立高效且無錯誤的查詢。</span><span class="sxs-lookup"><span data-stu-id="14a24-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="14a24-149">- [查詢最佳作法](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br /><span data-ttu-id="14a24-150">- [處理錯誤](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="14a24-151">**建立自訂偵測規則**</span><span class="sxs-lookup"><span data-stu-id="14a24-151">**Create custom detection rules**</span></span> | <span data-ttu-id="14a24-152">瞭解您可以如何使用高級搜尋查詢來觸發提醒並自動採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="14a24-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="14a24-153">- [自訂偵測簡介](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-153">- [Custom detections overview](custom-detections-overview.md)</span></span> <br /><span data-ttu-id="14a24-154">- [自訂偵測規則](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="14a24-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="14a24-155">取得存取權</span><span class="sxs-lookup"><span data-stu-id="14a24-155">Get access</span></span>
<span data-ttu-id="14a24-156">若要使用高級搜尋或其他 [Microsoft 365 Defender](microsoft-365-defender.md) 功能，您需要在 Azure Active Directory 中使用適當的角色。</span><span class="sxs-lookup"><span data-stu-id="14a24-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-365-defender.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="14a24-157">[閱讀高級搜尋所需的角色和許可權](custom-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="14a24-157">[Read about required roles and permissions for advanced hunting](custom-roles.md).</span></span>

<span data-ttu-id="14a24-158">此外，您可以使用 Microsoft Defender for Endpoint 中的角色型存取控制 (RBAC) 設定來決定您對端點資料的存取。</span><span class="sxs-lookup"><span data-stu-id="14a24-158">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="14a24-159">[閱讀管理 Microsoft 365 Defender 存取的相關資訊](m365d-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="14a24-159">[Read about managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>


## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="14a24-160">資料新鮮度和更新頻率</span><span class="sxs-lookup"><span data-stu-id="14a24-160">Data freshness and update frequency</span></span>
<span data-ttu-id="14a24-161">「高級搜尋」資料可以分類成兩種不同的類型，每個不同的合併。</span><span class="sxs-lookup"><span data-stu-id="14a24-161">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="14a24-162">**事件或活動資料**--填入有關警示、安全性事件、系統事件及例行評估的表格。</span><span class="sxs-lookup"><span data-stu-id="14a24-162">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="14a24-163">[！注意] 高級搜尋幾乎會在收集成功的感應器成功傳送至對應的雲端服務之後立即接收這類資料。</span><span class="sxs-lookup"><span data-stu-id="14a24-163">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="14a24-164">例如，您可以在工作站或網域控制站上的狀況良好的感應器上直接查詢事件資料，而這些資料在 Microsoft Defender for Endpoint 和 Microsoft Defender 身分識別後幾乎可以使用。</span><span class="sxs-lookup"><span data-stu-id="14a24-164">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="14a24-165">**實體資料**—以使用者和裝置的相關資訊填入資料表。</span><span class="sxs-lookup"><span data-stu-id="14a24-165">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="14a24-166">此資料來自相對靜態資料來源和動態來源，例如 Active Directory 專案和事件記錄。</span><span class="sxs-lookup"><span data-stu-id="14a24-166">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="14a24-167">若要提供全新的資料，每隔15分鐘更新一次所有新資訊的資料表，新增可能不會填滿的資料列。</span><span class="sxs-lookup"><span data-stu-id="14a24-167">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="14a24-168">每24小時都會合並資料，以插入記錄，其中包含每個實體的最新、最全面的資料集。</span><span class="sxs-lookup"><span data-stu-id="14a24-168">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="14a24-169">時區</span><span class="sxs-lookup"><span data-stu-id="14a24-169">Time zone</span></span>
<span data-ttu-id="14a24-170">「高級搜尋」中的時間資訊是在 UTC 時區。</span><span class="sxs-lookup"><span data-stu-id="14a24-170">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="14a24-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="14a24-171">Related topics</span></span>
- [<span data-ttu-id="14a24-172">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="14a24-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="14a24-173">取得專家訓練</span><span class="sxs-lookup"><span data-stu-id="14a24-173">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="14a24-174">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="14a24-174">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="14a24-175">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="14a24-175">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="14a24-176">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="14a24-176">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="14a24-177">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="14a24-177">Custom detections overview</span></span>](custom-detections-overview.md)
