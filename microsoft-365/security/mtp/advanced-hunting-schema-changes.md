---
title: Microsoft 365 Defender advanced 搜尋架構中的命名變更
description: 追蹤和審閱高級搜尋架構中的命名變更表格和欄
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、資料、命名變更、重新命名、Microsoft 威脅防護
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
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780784"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="b2451-104">高級搜尋架構命名變更</span><span class="sxs-lookup"><span data-stu-id="b2451-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2451-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="b2451-105">**Applies to:**</span></span>
- <span data-ttu-id="b2451-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2451-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b2451-107">「 [高級搜尋」架構](advanced-hunting-schema-tables.md) 會定期更新，以加入新的資料表和欄。</span><span class="sxs-lookup"><span data-stu-id="b2451-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="b2451-108">在某些情況下，會重新命名或取代現有的欄名，以提升使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="b2451-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="b2451-109">請參閱本文，以複查可能影響查詢的命名變更。</span><span class="sxs-lookup"><span data-stu-id="b2451-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="b2451-110">命名變更會自動套用至儲存在 [安全性中心] 中的查詢，包括自訂偵測規則所使用的查詢。</span><span class="sxs-lookup"><span data-stu-id="b2451-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="b2451-111">您不需要手動更新這些查詢。</span><span class="sxs-lookup"><span data-stu-id="b2451-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="b2451-112">不過，您將需要更新下列查詢：</span><span class="sxs-lookup"><span data-stu-id="b2451-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="b2451-113">使用 API 執行的查詢</span><span class="sxs-lookup"><span data-stu-id="b2451-113">Queries that are run using the API</span></span>
- <span data-ttu-id="b2451-114">儲存在安全性中心以外其他位置的查詢</span><span class="sxs-lookup"><span data-stu-id="b2451-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="b2451-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="b2451-115">December 2020</span></span>

| <span data-ttu-id="b2451-116">表格名稱</span><span class="sxs-lookup"><span data-stu-id="b2451-116">Table name</span></span> | <span data-ttu-id="b2451-117">原始欄名稱</span><span class="sxs-lookup"><span data-stu-id="b2451-117">Original column name</span></span> | <span data-ttu-id="b2451-118">新欄名稱</span><span class="sxs-lookup"><span data-stu-id="b2451-118">New column name</span></span> | <span data-ttu-id="b2451-119">變更的原因</span><span class="sxs-lookup"><span data-stu-id="b2451-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="b2451-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="b2451-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="b2451-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="b2451-121">FinalEmailAction</span></span> | <span data-ttu-id="b2451-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="b2451-122">EmailAction</span></span> | <span data-ttu-id="b2451-123">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="b2451-123">Customer feedback</span></span> |
| [<span data-ttu-id="b2451-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="b2451-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="b2451-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="b2451-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="b2451-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="b2451-126">EmailActionPolicy</span></span> | <span data-ttu-id="b2451-127">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="b2451-127">Customer feedback</span></span> |
| [<span data-ttu-id="b2451-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="b2451-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="b2451-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="b2451-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="b2451-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="b2451-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="b2451-131">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="b2451-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b2451-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2451-132">Related topics</span></span>
- [<span data-ttu-id="b2451-133">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="b2451-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b2451-134">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="b2451-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)