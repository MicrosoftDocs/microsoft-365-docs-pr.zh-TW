---
title: 進位搜尋架構中的 AlertEvidence 資料表
description: 在進位搜尋架構的 AlertEvidence 資料表中瞭解與警示相關聯的資訊
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、資料表、資料行、資料類型、描述、警示資訊、警示、實體、證據、檔案、IP 位址、裝置、電腦、使用者、帳戶
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932297"
---
# <a name="alertevidence"></a><span data-ttu-id="0f115-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="0f115-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0f115-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="0f115-105">**Applies to:**</span></span>
- <span data-ttu-id="0f115-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f115-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0f115-107">進位搜尋架構中的表格包含與 `AlertEvidence` 來自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 及 Microsoft Defender for Identity 之警示相關聯的各種實體相關資訊，例如檔案、IP 位址[](advanced-hunting-overview.md)、URL、使用者或裝置。</span><span class="sxs-lookup"><span data-stu-id="0f115-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="0f115-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="0f115-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0f115-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="0f115-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0f115-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="0f115-110">Column name</span></span> | <span data-ttu-id="0f115-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="0f115-111">Data type</span></span> | <span data-ttu-id="0f115-112">描述</span><span class="sxs-lookup"><span data-stu-id="0f115-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0f115-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0f115-113">datetime</span></span> | <span data-ttu-id="0f115-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="0f115-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="0f115-115">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-115">string</span></span> | <span data-ttu-id="0f115-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0f115-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="0f115-117">string</span><span class="sxs-lookup"><span data-stu-id="0f115-117">string</span></span> | <span data-ttu-id="0f115-118">提供警示資訊的產品或服務</span><span class="sxs-lookup"><span data-stu-id="0f115-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="0f115-119">string</span><span class="sxs-lookup"><span data-stu-id="0f115-119">string</span></span> | <span data-ttu-id="0f115-120">物件類型，例如檔案、程式、裝置或使用者</span><span class="sxs-lookup"><span data-stu-id="0f115-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="0f115-121">string</span><span class="sxs-lookup"><span data-stu-id="0f115-121">string</span></span> | <span data-ttu-id="0f115-122">實體如何參與警示，指出該警示是否受到影響或僅與警示相關</span><span class="sxs-lookup"><span data-stu-id="0f115-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="0f115-123">string</span><span class="sxs-lookup"><span data-stu-id="0f115-123">string</span></span> | <span data-ttu-id="0f115-124">指出實體是網路連接的來源或目的地</span><span class="sxs-lookup"><span data-stu-id="0f115-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="0f115-125">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-125">string</span></span> | <span data-ttu-id="0f115-126">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="0f115-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="0f115-127">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-127">string</span></span> | <span data-ttu-id="0f115-128">包含已記錄動作所使用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="0f115-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="0f115-129">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-129">string</span></span> | <span data-ttu-id="0f115-130">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="0f115-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="0f115-131">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-131">string</span></span> | <span data-ttu-id="0f115-132">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="0f115-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="0f115-133">此欄位通常不會填出，可用時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="0f115-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="0f115-134">int</span><span class="sxs-lookup"><span data-stu-id="0f115-134">int</span></span> | <span data-ttu-id="0f115-135">檔案大小 ，以位元組為單位</span><span class="sxs-lookup"><span data-stu-id="0f115-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="0f115-136">string</span><span class="sxs-lookup"><span data-stu-id="0f115-136">string</span></span> | <span data-ttu-id="0f115-137">已分類為以下專案之可疑或惡意檔案或程式下的惡意程式碼系列</span><span class="sxs-lookup"><span data-stu-id="0f115-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="0f115-138">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-138">string</span></span> | <span data-ttu-id="0f115-139">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0f115-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="0f115-140">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-140">string</span></span> | <span data-ttu-id="0f115-141">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0f115-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="0f115-142">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-142">string</span></span> | <span data-ttu-id="0f115-143">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="0f115-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0f115-144">string</span><span class="sxs-lookup"><span data-stu-id="0f115-144">string</span></span> | <span data-ttu-id="0f115-145">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="0f115-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="0f115-146">string</span><span class="sxs-lookup"><span data-stu-id="0f115-146">string</span></span> | <span data-ttu-id="0f115-147">帳戶 (安全性) SID 識別碼</span><span class="sxs-lookup"><span data-stu-id="0f115-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0f115-148">string</span><span class="sxs-lookup"><span data-stu-id="0f115-148">string</span></span> | <span data-ttu-id="0f115-149">Azure Active Directory 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0f115-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="0f115-150">string</span><span class="sxs-lookup"><span data-stu-id="0f115-150">string</span></span> | <span data-ttu-id="0f115-151">服務中裝置的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0f115-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0f115-152">string</span><span class="sxs-lookup"><span data-stu-id="0f115-152">string</span></span> | <span data-ttu-id="0f115-153">電腦的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="0f115-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="0f115-154">string</span><span class="sxs-lookup"><span data-stu-id="0f115-154">string</span></span> | <span data-ttu-id="0f115-155">指派給通訊期間使用之本地裝置之 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0f115-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="0f115-156">string</span><span class="sxs-lookup"><span data-stu-id="0f115-156">string</span></span> | <span data-ttu-id="0f115-157">Office 365 產生的電子郵件唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0f115-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="0f115-158">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-158">string</span></span> | <span data-ttu-id="0f115-159">電子郵件的主旨</span><span class="sxs-lookup"><span data-stu-id="0f115-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="0f115-160">字串</span><span class="sxs-lookup"><span data-stu-id="0f115-160">string</span></span> | <span data-ttu-id="0f115-161">應用程式的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="0f115-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="0f115-162">string</span><span class="sxs-lookup"><span data-stu-id="0f115-162">string</span></span> | <span data-ttu-id="0f115-163">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="0f115-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="0f115-164">string</span><span class="sxs-lookup"><span data-stu-id="0f115-164">string</span></span> | <span data-ttu-id="0f115-165">用來建立新流程的命令列</span><span class="sxs-lookup"><span data-stu-id="0f115-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="0f115-166">string</span><span class="sxs-lookup"><span data-stu-id="0f115-166">string</span></span> | <span data-ttu-id="0f115-167">以 JSON 陣列格式顯示之事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="0f115-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0f115-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="0f115-168">Related topics</span></span>
- [<span data-ttu-id="0f115-169">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="0f115-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0f115-170">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="0f115-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0f115-171">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="0f115-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0f115-172">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="0f115-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0f115-173">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="0f115-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0f115-174">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="0f115-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
