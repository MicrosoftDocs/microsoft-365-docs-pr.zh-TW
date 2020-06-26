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
ms.openlocfilehash: d5d666bef07c6ae8c5a43b641a8e7f6a11f5457a
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899252"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="dedc2-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="dedc2-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="dedc2-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="dedc2-105">**Applies to:**</span></span>
- <span data-ttu-id="dedc2-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="dedc2-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="dedc2-107">[！附注] `DeviceNetworkEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含有關網路連線和相關事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="dedc2-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="dedc2-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="dedc2-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="dedc2-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="dedc2-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dedc2-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="dedc2-110">Column name</span></span> | <span data-ttu-id="dedc2-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="dedc2-111">Data type</span></span> | <span data-ttu-id="dedc2-112">描述</span><span class="sxs-lookup"><span data-stu-id="dedc2-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="dedc2-113">datetime</span><span class="sxs-lookup"><span data-stu-id="dedc2-113">datetime</span></span> | <span data-ttu-id="dedc2-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="dedc2-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="dedc2-115">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-115">string</span></span> | <span data-ttu-id="dedc2-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="dedc2-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="dedc2-117">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-117">string</span></span> | <span data-ttu-id="dedc2-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="dedc2-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="dedc2-119">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-119">string</span></span> | <span data-ttu-id="dedc2-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="dedc2-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="dedc2-121">字串</span><span class="sxs-lookup"><span data-stu-id="dedc2-121">string</span></span> | <span data-ttu-id="dedc2-122">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="dedc2-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="dedc2-123">int</span><span class="sxs-lookup"><span data-stu-id="dedc2-123">int</span></span> | <span data-ttu-id="dedc2-124">連線的遠端裝置上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="dedc2-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="dedc2-125">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-125">string</span></span> | <span data-ttu-id="dedc2-126">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="dedc2-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="dedc2-127">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-127">string</span></span> | <span data-ttu-id="dedc2-128">指派給通訊期間使用之本機電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="dedc2-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="dedc2-129">int</span><span class="sxs-lookup"><span data-stu-id="dedc2-129">int</span></span> | <span data-ttu-id="dedc2-130">通訊期間使用的本機電腦上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="dedc2-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="dedc2-131">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-131">string</span></span> | <span data-ttu-id="dedc2-132">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="dedc2-132">Protocol used during the communication</span></span> |
| `LocalIPType` | <span data-ttu-id="dedc2-133">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-133">string</span></span> | <span data-ttu-id="dedc2-134">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="dedc2-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="dedc2-135">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-135">string</span></span> | <span data-ttu-id="dedc2-136">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="dedc2-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="dedc2-137">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-137">string</span></span> | <span data-ttu-id="dedc2-138">啟動事件之處理常式（映射檔）的 SHA-1</span><span class="sxs-lookup"><span data-stu-id="dedc2-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="dedc2-139">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-139">string</span></span> | <span data-ttu-id="dedc2-140">啟動事件之處理常式（映射檔）的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="dedc2-140">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="dedc2-141">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="dedc2-141">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="dedc2-142">字串</span><span class="sxs-lookup"><span data-stu-id="dedc2-142">string</span></span> | <span data-ttu-id="dedc2-143">啟動事件之處理常式（映射檔）的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="dedc2-143">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="dedc2-144">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-144">string</span></span> | <span data-ttu-id="dedc2-145">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="dedc2-145">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="dedc2-146">int</span><span class="sxs-lookup"><span data-stu-id="dedc2-146">int</span></span> | <span data-ttu-id="dedc2-147">啟動事件之處理常式的進程識別碼（PID）</span><span class="sxs-lookup"><span data-stu-id="dedc2-147">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="dedc2-148">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-148">string</span></span> | <span data-ttu-id="dedc2-149">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="dedc2-149">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="dedc2-150">datetime</span><span class="sxs-lookup"><span data-stu-id="dedc2-150">datetime</span></span> | <span data-ttu-id="dedc2-151">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="dedc2-151">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="dedc2-152">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-152">string</span></span> | <span data-ttu-id="dedc2-153">包含初始化事件之處理常式（映射檔）的資料夾</span><span class="sxs-lookup"><span data-stu-id="dedc2-153">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="dedc2-154">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-154">string</span></span> | <span data-ttu-id="dedc2-155">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="dedc2-155">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="dedc2-156">int</span><span class="sxs-lookup"><span data-stu-id="dedc2-156">int</span></span> | <span data-ttu-id="dedc2-157">產生負責事件之處理常式之父進程的進程識別碼（PID）</span><span class="sxs-lookup"><span data-stu-id="dedc2-157">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="dedc2-158">datetime</span><span class="sxs-lookup"><span data-stu-id="dedc2-158">datetime</span></span> | <span data-ttu-id="dedc2-159">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="dedc2-159">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="dedc2-160">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-160">string</span></span> | <span data-ttu-id="dedc2-161">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="dedc2-161">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="dedc2-162">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-162">string</span></span> | <span data-ttu-id="dedc2-163">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="dedc2-163">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="dedc2-164">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-164">string</span></span> | <span data-ttu-id="dedc2-165">執行事件處理常式之帳戶的安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="dedc2-165">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="dedc2-166">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-166">string</span></span> | <span data-ttu-id="dedc2-167">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="dedc2-167">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="dedc2-168">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="dedc2-168">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="dedc2-169">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="dedc2-169">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="dedc2-170">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-170">string</span></span> | <span data-ttu-id="dedc2-171">指出是否要將使用者存取控制（UAC）許可權提升套用至啟動事件之處理常式的 Token 類型</span><span class="sxs-lookup"><span data-stu-id="dedc2-171">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="dedc2-172">long</span><span class="sxs-lookup"><span data-stu-id="dedc2-172">long</span></span> | <span data-ttu-id="dedc2-173">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="dedc2-173">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="dedc2-174">若要識別唯一的事件，此資料行必須與 DeviceName 及 Timestamp 資料行一起使用</span><span class="sxs-lookup"><span data-stu-id="dedc2-174">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="dedc2-175">string</span><span class="sxs-lookup"><span data-stu-id="dedc2-175">string</span></span> | <span data-ttu-id="dedc2-176">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="dedc2-176">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="dedc2-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="dedc2-177">Related topics</span></span>
- [<span data-ttu-id="dedc2-178">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="dedc2-178">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dedc2-179">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="dedc2-179">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dedc2-180">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="dedc2-180">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dedc2-181">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="dedc2-181">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dedc2-182">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="dedc2-182">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dedc2-183">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="dedc2-183">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
