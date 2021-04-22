---
title: Advanced 搜尋架構中的 AppFileEvents 表格
description: 深入瞭解在高級搜尋架構的 AppFileEvents 資料表中，與雲端 app 和服務相關聯的檔案相關事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，microsoft 365，m365，search，query，遙測，schema reference，kusto，table，欄，資料類型，描述，AppFileEvents，Cloud App Security，MCAS
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
ms.openlocfilehash: 861a04eb168190f2bb64bbb0258de6767c619e1b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934714"
---
# <a name="appfileevents"></a><span data-ttu-id="db52e-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="db52e-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="db52e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="db52e-105">**Applies to:**</span></span>
- <span data-ttu-id="db52e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db52e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="db52e-107">[！附注] `AppFileEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含雲端 app 和服務中由 Microsoft cloud App Security 監控之檔案相關活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db52e-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="db52e-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="db52e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!WARNING]
><span data-ttu-id="db52e-109">此表格即將停用。</span><span class="sxs-lookup"><span data-stu-id="db52e-109">This table will be retired soon.</span></span> <span data-ttu-id="db52e-110">從2021年3月7日直到 `AppFileEvents` 資料表不再記錄記錄。</span><span class="sxs-lookup"><span data-stu-id="db52e-110">As of March 7, 2021, the `AppFileEvents` table is no longer logging records.</span></span> <span data-ttu-id="db52e-111">使用者在所說的日期以外的雲端服務中搜尋與檔案相關的活動，應改為使用 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 表格。</span><span class="sxs-lookup"><span data-stu-id="db52e-111">Users hunting through file-related activities in cloud services on and beyond the said date should use the [CloudAppEvents](advanced-hunting-cloudappevents-table.md) table instead.</span></span> <br><br><span data-ttu-id="db52e-112">請務必搜尋查詢和自訂偵測規則，該規則仍會使用 `AppFileEvents` 該表，並進行編輯，以使用 `CloudAppEvents` 該表。</span><span class="sxs-lookup"><span data-stu-id="db52e-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="db52e-113">若要瞭解轉換受影響查詢的相關指引，請參閱 [使用 Microsoft 365 Defender advanced 搜尋跨 cloud app Activity 搜尋](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。</span><span class="sxs-lookup"><span data-stu-id="db52e-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="db52e-114">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="db52e-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="db52e-115">欄名稱</span><span class="sxs-lookup"><span data-stu-id="db52e-115">Column name</span></span> | <span data-ttu-id="db52e-116">資料類型</span><span class="sxs-lookup"><span data-stu-id="db52e-116">Data type</span></span> | <span data-ttu-id="db52e-117">描述</span><span class="sxs-lookup"><span data-stu-id="db52e-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="db52e-118">datetime</span><span class="sxs-lookup"><span data-stu-id="db52e-118">datetime</span></span> | <span data-ttu-id="db52e-119">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="db52e-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="db52e-120">string</span><span class="sxs-lookup"><span data-stu-id="db52e-120">string</span></span> | <span data-ttu-id="db52e-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="db52e-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="db52e-122">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="db52e-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="db52e-123">string</span><span class="sxs-lookup"><span data-stu-id="db52e-123">string</span></span> | <span data-ttu-id="db52e-124">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="db52e-124">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="db52e-125">字串</span><span class="sxs-lookup"><span data-stu-id="db52e-125">string</span></span> | <span data-ttu-id="db52e-126">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="db52e-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="db52e-127">字串</span><span class="sxs-lookup"><span data-stu-id="db52e-127">string</span></span> | <span data-ttu-id="db52e-128">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="db52e-128">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="db52e-129">string</span><span class="sxs-lookup"><span data-stu-id="db52e-129">string</span></span> | <span data-ttu-id="db52e-130">重新命名為動作結果之檔案的原始名稱</span><span class="sxs-lookup"><span data-stu-id="db52e-130">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="db52e-131">string</span><span class="sxs-lookup"><span data-stu-id="db52e-131">string</span></span> | <span data-ttu-id="db52e-132">在套用錄製的動作之前包含檔的原始檔案夾</span><span class="sxs-lookup"><span data-stu-id="db52e-132">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="db52e-133">string</span><span class="sxs-lookup"><span data-stu-id="db52e-133">string</span></span> | <span data-ttu-id="db52e-134">使用的網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="db52e-134">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="db52e-135">string</span><span class="sxs-lookup"><span data-stu-id="db52e-135">string</span></span> | <span data-ttu-id="db52e-136">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="db52e-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="db52e-137">string</span><span class="sxs-lookup"><span data-stu-id="db52e-137">string</span></span> | <span data-ttu-id="db52e-138">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="db52e-138">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="db52e-139">string</span><span class="sxs-lookup"><span data-stu-id="db52e-139">string</span></span> | <span data-ttu-id="db52e-140">帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="db52e-140">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="db52e-141">string</span><span class="sxs-lookup"><span data-stu-id="db52e-141">string</span></span> | <span data-ttu-id="db52e-142">帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="db52e-142">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="db52e-143">string</span><span class="sxs-lookup"><span data-stu-id="db52e-143">string</span></span> | <span data-ttu-id="db52e-144">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="db52e-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="db52e-145">string</span><span class="sxs-lookup"><span data-stu-id="db52e-145">string</span></span> | <span data-ttu-id="db52e-146">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="db52e-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="db52e-147">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="db52e-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="db52e-148">string</span><span class="sxs-lookup"><span data-stu-id="db52e-148">string</span></span> | <span data-ttu-id="db52e-149">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="db52e-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="db52e-150">string</span><span class="sxs-lookup"><span data-stu-id="db52e-150">string</span></span> | <span data-ttu-id="db52e-151">裝置類型</span><span class="sxs-lookup"><span data-stu-id="db52e-151">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="db52e-152">string</span><span class="sxs-lookup"><span data-stu-id="db52e-152">string</span></span> | <span data-ttu-id="db52e-153">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="db52e-153">Platform of the operating system running on the device.</span></span> <span data-ttu-id="db52e-154">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="db52e-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="db52e-155">字串</span><span class="sxs-lookup"><span data-stu-id="db52e-155">string</span></span> | <span data-ttu-id="db52e-156">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="db52e-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="db52e-157">string</span><span class="sxs-lookup"><span data-stu-id="db52e-157">string</span></span> | <span data-ttu-id="db52e-158">通訊期間使用的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="db52e-158">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="db52e-159">string</span><span class="sxs-lookup"><span data-stu-id="db52e-159">string</span></span> | <span data-ttu-id="db52e-160">執行伺服器應用程式（處理錄製的動作）的裝置名稱</span><span class="sxs-lookup"><span data-stu-id="db52e-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="db52e-161">string</span><span class="sxs-lookup"><span data-stu-id="db52e-161">string</span></span> | <span data-ttu-id="db52e-162">執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="db52e-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="db52e-163">string</span><span class="sxs-lookup"><span data-stu-id="db52e-163">string</span></span> | <span data-ttu-id="db52e-164">相關網路通訊的目的地埠</span><span class="sxs-lookup"><span data-stu-id="db52e-164">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="db52e-165">string</span><span class="sxs-lookup"><span data-stu-id="db52e-165">string</span></span> | <span data-ttu-id="db52e-166">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="db52e-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="db52e-167">string</span><span class="sxs-lookup"><span data-stu-id="db52e-167">string</span></span> | <span data-ttu-id="db52e-168">網際網路服務提供者 (與端點 IP 位址相關聯的 ISP) </span><span class="sxs-lookup"><span data-stu-id="db52e-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="db52e-169">long</span><span class="sxs-lookup"><span data-stu-id="db52e-169">long</span></span> | <span data-ttu-id="db52e-170">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="db52e-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="db52e-171">string</span><span class="sxs-lookup"><span data-stu-id="db52e-171">string</span></span> | <span data-ttu-id="db52e-172">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="db52e-172">Additional information about the entity or event</span></span> |

>[!TIP]
> <span data-ttu-id="db52e-173">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的內建架構參照。</span><span class="sxs-lookup"><span data-stu-id="db52e-173">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>


## <a name="related-topics"></a><span data-ttu-id="db52e-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="db52e-174">Related topics</span></span>
- [<span data-ttu-id="db52e-175">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="db52e-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="db52e-176">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="db52e-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="db52e-177">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="db52e-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="db52e-178">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="db52e-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="db52e-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="db52e-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="db52e-180">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="db52e-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
