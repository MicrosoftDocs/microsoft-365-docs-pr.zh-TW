---
title: 進階搜捕結構描述中的 AlertEvents 表格
description: 了解進階搜捕結構描述之 AlertEvents 表格中的警示產生事件
keywords: 進階搜捕、威脅搜捕、網路威脅搜捕、搜尋、查詢、遙測、結構描述參考、kusto、表格、欄、資料類型、描述、alertevents、警示、嚴重性、類別
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910921"
---
# <a name="alertevents"></a><span data-ttu-id="e1e48-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="e1e48-104">AlertEvents</span></span>

<span data-ttu-id="e1e48-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="e1e48-105">**Applies to:**</span></span>
- <span data-ttu-id="e1e48-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="e1e48-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="e1e48-107">[進階搜捕](advanced-hunting-overview.md)結構描述中的 `AlertEvents` 表格包含有關 Microsoft Defender ATP 警示的資訊。</span><span class="sxs-lookup"><span data-stu-id="e1e48-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="e1e48-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="e1e48-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e1e48-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="e1e48-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e1e48-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="e1e48-110">Column name</span></span> | <span data-ttu-id="e1e48-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="e1e48-111">Data type</span></span> | <span data-ttu-id="e1e48-112">描述</span><span class="sxs-lookup"><span data-stu-id="e1e48-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="e1e48-113">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-113">string</span></span> | <span data-ttu-id="e1e48-114">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e1e48-114">Unique identifier for the bucket.</span></span> |
| `EventTime` | <span data-ttu-id="e1e48-115">datetime</span><span class="sxs-lookup"><span data-stu-id="e1e48-115">DateTime</span></span> | <span data-ttu-id="e1e48-116">事件記錄的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="e1e48-116">Date and time when the event was recorded</span></span> |
| `MachineId` | <span data-ttu-id="e1e48-117">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-117">string</span></span> | <span data-ttu-id="e1e48-118">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e1e48-118">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="e1e48-119">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-119">string</span></span> | <span data-ttu-id="e1e48-120">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e1e48-120">Fully qualified domain name (FQDN) of the pool</span></span> |
| `Severity` | <span data-ttu-id="e1e48-121">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-121">string</span></span> | <span data-ttu-id="e1e48-122">表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低)</span><span class="sxs-lookup"><span data-stu-id="e1e48-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="e1e48-123">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-123">string</span></span> | <span data-ttu-id="e1e48-124">輸入由警示所識別的威脅指示器或入侵活動類型</span><span class="sxs-lookup"><span data-stu-id="e1e48-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="e1e48-125">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-125">string</span></span> | <span data-ttu-id="e1e48-126">警示標題</span><span class="sxs-lookup"><span data-stu-id="e1e48-126">Title of the alert.</span></span> |
| `FileName` | <span data-ttu-id="e1e48-127">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-127">string</span></span> | <span data-ttu-id="e1e48-128">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="e1e48-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="e1e48-129">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-129">string</span></span> | <span data-ttu-id="e1e48-130">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="e1e48-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="e1e48-131">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-131">string</span></span> | <span data-ttu-id="e1e48-132">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e1e48-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="e1e48-133">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-133">string</span></span> | <span data-ttu-id="e1e48-134">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e1e48-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="e1e48-135">long</span><span class="sxs-lookup"><span data-stu-id="e1e48-135">long</span></span> | <span data-ttu-id="e1e48-136">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="e1e48-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e1e48-137">若要識別唯一事件，此欄必須與 ComputerName 和 EventTime 欄搭配使用</span><span class="sxs-lookup"><span data-stu-id="e1e48-137">To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns</span></span> |
| `Table` | <span data-ttu-id="e1e48-138">字串</span><span class="sxs-lookup"><span data-stu-id="e1e48-138">string</span></span> | <span data-ttu-id="e1e48-139">含有事件詳細資料的表格</span><span class="sxs-lookup"><span data-stu-id="e1e48-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e1e48-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="e1e48-140">Related topics</span></span>
- [<span data-ttu-id="e1e48-141">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="e1e48-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e1e48-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="e1e48-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e1e48-143">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="e1e48-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e1e48-144">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="e1e48-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e1e48-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="e1e48-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e1e48-146">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="e1e48-146">Apply design best practices.</span></span>](advanced-hunting-best-practices.md)
