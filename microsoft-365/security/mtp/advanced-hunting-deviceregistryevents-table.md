---
title: Advanced 搜尋架構中的 DeviceRegistryEvents 表格
description: 深入瞭解您可以從高級搜尋架構的 DeviceRegistryEvents 資料表查詢的登錄事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，registryevents，registry，DeviceRegistryEvents，key，子機碼，value
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
ms.openlocfilehash: 35544866b9ebad94b14300b3734ddb2335fd657e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899002"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="5dbe4-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="5dbe4-104">DeviceRegistryEvents</span></span>

<span data-ttu-id="5dbe4-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5dbe4-105">**Applies to:**</span></span>
- <span data-ttu-id="5dbe4-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="5dbe4-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5dbe4-107">[！附注] `DeviceRegistryEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含建立及修改登錄專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="5dbe4-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5dbe4-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5dbe4-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="5dbe4-110">Column name</span></span> | <span data-ttu-id="5dbe4-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="5dbe4-111">Data type</span></span> | <span data-ttu-id="5dbe4-112">描述</span><span class="sxs-lookup"><span data-stu-id="5dbe4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5dbe4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5dbe4-113">datetime</span></span> | <span data-ttu-id="5dbe4-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5dbe4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5dbe4-115">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-115">string</span></span> | <span data-ttu-id="5dbe4-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="5dbe4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5dbe4-117">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-117">string</span></span> | <span data-ttu-id="5dbe4-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="5dbe4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="5dbe4-119">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-119">string</span></span> | <span data-ttu-id="5dbe4-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="5dbe4-120">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="5dbe4-121">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-121">string</span></span> | <span data-ttu-id="5dbe4-122">套用錄製的動作所用的登錄機碼</span><span class="sxs-lookup"><span data-stu-id="5dbe4-122">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="5dbe4-123">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-123">string</span></span> | <span data-ttu-id="5dbe4-124">已錄製動作套用至之登錄值的資料類型，例如二進位或字串</span><span class="sxs-lookup"><span data-stu-id="5dbe4-124">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="5dbe4-125">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-125">string</span></span> | <span data-ttu-id="5dbe4-126">已錄製動作套用至之登錄值的名稱</span><span class="sxs-lookup"><span data-stu-id="5dbe4-126">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="5dbe4-127">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-127">string</span></span> | <span data-ttu-id="5dbe4-128">已錄製動作套用至之登錄值的資料</span><span class="sxs-lookup"><span data-stu-id="5dbe4-128">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="5dbe4-129">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-129">string</span></span> | <span data-ttu-id="5dbe4-130">修改之前登錄值的原始名稱</span><span class="sxs-lookup"><span data-stu-id="5dbe4-130">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="5dbe4-131">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-131">string</span></span> | <span data-ttu-id="5dbe4-132">修改之前登錄值的原始資料</span><span class="sxs-lookup"><span data-stu-id="5dbe4-132">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="5dbe4-133">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-133">string</span></span> | <span data-ttu-id="5dbe4-134">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="5dbe4-134">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="5dbe4-135">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-135">string</span></span> | <span data-ttu-id="5dbe4-136">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="5dbe4-136">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="5dbe4-137">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-137">string</span></span> | <span data-ttu-id="5dbe4-138">執行事件處理常式之帳戶的安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="5dbe4-138">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="5dbe4-139">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-139">string</span></span> | <span data-ttu-id="5dbe4-140">啟動事件之處理常式（映射檔）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5dbe4-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="5dbe4-141">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-141">string</span></span> | <span data-ttu-id="5dbe4-142">啟動事件之處理常式（映射檔）的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="5dbe4-143">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="5dbe4-144">字串</span><span class="sxs-lookup"><span data-stu-id="5dbe4-144">string</span></span> | <span data-ttu-id="5dbe4-145">啟動事件之處理常式（映射檔）的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="5dbe4-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="5dbe4-146">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-146">string</span></span> | <span data-ttu-id="5dbe4-147">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="5dbe4-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="5dbe4-148">int</span><span class="sxs-lookup"><span data-stu-id="5dbe4-148">int</span></span> | <span data-ttu-id="5dbe4-149">啟動事件之處理常式的進程識別碼（PID）</span><span class="sxs-lookup"><span data-stu-id="5dbe4-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="5dbe4-150">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-150">string</span></span> | <span data-ttu-id="5dbe4-151">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="5dbe4-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="5dbe4-152">datetime</span><span class="sxs-lookup"><span data-stu-id="5dbe4-152">datetime</span></span> | <span data-ttu-id="5dbe4-153">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5dbe4-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="5dbe4-154">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-154">string</span></span> | <span data-ttu-id="5dbe4-155">包含初始化事件之處理常式（映射檔）的資料夾</span><span class="sxs-lookup"><span data-stu-id="5dbe4-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="5dbe4-156">int</span><span class="sxs-lookup"><span data-stu-id="5dbe4-156">int</span></span> | <span data-ttu-id="5dbe4-157">產生負責事件之處理常式之父進程的進程識別碼（PID）</span><span class="sxs-lookup"><span data-stu-id="5dbe4-157">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="5dbe4-158">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-158">string</span></span> | <span data-ttu-id="5dbe4-159">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="5dbe4-159">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="5dbe4-160">datetime</span><span class="sxs-lookup"><span data-stu-id="5dbe4-160">datetime</span></span> | <span data-ttu-id="5dbe4-161">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5dbe4-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="5dbe4-162">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-162">string</span></span> | <span data-ttu-id="5dbe4-163">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-163">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="5dbe4-164">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-164">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="5dbe4-165">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="5dbe4-165">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="5dbe4-166">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-166">string</span></span> | <span data-ttu-id="5dbe4-167">指出是否要將使用者存取控制（UAC）許可權提升套用至啟動事件之處理常式的 Token 類型</span><span class="sxs-lookup"><span data-stu-id="5dbe4-167">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="5dbe4-168">long</span><span class="sxs-lookup"><span data-stu-id="5dbe4-168">long</span></span> | <span data-ttu-id="5dbe4-169">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="5dbe4-169">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5dbe4-170">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="5dbe4-170">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="5dbe4-171">string</span><span class="sxs-lookup"><span data-stu-id="5dbe4-171">string</span></span> | <span data-ttu-id="5dbe4-172">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="5dbe4-172">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5dbe4-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="5dbe4-173">Related topics</span></span>
- [<span data-ttu-id="5dbe4-174">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="5dbe4-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5dbe4-175">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="5dbe4-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5dbe4-176">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="5dbe4-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5dbe4-177">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="5dbe4-177">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5dbe4-178">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="5dbe4-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5dbe4-179">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="5dbe4-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
