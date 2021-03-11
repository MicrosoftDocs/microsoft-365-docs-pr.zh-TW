---
title: Advanced 搜尋架構中的 DeviceRegistryEvents 表格
description: 深入瞭解您可以從高級搜尋架構的 DeviceRegistryEvents 資料表查詢的登錄事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，registryevents，registry，DeviceRegistryEvents，key，子機碼，value
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
ms.openlocfilehash: 1102f16249841779fd5b7293f89fb0955f14a496
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712399"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="32506-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="32506-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="32506-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="32506-105">**Applies to:**</span></span>
- <span data-ttu-id="32506-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32506-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="32506-107">[！附注] `DeviceRegistryEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含建立及修改登錄專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="32506-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="32506-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="32506-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="32506-109">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的內建架構參照。</span><span class="sxs-lookup"><span data-stu-id="32506-109">For detailed information about the events types (`ActionType` values) supported by a table, use the  built-in schema reference available in the security center.</span></span>

<span data-ttu-id="32506-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="32506-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="32506-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="32506-111">Column name</span></span> | <span data-ttu-id="32506-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="32506-112">Data type</span></span> | <span data-ttu-id="32506-113">描述</span><span class="sxs-lookup"><span data-stu-id="32506-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="32506-114">datetime</span><span class="sxs-lookup"><span data-stu-id="32506-114">datetime</span></span> | <span data-ttu-id="32506-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="32506-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="32506-116">string</span><span class="sxs-lookup"><span data-stu-id="32506-116">string</span></span> | <span data-ttu-id="32506-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="32506-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="32506-118">string</span><span class="sxs-lookup"><span data-stu-id="32506-118">string</span></span> | <span data-ttu-id="32506-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="32506-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="32506-120">string</span><span class="sxs-lookup"><span data-stu-id="32506-120">string</span></span> | <span data-ttu-id="32506-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="32506-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="32506-122">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="32506-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RegistryKey` | <span data-ttu-id="32506-123">string</span><span class="sxs-lookup"><span data-stu-id="32506-123">string</span></span> | <span data-ttu-id="32506-124">套用錄製的動作所用的登錄機碼</span><span class="sxs-lookup"><span data-stu-id="32506-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="32506-125">string</span><span class="sxs-lookup"><span data-stu-id="32506-125">string</span></span> | <span data-ttu-id="32506-126">已錄製動作套用至之登錄值的資料類型，例如二進位或字串</span><span class="sxs-lookup"><span data-stu-id="32506-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="32506-127">string</span><span class="sxs-lookup"><span data-stu-id="32506-127">string</span></span> | <span data-ttu-id="32506-128">已錄製動作套用至之登錄值的名稱</span><span class="sxs-lookup"><span data-stu-id="32506-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="32506-129">string</span><span class="sxs-lookup"><span data-stu-id="32506-129">string</span></span> | <span data-ttu-id="32506-130">已錄製動作套用至之登錄值的資料</span><span class="sxs-lookup"><span data-stu-id="32506-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryKey` | <span data-ttu-id="32506-131">string</span><span class="sxs-lookup"><span data-stu-id="32506-131">string</span></span> | <span data-ttu-id="32506-132">修改之前登錄值的原始登錄機碼</span><span class="sxs-lookup"><span data-stu-id="32506-132">Original registry key of the registry value before it was modified</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="32506-133">string</span><span class="sxs-lookup"><span data-stu-id="32506-133">string</span></span> | <span data-ttu-id="32506-134">修改之前登錄值的原始名稱</span><span class="sxs-lookup"><span data-stu-id="32506-134">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="32506-135">string</span><span class="sxs-lookup"><span data-stu-id="32506-135">string</span></span> | <span data-ttu-id="32506-136">修改之前登錄值的原始資料</span><span class="sxs-lookup"><span data-stu-id="32506-136">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="32506-137">string</span><span class="sxs-lookup"><span data-stu-id="32506-137">string</span></span> | <span data-ttu-id="32506-138">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="32506-138">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="32506-139">string</span><span class="sxs-lookup"><span data-stu-id="32506-139">string</span></span> | <span data-ttu-id="32506-140">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="32506-140">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="32506-141">string</span><span class="sxs-lookup"><span data-stu-id="32506-141">string</span></span> | <span data-ttu-id="32506-142">執行事件負責處理之帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="32506-142">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="32506-143">string</span><span class="sxs-lookup"><span data-stu-id="32506-143">string</span></span> | <span data-ttu-id="32506-144">執行事件負責之帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="32506-144">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountObjectId` | <span data-ttu-id="32506-145">string</span><span class="sxs-lookup"><span data-stu-id="32506-145">string</span></span> | <span data-ttu-id="32506-146">執行負責事件之處理常式之使用者帳戶的 Azure AD 物件識別碼</span><span class="sxs-lookup"><span data-stu-id="32506-146">Azure AD object ID of the user account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="32506-147">string</span><span class="sxs-lookup"><span data-stu-id="32506-147">string</span></span> | <span data-ttu-id="32506-148">啟動事件) 的處理常式 (映射檔 SHA-1</span><span class="sxs-lookup"><span data-stu-id="32506-148">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="32506-149">string</span><span class="sxs-lookup"><span data-stu-id="32506-149">string</span></span> | <span data-ttu-id="32506-150">啟動事件) 的處理常式 (映射檔 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="32506-150">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="32506-151">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="32506-151">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="32506-152">字串</span><span class="sxs-lookup"><span data-stu-id="32506-152">string</span></span> | <span data-ttu-id="32506-153">啟動事件之程式 (映射檔) 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="32506-153">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="32506-154">string</span><span class="sxs-lookup"><span data-stu-id="32506-154">string</span></span> | <span data-ttu-id="32506-155">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="32506-155">Name of the process that initiated the event</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="32506-156">long</span><span class="sxs-lookup"><span data-stu-id="32506-156">long</span></span> | <span data-ttu-id="32506-157">執行事件處理常式的檔案大小</span><span class="sxs-lookup"><span data-stu-id="32506-157">Size of the file that ran the process responsible for the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="32506-158">int</span><span class="sxs-lookup"><span data-stu-id="32506-158">int</span></span> | <span data-ttu-id="32506-159">啟動事件之程式的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="32506-159">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="32506-160">string</span><span class="sxs-lookup"><span data-stu-id="32506-160">string</span></span> | <span data-ttu-id="32506-161">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="32506-161">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="32506-162">datetime</span><span class="sxs-lookup"><span data-stu-id="32506-162">datetime</span></span> | <span data-ttu-id="32506-163">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="32506-163">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="32506-164">string</span><span class="sxs-lookup"><span data-stu-id="32506-164">string</span></span> | <span data-ttu-id="32506-165">包含初始化事件之處理 (映射檔) 程式的資料夾</span><span class="sxs-lookup"><span data-stu-id="32506-165">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="32506-166">int</span><span class="sxs-lookup"><span data-stu-id="32506-166">int</span></span> | <span data-ttu-id="32506-167">產生負責事件之處理常式之父進程的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="32506-167">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="32506-168">string</span><span class="sxs-lookup"><span data-stu-id="32506-168">string</span></span> | <span data-ttu-id="32506-169">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="32506-169">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="32506-170">datetime</span><span class="sxs-lookup"><span data-stu-id="32506-170">datetime</span></span> | <span data-ttu-id="32506-171">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="32506-171">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="32506-172">string</span><span class="sxs-lookup"><span data-stu-id="32506-172">string</span></span> | <span data-ttu-id="32506-173">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="32506-173">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="32506-174">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="32506-174">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="32506-175">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="32506-175">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="32506-176">string</span><span class="sxs-lookup"><span data-stu-id="32506-176">string</span></span> | <span data-ttu-id="32506-177">指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。</span><span class="sxs-lookup"><span data-stu-id="32506-177">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="32506-178">long</span><span class="sxs-lookup"><span data-stu-id="32506-178">long</span></span> | <span data-ttu-id="32506-179">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="32506-179">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="32506-180">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="32506-180">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="32506-181">string</span><span class="sxs-lookup"><span data-stu-id="32506-181">string</span></span> | <span data-ttu-id="32506-182">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="32506-182">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="32506-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="32506-183">Related topics</span></span>
- [<span data-ttu-id="32506-184">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="32506-184">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="32506-185">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="32506-185">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="32506-186">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="32506-186">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="32506-187">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="32506-187">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="32506-188">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="32506-188">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="32506-189">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="32506-189">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
