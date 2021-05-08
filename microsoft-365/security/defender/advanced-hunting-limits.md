---
title: Microsoft 365 Defender 中的高級搜尋配額和使用參數
description: '瞭解各種配額和使用參數 (服務限制可讓高級搜尋服務保持回應的) '
keywords: 「高級搜尋」、「威脅搜尋」、「網路威脅搜尋」、「Microsoft 365 Defender」、Microsoft 365、m365、搜尋、查詢、遙測、架構、kusto、CPU 限制、查詢限制、資源、最大結果、配額、參數、配置
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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245597"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="42ab0-104">高級搜尋配額和使用參數</span><span class="sxs-lookup"><span data-stu-id="42ab0-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="42ab0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="42ab0-105">**Applies to:**</span></span>
- <span data-ttu-id="42ab0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42ab0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="42ab0-107">為了讓服務具有高性能和回應能力，「高級搜尋」會設定各種配額和使用參數 (也稱為「服務限制」 ) 。</span><span class="sxs-lookup"><span data-stu-id="42ab0-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="42ab0-108">這些配額和參數會獨立套用，以手動方式執行查詢，並使用 [自訂偵測規則](custom-detection-rules.md)執行查詢。</span><span class="sxs-lookup"><span data-stu-id="42ab0-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="42ab0-109">定期執行多個查詢的客戶應注意這些限制，並套用 [優化的最佳作法](advanced-hunting-best-practices.md) ，以盡可能減少中斷。</span><span class="sxs-lookup"><span data-stu-id="42ab0-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="42ab0-110">請參閱下表以瞭解現有的配額和使用參數。</span><span class="sxs-lookup"><span data-stu-id="42ab0-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="42ab0-111">Quota 或參數</span><span class="sxs-lookup"><span data-stu-id="42ab0-111">Quota or parameter</span></span> | <span data-ttu-id="42ab0-112">Size</span><span class="sxs-lookup"><span data-stu-id="42ab0-112">Size</span></span> | <span data-ttu-id="42ab0-113">重新整理週期</span><span class="sxs-lookup"><span data-stu-id="42ab0-113">Refresh cycle</span></span> | <span data-ttu-id="42ab0-114">描述</span><span class="sxs-lookup"><span data-stu-id="42ab0-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="42ab0-115">資料範圍</span><span class="sxs-lookup"><span data-stu-id="42ab0-115">Data range</span></span> | <span data-ttu-id="42ab0-116">30 天</span><span class="sxs-lookup"><span data-stu-id="42ab0-116">30 days</span></span> | <span data-ttu-id="42ab0-117">每個查詢</span><span class="sxs-lookup"><span data-stu-id="42ab0-117">Every query</span></span> | <span data-ttu-id="42ab0-118">每個查詢都可以查詢過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="42ab0-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="42ab0-119">結果集</span><span class="sxs-lookup"><span data-stu-id="42ab0-119">Result set</span></span> | <span data-ttu-id="42ab0-120">10000列</span><span class="sxs-lookup"><span data-stu-id="42ab0-120">10,000 rows</span></span> | <span data-ttu-id="42ab0-121">每個查詢</span><span class="sxs-lookup"><span data-stu-id="42ab0-121">Every query</span></span> | <span data-ttu-id="42ab0-122">每個查詢最多可以傳回10000筆記錄。</span><span class="sxs-lookup"><span data-stu-id="42ab0-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="42ab0-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="42ab0-123">Timeout</span></span> | <span data-ttu-id="42ab0-124">10 分鐘</span><span class="sxs-lookup"><span data-stu-id="42ab0-124">10 minutes</span></span> | <span data-ttu-id="42ab0-125">每個查詢</span><span class="sxs-lookup"><span data-stu-id="42ab0-125">Every query</span></span> | <span data-ttu-id="42ab0-126">每個查詢可長達10分鐘執行一次。</span><span class="sxs-lookup"><span data-stu-id="42ab0-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="42ab0-127">若未在10分鐘內完成，則服務會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="42ab0-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="42ab0-128">CPU 資源</span><span class="sxs-lookup"><span data-stu-id="42ab0-128">CPU resources</span></span> | <span data-ttu-id="42ab0-129">根據租使用者規模</span><span class="sxs-lookup"><span data-stu-id="42ab0-129">Based on tenant size</span></span> | <span data-ttu-id="42ab0-130">每 15 分鐘</span><span class="sxs-lookup"><span data-stu-id="42ab0-130">Every 15 minutes</span></span> | <span data-ttu-id="42ab0-131">每當查詢執行且租使用者佔用10% 的已分配資源時， [門戶會顯示錯誤](advanced-hunting-errors.md) 。</span><span class="sxs-lookup"><span data-stu-id="42ab0-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="42ab0-132">如果租使用者到達100%，直到接下來的15分鐘週期過後，便會封鎖查詢。</span><span class="sxs-lookup"><span data-stu-id="42ab0-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="42ab0-133">個別的配額和參數集適用于透過 API 執行的高級搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="42ab0-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="42ab0-134">閱讀高級搜尋 APIs</span><span class="sxs-lookup"><span data-stu-id="42ab0-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="42ab0-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="42ab0-135">Related topics</span></span>

- [<span data-ttu-id="42ab0-136">高級搜尋最佳作法</span><span class="sxs-lookup"><span data-stu-id="42ab0-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="42ab0-137">處理高級搜尋錯誤</span><span class="sxs-lookup"><span data-stu-id="42ab0-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="42ab0-138">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="42ab0-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="42ab0-139">自訂偵測概觀</span><span class="sxs-lookup"><span data-stu-id="42ab0-139">Custom detections overview</span></span>](custom-detections-overview.md)