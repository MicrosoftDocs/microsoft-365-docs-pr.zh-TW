---
title: 進位搜尋架構中的 DeviceNetworkEvents 資料表
description: 瞭解可以從進位搜尋架構的 DeviceNetworkEvents 資料表查詢的網路連接事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、資料表、資料行、資料類型、devicenetworkevents、NetworkCommunicationEvents、網路連接、遠端 ip、local ip
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
ms.openlocfilehash: 0ed696f36737a4102895369e1254b4215cad4def
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931215"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="442c1-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="442c1-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="442c1-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="442c1-105">**Applies to:**</span></span>
- <span data-ttu-id="442c1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="442c1-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="442c1-107">進 `DeviceNetworkEvents` 位搜尋架構 [中的表格](advanced-hunting-overview.md) 包含網路連接和相關事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="442c1-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="442c1-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="442c1-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="442c1-109">有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="442c1-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="442c1-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="442c1-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="442c1-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="442c1-111">Column name</span></span> | <span data-ttu-id="442c1-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="442c1-112">Data type</span></span> | <span data-ttu-id="442c1-113">描述</span><span class="sxs-lookup"><span data-stu-id="442c1-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="442c1-114">datetime</span><span class="sxs-lookup"><span data-stu-id="442c1-114">datetime</span></span> | <span data-ttu-id="442c1-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="442c1-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="442c1-116">string</span><span class="sxs-lookup"><span data-stu-id="442c1-116">string</span></span> | <span data-ttu-id="442c1-117">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="442c1-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="442c1-118">string</span><span class="sxs-lookup"><span data-stu-id="442c1-118">string</span></span> | <span data-ttu-id="442c1-119">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="442c1-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="442c1-120">string</span><span class="sxs-lookup"><span data-stu-id="442c1-120">string</span></span> | <span data-ttu-id="442c1-121">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="442c1-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="442c1-122">請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="442c1-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `RemoteIP` | <span data-ttu-id="442c1-123">字串</span><span class="sxs-lookup"><span data-stu-id="442c1-123">string</span></span> | <span data-ttu-id="442c1-124">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="442c1-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="442c1-125">int</span><span class="sxs-lookup"><span data-stu-id="442c1-125">int</span></span> | <span data-ttu-id="442c1-126">正在連接之遠端裝置上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="442c1-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="442c1-127">字串</span><span class="sxs-lookup"><span data-stu-id="442c1-127">string</span></span> | <span data-ttu-id="442c1-128">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="442c1-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="442c1-129">字串</span><span class="sxs-lookup"><span data-stu-id="442c1-129">string</span></span> | <span data-ttu-id="442c1-130">指派給通訊期間使用的本機電腦之 IP 位址</span><span class="sxs-lookup"><span data-stu-id="442c1-130">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="442c1-131">int</span><span class="sxs-lookup"><span data-stu-id="442c1-131">int</span></span> | <span data-ttu-id="442c1-132">在通訊期間使用的本機電腦上 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="442c1-132">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="442c1-133">string</span><span class="sxs-lookup"><span data-stu-id="442c1-133">string</span></span> | <span data-ttu-id="442c1-134">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="442c1-134">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="442c1-135">string</span><span class="sxs-lookup"><span data-stu-id="442c1-135">string</span></span> | <span data-ttu-id="442c1-136">IP 位址類型，例如公用、私人、保留、Loopback、Teredo、FourToSixMapping 和 Broadcast</span><span class="sxs-lookup"><span data-stu-id="442c1-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="442c1-137">string</span><span class="sxs-lookup"><span data-stu-id="442c1-137">string</span></span> | <span data-ttu-id="442c1-138">IP 位址類型，例如公用、私人、保留、Loopback、Teredo、FourToSixMapping 和 Broadcast</span><span class="sxs-lookup"><span data-stu-id="442c1-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="442c1-139">string</span><span class="sxs-lookup"><span data-stu-id="442c1-139">string</span></span> | <span data-ttu-id="442c1-140">初始化活動的影像 (的 SHA-1) 影像檔案</span><span class="sxs-lookup"><span data-stu-id="442c1-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="442c1-141">string</span><span class="sxs-lookup"><span data-stu-id="442c1-141">string</span></span> | <span data-ttu-id="442c1-142">初始化事件的 (的 SHA-256) 影像檔案。</span><span class="sxs-lookup"><span data-stu-id="442c1-142">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="442c1-143">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="442c1-143">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="442c1-144">字串</span><span class="sxs-lookup"><span data-stu-id="442c1-144">string</span></span> | <span data-ttu-id="442c1-145">初始化活動的 (圖像) MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="442c1-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="442c1-146">string</span><span class="sxs-lookup"><span data-stu-id="442c1-146">string</span></span> | <span data-ttu-id="442c1-147">初始化事件之程式的名稱</span><span class="sxs-lookup"><span data-stu-id="442c1-147">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="442c1-148">int</span><span class="sxs-lookup"><span data-stu-id="442c1-148">int</span></span> | <span data-ttu-id="442c1-149">程式識別碼 (初始化) 的 PID 值</span><span class="sxs-lookup"><span data-stu-id="442c1-149">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="442c1-150">string</span><span class="sxs-lookup"><span data-stu-id="442c1-150">string</span></span> | <span data-ttu-id="442c1-151">用來執行初始化事件的流程的命令列</span><span class="sxs-lookup"><span data-stu-id="442c1-151">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="442c1-152">datetime</span><span class="sxs-lookup"><span data-stu-id="442c1-152">datetime</span></span> | <span data-ttu-id="442c1-153">啟動事件之程式開始的日期和時間</span><span class="sxs-lookup"><span data-stu-id="442c1-153">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="442c1-154">string</span><span class="sxs-lookup"><span data-stu-id="442c1-154">string</span></span> | <span data-ttu-id="442c1-155">啟動事件之 (圖像) 的資料夾</span><span class="sxs-lookup"><span data-stu-id="442c1-155">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="442c1-156">string</span><span class="sxs-lookup"><span data-stu-id="442c1-156">string</span></span> | <span data-ttu-id="442c1-157">指定事件所負責之程式之父程式的名稱</span><span class="sxs-lookup"><span data-stu-id="442c1-157">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="442c1-158">int</span><span class="sxs-lookup"><span data-stu-id="442c1-158">int</span></span> | <span data-ttu-id="442c1-159">程式識別碼 (產生) 事件之父流程的 PID 值</span><span class="sxs-lookup"><span data-stu-id="442c1-159">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="442c1-160">datetime</span><span class="sxs-lookup"><span data-stu-id="442c1-160">datetime</span></span> | <span data-ttu-id="442c1-161">事件負責之程式父項開始的日期和時間</span><span class="sxs-lookup"><span data-stu-id="442c1-161">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="442c1-162">string</span><span class="sxs-lookup"><span data-stu-id="442c1-162">string</span></span> | <span data-ttu-id="442c1-163">執行負責事件之程式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="442c1-163">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="442c1-164">string</span><span class="sxs-lookup"><span data-stu-id="442c1-164">string</span></span> | <span data-ttu-id="442c1-165">執行負責事件之程式之帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="442c1-165">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="442c1-166">string</span><span class="sxs-lookup"><span data-stu-id="442c1-166">string</span></span> | <span data-ttu-id="442c1-167">執行 (之) 之帳戶的安全性識別碼為 SID</span><span class="sxs-lookup"><span data-stu-id="442c1-167">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="442c1-168">string</span><span class="sxs-lookup"><span data-stu-id="442c1-168">string</span></span> | <span data-ttu-id="442c1-169">初始化事件之程式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="442c1-169">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="442c1-170">Windows 會依據特定特性指派完整性層級給程式，例如從網際網路下載啟動程式。</span><span class="sxs-lookup"><span data-stu-id="442c1-170">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="442c1-171">這些完整性等級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="442c1-171">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="442c1-172">string</span><span class="sxs-lookup"><span data-stu-id="442c1-172">string</span></span> | <span data-ttu-id="442c1-173">指出使用者存取控制存在或不存在的權杖類型 (UAC) 許可權提高已應用至初始化事件的流程</span><span class="sxs-lookup"><span data-stu-id="442c1-173">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="442c1-174">long</span><span class="sxs-lookup"><span data-stu-id="442c1-174">long</span></span> | <span data-ttu-id="442c1-175">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="442c1-175">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="442c1-176">若要識別唯一事件，此欄必須與 DeviceName 和 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="442c1-176">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="442c1-177">string</span><span class="sxs-lookup"><span data-stu-id="442c1-177">string</span></span> | <span data-ttu-id="442c1-178">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="442c1-178">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="442c1-179">相關主題</span><span class="sxs-lookup"><span data-stu-id="442c1-179">Related topics</span></span>
- [<span data-ttu-id="442c1-180">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="442c1-180">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="442c1-181">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="442c1-181">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="442c1-182">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="442c1-182">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="442c1-183">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="442c1-183">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="442c1-184">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="442c1-184">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="442c1-185">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="442c1-185">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
