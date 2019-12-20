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
ms.openlocfilehash: ee14dcc1c2ae0a2bc6fa3c094d757441515f00de
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807012"
---
# <a name="alertevents"></a><span data-ttu-id="a9000-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="a9000-104">AlertEvents</span></span>

<span data-ttu-id="a9000-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="a9000-105">**Applies to:**</span></span>
- <span data-ttu-id="a9000-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a9000-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a9000-107">[進階搜捕](advanced-hunting-overview.md)結構描述中的 `AlertEvents` 表格包含有關 Microsoft Defender ATP 警示的資訊。</span><span class="sxs-lookup"><span data-stu-id="a9000-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="a9000-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="a9000-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a9000-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="a9000-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a9000-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="a9000-110">Column name</span></span> | <span data-ttu-id="a9000-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="a9000-111">Data type</span></span> | <span data-ttu-id="a9000-112">描述</span><span class="sxs-lookup"><span data-stu-id="a9000-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="a9000-113">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-113">string</span></span> | <span data-ttu-id="a9000-114">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a9000-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="a9000-115">datetime</span><span class="sxs-lookup"><span data-stu-id="a9000-115">datetime</span></span> | <span data-ttu-id="a9000-116">事件記錄的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a9000-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a9000-117">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-117">string</span></span> | <span data-ttu-id="a9000-118">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="a9000-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a9000-119">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-119">string</span></span> | <span data-ttu-id="a9000-120">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a9000-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="a9000-121">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-121">string</span></span> | <span data-ttu-id="a9000-122">表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低)</span><span class="sxs-lookup"><span data-stu-id="a9000-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="a9000-123">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-123">string</span></span> | <span data-ttu-id="a9000-124">輸入由警示所識別的威脅指示器或入侵活動類型</span><span class="sxs-lookup"><span data-stu-id="a9000-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="a9000-125">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-125">string</span></span> | <span data-ttu-id="a9000-126">警示標題</span><span class="sxs-lookup"><span data-stu-id="a9000-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="a9000-127">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-127">string</span></span> | <span data-ttu-id="a9000-128">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="a9000-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="a9000-129">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-129">string</span></span> | <span data-ttu-id="a9000-130">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="a9000-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="a9000-131">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-131">string</span></span> | <span data-ttu-id="a9000-132">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="a9000-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="a9000-133">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-133">string</span></span> | <span data-ttu-id="a9000-134">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a9000-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="a9000-135">long</span><span class="sxs-lookup"><span data-stu-id="a9000-135">long</span></span> | <span data-ttu-id="a9000-136">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="a9000-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a9000-137">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="a9000-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="a9000-138">字串</span><span class="sxs-lookup"><span data-stu-id="a9000-138">string</span></span> | <span data-ttu-id="a9000-139">含有事件詳細資料的表格</span><span class="sxs-lookup"><span data-stu-id="a9000-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a9000-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="a9000-140">Related topics</span></span>
- [<span data-ttu-id="a9000-141">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="a9000-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a9000-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="a9000-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a9000-143">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="a9000-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a9000-144">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="a9000-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a9000-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="a9000-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a9000-146">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="a9000-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
