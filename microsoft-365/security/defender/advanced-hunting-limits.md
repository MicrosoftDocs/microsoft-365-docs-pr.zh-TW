---
title: Microsoft 365 Defender 中的高級搜尋配額和使用參數
description: '瞭解各種配額和使用參數 (服務限制可讓高級搜尋服務保持回應的) '
keywords: 「高級搜尋」、「威脅搜尋」、「網路威脅搜尋」、Microsoft 365 Defender、microsoft 365、m365、搜尋、查詢、遙測、架構、kusto、CPU 限制、查詢限制、資源、最大結果、配額、參數、配置
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
ms.technology: m365d
ms.openlocfilehash: c9526363b0430514455db1fbdf12cfb7a18229f1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932986"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="96904-104">高級搜尋配額和使用參數</span><span class="sxs-lookup"><span data-stu-id="96904-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="96904-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="96904-105">**Applies to:**</span></span>
- <span data-ttu-id="96904-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96904-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="96904-107">為了讓服務具有高性能和回應能力，「高級搜尋」會設定各種配額和使用參數 (也稱為「服務限制」 ) 。</span><span class="sxs-lookup"><span data-stu-id="96904-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="96904-108">這些配額和參數會套用到以手動方式及 [自訂偵測規則](custom-detection-rules.md)執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="96904-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="96904-109">定期執行多個查詢的客戶應追蹤工作量並套用 [優化最佳作法](advanced-hunting-best-practices.md) ，以盡可能減少中斷。</span><span class="sxs-lookup"><span data-stu-id="96904-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="96904-110">請參閱下表以瞭解現有的配額和使用參數。</span><span class="sxs-lookup"><span data-stu-id="96904-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="96904-111">Quota 或參數</span><span class="sxs-lookup"><span data-stu-id="96904-111">Quota or parameter</span></span> | <span data-ttu-id="96904-112">Size</span><span class="sxs-lookup"><span data-stu-id="96904-112">Size</span></span> | <span data-ttu-id="96904-113">重新整理週期</span><span class="sxs-lookup"><span data-stu-id="96904-113">Refresh cycle</span></span> | <span data-ttu-id="96904-114">描述</span><span class="sxs-lookup"><span data-stu-id="96904-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="96904-115">資料範圍</span><span class="sxs-lookup"><span data-stu-id="96904-115">Data range</span></span> | <span data-ttu-id="96904-116">30 天</span><span class="sxs-lookup"><span data-stu-id="96904-116">30 days</span></span> | <span data-ttu-id="96904-117">每個查詢</span><span class="sxs-lookup"><span data-stu-id="96904-117">Every query</span></span> | <span data-ttu-id="96904-118">每個查詢都可以查詢過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="96904-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="96904-119">結果集</span><span class="sxs-lookup"><span data-stu-id="96904-119">Result set</span></span> | <span data-ttu-id="96904-120">10000列</span><span class="sxs-lookup"><span data-stu-id="96904-120">10,000 rows</span></span> | <span data-ttu-id="96904-121">每個查詢</span><span class="sxs-lookup"><span data-stu-id="96904-121">Every query</span></span> | <span data-ttu-id="96904-122">每個查詢最多可以傳回10000筆記錄。</span><span class="sxs-lookup"><span data-stu-id="96904-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="96904-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="96904-123">Timeout</span></span> | <span data-ttu-id="96904-124">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="96904-124">10 minutes</span></span> | <span data-ttu-id="96904-125">每個查詢</span><span class="sxs-lookup"><span data-stu-id="96904-125">Every query</span></span> | <span data-ttu-id="96904-126">每個查詢可長達10分鐘執行一次。</span><span class="sxs-lookup"><span data-stu-id="96904-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="96904-127">若未在10分鐘內完成，則服務會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="96904-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="96904-128">CPU 資源</span><span class="sxs-lookup"><span data-stu-id="96904-128">CPU resources</span></span> | <span data-ttu-id="96904-129">根據租使用者規模</span><span class="sxs-lookup"><span data-stu-id="96904-129">Based on tenant size</span></span> | <span data-ttu-id="96904-130">-在每小時，然後每隔15分鐘</span><span class="sxs-lookup"><span data-stu-id="96904-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="96904-131">-每日12午夜</span><span class="sxs-lookup"><span data-stu-id="96904-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="96904-132">服務會分別強制執行每日和15分鐘的配額。</span><span class="sxs-lookup"><span data-stu-id="96904-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="96904-133">針對每個配額，當查詢執行且租使用者已使用超過10% 的已分派資源 [時，門戶會顯示錯誤](advanced-hunting-errors.md) 。</span><span class="sxs-lookup"><span data-stu-id="96904-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="96904-134">如果租使用者已到達100%，直到下一天或15分鐘週期之後，才會封鎖查詢。</span><span class="sxs-lookup"><span data-stu-id="96904-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="96904-135">個別的配額和參數集適用于透過 API 執行的高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="96904-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="96904-136">閱讀高級搜尋 APIs</span><span class="sxs-lookup"><span data-stu-id="96904-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="96904-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="96904-137">Related topics</span></span>

- [<span data-ttu-id="96904-138">高級搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="96904-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="96904-139">處理高級搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="96904-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="96904-140">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="96904-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="96904-141">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="96904-141">Custom detections overview</span></span>](custom-detections-overview.md)