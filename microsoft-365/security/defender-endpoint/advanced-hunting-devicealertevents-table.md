---
title: Advanced 搜尋架構中的 DeviceAlertEvents 表格
description: 深入瞭解高級搜尋架構的 DeviceAlertEvents 資料表中的警示產生事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，mdatp，microsoft defender atp，microsoft defender for endpoint，wdatp search，查詢，遙測，schema reference，kusto，table，column，data type，description，DeviceAlertEvents，alert，嚴重性，category
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939645"
---
# <a name="devicealertevents"></a><span data-ttu-id="6a6f6-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="6a6f6-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a6f6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6a6f6-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a6f6-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6a6f6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="6a6f6-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6a6f6-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a6f6-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6a6f6-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="6a6f6-109">[！附注] `DeviceAlertEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含 Microsoft Defender Security Center 中警示的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6a6f6-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6a6f6-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="6a6f6-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6a6f6-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="6a6f6-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="6a6f6-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="6a6f6-112">Column name</span></span> | <span data-ttu-id="6a6f6-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="6a6f6-113">Data type</span></span> | <span data-ttu-id="6a6f6-114">描述</span><span class="sxs-lookup"><span data-stu-id="6a6f6-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="6a6f6-115">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-115">string</span></span> | <span data-ttu-id="6a6f6-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="6a6f6-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="6a6f6-117">datetime</span><span class="sxs-lookup"><span data-stu-id="6a6f6-117">datetime</span></span> | <span data-ttu-id="6a6f6-118">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="6a6f6-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6a6f6-119">string</span><span class="sxs-lookup"><span data-stu-id="6a6f6-119">string</span></span> | <span data-ttu-id="6a6f6-120">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6a6f6-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6a6f6-121">string</span><span class="sxs-lookup"><span data-stu-id="6a6f6-121">string</span></span> | <span data-ttu-id="6a6f6-122">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="6a6f6-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="6a6f6-123">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-123">string</span></span> | <span data-ttu-id="6a6f6-124">表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低)</span><span class="sxs-lookup"><span data-stu-id="6a6f6-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="6a6f6-125">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-125">string</span></span> | <span data-ttu-id="6a6f6-126">輸入由警示所識別的威脅指示器或入侵活動類型</span><span class="sxs-lookup"><span data-stu-id="6a6f6-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="6a6f6-127">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-127">string</span></span> | <span data-ttu-id="6a6f6-128">警示標題</span><span class="sxs-lookup"><span data-stu-id="6a6f6-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="6a6f6-129">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-129">string</span></span> | <span data-ttu-id="6a6f6-130">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="6a6f6-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="6a6f6-131">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-131">string</span></span> | <span data-ttu-id="6a6f6-132">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="6a6f6-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="6a6f6-133">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-133">string</span></span> | <span data-ttu-id="6a6f6-134">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="6a6f6-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="6a6f6-135">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-135">string</span></span> | <span data-ttu-id="6a6f6-136">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6a6f6-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="6a6f6-137">string</span><span class="sxs-lookup"><span data-stu-id="6a6f6-137">string</span></span> | <span data-ttu-id="6a6f6-138">MITRE ATT&與觸發警示之活動相關聯的 CK 技術</span><span class="sxs-lookup"><span data-stu-id="6a6f6-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="6a6f6-139">long</span><span class="sxs-lookup"><span data-stu-id="6a6f6-139">long</span></span> | <span data-ttu-id="6a6f6-140">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="6a6f6-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6a6f6-141">若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用</span><span class="sxs-lookup"><span data-stu-id="6a6f6-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="6a6f6-142">字串</span><span class="sxs-lookup"><span data-stu-id="6a6f6-142">string</span></span> | <span data-ttu-id="6a6f6-143">含有事件詳細資料的表格</span><span class="sxs-lookup"><span data-stu-id="6a6f6-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6a6f6-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="6a6f6-144">Related topics</span></span>
- [<span data-ttu-id="6a6f6-145">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="6a6f6-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6a6f6-146">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="6a6f6-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6a6f6-147">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="6a6f6-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
