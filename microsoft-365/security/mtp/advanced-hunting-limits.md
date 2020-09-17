---
title: Microsoft 威脅防護中的高級搜尋限制
description: 瞭解可讓高級搜尋服務保持回應的各種服務限制
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構，kusto，CPU 限制，查詢限制，資源，最大結果
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
ms.openlocfilehash: e3fbe29076d541df68dc39754960386fe935c7bc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950922"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="e8fc2-104">高級搜尋服務限制</span><span class="sxs-lookup"><span data-stu-id="e8fc2-104">Advanced hunting service limits</span></span>

<span data-ttu-id="e8fc2-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e8fc2-105">**Applies to:**</span></span>
- <span data-ttu-id="e8fc2-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="e8fc2-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e8fc2-107">為了讓服務具有高性能和回應能力，「高級搜尋」會為手動執行和 [自訂偵測規則](custom-detection-rules.md)，設定各種查詢限制。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="e8fc2-108">請參閱下表以瞭解這些限制。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="e8fc2-109">限制</span><span class="sxs-lookup"><span data-stu-id="e8fc2-109">Limit</span></span> | <span data-ttu-id="e8fc2-110">大小</span><span class="sxs-lookup"><span data-stu-id="e8fc2-110">Size</span></span> | <span data-ttu-id="e8fc2-111">重新整理週期</span><span class="sxs-lookup"><span data-stu-id="e8fc2-111">Refresh cycle</span></span> | <span data-ttu-id="e8fc2-112">說明</span><span class="sxs-lookup"><span data-stu-id="e8fc2-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="e8fc2-113">資料範圍</span><span class="sxs-lookup"><span data-stu-id="e8fc2-113">Data range</span></span> | <span data-ttu-id="e8fc2-114">30 天</span><span class="sxs-lookup"><span data-stu-id="e8fc2-114">30 days</span></span> | <span data-ttu-id="e8fc2-115">每個查詢</span><span class="sxs-lookup"><span data-stu-id="e8fc2-115">Every query</span></span> | <span data-ttu-id="e8fc2-116">每個查詢都可以查詢過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="e8fc2-117">結果集</span><span class="sxs-lookup"><span data-stu-id="e8fc2-117">Result set</span></span> | <span data-ttu-id="e8fc2-118">10000列</span><span class="sxs-lookup"><span data-stu-id="e8fc2-118">10,000 rows</span></span> | <span data-ttu-id="e8fc2-119">每個查詢</span><span class="sxs-lookup"><span data-stu-id="e8fc2-119">Every query</span></span> | <span data-ttu-id="e8fc2-120">每個查詢最多可以傳回10000筆記錄。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="e8fc2-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="e8fc2-121">Timeout</span></span> | <span data-ttu-id="e8fc2-122">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="e8fc2-122">10 minutes</span></span> | <span data-ttu-id="e8fc2-123">每個查詢</span><span class="sxs-lookup"><span data-stu-id="e8fc2-123">Every query</span></span> | <span data-ttu-id="e8fc2-124">每個查詢可長達10分鐘執行一次。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="e8fc2-125">若未在10分鐘內完成，則服務會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="e8fc2-126">CPU 資源</span><span class="sxs-lookup"><span data-stu-id="e8fc2-126">CPU resources</span></span> | <span data-ttu-id="e8fc2-127">根據租使用者規模</span><span class="sxs-lookup"><span data-stu-id="e8fc2-127">Based on tenant size</span></span> | <span data-ttu-id="e8fc2-128">-在每小時，然後每隔15分鐘</span><span class="sxs-lookup"><span data-stu-id="e8fc2-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="e8fc2-129">-每日12午夜</span><span class="sxs-lookup"><span data-stu-id="e8fc2-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="e8fc2-130">服務會分別強制執行每日和15分鐘的限制。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="e8fc2-131">針對每個限制，當執行查詢且租使用者使用的資源超過10% 時， [門戶會顯示錯誤](advanced-hunting-errors.md) 。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="e8fc2-132">如果租使用者已到達100%，直到下一天或15分鐘週期之後，才會封鎖查詢。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="e8fc2-133">一組不同的限制適用于透過 API 執行的高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="e8fc2-134">閱讀高級搜尋 APIs</span><span class="sxs-lookup"><span data-stu-id="e8fc2-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="e8fc2-135">定期執行多個查詢的客戶應追蹤工作量並套用 [優化最佳作法](advanced-hunting-best-practices.md) ，以盡可能減少超出這些限制所產生的中斷。</span><span class="sxs-lookup"><span data-stu-id="e8fc2-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8fc2-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="e8fc2-136">Related topics</span></span>

- [<span data-ttu-id="e8fc2-137">高級搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="e8fc2-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e8fc2-138">處理高級搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="e8fc2-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="e8fc2-139">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="e8fc2-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e8fc2-140">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="e8fc2-140">Custom detections overview</span></span>](custom-detections-overview.md)
