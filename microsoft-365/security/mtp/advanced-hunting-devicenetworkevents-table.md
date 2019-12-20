---
title: DeviceNetworkEvents 資料表中的進階的狩獵結構描述
description: 了解您可以從 DeviceNetworkEvents 資料表的進階的狩獵結構描述查詢的網路連線事件
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 devicenetworkevents，NetworkCommunicationEvents，網路連線、 遠端 ip、 本機 ip
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 82475ad15090250aa4fca70a6810cb869128102d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809263"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="432e7-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="432e7-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="432e7-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="432e7-105">**Applies to:**</span></span>
- <span data-ttu-id="432e7-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="432e7-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="432e7-107">`DeviceNetworkEvents` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含網路連線及相關的事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="432e7-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="432e7-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="432e7-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="432e7-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="432e7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="432e7-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="432e7-110">Column name</span></span> | <span data-ttu-id="432e7-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="432e7-111">Data type</span></span> | <span data-ttu-id="432e7-112">描述</span><span class="sxs-lookup"><span data-stu-id="432e7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="432e7-113">datetime</span><span class="sxs-lookup"><span data-stu-id="432e7-113">datetime</span></span> | <span data-ttu-id="432e7-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="432e7-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="432e7-115">string</span><span class="sxs-lookup"><span data-stu-id="432e7-115">string</span></span> | <span data-ttu-id="432e7-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="432e7-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="432e7-117">string</span><span class="sxs-lookup"><span data-stu-id="432e7-117">string</span></span> | <span data-ttu-id="432e7-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="432e7-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="432e7-119">string</span><span class="sxs-lookup"><span data-stu-id="432e7-119">string</span></span> | <span data-ttu-id="432e7-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="432e7-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="432e7-121">字串</span><span class="sxs-lookup"><span data-stu-id="432e7-121">string</span></span> | <span data-ttu-id="432e7-122">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="432e7-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="432e7-123">int</span><span class="sxs-lookup"><span data-stu-id="432e7-123">int</span></span> | <span data-ttu-id="432e7-124">已連線至遠端裝置上的 TCP 連接埠</span><span class="sxs-lookup"><span data-stu-id="432e7-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="432e7-125">string</span><span class="sxs-lookup"><span data-stu-id="432e7-125">string</span></span> | <span data-ttu-id="432e7-126">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="432e7-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="432e7-127">字串</span><span class="sxs-lookup"><span data-stu-id="432e7-127">string</span></span> | <span data-ttu-id="432e7-128">指派給通訊期間，使用本機電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="432e7-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="432e7-129">int</span><span class="sxs-lookup"><span data-stu-id="432e7-129">int</span></span> | <span data-ttu-id="432e7-130">在通訊期間，使用本機電腦上的 TCP 連接埠</span><span class="sxs-lookup"><span data-stu-id="432e7-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="432e7-131">string</span><span class="sxs-lookup"><span data-stu-id="432e7-131">string</span></span> | <span data-ttu-id="432e7-132">IP 通訊協定是否使用 TCP 或 UDP</span><span class="sxs-lookup"><span data-stu-id="432e7-132">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="432e7-133">string</span><span class="sxs-lookup"><span data-stu-id="432e7-133">string</span></span> | <span data-ttu-id="432e7-134">IP 位址，例如公用、 私用、 保留、 回送、 Teredo、 FourToSixMapping 及廣播的類型</span><span class="sxs-lookup"><span data-stu-id="432e7-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="432e7-135">string</span><span class="sxs-lookup"><span data-stu-id="432e7-135">string</span></span> | <span data-ttu-id="432e7-136">IP 位址，例如公用、 私用、 保留、 回送、 Teredo、 FourToSixMapping 及廣播的類型</span><span class="sxs-lookup"><span data-stu-id="432e7-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="432e7-137">string</span><span class="sxs-lookup"><span data-stu-id="432e7-137">string</span></span> | <span data-ttu-id="432e7-138">SHA-1 起始之事件程序 （影像檔案）</span><span class="sxs-lookup"><span data-stu-id="432e7-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="432e7-139">string</span><span class="sxs-lookup"><span data-stu-id="432e7-139">string</span></span> | <span data-ttu-id="432e7-140">初始化事件程序 （影像檔案） 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="432e7-140">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="432e7-141">string</span><span class="sxs-lookup"><span data-stu-id="432e7-141">string</span></span> | <span data-ttu-id="432e7-142">初始化事件的處理序名稱</span><span class="sxs-lookup"><span data-stu-id="432e7-142">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="432e7-143">int</span><span class="sxs-lookup"><span data-stu-id="432e7-143">int</span></span> | <span data-ttu-id="432e7-144">處理程序識別碼 (PID) 的起始事件程序</span><span class="sxs-lookup"><span data-stu-id="432e7-144">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="432e7-145">string</span><span class="sxs-lookup"><span data-stu-id="432e7-145">string</span></span> | <span data-ttu-id="432e7-146">用來執行初始化事件程序的命令列</span><span class="sxs-lookup"><span data-stu-id="432e7-146">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="432e7-147">datetime</span><span class="sxs-lookup"><span data-stu-id="432e7-147">datetime</span></span> | <span data-ttu-id="432e7-148">初始化事件程序時已開始日期和時間</span><span class="sxs-lookup"><span data-stu-id="432e7-148">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="432e7-149">string</span><span class="sxs-lookup"><span data-stu-id="432e7-149">string</span></span> | <span data-ttu-id="432e7-150">包含起始事件程序 （影像檔案） 的資料夾</span><span class="sxs-lookup"><span data-stu-id="432e7-150">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="432e7-151">string</span><span class="sxs-lookup"><span data-stu-id="432e7-151">string</span></span> | <span data-ttu-id="432e7-152">產生負責事件程序的父處理序名稱</span><span class="sxs-lookup"><span data-stu-id="432e7-152">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="432e7-153">int</span><span class="sxs-lookup"><span data-stu-id="432e7-153">int</span></span> | <span data-ttu-id="432e7-154">處理程序識別碼 (PID) 的產生處理程序負責事件父處理序</span><span class="sxs-lookup"><span data-stu-id="432e7-154">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="432e7-155">datetime</span><span class="sxs-lookup"><span data-stu-id="432e7-155">datetime</span></span> | <span data-ttu-id="432e7-156">日期和時間的父代負責事件程序已啟動時</span><span class="sxs-lookup"><span data-stu-id="432e7-156">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="432e7-157">string</span><span class="sxs-lookup"><span data-stu-id="432e7-157">string</span></span> | <span data-ttu-id="432e7-158">執行負責事件程序的帳戶網域</span><span class="sxs-lookup"><span data-stu-id="432e7-158">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="432e7-159">string</span><span class="sxs-lookup"><span data-stu-id="432e7-159">string</span></span> | <span data-ttu-id="432e7-160">執行負責事件程序的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="432e7-160">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="432e7-161">string</span><span class="sxs-lookup"><span data-stu-id="432e7-161">string</span></span> | <span data-ttu-id="432e7-162">安全性識別碼 (SID) 執行負責事件程序的帳戶</span><span class="sxs-lookup"><span data-stu-id="432e7-162">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="432e7-163">string</span><span class="sxs-lookup"><span data-stu-id="432e7-163">string</span></span> | <span data-ttu-id="432e7-164">初始化事件程序的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="432e7-164">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="432e7-165">Windows 會指派完整性層級根據若干特質程序，例如如果他們已啟動從網際網路下載。</span><span class="sxs-lookup"><span data-stu-id="432e7-165">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="432e7-166">這些完整性層級影響資源的權限</span><span class="sxs-lookup"><span data-stu-id="432e7-166">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="432e7-167">string</span><span class="sxs-lookup"><span data-stu-id="432e7-167">string</span></span> | <span data-ttu-id="432e7-168">指出使用者存取控制 (UAC) 提高權限套用至初始化事件程序存在的 token 型別</span><span class="sxs-lookup"><span data-stu-id="432e7-168">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="432e7-169">long</span><span class="sxs-lookup"><span data-stu-id="432e7-169">long</span></span> | <span data-ttu-id="432e7-170">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="432e7-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="432e7-171">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="432e7-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="432e7-172">string</span><span class="sxs-lookup"><span data-stu-id="432e7-172">string</span></span> | <span data-ttu-id="432e7-173">虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼</span><span class="sxs-lookup"><span data-stu-id="432e7-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="432e7-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="432e7-174">Related topics</span></span>
- [<span data-ttu-id="432e7-175">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="432e7-175">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="432e7-176">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="432e7-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="432e7-177">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="432e7-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="432e7-178">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="432e7-178">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="432e7-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="432e7-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="432e7-180">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="432e7-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
