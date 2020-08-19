---
title: Advanced 搜尋架構中的 DeviceImageLoadEvents 表格
description: 瞭解在高級搜尋架構的 DeviceImageLoadEvents 資料表中載入 DLL 的事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，imageloadevents，DeviceImageLoadEvents，DLL 載入，文件庫，檔案影像
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
ms.openlocfilehash: 3c63808e503da5474176de11ff5df8d909ab58e3
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797941"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="fea5c-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="fea5c-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="fea5c-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fea5c-105">**Applies to:**</span></span>
- <span data-ttu-id="fea5c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="fea5c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="fea5c-107">[！附注] `DeviceImageLoadEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含 DLL 載入事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fea5c-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="fea5c-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="fea5c-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="fea5c-109">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="fea5c-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="fea5c-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="fea5c-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fea5c-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="fea5c-111">Column name</span></span> | <span data-ttu-id="fea5c-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="fea5c-112">Data type</span></span> | <span data-ttu-id="fea5c-113">描述</span><span class="sxs-lookup"><span data-stu-id="fea5c-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="fea5c-114">datetime</span><span class="sxs-lookup"><span data-stu-id="fea5c-114">datetime</span></span> | <span data-ttu-id="fea5c-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="fea5c-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="fea5c-116">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-116">string</span></span> | <span data-ttu-id="fea5c-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="fea5c-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="fea5c-118">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-118">string</span></span> | <span data-ttu-id="fea5c-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="fea5c-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="fea5c-120">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-120">string</span></span> | <span data-ttu-id="fea5c-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="fea5c-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="fea5c-122">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="fea5c-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="fea5c-123">字串</span><span class="sxs-lookup"><span data-stu-id="fea5c-123">string</span></span> | <span data-ttu-id="fea5c-124">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="fea5c-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="fea5c-125">字串</span><span class="sxs-lookup"><span data-stu-id="fea5c-125">string</span></span> | <span data-ttu-id="fea5c-126">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="fea5c-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="fea5c-127">字串</span><span class="sxs-lookup"><span data-stu-id="fea5c-127">string</span></span> | <span data-ttu-id="fea5c-128">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="fea5c-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="fea5c-129">字串</span><span class="sxs-lookup"><span data-stu-id="fea5c-129">string</span></span> | <span data-ttu-id="fea5c-130">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="fea5c-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="fea5c-131">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="fea5c-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="fea5c-132">字串</span><span class="sxs-lookup"><span data-stu-id="fea5c-132">string</span></span> | <span data-ttu-id="fea5c-133">錄製的動作所套用的檔案 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="fea5c-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="fea5c-134">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-134">string</span></span> | <span data-ttu-id="fea5c-135">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="fea5c-135">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="fea5c-136">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-136">string</span></span> | <span data-ttu-id="fea5c-137">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="fea5c-137">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="fea5c-138">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-138">string</span></span> | <span data-ttu-id="fea5c-139">執行事件負責處理之帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="fea5c-139">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="fea5c-140">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-140">string</span></span> | <span data-ttu-id="fea5c-141">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="fea5c-141">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="fea5c-142">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="fea5c-142">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="fea5c-143">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="fea5c-143">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="fea5c-144">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-144">string</span></span> | <span data-ttu-id="fea5c-145">指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。</span><span class="sxs-lookup"><span data-stu-id="fea5c-145">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="fea5c-146">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-146">string</span></span> | <span data-ttu-id="fea5c-147">啟動事件) 的處理常式 (映射檔 SHA-1</span><span class="sxs-lookup"><span data-stu-id="fea5c-147">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="fea5c-148">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-148">string</span></span> | <span data-ttu-id="fea5c-149">啟動事件) 的處理常式 (映射檔 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="fea5c-149">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="fea5c-150">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="fea5c-150">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="fea5c-151">字串</span><span class="sxs-lookup"><span data-stu-id="fea5c-151">string</span></span> | <span data-ttu-id="fea5c-152">啟動事件之程式 (映射檔) 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="fea5c-152">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="fea5c-153">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-153">string</span></span> | <span data-ttu-id="fea5c-154">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="fea5c-154">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="fea5c-155">int</span><span class="sxs-lookup"><span data-stu-id="fea5c-155">int</span></span> | <span data-ttu-id="fea5c-156">啟動事件之程式的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="fea5c-156">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="fea5c-157">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-157">string</span></span> | <span data-ttu-id="fea5c-158">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="fea5c-158">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="fea5c-159">datetime</span><span class="sxs-lookup"><span data-stu-id="fea5c-159">datetime</span></span> | <span data-ttu-id="fea5c-160">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="fea5c-160">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="fea5c-161">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-161">string</span></span> | <span data-ttu-id="fea5c-162">包含初始化事件之處理 (映射檔) 程式的資料夾</span><span class="sxs-lookup"><span data-stu-id="fea5c-162">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="fea5c-163">int</span><span class="sxs-lookup"><span data-stu-id="fea5c-163">int</span></span> | <span data-ttu-id="fea5c-164">產生負責事件之處理常式之父進程的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="fea5c-164">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="fea5c-165">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-165">string</span></span> | <span data-ttu-id="fea5c-166">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="fea5c-166">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="fea5c-167">datetime</span><span class="sxs-lookup"><span data-stu-id="fea5c-167">datetime</span></span> | <span data-ttu-id="fea5c-168">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="fea5c-168">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="fea5c-169">long</span><span class="sxs-lookup"><span data-stu-id="fea5c-169">long</span></span> | <span data-ttu-id="fea5c-170">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="fea5c-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="fea5c-171">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="fea5c-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="fea5c-172">string</span><span class="sxs-lookup"><span data-stu-id="fea5c-172">string</span></span> | <span data-ttu-id="fea5c-173">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="fea5c-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fea5c-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="fea5c-174">Related topics</span></span>
- [<span data-ttu-id="fea5c-175">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="fea5c-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fea5c-176">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="fea5c-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fea5c-177">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="fea5c-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fea5c-178">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="fea5c-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fea5c-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="fea5c-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fea5c-180">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="fea5c-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
