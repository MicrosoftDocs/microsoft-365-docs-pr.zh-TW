---
title: 進階搜捕結構描述中的 AlertEvents 表格
description: 了解進階搜捕結構描述之 AlertEvents 表格中的警示產生事件
keywords: 狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 alertevents、 進階警示，在高的嚴重性等級類別
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 02a3f50019321f68390d3eb9b76576f4e6dfdd8a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602770"
---
# <a name="alertevents"></a><span data-ttu-id="7ef4c-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="7ef4c-104">AlertEvents</span></span>

<span data-ttu-id="7ef4c-105">**適用範圍：**</span><span class="sxs-lookup"><span data-stu-id="7ef4c-105">**Applies to:**</span></span>
- <span data-ttu-id="7ef4c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="7ef4c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7ef4c-107">[進階搜捕](advanced-hunting-overview.md)結構描述中的 `AlertEvents` 表格包含有關 Microsoft Defender ATP 警示的資訊。</span><span class="sxs-lookup"><span data-stu-id="7ef4c-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="7ef4c-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="7ef4c-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7ef4c-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="7ef4c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7ef4c-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="7ef4c-110">Column name</span></span> | <span data-ttu-id="7ef4c-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="7ef4c-111">Data type</span></span> | <span data-ttu-id="7ef4c-112">描述</span><span class="sxs-lookup"><span data-stu-id="7ef4c-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="7ef4c-113">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-113">string</span></span> | <span data-ttu-id="7ef4c-114">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7ef4c-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="7ef4c-115">datetime</span><span class="sxs-lookup"><span data-stu-id="7ef4c-115">datetime</span></span> | <span data-ttu-id="7ef4c-116">事件記錄的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="7ef4c-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7ef4c-117">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-117">string</span></span> | <span data-ttu-id="7ef4c-118">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="7ef4c-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7ef4c-119">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-119">string</span></span> | <span data-ttu-id="7ef4c-120">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="7ef4c-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="7ef4c-121">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-121">string</span></span> | <span data-ttu-id="7ef4c-122">表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低)</span><span class="sxs-lookup"><span data-stu-id="7ef4c-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="7ef4c-123">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-123">string</span></span> | <span data-ttu-id="7ef4c-124">輸入由警示所識別的威脅指示器或入侵活動類型</span><span class="sxs-lookup"><span data-stu-id="7ef4c-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="7ef4c-125">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-125">string</span></span> | <span data-ttu-id="7ef4c-126">警示標題</span><span class="sxs-lookup"><span data-stu-id="7ef4c-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="7ef4c-127">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-127">string</span></span> | <span data-ttu-id="7ef4c-128">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="7ef4c-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="7ef4c-129">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-129">string</span></span> | <span data-ttu-id="7ef4c-130">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="7ef4c-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="7ef4c-131">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-131">string</span></span> | <span data-ttu-id="7ef4c-132">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="7ef4c-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="7ef4c-133">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-133">string</span></span> | <span data-ttu-id="7ef4c-134">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7ef4c-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="7ef4c-135">long</span><span class="sxs-lookup"><span data-stu-id="7ef4c-135">long</span></span> | <span data-ttu-id="7ef4c-136">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="7ef4c-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7ef4c-137">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="7ef4c-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="7ef4c-138">字串</span><span class="sxs-lookup"><span data-stu-id="7ef4c-138">string</span></span> | <span data-ttu-id="7ef4c-139">含有事件詳細資料的表格</span><span class="sxs-lookup"><span data-stu-id="7ef4c-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7ef4c-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="7ef4c-140">Related topics</span></span>
- [<span data-ttu-id="7ef4c-141">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="7ef4c-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7ef4c-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="7ef4c-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7ef4c-143">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="7ef4c-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7ef4c-144">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="7ef4c-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7ef4c-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="7ef4c-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7ef4c-146">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="7ef4c-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
