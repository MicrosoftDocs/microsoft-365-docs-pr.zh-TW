---
title: Advanced 搜尋架構中的 AlertEvidence 表格
description: 深入瞭解在高級搜尋架構的 AlertEvidence 資料表中，與產生之警示相關聯的檔案、網路位址、使用者或裝置資訊
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a0f2ae36752a4415da7c1bc39ce35bd7f744a764
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899348"
---
# <a name="alertevidence"></a><span data-ttu-id="4bd08-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="4bd08-104">AlertEvidence</span></span>

<span data-ttu-id="4bd08-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4bd08-105">**Applies to:**</span></span>
- <span data-ttu-id="4bd08-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="4bd08-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4bd08-107">[！附注] `AlertEvidence` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含各種實體（檔案、IP 位址、URLs、使用者或裝置）相關資訊，這些資訊與 Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App SECURITY 和 Azure atp 相關聯的警示相關聯。</span><span class="sxs-lookup"><span data-stu-id="4bd08-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="4bd08-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="4bd08-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4bd08-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="4bd08-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4bd08-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="4bd08-110">Column name</span></span> | <span data-ttu-id="4bd08-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="4bd08-111">Data type</span></span> | <span data-ttu-id="4bd08-112">描述</span><span class="sxs-lookup"><span data-stu-id="4bd08-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4bd08-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4bd08-113">datetime</span></span> | <span data-ttu-id="4bd08-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="4bd08-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="4bd08-115">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-115">string</span></span> | <span data-ttu-id="4bd08-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="4bd08-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="4bd08-117">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-117">string</span></span> | <span data-ttu-id="4bd08-118">物件的類型，例如檔案、進程、裝置或使用者</span><span class="sxs-lookup"><span data-stu-id="4bd08-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="4bd08-119">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-119">string</span></span> | <span data-ttu-id="4bd08-120">如何將實體包含在警示中，指出它會受到影響或僅僅是相關的</span><span class="sxs-lookup"><span data-stu-id="4bd08-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="4bd08-121">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-121">string</span></span> | <span data-ttu-id="4bd08-122">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="4bd08-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="4bd08-123">字串</span><span class="sxs-lookup"><span data-stu-id="4bd08-123">string</span></span> | <span data-ttu-id="4bd08-124">記錄動作已套用的檔案 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="4bd08-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="4bd08-125">此欄位通常未填入，可取得時請使用 SHA1 欄。</span><span class="sxs-lookup"><span data-stu-id="4bd08-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="4bd08-126">字串</span><span class="sxs-lookup"><span data-stu-id="4bd08-126">string</span></span> | <span data-ttu-id="4bd08-127">連線到的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="4bd08-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="4bd08-128">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-128">string</span></span> | <span data-ttu-id="4bd08-129">已連線到的 URL 或完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="4bd08-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="4bd08-130">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-130">string</span></span> | <span data-ttu-id="4bd08-131">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="4bd08-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="4bd08-132">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-132">string</span></span> | <span data-ttu-id="4bd08-133">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="4bd08-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="4bd08-134">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-134">string</span></span> | <span data-ttu-id="4bd08-135">帳戶的安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="4bd08-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="4bd08-136">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-136">string</span></span> | <span data-ttu-id="4bd08-137">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="4bd08-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="4bd08-138">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-138">string</span></span> | <span data-ttu-id="4bd08-139">服務中電腦的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="4bd08-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="4bd08-140">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-140">string</span></span> | <span data-ttu-id="4bd08-141">已分類的可疑或惡意檔或程式的惡意程式碼系列</span><span class="sxs-lookup"><span data-stu-id="4bd08-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="4bd08-142">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-142">string</span></span> | <span data-ttu-id="4bd08-143">指出實體是否為網路連線的來源或目的地</span><span class="sxs-lookup"><span data-stu-id="4bd08-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="4bd08-144">string</span><span class="sxs-lookup"><span data-stu-id="4bd08-144">string</span></span> | <span data-ttu-id="4bd08-145">有關 JSON 陣列格式之事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="4bd08-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4bd08-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="4bd08-146">Related topics</span></span>
- [<span data-ttu-id="4bd08-147">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="4bd08-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4bd08-148">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="4bd08-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4bd08-149">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="4bd08-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4bd08-150">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="4bd08-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4bd08-151">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="4bd08-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4bd08-152">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="4bd08-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
