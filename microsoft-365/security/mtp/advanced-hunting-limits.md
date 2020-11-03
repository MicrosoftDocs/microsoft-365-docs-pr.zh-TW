---
title: Microsoft 365 Defender 中的高級搜尋配額和使用參數
description: '瞭解各種配額和使用參數 (服務限制可讓高級搜尋服務保持回應的) '
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構，kusto，CPU 限制，查詢限制，資源，最大結果，配額，參數，配置
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
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847365"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="9e48e-104">高級搜尋配額和使用參數</span><span class="sxs-lookup"><span data-stu-id="9e48e-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e48e-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="9e48e-105">**Applies to:**</span></span>
- <span data-ttu-id="9e48e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e48e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9e48e-107">為了讓服務具有高性能和回應能力，「高級搜尋」會設定各種配額和使用參數 (也稱為「服務限制」 ) 。</span><span class="sxs-lookup"><span data-stu-id="9e48e-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="9e48e-108">這些配額和參數會套用到以手動方式及 [自訂偵測規則](custom-detection-rules.md)執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="9e48e-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="9e48e-109">定期執行多個查詢的客戶應追蹤工作量並套用 [優化最佳作法](advanced-hunting-best-practices.md) ，以盡可能減少中斷。</span><span class="sxs-lookup"><span data-stu-id="9e48e-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="9e48e-110">請參閱下表以瞭解現有的配額和使用參數。</span><span class="sxs-lookup"><span data-stu-id="9e48e-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="9e48e-111">Quota 或參數</span><span class="sxs-lookup"><span data-stu-id="9e48e-111">Quota or parameter</span></span> | <span data-ttu-id="9e48e-112">大小</span><span class="sxs-lookup"><span data-stu-id="9e48e-112">Size</span></span> | <span data-ttu-id="9e48e-113">重新整理週期</span><span class="sxs-lookup"><span data-stu-id="9e48e-113">Refresh cycle</span></span> | <span data-ttu-id="9e48e-114">描述</span><span class="sxs-lookup"><span data-stu-id="9e48e-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="9e48e-115">資料範圍</span><span class="sxs-lookup"><span data-stu-id="9e48e-115">Data range</span></span> | <span data-ttu-id="9e48e-116">30 天</span><span class="sxs-lookup"><span data-stu-id="9e48e-116">30 days</span></span> | <span data-ttu-id="9e48e-117">每個查詢</span><span class="sxs-lookup"><span data-stu-id="9e48e-117">Every query</span></span> | <span data-ttu-id="9e48e-118">每個查詢都可以查詢過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="9e48e-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="9e48e-119">結果集</span><span class="sxs-lookup"><span data-stu-id="9e48e-119">Result set</span></span> | <span data-ttu-id="9e48e-120">10000列</span><span class="sxs-lookup"><span data-stu-id="9e48e-120">10,000 rows</span></span> | <span data-ttu-id="9e48e-121">每個查詢</span><span class="sxs-lookup"><span data-stu-id="9e48e-121">Every query</span></span> | <span data-ttu-id="9e48e-122">每個查詢最多可以傳回10000筆記錄。</span><span class="sxs-lookup"><span data-stu-id="9e48e-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="9e48e-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="9e48e-123">Timeout</span></span> | <span data-ttu-id="9e48e-124">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="9e48e-124">10 minutes</span></span> | <span data-ttu-id="9e48e-125">每個查詢</span><span class="sxs-lookup"><span data-stu-id="9e48e-125">Every query</span></span> | <span data-ttu-id="9e48e-126">每個查詢可長達10分鐘執行一次。</span><span class="sxs-lookup"><span data-stu-id="9e48e-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="9e48e-127">若未在10分鐘內完成，則服務會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="9e48e-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="9e48e-128">CPU 資源</span><span class="sxs-lookup"><span data-stu-id="9e48e-128">CPU resources</span></span> | <span data-ttu-id="9e48e-129">根據租使用者規模</span><span class="sxs-lookup"><span data-stu-id="9e48e-129">Based on tenant size</span></span> | <span data-ttu-id="9e48e-130">-在每小時，然後每隔15分鐘</span><span class="sxs-lookup"><span data-stu-id="9e48e-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="9e48e-131">-每日12午夜</span><span class="sxs-lookup"><span data-stu-id="9e48e-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="9e48e-132">服務會分別強制執行每日和15分鐘的配額。</span><span class="sxs-lookup"><span data-stu-id="9e48e-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="9e48e-133">針對每個配額，當查詢執行且租使用者已使用超過10% 的已分派資源 [時，門戶會顯示錯誤](advanced-hunting-errors.md) 。</span><span class="sxs-lookup"><span data-stu-id="9e48e-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="9e48e-134">如果租使用者已到達100%，直到下一天或15分鐘週期之後，才會封鎖查詢。</span><span class="sxs-lookup"><span data-stu-id="9e48e-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="9e48e-135">個別的配額和參數集適用于透過 API 執行的高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="9e48e-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="9e48e-136">閱讀高級搜尋 APIs</span><span class="sxs-lookup"><span data-stu-id="9e48e-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="9e48e-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="9e48e-137">Related topics</span></span>

- [<span data-ttu-id="9e48e-138">高級搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="9e48e-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="9e48e-139">處理高級搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="9e48e-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="9e48e-140">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="9e48e-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e48e-141">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="9e48e-141">Custom detections overview</span></span>](custom-detections-overview.md)