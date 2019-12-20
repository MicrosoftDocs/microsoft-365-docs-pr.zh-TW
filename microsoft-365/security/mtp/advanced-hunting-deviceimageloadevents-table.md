---
title: DeviceImageLoadEvents 資料表中的進階的狩獵結構描述
description: 了解 loading 事件的進階的狩獵結構描述的 DeviceImageLoadEvents 資料表中的 DLL
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 imageloadevents，DeviceImageLoadEvents、 DLL 載入、 文件庫、 檔案影像
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fdb69ee2e53372fdc486679831704c98202dddfe
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809251"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="83228-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="83228-104">DeviceImageLoadEvents</span></span>

<span data-ttu-id="83228-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="83228-105">**Applies to:**</span></span>
- <span data-ttu-id="83228-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="83228-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="83228-107">`DeviceImageLoadEvents` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含 DLL loading 事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="83228-107">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="83228-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="83228-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="83228-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="83228-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="83228-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="83228-110">Column name</span></span> | <span data-ttu-id="83228-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="83228-111">Data type</span></span> | <span data-ttu-id="83228-112">描述</span><span class="sxs-lookup"><span data-stu-id="83228-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="83228-113">datetime</span><span class="sxs-lookup"><span data-stu-id="83228-113">datetime</span></span> | <span data-ttu-id="83228-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="83228-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="83228-115">string</span><span class="sxs-lookup"><span data-stu-id="83228-115">string</span></span> | <span data-ttu-id="83228-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="83228-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="83228-117">string</span><span class="sxs-lookup"><span data-stu-id="83228-117">string</span></span> | <span data-ttu-id="83228-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="83228-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="83228-119">string</span><span class="sxs-lookup"><span data-stu-id="83228-119">string</span></span> | <span data-ttu-id="83228-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="83228-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="83228-121">string</span><span class="sxs-lookup"><span data-stu-id="83228-121">string</span></span> | <span data-ttu-id="83228-122">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="83228-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="83228-123">string</span><span class="sxs-lookup"><span data-stu-id="83228-123">string</span></span> | <span data-ttu-id="83228-124">包含已錄製的巨集指令所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="83228-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="83228-125">字串</span><span class="sxs-lookup"><span data-stu-id="83228-125">string</span></span> | <span data-ttu-id="83228-126">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="83228-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="83228-127">字串</span><span class="sxs-lookup"><span data-stu-id="83228-127">string</span></span> | <span data-ttu-id="83228-128">錄製巨集指令所套用之檔案的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="83228-128">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="83228-129">string</span><span class="sxs-lookup"><span data-stu-id="83228-129">string</span></span> | <span data-ttu-id="83228-130">執行負責事件程序的帳戶網域</span><span class="sxs-lookup"><span data-stu-id="83228-130">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="83228-131">string</span><span class="sxs-lookup"><span data-stu-id="83228-131">string</span></span> | <span data-ttu-id="83228-132">執行負責事件程序的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="83228-132">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="83228-133">string</span><span class="sxs-lookup"><span data-stu-id="83228-133">string</span></span> | <span data-ttu-id="83228-134">安全性識別碼 (SID) 執行負責事件程序的帳戶</span><span class="sxs-lookup"><span data-stu-id="83228-134">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="83228-135">string</span><span class="sxs-lookup"><span data-stu-id="83228-135">string</span></span> | <span data-ttu-id="83228-136">初始化事件程序的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="83228-136">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="83228-137">Windows 會指派完整性層級根據若干特質程序，例如如果他們已啟動從網際網路下載。</span><span class="sxs-lookup"><span data-stu-id="83228-137">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="83228-138">這些完整性層級影響資源的權限</span><span class="sxs-lookup"><span data-stu-id="83228-138">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="83228-139">string</span><span class="sxs-lookup"><span data-stu-id="83228-139">string</span></span> | <span data-ttu-id="83228-140">指出使用者存取控制 (UAC) 提高權限套用至初始化事件程序存在的 token 型別</span><span class="sxs-lookup"><span data-stu-id="83228-140">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="83228-141">string</span><span class="sxs-lookup"><span data-stu-id="83228-141">string</span></span> | <span data-ttu-id="83228-142">SHA-1 起始之事件程序 （影像檔案）</span><span class="sxs-lookup"><span data-stu-id="83228-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="83228-143">string</span><span class="sxs-lookup"><span data-stu-id="83228-143">string</span></span> | <span data-ttu-id="83228-144">初始化事件程序 （影像檔案） 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="83228-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="83228-145">string</span><span class="sxs-lookup"><span data-stu-id="83228-145">string</span></span> | <span data-ttu-id="83228-146">初始化事件的處理序名稱</span><span class="sxs-lookup"><span data-stu-id="83228-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="83228-147">int</span><span class="sxs-lookup"><span data-stu-id="83228-147">int</span></span> | <span data-ttu-id="83228-148">處理程序識別碼 (PID) 的起始事件程序</span><span class="sxs-lookup"><span data-stu-id="83228-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="83228-149">string</span><span class="sxs-lookup"><span data-stu-id="83228-149">string</span></span> | <span data-ttu-id="83228-150">用來執行初始化事件程序的命令列</span><span class="sxs-lookup"><span data-stu-id="83228-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="83228-151">datetime</span><span class="sxs-lookup"><span data-stu-id="83228-151">datetime</span></span> | <span data-ttu-id="83228-152">初始化事件程序時已開始日期和時間</span><span class="sxs-lookup"><span data-stu-id="83228-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="83228-153">string</span><span class="sxs-lookup"><span data-stu-id="83228-153">string</span></span> | <span data-ttu-id="83228-154">包含起始事件程序 （影像檔案） 的資料夾</span><span class="sxs-lookup"><span data-stu-id="83228-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="83228-155">int</span><span class="sxs-lookup"><span data-stu-id="83228-155">int</span></span> | <span data-ttu-id="83228-156">處理程序識別碼 (PID) 的產生處理程序負責事件父處理序</span><span class="sxs-lookup"><span data-stu-id="83228-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="83228-157">string</span><span class="sxs-lookup"><span data-stu-id="83228-157">string</span></span> | <span data-ttu-id="83228-158">產生負責事件程序的父處理序名稱</span><span class="sxs-lookup"><span data-stu-id="83228-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="83228-159">datetime</span><span class="sxs-lookup"><span data-stu-id="83228-159">datetime</span></span> | <span data-ttu-id="83228-160">日期和時間的父代負責事件程序已啟動時</span><span class="sxs-lookup"><span data-stu-id="83228-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="83228-161">long</span><span class="sxs-lookup"><span data-stu-id="83228-161">long</span></span> | <span data-ttu-id="83228-162">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="83228-162">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="83228-163">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="83228-163">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="83228-164">string</span><span class="sxs-lookup"><span data-stu-id="83228-164">string</span></span> | <span data-ttu-id="83228-165">虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼</span><span class="sxs-lookup"><span data-stu-id="83228-165">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="83228-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="83228-166">Related topics</span></span>
- [<span data-ttu-id="83228-167">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="83228-167">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="83228-168">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="83228-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="83228-169">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="83228-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="83228-170">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="83228-170">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="83228-171">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="83228-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="83228-172">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="83228-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
