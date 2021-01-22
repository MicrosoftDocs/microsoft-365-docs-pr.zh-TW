---
title: 進位搜尋架構中的 DeviceImageLoadEvents 資料表
description: 瞭解進位搜尋架構的 DeviceImageLoadEvents 資料表中的 DLL 載入事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、資料行、資料類型、描述、Imageloadevents、DeviceImageLoadEvents、DLL 載入、文件庫、檔案圖像
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
ms.openlocfilehash: 924d465d90086bcfffe29660b7f281ff3d5b07aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931287"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="9a0bd-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="9a0bd-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9a0bd-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="9a0bd-105">**Applies to:**</span></span>
- <span data-ttu-id="9a0bd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a0bd-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="9a0bd-107">進 `DeviceImageLoadEvents` 位搜尋架構 [中的表格](advanced-hunting-overview.md) 包含 DLL 載入事件相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="9a0bd-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9a0bd-109">有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="9a0bd-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9a0bd-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9a0bd-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="9a0bd-111">Column name</span></span> | <span data-ttu-id="9a0bd-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="9a0bd-112">Data type</span></span> | <span data-ttu-id="9a0bd-113">描述</span><span class="sxs-lookup"><span data-stu-id="9a0bd-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9a0bd-114">datetime</span><span class="sxs-lookup"><span data-stu-id="9a0bd-114">datetime</span></span> | <span data-ttu-id="9a0bd-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="9a0bd-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9a0bd-116">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-116">string</span></span> | <span data-ttu-id="9a0bd-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="9a0bd-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9a0bd-118">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-118">string</span></span> | <span data-ttu-id="9a0bd-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9a0bd-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="9a0bd-120">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-120">string</span></span> | <span data-ttu-id="9a0bd-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="9a0bd-122">請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="9a0bd-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="9a0bd-123">字串</span><span class="sxs-lookup"><span data-stu-id="9a0bd-123">string</span></span> | <span data-ttu-id="9a0bd-124">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="9a0bd-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="9a0bd-125">字串</span><span class="sxs-lookup"><span data-stu-id="9a0bd-125">string</span></span> | <span data-ttu-id="9a0bd-126">包含已記錄動作所使用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="9a0bd-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="9a0bd-127">字串</span><span class="sxs-lookup"><span data-stu-id="9a0bd-127">string</span></span> | <span data-ttu-id="9a0bd-128">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="9a0bd-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="9a0bd-129">字串</span><span class="sxs-lookup"><span data-stu-id="9a0bd-129">string</span></span> | <span data-ttu-id="9a0bd-130">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="9a0bd-131">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="9a0bd-132">字串</span><span class="sxs-lookup"><span data-stu-id="9a0bd-132">string</span></span> | <span data-ttu-id="9a0bd-133">已記錄動作所針對之檔案的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="9a0bd-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="9a0bd-134">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-134">string</span></span> | <span data-ttu-id="9a0bd-135">執行負責事件之程式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="9a0bd-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="9a0bd-136">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-136">string</span></span> | <span data-ttu-id="9a0bd-137">執行負責事件之程式之帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="9a0bd-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="9a0bd-138">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-138">string</span></span> | <span data-ttu-id="9a0bd-139">執行 (之) 之帳戶的安全性識別碼為 SID</span><span class="sxs-lookup"><span data-stu-id="9a0bd-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="9a0bd-140">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-140">string</span></span> | <span data-ttu-id="9a0bd-141">初始化事件之程式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-141">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="9a0bd-142">Windows 會依據某些特性指派完整性等級給程式，例如從網際網路下載啟動程式。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-142">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="9a0bd-143">這些完整性等級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="9a0bd-143">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="9a0bd-144">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-144">string</span></span> | <span data-ttu-id="9a0bd-145">指出使用者存取控制存在或不存在的權杖類型 (UAC) 許可權提高已應用至初始化事件的流程</span><span class="sxs-lookup"><span data-stu-id="9a0bd-145">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="9a0bd-146">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-146">string</span></span> | <span data-ttu-id="9a0bd-147">初始化活動的影像 (的 SHA-1) 影像檔案</span><span class="sxs-lookup"><span data-stu-id="9a0bd-147">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="9a0bd-148">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-148">string</span></span> | <span data-ttu-id="9a0bd-149">初始化事件的 (的 SHA-256) 影像檔案。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-149">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="9a0bd-150">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-150">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="9a0bd-151">字串</span><span class="sxs-lookup"><span data-stu-id="9a0bd-151">string</span></span> | <span data-ttu-id="9a0bd-152">啟動活動的 (圖像) MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="9a0bd-152">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="9a0bd-153">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-153">string</span></span> | <span data-ttu-id="9a0bd-154">初始化事件之程式的名稱</span><span class="sxs-lookup"><span data-stu-id="9a0bd-154">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="9a0bd-155">int</span><span class="sxs-lookup"><span data-stu-id="9a0bd-155">int</span></span> | <span data-ttu-id="9a0bd-156">程式識別碼 (初始化) 的 PID 值</span><span class="sxs-lookup"><span data-stu-id="9a0bd-156">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="9a0bd-157">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-157">string</span></span> | <span data-ttu-id="9a0bd-158">用來執行初始化活動的程式命令列</span><span class="sxs-lookup"><span data-stu-id="9a0bd-158">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="9a0bd-159">datetime</span><span class="sxs-lookup"><span data-stu-id="9a0bd-159">datetime</span></span> | <span data-ttu-id="9a0bd-160">啟動事件之程式開始的日期和時間</span><span class="sxs-lookup"><span data-stu-id="9a0bd-160">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="9a0bd-161">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-161">string</span></span> | <span data-ttu-id="9a0bd-162">啟動事件之 (圖像) 的資料夾</span><span class="sxs-lookup"><span data-stu-id="9a0bd-162">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="9a0bd-163">int</span><span class="sxs-lookup"><span data-stu-id="9a0bd-163">int</span></span> | <span data-ttu-id="9a0bd-164">程式識別碼 (產生) 事件之父流程的 PID 值</span><span class="sxs-lookup"><span data-stu-id="9a0bd-164">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="9a0bd-165">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-165">string</span></span> | <span data-ttu-id="9a0bd-166">指定事件所負責之程式之父程式的名稱</span><span class="sxs-lookup"><span data-stu-id="9a0bd-166">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="9a0bd-167">datetime</span><span class="sxs-lookup"><span data-stu-id="9a0bd-167">datetime</span></span> | <span data-ttu-id="9a0bd-168">事件負責之程式父項開始的日期和時間</span><span class="sxs-lookup"><span data-stu-id="9a0bd-168">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="9a0bd-169">long</span><span class="sxs-lookup"><span data-stu-id="9a0bd-169">long</span></span> | <span data-ttu-id="9a0bd-170">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="9a0bd-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9a0bd-171">若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="9a0bd-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="9a0bd-172">string</span><span class="sxs-lookup"><span data-stu-id="9a0bd-172">string</span></span> | <span data-ttu-id="9a0bd-173">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="9a0bd-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9a0bd-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="9a0bd-174">Related topics</span></span>
- [<span data-ttu-id="9a0bd-175">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="9a0bd-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9a0bd-176">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="9a0bd-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9a0bd-177">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="9a0bd-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9a0bd-178">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="9a0bd-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9a0bd-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="9a0bd-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9a0bd-180">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="9a0bd-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
