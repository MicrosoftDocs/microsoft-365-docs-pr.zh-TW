---
title: Advanced 搜尋架構中的 AlertEvidence 表格
description: 深入瞭解與高級搜尋架構之 AlertEvidence 表格中的警示相關的資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，AlertInfo，alert，實體，證據，檔案，IP 位址，裝置，機器，使用者，帳戶
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
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430160"
---
# <a name="alertevidence"></a><span data-ttu-id="ef84b-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="ef84b-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ef84b-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef84b-105">**Applies to:**</span></span>
- <span data-ttu-id="ef84b-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="ef84b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ef84b-107">[！附注] `AlertEvidence` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含各種實體（檔案、IP 位址、URLs、使用者或裝置）相關資訊，這些資訊與 Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App SECURITY 和 Azure atp 相關聯的警示相關聯。</span><span class="sxs-lookup"><span data-stu-id="ef84b-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="ef84b-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="ef84b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ef84b-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="ef84b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ef84b-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="ef84b-110">Column name</span></span> | <span data-ttu-id="ef84b-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="ef84b-111">Data type</span></span> | <span data-ttu-id="ef84b-112">描述</span><span class="sxs-lookup"><span data-stu-id="ef84b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ef84b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ef84b-113">datetime</span></span> | <span data-ttu-id="ef84b-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="ef84b-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="ef84b-115">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-115">string</span></span> | <span data-ttu-id="ef84b-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="ef84b-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="ef84b-117">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-117">string</span></span> | <span data-ttu-id="ef84b-118">提供提醒資訊的產品或服務</span><span class="sxs-lookup"><span data-stu-id="ef84b-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="ef84b-119">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-119">string</span></span> | <span data-ttu-id="ef84b-120">物件的類型，例如檔案、進程、裝置或使用者</span><span class="sxs-lookup"><span data-stu-id="ef84b-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="ef84b-121">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-121">string</span></span> | <span data-ttu-id="ef84b-122">如何將實體包含在警示中，指出它會受到影響或僅僅是相關的</span><span class="sxs-lookup"><span data-stu-id="ef84b-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="ef84b-123">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-123">string</span></span> | <span data-ttu-id="ef84b-124">指出實體是否為網路連線的來源或目的地</span><span class="sxs-lookup"><span data-stu-id="ef84b-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="ef84b-125">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-125">string</span></span> | <span data-ttu-id="ef84b-126">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="ef84b-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="ef84b-127">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-127">string</span></span> | <span data-ttu-id="ef84b-128">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="ef84b-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="ef84b-129">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-129">string</span></span> | <span data-ttu-id="ef84b-130">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="ef84b-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="ef84b-131">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-131">string</span></span> | <span data-ttu-id="ef84b-132">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="ef84b-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="ef84b-133">通常不會填入此欄位，可用時使用 SHA1] 欄位。</span><span class="sxs-lookup"><span data-stu-id="ef84b-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="ef84b-134">int</span><span class="sxs-lookup"><span data-stu-id="ef84b-134">int</span></span> | <span data-ttu-id="ef84b-135">檔案大小（以位元組為單位）</span><span class="sxs-lookup"><span data-stu-id="ef84b-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="ef84b-136">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-136">string</span></span> | <span data-ttu-id="ef84b-137">已分類的可疑或惡意檔或程式的惡意程式碼系列</span><span class="sxs-lookup"><span data-stu-id="ef84b-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="ef84b-138">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-138">string</span></span> | <span data-ttu-id="ef84b-139">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ef84b-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="ef84b-140">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-140">string</span></span> | <span data-ttu-id="ef84b-141">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ef84b-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="ef84b-142">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-142">string</span></span> | <span data-ttu-id="ef84b-143">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="ef84b-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ef84b-144">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-144">string</span></span> | <span data-ttu-id="ef84b-145">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="ef84b-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="ef84b-146">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-146">string</span></span> | <span data-ttu-id="ef84b-147">帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="ef84b-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="ef84b-148">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-148">string</span></span> | <span data-ttu-id="ef84b-149">Azure Active Directory 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="ef84b-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="ef84b-150">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-150">string</span></span> | <span data-ttu-id="ef84b-151">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="ef84b-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ef84b-152">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-152">string</span></span> | <span data-ttu-id="ef84b-153">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ef84b-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="ef84b-154">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-154">string</span></span> | <span data-ttu-id="ef84b-155">指派給通訊期間所使用之本機裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ef84b-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="ef84b-156">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-156">string</span></span> | <span data-ttu-id="ef84b-157">Office 365 產生的電子郵件唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="ef84b-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="ef84b-158">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-158">string</span></span> | <span data-ttu-id="ef84b-159">電子郵件的主旨</span><span class="sxs-lookup"><span data-stu-id="ef84b-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="ef84b-160">字串</span><span class="sxs-lookup"><span data-stu-id="ef84b-160">string</span></span> | <span data-ttu-id="ef84b-161">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="ef84b-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="ef84b-162">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-162">string</span></span> | <span data-ttu-id="ef84b-163">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="ef84b-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="ef84b-164">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-164">string</span></span> | <span data-ttu-id="ef84b-165">用來建立新程式的命令列</span><span class="sxs-lookup"><span data-stu-id="ef84b-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="ef84b-166">string</span><span class="sxs-lookup"><span data-stu-id="ef84b-166">string</span></span> | <span data-ttu-id="ef84b-167">有關 JSON 陣列格式之事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="ef84b-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ef84b-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="ef84b-168">Related topics</span></span>
- [<span data-ttu-id="ef84b-169">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="ef84b-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ef84b-170">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="ef84b-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ef84b-171">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="ef84b-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ef84b-172">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="ef84b-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ef84b-173">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="ef84b-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ef84b-174">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="ef84b-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
