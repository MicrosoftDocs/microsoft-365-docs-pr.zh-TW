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
ms.openlocfilehash: 98aac3d231e2c8630cb4721ee8012054ab90feef
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617137"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="de58c-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="de58c-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="de58c-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="de58c-105">**Applies to:**</span></span>
- <span data-ttu-id="de58c-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="de58c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="de58c-107">[！附注] `DeviceImageLoadEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含 DLL 載入事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="de58c-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="de58c-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="de58c-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="de58c-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="de58c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="de58c-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="de58c-110">Column name</span></span> | <span data-ttu-id="de58c-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="de58c-111">Data type</span></span> | <span data-ttu-id="de58c-112">描述</span><span class="sxs-lookup"><span data-stu-id="de58c-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="de58c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="de58c-113">datetime</span></span> | <span data-ttu-id="de58c-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="de58c-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="de58c-115">string</span><span class="sxs-lookup"><span data-stu-id="de58c-115">string</span></span> | <span data-ttu-id="de58c-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="de58c-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="de58c-117">string</span><span class="sxs-lookup"><span data-stu-id="de58c-117">string</span></span> | <span data-ttu-id="de58c-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="de58c-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="de58c-119">string</span><span class="sxs-lookup"><span data-stu-id="de58c-119">string</span></span> | <span data-ttu-id="de58c-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="de58c-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="de58c-121">string</span><span class="sxs-lookup"><span data-stu-id="de58c-121">string</span></span> | <span data-ttu-id="de58c-122">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="de58c-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="de58c-123">string</span><span class="sxs-lookup"><span data-stu-id="de58c-123">string</span></span> | <span data-ttu-id="de58c-124">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="de58c-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="de58c-125">string</span><span class="sxs-lookup"><span data-stu-id="de58c-125">string</span></span> | <span data-ttu-id="de58c-126">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="de58c-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="de58c-127">字串</span><span class="sxs-lookup"><span data-stu-id="de58c-127">string</span></span> | <span data-ttu-id="de58c-128">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="de58c-128">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="de58c-129">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="de58c-129">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="de58c-130">字串</span><span class="sxs-lookup"><span data-stu-id="de58c-130">string</span></span> | <span data-ttu-id="de58c-131">錄製的動作所套用的檔案 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="de58c-131">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="de58c-132">string</span><span class="sxs-lookup"><span data-stu-id="de58c-132">string</span></span> | <span data-ttu-id="de58c-133">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="de58c-133">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="de58c-134">string</span><span class="sxs-lookup"><span data-stu-id="de58c-134">string</span></span> | <span data-ttu-id="de58c-135">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="de58c-135">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="de58c-136">string</span><span class="sxs-lookup"><span data-stu-id="de58c-136">string</span></span> | <span data-ttu-id="de58c-137">執行事件處理常式之帳戶的安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="de58c-137">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="de58c-138">string</span><span class="sxs-lookup"><span data-stu-id="de58c-138">string</span></span> | <span data-ttu-id="de58c-139">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="de58c-139">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="de58c-140">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="de58c-140">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="de58c-141">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="de58c-141">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="de58c-142">string</span><span class="sxs-lookup"><span data-stu-id="de58c-142">string</span></span> | <span data-ttu-id="de58c-143">指出是否要將使用者存取控制（UAC）許可權提升套用至啟動事件之處理常式的 Token 類型</span><span class="sxs-lookup"><span data-stu-id="de58c-143">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="de58c-144">string</span><span class="sxs-lookup"><span data-stu-id="de58c-144">string</span></span> | <span data-ttu-id="de58c-145">啟動事件之處理常式（映射檔）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="de58c-145">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="de58c-146">string</span><span class="sxs-lookup"><span data-stu-id="de58c-146">string</span></span> | <span data-ttu-id="de58c-147">啟動事件之處理常式（映射檔）的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="de58c-147">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="de58c-148">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="de58c-148">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="de58c-149">字串</span><span class="sxs-lookup"><span data-stu-id="de58c-149">string</span></span> | <span data-ttu-id="de58c-150">啟動事件之處理常式（映射檔）的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="de58c-150">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="de58c-151">string</span><span class="sxs-lookup"><span data-stu-id="de58c-151">string</span></span> | <span data-ttu-id="de58c-152">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="de58c-152">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="de58c-153">int</span><span class="sxs-lookup"><span data-stu-id="de58c-153">int</span></span> | <span data-ttu-id="de58c-154">啟動事件之處理常式的進程識別碼（PID）</span><span class="sxs-lookup"><span data-stu-id="de58c-154">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="de58c-155">string</span><span class="sxs-lookup"><span data-stu-id="de58c-155">string</span></span> | <span data-ttu-id="de58c-156">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="de58c-156">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="de58c-157">datetime</span><span class="sxs-lookup"><span data-stu-id="de58c-157">datetime</span></span> | <span data-ttu-id="de58c-158">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="de58c-158">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="de58c-159">string</span><span class="sxs-lookup"><span data-stu-id="de58c-159">string</span></span> | <span data-ttu-id="de58c-160">包含初始化事件之處理常式（映射檔）的資料夾</span><span class="sxs-lookup"><span data-stu-id="de58c-160">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="de58c-161">int</span><span class="sxs-lookup"><span data-stu-id="de58c-161">int</span></span> | <span data-ttu-id="de58c-162">產生負責事件之處理常式之父進程的進程識別碼（PID）</span><span class="sxs-lookup"><span data-stu-id="de58c-162">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="de58c-163">string</span><span class="sxs-lookup"><span data-stu-id="de58c-163">string</span></span> | <span data-ttu-id="de58c-164">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="de58c-164">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="de58c-165">datetime</span><span class="sxs-lookup"><span data-stu-id="de58c-165">datetime</span></span> | <span data-ttu-id="de58c-166">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="de58c-166">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="de58c-167">long</span><span class="sxs-lookup"><span data-stu-id="de58c-167">long</span></span> | <span data-ttu-id="de58c-168">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="de58c-168">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="de58c-169">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="de58c-169">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="de58c-170">string</span><span class="sxs-lookup"><span data-stu-id="de58c-170">string</span></span> | <span data-ttu-id="de58c-171">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="de58c-171">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="de58c-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="de58c-172">Related topics</span></span>
- [<span data-ttu-id="de58c-173">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="de58c-173">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="de58c-174">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="de58c-174">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="de58c-175">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="de58c-175">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="de58c-176">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="de58c-176">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="de58c-177">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="de58c-177">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="de58c-178">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="de58c-178">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
