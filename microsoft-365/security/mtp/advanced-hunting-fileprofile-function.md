---
title: 'FileProfile Microsoft 威脅防護的高級搜尋中的 ( # A1 函數'
description: '瞭解如何使用 FileProfile ( # A1，以濃縮您的高級搜尋查詢結果中檔案的相關資訊。'
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，FileProfile，file profile，function，豐富
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: a89622206917c6b343ce47638c443b789513367b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412175"
---
# <a name="fileprofile"></a><span data-ttu-id="20d98-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="20d98-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="20d98-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="20d98-105">**Applies to:**</span></span>
- <span data-ttu-id="20d98-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="20d98-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="20d98-107">`FileProfile()`函數是[高級搜尋](advanced-hunting-overview.md)中的豐富函數，可將下列資料新增至查詢所找到的檔案。</span><span class="sxs-lookup"><span data-stu-id="20d98-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="20d98-108">欄</span><span class="sxs-lookup"><span data-stu-id="20d98-108">Column</span></span> | <span data-ttu-id="20d98-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="20d98-109">Data type</span></span> | <span data-ttu-id="20d98-110">描述</span><span class="sxs-lookup"><span data-stu-id="20d98-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="20d98-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="20d98-111">SHA1</span></span> | <span data-ttu-id="20d98-112">字串</span><span class="sxs-lookup"><span data-stu-id="20d98-112">string</span></span> | <span data-ttu-id="20d98-113">記錄動作已套用的檔案 SHA-1</span><span class="sxs-lookup"><span data-stu-id="20d98-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="20d98-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="20d98-114">SHA256</span></span> | <span data-ttu-id="20d98-115">string</span><span class="sxs-lookup"><span data-stu-id="20d98-115">string</span></span> | <span data-ttu-id="20d98-116">錄製的動作所套用的檔案 SHA-256</span><span class="sxs-lookup"><span data-stu-id="20d98-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="20d98-117">MD5</span><span class="sxs-lookup"><span data-stu-id="20d98-117">MD5</span></span> | <span data-ttu-id="20d98-118">string</span><span class="sxs-lookup"><span data-stu-id="20d98-118">string</span></span> | <span data-ttu-id="20d98-119">錄製的動作所套用的檔案 MD5 雜湊</span><span class="sxs-lookup"><span data-stu-id="20d98-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="20d98-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="20d98-120">FileSize</span></span> | <span data-ttu-id="20d98-121">int</span><span class="sxs-lookup"><span data-stu-id="20d98-121">int</span></span> | <span data-ttu-id="20d98-122">檔案大小（以位元組為單位）</span><span class="sxs-lookup"><span data-stu-id="20d98-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="20d98-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="20d98-123">GlobalPrevalence</span></span> | <span data-ttu-id="20d98-124">int</span><span class="sxs-lookup"><span data-stu-id="20d98-124">int</span></span> | <span data-ttu-id="20d98-125">由 Microsoft 全域觀測的實體實例數目</span><span class="sxs-lookup"><span data-stu-id="20d98-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="20d98-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="20d98-126">GlobalFirstSeen</span></span> | <span data-ttu-id="20d98-127">datetime</span><span class="sxs-lookup"><span data-stu-id="20d98-127">datetime</span></span> | <span data-ttu-id="20d98-128">Microsoft 全球第一次觀測實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="20d98-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="20d98-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="20d98-129">GlobalLastSeen</span></span> | <span data-ttu-id="20d98-130">datetime</span><span class="sxs-lookup"><span data-stu-id="20d98-130">datetime</span></span> | <span data-ttu-id="20d98-131">Microsoft 全球最後觀測實體的日期和時間</span><span class="sxs-lookup"><span data-stu-id="20d98-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="20d98-132">簽名</span><span class="sxs-lookup"><span data-stu-id="20d98-132">Signer</span></span> | <span data-ttu-id="20d98-133">string</span><span class="sxs-lookup"><span data-stu-id="20d98-133">string</span></span> | <span data-ttu-id="20d98-134">檔案的簽署者相關資訊</span><span class="sxs-lookup"><span data-stu-id="20d98-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="20d98-135">發行者</span><span class="sxs-lookup"><span data-stu-id="20d98-135">Issuer</span></span> | <span data-ttu-id="20d98-136">string</span><span class="sxs-lookup"><span data-stu-id="20d98-136">string</span></span> | <span data-ttu-id="20d98-137">發證憑證授權 (CA 的相關資訊) </span><span class="sxs-lookup"><span data-stu-id="20d98-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="20d98-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="20d98-138">SignerHash</span></span> | <span data-ttu-id="20d98-139">string</span><span class="sxs-lookup"><span data-stu-id="20d98-139">string</span></span> | <span data-ttu-id="20d98-140">識別簽署者的唯一雜湊值</span><span class="sxs-lookup"><span data-stu-id="20d98-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="20d98-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="20d98-141">IsCertificateValid</span></span> | <span data-ttu-id="20d98-142">布林值</span><span class="sxs-lookup"><span data-stu-id="20d98-142">boolean</span></span> | <span data-ttu-id="20d98-143">用於簽署檔的憑證是否有效</span><span class="sxs-lookup"><span data-stu-id="20d98-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="20d98-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="20d98-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="20d98-145">布林值</span><span class="sxs-lookup"><span data-stu-id="20d98-145">boolean</span></span> | <span data-ttu-id="20d98-146">會指出根憑證的簽署者是否為 Microsoft</span><span class="sxs-lookup"><span data-stu-id="20d98-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="20d98-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="20d98-147">IsExecutable</span></span> | <span data-ttu-id="20d98-148">布林值</span><span class="sxs-lookup"><span data-stu-id="20d98-148">boolean</span></span> | <span data-ttu-id="20d98-149">檔案是否為可遷移的可執行檔 (PE) file</span><span class="sxs-lookup"><span data-stu-id="20d98-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="20d98-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="20d98-150">ThreatName</span></span> | <span data-ttu-id="20d98-151">string</span><span class="sxs-lookup"><span data-stu-id="20d98-151">string</span></span> | <span data-ttu-id="20d98-152">找到的任何惡意程式碼或其他威脅的偵測名稱</span><span class="sxs-lookup"><span data-stu-id="20d98-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="20d98-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="20d98-153">Publisher</span></span> | <span data-ttu-id="20d98-154">string</span><span class="sxs-lookup"><span data-stu-id="20d98-154">string</span></span> | <span data-ttu-id="20d98-155">發佈檔的組織名稱</span><span class="sxs-lookup"><span data-stu-id="20d98-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="20d98-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="20d98-156">SoftwareName</span></span> | <span data-ttu-id="20d98-157">字串</span><span class="sxs-lookup"><span data-stu-id="20d98-157">string</span></span> | <span data-ttu-id="20d98-158">軟體產品名稱</span><span class="sxs-lookup"><span data-stu-id="20d98-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="20d98-159">語法</span><span class="sxs-lookup"><span data-stu-id="20d98-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="20d98-160">引數</span><span class="sxs-lookup"><span data-stu-id="20d98-160">Arguments</span></span>

- <span data-ttu-id="20d98-161">**x**-要使用的檔案識別碼欄： `SHA1` 、、 `SHA256` `InitiatingProcessSHA1` 、 `InitiatingProcessSHA256` 或; `SHA1` 如果未指定，則函數會使用</span><span class="sxs-lookup"><span data-stu-id="20d98-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="20d98-162">**y**-對要濃縮的記錄數目的限制，1-1000;函數使用100（若未指定）</span><span class="sxs-lookup"><span data-stu-id="20d98-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="20d98-163">範例</span><span class="sxs-lookup"><span data-stu-id="20d98-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="20d98-164">僅限 Project 的 SHA1 欄並濃縮</span><span class="sxs-lookup"><span data-stu-id="20d98-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="20d98-165">豐富第一筆500記錄並列出低傳播檔</span><span class="sxs-lookup"><span data-stu-id="20d98-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="20d98-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="20d98-166">Related topics</span></span>
- [<span data-ttu-id="20d98-167">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="20d98-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="20d98-168">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="20d98-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="20d98-169">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="20d98-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="20d98-170">取得更多查詢範例</span><span class="sxs-lookup"><span data-stu-id="20d98-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
