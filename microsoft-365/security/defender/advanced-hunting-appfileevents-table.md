---
title: Advanced 搜尋架構中的 AppFileEvents 表格
description: 深入瞭解在高級搜尋架構的 AppFileEvents 資料表中，與雲端 app 和服務相關聯的檔案相關事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，AppFileEvents，Cloud App Security，MCAS
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
ms.openlocfilehash: b8b3b34e1b8535772d19f8ddd9f52c5c0a89292b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499341"
---
# <a name="appfileevents"></a><span data-ttu-id="8a911-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="8a911-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a911-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8a911-105">**Applies to:**</span></span>
- <span data-ttu-id="8a911-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a911-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8a911-107">[！附注] `AppFileEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含雲端 app 和服務中由 Microsoft cloud App Security 監控之檔案相關活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8a911-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="8a911-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="8a911-108">Use this reference to construct queries that return information from this table.</span></span>

>[!WARNING]
><span data-ttu-id="8a911-109">此表格即將停用。</span><span class="sxs-lookup"><span data-stu-id="8a911-109">This table will be retired soon.</span></span> <span data-ttu-id="8a911-110">從2021年3月7日直到 `AppFileEvents` 資料表不再記錄記錄。</span><span class="sxs-lookup"><span data-stu-id="8a911-110">As of March 7, 2021, the `AppFileEvents` table is no longer logging records.</span></span> <span data-ttu-id="8a911-111">使用者在所說的日期以外的雲端服務中搜尋與檔案相關的活動，應改為使用 [CloudAppEvents](advanced-hunting-cloudappevents-table.md) 表格。</span><span class="sxs-lookup"><span data-stu-id="8a911-111">Users hunting through file-related activities in cloud services on and beyond the said date should use the [CloudAppEvents](advanced-hunting-cloudappevents-table.md) table instead.</span></span> <br><br><span data-ttu-id="8a911-112">請務必搜尋查詢和自訂偵測規則，該規則仍會使用 `AppFileEvents` 該表，並進行編輯，以使用 `CloudAppEvents` 該表。</span><span class="sxs-lookup"><span data-stu-id="8a911-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="8a911-113">若要瞭解轉換受影響查詢的相關指引，請參閱 [使用 Microsoft 365 Defender advanced 搜尋跨 cloud app Activity 搜尋](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。</span><span class="sxs-lookup"><span data-stu-id="8a911-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="8a911-114">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="8a911-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8a911-115">欄名稱</span><span class="sxs-lookup"><span data-stu-id="8a911-115">Column name</span></span> | <span data-ttu-id="8a911-116">資料類型</span><span class="sxs-lookup"><span data-stu-id="8a911-116">Data type</span></span> | <span data-ttu-id="8a911-117">描述</span><span class="sxs-lookup"><span data-stu-id="8a911-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8a911-118">datetime</span><span class="sxs-lookup"><span data-stu-id="8a911-118">datetime</span></span> | <span data-ttu-id="8a911-119">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="8a911-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="8a911-120">string</span><span class="sxs-lookup"><span data-stu-id="8a911-120">string</span></span> | <span data-ttu-id="8a911-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="8a911-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="8a911-122">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="8a911-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="8a911-123">string</span><span class="sxs-lookup"><span data-stu-id="8a911-123">string</span></span> | <span data-ttu-id="8a911-124">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="8a911-124">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="8a911-125">字串</span><span class="sxs-lookup"><span data-stu-id="8a911-125">string</span></span> | <span data-ttu-id="8a911-126">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="8a911-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="8a911-127">字串</span><span class="sxs-lookup"><span data-stu-id="8a911-127">string</span></span> | <span data-ttu-id="8a911-128">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="8a911-128">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="8a911-129">string</span><span class="sxs-lookup"><span data-stu-id="8a911-129">string</span></span> | <span data-ttu-id="8a911-130">重新命名為動作結果之檔案的原始名稱</span><span class="sxs-lookup"><span data-stu-id="8a911-130">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="8a911-131">string</span><span class="sxs-lookup"><span data-stu-id="8a911-131">string</span></span> | <span data-ttu-id="8a911-132">在套用錄製的動作之前包含檔的原始檔案夾</span><span class="sxs-lookup"><span data-stu-id="8a911-132">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="8a911-133">string</span><span class="sxs-lookup"><span data-stu-id="8a911-133">string</span></span> | <span data-ttu-id="8a911-134">使用的網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="8a911-134">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="8a911-135">string</span><span class="sxs-lookup"><span data-stu-id="8a911-135">string</span></span> | <span data-ttu-id="8a911-136">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="8a911-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="8a911-137">string</span><span class="sxs-lookup"><span data-stu-id="8a911-137">string</span></span> | <span data-ttu-id="8a911-138">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="8a911-138">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="8a911-139">string</span><span class="sxs-lookup"><span data-stu-id="8a911-139">string</span></span> | <span data-ttu-id="8a911-140">帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="8a911-140">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="8a911-141">string</span><span class="sxs-lookup"><span data-stu-id="8a911-141">string</span></span> | <span data-ttu-id="8a911-142">帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="8a911-142">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="8a911-143">string</span><span class="sxs-lookup"><span data-stu-id="8a911-143">string</span></span> | <span data-ttu-id="8a911-144">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="8a911-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="8a911-145">string</span><span class="sxs-lookup"><span data-stu-id="8a911-145">string</span></span> | <span data-ttu-id="8a911-146">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="8a911-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="8a911-147">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="8a911-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="8a911-148">string</span><span class="sxs-lookup"><span data-stu-id="8a911-148">string</span></span> | <span data-ttu-id="8a911-149">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="8a911-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="8a911-150">string</span><span class="sxs-lookup"><span data-stu-id="8a911-150">string</span></span> | <span data-ttu-id="8a911-151">裝置類型</span><span class="sxs-lookup"><span data-stu-id="8a911-151">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="8a911-152">string</span><span class="sxs-lookup"><span data-stu-id="8a911-152">string</span></span> | <span data-ttu-id="8a911-153">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="8a911-153">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8a911-154">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="8a911-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="8a911-155">字串</span><span class="sxs-lookup"><span data-stu-id="8a911-155">string</span></span> | <span data-ttu-id="8a911-156">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="8a911-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="8a911-157">string</span><span class="sxs-lookup"><span data-stu-id="8a911-157">string</span></span> | <span data-ttu-id="8a911-158">通訊期間使用的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="8a911-158">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="8a911-159">string</span><span class="sxs-lookup"><span data-stu-id="8a911-159">string</span></span> | <span data-ttu-id="8a911-160">執行伺服器應用程式（處理錄製的動作）的裝置名稱</span><span class="sxs-lookup"><span data-stu-id="8a911-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="8a911-161">string</span><span class="sxs-lookup"><span data-stu-id="8a911-161">string</span></span> | <span data-ttu-id="8a911-162">執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8a911-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="8a911-163">string</span><span class="sxs-lookup"><span data-stu-id="8a911-163">string</span></span> | <span data-ttu-id="8a911-164">相關網路通訊的目的地埠</span><span class="sxs-lookup"><span data-stu-id="8a911-164">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="8a911-165">string</span><span class="sxs-lookup"><span data-stu-id="8a911-165">string</span></span> | <span data-ttu-id="8a911-166">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="8a911-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="8a911-167">string</span><span class="sxs-lookup"><span data-stu-id="8a911-167">string</span></span> | <span data-ttu-id="8a911-168">網際網路服務提供者 (與端點 IP 位址相關聯的 ISP) </span><span class="sxs-lookup"><span data-stu-id="8a911-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="8a911-169">long</span><span class="sxs-lookup"><span data-stu-id="8a911-169">long</span></span> | <span data-ttu-id="8a911-170">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="8a911-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="8a911-171">string</span><span class="sxs-lookup"><span data-stu-id="8a911-171">string</span></span> | <span data-ttu-id="8a911-172">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="8a911-172">Additional information about the entity or event</span></span> |

>[!TIP]
> <span data-ttu-id="8a911-173">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的內建架構參照。</span><span class="sxs-lookup"><span data-stu-id="8a911-173">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>


## <a name="related-topics"></a><span data-ttu-id="8a911-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="8a911-174">Related topics</span></span>
- [<span data-ttu-id="8a911-175">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="8a911-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a911-176">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="8a911-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a911-177">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="8a911-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a911-178">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="8a911-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8a911-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="8a911-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a911-180">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="8a911-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
