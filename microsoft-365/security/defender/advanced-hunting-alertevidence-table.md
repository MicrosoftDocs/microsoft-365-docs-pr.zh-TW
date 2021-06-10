---
title: Advanced 搜尋架構中的 AlertEvidence 表格
description: 深入瞭解與高級搜尋架構之 AlertEvidence 表格中的警示相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，column，資料類型，描述，，警示，實體，證據，檔案，IP 位址，裝置，機器，使用者，帳戶
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932580"
---
# <a name="alertevidence"></a><span data-ttu-id="e4ae6-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="e4ae6-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e4ae6-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e4ae6-105">**Applies to:**</span></span>
- <span data-ttu-id="e4ae6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4ae6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e4ae6-107">[！附注] `AlertEvidence` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含各種實體（檔案、IP 位址、URLs、使用者或裝置）相關資訊，這些資訊與 microsoft defender for Endpoint （適用于 Office 365、Microsoft Cloud App Security 和 Microsoft defender 身分識別）相關聯的提醒相關聯。</span><span class="sxs-lookup"><span data-stu-id="e4ae6-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="e4ae6-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="e4ae6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e4ae6-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="e4ae6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e4ae6-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="e4ae6-110">Column name</span></span> | <span data-ttu-id="e4ae6-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="e4ae6-111">Data type</span></span> | <span data-ttu-id="e4ae6-112">描述</span><span class="sxs-lookup"><span data-stu-id="e4ae6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e4ae6-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e4ae6-113">datetime</span></span> | <span data-ttu-id="e4ae6-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="e4ae6-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="e4ae6-115">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-115">string</span></span> | <span data-ttu-id="e4ae6-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e4ae6-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="e4ae6-117">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-117">string</span></span> | <span data-ttu-id="e4ae6-118">提供提醒資訊的產品或服務</span><span class="sxs-lookup"><span data-stu-id="e4ae6-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="e4ae6-119">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-119">string</span></span> | <span data-ttu-id="e4ae6-120">物件的類型，例如檔案、進程、裝置或使用者</span><span class="sxs-lookup"><span data-stu-id="e4ae6-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="e4ae6-121">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-121">string</span></span> | <span data-ttu-id="e4ae6-122">如何將實體包含在警示中，指出它會受到影響或僅僅是相關的</span><span class="sxs-lookup"><span data-stu-id="e4ae6-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="e4ae6-123">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-123">string</span></span> | <span data-ttu-id="e4ae6-124">指出實體是否為網路連線的來源或目的地</span><span class="sxs-lookup"><span data-stu-id="e4ae6-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="e4ae6-125">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-125">string</span></span> | <span data-ttu-id="e4ae6-126">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="e4ae6-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="e4ae6-127">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-127">string</span></span> | <span data-ttu-id="e4ae6-128">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="e4ae6-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="e4ae6-129">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-129">string</span></span> | <span data-ttu-id="e4ae6-130">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="e4ae6-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="e4ae6-131">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-131">string</span></span> | <span data-ttu-id="e4ae6-132">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="e4ae6-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="e4ae6-133">通常不會填入此欄位，可用時使用 SHA1] 欄位。</span><span class="sxs-lookup"><span data-stu-id="e4ae6-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="e4ae6-134">int</span><span class="sxs-lookup"><span data-stu-id="e4ae6-134">int</span></span> | <span data-ttu-id="e4ae6-135">檔案大小（以位元組為單位）</span><span class="sxs-lookup"><span data-stu-id="e4ae6-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="e4ae6-136">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-136">string</span></span> | <span data-ttu-id="e4ae6-137">已分類的可疑或惡意檔或程式的惡意程式碼系列</span><span class="sxs-lookup"><span data-stu-id="e4ae6-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="e4ae6-138">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-138">string</span></span> | <span data-ttu-id="e4ae6-139">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e4ae6-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="e4ae6-140">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-140">string</span></span> | <span data-ttu-id="e4ae6-141">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e4ae6-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="e4ae6-142">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-142">string</span></span> | <span data-ttu-id="e4ae6-143">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="e4ae6-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="e4ae6-144">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-144">string</span></span> | <span data-ttu-id="e4ae6-145">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="e4ae6-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="e4ae6-146">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-146">string</span></span> | <span data-ttu-id="e4ae6-147">帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="e4ae6-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="e4ae6-148">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-148">string</span></span> | <span data-ttu-id="e4ae6-149">帳戶在 Azure Active Directory 中的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e4ae6-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="e4ae6-150">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-150">string</span></span> | <span data-ttu-id="e4ae6-151">帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="e4ae6-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="e4ae6-152">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-152">string</span></span> | <span data-ttu-id="e4ae6-153">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e4ae6-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e4ae6-154">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-154">string</span></span> | <span data-ttu-id="e4ae6-155">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="e4ae6-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="e4ae6-156">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-156">string</span></span> | <span data-ttu-id="e4ae6-157">指派給通訊期間所使用之本機裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e4ae6-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="e4ae6-158">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-158">string</span></span> | <span data-ttu-id="e4ae6-159">Office 365 產生的電子郵件唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e4ae6-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="e4ae6-160">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-160">string</span></span> | <span data-ttu-id="e4ae6-161">電子郵件的主旨</span><span class="sxs-lookup"><span data-stu-id="e4ae6-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="e4ae6-162">字串</span><span class="sxs-lookup"><span data-stu-id="e4ae6-162">string</span></span> | <span data-ttu-id="e4ae6-163">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="e4ae6-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="e4ae6-164">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-164">string</span></span> | <span data-ttu-id="e4ae6-165">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="e4ae6-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="e4ae6-166">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-166">string</span></span> | <span data-ttu-id="e4ae6-167">用來建立新程式的命令列</span><span class="sxs-lookup"><span data-stu-id="e4ae6-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="e4ae6-168">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-168">string</span></span> | <span data-ttu-id="e4ae6-169">有關 JSON 陣列格式之事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="e4ae6-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="e4ae6-170">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-170">string</span></span> | <span data-ttu-id="e4ae6-171">套用錄製的動作所用的登錄機碼</span><span class="sxs-lookup"><span data-stu-id="e4ae6-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="e4ae6-172">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-172">string</span></span> | <span data-ttu-id="e4ae6-173">已錄製動作套用至之登錄值的名稱</span><span class="sxs-lookup"><span data-stu-id="e4ae6-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="e4ae6-174">string</span><span class="sxs-lookup"><span data-stu-id="e4ae6-174">string</span></span> | <span data-ttu-id="e4ae6-175">已錄製動作套用至之登錄值的資料</span><span class="sxs-lookup"><span data-stu-id="e4ae6-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e4ae6-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="e4ae6-176">Related topics</span></span>
- [<span data-ttu-id="e4ae6-177">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="e4ae6-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e4ae6-178">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="e4ae6-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e4ae6-179">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="e4ae6-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e4ae6-180">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="e4ae6-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e4ae6-181">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="e4ae6-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e4ae6-182">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="e4ae6-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
