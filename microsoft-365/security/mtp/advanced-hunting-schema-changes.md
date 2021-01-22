---
title: Microsoft 365 Defender 進位搜尋架構中的命名變更
description: 追蹤及檢查進位搜尋架構中的資料表和欄的命名變更
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料、資料、命名變更、重新命名、Microsoft 威脅防護
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
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932199"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="16624-104">進位搜尋架構 - 命名變更</span><span class="sxs-lookup"><span data-stu-id="16624-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="16624-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="16624-105">**Applies to:**</span></span>
- <span data-ttu-id="16624-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16624-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="16624-107">進 [位搜尋架構](advanced-hunting-schema-tables.md) 會定期更新，以新增資料表和欄。</span><span class="sxs-lookup"><span data-stu-id="16624-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="16624-108">在某些情況下，會重新命名或取代現有的資料行名稱，以改善使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="16624-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="16624-109">請參閱這篇文章，以檢查可能會影響查詢的命名變更。</span><span class="sxs-lookup"><span data-stu-id="16624-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="16624-110">命名變更會自動適用于儲存于安全性中心的查詢，包括自訂偵測規則使用的查詢。</span><span class="sxs-lookup"><span data-stu-id="16624-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="16624-111">您不一樣需要手動更新這些查詢。</span><span class="sxs-lookup"><span data-stu-id="16624-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="16624-112">不過，您必須更新下列查詢：</span><span class="sxs-lookup"><span data-stu-id="16624-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="16624-113">使用 API 執行查詢</span><span class="sxs-lookup"><span data-stu-id="16624-113">Queries that are run using the API</span></span>
- <span data-ttu-id="16624-114">儲存于資訊安全中心以外位置的查詢</span><span class="sxs-lookup"><span data-stu-id="16624-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="16624-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="16624-115">December 2020</span></span>

| <span data-ttu-id="16624-116">表格名稱</span><span class="sxs-lookup"><span data-stu-id="16624-116">Table name</span></span> | <span data-ttu-id="16624-117">原始欄名稱</span><span class="sxs-lookup"><span data-stu-id="16624-117">Original column name</span></span> | <span data-ttu-id="16624-118">新增欄名稱</span><span class="sxs-lookup"><span data-stu-id="16624-118">New column name</span></span> | <span data-ttu-id="16624-119">變更原因</span><span class="sxs-lookup"><span data-stu-id="16624-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="16624-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="16624-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="16624-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="16624-121">FinalEmailAction</span></span> | <span data-ttu-id="16624-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="16624-122">EmailAction</span></span> | <span data-ttu-id="16624-123">客戶意見回饋</span><span class="sxs-lookup"><span data-stu-id="16624-123">Customer feedback</span></span> |
| [<span data-ttu-id="16624-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="16624-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="16624-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="16624-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="16624-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="16624-126">EmailActionPolicy</span></span> | <span data-ttu-id="16624-127">客戶意見回饋</span><span class="sxs-lookup"><span data-stu-id="16624-127">Customer feedback</span></span> |
| [<span data-ttu-id="16624-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="16624-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="16624-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="16624-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="16624-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="16624-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="16624-131">客戶意見回饋</span><span class="sxs-lookup"><span data-stu-id="16624-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="16624-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="16624-132">Related topics</span></span>
- [<span data-ttu-id="16624-133">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="16624-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="16624-134">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="16624-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)