---
title: 概觀 - 進位搜尋
description: 了解 Microsoft 365 中的進階搜捕查詢，以及如何使用該功能主動找出您的網路中的威脅和弱點
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、自訂偵測、架構、kusto、microsoft 365、Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 8fbf9c3d93434ec2dbc3f069bc0fbd3fe03fc260
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932271"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a><span data-ttu-id="74b34-104">使用 Microsoft 365 Defender 中的進位搜尋主動搜尋威脅</span><span class="sxs-lookup"><span data-stu-id="74b34-104">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="74b34-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="74b34-105">**Applies to:**</span></span>
- <span data-ttu-id="74b34-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74b34-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="74b34-107">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="74b34-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="74b34-108">您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="74b34-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="74b34-109">進階搜捕是一種查詢式威脅搜捕工具，可讓您探索最多 30 天的原始資料。</span><span class="sxs-lookup"><span data-stu-id="74b34-109">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="74b34-110">您可以主動檢查您網路中的事件，以找出威脅標記和實體。</span><span class="sxs-lookup"><span data-stu-id="74b34-110">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="74b34-111">彈性的資料存取可讓系統針對已知和潛在威脅進行快速搜尋。</span><span class="sxs-lookup"><span data-stu-id="74b34-111">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

<span data-ttu-id="74b34-112">您可以使用相同的威脅搜尋查詢來建立自訂的偵測規則。</span><span class="sxs-lookup"><span data-stu-id="74b34-112">You can use the same threat-hunting queries to build custom detection rules.</span></span> <span data-ttu-id="74b34-113">這些規則會自動執行，以檢查並回應可疑的外泄活動、錯誤的電腦和其他發現。</span><span class="sxs-lookup"><span data-stu-id="74b34-113">These rules run automatically to check for and then respond to suspected breach activity, misconfigured machines, and other findings.</span></span>

