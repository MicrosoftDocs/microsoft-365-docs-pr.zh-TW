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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: a1a1dd5bbf39a3d95a01cc27169cf3987f5c788e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842663"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="97a46-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="97a46-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="97a46-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="97a46-105">**Applies to:**</span></span>
- <span data-ttu-id="97a46-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97a46-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="97a46-107">[！附注] `DeviceNetworkEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含有關網路連線和相關事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="97a46-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="97a46-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="97a46-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="97a46-109">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="97a46-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="97a46-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="97a46-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="97a46-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="97a46-111">Column name</span></span> | <span data-ttu-id="97a46-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="97a46-112">Data type</span></span> | <span data-ttu-id="97a46-113">描述</span><span class="sxs-lookup"><span data-stu-id="97a46-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="97a46-114">datetime</span><span class="sxs-lookup"><span data-stu-id="97a46-114">datetime</span></span> | <span data-ttu-id="97a46-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="97a46-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="97a46-116">string</span><span class="sxs-lookup"><span data-stu-id="97a46-116">string</span></span> | <span data-ttu-id="97a46-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="97a46-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="97a46-118">string</span><span class="sxs-lookup"><span data-stu-id="97a46-118">string</span></span> | <span data-ttu-id="97a46-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="97a46-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="97a46-120">string</span><span class="sxs-lookup"><span data-stu-id="97a46-120">string</span></span> | <span data-ttu-id="97a46-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="97a46-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="97a46-122">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="97a46-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="97a46-123">字串</span><span class="sxs-lookup"><span data-stu-id="97a46-123">string</span></span> | <span data-ttu-id="97a46-124">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="97a46-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="97a46-125">int</span><span class="sxs-lookup"><span data-stu-id="97a46-125">int</span></span> | <span data-ttu-id="97a46-126">連線的遠端裝置上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="97a46-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="97a46-127">字串</span><span class="sxs-lookup"><span data-stu-id="97a46-127">string</span></span> | <span data-ttu-id="97a46-128">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="97a46-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="97a46-129">字串</span><span class="sxs-lookup"><span data-stu-id="97a46-129">string</span></span> | <span data-ttu-id="97a46-130">指派給通訊期間使用之本機電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="97a46-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="97a46-131">int</span><span class="sxs-lookup"><span data-stu-id="97a46-131">int</span></span> | <span data-ttu-id="97a46-132">通訊期間使用的本機電腦上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="97a46-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="97a46-133">string</span><span class="sxs-lookup"><span data-stu-id="97a46-133">string</span></span> | <span data-ttu-id="97a46-134">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="97a46-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="97a46-135">string</span><span class="sxs-lookup"><span data-stu-id="97a46-135">string</span></span> | <span data-ttu-id="97a46-136">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="97a46-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="97a46-137">string</span><span class="sxs-lookup"><span data-stu-id="97a46-137">string</span></span> | <span data-ttu-id="97a46-138">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="97a46-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="97a46-139">string</span><span class="sxs-lookup"><span data-stu-id="97a46-139">string</span></span> | <span data-ttu-id="97a46-140">啟動事件) 的處理常式 (映射檔 SHA-1</span><span class="sxs-lookup"><span data-stu-id="97a46-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="97a46-141">string</span><span class="sxs-lookup"><span data-stu-id="97a46-141">string</span></span> | <span data-ttu-id="97a46-142">啟動事件) 的處理常式 (映射檔 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="97a46-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="97a46-143">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="97a46-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="97a46-144">字串</span><span class="sxs-lookup"><span data-stu-id="97a46-144">string</span></span> | <span data-ttu-id="97a46-145">啟動事件之程式 (映射檔) 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="97a46-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="97a46-146">string</span><span class="sxs-lookup"><span data-stu-id="97a46-146">string</span></span> | <span data-ttu-id="97a46-147">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="97a46-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="97a46-148">int</span><span class="sxs-lookup"><span data-stu-id="97a46-148">int</span></span> | <span data-ttu-id="97a46-149">啟動事件之程式的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="97a46-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="97a46-150">string</span><span class="sxs-lookup"><span data-stu-id="97a46-150">string</span></span> | <span data-ttu-id="97a46-151">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="97a46-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="97a46-152">datetime</span><span class="sxs-lookup"><span data-stu-id="97a46-152">datetime</span></span> | <span data-ttu-id="97a46-153">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="97a46-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="97a46-154">string</span><span class="sxs-lookup"><span data-stu-id="97a46-154">string</span></span> | <span data-ttu-id="97a46-155">包含初始化事件之處理 (映射檔) 程式的資料夾</span><span class="sxs-lookup"><span data-stu-id="97a46-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="97a46-156">string</span><span class="sxs-lookup"><span data-stu-id="97a46-156">string</span></span> | <span data-ttu-id="97a46-157">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="97a46-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="97a46-158">int</span><span class="sxs-lookup"><span data-stu-id="97a46-158">int</span></span> | <span data-ttu-id="97a46-159">產生負責事件之處理常式之父進程的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="97a46-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="97a46-160">datetime</span><span class="sxs-lookup"><span data-stu-id="97a46-160">datetime</span></span> | <span data-ttu-id="97a46-161">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="97a46-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="97a46-162">string</span><span class="sxs-lookup"><span data-stu-id="97a46-162">string</span></span> | <span data-ttu-id="97a46-163">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="97a46-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="97a46-164">string</span><span class="sxs-lookup"><span data-stu-id="97a46-164">string</span></span> | <span data-ttu-id="97a46-165">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="97a46-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="97a46-166">string</span><span class="sxs-lookup"><span data-stu-id="97a46-166">string</span></span> | <span data-ttu-id="97a46-167">執行事件負責處理之帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="97a46-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="97a46-168">string</span><span class="sxs-lookup"><span data-stu-id="97a46-168">string</span></span> | <span data-ttu-id="97a46-169">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="97a46-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="97a46-170">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="97a46-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="97a46-171">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="97a46-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="97a46-172">string</span><span class="sxs-lookup"><span data-stu-id="97a46-172">string</span></span> | <span data-ttu-id="97a46-173">指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。</span><span class="sxs-lookup"><span data-stu-id="97a46-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="97a46-174">long</span><span class="sxs-lookup"><span data-stu-id="97a46-174">long</span></span> | <span data-ttu-id="97a46-175">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="97a46-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="97a46-176">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="97a46-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="97a46-177">string</span><span class="sxs-lookup"><span data-stu-id="97a46-177">string</span></span> | <span data-ttu-id="97a46-178">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="97a46-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="97a46-179">相關主題</span><span class="sxs-lookup"><span data-stu-id="97a46-179">Related topics</span></span>
- [<span data-ttu-id="97a46-180">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="97a46-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="97a46-181">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="97a46-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="97a46-182">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="97a46-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="97a46-183">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="97a46-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="97a46-184">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="97a46-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="97a46-185">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="97a46-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
