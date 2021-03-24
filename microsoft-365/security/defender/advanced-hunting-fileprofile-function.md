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
ms.openlocfilehash: e511c12240512af772b3552f63ad9ed98ff105af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057303"
---
# <a name="fileprofile"></a><span data-ttu-id="bce77-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="bce77-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bce77-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bce77-105">**Applies to:**</span></span>
- <span data-ttu-id="bce77-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bce77-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bce77-107">`FileProfile()`函數是[高級搜尋](advanced-hunting-overview.md)中的豐富函數，可將下列資料新增至查詢所找到的檔案。</span><span class="sxs-lookup"><span data-stu-id="bce77-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="bce77-108">欄</span><span class="sxs-lookup"><span data-stu-id="bce77-108">Column</span></span> | <span data-ttu-id="bce77-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="bce77-109">Data type</span></span> | <span data-ttu-id="bce77-110">描述</span><span class="sxs-lookup"><span data-stu-id="bce77-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="bce77-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="bce77-111">SHA1</span></span> | <span data-ttu-id="bce77-112">字串</span><span class="sxs-lookup"><span data-stu-id="bce77-112">string</span></span> | <span data-ttu-id="bce77-113">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="bce77-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="bce77-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="bce77-114">SHA256</span></span> | <span data-ttu-id="bce77-115">string</span><span class="sxs-lookup"><span data-stu-id="bce77-115">string</span></span> | <span data-ttu-id="bce77-116">錄製的動作所套用的檔案 SHA-256</span><span class="sxs-lookup"><span data-stu-id="bce77-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="bce77-117">MD5</span><span class="sxs-lookup"><span data-stu-id="bce77-117">MD5</span></span> | <span data-ttu-id="bce77-118">string</span><span class="sxs-lookup"><span data-stu-id="bce77-118">string</span></span> | <span data-ttu-id="bce77-119">錄製的動作所套用的檔案 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="bce77-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="bce77-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="bce77-120">FileSize</span></span> | <span data-ttu-id="bce77-121">int</span><span class="sxs-lookup"><span data-stu-id="bce77-121">int</span></span> | <span data-ttu-id="bce77-122">檔案大小（以位元組為單位）</span><span class="sxs-lookup"><span data-stu-id="bce77-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="bce77-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="bce77-123">GlobalPrevalence</span></span> | <span data-ttu-id="bce77-124">int</span><span class="sxs-lookup"><span data-stu-id="bce77-124">int</span></span> | <span data-ttu-id="bce77-125">由 Microsoft 全域觀測的實體實例數目</span><span class="sxs-lookup"><span data-stu-id="bce77-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="bce77-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="bce77-126">GlobalFirstSeen</span></span> | <span data-ttu-id="bce77-127">datetime</span><span class="sxs-lookup"><span data-stu-id="bce77-127">datetime</span></span> | <span data-ttu-id="bce77-128">Microsoft 全球第一次觀測實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="bce77-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="bce77-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="bce77-129">GlobalLastSeen</span></span> | <span data-ttu-id="bce77-130">datetime</span><span class="sxs-lookup"><span data-stu-id="bce77-130">datetime</span></span> | <span data-ttu-id="bce77-131">Microsoft 全球最後觀測實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="bce77-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="bce77-132">簽名</span><span class="sxs-lookup"><span data-stu-id="bce77-132">Signer</span></span> | <span data-ttu-id="bce77-133">string</span><span class="sxs-lookup"><span data-stu-id="bce77-133">string</span></span> | <span data-ttu-id="bce77-134">檔案的簽署者相關資訊</span><span class="sxs-lookup"><span data-stu-id="bce77-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="bce77-135">發行者</span><span class="sxs-lookup"><span data-stu-id="bce77-135">Issuer</span></span> | <span data-ttu-id="bce77-136">string</span><span class="sxs-lookup"><span data-stu-id="bce77-136">string</span></span> | <span data-ttu-id="bce77-137">發證憑證授權 (CA 的相關資訊) </span><span class="sxs-lookup"><span data-stu-id="bce77-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="bce77-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="bce77-138">SignerHash</span></span> | <span data-ttu-id="bce77-139">string</span><span class="sxs-lookup"><span data-stu-id="bce77-139">string</span></span> | <span data-ttu-id="bce77-140">識別簽署者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="bce77-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="bce77-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="bce77-141">IsCertificateValid</span></span> | <span data-ttu-id="bce77-142">布林值</span><span class="sxs-lookup"><span data-stu-id="bce77-142">boolean</span></span> | <span data-ttu-id="bce77-143">用於簽署檔的憑證是否有效</span><span class="sxs-lookup"><span data-stu-id="bce77-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="bce77-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="bce77-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="bce77-145">布林值</span><span class="sxs-lookup"><span data-stu-id="bce77-145">boolean</span></span> | <span data-ttu-id="bce77-146">會指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="bce77-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="bce77-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="bce77-147">IsExecutable</span></span> | <span data-ttu-id="bce77-148">布林值</span><span class="sxs-lookup"><span data-stu-id="bce77-148">boolean</span></span> | <span data-ttu-id="bce77-149">檔案是否為可遷移的可執行檔 (PE) file</span><span class="sxs-lookup"><span data-stu-id="bce77-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="bce77-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="bce77-150">ThreatName</span></span> | <span data-ttu-id="bce77-151">string</span><span class="sxs-lookup"><span data-stu-id="bce77-151">string</span></span> | <span data-ttu-id="bce77-152">找到的任何惡意程式碼或其他威脅的偵測名稱</span><span class="sxs-lookup"><span data-stu-id="bce77-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="bce77-153">發行者</span><span class="sxs-lookup"><span data-stu-id="bce77-153">Publisher</span></span> | <span data-ttu-id="bce77-154">string</span><span class="sxs-lookup"><span data-stu-id="bce77-154">string</span></span> | <span data-ttu-id="bce77-155">發佈檔的組織名稱</span><span class="sxs-lookup"><span data-stu-id="bce77-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="bce77-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="bce77-156">SoftwareName</span></span> | <span data-ttu-id="bce77-157">字串</span><span class="sxs-lookup"><span data-stu-id="bce77-157">string</span></span> | <span data-ttu-id="bce77-158">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="bce77-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="bce77-159">語法</span><span class="sxs-lookup"><span data-stu-id="bce77-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="bce77-160">引數</span><span class="sxs-lookup"><span data-stu-id="bce77-160">Arguments</span></span>