<span data-ttu-id="74b34-114">此功能類似于 Microsoft [Defender for Endpoint 中的進位搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。</span><span class="sxs-lookup"><span data-stu-id="74b34-114">This capability is similar to [advanced hunting in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).</span></span> <span data-ttu-id="74b34-115">此功能可在 Microsoft 365 資訊安全中心使用，支援可檢查更多資料集的查詢：</span><span class="sxs-lookup"><span data-stu-id="74b34-115">Available in Microsoft 365 security center, this capability supports queries that check a broader data set from:</span></span>

- <span data-ttu-id="74b34-116">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="74b34-116">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="74b34-117">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="74b34-117">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="74b34-118">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="74b34-118">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="74b34-119">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="74b34-119">Microsoft Defender for Identity</span></span>

<span data-ttu-id="74b34-120">若要使用進位搜尋[，請開啟 Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-120">To use advanced hunting, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="74b34-121">開始使用進階搜捕</span><span class="sxs-lookup"><span data-stu-id="74b34-121">Get started with advanced hunting</span></span>

<span data-ttu-id="74b34-122">我們建議您執行數個步驟，以快速開始進一步搜尋。</span><span class="sxs-lookup"><span data-stu-id="74b34-122">We recommend going through several steps to quickly get started with advanced hunting.</span></span>

| <span data-ttu-id="74b34-123">學習目標</span><span class="sxs-lookup"><span data-stu-id="74b34-123">Learning goal</span></span> | <span data-ttu-id="74b34-124">描述</span><span class="sxs-lookup"><span data-stu-id="74b34-124">Description</span></span> | <span data-ttu-id="74b34-125">資源</span><span class="sxs-lookup"><span data-stu-id="74b34-125">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="74b34-126">**瞭解語言**</span><span class="sxs-lookup"><span data-stu-id="74b34-126">**Learn the language**</span></span> | <span data-ttu-id="74b34-127">進位搜尋是以 [Kusto 查詢語言](https://docs.microsoft.com/azure/kusto/query/)為基礎，支援相同的語法及運算子。</span><span class="sxs-lookup"><span data-stu-id="74b34-127">Advanced hunting is based on [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="74b34-128">執行您的第一個查詢來開始學習查詢語言。</span><span class="sxs-lookup"><span data-stu-id="74b34-128">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="74b34-129">查詢語言概觀</span><span class="sxs-lookup"><span data-stu-id="74b34-129">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="74b34-130">**瞭解如何使用查詢結果**</span><span class="sxs-lookup"><span data-stu-id="74b34-130">**Learn how to use the query results**</span></span> | <span data-ttu-id="74b34-131">瞭解圖表以及您可以視圖或匯出結果的各種方式。</span><span class="sxs-lookup"><span data-stu-id="74b34-131">Learn about charts and various ways you can view or export your results.</span></span> <span data-ttu-id="74b34-132">探索如何快速調整查詢、向下切入以取得更豐富的資訊，以及採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="74b34-132">Explore how you can quickly tweak queries, drill down to get richer information, and take response actions.</span></span> | <span data-ttu-id="74b34-133">- [使用查詢結果](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-133">- [Work with query results](advanced-hunting-query-results.md)</span></span><br><span data-ttu-id="74b34-134">- [對查詢結果採取行動](advanced-hunting-take-action.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-134">- [Take action on query results](advanced-hunting-take-action.md)</span></span> |
| <span data-ttu-id="74b34-135">**了解結構描述**</span><span class="sxs-lookup"><span data-stu-id="74b34-135">**Understand the schema**</span></span> | <span data-ttu-id="74b34-136">深入了解結構描述中的資料表和資料行。</span><span class="sxs-lookup"><span data-stu-id="74b34-136">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="74b34-137">瞭解在建構查詢時要在哪裡尋找資料。</span><span class="sxs-lookup"><span data-stu-id="74b34-137">Learn where to look for data when constructing your queries.</span></span> | <span data-ttu-id="74b34-138">- [架構參照](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-138">- [Schema reference](advanced-hunting-schema-tables.md)</span></span><br><span data-ttu-id="74b34-139">- [從 Microsoft Defender for Endpoint 轉換](advanced-hunting-migrate-from-mdatp.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-139">- [Transition from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mdatp.md)</span></span> |
| <span data-ttu-id="74b34-140">**取得專家秘訣和範例**</span><span class="sxs-lookup"><span data-stu-id="74b34-140">**Get expert tips and examples**</span></span> | <span data-ttu-id="74b34-141">使用 Microsoft 專家的指南免費訓練。</span><span class="sxs-lookup"><span data-stu-id="74b34-141">Train for free with guides from Microsoft experts.</span></span> <span data-ttu-id="74b34-142">探索涵蓋不同威脅搜捕案例的預先定義查詢集合。</span><span class="sxs-lookup"><span data-stu-id="74b34-142">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | <span data-ttu-id="74b34-143">- [取得專家訓練](advanced-hunting-expert-training.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-143">- [Get expert training](advanced-hunting-expert-training.md)</span></span><br><span data-ttu-id="74b34-144">- [使用共用查詢](advanced-hunting-shared-queries.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-144">- [Use shared queries](advanced-hunting-shared-queries.md)</span></span><br><span data-ttu-id="74b34-145">- [前往搜尋](advanced-hunting-go-hunt.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-145">- [Go hunt](advanced-hunting-go-hunt.md)</span></span><br><span data-ttu-id="74b34-146">- [跨裝置、電子郵件、應用程式和身分身分尋找威脅](advanced-hunting-query-emails-devices.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-146">- [Hunt for threats across devices, emails, apps, and identities](advanced-hunting-query-emails-devices.md)</span></span> |
| <span data-ttu-id="74b34-147">**優化查詢並處理錯誤**</span><span class="sxs-lookup"><span data-stu-id="74b34-147">**Optimize queries and handle errors**</span></span> | <span data-ttu-id="74b34-148">瞭解如何建立有效率且無錯誤的查詢。</span><span class="sxs-lookup"><span data-stu-id="74b34-148">Understand how to create efficient and error-free queries.</span></span> | <span data-ttu-id="74b34-149">- [查詢最佳做法](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-149">- [Query best practices](advanced-hunting-best-practices.md)</span></span><br><span data-ttu-id="74b34-150">- [處理錯誤](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-150">- [Handle errors](advanced-hunting-errors.md)</span></span> |
| <span data-ttu-id="74b34-151">**建立自訂偵測規則**</span><span class="sxs-lookup"><span data-stu-id="74b34-151">**Create custom detection rules**</span></span> | <span data-ttu-id="74b34-152">瞭解如何使用進位搜尋查詢來觸發警示，並自動採取回應動作。</span><span class="sxs-lookup"><span data-stu-id="74b34-152">Understand how you can use advanced hunting queries to trigger alerts and take response actions automatically.</span></span> | <span data-ttu-id="74b34-153">- [自訂偵測概觀](custom-detections-overview.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-153">- [Custom detections overview](custom-detections-overview.md)</span></span><br><span data-ttu-id="74b34-154">- [自訂偵測規則](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="74b34-154">- [Custom detection rules](custom-detection-rules.md)</span></span> |

## <a name="get-access"></a><span data-ttu-id="74b34-155">取得存取權</span><span class="sxs-lookup"><span data-stu-id="74b34-155">Get access</span></span>
<span data-ttu-id="74b34-156">若要使用進位搜尋或其他 [Microsoft 365 Defender](microsoft-threat-protection.md) 功能，您需要在 Azure Active Directory 中擔任適當的角色。</span><span class="sxs-lookup"><span data-stu-id="74b34-156">To use advanced hunting or other [Microsoft 365 Defender](microsoft-threat-protection.md) capabilities, you need an appropriate role in Azure Active Directory.</span></span> <span data-ttu-id="74b34-157">此外，端點資料的存取權是由 Microsoft Defender for Endpoint (RBAC) 角色型存取控制決定。</span><span class="sxs-lookup"><span data-stu-id="74b34-157">Also, your access to endpoint data is determined by role-based access control (RBAC) settings in Microsoft Defender for Endpoint.</span></span> [<span data-ttu-id="74b34-158">閱讀有關管理 Microsoft 365 Defender 存取權</span><span class="sxs-lookup"><span data-stu-id="74b34-158">Read about managing access to Microsoft 365 Defender</span></span>](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a><span data-ttu-id="74b34-159">資料更新和更新頻率</span><span class="sxs-lookup"><span data-stu-id="74b34-159">Data freshness and update frequency</span></span>
<span data-ttu-id="74b34-160">進位搜尋資料可以分類為兩種不同的類型，每個合併方式不同。</span><span class="sxs-lookup"><span data-stu-id="74b34-160">Advanced hunting data can be categorized into two distinct types, each consolidated differently.</span></span>

- <span data-ttu-id="74b34-161">**事件或活動資料**— 填入有關警示、安全性事件、系統事件和例行評定的資料表。</span><span class="sxs-lookup"><span data-stu-id="74b34-161">**Event or activity data**—populates tables about alerts, security events, system events, and routine assessments.</span></span> <span data-ttu-id="74b34-162">進位搜尋幾乎會立即在收集它們成功傳送至對應雲端服務的感應器之後接收這些資料。</span><span class="sxs-lookup"><span data-stu-id="74b34-162">Advanced hunting receives this data almost immediately after the sensors that collect them successfully transmit them to the corresponding cloud services.</span></span> <span data-ttu-id="74b34-163">例如，您可以查詢工作站或網網域控制站上健康感應器的事件資料，它們幾乎可在 Microsoft Defender for Endpoint 和 Microsoft Defender 的識別功能上使用後立即查詢。</span><span class="sxs-lookup"><span data-stu-id="74b34-163">For example, you can query event data from healthy sensors on workstations or domain controllers almost immediately after they are available on Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>
- <span data-ttu-id="74b34-164">**實體資料**— 將資料表填入使用者和裝置相關資訊。</span><span class="sxs-lookup"><span data-stu-id="74b34-164">**Entity data**—populates tables with information about users and devices.</span></span> <span data-ttu-id="74b34-165">此資料來自相對靜態的資料來源和動態來源，例如 Active Directory 專案及事件記錄。</span><span class="sxs-lookup"><span data-stu-id="74b34-165">This data comes from both relatively static data sources and dynamic sources, such as Active Directory entries and event logs.</span></span> <span data-ttu-id="74b34-166">為了提供最新的資料，表格每 15 分鐘會以任何新資訊更新，並新增可能尚未完全填進的列。</span><span class="sxs-lookup"><span data-stu-id="74b34-166">To provide fresh data, tables are updated with any new information every 15 minutes, adding rows that might not be fully populated.</span></span> <span data-ttu-id="74b34-167">每 24 小時會合並一次資料，以插入包含每個實體最新、最全面資料集的記錄。</span><span class="sxs-lookup"><span data-stu-id="74b34-167">Every 24 hours, data is consolidated to insert a record that contains the latest, most comprehensive data set about each entity.</span></span>

## <a name="time-zone"></a><span data-ttu-id="74b34-168">時區</span><span class="sxs-lookup"><span data-stu-id="74b34-168">Time zone</span></span>
<span data-ttu-id="74b34-169">進位搜尋的時間資訊為 UTC 時區。</span><span class="sxs-lookup"><span data-stu-id="74b34-169">Time information in advanced hunting is in the UTC time zone.</span></span>

## <a name="related-topics"></a><span data-ttu-id="74b34-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="74b34-170">Related topics</span></span>
- [<span data-ttu-id="74b34-171">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="74b34-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="74b34-172">取得專家訓練</span><span class="sxs-lookup"><span data-stu-id="74b34-172">Get expert training</span></span>](advanced-hunting-expert-training.md)
- [<span data-ttu-id="74b34-173">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="74b34-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="74b34-174">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="74b34-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="74b34-175">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="74b34-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="74b34-176">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="74b34-176">Custom detections overview</span></span>](custom-detections-overview.md)

