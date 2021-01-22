---
title: Microsoft 365 Defender 中的進位搜尋配額與使用參數
description: 瞭解各種配額和使用量參數 (服務限制) 進一) 服務回應
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構、kusto、CPU 限制、查詢限制、資源、最大結果、配額、參數、配置
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
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929787"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="33cf2-104">進位搜尋配額與使用參數</span><span class="sxs-lookup"><span data-stu-id="33cf2-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="33cf2-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="33cf2-105">**Applies to:**</span></span>
- <span data-ttu-id="33cf2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33cf2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="33cf2-107">為保持服務執行速度與回應能力，進位搜尋會設定不同的配額 (使用參數，也稱為「服務限制」) 。</span><span class="sxs-lookup"><span data-stu-id="33cf2-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="33cf2-108">這些配額和參數適用于手動執行及自訂偵測 [規則的查詢](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="33cf2-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="33cf2-109">定期執行多個查詢的客戶應追蹤使用，並運用優化 [最佳做法，](advanced-hunting-best-practices.md) 將干擾降到最低。</span><span class="sxs-lookup"><span data-stu-id="33cf2-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="33cf2-110">請參閱下表以瞭解現有的配額和使用量參數。</span><span class="sxs-lookup"><span data-stu-id="33cf2-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="33cf2-111">配額或參數</span><span class="sxs-lookup"><span data-stu-id="33cf2-111">Quota or parameter</span></span> | <span data-ttu-id="33cf2-112">大小</span><span class="sxs-lookup"><span data-stu-id="33cf2-112">Size</span></span> | <span data-ttu-id="33cf2-113">重新更新迴圈</span><span class="sxs-lookup"><span data-stu-id="33cf2-113">Refresh cycle</span></span> | <span data-ttu-id="33cf2-114">說明</span><span class="sxs-lookup"><span data-stu-id="33cf2-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="33cf2-115">資料範圍</span><span class="sxs-lookup"><span data-stu-id="33cf2-115">Data range</span></span> | <span data-ttu-id="33cf2-116">30 天</span><span class="sxs-lookup"><span data-stu-id="33cf2-116">30 days</span></span> | <span data-ttu-id="33cf2-117">每個查詢</span><span class="sxs-lookup"><span data-stu-id="33cf2-117">Every query</span></span> | <span data-ttu-id="33cf2-118">每個查詢都可以查詢過去 30 天內的資料。</span><span class="sxs-lookup"><span data-stu-id="33cf2-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="33cf2-119">結果集</span><span class="sxs-lookup"><span data-stu-id="33cf2-119">Result set</span></span> | <span data-ttu-id="33cf2-120">10，000 列</span><span class="sxs-lookup"><span data-stu-id="33cf2-120">10,000 rows</span></span> | <span data-ttu-id="33cf2-121">每個查詢</span><span class="sxs-lookup"><span data-stu-id="33cf2-121">Every query</span></span> | <span data-ttu-id="33cf2-122">每個查詢最多可以回回 10，000 個記錄。</span><span class="sxs-lookup"><span data-stu-id="33cf2-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="33cf2-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="33cf2-123">Timeout</span></span> | <span data-ttu-id="33cf2-124">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="33cf2-124">10 minutes</span></span> | <span data-ttu-id="33cf2-125">每個查詢</span><span class="sxs-lookup"><span data-stu-id="33cf2-125">Every query</span></span> | <span data-ttu-id="33cf2-126">每個查詢最多可以執行 10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="33cf2-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="33cf2-127">如果 10 分鐘內無法完成，服務會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="33cf2-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="33cf2-128">CPU 資源</span><span class="sxs-lookup"><span data-stu-id="33cf2-128">CPU resources</span></span> | <span data-ttu-id="33cf2-129">根據租使用者大小</span><span class="sxs-lookup"><span data-stu-id="33cf2-129">Based on tenant size</span></span> | <span data-ttu-id="33cf2-130">- 使用小時，然後每 15 分鐘</span><span class="sxs-lookup"><span data-stu-id="33cf2-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="33cf2-131">- 每天午夜 12 點</span><span class="sxs-lookup"><span data-stu-id="33cf2-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="33cf2-132">此服務會分別強制執行每日和 15 分鐘的配額。</span><span class="sxs-lookup"><span data-stu-id="33cf2-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="33cf2-133">針對每個配額，每當[](advanced-hunting-errors.md)查詢執行且租使用者已耗用超過 10% 的已配置資源時，入口網站會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="33cf2-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="33cf2-134">如果租使用者已達 100%，直到下一個每日或 15 分鐘迴圈之後，查詢會封鎖。</span><span class="sxs-lookup"><span data-stu-id="33cf2-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="33cf2-135">另一組配額和參數適用于透過 API 執行進位搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="33cf2-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="33cf2-136">閱讀進一搜尋 API</span><span class="sxs-lookup"><span data-stu-id="33cf2-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="33cf2-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="33cf2-137">Related topics</span></span>

- [<span data-ttu-id="33cf2-138">進位搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="33cf2-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="33cf2-139">處理進位搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="33cf2-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="33cf2-140">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="33cf2-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="33cf2-141">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="33cf2-141">Custom detections overview</span></span>](custom-detections-overview.md)