---
title: Advanced 搜尋架構中的 DeviceNetworkEvents 表格
description: 深入瞭解您可以從高級搜尋架構的 DeviceNetworkEvents 表查詢的網路線上活動
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，column，data type，devicenetworkevents，NetworkCommunicationEvents，network connection，remote ip，local ip
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
ms.openlocfilehash: 892ffe59f0902938b5d248e11a967b46de9c30b3
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649046"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="31009-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="31009-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="31009-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="31009-105">**Applies to:**</span></span>
- <span data-ttu-id="31009-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="31009-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="31009-107">[！附注] `DeviceNetworkEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含有關網路連線和相關事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="31009-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="31009-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="31009-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="31009-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="31009-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="31009-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="31009-110">Column name</span></span> | <span data-ttu-id="31009-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="31009-111">Data type</span></span> | <span data-ttu-id="31009-112">描述</span><span class="sxs-lookup"><span data-stu-id="31009-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="31009-113">datetime</span><span class="sxs-lookup"><span data-stu-id="31009-113">datetime</span></span> | <span data-ttu-id="31009-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="31009-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="31009-115">string</span><span class="sxs-lookup"><span data-stu-id="31009-115">string</span></span> | <span data-ttu-id="31009-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="31009-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="31009-117">string</span><span class="sxs-lookup"><span data-stu-id="31009-117">string</span></span> | <span data-ttu-id="31009-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="31009-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="31009-119">string</span><span class="sxs-lookup"><span data-stu-id="31009-119">string</span></span> | <span data-ttu-id="31009-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="31009-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="31009-121">字串</span><span class="sxs-lookup"><span data-stu-id="31009-121">string</span></span> | <span data-ttu-id="31009-122">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="31009-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="31009-123">int</span><span class="sxs-lookup"><span data-stu-id="31009-123">int</span></span> | <span data-ttu-id="31009-124">連線的遠端裝置上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="31009-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="31009-125">字串</span><span class="sxs-lookup"><span data-stu-id="31009-125">string</span></span> | <span data-ttu-id="31009-126">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="31009-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="31009-127">字串</span><span class="sxs-lookup"><span data-stu-id="31009-127">string</span></span> | <span data-ttu-id="31009-128">指派給通訊期間使用之本機電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="31009-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="31009-129">int</span><span class="sxs-lookup"><span data-stu-id="31009-129">int</span></span> | <span data-ttu-id="31009-130">通訊期間使用的本機電腦上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="31009-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="31009-131">string</span><span class="sxs-lookup"><span data-stu-id="31009-131">string</span></span> | <span data-ttu-id="31009-132">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="31009-132">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="31009-133">string</span><span class="sxs-lookup"><span data-stu-id="31009-133">string</span></span> | <span data-ttu-id="31009-134">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="31009-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="31009-135">string</span><span class="sxs-lookup"><span data-stu-id="31009-135">string</span></span> | <span data-ttu-id="31009-136">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="31009-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="31009-137">string</span><span class="sxs-lookup"><span data-stu-id="31009-137">string</span></span> | <span data-ttu-id="31009-138">啟動事件) 的處理常式 (映射檔 SHA-1</span><span class="sxs-lookup"><span data-stu-id="31009-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="31009-139">string</span><span class="sxs-lookup"><span data-stu-id="31009-139">string</span></span> | <span data-ttu-id="31009-140">啟動事件) 的處理常式 (映射檔 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="31009-140">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="31009-141">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="31009-141">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="31009-142">字串</span><span class="sxs-lookup"><span data-stu-id="31009-142">string</span></span> | <span data-ttu-id="31009-143">啟動事件之程式 (映射檔) 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="31009-143">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="31009-144">string</span><span class="sxs-lookup"><span data-stu-id="31009-144">string</span></span> | <span data-ttu-id="31009-145">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="31009-145">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="31009-146">int</span><span class="sxs-lookup"><span data-stu-id="31009-146">int</span></span> | <span data-ttu-id="31009-147">啟動事件之程式的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="31009-147">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="31009-148">string</span><span class="sxs-lookup"><span data-stu-id="31009-148">string</span></span> | <span data-ttu-id="31009-149">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="31009-149">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="31009-150">datetime</span><span class="sxs-lookup"><span data-stu-id="31009-150">datetime</span></span> | <span data-ttu-id="31009-151">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="31009-151">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="31009-152">string</span><span class="sxs-lookup"><span data-stu-id="31009-152">string</span></span> | <span data-ttu-id="31009-153">包含初始化事件之處理 (映射檔) 程式的資料夾</span><span class="sxs-lookup"><span data-stu-id="31009-153">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="31009-154">string</span><span class="sxs-lookup"><span data-stu-id="31009-154">string</span></span> | <span data-ttu-id="31009-155">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="31009-155">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="31009-156">int</span><span class="sxs-lookup"><span data-stu-id="31009-156">int</span></span> | <span data-ttu-id="31009-157">產生負責事件之處理常式之父進程的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="31009-157">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="31009-158">datetime</span><span class="sxs-lookup"><span data-stu-id="31009-158">datetime</span></span> | <span data-ttu-id="31009-159">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="31009-159">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="31009-160">string</span><span class="sxs-lookup"><span data-stu-id="31009-160">string</span></span> | <span data-ttu-id="31009-161">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="31009-161">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="31009-162">string</span><span class="sxs-lookup"><span data-stu-id="31009-162">string</span></span> | <span data-ttu-id="31009-163">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="31009-163">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="31009-164">string</span><span class="sxs-lookup"><span data-stu-id="31009-164">string</span></span> | <span data-ttu-id="31009-165">執行事件負責處理之帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="31009-165">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="31009-166">string</span><span class="sxs-lookup"><span data-stu-id="31009-166">string</span></span> | <span data-ttu-id="31009-167">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="31009-167">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="31009-168">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="31009-168">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="31009-169">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="31009-169">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="31009-170">string</span><span class="sxs-lookup"><span data-stu-id="31009-170">string</span></span> | <span data-ttu-id="31009-171">指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。</span><span class="sxs-lookup"><span data-stu-id="31009-171">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="31009-172">long</span><span class="sxs-lookup"><span data-stu-id="31009-172">long</span></span> | <span data-ttu-id="31009-173">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="31009-173">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="31009-174">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="31009-174">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="31009-175">string</span><span class="sxs-lookup"><span data-stu-id="31009-175">string</span></span> | <span data-ttu-id="31009-176">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="31009-176">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="31009-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="31009-177">Related topics</span></span>
- [<span data-ttu-id="31009-178">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="31009-178">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="31009-179">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="31009-179">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="31009-180">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="31009-180">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="31009-181">跨裝置、電子郵件、應用程式及身分識別搜尋</span><span class="sxs-lookup"><span data-stu-id="31009-181">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="31009-182">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="31009-182">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="31009-183">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="31009-183">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
