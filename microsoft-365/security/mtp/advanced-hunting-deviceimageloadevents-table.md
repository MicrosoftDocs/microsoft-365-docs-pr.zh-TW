---
title: DeviceImageLoadEvents 資料表中的進階的狩獵結構描述
description: 了解 loading 事件的進階的狩獵結構描述的 DeviceImageLoadEvents 資料表中的 DLL
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 imageloadevents，DeviceImageLoadEvents、 載入 DLL文件庫，檔案影像
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
ms.openlocfilehash: e3f51cfbe19a7b487f7382f0d2534b4a5efaab95
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235052"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="cdd82-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="cdd82-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="cdd82-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cdd82-105">**Applies to:**</span></span>
- <span data-ttu-id="cdd82-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="cdd82-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="cdd82-107">`DeviceImageLoadEvents` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含 DLL loading 事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cdd82-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="cdd82-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="cdd82-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="cdd82-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="cdd82-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cdd82-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="cdd82-110">Column name</span></span> | <span data-ttu-id="cdd82-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="cdd82-111">Data type</span></span> | <span data-ttu-id="cdd82-112">描述</span><span class="sxs-lookup"><span data-stu-id="cdd82-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="cdd82-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cdd82-113">datetime</span></span> | <span data-ttu-id="cdd82-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="cdd82-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="cdd82-115">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-115">string</span></span> | <span data-ttu-id="cdd82-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="cdd82-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="cdd82-117">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-117">string</span></span> | <span data-ttu-id="cdd82-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="cdd82-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="cdd82-119">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-119">string</span></span> | <span data-ttu-id="cdd82-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="cdd82-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="cdd82-121">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-121">string</span></span> | <span data-ttu-id="cdd82-122">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="cdd82-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="cdd82-123">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-123">string</span></span> | <span data-ttu-id="cdd82-124">包含已錄製的巨集指令所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="cdd82-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="cdd82-125">字串</span><span class="sxs-lookup"><span data-stu-id="cdd82-125">string</span></span> | <span data-ttu-id="cdd82-126">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="cdd82-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="cdd82-127">字串</span><span class="sxs-lookup"><span data-stu-id="cdd82-127">string</span></span> | <span data-ttu-id="cdd82-128">錄製巨集指令所套用之檔案的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="cdd82-128">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="cdd82-129">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-129">string</span></span> | <span data-ttu-id="cdd82-130">執行負責事件程序的帳戶網域</span><span class="sxs-lookup"><span data-stu-id="cdd82-130">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="cdd82-131">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-131">string</span></span> | <span data-ttu-id="cdd82-132">執行負責事件程序的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="cdd82-132">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="cdd82-133">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-133">string</span></span> | <span data-ttu-id="cdd82-134">安全性識別碼 (SID) 執行負責事件程序的帳戶</span><span class="sxs-lookup"><span data-stu-id="cdd82-134">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="cdd82-135">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-135">string</span></span> | <span data-ttu-id="cdd82-136">初始化事件程序的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="cdd82-136">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="cdd82-137">Windows 會指派完整性層級根據若干特質程序，例如如果他們已啟動從網際網路下載。</span><span class="sxs-lookup"><span data-stu-id="cdd82-137">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="cdd82-138">這些完整性層級影響資源的權限</span><span class="sxs-lookup"><span data-stu-id="cdd82-138">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="cdd82-139">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-139">string</span></span> | <span data-ttu-id="cdd82-140">指出使用者存取控制 (UAC) 提高權限套用至初始化事件程序存在的 token 型別</span><span class="sxs-lookup"><span data-stu-id="cdd82-140">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="cdd82-141">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-141">string</span></span> | <span data-ttu-id="cdd82-142">SHA-1 起始之事件程序 （影像檔案）</span><span class="sxs-lookup"><span data-stu-id="cdd82-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="cdd82-143">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-143">string</span></span> | <span data-ttu-id="cdd82-144">初始化事件程序 （影像檔案） 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="cdd82-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="cdd82-145">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-145">string</span></span> | <span data-ttu-id="cdd82-146">初始化事件的處理序名稱</span><span class="sxs-lookup"><span data-stu-id="cdd82-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="cdd82-147">int</span><span class="sxs-lookup"><span data-stu-id="cdd82-147">int</span></span> | <span data-ttu-id="cdd82-148">處理程序識別碼 (PID) 的起始事件程序</span><span class="sxs-lookup"><span data-stu-id="cdd82-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="cdd82-149">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-149">string</span></span> | <span data-ttu-id="cdd82-150">用來執行初始化事件程序的命令列</span><span class="sxs-lookup"><span data-stu-id="cdd82-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="cdd82-151">datetime</span><span class="sxs-lookup"><span data-stu-id="cdd82-151">datetime</span></span> | <span data-ttu-id="cdd82-152">初始化事件程序時已開始日期和時間</span><span class="sxs-lookup"><span data-stu-id="cdd82-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="cdd82-153">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-153">string</span></span> | <span data-ttu-id="cdd82-154">包含起始事件程序 （影像檔案） 的資料夾</span><span class="sxs-lookup"><span data-stu-id="cdd82-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="cdd82-155">int</span><span class="sxs-lookup"><span data-stu-id="cdd82-155">int</span></span> | <span data-ttu-id="cdd82-156">處理程序識別碼 (PID) 的產生處理程序負責事件父處理序</span><span class="sxs-lookup"><span data-stu-id="cdd82-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="cdd82-157">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-157">string</span></span> | <span data-ttu-id="cdd82-158">產生負責事件程序的父處理序名稱</span><span class="sxs-lookup"><span data-stu-id="cdd82-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="cdd82-159">datetime</span><span class="sxs-lookup"><span data-stu-id="cdd82-159">datetime</span></span> | <span data-ttu-id="cdd82-160">日期和時間的父代負責事件程序已啟動時</span><span class="sxs-lookup"><span data-stu-id="cdd82-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="cdd82-161">long</span><span class="sxs-lookup"><span data-stu-id="cdd82-161">long</span></span> | <span data-ttu-id="cdd82-162">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="cdd82-162">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="cdd82-163">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="cdd82-163">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="cdd82-164">string</span><span class="sxs-lookup"><span data-stu-id="cdd82-164">string</span></span> | <span data-ttu-id="cdd82-165">虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼</span><span class="sxs-lookup"><span data-stu-id="cdd82-165">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cdd82-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="cdd82-166">Related topics</span></span>
- [<span data-ttu-id="cdd82-167">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="cdd82-167">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cdd82-168">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="cdd82-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cdd82-169">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="cdd82-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cdd82-170">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="cdd82-170">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cdd82-171">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="cdd82-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cdd82-172">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="cdd82-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
