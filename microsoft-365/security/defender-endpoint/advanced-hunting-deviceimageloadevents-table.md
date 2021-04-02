---
title: Advanced 搜尋架構中的 DeviceImageLoadEvents 表格
description: 瞭解在高級搜尋架構的 DeviceImageLoadEvents 資料表中載入 DLL 的事件
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、deviceimageloadevents、DLL 載入、文件庫、檔案影像、ImageLoadEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b47996da16b131d1739acd26519447b9167870ec
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498783"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="1f998-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="1f998-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1f998-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1f998-105">**Applies to:**</span></span>
- [<span data-ttu-id="1f998-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1f998-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="1f998-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="1f998-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1f998-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1f998-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="1f998-109">[！附注] `DeviceImageLoadEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含 DLL 載入事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1f998-109">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="1f998-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="1f998-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="1f998-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="1f998-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="1f998-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="1f998-112">Column name</span></span> | <span data-ttu-id="1f998-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="1f998-113">Data type</span></span> | <span data-ttu-id="1f998-114">描述</span><span class="sxs-lookup"><span data-stu-id="1f998-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1f998-115">datetime</span><span class="sxs-lookup"><span data-stu-id="1f998-115">datetime</span></span> | <span data-ttu-id="1f998-116">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="1f998-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="1f998-117">string</span><span class="sxs-lookup"><span data-stu-id="1f998-117">string</span></span> | <span data-ttu-id="1f998-118">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="1f998-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1f998-119">string</span><span class="sxs-lookup"><span data-stu-id="1f998-119">string</span></span> | <span data-ttu-id="1f998-120">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="1f998-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="1f998-121">string</span><span class="sxs-lookup"><span data-stu-id="1f998-121">string</span></span> | <span data-ttu-id="1f998-122">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="1f998-122">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="1f998-123">字串</span><span class="sxs-lookup"><span data-stu-id="1f998-123">string</span></span> | <span data-ttu-id="1f998-124">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="1f998-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="1f998-125">字串</span><span class="sxs-lookup"><span data-stu-id="1f998-125">string</span></span> | <span data-ttu-id="1f998-126">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="1f998-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="1f998-127">字串</span><span class="sxs-lookup"><span data-stu-id="1f998-127">string</span></span> | <span data-ttu-id="1f998-128">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="1f998-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="1f998-129">字串</span><span class="sxs-lookup"><span data-stu-id="1f998-129">string</span></span> | <span data-ttu-id="1f998-130">錄製的動作所套用的檔案 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="1f998-130">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="1f998-131">string</span><span class="sxs-lookup"><span data-stu-id="1f998-131">string</span></span> | <span data-ttu-id="1f998-132">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="1f998-132">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="1f998-133">string</span><span class="sxs-lookup"><span data-stu-id="1f998-133">string</span></span> | <span data-ttu-id="1f998-134">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="1f998-134">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="1f998-135">string</span><span class="sxs-lookup"><span data-stu-id="1f998-135">string</span></span> | <span data-ttu-id="1f998-136">執行事件負責處理之帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="1f998-136">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="1f998-137">string</span><span class="sxs-lookup"><span data-stu-id="1f998-137">string</span></span> | <span data-ttu-id="1f998-138">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="1f998-138">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="1f998-139">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="1f998-139">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="1f998-140">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="1f998-140">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="1f998-141">string</span><span class="sxs-lookup"><span data-stu-id="1f998-141">string</span></span> | <span data-ttu-id="1f998-142">指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。</span><span class="sxs-lookup"><span data-stu-id="1f998-142">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="1f998-143">string</span><span class="sxs-lookup"><span data-stu-id="1f998-143">string</span></span> | <span data-ttu-id="1f998-144">啟動事件) 的處理常式 (映射檔 SHA-1</span><span class="sxs-lookup"><span data-stu-id="1f998-144">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="1f998-145">string</span><span class="sxs-lookup"><span data-stu-id="1f998-145">string</span></span> | <span data-ttu-id="1f998-146">啟動事件之程式 (映射檔) 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="1f998-146">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="1f998-147">string</span><span class="sxs-lookup"><span data-stu-id="1f998-147">string</span></span> | <span data-ttu-id="1f998-148">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="1f998-148">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="1f998-149">int</span><span class="sxs-lookup"><span data-stu-id="1f998-149">int</span></span> | <span data-ttu-id="1f998-150">啟動事件之程式的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="1f998-150">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="1f998-151">string</span><span class="sxs-lookup"><span data-stu-id="1f998-151">string</span></span> | <span data-ttu-id="1f998-152">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="1f998-152">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="1f998-153">datetime</span><span class="sxs-lookup"><span data-stu-id="1f998-153">datetime</span></span> | <span data-ttu-id="1f998-154">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="1f998-154">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="1f998-155">string</span><span class="sxs-lookup"><span data-stu-id="1f998-155">string</span></span> | <span data-ttu-id="1f998-156">包含初始化事件之處理 (映射檔) 程式的資料夾</span><span class="sxs-lookup"><span data-stu-id="1f998-156">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="1f998-157">int</span><span class="sxs-lookup"><span data-stu-id="1f998-157">int</span></span> | <span data-ttu-id="1f998-158">產生負責事件之處理常式之父進程的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="1f998-158">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="1f998-159">string</span><span class="sxs-lookup"><span data-stu-id="1f998-159">string</span></span> | <span data-ttu-id="1f998-160">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="1f998-160">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="1f998-161">datetime</span><span class="sxs-lookup"><span data-stu-id="1f998-161">datetime</span></span> | <span data-ttu-id="1f998-162">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="1f998-162">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="1f998-163">long</span><span class="sxs-lookup"><span data-stu-id="1f998-163">long</span></span> | <span data-ttu-id="1f998-164">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="1f998-164">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="1f998-165">若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用</span><span class="sxs-lookup"><span data-stu-id="1f998-165">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="1f998-166">string</span><span class="sxs-lookup"><span data-stu-id="1f998-166">string</span></span> | <span data-ttu-id="1f998-167">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="1f998-167">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1f998-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f998-168">Related topics</span></span>
- [<span data-ttu-id="1f998-169">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="1f998-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1f998-170">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="1f998-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1f998-171">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="1f998-171">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
