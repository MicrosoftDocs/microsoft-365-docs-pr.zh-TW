---
title: Advanced 搜尋架構中的 DeviceAlertEvents 表格
description: 深入瞭解高級搜尋架構的 DeviceAlertEvents 資料表中的警示產生事件
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、mdatp、microsoft defender atp、wdatp 搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、DeviceAlertEvents、警示、嚴重性、類別
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
ms.openlocfilehash: 66ecdc8fbcde04d78f2deede5f4e296a7f051ef0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499167"
---
# <a name="devicealertevents"></a><span data-ttu-id="377a5-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="377a5-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="377a5-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="377a5-105">**Applies to:**</span></span>
- [<span data-ttu-id="377a5-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="377a5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="377a5-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="377a5-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="377a5-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="377a5-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="377a5-109">[！附注] `DeviceAlertEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含 Microsoft Defender Security Center 中警示的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="377a5-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="377a5-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="377a5-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="377a5-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="377a5-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="377a5-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="377a5-112">Column name</span></span> | <span data-ttu-id="377a5-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="377a5-113">Data type</span></span> | <span data-ttu-id="377a5-114">描述</span><span class="sxs-lookup"><span data-stu-id="377a5-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="377a5-115">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-115">string</span></span> | <span data-ttu-id="377a5-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="377a5-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="377a5-117">datetime</span><span class="sxs-lookup"><span data-stu-id="377a5-117">datetime</span></span> | <span data-ttu-id="377a5-118">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="377a5-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="377a5-119">string</span><span class="sxs-lookup"><span data-stu-id="377a5-119">string</span></span> | <span data-ttu-id="377a5-120">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="377a5-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="377a5-121">string</span><span class="sxs-lookup"><span data-stu-id="377a5-121">string</span></span> | <span data-ttu-id="377a5-122">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="377a5-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="377a5-123">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-123">string</span></span> | <span data-ttu-id="377a5-124">表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低)</span><span class="sxs-lookup"><span data-stu-id="377a5-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="377a5-125">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-125">string</span></span> | <span data-ttu-id="377a5-126">輸入由警示所識別的威脅指示器或入侵活動類型</span><span class="sxs-lookup"><span data-stu-id="377a5-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="377a5-127">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-127">string</span></span> | <span data-ttu-id="377a5-128">警示標題</span><span class="sxs-lookup"><span data-stu-id="377a5-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="377a5-129">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-129">string</span></span> | <span data-ttu-id="377a5-130">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="377a5-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="377a5-131">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-131">string</span></span> | <span data-ttu-id="377a5-132">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="377a5-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="377a5-133">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-133">string</span></span> | <span data-ttu-id="377a5-134">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="377a5-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="377a5-135">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-135">string</span></span> | <span data-ttu-id="377a5-136">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="377a5-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="377a5-137">string</span><span class="sxs-lookup"><span data-stu-id="377a5-137">string</span></span> | <span data-ttu-id="377a5-138">MITRE ATT&與觸發警示之活動相關聯的 CK 技術</span><span class="sxs-lookup"><span data-stu-id="377a5-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="377a5-139">long</span><span class="sxs-lookup"><span data-stu-id="377a5-139">long</span></span> | <span data-ttu-id="377a5-140">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="377a5-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="377a5-141">若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用</span><span class="sxs-lookup"><span data-stu-id="377a5-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="377a5-142">字串</span><span class="sxs-lookup"><span data-stu-id="377a5-142">string</span></span> | <span data-ttu-id="377a5-143">含有事件詳細資料的表格</span><span class="sxs-lookup"><span data-stu-id="377a5-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="377a5-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="377a5-144">Related topics</span></span>
- [<span data-ttu-id="377a5-145">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="377a5-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="377a5-146">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="377a5-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="377a5-147">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="377a5-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