- <span data-ttu-id="bce77-161">**x**-要使用的檔案識別碼欄： `SHA1` 、、 `SHA256` `InitiatingProcessSHA1` 、 `InitiatingProcessSHA256` 或; `SHA1` 如果未指定，則函數會使用</span><span class="sxs-lookup"><span data-stu-id="bce77-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="bce77-162">**y**-對要濃縮的記錄數目的限制，1-1000;函數使用100（若未指定）</span><span class="sxs-lookup"><span data-stu-id="bce77-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="bce77-163">豐富函數只會顯示輔助性資訊（僅適用時）。</span><span class="sxs-lookup"><span data-stu-id="bce77-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="bce77-164">資訊的可用性會不同，且取決於許多因素。</span><span class="sxs-lookup"><span data-stu-id="bce77-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="bce77-165">當您在查詢中或建立自訂的偵測中使用 FileProfile () 時，請務必考慮到這一點。</span><span class="sxs-lookup"><span data-stu-id="bce77-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="bce77-166">為了獲得最佳結果，建議使用 FileProfile () 函數搭配 SHA1。</span><span class="sxs-lookup"><span data-stu-id="bce77-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="bce77-167">範例</span><span class="sxs-lookup"><span data-stu-id="bce77-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="bce77-168">僅限 Project 的 SHA1 欄並濃縮</span><span class="sxs-lookup"><span data-stu-id="bce77-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="bce77-169">豐富第一筆500記錄並列出低傳播檔</span><span class="sxs-lookup"><span data-stu-id="bce77-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="bce77-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="bce77-170">Related topics</span></span>
- [<span data-ttu-id="bce77-171">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="bce77-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bce77-172">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="bce77-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bce77-173">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="bce77-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bce77-174">取得更多查詢範例</span><span class="sxs-lookup"><span data-stu-id="bce77-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
