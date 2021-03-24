---
title: Advanced 搜尋架構中的 CloudAppEvents 表格
description: 深入瞭解高級搜尋架構之 CloudAppEvents 資料表中 cloud apps and service 的事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，CloudAppEvents，Cloud App Security，MCAS
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e9e9cc78289136e22da1871d68a384eac2a901ef
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058039"
---
# <a name="cloudappevents"></a><span data-ttu-id="76074-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="76074-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="76074-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="76074-105">**Applies to:**</span></span>
- <span data-ttu-id="76074-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76074-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="76074-107">[！附注] `CloudAppEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含 Microsoft cloud App Security、特別是 Dropbox、Exchange Online、OneDrive、Microsoft 團隊及 SharePoint 所涵蓋的各種雲端應用程式和服務中的活動相關資訊。</span><span class="sxs-lookup"><span data-stu-id="76074-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="76074-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="76074-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="76074-109">此表格包含可用於表格的資訊 `AppFileEvents` 。</span><span class="sxs-lookup"><span data-stu-id="76074-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="76074-110">從2021年3月7日起，使用者在此日期以外的雲端服務中搜尋與檔案相關的活動，應改為使用 `CloudAppEvents` 表格。</span><span class="sxs-lookup"><span data-stu-id="76074-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="76074-111">請務必搜尋查詢和自訂偵測規則，該規則仍會使用 `AppFileEvents` 該表，並進行編輯，以使用 `CloudAppEvents` 該表。</span><span class="sxs-lookup"><span data-stu-id="76074-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="76074-112">若要瞭解轉換受影響查詢的相關指引，請參閱 [使用 Microsoft 365 Defender advanced 搜尋跨 cloud app Activity 搜尋](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)。</span><span class="sxs-lookup"><span data-stu-id="76074-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="76074-113">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="76074-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="76074-114">欄名稱</span><span class="sxs-lookup"><span data-stu-id="76074-114">Column name</span></span> | <span data-ttu-id="76074-115">資料類型</span><span class="sxs-lookup"><span data-stu-id="76074-115">Data type</span></span> | <span data-ttu-id="76074-116">描述</span><span class="sxs-lookup"><span data-stu-id="76074-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="76074-117">datetime</span><span class="sxs-lookup"><span data-stu-id="76074-117">datetime</span></span> | <span data-ttu-id="76074-118">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="76074-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="76074-119">string</span><span class="sxs-lookup"><span data-stu-id="76074-119">string</span></span> | <span data-ttu-id="76074-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="76074-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="76074-121">string</span><span class="sxs-lookup"><span data-stu-id="76074-121">string</span></span> | <span data-ttu-id="76074-122">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="76074-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="76074-123">string</span><span class="sxs-lookup"><span data-stu-id="76074-123">string</span></span> | <span data-ttu-id="76074-124">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="76074-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="76074-125">string</span><span class="sxs-lookup"><span data-stu-id="76074-125">string</span></span> | <span data-ttu-id="76074-126">Azure Active Directory 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="76074-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="76074-127">string</span><span class="sxs-lookup"><span data-stu-id="76074-127">string</span></span> | <span data-ttu-id="76074-128">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="76074-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="76074-129">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="76074-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="76074-130">string</span><span class="sxs-lookup"><span data-stu-id="76074-130">string</span></span> | <span data-ttu-id="76074-131">指出活動是否由系統管理員執行</span><span class="sxs-lookup"><span data-stu-id="76074-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="76074-132">string</span><span class="sxs-lookup"><span data-stu-id="76074-132">string</span></span> | <span data-ttu-id="76074-133">根據用途及功能的裝置類型，例如「網路裝置」、「工作站」、「伺服器」、「Mobile」、「遊戲主控台」或「印表機」。</span><span class="sxs-lookup"><span data-stu-id="76074-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="76074-134">string</span><span class="sxs-lookup"><span data-stu-id="76074-134">string</span></span> | <span data-ttu-id="76074-135">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="76074-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="76074-136">此欄會指出特定的作業系統，包括相同系列內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="76074-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="76074-137">string</span><span class="sxs-lookup"><span data-stu-id="76074-137">string</span></span> | <span data-ttu-id="76074-138">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="76074-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="76074-139">string</span><span class="sxs-lookup"><span data-stu-id="76074-139">string</span></span> | <span data-ttu-id="76074-140">指出 IP 位址是否屬於已知的匿名 proxy</span><span class="sxs-lookup"><span data-stu-id="76074-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="76074-141">string</span><span class="sxs-lookup"><span data-stu-id="76074-141">string</span></span> | <span data-ttu-id="76074-142">兩個字母的代碼，指出用戶端 IP 位址為 geolocated 的國家/地區</span><span class="sxs-lookup"><span data-stu-id="76074-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="76074-143">string</span><span class="sxs-lookup"><span data-stu-id="76074-143">string</span></span> | <span data-ttu-id="76074-144">用戶端 IP 位址為 geolocated 的城市</span><span class="sxs-lookup"><span data-stu-id="76074-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="76074-145">string</span><span class="sxs-lookup"><span data-stu-id="76074-145">string</span></span> | <span data-ttu-id="76074-146">網際網路服務提供者 (與 IP 位址相關聯的 ISP) </span><span class="sxs-lookup"><span data-stu-id="76074-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="76074-147">string</span><span class="sxs-lookup"><span data-stu-id="76074-147">string</span></span> | <span data-ttu-id="76074-148">來自網頁瀏覽器或其他用戶端應用程式的使用者代理程式資訊</span><span class="sxs-lookup"><span data-stu-id="76074-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="76074-149">string</span><span class="sxs-lookup"><span data-stu-id="76074-149">string</span></span> | <span data-ttu-id="76074-150">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="76074-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="76074-151">string</span><span class="sxs-lookup"><span data-stu-id="76074-151">string</span></span> | <span data-ttu-id="76074-152">錄製的活動中所涉及的物件（例如檔案或資料夾）的清單</span><span class="sxs-lookup"><span data-stu-id="76074-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="76074-153">string</span><span class="sxs-lookup"><span data-stu-id="76074-153">string</span></span> | <span data-ttu-id="76074-154">已錄製動作套用至之物件的名稱</span><span class="sxs-lookup"><span data-stu-id="76074-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="76074-155">string</span><span class="sxs-lookup"><span data-stu-id="76074-155">string</span></span> | <span data-ttu-id="76074-156">錄製的動作所套用的物件類型，例如檔案或資料夾</span><span class="sxs-lookup"><span data-stu-id="76074-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="76074-157">string</span><span class="sxs-lookup"><span data-stu-id="76074-157">string</span></span> | <span data-ttu-id="76074-158">套用錄製動作之物件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="76074-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="76074-159">string</span><span class="sxs-lookup"><span data-stu-id="76074-159">string</span></span> | <span data-ttu-id="76074-160">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="76074-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="76074-161">string</span><span class="sxs-lookup"><span data-stu-id="76074-161">string</span></span> | <span data-ttu-id="76074-162">來源應用程式或服務中 JSON 格式的原始事件資訊</span><span class="sxs-lookup"><span data-stu-id="76074-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="76074-163">string</span><span class="sxs-lookup"><span data-stu-id="76074-163">string</span></span> | <span data-ttu-id="76074-164">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="76074-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="76074-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="76074-165">Related topics</span></span>
- [<span data-ttu-id="76074-166">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="76074-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="76074-167">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="76074-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="76074-168">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="76074-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="76074-169">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="76074-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="76074-170">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="76074-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="76074-171">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="76074-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
