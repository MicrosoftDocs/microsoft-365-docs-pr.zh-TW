---
title: 進位搜尋架構中的 AppFileEvents 資料表
description: 在進位搜尋架構的 AppFileEvents 資料表中，瞭解與雲端應用程式和服務相關聯的檔案相關事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、資料行、資料類型、描述、AppFileEvents、雲端 App 安全性、MCAS
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932871"
---
# <a name="appfileevents"></a><span data-ttu-id="0db87-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="0db87-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0db87-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="0db87-105">**Applies to:**</span></span>
- <span data-ttu-id="0db87-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0db87-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0db87-107">進位搜尋架構中的表格包含 Microsoft Cloud App 安全性所監控之雲端應用程式和服務中的檔案 `AppFileEvents` 相關活動相關資訊。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0db87-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="0db87-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="0db87-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0db87-109">有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參照。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="0db87-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="0db87-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="0db87-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0db87-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="0db87-111">Column name</span></span> | <span data-ttu-id="0db87-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="0db87-112">Data type</span></span> | <span data-ttu-id="0db87-113">描述</span><span class="sxs-lookup"><span data-stu-id="0db87-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0db87-114">datetime</span><span class="sxs-lookup"><span data-stu-id="0db87-114">datetime</span></span> | <span data-ttu-id="0db87-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="0db87-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0db87-116">string</span><span class="sxs-lookup"><span data-stu-id="0db87-116">string</span></span> | <span data-ttu-id="0db87-117">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="0db87-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="0db87-118">請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="0db87-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="0db87-119">string</span><span class="sxs-lookup"><span data-stu-id="0db87-119">string</span></span> | <span data-ttu-id="0db87-120">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="0db87-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="0db87-121">字串</span><span class="sxs-lookup"><span data-stu-id="0db87-121">string</span></span> | <span data-ttu-id="0db87-122">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="0db87-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0db87-123">字串</span><span class="sxs-lookup"><span data-stu-id="0db87-123">string</span></span> | <span data-ttu-id="0db87-124">包含已記錄動作所使用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="0db87-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="0db87-125">string</span><span class="sxs-lookup"><span data-stu-id="0db87-125">string</span></span> | <span data-ttu-id="0db87-126">因動作而重新命名之檔案的原始名稱</span><span class="sxs-lookup"><span data-stu-id="0db87-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="0db87-127">string</span><span class="sxs-lookup"><span data-stu-id="0db87-127">string</span></span> | <span data-ttu-id="0db87-128">在已記錄的動作之前包含檔案的原始檔案夾</span><span class="sxs-lookup"><span data-stu-id="0db87-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="0db87-129">string</span><span class="sxs-lookup"><span data-stu-id="0db87-129">string</span></span> | <span data-ttu-id="0db87-130">已使用網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="0db87-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="0db87-131">string</span><span class="sxs-lookup"><span data-stu-id="0db87-131">string</span></span> | <span data-ttu-id="0db87-132">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="0db87-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0db87-133">string</span><span class="sxs-lookup"><span data-stu-id="0db87-133">string</span></span> | <span data-ttu-id="0db87-134">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="0db87-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0db87-135">string</span><span class="sxs-lookup"><span data-stu-id="0db87-135">string</span></span> | <span data-ttu-id="0db87-136">帳戶 (UPN) 使用者主體名稱</span><span class="sxs-lookup"><span data-stu-id="0db87-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0db87-137">string</span><span class="sxs-lookup"><span data-stu-id="0db87-137">string</span></span> | <span data-ttu-id="0db87-138">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0db87-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0db87-139">string</span><span class="sxs-lookup"><span data-stu-id="0db87-139">string</span></span> | <span data-ttu-id="0db87-140">顯示在通訊錄中的帳戶使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="0db87-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0db87-141">通常是指定或名字、中間名、姓氏或名字的組合。</span><span class="sxs-lookup"><span data-stu-id="0db87-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0db87-142">string</span><span class="sxs-lookup"><span data-stu-id="0db87-142">string</span></span> | <span data-ttu-id="0db87-143">裝置 FQDN (完整) 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="0db87-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="0db87-144">string</span><span class="sxs-lookup"><span data-stu-id="0db87-144">string</span></span> | <span data-ttu-id="0db87-145">裝置類型</span><span class="sxs-lookup"><span data-stu-id="0db87-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="0db87-146">string</span><span class="sxs-lookup"><span data-stu-id="0db87-146">string</span></span> | <span data-ttu-id="0db87-147">在裝置上作業系統平臺。</span><span class="sxs-lookup"><span data-stu-id="0db87-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0db87-148">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="0db87-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0db87-149">字串</span><span class="sxs-lookup"><span data-stu-id="0db87-149">string</span></span> | <span data-ttu-id="0db87-150">指派給端點的 IP 位址，用於相關網路通訊期間</span><span class="sxs-lookup"><span data-stu-id="0db87-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="0db87-151">string</span><span class="sxs-lookup"><span data-stu-id="0db87-151">string</span></span> | <span data-ttu-id="0db87-152">執行處理錄製動作之伺服器應用程式之裝置的名稱</span><span class="sxs-lookup"><span data-stu-id="0db87-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="0db87-153">string</span><span class="sxs-lookup"><span data-stu-id="0db87-153">string</span></span> | <span data-ttu-id="0db87-154">執行處理錄製動作之伺服器應用程式的裝置 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0db87-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="0db87-155">string</span><span class="sxs-lookup"><span data-stu-id="0db87-155">string</span></span> | <span data-ttu-id="0db87-156">與活動相關的城市、國家/地區或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="0db87-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="0db87-157">string</span><span class="sxs-lookup"><span data-stu-id="0db87-157">string</span></span> | <span data-ttu-id="0db87-158">與端點 IP 位址 (ISP) 網際網路服務提供者</span><span class="sxs-lookup"><span data-stu-id="0db87-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="0db87-159">long</span><span class="sxs-lookup"><span data-stu-id="0db87-159">long</span></span> | <span data-ttu-id="0db87-160">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0db87-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="0db87-161">string</span><span class="sxs-lookup"><span data-stu-id="0db87-161">string</span></span> | <span data-ttu-id="0db87-162">實體或事件的其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="0db87-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0db87-163">相關主題</span><span class="sxs-lookup"><span data-stu-id="0db87-163">Related topics</span></span>
- [<span data-ttu-id="0db87-164">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="0db87-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0db87-165">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="0db87-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0db87-166">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="0db87-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0db87-167">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="0db87-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0db87-168">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="0db87-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0db87-169">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="0db87-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
