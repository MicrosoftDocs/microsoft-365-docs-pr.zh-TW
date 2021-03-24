---
title: Advanced 搜尋架構中的 DeviceNetworkEvents 表格
description: 深入瞭解您可以從高級搜尋架構的 DeviceNetworkEvents 表查詢的網路線上活動
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、搜尋、查詢、遙測、schema reference、kusto、table、column、data type、devicenetworkevents、network connection、remote ip、local ip、NetworkCommunicationEvents
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
ms.openlocfilehash: 8c43d8ca790f246415a0419bca0adc3a21c92a84
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059791"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="d6aeb-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="d6aeb-104">DeviceNetworkEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d6aeb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d6aeb-105">**Applies to:**</span></span>
- [<span data-ttu-id="d6aeb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6aeb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="d6aeb-107">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d6aeb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d6aeb-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="d6aeb-109">[！附注] `DeviceNetworkEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含有關網路連線和相關事件的資訊。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-109">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="d6aeb-110">使用這個參考來建立從表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d6aeb-111">如需高級搜尋架構中其他資料表的詳細資訊，請參閱「 [高級搜尋架構參考](advanced-hunting-schema-reference.md)」。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="d6aeb-112">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="d6aeb-112">Column name</span></span> | <span data-ttu-id="d6aeb-113">資料類型</span><span class="sxs-lookup"><span data-stu-id="d6aeb-113">Data type</span></span> | <span data-ttu-id="d6aeb-114">描述</span><span class="sxs-lookup"><span data-stu-id="d6aeb-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d6aeb-115">datetime</span><span class="sxs-lookup"><span data-stu-id="d6aeb-115">datetime</span></span> | <span data-ttu-id="d6aeb-116">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="d6aeb-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d6aeb-117">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-117">string</span></span> | <span data-ttu-id="d6aeb-118">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="d6aeb-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d6aeb-119">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-119">string</span></span> | <span data-ttu-id="d6aeb-120">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="d6aeb-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="d6aeb-121">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-121">string</span></span> | <span data-ttu-id="d6aeb-122">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="d6aeb-122">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="d6aeb-123">字串</span><span class="sxs-lookup"><span data-stu-id="d6aeb-123">string</span></span> | <span data-ttu-id="d6aeb-124">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d6aeb-124">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="d6aeb-125">int</span><span class="sxs-lookup"><span data-stu-id="d6aeb-125">int</span></span> | <span data-ttu-id="d6aeb-126">連線的遠端裝置上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="d6aeb-126">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="d6aeb-127">字串</span><span class="sxs-lookup"><span data-stu-id="d6aeb-127">string</span></span> | <span data-ttu-id="d6aeb-128">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d6aeb-128">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="d6aeb-129">字串</span><span class="sxs-lookup"><span data-stu-id="d6aeb-129">string</span></span> | <span data-ttu-id="d6aeb-130">指派給通訊期間所使用之本機裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d6aeb-130">IP address assigned to the local device used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="d6aeb-131">int</span><span class="sxs-lookup"><span data-stu-id="d6aeb-131">int</span></span> | <span data-ttu-id="d6aeb-132">通訊期間使用的本機裝置上的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="d6aeb-132">TCP port on the local device used during communication</span></span> |
| `Protocol` | <span data-ttu-id="d6aeb-133">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-133">string</span></span> | <span data-ttu-id="d6aeb-134">使用 IP 通訊協定，不論是 TCP 還是 UDP</span><span class="sxs-lookup"><span data-stu-id="d6aeb-134">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="d6aeb-135">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-135">string</span></span> | <span data-ttu-id="d6aeb-136">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="d6aeb-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="d6aeb-137">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-137">string</span></span> | <span data-ttu-id="d6aeb-138">IP 位址的類型，例如 Public、Private、Reserved、環回、Teredo、FourToSixMapping 及廣播</span><span class="sxs-lookup"><span data-stu-id="d6aeb-138">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="d6aeb-139">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-139">string</span></span> | <span data-ttu-id="d6aeb-140">啟動事件) 的處理常式 (映射檔 SHA-1</span><span class="sxs-lookup"><span data-stu-id="d6aeb-140">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="d6aeb-141">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-141">string</span></span> | <span data-ttu-id="d6aeb-142">啟動事件之程式 (映射檔) 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="d6aeb-142">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="d6aeb-143">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-143">string</span></span> | <span data-ttu-id="d6aeb-144">啟動事件的進程名稱</span><span class="sxs-lookup"><span data-stu-id="d6aeb-144">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="d6aeb-145">int</span><span class="sxs-lookup"><span data-stu-id="d6aeb-145">int</span></span> | <span data-ttu-id="d6aeb-146">啟動事件之程式的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="d6aeb-146">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="d6aeb-147">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-147">string</span></span> | <span data-ttu-id="d6aeb-148">用來執行啟動事件之處理常式的命令列</span><span class="sxs-lookup"><span data-stu-id="d6aeb-148">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="d6aeb-149">datetime</span><span class="sxs-lookup"><span data-stu-id="d6aeb-149">datetime</span></span> | <span data-ttu-id="d6aeb-150">啟動事件處理常式的日期和時間</span><span class="sxs-lookup"><span data-stu-id="d6aeb-150">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="d6aeb-151">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-151">string</span></span> | <span data-ttu-id="d6aeb-152">包含初始化事件之處理 (映射檔) 程式的資料夾</span><span class="sxs-lookup"><span data-stu-id="d6aeb-152">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="d6aeb-153">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-153">string</span></span> | <span data-ttu-id="d6aeb-154">產生負責事件之處理常式的父進程名稱</span><span class="sxs-lookup"><span data-stu-id="d6aeb-154">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="d6aeb-155">int</span><span class="sxs-lookup"><span data-stu-id="d6aeb-155">int</span></span> | <span data-ttu-id="d6aeb-156">產生負責事件之處理常式之父進程的進程識別碼 (PID) </span><span class="sxs-lookup"><span data-stu-id="d6aeb-156">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="d6aeb-157">datetime</span><span class="sxs-lookup"><span data-stu-id="d6aeb-157">datetime</span></span> | <span data-ttu-id="d6aeb-158">啟動事件之處理常式的父項時的日期和時間</span><span class="sxs-lookup"><span data-stu-id="d6aeb-158">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="d6aeb-159">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-159">string</span></span> | <span data-ttu-id="d6aeb-160">執行負責事件之處理常式之帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="d6aeb-160">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="d6aeb-161">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-161">string</span></span> | <span data-ttu-id="d6aeb-162">負責事件之處理常式的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="d6aeb-162">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="d6aeb-163">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-163">string</span></span> | <span data-ttu-id="d6aeb-164">執行事件負責處理之帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="d6aeb-164">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="d6aeb-165">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-165">string</span></span> | <span data-ttu-id="d6aeb-166">啟動事件之處理常式的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-166">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="d6aeb-167">Windows 會根據特定的特性，例如從網際網路下載啟動，將完整性層級指派給處理常式。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-167">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="d6aeb-168">這些完整性層級會影響資源的許可權</span><span class="sxs-lookup"><span data-stu-id="d6aeb-168">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="d6aeb-169">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-169">string</span></span> | <span data-ttu-id="d6aeb-170">指出是否存在使用者存取控制的 Token 類型 (UAC) 許可權提升會套用至啟動事件的程式。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-170">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="d6aeb-171">long</span><span class="sxs-lookup"><span data-stu-id="d6aeb-171">long</span></span> | <span data-ttu-id="d6aeb-172">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="d6aeb-172">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d6aeb-173">若要識別唯一的事件，此資料行必須與 `DeviceName` 和欄一起 `Timestamp` 使用</span><span class="sxs-lookup"><span data-stu-id="d6aeb-173">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="d6aeb-174">string</span><span class="sxs-lookup"><span data-stu-id="d6aeb-174">string</span></span> | <span data-ttu-id="d6aeb-175">Application Guard 用來隔離瀏覽器活動的虛擬容器識別碼</span><span class="sxs-lookup"><span data-stu-id="d6aeb-175">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d6aeb-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="d6aeb-176">Related topics</span></span>
- [<span data-ttu-id="d6aeb-177">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="d6aeb-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d6aeb-178">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="d6aeb-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d6aeb-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="d6aeb-179">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
