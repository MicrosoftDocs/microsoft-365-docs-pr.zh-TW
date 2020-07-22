---
title: Advanced 搜尋架構中的 AppFileEvents 表格
description: 深入瞭解在高級搜尋架構的 AppFileEvents 資料表中，與雲端 app 和服務相關聯的檔案相關事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，AppFileEvents，Cloud App Security，MCAS
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
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204752"
---
# <a name="appfileevents"></a><span data-ttu-id="72abc-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="72abc-104">AppFileEvents</span></span>

<span data-ttu-id="72abc-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="72abc-105">**Applies to:**</span></span>
- <span data-ttu-id="72abc-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="72abc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="72abc-107">[！附注] `AppFileEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含雲端 app 和服務中由 Microsoft cloud App Security 監控之檔案相關活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="72abc-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="72abc-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="72abc-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="72abc-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="72abc-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="72abc-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="72abc-110">Column name</span></span> | <span data-ttu-id="72abc-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="72abc-111">Data type</span></span> | <span data-ttu-id="72abc-112">描述</span><span class="sxs-lookup"><span data-stu-id="72abc-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="72abc-113">datetime</span><span class="sxs-lookup"><span data-stu-id="72abc-113">datetime</span></span> | <span data-ttu-id="72abc-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="72abc-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="72abc-115">string</span><span class="sxs-lookup"><span data-stu-id="72abc-115">string</span></span> | <span data-ttu-id="72abc-116">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="72abc-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="72abc-117">string</span><span class="sxs-lookup"><span data-stu-id="72abc-117">string</span></span> | <span data-ttu-id="72abc-118">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="72abc-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="72abc-119">字串</span><span class="sxs-lookup"><span data-stu-id="72abc-119">string</span></span> | <span data-ttu-id="72abc-120">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="72abc-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="72abc-121">字串</span><span class="sxs-lookup"><span data-stu-id="72abc-121">string</span></span> | <span data-ttu-id="72abc-122">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="72abc-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="72abc-123">string</span><span class="sxs-lookup"><span data-stu-id="72abc-123">string</span></span> | <span data-ttu-id="72abc-124">重新命名為動作結果之檔案的原始名稱</span><span class="sxs-lookup"><span data-stu-id="72abc-124">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="72abc-125">string</span><span class="sxs-lookup"><span data-stu-id="72abc-125">string</span></span> | <span data-ttu-id="72abc-126">在套用錄製的動作之前包含檔的原始檔案夾</span><span class="sxs-lookup"><span data-stu-id="72abc-126">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="72abc-127">string</span><span class="sxs-lookup"><span data-stu-id="72abc-127">string</span></span> | <span data-ttu-id="72abc-128">使用的網路通訊協定</span><span class="sxs-lookup"><span data-stu-id="72abc-128">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="72abc-129">string</span><span class="sxs-lookup"><span data-stu-id="72abc-129">string</span></span> | <span data-ttu-id="72abc-130">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="72abc-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="72abc-131">string</span><span class="sxs-lookup"><span data-stu-id="72abc-131">string</span></span> | <span data-ttu-id="72abc-132">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="72abc-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="72abc-133">string</span><span class="sxs-lookup"><span data-stu-id="72abc-133">string</span></span> | <span data-ttu-id="72abc-134">帳戶的使用者主要名稱（UPN）</span><span class="sxs-lookup"><span data-stu-id="72abc-134">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="72abc-135">string</span><span class="sxs-lookup"><span data-stu-id="72abc-135">string</span></span> | <span data-ttu-id="72abc-136">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="72abc-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="72abc-137">string</span><span class="sxs-lookup"><span data-stu-id="72abc-137">string</span></span> | <span data-ttu-id="72abc-138">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="72abc-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="72abc-139">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="72abc-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="72abc-140">string</span><span class="sxs-lookup"><span data-stu-id="72abc-140">string</span></span> | <span data-ttu-id="72abc-141">裝置的完整功能變數名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="72abc-141">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="72abc-142">string</span><span class="sxs-lookup"><span data-stu-id="72abc-142">string</span></span> | <span data-ttu-id="72abc-143">裝置類型</span><span class="sxs-lookup"><span data-stu-id="72abc-143">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="72abc-144">string</span><span class="sxs-lookup"><span data-stu-id="72abc-144">string</span></span> | <span data-ttu-id="72abc-145">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="72abc-145">Platform of the operating system running on the device.</span></span> <span data-ttu-id="72abc-146">這表示特定作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="72abc-146">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="72abc-147">string</span><span class="sxs-lookup"><span data-stu-id="72abc-147">string</span></span> | <span data-ttu-id="72abc-148">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="72abc-148">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="72abc-149">string</span><span class="sxs-lookup"><span data-stu-id="72abc-149">string</span></span> | <span data-ttu-id="72abc-150">執行伺服器應用程式（處理錄製的動作）的裝置名稱</span><span class="sxs-lookup"><span data-stu-id="72abc-150">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="72abc-151">string</span><span class="sxs-lookup"><span data-stu-id="72abc-151">string</span></span> | <span data-ttu-id="72abc-152">執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="72abc-152">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="72abc-153">string</span><span class="sxs-lookup"><span data-stu-id="72abc-153">string</span></span> | <span data-ttu-id="72abc-154">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="72abc-154">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="72abc-155">string</span><span class="sxs-lookup"><span data-stu-id="72abc-155">string</span></span> | <span data-ttu-id="72abc-156">與端點 IP 位址相關聯的網際網路服務提供者（ISP）</span><span class="sxs-lookup"><span data-stu-id="72abc-156">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="72abc-157">long</span><span class="sxs-lookup"><span data-stu-id="72abc-157">long</span></span> | <span data-ttu-id="72abc-158">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="72abc-158">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="72abc-159">string</span><span class="sxs-lookup"><span data-stu-id="72abc-159">string</span></span> | <span data-ttu-id="72abc-160">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="72abc-160">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="72abc-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="72abc-161">Related topics</span></span>
- [<span data-ttu-id="72abc-162">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="72abc-162">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72abc-163">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="72abc-163">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="72abc-164">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="72abc-164">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="72abc-165">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="72abc-165">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="72abc-166">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="72abc-166">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="72abc-167">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="72abc-167">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
