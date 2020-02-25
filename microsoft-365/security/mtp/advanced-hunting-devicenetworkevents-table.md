---
title: DeviceNetworkEvents 資料表中的進階的狩獵結構描述
description: 了解您可以從 DeviceNetworkEvents 資料表的進階的狩獵結構描述查詢的網路連線事件
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、] 欄中，資料型別 devicenetworkevents，NetworkCommunicationEvents，網路連線、 遠端 ip、 本機 ip
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
ms.openlocfilehash: 2e7999fef43adb372947d9edf92b84ac67f347fe
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235002"
---
# <a name="devicenetworkevents"></a><span data-ttu-id="09a63-104">DeviceNetworkEvents</span><span class="sxs-lookup"><span data-stu-id="09a63-104">DeviceNetworkEvents</span></span>

<span data-ttu-id="09a63-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="09a63-105">**Applies to:**</span></span>
- <span data-ttu-id="09a63-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="09a63-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="09a63-107">`DeviceNetworkEvents` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含網路連線及相關的事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="09a63-107">The `DeviceNetworkEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about network connections and related events.</span></span> <span data-ttu-id="09a63-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="09a63-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="09a63-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="09a63-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="09a63-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="09a63-110">Column name</span></span> | <span data-ttu-id="09a63-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="09a63-111">Data type</span></span> | <span data-ttu-id="09a63-112">描述</span><span class="sxs-lookup"><span data-stu-id="09a63-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="09a63-113">datetime</span><span class="sxs-lookup"><span data-stu-id="09a63-113">datetime</span></span> | <span data-ttu-id="09a63-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="09a63-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="09a63-115">string</span><span class="sxs-lookup"><span data-stu-id="09a63-115">string</span></span> | <span data-ttu-id="09a63-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="09a63-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="09a63-117">string</span><span class="sxs-lookup"><span data-stu-id="09a63-117">string</span></span> | <span data-ttu-id="09a63-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="09a63-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="09a63-119">string</span><span class="sxs-lookup"><span data-stu-id="09a63-119">string</span></span> | <span data-ttu-id="09a63-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="09a63-120">Type of activity that triggered the event</span></span> |
| `RemoteIP` | <span data-ttu-id="09a63-121">字串</span><span class="sxs-lookup"><span data-stu-id="09a63-121">string</span></span> | <span data-ttu-id="09a63-122">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="09a63-122">IP address that was being connected to</span></span> |
| `RemotePort` | <span data-ttu-id="09a63-123">int</span><span class="sxs-lookup"><span data-stu-id="09a63-123">int</span></span> | <span data-ttu-id="09a63-124">已連線至遠端裝置上的 TCP 連接埠</span><span class="sxs-lookup"><span data-stu-id="09a63-124">TCP port on the remote device that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="09a63-125">string</span><span class="sxs-lookup"><span data-stu-id="09a63-125">string</span></span> | <span data-ttu-id="09a63-126">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="09a63-126">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `LocalIP` | <span data-ttu-id="09a63-127">字串</span><span class="sxs-lookup"><span data-stu-id="09a63-127">string</span></span> | <span data-ttu-id="09a63-128">指派給通訊期間，使用本機電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="09a63-128">IP address assigned to the local machine used during communication</span></span> |
| `LocalPort` | <span data-ttu-id="09a63-129">int</span><span class="sxs-lookup"><span data-stu-id="09a63-129">int</span></span> | <span data-ttu-id="09a63-130">在通訊期間，使用本機電腦上的 TCP 連接埠</span><span class="sxs-lookup"><span data-stu-id="09a63-130">TCP port on the local machine used during communication</span></span> |
| `Protocol` | <span data-ttu-id="09a63-131">string</span><span class="sxs-lookup"><span data-stu-id="09a63-131">string</span></span> | <span data-ttu-id="09a63-132">IP 通訊協定是否使用 TCP 或 UDP</span><span class="sxs-lookup"><span data-stu-id="09a63-132">IP protocol used, whether TCP or UDP</span></span> |
| `LocalIPType` | <span data-ttu-id="09a63-133">string</span><span class="sxs-lookup"><span data-stu-id="09a63-133">string</span></span> | <span data-ttu-id="09a63-134">IP 位址，例如公用、 私用、 保留、 回送、 Teredo、 FourToSixMapping 及廣播的類型</span><span class="sxs-lookup"><span data-stu-id="09a63-134">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `RemoteIPType` | <span data-ttu-id="09a63-135">string</span><span class="sxs-lookup"><span data-stu-id="09a63-135">string</span></span> | <span data-ttu-id="09a63-136">IP 位址，例如公用、 私用、 保留、 回送、 Teredo、 FourToSixMapping 及廣播的類型</span><span class="sxs-lookup"><span data-stu-id="09a63-136">Type of IP address, for example Public, Private, Reserved, Loopback, Teredo, FourToSixMapping, and Broadcast</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="09a63-137">string</span><span class="sxs-lookup"><span data-stu-id="09a63-137">string</span></span> | <span data-ttu-id="09a63-138">SHA-1 起始之事件程序 （影像檔案）</span><span class="sxs-lookup"><span data-stu-id="09a63-138">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="09a63-139">string</span><span class="sxs-lookup"><span data-stu-id="09a63-139">string</span></span> | <span data-ttu-id="09a63-140">初始化事件程序 （影像檔案） 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="09a63-140">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="09a63-141">string</span><span class="sxs-lookup"><span data-stu-id="09a63-141">string</span></span> | <span data-ttu-id="09a63-142">初始化事件的處理序名稱</span><span class="sxs-lookup"><span data-stu-id="09a63-142">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="09a63-143">int</span><span class="sxs-lookup"><span data-stu-id="09a63-143">int</span></span> | <span data-ttu-id="09a63-144">處理程序識別碼 (PID) 的起始事件程序</span><span class="sxs-lookup"><span data-stu-id="09a63-144">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="09a63-145">string</span><span class="sxs-lookup"><span data-stu-id="09a63-145">string</span></span> | <span data-ttu-id="09a63-146">用來執行初始化事件程序的命令列</span><span class="sxs-lookup"><span data-stu-id="09a63-146">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="09a63-147">datetime</span><span class="sxs-lookup"><span data-stu-id="09a63-147">datetime</span></span> | <span data-ttu-id="09a63-148">初始化事件程序時已開始日期和時間</span><span class="sxs-lookup"><span data-stu-id="09a63-148">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="09a63-149">string</span><span class="sxs-lookup"><span data-stu-id="09a63-149">string</span></span> | <span data-ttu-id="09a63-150">包含起始事件程序 （影像檔案） 的資料夾</span><span class="sxs-lookup"><span data-stu-id="09a63-150">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="09a63-151">string</span><span class="sxs-lookup"><span data-stu-id="09a63-151">string</span></span> | <span data-ttu-id="09a63-152">產生負責事件程序的父處理序名稱</span><span class="sxs-lookup"><span data-stu-id="09a63-152">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="09a63-153">int</span><span class="sxs-lookup"><span data-stu-id="09a63-153">int</span></span> | <span data-ttu-id="09a63-154">處理程序識別碼 (PID) 的產生處理程序負責事件父處理序</span><span class="sxs-lookup"><span data-stu-id="09a63-154">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="09a63-155">datetime</span><span class="sxs-lookup"><span data-stu-id="09a63-155">datetime</span></span> | <span data-ttu-id="09a63-156">日期和時間的父代負責事件程序已啟動時</span><span class="sxs-lookup"><span data-stu-id="09a63-156">Date and time when the parent of the process responsible for the event was started</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="09a63-157">string</span><span class="sxs-lookup"><span data-stu-id="09a63-157">string</span></span> | <span data-ttu-id="09a63-158">執行負責事件程序的帳戶網域</span><span class="sxs-lookup"><span data-stu-id="09a63-158">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="09a63-159">string</span><span class="sxs-lookup"><span data-stu-id="09a63-159">string</span></span> | <span data-ttu-id="09a63-160">執行負責事件程序的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="09a63-160">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="09a63-161">string</span><span class="sxs-lookup"><span data-stu-id="09a63-161">string</span></span> | <span data-ttu-id="09a63-162">安全性識別碼 (SID) 執行負責事件程序的帳戶</span><span class="sxs-lookup"><span data-stu-id="09a63-162">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="09a63-163">string</span><span class="sxs-lookup"><span data-stu-id="09a63-163">string</span></span> | <span data-ttu-id="09a63-164">初始化事件程序的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="09a63-164">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="09a63-165">Windows 會指派完整性層級根據若干特質程序，例如如果他們已啟動從網際網路下載。</span><span class="sxs-lookup"><span data-stu-id="09a63-165">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="09a63-166">這些完整性層級影響資源的權限</span><span class="sxs-lookup"><span data-stu-id="09a63-166">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="09a63-167">string</span><span class="sxs-lookup"><span data-stu-id="09a63-167">string</span></span> | <span data-ttu-id="09a63-168">指出使用者存取控制 (UAC) 提高權限套用至初始化事件程序存在的 token 型別</span><span class="sxs-lookup"><span data-stu-id="09a63-168">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `ReportId` | <span data-ttu-id="09a63-169">long</span><span class="sxs-lookup"><span data-stu-id="09a63-169">long</span></span> | <span data-ttu-id="09a63-170">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="09a63-170">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="09a63-171">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="09a63-171">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="09a63-172">string</span><span class="sxs-lookup"><span data-stu-id="09a63-172">string</span></span> | <span data-ttu-id="09a63-173">虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼</span><span class="sxs-lookup"><span data-stu-id="09a63-173">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="09a63-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="09a63-174">Related topics</span></span>
- [<span data-ttu-id="09a63-175">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="09a63-175">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="09a63-176">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="09a63-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="09a63-177">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="09a63-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="09a63-178">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="09a63-178">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="09a63-179">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="09a63-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="09a63-180">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="09a63-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
