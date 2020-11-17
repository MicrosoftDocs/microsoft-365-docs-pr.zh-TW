---
title: Advanced 搜尋架構中的 CloudAppEvents 表格
description: 深入瞭解高級搜尋架構之 CloudAppEvents 資料表中 cloud apps and service 的事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，CloudAppEvents，Cloud App Security，MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087761"
---
# <a name="cloudappevents"></a><span data-ttu-id="f5bbe-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="f5bbe-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5bbe-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="f5bbe-105">**Applies to:**</span></span>
- <span data-ttu-id="f5bbe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5bbe-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f5bbe-107">目前在預覽中， `CloudAppEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含各種雲端應用程式和服務中的活動相關資訊，特別是 Microsoft 團隊和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="f5bbe-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f5bbe-109">此表格會展開以包含 Microsoft Cloud App Security 監控的更多活動。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="f5bbe-110">最後，此表格會包含目前儲存在 [AppFileEvents](advanced-hunting-appfileevents-table.md) 資料表中的檔案活動。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="f5bbe-111">當更多資料移至此表格時，Microsoft 會提供額外的指導方針。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="f5bbe-112">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f5bbe-113">欄名稱</span><span class="sxs-lookup"><span data-stu-id="f5bbe-113">Column name</span></span> | <span data-ttu-id="f5bbe-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="f5bbe-114">Data type</span></span> | <span data-ttu-id="f5bbe-115">描述</span><span class="sxs-lookup"><span data-stu-id="f5bbe-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f5bbe-116">datetime</span><span class="sxs-lookup"><span data-stu-id="f5bbe-116">datetime</span></span> | <span data-ttu-id="f5bbe-117">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="f5bbe-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f5bbe-118">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-118">string</span></span> | <span data-ttu-id="f5bbe-119">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="f5bbe-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="f5bbe-120">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-120">string</span></span> | <span data-ttu-id="f5bbe-121">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="f5bbe-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="f5bbe-122">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-122">string</span></span> | <span data-ttu-id="f5bbe-123">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f5bbe-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="f5bbe-124">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-124">string</span></span> | <span data-ttu-id="f5bbe-125">Azure Active Directory 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f5bbe-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f5bbe-126">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-126">string</span></span> | <span data-ttu-id="f5bbe-127">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f5bbe-128">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="f5bbe-129">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-129">string</span></span> | <span data-ttu-id="f5bbe-130">指出活動是否由系統管理員執行</span><span class="sxs-lookup"><span data-stu-id="f5bbe-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="f5bbe-131">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-131">string</span></span> | <span data-ttu-id="f5bbe-132">根據用途及功能的裝置類型，例如「網路裝置」、「工作站」、「伺服器」、「Mobile」、「遊戲主控台」或「印表機」。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="f5bbe-133">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-133">string</span></span> | <span data-ttu-id="f5bbe-134">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f5bbe-135">此欄會指出特定的作業系統，包括相同系列內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="f5bbe-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="f5bbe-136">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-136">string</span></span> | <span data-ttu-id="f5bbe-137">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="f5bbe-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="f5bbe-138">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-138">string</span></span> | <span data-ttu-id="f5bbe-139">指出 IP 位址是否屬於已知的匿名 proxy</span><span class="sxs-lookup"><span data-stu-id="f5bbe-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="f5bbe-140">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-140">string</span></span> | <span data-ttu-id="f5bbe-141">兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區</span><span class="sxs-lookup"><span data-stu-id="f5bbe-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="f5bbe-142">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-142">string</span></span> | <span data-ttu-id="f5bbe-143">用戶端 IP 位址為 geolocated 的城市</span><span class="sxs-lookup"><span data-stu-id="f5bbe-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="f5bbe-144">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-144">string</span></span> | <span data-ttu-id="f5bbe-145">網際網路服務提供者 (與 IP 位址相關聯的 ISP) </span><span class="sxs-lookup"><span data-stu-id="f5bbe-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="f5bbe-146">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-146">string</span></span> | <span data-ttu-id="f5bbe-147">來自網頁瀏覽器或其他用戶端應用程式的使用者代理程式資訊</span><span class="sxs-lookup"><span data-stu-id="f5bbe-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="f5bbe-148">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-148">string</span></span> | <span data-ttu-id="f5bbe-149">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="f5bbe-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="f5bbe-150">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-150">string</span></span> | <span data-ttu-id="f5bbe-151">錄製的活動中所涉及的物件（例如檔案或資料夾）的清單</span><span class="sxs-lookup"><span data-stu-id="f5bbe-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="f5bbe-152">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-152">string</span></span> | <span data-ttu-id="f5bbe-153">已錄製動作套用至之物件的名稱</span><span class="sxs-lookup"><span data-stu-id="f5bbe-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="f5bbe-154">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-154">string</span></span> | <span data-ttu-id="f5bbe-155">錄製的動作所套用的物件類型，例如檔案或資料夾</span><span class="sxs-lookup"><span data-stu-id="f5bbe-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="f5bbe-156">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-156">string</span></span> | <span data-ttu-id="f5bbe-157">套用錄製動作之物件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f5bbe-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="f5bbe-158">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-158">string</span></span> | <span data-ttu-id="f5bbe-159">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f5bbe-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="f5bbe-160">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-160">string</span></span> | <span data-ttu-id="f5bbe-161">來源應用程式或服務中 JSON 格式的原始事件資訊</span><span class="sxs-lookup"><span data-stu-id="f5bbe-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="f5bbe-162">string</span><span class="sxs-lookup"><span data-stu-id="f5bbe-162">string</span></span> | <span data-ttu-id="f5bbe-163">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="f5bbe-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f5bbe-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="f5bbe-164">Related topics</span></span>
- [<span data-ttu-id="f5bbe-165">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="f5bbe-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5bbe-166">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="f5bbe-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f5bbe-167">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="f5bbe-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f5bbe-168">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="f5bbe-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f5bbe-169">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="f5bbe-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f5bbe-170">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="f5bbe-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
