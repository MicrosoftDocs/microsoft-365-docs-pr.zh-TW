---
title: Advanced 搜尋架構中的 DeviceRegistryEvents 表格
description: 深入瞭解您可以從高級搜尋架構的 DeviceRegistryEvents 資料表查詢的登錄事件
keywords: 「高級搜尋」、「威脅搜尋」、「網路威脅搜尋」、「搜尋」、「查詢」、「遙測」、「架構參考」、「kusto」、「表格」、「資料類型」、「deviceregistryevents」、「註冊表
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 39ea04e2faa43d230ecdc281967b6a9e8f8c9abe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059768"
---
# <a name="deviceregistryevents"></a><span data-ttu-id="98425-104">DeviceRegistryEvents</span><span class="sxs-lookup"><span data-stu-id="98425-104">DeviceRegistryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98425-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="98425-105">**Applies to:**</span></span>
- [<span data-ttu-id="98425-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="98425-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="98425-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="98425-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98425-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="98425-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="98425-109">[！附注] `DeviceRegistryEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含建立及修改登錄專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="98425-109">The `DeviceRegistryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about the creation and modification of registry entries.</span></span> <span data-ttu-id="98425-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="98425-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="98425-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="98425-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="98425-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="98425-112">Column name</span></span> | <span data-ttu-id="98425-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="98425-113">Data type</span></span> | <span data-ttu-id="98425-114">描述</span><span class="sxs-lookup"><span data-stu-id="98425-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="98425-115">datetime</span><span class="sxs-lookup"><span data-stu-id="98425-115">datetime</span></span> | <span data-ttu-id="98425-116">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="98425-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="98425-117">string</span><span class="sxs-lookup"><span data-stu-id="98425-117">string</span></span> | <span data-ttu-id="98425-118">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="98425-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="98425-119">string</span><span class="sxs-lookup"><span data-stu-id="98425-119">string</span></span> | <span data-ttu-id="98425-120">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="98425-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="98425-121">string</span><span class="sxs-lookup"><span data-stu-id="98425-121">string</span></span> | <span data-ttu-id="98425-122">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="98425-122">Type of activity that triggered the event</span></span> |
| `RegistryKey` | <span data-ttu-id="98425-123">string</span><span class="sxs-lookup"><span data-stu-id="98425-123">string</span></span> | <span data-ttu-id="98425-124">套用錄製的動作所用的登錄機碼</span><span class="sxs-lookup"><span data-stu-id="98425-124">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueType` | <span data-ttu-id="98425-125">string</span><span class="sxs-lookup"><span data-stu-id="98425-125">string</span></span> | <span data-ttu-id="98425-126">已錄製動作套用至之登錄值的資料類型，例如二進位或字串</span><span class="sxs-lookup"><span data-stu-id="98425-126">Data type, such as binary or string, of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueName` | <span data-ttu-id="98425-127">string</span><span class="sxs-lookup"><span data-stu-id="98425-127">string</span></span> | <span data-ttu-id="98425-128">已錄製動作套用至之登錄值的名稱</span><span class="sxs-lookup"><span data-stu-id="98425-128">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` | <span data-ttu-id="98425-129">string</span><span class="sxs-lookup"><span data-stu-id="98425-129">string</span></span> | <span data-ttu-id="98425-130">已錄製動作套用至之登錄值的資料</span><span class="sxs-lookup"><span data-stu-id="98425-130">Data of the registry value that the recorded action was applied to</span></span> |
| `PreviousRegistryValueName` | <span data-ttu-id="98425-131">string</span><span class="sxs-lookup"><span data-stu-id="98425-131">string</span></span> | <span data-ttu-id="98425-132">修改之前登錄值的原始名稱</span><span class="sxs-lookup"><span data-stu-id="98425-132">Original name of the registry value before it was modified</span></span> |
| `PreviousRegistryValueData` | <span data-ttu-id="98425-133">string</span><span class="sxs-lookup"><span data-stu-id="98425-133">string</span></span> | <span data-ttu-id="98425-134">修改之前登錄值的原始資料</span><span class="sxs-lookup"><span data-stu-id="98425-134">Original data of the registry value before it was modified</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="98425-135">string</span><span class="sxs-lookup"><span data-stu-id="98425-135">string</span></span> | <span data-ttu-id="98425-136">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="98425-136">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="98425-137">string</span><span class="sxs-lookup"><span data-stu-id="98425-137">string</span></span> | <span data-ttu-id="98425-138">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="98425-138">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="98425-139">string</span><span class="sxs-lookup"><span data-stu-id="98425-139">string</span></span> | <span data-ttu-id="98425-140">執行事件負責處理之帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="98425-140">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="98425-141">string</span><span class="sxs-lookup"><span data-stu-id="98425-141">string</span></span> | <span data-ttu-id="98425-142">啟動事件) 的處理常式 (映射檔 SHA-1</span><span class="sxs-lookup"><span data-stu-id="98425-142">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="98425-143">string</span><span class="sxs-lookup"><span data-stu-id="98425-143">string</span></span> | <span data-ttu-id="98425-144">啟動事件之程式 (映射檔) 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="98425-144">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="98425-145">string</span><span class="sxs-lookup"><span data-stu-id="98425-145">string</span></span> | <span data-ttu-id="98425-146">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="98425-146">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="98425-147">int</span><span class="sxs-lookup"><span data-stu-id="98425-147">int</span></span> | <span data-ttu-id="98425-148">啟動事件之程式的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="98425-148">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="98425-149">string</span><span class="sxs-lookup"><span data-stu-id="98425-149">string</span></span> | <span data-ttu-id="98425-150">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="98425-150">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="98425-151">datetime</span><span class="sxs-lookup"><span data-stu-id="98425-151">datetime</span></span> | <span data-ttu-id="98425-152">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="98425-152">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="98425-153">string</span><span class="sxs-lookup"><span data-stu-id="98425-153">string</span></span> | <span data-ttu-id="98425-154">包含初始化事件之處理 (映射檔) 程式的資料夾</span><span class="sxs-lookup"><span data-stu-id="98425-154">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="98425-155">int</span><span class="sxs-lookup"><span data-stu-id="98425-155">int</span></span> | <span data-ttu-id="98425-156">產生負責事件之處理常式之父進程的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="98425-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="98425-157">string</span><span class="sxs-lookup"><span data-stu-id="98425-157">string</span></span> | <span data-ttu-id="98425-158">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="98425-158">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="98425-159">datetime</span><span class="sxs-lookup"><span data-stu-id="98425-159">datetime</span></span> | <span data-ttu-id="98425-160">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="98425-160">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="98425-161">string</span><span class="sxs-lookup"><span data-stu-id="98425-161">string</span></span> | <span data-ttu-id="98425-162">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="98425-162">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="98425-163">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="98425-163">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="98425-164">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="98425-164">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="98425-165">string</span><span class="sxs-lookup"><span data-stu-id="98425-165">string</span></span> | <span data-ttu-id="98425-166">指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。</span><span class="sxs-lookup"><span data-stu-id="98425-166">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="98425-167">long</span><span class="sxs-lookup"><span data-stu-id="98425-167">long</span></span> | <span data-ttu-id="98425-168">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="98425-168">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="98425-169">若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用</span><span class="sxs-lookup"><span data-stu-id="98425-169">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="98425-170">string</span><span class="sxs-lookup"><span data-stu-id="98425-170">string</span></span> | <span data-ttu-id="98425-171">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="98425-171">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="98425-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="98425-172">Related topics</span></span>
- [<span data-ttu-id="98425-173">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="98425-173">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98425-174">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="98425-174">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="98425-175">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="98425-175">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
