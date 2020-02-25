---
title: DeviceFileEvents 資料表中的進階的狩獵結構描述
description: 了解進階的狩獵結構描述的 DeviceFileEvents 資料表中的檔案相關的事件
keywords: 進階狩獵、 威脅狩獵、 網路威脅狩獵、 microsoft 威脅防護、 microsoft 365、 mtp、 m365、 搜尋、 查詢、 遙測、 結構描述參考、 kusto、 表格、 欄、 資料類型、 描述、 filecreationevents、 DeviceFileEvents、 檔案、 路徑雜湊、 sha1、 sha256、 md5
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
ms.openlocfilehash: 07569b93244bd420fe5961e20e6951ea84ae47d7
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235032"
---
# <a name="devicefileevents"></a><span data-ttu-id="85753-104">DeviceFileEvents</span><span class="sxs-lookup"><span data-stu-id="85753-104">DeviceFileEvents</span></span>

<span data-ttu-id="85753-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="85753-105">**Applies to:**</span></span>
- <span data-ttu-id="85753-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="85753-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="85753-107">`DeviceFileEvents` [進階的狩獵](advanced-hunting-overview.md)結構描述中的表格包含的檔案建立、 修改和其他檔案系統事件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="85753-107">The `DeviceFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file creation, modification, and other file system events.</span></span> <span data-ttu-id="85753-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="85753-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="85753-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="85753-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="85753-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="85753-110">Column name</span></span> | <span data-ttu-id="85753-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="85753-111">Data type</span></span> | <span data-ttu-id="85753-112">描述</span><span class="sxs-lookup"><span data-stu-id="85753-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="85753-113">datetime</span><span class="sxs-lookup"><span data-stu-id="85753-113">datetime</span></span> | <span data-ttu-id="85753-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="85753-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="85753-115">string</span><span class="sxs-lookup"><span data-stu-id="85753-115">string</span></span> | <span data-ttu-id="85753-116">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="85753-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="85753-117">string</span><span class="sxs-lookup"><span data-stu-id="85753-117">string</span></span> | <span data-ttu-id="85753-118">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="85753-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="85753-119">string</span><span class="sxs-lookup"><span data-stu-id="85753-119">string</span></span> | <span data-ttu-id="85753-120">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="85753-120">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="85753-121">string</span><span class="sxs-lookup"><span data-stu-id="85753-121">string</span></span> | <span data-ttu-id="85753-122">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="85753-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="85753-123">string</span><span class="sxs-lookup"><span data-stu-id="85753-123">string</span></span> | <span data-ttu-id="85753-124">包含已錄製的巨集指令所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="85753-124">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="85753-125">string</span><span class="sxs-lookup"><span data-stu-id="85753-125">string</span></span> | <span data-ttu-id="85753-126">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="85753-126">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="85753-127">字串</span><span class="sxs-lookup"><span data-stu-id="85753-127">string</span></span> | <span data-ttu-id="85753-128">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="85753-128">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="85753-129">通常沒有填入此欄位 — 使用時可用的 SHA1 欄</span><span class="sxs-lookup"><span data-stu-id="85753-129">This field is usually not populated—use the SHA1 column when available</span></span> |
| `MD5` | <span data-ttu-id="85753-130">string</span><span class="sxs-lookup"><span data-stu-id="85753-130">string</span></span> | <span data-ttu-id="85753-131">錄製巨集指令所套用之檔案的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="85753-131">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileOriginUrl` | <span data-ttu-id="85753-132">string</span><span class="sxs-lookup"><span data-stu-id="85753-132">string</span></span> | <span data-ttu-id="85753-133">從何處下載檔案的 URL</span><span class="sxs-lookup"><span data-stu-id="85753-133">URL where the file was downloaded from</span></span> |
| `FileOriginReferrerUrl` | <span data-ttu-id="85753-134">string</span><span class="sxs-lookup"><span data-stu-id="85753-134">string</span></span> | <span data-ttu-id="85753-135">下載的檔案所連結之 web 頁面的 URL</span><span class="sxs-lookup"><span data-stu-id="85753-135">URL of the web page that links to the downloaded file</span></span> |
| `FileOriginIP` | <span data-ttu-id="85753-136">string</span><span class="sxs-lookup"><span data-stu-id="85753-136">string</span></span> | <span data-ttu-id="85753-137">從何處下載檔案的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="85753-137">IP address where the file was downloaded from</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="85753-138">string</span><span class="sxs-lookup"><span data-stu-id="85753-138">string</span></span> | <span data-ttu-id="85753-139">執行負責事件程序的帳戶網域</span><span class="sxs-lookup"><span data-stu-id="85753-139">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="85753-140">string</span><span class="sxs-lookup"><span data-stu-id="85753-140">string</span></span> | <span data-ttu-id="85753-141">執行負責事件程序的帳戶使用者名稱</span><span class="sxs-lookup"><span data-stu-id="85753-141">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="85753-142">string</span><span class="sxs-lookup"><span data-stu-id="85753-142">string</span></span> | <span data-ttu-id="85753-143">安全性識別碼 (SID) 執行負責事件程序的帳戶</span><span class="sxs-lookup"><span data-stu-id="85753-143">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="85753-144">string</span><span class="sxs-lookup"><span data-stu-id="85753-144">string</span></span> | <span data-ttu-id="85753-145">初始化事件程序 （影像檔案） 的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="85753-145">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="85753-146">string</span><span class="sxs-lookup"><span data-stu-id="85753-146">string</span></span> | <span data-ttu-id="85753-147">SHA-1 起始之事件程序 （影像檔案）</span><span class="sxs-lookup"><span data-stu-id="85753-147">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="85753-148">string</span><span class="sxs-lookup"><span data-stu-id="85753-148">string</span></span> | <span data-ttu-id="85753-149">包含起始事件程序 （影像檔案） 的資料夾</span><span class="sxs-lookup"><span data-stu-id="85753-149">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="85753-150">string</span><span class="sxs-lookup"><span data-stu-id="85753-150">string</span></span> | <span data-ttu-id="85753-151">初始化事件的處理序名稱</span><span class="sxs-lookup"><span data-stu-id="85753-151">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="85753-152">int</span><span class="sxs-lookup"><span data-stu-id="85753-152">int</span></span> | <span data-ttu-id="85753-153">處理程序識別碼 (PID) 的起始事件程序</span><span class="sxs-lookup"><span data-stu-id="85753-153">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="85753-154">string</span><span class="sxs-lookup"><span data-stu-id="85753-154">string</span></span> | <span data-ttu-id="85753-155">用來執行初始化事件程序的命令列</span><span class="sxs-lookup"><span data-stu-id="85753-155">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="85753-156">datetime</span><span class="sxs-lookup"><span data-stu-id="85753-156">datetime</span></span> | <span data-ttu-id="85753-157">初始化事件程序時已開始日期和時間</span><span class="sxs-lookup"><span data-stu-id="85753-157">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="85753-158">string</span><span class="sxs-lookup"><span data-stu-id="85753-158">string</span></span> | <span data-ttu-id="85753-159">初始化事件程序的完整性層級。</span><span class="sxs-lookup"><span data-stu-id="85753-159">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="85753-160">Windows 會指派完整性層級根據若干特質程序，例如如果他們已啟動從網際網路下載。</span><span class="sxs-lookup"><span data-stu-id="85753-160">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="85753-161">這些完整性層級影響資源的權限</span><span class="sxs-lookup"><span data-stu-id="85753-161">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="85753-162">string</span><span class="sxs-lookup"><span data-stu-id="85753-162">string</span></span> | <span data-ttu-id="85753-163">指出使用者存取控制 (UAC) 提高權限套用至初始化事件程序存在的 token 型別</span><span class="sxs-lookup"><span data-stu-id="85753-163">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="85753-164">int</span><span class="sxs-lookup"><span data-stu-id="85753-164">int</span></span> | <span data-ttu-id="85753-165">處理程序識別碼 (PID) 的產生處理程序負責事件父處理序</span><span class="sxs-lookup"><span data-stu-id="85753-165">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="85753-166">string</span><span class="sxs-lookup"><span data-stu-id="85753-166">string</span></span> | <span data-ttu-id="85753-167">產生負責事件程序的父處理序名稱</span><span class="sxs-lookup"><span data-stu-id="85753-167">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="85753-168">datetime</span><span class="sxs-lookup"><span data-stu-id="85753-168">datetime</span></span> | <span data-ttu-id="85753-169">日期和時間的父代負責事件程序已啟動時</span><span class="sxs-lookup"><span data-stu-id="85753-169">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="85753-170">long</span><span class="sxs-lookup"><span data-stu-id="85753-170">long</span></span> | <span data-ttu-id="85753-171">以重複計數器為基礎的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="85753-171">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="85753-172">若要識別唯一的事件，必須使用此資料行搭配 DeviceName 和時間戳記欄</span><span class="sxs-lookup"><span data-stu-id="85753-172">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="85753-173">string</span><span class="sxs-lookup"><span data-stu-id="85753-173">string</span></span> | <span data-ttu-id="85753-174">虛擬化的容器應用程式防護用於隔離瀏覽器活動識別碼</span><span class="sxs-lookup"><span data-stu-id="85753-174">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `SensitivityLabel` | <span data-ttu-id="85753-175">string</span><span class="sxs-lookup"><span data-stu-id="85753-175">string</span></span> | <span data-ttu-id="85753-176">套用至電子郵件、 檔案或其他內容來分類資訊保護標籤</span><span class="sxs-lookup"><span data-stu-id="85753-176">Label applied to an email, file, or other content to classify it for information protection</span></span> |
| `SensitivitySubLabel` | <span data-ttu-id="85753-177">string</span><span class="sxs-lookup"><span data-stu-id="85753-177">string</span></span> | <span data-ttu-id="85753-178">子標籤套用至電子郵件、 檔案或其他內容來分類資訊保護;敏感度子標籤進行分組敏感度標籤，但分開處理</span><span class="sxs-lookup"><span data-stu-id="85753-178">Sublabel applied to an email, file, or other content to classify it for information protection; sensitivity sublabels are grouped under sensitivity labels but are treated independently</span></span> |
| `IsAzureInfoProtectionApplied` | <span data-ttu-id="85753-179">布林值</span><span class="sxs-lookup"><span data-stu-id="85753-179">boolean</span></span> | <span data-ttu-id="85753-180">會指出是否要將檔案加密的 Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="85753-180">Indicates whether the file is encrypted by Azure Information Protection</span></span> |

## <a name="related-topics"></a><span data-ttu-id="85753-181">相關主題</span><span class="sxs-lookup"><span data-stu-id="85753-181">Related topics</span></span>
- [<span data-ttu-id="85753-182">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="85753-182">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="85753-183">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="85753-183">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="85753-184">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="85753-184">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="85753-185">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="85753-185">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="85753-186">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="85753-186">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="85753-187">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="85753-187">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
