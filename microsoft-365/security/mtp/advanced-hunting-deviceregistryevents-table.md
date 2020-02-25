---
title: DeviceRegistryEvents 資料表中的進階的狩獵結構描述
description: 了解您可以從 DeviceRegistryEvents 資料表的進階的狩獵結構描述查詢的登錄事件
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 registryevents、 登錄、 DeviceRegistryEvents，索引鍵，子機碼，值
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
ms.openlocfilehash: c0b58d41996df2829590d7184615e8f30f4c4e16
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234802"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="e9a9e-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="e9a9e-104">DeviceRegistryEvents</span></span>

<span data-ttu-id="e9a9e-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e9a9e-105">**Applies to:**</span></span>
- <span data-ttu-id="e9a9e-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="e9a9e-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="e9a9e-107">`DeviceRegistryEvents` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含建立和修改登錄項目相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e9a9e-107">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="e9a9e-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="e9a9e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e9a9e-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="e9a9e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e9a9e-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="e9a9e-110">Column name</span></span> | <span data-ttu-id="e9a9e-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="e9a9e-111">Data type</span></span> | <span data-ttu-id="e9a9e-112">描述</span><span class="sxs-lookup"><span data-stu-id="e9a9e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e9a9e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e9a9e-113">datetime</span></span> | <span data-ttu-id="e9a9e-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="e9a9e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="e9a9e-115">字串</span><span class="sxs-lookup"><span data-stu-id="e9a9e-115">string</span></span> | <span data-ttu-id="e9a9e-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e9a9e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e9a9e-117">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-117">string</span></span> | <span data-ttu-id="e9a9e-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e9a9e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="e9a9e-119">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-119">string</span></span> | <span data-ttu-id="e9a9e-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="e9a9e-120">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="e9a9e-121">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-121">string</span></span> | <span data-ttu-id="e9a9e-122">錄製巨集指令所套用的登錄機碼</span><span class="sxs-lookup"><span data-stu-id="e9a9e-122">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="e9a9e-123">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-123">string</span></span> | <span data-ttu-id="e9a9e-124">二進制資料或錄製的巨集指令所套用的登錄值的字串，例如資料類型</span><span class="sxs-lookup"><span data-stu-id="e9a9e-124">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="e9a9e-125">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-125">string</span></span> | <span data-ttu-id="e9a9e-126">錄製巨集指令所套用的登錄值的名稱</span><span class="sxs-lookup"><span data-stu-id="e9a9e-126">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="e9a9e-127">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-127">string</span></span> | <span data-ttu-id="e9a9e-128">錄製巨集指令所套用的登錄值的資料</span><span class="sxs-lookup"><span data-stu-id="e9a9e-128">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="e9a9e-129">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-129">string</span></span> | <span data-ttu-id="e9a9e-130">登錄值之前修改它的原始名稱</span><span class="sxs-lookup"><span data-stu-id="e9a9e-130">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="e9a9e-131">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-131">string</span></span> | <span data-ttu-id="e9a9e-132">登錄值之前修改它的原始資料</span><span class="sxs-lookup"><span data-stu-id="e9a9e-132">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="e9a9e-133">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-133">string</span></span> | <span data-ttu-id="e9a9e-134">執行負責事件程序的帳戶網域</span><span class="sxs-lookup"><span data-stu-id="e9a9e-134">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="e9a9e-135">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-135">string</span></span> | <span data-ttu-id="e9a9e-136">執行負責事件程序的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="e9a9e-136">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="e9a9e-137">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-137">string</span></span> | <span data-ttu-id="e9a9e-138">安全性識別碼 (SID) 執行負責事件程序的帳戶</span><span class="sxs-lookup"><span data-stu-id="e9a9e-138">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="e9a9e-139">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-139">string</span></span> | <span data-ttu-id="e9a9e-140">SHA-1 起始之事件程序 （影像檔案）</span><span class="sxs-lookup"><span data-stu-id="e9a9e-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="e9a9e-141">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-141">string</span></span> | <span data-ttu-id="e9a9e-142">初始化事件程序 （影像檔案） 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="e9a9e-142">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="e9a9e-143">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-143">string</span></span> | <span data-ttu-id="e9a9e-144">初始化事件的處理序名稱</span><span class="sxs-lookup"><span data-stu-id="e9a9e-144">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="e9a9e-145">int</span><span class="sxs-lookup"><span data-stu-id="e9a9e-145">int</span></span> | <span data-ttu-id="e9a9e-146">處理程序識別碼 (PID) 的起始事件程序</span><span class="sxs-lookup"><span data-stu-id="e9a9e-146">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="e9a9e-147">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-147">string</span></span> | <span data-ttu-id="e9a9e-148">用來執行初始化事件程序的命令列</span><span class="sxs-lookup"><span data-stu-id="e9a9e-148">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="e9a9e-149">datetime</span><span class="sxs-lookup"><span data-stu-id="e9a9e-149">datetime</span></span> | <span data-ttu-id="e9a9e-150">初始化事件程序時已開始日期和時間</span><span class="sxs-lookup"><span data-stu-id="e9a9e-150">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="e9a9e-151">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-151">string</span></span> | <span data-ttu-id="e9a9e-152">包含起始事件程序 （影像檔案） 的資料夾</span><span class="sxs-lookup"><span data-stu-id="e9a9e-152">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="e9a9e-153">int</span><span class="sxs-lookup"><span data-stu-id="e9a9e-153">int</span></span> | <span data-ttu-id="e9a9e-154">處理程序識別碼 (PID) 的產生處理程序負責事件父處理序</span><span class="sxs-lookup"><span data-stu-id="e9a9e-154">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="e9a9e-155">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-155">string</span></span> | <span data-ttu-id="e9a9e-156">產生負責事件程序的父處理序名稱</span><span class="sxs-lookup"><span data-stu-id="e9a9e-156">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="e9a9e-157">datetime</span><span class="sxs-lookup"><span data-stu-id="e9a9e-157">datetime</span></span> | <span data-ttu-id="e9a9e-158">日期和時間的父代負責事件程序已啟動時</span><span class="sxs-lookup"><span data-stu-id="e9a9e-158">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="e9a9e-159">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-159">string</span></span> | <span data-ttu-id="e9a9e-160">初始化事件程序的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="e9a9e-160">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="e9a9e-161">Windows 會指派完整性層級根據若干特質程序，例如如果他們已啟動從網際網路下載。</span><span class="sxs-lookup"><span data-stu-id="e9a9e-161">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="e9a9e-162">這些完整性層級影響資源的權限</span><span class="sxs-lookup"><span data-stu-id="e9a9e-162">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="e9a9e-163">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-163">string</span></span> | <span data-ttu-id="e9a9e-164">指出使用者存取控制 (UAC) 提高權限套用至初始化事件程序存在的 token 型別</span><span class="sxs-lookup"><span data-stu-id="e9a9e-164">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="e9a9e-165">long</span><span class="sxs-lookup"><span data-stu-id="e9a9e-165">long</span></span> | <span data-ttu-id="e9a9e-166">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="e9a9e-166">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="e9a9e-167">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="e9a9e-167">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="e9a9e-168">string</span><span class="sxs-lookup"><span data-stu-id="e9a9e-168">string</span></span> | <span data-ttu-id="e9a9e-169">虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼</span><span class="sxs-lookup"><span data-stu-id="e9a9e-169">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e9a9e-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="e9a9e-170">Related topics</span></span>
- [<span data-ttu-id="e9a9e-171">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="e9a9e-171">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9a9e-172">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="e9a9e-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e9a9e-173">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="e9a9e-173">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e9a9e-174">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="e9a9e-174">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e9a9e-175">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="e9a9e-175">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e9a9e-176">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="e9a9e-176">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
