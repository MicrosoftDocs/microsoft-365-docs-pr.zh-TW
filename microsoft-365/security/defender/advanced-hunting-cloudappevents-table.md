---
title: Advanced 搜尋架構中的 CloudAppEvents 表格
description: 深入瞭解高級搜尋架構之 CloudAppEvents 資料表中 cloud apps and service 的事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，CloudAppEvents，雲端 App 安全性，MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935866"
---
# <a name="cloudappevents"></a><span data-ttu-id="45517-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="45517-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="45517-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="45517-105">**Applies to:**</span></span>
- <span data-ttu-id="45517-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45517-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="45517-107">[！附注] `CloudAppEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含 Microsoft Cloud App Security 所涵蓋之各種雲端 app 和服務中的活動相關資訊。</span><span class="sxs-lookup"><span data-stu-id="45517-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="45517-108">如需完整清單，請跳至 [應用程式和服務涵蓋](#apps-and-services-covered)。</span><span class="sxs-lookup"><span data-stu-id="45517-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="45517-109">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="45517-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="45517-110">此表格包含可用於表格的資訊 `AppFileEvents` 。</span><span class="sxs-lookup"><span data-stu-id="45517-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="45517-111">從2021年3月7日起，使用者在此日期以外的雲端服務中搜尋與檔案相關的活動，應改為使用 `CloudAppEvents` 表格。</span><span class="sxs-lookup"><span data-stu-id="45517-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="45517-112">請務必搜尋查詢和自訂偵測規則，該規則仍會使用 `AppFileEvents` 該表，並進行編輯，以使用 `CloudAppEvents` 該表。</span><span class="sxs-lookup"><span data-stu-id="45517-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="45517-113">若要瞭解轉換受影響查詢的相關指引[，請參閱使用 Microsoft 365 Defender 高級搜尋來搜尋各項 cloud app activity](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。</span><span class="sxs-lookup"><span data-stu-id="45517-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="45517-114">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="45517-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="45517-115">欄名稱</span><span class="sxs-lookup"><span data-stu-id="45517-115">Column name</span></span> | <span data-ttu-id="45517-116">資料類型</span><span class="sxs-lookup"><span data-stu-id="45517-116">Data type</span></span> | <span data-ttu-id="45517-117">描述</span><span class="sxs-lookup"><span data-stu-id="45517-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="45517-118">datetime</span><span class="sxs-lookup"><span data-stu-id="45517-118">datetime</span></span> | <span data-ttu-id="45517-119">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="45517-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="45517-120">string</span><span class="sxs-lookup"><span data-stu-id="45517-120">string</span></span> | <span data-ttu-id="45517-121">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="45517-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="45517-122">string</span><span class="sxs-lookup"><span data-stu-id="45517-122">string</span></span> | <span data-ttu-id="45517-123">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="45517-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="45517-124">string</span><span class="sxs-lookup"><span data-stu-id="45517-124">string</span></span> | <span data-ttu-id="45517-125">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="45517-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="45517-126">string</span><span class="sxs-lookup"><span data-stu-id="45517-126">string</span></span> | <span data-ttu-id="45517-127">帳戶在 Azure Active Directory 中的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="45517-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="45517-128">string</span><span class="sxs-lookup"><span data-stu-id="45517-128">string</span></span> | <span data-ttu-id="45517-129">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="45517-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="45517-130">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="45517-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="45517-131">string</span><span class="sxs-lookup"><span data-stu-id="45517-131">string</span></span> | <span data-ttu-id="45517-132">指出活動是否由系統管理員執行</span><span class="sxs-lookup"><span data-stu-id="45517-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="45517-133">string</span><span class="sxs-lookup"><span data-stu-id="45517-133">string</span></span> | <span data-ttu-id="45517-134">根據用途及功能的裝置類型，例如「網路裝置」、「工作站」、「伺服器」、「Mobile」、「遊戲主控台」或「印表機」。</span><span class="sxs-lookup"><span data-stu-id="45517-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="45517-135">string</span><span class="sxs-lookup"><span data-stu-id="45517-135">string</span></span> | <span data-ttu-id="45517-136">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="45517-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="45517-137">此欄會指出特定的作業系統，包括相同系列內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="45517-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="45517-138">string</span><span class="sxs-lookup"><span data-stu-id="45517-138">string</span></span> | <span data-ttu-id="45517-139">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="45517-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="45517-140">string</span><span class="sxs-lookup"><span data-stu-id="45517-140">string</span></span> | <span data-ttu-id="45517-141">指出 IP 位址是否屬於已知的匿名 proxy</span><span class="sxs-lookup"><span data-stu-id="45517-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="45517-142">string</span><span class="sxs-lookup"><span data-stu-id="45517-142">string</span></span> | <span data-ttu-id="45517-143">兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區</span><span class="sxs-lookup"><span data-stu-id="45517-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="45517-144">string</span><span class="sxs-lookup"><span data-stu-id="45517-144">string</span></span> | <span data-ttu-id="45517-145">用戶端 IP 位址為 geolocated 的城市</span><span class="sxs-lookup"><span data-stu-id="45517-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="45517-146">string</span><span class="sxs-lookup"><span data-stu-id="45517-146">string</span></span> | <span data-ttu-id="45517-147">網際網路服務提供者 (與 IP 位址相關聯的 ISP) </span><span class="sxs-lookup"><span data-stu-id="45517-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="45517-148">string</span><span class="sxs-lookup"><span data-stu-id="45517-148">string</span></span> | <span data-ttu-id="45517-149">來自網頁瀏覽器或其他用戶端應用程式的使用者代理程式資訊</span><span class="sxs-lookup"><span data-stu-id="45517-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="45517-150">string</span><span class="sxs-lookup"><span data-stu-id="45517-150">string</span></span> | <span data-ttu-id="45517-151">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="45517-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="45517-152">string</span><span class="sxs-lookup"><span data-stu-id="45517-152">string</span></span> | <span data-ttu-id="45517-153">錄製的活動中所涉及的物件（例如檔案或資料夾）的清單</span><span class="sxs-lookup"><span data-stu-id="45517-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="45517-154">string</span><span class="sxs-lookup"><span data-stu-id="45517-154">string</span></span> | <span data-ttu-id="45517-155">已錄製動作套用至之物件的名稱</span><span class="sxs-lookup"><span data-stu-id="45517-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="45517-156">string</span><span class="sxs-lookup"><span data-stu-id="45517-156">string</span></span> | <span data-ttu-id="45517-157">錄製的動作所套用的物件類型，例如檔案或資料夾</span><span class="sxs-lookup"><span data-stu-id="45517-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="45517-158">string</span><span class="sxs-lookup"><span data-stu-id="45517-158">string</span></span> | <span data-ttu-id="45517-159">套用錄製動作之物件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="45517-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="45517-160">string</span><span class="sxs-lookup"><span data-stu-id="45517-160">string</span></span> | <span data-ttu-id="45517-161">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="45517-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="45517-162">string</span><span class="sxs-lookup"><span data-stu-id="45517-162">string</span></span> | <span data-ttu-id="45517-163">來源應用程式或服務中 JSON 格式的原始事件資訊</span><span class="sxs-lookup"><span data-stu-id="45517-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="45517-164">string</span><span class="sxs-lookup"><span data-stu-id="45517-164">string</span></span> | <span data-ttu-id="45517-165">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="45517-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="45517-166">應用程式和服務涵蓋</span><span class="sxs-lookup"><span data-stu-id="45517-166">Apps and services covered</span></span>

- <span data-ttu-id="45517-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="45517-167">Dropbox</span></span>
- <span data-ttu-id="45517-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="45517-168">Dynamics 365</span></span>
- <span data-ttu-id="45517-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="45517-169">Exchange Online</span></span>
- <span data-ttu-id="45517-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45517-170">Microsoft Teams</span></span>
- <span data-ttu-id="45517-171">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="45517-171">OneDrive for Business</span></span>
- <span data-ttu-id="45517-172">電源自動化</span><span class="sxs-lookup"><span data-stu-id="45517-172">Power Automate</span></span>
- <span data-ttu-id="45517-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="45517-173">Power BI</span></span>
- <span data-ttu-id="45517-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="45517-174">SharePoint Online</span></span>
- <span data-ttu-id="45517-175">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="45517-175">Skype for Business</span></span>
- <span data-ttu-id="45517-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="45517-176">Office 365</span></span>
- <span data-ttu-id="45517-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="45517-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="45517-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="45517-178">Related topics</span></span>
- [<span data-ttu-id="45517-179">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="45517-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="45517-180">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="45517-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="45517-181">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="45517-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="45517-182">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="45517-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="45517-183">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="45517-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="45517-184">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="45517-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
