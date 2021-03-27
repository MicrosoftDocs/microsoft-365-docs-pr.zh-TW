---
title: Microsoft 365 Defender 的高級搜尋中的 FileProfile () 功能
description: 瞭解如何使用 FileProfile () 豐富您的高級搜尋查詢結果中檔案的相關資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，FileProfile，file profile，function，豐富
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a9ca0af0c522205309ffdcbfd1ac28638bd197c7
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382790"
---
# <a name="fileprofile"></a><span data-ttu-id="9932a-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="9932a-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9932a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9932a-105">**Applies to:**</span></span>
- <span data-ttu-id="9932a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9932a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9932a-107">`FileProfile()`函數是[高級搜尋](advanced-hunting-overview.md)中的豐富函數，可將下列資料新增至查詢所找到的檔案。</span><span class="sxs-lookup"><span data-stu-id="9932a-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="9932a-108">欄</span><span class="sxs-lookup"><span data-stu-id="9932a-108">Column</span></span> | <span data-ttu-id="9932a-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="9932a-109">Data type</span></span> | <span data-ttu-id="9932a-110">描述</span><span class="sxs-lookup"><span data-stu-id="9932a-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="9932a-111">字串</span><span class="sxs-lookup"><span data-stu-id="9932a-111">string</span></span> | <span data-ttu-id="9932a-112">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="9932a-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="9932a-113">字串</span><span class="sxs-lookup"><span data-stu-id="9932a-113">string</span></span> | <span data-ttu-id="9932a-114">錄製的動作所套用的檔案 SHA-256</span><span class="sxs-lookup"><span data-stu-id="9932a-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="9932a-115">string</span><span class="sxs-lookup"><span data-stu-id="9932a-115">string</span></span> | <span data-ttu-id="9932a-116">錄製的動作所套用的檔案 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="9932a-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="9932a-117">int</span><span class="sxs-lookup"><span data-stu-id="9932a-117">int</span></span> | <span data-ttu-id="9932a-118">檔案大小（以位元組為單位）</span><span class="sxs-lookup"><span data-stu-id="9932a-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="9932a-119">int</span><span class="sxs-lookup"><span data-stu-id="9932a-119">int</span></span> | <span data-ttu-id="9932a-120">由 Microsoft 全域觀測的實體實例數目</span><span class="sxs-lookup"><span data-stu-id="9932a-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="9932a-121">datetime</span><span class="sxs-lookup"><span data-stu-id="9932a-121">datetime</span></span> | <span data-ttu-id="9932a-122">Microsoft 全球第一次觀測實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="9932a-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="9932a-123">datetime</span><span class="sxs-lookup"><span data-stu-id="9932a-123">datetime</span></span> | <span data-ttu-id="9932a-124">Microsoft 全球最後觀測實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="9932a-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="9932a-125">string</span><span class="sxs-lookup"><span data-stu-id="9932a-125">string</span></span> | <span data-ttu-id="9932a-126">檔案的簽署者相關資訊</span><span class="sxs-lookup"><span data-stu-id="9932a-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="9932a-127">string</span><span class="sxs-lookup"><span data-stu-id="9932a-127">string</span></span> | <span data-ttu-id="9932a-128">發證憑證授權 (CA 的相關資訊) </span><span class="sxs-lookup"><span data-stu-id="9932a-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="9932a-129">string</span><span class="sxs-lookup"><span data-stu-id="9932a-129">string</span></span> | <span data-ttu-id="9932a-130">識別簽署者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="9932a-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="9932a-131">布林值</span><span class="sxs-lookup"><span data-stu-id="9932a-131">boolean</span></span> | <span data-ttu-id="9932a-132">用於簽署檔的憑證是否有效</span><span class="sxs-lookup"><span data-stu-id="9932a-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="9932a-133">布林值</span><span class="sxs-lookup"><span data-stu-id="9932a-133">boolean</span></span> | <span data-ttu-id="9932a-134">會指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="9932a-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="9932a-135">string</span><span class="sxs-lookup"><span data-stu-id="9932a-135">string</span></span> | <span data-ttu-id="9932a-136">檔簽章的狀態： SignedValid-已使用有效的簽章簽署檔案，SignedInvalid-已簽署該檔案，但憑證無效，未簽署-檔案不會簽署，無法進行檔案的未知資訊</span><span class="sxs-lookup"><span data-stu-id="9932a-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="9932a-137">布林值</span><span class="sxs-lookup"><span data-stu-id="9932a-137">boolean</span></span> | <span data-ttu-id="9932a-138">檔案是否為可遷移的可執行檔 (PE) file</span><span class="sxs-lookup"><span data-stu-id="9932a-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="9932a-139">string</span><span class="sxs-lookup"><span data-stu-id="9932a-139">string</span></span> | <span data-ttu-id="9932a-140">找到的任何惡意程式碼或其他威脅的偵測名稱</span><span class="sxs-lookup"><span data-stu-id="9932a-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="9932a-141">string</span><span class="sxs-lookup"><span data-stu-id="9932a-141">string</span></span> | <span data-ttu-id="9932a-142">發佈檔的組織名稱</span><span class="sxs-lookup"><span data-stu-id="9932a-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="9932a-143">字串</span><span class="sxs-lookup"><span data-stu-id="9932a-143">string</span></span> | <span data-ttu-id="9932a-144">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="9932a-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="9932a-145">語法</span><span class="sxs-lookup"><span data-stu-id="9932a-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="9932a-146">引數</span><span class="sxs-lookup"><span data-stu-id="9932a-146">Arguments</span></span>

- <span data-ttu-id="9932a-147">**x**-要使用的檔案識別碼欄： `SHA1` 、、 `SHA256` `InitiatingProcessSHA1` 、 `InitiatingProcessSHA256` 或; `SHA1` 如果未指定，則函數會使用</span><span class="sxs-lookup"><span data-stu-id="9932a-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="9932a-148">**y**-對要濃縮的記錄數目的限制，1-1000;函數使用100（若未指定）</span><span class="sxs-lookup"><span data-stu-id="9932a-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="9932a-149">豐富函數只會顯示輔助性資訊（僅適用時）。</span><span class="sxs-lookup"><span data-stu-id="9932a-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="9932a-150">資訊的可用性會不同，且取決於許多因素。</span><span class="sxs-lookup"><span data-stu-id="9932a-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="9932a-151">當您在查詢中或建立自訂的偵測中使用 FileProfile () 時，請務必考慮到這一點。</span><span class="sxs-lookup"><span data-stu-id="9932a-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="9932a-152">為了獲得最佳結果，建議使用 FileProfile () 函數搭配 SHA1。</span><span class="sxs-lookup"><span data-stu-id="9932a-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="9932a-153">範例</span><span class="sxs-lookup"><span data-stu-id="9932a-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="9932a-154">僅限 Project 的 SHA1 欄並濃縮</span><span class="sxs-lookup"><span data-stu-id="9932a-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="9932a-155">豐富第一筆500記錄並列出低傳播檔</span><span class="sxs-lookup"><span data-stu-id="9932a-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="9932a-156">相關主題</span><span class="sxs-lookup"><span data-stu-id="9932a-156">Related topics</span></span>
- [<span data-ttu-id="9932a-157">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="9932a-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9932a-158">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="9932a-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9932a-159">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="9932a-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9932a-160">取得更多查詢範例</span><span class="sxs-lookup"><span data-stu-id="9932a-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
