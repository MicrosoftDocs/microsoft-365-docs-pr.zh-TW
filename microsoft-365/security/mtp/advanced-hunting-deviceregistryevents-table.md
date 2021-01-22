---
title: 進位搜尋架構中的 DeviceRegistryEvents 資料表
description: 瞭解可以從進位搜尋架構的 DeviceRegistryEvents 資料表查詢的註冊表事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料表、資料行、資料類型、註冊表、Registry、DeviceRegistryEvents、key、subkey、value
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
ms.openlocfilehash: 376e54fb4bf5f07a1c821ff436ddc8ec7dd25812
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931107"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="1b42d-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="1b42d-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1b42d-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="1b42d-105">**Applies to:**</span></span>
- <span data-ttu-id="1b42d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b42d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1b42d-107">進 `DeviceRegistryEvents` 位搜尋架構 [中的資料](advanced-hunting-overview.md) 表包含建立及修改登錄機碼目的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b42d-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="1b42d-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="1b42d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="1b42d-109">有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="1b42d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="1b42d-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="1b42d-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1b42d-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="1b42d-111">Column name</span></span> | <span data-ttu-id="1b42d-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="1b42d-112">Data type</span></span> | <span data-ttu-id="1b42d-113">描述</span><span class="sxs-lookup"><span data-stu-id="1b42d-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1b42d-114">datetime</span><span class="sxs-lookup"><span data-stu-id="1b42d-114">datetime</span></span> | <span data-ttu-id="1b42d-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="1b42d-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="1b42d-116">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-116">string</span></span> | <span data-ttu-id="1b42d-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="1b42d-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1b42d-118">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-118">string</span></span> | <span data-ttu-id="1b42d-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="1b42d-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="1b42d-120">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-120">string</span></span> | <span data-ttu-id="1b42d-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="1b42d-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="1b42d-122">請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="1b42d-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RegistryKey` | <span data-ttu-id="1b42d-123">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-123">string</span></span> | <span data-ttu-id="1b42d-124">已記錄動作所適用于的註冊表金鑰</span><span class="sxs-lookup"><span data-stu-id="1b42d-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="1b42d-125">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-125">string</span></span> | <span data-ttu-id="1b42d-126">所記錄動作所適用于之註冊表值的資料類型，例如二進位或字串</span><span class="sxs-lookup"><span data-stu-id="1b42d-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="1b42d-127">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-127">string</span></span> | <span data-ttu-id="1b42d-128">記錄的動作所使用之註冊表值的名稱</span><span class="sxs-lookup"><span data-stu-id="1b42d-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="1b42d-129">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-129">string</span></span> | <span data-ttu-id="1b42d-130">記錄的動作所適用于之註冊表值的資料</span><span class="sxs-lookup"><span data-stu-id="1b42d-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="1b42d-131">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-131">string</span></span> | <span data-ttu-id="1b42d-132">修改前之註冊表值的原始名稱</span><span class="sxs-lookup"><span data-stu-id="1b42d-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="1b42d-133">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-133">string</span></span> | <span data-ttu-id="1b42d-134">修改前之註冊表值的原始資料</span><span class="sxs-lookup"><span data-stu-id="1b42d-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="1b42d-135">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-135">string</span></span> | <span data-ttu-id="1b42d-136">執行負責事件之程式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="1b42d-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="1b42d-137">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-137">string</span></span> | <span data-ttu-id="1b42d-138">執行負責事件之程式之帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="1b42d-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="1b42d-139">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-139">string</span></span> | <span data-ttu-id="1b42d-140">執行 (之) 之帳戶的安全性識別碼為 SID</span><span class="sxs-lookup"><span data-stu-id="1b42d-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="1b42d-141">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-141">string</span></span> | <span data-ttu-id="1b42d-142">初始化活動的影像 (的 SHA-1) 影像檔案</span><span class="sxs-lookup"><span data-stu-id="1b42d-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="1b42d-143">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-143">string</span></span> | <span data-ttu-id="1b42d-144">初始化事件的 (的 SHA-256) 影像檔案。</span><span class="sxs-lookup"><span data-stu-id="1b42d-144">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="1b42d-145">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="1b42d-145">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="1b42d-146">字串</span><span class="sxs-lookup"><span data-stu-id="1b42d-146">string</span></span> | <span data-ttu-id="1b42d-147">初始化活動的 (圖像) MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="1b42d-147">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="1b42d-148">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-148">string</span></span> | <span data-ttu-id="1b42d-149">初始化事件之程式的名稱</span><span class="sxs-lookup"><span data-stu-id="1b42d-149">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="1b42d-150">int</span><span class="sxs-lookup"><span data-stu-id="1b42d-150">int</span></span> | <span data-ttu-id="1b42d-151">程式識別碼 (初始化) 的 PID 值</span><span class="sxs-lookup"><span data-stu-id="1b42d-151">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="1b42d-152">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-152">string</span></span> | <span data-ttu-id="1b42d-153">用來執行初始化事件的流程的命令列</span><span class="sxs-lookup"><span data-stu-id="1b42d-153">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="1b42d-154">datetime</span><span class="sxs-lookup"><span data-stu-id="1b42d-154">datetime</span></span> | <span data-ttu-id="1b42d-155">啟動事件之程式開始的日期和時間</span><span class="sxs-lookup"><span data-stu-id="1b42d-155">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="1b42d-156">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-156">string</span></span> | <span data-ttu-id="1b42d-157">啟動事件之 (圖像) 的資料夾</span><span class="sxs-lookup"><span data-stu-id="1b42d-157">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="1b42d-158">int</span><span class="sxs-lookup"><span data-stu-id="1b42d-158">int</span></span> | <span data-ttu-id="1b42d-159">程式識別碼 (產生) 事件之父流程的 PID 值</span><span class="sxs-lookup"><span data-stu-id="1b42d-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="1b42d-160">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-160">string</span></span> | <span data-ttu-id="1b42d-161">指定事件所負責之程式之父程式的名稱</span><span class="sxs-lookup"><span data-stu-id="1b42d-161">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="1b42d-162">datetime</span><span class="sxs-lookup"><span data-stu-id="1b42d-162">datetime</span></span> | <span data-ttu-id="1b42d-163">事件負責之程式父項開始的日期和時間</span><span class="sxs-lookup"><span data-stu-id="1b42d-163">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="1b42d-164">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-164">string</span></span> | <span data-ttu-id="1b42d-165">初始化事件之程式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="1b42d-165">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="1b42d-166">Windows 會依據特定特性指派完整性層級給程式，例如從網際網路下載啟動程式。</span><span class="sxs-lookup"><span data-stu-id="1b42d-166">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="1b42d-167">這些完整性等級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="1b42d-167">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="1b42d-168">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-168">string</span></span> | <span data-ttu-id="1b42d-169">指出使用者存取控制存在或不存在的權杖類型 (UAC) 許可權提高已應用至初始化事件的流程</span><span class="sxs-lookup"><span data-stu-id="1b42d-169">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="1b42d-170">long</span><span class="sxs-lookup"><span data-stu-id="1b42d-170">long</span></span> | <span data-ttu-id="1b42d-171">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b42d-171">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="1b42d-172">若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="1b42d-172">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="1b42d-173">string</span><span class="sxs-lookup"><span data-stu-id="1b42d-173">string</span></span> | <span data-ttu-id="1b42d-174">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="1b42d-174">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1b42d-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="1b42d-175">Related topics</span></span>
- [<span data-ttu-id="1b42d-176">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="1b42d-176">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1b42d-177">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="1b42d-177">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1b42d-178">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="1b42d-178">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1b42d-179">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="1b42d-179">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1b42d-180">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="1b42d-180">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1b42d-181">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="1b42d-181">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
