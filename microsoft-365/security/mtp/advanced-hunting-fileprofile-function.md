---
title: Microsoft 365 Defender 進 (尋找中的 FileProfile () 函數
description: 瞭解如何使用 FileProfile () 來豐富進位搜尋查詢結果中檔案的資訊
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、FileProfile、檔案設定檔、函數、擴充
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929547"
---
# <a name="fileprofile"></a><span data-ttu-id="5c71a-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="5c71a-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5c71a-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="5c71a-105">**Applies to:**</span></span>
- <span data-ttu-id="5c71a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c71a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5c71a-107">此 `FileProfile()` 函數是進一步搜尋中的擴充 [函數](advanced-hunting-overview.md) ，會將下列資料新增到查詢找到的檔案中。</span><span class="sxs-lookup"><span data-stu-id="5c71a-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="5c71a-108">欄</span><span class="sxs-lookup"><span data-stu-id="5c71a-108">Column</span></span> | <span data-ttu-id="5c71a-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="5c71a-109">Data type</span></span> | <span data-ttu-id="5c71a-110">描述</span><span class="sxs-lookup"><span data-stu-id="5c71a-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="5c71a-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="5c71a-111">SHA1</span></span> | <span data-ttu-id="5c71a-112">字串</span><span class="sxs-lookup"><span data-stu-id="5c71a-112">string</span></span> | <span data-ttu-id="5c71a-113">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="5c71a-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="5c71a-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="5c71a-114">SHA256</span></span> | <span data-ttu-id="5c71a-115">string</span><span class="sxs-lookup"><span data-stu-id="5c71a-115">string</span></span> | <span data-ttu-id="5c71a-116">已記錄動作所適用于檔案的 SHA-256</span><span class="sxs-lookup"><span data-stu-id="5c71a-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="5c71a-117">MD5</span><span class="sxs-lookup"><span data-stu-id="5c71a-117">MD5</span></span> | <span data-ttu-id="5c71a-118">string</span><span class="sxs-lookup"><span data-stu-id="5c71a-118">string</span></span> | <span data-ttu-id="5c71a-119">已記錄動作所針對之檔案的 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="5c71a-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="5c71a-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="5c71a-120">FileSize</span></span> | <span data-ttu-id="5c71a-121">int</span><span class="sxs-lookup"><span data-stu-id="5c71a-121">int</span></span> | <span data-ttu-id="5c71a-122">檔案大小 ，以位元組為單位</span><span class="sxs-lookup"><span data-stu-id="5c71a-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="5c71a-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="5c71a-123">GlobalPrevalence</span></span> | <span data-ttu-id="5c71a-124">int</span><span class="sxs-lookup"><span data-stu-id="5c71a-124">int</span></span> | <span data-ttu-id="5c71a-125">Microsoft 全域觀察之實體的實例數目</span><span class="sxs-lookup"><span data-stu-id="5c71a-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="5c71a-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="5c71a-126">GlobalFirstSeen</span></span> | <span data-ttu-id="5c71a-127">datetime</span><span class="sxs-lookup"><span data-stu-id="5c71a-127">datetime</span></span> | <span data-ttu-id="5c71a-128">Microsoft 全域第一次觀察實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5c71a-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="5c71a-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="5c71a-129">GlobalLastSeen</span></span> | <span data-ttu-id="5c71a-130">datetime</span><span class="sxs-lookup"><span data-stu-id="5c71a-130">datetime</span></span> | <span data-ttu-id="5c71a-131">Microsoft 全域上次觀察實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5c71a-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="5c71a-132">簽名</span><span class="sxs-lookup"><span data-stu-id="5c71a-132">Signer</span></span> | <span data-ttu-id="5c71a-133">string</span><span class="sxs-lookup"><span data-stu-id="5c71a-133">string</span></span> | <span data-ttu-id="5c71a-134">檔案簽署者的資訊</span><span class="sxs-lookup"><span data-stu-id="5c71a-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="5c71a-135">發行者</span><span class="sxs-lookup"><span data-stu-id="5c71a-135">Issuer</span></span> | <span data-ttu-id="5c71a-136">string</span><span class="sxs-lookup"><span data-stu-id="5c71a-136">string</span></span> | <span data-ttu-id="5c71a-137">發行憑證授權單位 (CA) </span><span class="sxs-lookup"><span data-stu-id="5c71a-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="5c71a-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="5c71a-138">SignerHash</span></span> | <span data-ttu-id="5c71a-139">string</span><span class="sxs-lookup"><span data-stu-id="5c71a-139">string</span></span> | <span data-ttu-id="5c71a-140">識別簽簽者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="5c71a-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="5c71a-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="5c71a-141">IsCertificateValid</span></span> | <span data-ttu-id="5c71a-142">布林值</span><span class="sxs-lookup"><span data-stu-id="5c71a-142">boolean</span></span> | <span data-ttu-id="5c71a-143">用來簽署檔案的憑證是否有效</span><span class="sxs-lookup"><span data-stu-id="5c71a-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="5c71a-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="5c71a-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="5c71a-145">布林值</span><span class="sxs-lookup"><span data-stu-id="5c71a-145">boolean</span></span> | <span data-ttu-id="5c71a-146">指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c71a-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="5c71a-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="5c71a-147">IsExecutable</span></span> | <span data-ttu-id="5c71a-148">布林值</span><span class="sxs-lookup"><span data-stu-id="5c71a-148">boolean</span></span> | <span data-ttu-id="5c71a-149">檔案為可攜式可執行檔 (PE) 檔案</span><span class="sxs-lookup"><span data-stu-id="5c71a-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="5c71a-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="5c71a-150">ThreatName</span></span> | <span data-ttu-id="5c71a-151">string</span><span class="sxs-lookup"><span data-stu-id="5c71a-151">string</span></span> | <span data-ttu-id="5c71a-152">找到任何惡意攻擊或其他威脅的偵測名稱</span><span class="sxs-lookup"><span data-stu-id="5c71a-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="5c71a-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="5c71a-153">Publisher</span></span> | <span data-ttu-id="5c71a-154">string</span><span class="sxs-lookup"><span data-stu-id="5c71a-154">string</span></span> | <span data-ttu-id="5c71a-155">發佈檔案的組織名稱</span><span class="sxs-lookup"><span data-stu-id="5c71a-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="5c71a-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="5c71a-156">SoftwareName</span></span> | <span data-ttu-id="5c71a-157">字串</span><span class="sxs-lookup"><span data-stu-id="5c71a-157">string</span></span> | <span data-ttu-id="5c71a-158">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="5c71a-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="5c71a-159">語法</span><span class="sxs-lookup"><span data-stu-id="5c71a-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="5c71a-160">引數</span><span class="sxs-lookup"><span data-stu-id="5c71a-160">Arguments</span></span>

- <span data-ttu-id="5c71a-161">**x**—未指定時，會使用檔案識別碼資料行：、、或 `SHA1` `SHA256` ; `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` 函數</span><span class="sxs-lookup"><span data-stu-id="5c71a-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="5c71a-162">**y**— 限制要豐富記錄的數量，1-1000;函數使用 100 未指定時</span><span class="sxs-lookup"><span data-stu-id="5c71a-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="5c71a-163">範例</span><span class="sxs-lookup"><span data-stu-id="5c71a-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="5c71a-164">只預計 SHA1 欄並豐富</span><span class="sxs-lookup"><span data-stu-id="5c71a-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="5c71a-165">豐富前 500 個記錄，並列出低品質檔案</span><span class="sxs-lookup"><span data-stu-id="5c71a-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="5c71a-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="5c71a-166">Related topics</span></span>
- [<span data-ttu-id="5c71a-167">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="5c71a-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5c71a-168">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="5c71a-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5c71a-169">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="5c71a-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5c71a-170">取得更多查詢範例</span><span class="sxs-lookup"><span data-stu-id="5c71a-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
