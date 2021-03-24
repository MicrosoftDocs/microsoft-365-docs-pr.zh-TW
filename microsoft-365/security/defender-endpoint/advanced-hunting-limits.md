---
title: Microsoft Defender ATP 中的高級搜尋限制
description: 瞭解可讓高級搜尋服務保持回應的各種服務限制
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp、搜尋、查詢、遙測、架構、kusto、CPU 限制、查詢限制、資源、最大結果
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060235"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="07fd5-104">高級搜尋服務限制</span><span class="sxs-lookup"><span data-stu-id="07fd5-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07fd5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="07fd5-105">**Applies to:**</span></span>
- [<span data-ttu-id="07fd5-106">適用於端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="07fd5-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="07fd5-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="07fd5-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="07fd5-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="07fd5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="07fd5-109">為了讓服務具有高性能和回應能力，「高級搜尋」會為手動執行和 [自訂偵測規則](custom-detection-rules.md)，設定各種查詢限制。</span><span class="sxs-lookup"><span data-stu-id="07fd5-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="07fd5-110">請參閱下表以瞭解這些限制。</span><span class="sxs-lookup"><span data-stu-id="07fd5-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="07fd5-111">限制</span><span class="sxs-lookup"><span data-stu-id="07fd5-111">Limit</span></span> | <span data-ttu-id="07fd5-112">Size</span><span class="sxs-lookup"><span data-stu-id="07fd5-112">Size</span></span> | <span data-ttu-id="07fd5-113">重新整理週期</span><span class="sxs-lookup"><span data-stu-id="07fd5-113">Refresh cycle</span></span> | <span data-ttu-id="07fd5-114">描述</span><span class="sxs-lookup"><span data-stu-id="07fd5-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="07fd5-115">資料範圍</span><span class="sxs-lookup"><span data-stu-id="07fd5-115">Data range</span></span> | <span data-ttu-id="07fd5-116">30 天</span><span class="sxs-lookup"><span data-stu-id="07fd5-116">30 days</span></span> | <span data-ttu-id="07fd5-117">每個查詢</span><span class="sxs-lookup"><span data-stu-id="07fd5-117">Every query</span></span> | <span data-ttu-id="07fd5-118">每個查詢都可以查詢過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="07fd5-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="07fd5-119">結果集</span><span class="sxs-lookup"><span data-stu-id="07fd5-119">Result set</span></span> | <span data-ttu-id="07fd5-120">10000列</span><span class="sxs-lookup"><span data-stu-id="07fd5-120">10,000 rows</span></span> | <span data-ttu-id="07fd5-121">每個查詢</span><span class="sxs-lookup"><span data-stu-id="07fd5-121">Every query</span></span> | <span data-ttu-id="07fd5-122">每個查詢最多可以傳回10000筆記錄。</span><span class="sxs-lookup"><span data-stu-id="07fd5-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="07fd5-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="07fd5-123">Timeout</span></span> | <span data-ttu-id="07fd5-124">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="07fd5-124">10 minutes</span></span> | <span data-ttu-id="07fd5-125">每個查詢</span><span class="sxs-lookup"><span data-stu-id="07fd5-125">Every query</span></span> | <span data-ttu-id="07fd5-126">每個查詢可長達10分鐘執行一次。</span><span class="sxs-lookup"><span data-stu-id="07fd5-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="07fd5-127">若未在10分鐘內完成，則服務會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="07fd5-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="07fd5-128">CPU 資源</span><span class="sxs-lookup"><span data-stu-id="07fd5-128">CPU resources</span></span> | <span data-ttu-id="07fd5-129">根據租使用者規模</span><span class="sxs-lookup"><span data-stu-id="07fd5-129">Based on tenant size</span></span> | <span data-ttu-id="07fd5-130">-在每小時，然後每隔15分鐘</span><span class="sxs-lookup"><span data-stu-id="07fd5-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="07fd5-131">-每日12午夜</span><span class="sxs-lookup"><span data-stu-id="07fd5-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="07fd5-132">服務會分別強制執行每日和15分鐘的限制。</span><span class="sxs-lookup"><span data-stu-id="07fd5-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="07fd5-133">針對每個限制，當執行查詢且租使用者使用的資源超過10% 時， [門戶會顯示錯誤](advanced-hunting-errors.md) 。</span><span class="sxs-lookup"><span data-stu-id="07fd5-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="07fd5-134">如果租使用者已到達100%，直到下一天或15分鐘週期之後，才會封鎖查詢。</span><span class="sxs-lookup"><span data-stu-id="07fd5-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="07fd5-135">一組不同的限制適用于透過 API 執行的高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="07fd5-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="07fd5-136">閱讀高級搜尋 APIs</span><span class="sxs-lookup"><span data-stu-id="07fd5-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="07fd5-137">定期執行多個查詢的客戶應追蹤工作量並套用 [優化最佳作法](advanced-hunting-best-practices.md) ，以盡可能減少超出這些限制所產生的中斷。</span><span class="sxs-lookup"><span data-stu-id="07fd5-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="07fd5-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="07fd5-138">Related topics</span></span>

- [<span data-ttu-id="07fd5-139">高級搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="07fd5-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="07fd5-140">處理高級搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="07fd5-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="07fd5-141">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="07fd5-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07fd5-142">自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="07fd5-142">Custom detections rules</span></span>](custom-detection-rules.md)
