---
title: 使用精確資料比對建立自訂敏感性資訊類型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05d5889ba690bdf61fd51044b3c059f1476342af
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964653"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="45f1a-103">使用以精確資料比對為基礎的分類建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="45f1a-103">Create custom sensitive information types with Exact Data Match based classification</span></span>



<span data-ttu-id="45f1a-104">[自訂敏感性資訊類型](sensitive-information-type-learn-about.md)用於協助識別敏感性項目，使得您可以防止不小心或不適當地將其與他人共用。</span><span class="sxs-lookup"><span data-stu-id="45f1a-104">[Custom sensitive information types](sensitive-information-type-learn-about.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="45f1a-105">您可以根據下列專案 (SIT) 定義自訂敏感資訊類型：</span><span class="sxs-lookup"><span data-stu-id="45f1a-105">You define a custom sensitive information type (SIT)based on:</span></span>

- <span data-ttu-id="45f1a-106">模式</span><span class="sxs-lookup"><span data-stu-id="45f1a-106">patterns</span></span>
- <span data-ttu-id="45f1a-107">關鍵字辨識項，例如 *員工*、*識別證* 或 *識別碼*</span><span class="sxs-lookup"><span data-stu-id="45f1a-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="45f1a-108">字元以特定模式接近證據</span><span class="sxs-lookup"><span data-stu-id="45f1a-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="45f1a-109">信賴等級</span><span class="sxs-lookup"><span data-stu-id="45f1a-109">confidence levels</span></span>

 <span data-ttu-id="45f1a-110">這類自訂敏感性資訊類型符合許多組織的業務需求。</span><span class="sxs-lookup"><span data-stu-id="45f1a-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="45f1a-111">但是，如果您想要使用精確資料值的自訂敏感性資訊類型 (SIT)，而非根據泛型模式所找到的類型，該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="45f1a-111">But what if you wanted a custom sensitive information type (SIT) that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="45f1a-112">使用以精確資料比對 (EDM) 為基礎的分類，您可以建立其設計目的為以下的自訂敏感性資訊類型：</span><span class="sxs-lookup"><span data-stu-id="45f1a-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="45f1a-113">充滿活力並可以輕鬆刷新;</span><span class="sxs-lookup"><span data-stu-id="45f1a-113">be dynamic and easily refreshed</span></span>
- <span data-ttu-id="45f1a-114">更可以調整的；</span><span class="sxs-lookup"><span data-stu-id="45f1a-114">be more scalable</span></span>
- <span data-ttu-id="45f1a-115">造成較少的誤判；</span><span class="sxs-lookup"><span data-stu-id="45f1a-115">result in fewer false-positives</span></span>
- <span data-ttu-id="45f1a-116">使用結構化的敏感性資料；</span><span class="sxs-lookup"><span data-stu-id="45f1a-116">work with structured sensitive data</span></span>
- <span data-ttu-id="45f1a-117">更安全地處理敏感性資訊；以及</span><span class="sxs-lookup"><span data-stu-id="45f1a-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="45f1a-118">能與數個 Microsoft 雲端服務搭配使用。</span><span class="sxs-lookup"><span data-stu-id="45f1a-118">be used with several Microsoft cloud services</span></span>

![以 EDM 為基礎的分類](../media/EDMClassification.png)

<span data-ttu-id="45f1a-120">以 EDM 為基礎的分類可讓您建立自訂敏感性資訊類型，其參考敏感性資訊資料庫中的確切值。</span><span class="sxs-lookup"><span data-stu-id="45f1a-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="45f1a-121">資料庫可以每日重新整理，而且可以包含最多 1 億資料列。</span><span class="sxs-lookup"><span data-stu-id="45f1a-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="45f1a-122">因此，隨著員工、病患或客戶來來去去，以及記錄變更，您的自訂敏感性資訊類型會維持最新且適用。</span><span class="sxs-lookup"><span data-stu-id="45f1a-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="45f1a-123">同時，您可以和原則一起使用以 EDM 為基礎的分類，例如[資料外洩防護原則](dlp-learn-about-dlp.md) 或 [Microsoft Cloud App Security 檔案原則](/cloud-app-security/data-protection-policies)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](dlp-learn-about-dlp.md) or [Microsoft Cloud App Security file policies](/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="45f1a-124">Microsoft 365 資訊保護在預覽版中支援下列雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="45f1a-124">Microsoft 365 Information Protection supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="45f1a-125">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="45f1a-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="45f1a-126">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="45f1a-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="45f1a-127">韓文</span><span class="sxs-lookup"><span data-stu-id="45f1a-127">Korean</span></span>
> - <span data-ttu-id="45f1a-128">日文</span><span class="sxs-lookup"><span data-stu-id="45f1a-128">Japanese</span></span>
> 
> <span data-ttu-id="45f1a-129">這項支援適用於敏感性資訊類型。</span><span class="sxs-lookup"><span data-stu-id="45f1a-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="45f1a-130">如需詳細資訊，請參閱[資訊保護支援雙位元組字元集的版本資訊 (預覽版)](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>
 

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="45f1a-131">必要的授權和權限</span><span class="sxs-lookup"><span data-stu-id="45f1a-131">Required licenses and permissions</span></span>

<span data-ttu-id="45f1a-132">您必須是全域系統管理員、合規性系統管理員或 Exchange Online 系統管理員，才能執行本文所述的工作。</span><span class="sxs-lookup"><span data-stu-id="45f1a-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="45f1a-133">若要進一步了解 DLP 權限，請參閱[權限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="45f1a-134">這些訂閱中包含 EDM 型分類</span><span class="sxs-lookup"><span data-stu-id="45f1a-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="45f1a-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="45f1a-135">Office 365 E5</span></span>
- <span data-ttu-id="45f1a-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="45f1a-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="45f1a-137">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="45f1a-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="45f1a-138">Microsoft E5/A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="45f1a-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="45f1a-139">訂閱的入口網站連結</span><span class="sxs-lookup"><span data-stu-id="45f1a-139">Portal links for your subscription</span></span>


|<span data-ttu-id="45f1a-140">入口網站</span><span class="sxs-lookup"><span data-stu-id="45f1a-140">Portal</span></span>  |<span data-ttu-id="45f1a-141">全球/GCC</span><span class="sxs-lookup"><span data-stu-id="45f1a-141">World Wide/GCC</span></span>  |<span data-ttu-id="45f1a-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="45f1a-142">GCC-High</span></span>  |<span data-ttu-id="45f1a-143">DOD</span><span class="sxs-lookup"><span data-stu-id="45f1a-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="45f1a-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="45f1a-144">Office SCC</span></span>     |  <span data-ttu-id="45f1a-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="45f1a-145">protection.office.com</span></span>       |<span data-ttu-id="45f1a-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="45f1a-146">scc.office365.us</span></span>         |<span data-ttu-id="45f1a-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="45f1a-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="45f1a-148">Microsoft 365 安全性中心</span><span class="sxs-lookup"><span data-stu-id="45f1a-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="45f1a-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="45f1a-149">security.microsoft.com</span></span>         |<span data-ttu-id="45f1a-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="45f1a-150">security.microsoft.us</span></span>         |<span data-ttu-id="45f1a-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="45f1a-151">security.apps.mil</span></span>|
|<span data-ttu-id="45f1a-152">Microsoft 365 合規性中心</span><span class="sxs-lookup"><span data-stu-id="45f1a-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="45f1a-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="45f1a-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="45f1a-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="45f1a-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="45f1a-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="45f1a-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="45f1a-156">工作流程概覽</span><span class="sxs-lookup"><span data-stu-id="45f1a-156">The work flow at a glance</span></span>

|<span data-ttu-id="45f1a-157">階段</span><span class="sxs-lookup"><span data-stu-id="45f1a-157">Phase</span></span>  |<span data-ttu-id="45f1a-158">需要的項目</span><span class="sxs-lookup"><span data-stu-id="45f1a-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="45f1a-159">第 1 部分：設定以 EDM 為基礎的分類</span><span class="sxs-lookup"><span data-stu-id="45f1a-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="45f1a-160">(視需要)</span><span class="sxs-lookup"><span data-stu-id="45f1a-160">(As needed)</span></span><br/><span data-ttu-id="45f1a-161">- [編輯資料庫結構描述](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="45f1a-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="45f1a-162">- [移除結構描述](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="45f1a-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="45f1a-163">- 敏感性資料的讀取存取權</span><span class="sxs-lookup"><span data-stu-id="45f1a-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="45f1a-164">- XML 格式的資料庫結構描述 (提供範例)</span><span class="sxs-lookup"><span data-stu-id="45f1a-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="45f1a-165">- XML 格式的規則套件 (提供範例)</span><span class="sxs-lookup"><span data-stu-id="45f1a-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="45f1a-166">- 安全性與合規性中心的系統管理員權限 (使用 PowerShell)</span><span class="sxs-lookup"><span data-stu-id="45f1a-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="45f1a-167">第 2 部分：雜湊和上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="45f1a-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="45f1a-168">(視需要)</span><span class="sxs-lookup"><span data-stu-id="45f1a-168">(As needed)</span></span><br/>[<span data-ttu-id="45f1a-169">重新整理資料</span><span class="sxs-lookup"><span data-stu-id="45f1a-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="45f1a-170">- 自訂安全性群組和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="45f1a-170">- Custom security group and user account</span></span><br/><span data-ttu-id="45f1a-171">- 具有 EDM 上傳代理程式電腦的本機系統管理員存取權</span><span class="sxs-lookup"><span data-stu-id="45f1a-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="45f1a-172">- 敏感性資料的讀取存取權</span><span class="sxs-lookup"><span data-stu-id="45f1a-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="45f1a-173">- 重新整理資料的程序和排程</span><span class="sxs-lookup"><span data-stu-id="45f1a-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="45f1a-174">第 3 部分：使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="45f1a-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="45f1a-175">- Microsoft 365 訂閱與 DLP</span><span class="sxs-lookup"><span data-stu-id="45f1a-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="45f1a-176">- 已啟用以 EDM 為基礎的分類功能</span><span class="sxs-lookup"><span data-stu-id="45f1a-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="45f1a-177">第 1 部分：設定以 EDM 為基礎的分類</span><span class="sxs-lookup"><span data-stu-id="45f1a-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="45f1a-178">設定及安裝以 EDM 為基礎的分類會涉及：</span><span class="sxs-lookup"><span data-stu-id="45f1a-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="45f1a-179">以 .csv 或 tsv 格式儲存敏感性資料</span><span class="sxs-lookup"><span data-stu-id="45f1a-179">Saving sensitive data in .csv or .tsv format</span></span>](#save-sensitive-data-in-csv-or-tsv-format)
2. [<span data-ttu-id="45f1a-180">定義您的機密資訊資料庫架構</span><span class="sxs-lookup"><span data-stu-id="45f1a-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="45f1a-181">建立規則套件</span><span class="sxs-lookup"><span data-stu-id="45f1a-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-or-tsv-format"></a><span data-ttu-id="45f1a-182">以 .csv 或 tsv 格式儲存敏感性資料</span><span class="sxs-lookup"><span data-stu-id="45f1a-182">Save sensitive data in .csv or .tsv format</span></span>

1. <span data-ttu-id="45f1a-183">找出您要使用的敏感性資訊。</span><span class="sxs-lookup"><span data-stu-id="45f1a-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="45f1a-184">將資料匯出至應用程式，例如 Microsoft Excel，並將檔案儲存在文字檔中。</span><span class="sxs-lookup"><span data-stu-id="45f1a-184">Export the data to an app, such as Microsoft Excel, and save the file in a text file.</span></span> <span data-ttu-id="45f1a-185">檔案可以儲存在 .csv (逗號分隔值) 、tsv (tab 分隔值) 或管道分隔 (|) 格式。</span><span class="sxs-lookup"><span data-stu-id="45f1a-185">The file can be saved in .csv (comma-separated values), .tsv (tab-separated values), or pipe-separated (|) format.</span></span> <span data-ttu-id="45f1a-186">在您的資料值可能包含逗號（例如街道位址）的情況下，建議使用 tsv 格式。</span><span class="sxs-lookup"><span data-stu-id="45f1a-186">The .tsv format is recommended in cases where your data values may included commas, such as street addresses.</span></span>
<span data-ttu-id="45f1a-187">資料檔案可能包含：</span><span class="sxs-lookup"><span data-stu-id="45f1a-187">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="45f1a-188">最多 1 億列敏感性資料</span><span class="sxs-lookup"><span data-stu-id="45f1a-188">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="45f1a-189">每個資料來源最多 32 個資料行 (欄位)</span><span class="sxs-lookup"><span data-stu-id="45f1a-189">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="45f1a-190">最多 5 個資料行 (欄位) 標示為可搜尋</span><span class="sxs-lookup"><span data-stu-id="45f1a-190">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="45f1a-191">在 .csv 或 tsv 檔案中構造敏感性資料，如此一來，第一列會包含用於 EDM 型分類的欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="45f1a-191">Structure the sensitive data in the .csv or .tsv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="45f1a-192">在您的檔案中，您可能會有諸如 "ssn"、"出生"、"firstname"、"lastname" 等欄位的名稱。</span><span class="sxs-lookup"><span data-stu-id="45f1a-192">In your file you might have field names such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="45f1a-193">欄標題名稱不能包含空格或底線。</span><span class="sxs-lookup"><span data-stu-id="45f1a-193">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="45f1a-194">例如，在本文我們所使用的 .csv 檔案範例稱為 *PatientRecords.csv*，而其資料行包含 *PatientID*、*MRN*、*LastName*、*FirstName*、*SSN* 等等。</span><span class="sxs-lookup"><span data-stu-id="45f1a-194">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="45f1a-195">請留意敏感性資料欄位的格式。</span><span class="sxs-lookup"><span data-stu-id="45f1a-195">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="45f1a-196">尤其是，在其內容中可能包含逗號的欄位，例如，包含值 "西雅圖，WA" 的街道位址會在分析時，視為兩個不同的欄位進行分析時，是否選取 .csv 格式。</span><span class="sxs-lookup"><span data-stu-id="45f1a-196">In particular, fields that may contain commas in their content, for example, a street address that contains the value "Seattle,WA" would be parsed as two separate fields when parsed if the .csv format is selected.</span></span> <span data-ttu-id="45f1a-197">若要避免這種情況，請使用. tsv 格式或圍繞在敏感性資料表格中的雙引號（包含值的英文）。</span><span class="sxs-lookup"><span data-stu-id="45f1a-197">To avoid this, use the .tsv format or surrounded the comma containing values by double quotes in the sensitive data table.</span></span> <span data-ttu-id="45f1a-198">如果逗號包含值也包含空格，您必須建立符合對應格式的自訂 SIT。</span><span class="sxs-lookup"><span data-stu-id="45f1a-198">If comma containing values also contain spaces, you need to create a custom SIT that matches the corresponding format.</span></span> <span data-ttu-id="45f1a-199">例如，用來偵測具有逗號和空格之多字字串的 SIT。</span><span class="sxs-lookup"><span data-stu-id="45f1a-199">For example, a SIT that detects multi-word string with commas and spaces in it.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="45f1a-200">定義用於敏感性資訊的資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="45f1a-200">Define the schema for your database of sensitive information</span></span>

<span data-ttu-id="45f1a-201">如果基於商務或技術因素，您不想使用 PowerShell 或命令列來建立結構描述和 EDM 敏感性資訊類型模式 (規則套件)，您可以使用 [完全符合結構描述和敏感性資訊類型的精靈](sit-edm-wizard.md) 來建立它們。</span><span class="sxs-lookup"><span data-stu-id="45f1a-201">If for business or technical reasons, you prefer not to use PowerShell or command line to create your schema and EDM sensitive info type pattern (rule package), you can use the [Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) to create them.</span></span> <span data-ttu-id="45f1a-202">當您完成建立結構描述和 EDM 敏感性資訊類型模式後，請返回以完成所有必要的步驟，讓您 EDM 的敏感性資訊類型可供使用。</span><span class="sxs-lookup"><span data-stu-id="45f1a-202">When you are done creating the schema and EDM sensitive info type pattern, return to complete all the steps necessary to make your EDM based sensitive information type available for use.</span></span>

> [!NOTE]
> <span data-ttu-id="45f1a-203">「完全符合結構描述和敏感性資訊類型」精靈只適用于 World Wide 和 GCC 雲端。</span><span class="sxs-lookup"><span data-stu-id="45f1a-203">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

1. <span data-ttu-id="45f1a-204">以 XML 格式定義用於敏感性資訊資料庫的結構描述 (類似以下的範例)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-204">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="45f1a-205">將此結構描述檔案命名為 **edm.xml**，然後進行設定，讓資料庫中的每一個資料行都會有使用下列語法的行：</span><span class="sxs-lookup"><span data-stu-id="45f1a-205">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="45f1a-206">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="45f1a-206">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="45f1a-207">使用資料行名稱作為 *欄位名稱* 值。</span><span class="sxs-lookup"><span data-stu-id="45f1a-207">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="45f1a-208">對您想讓它可供搜尋最多 5 個欄位的欄位，使用 *searchable="true"*。</span><span class="sxs-lookup"><span data-stu-id="45f1a-208">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="45f1a-209">至少必須有一個欄位可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="45f1a-209">At least one field must be searchable.</span></span>

      <span data-ttu-id="45f1a-210">例如，下列 XML 檔會為病患記錄資料庫定義結構描述，並將五個欄位指定為可供搜尋：*PatientID*、*MRN*、*SSN*、*Phone* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="45f1a-210">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="45f1a-211">(您可以複製、修改及使用我們的範例)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-211">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

##### <a name="configurable-match-using-the-caseinsensitive-and-ignoreddelimiters-fields"></a><span data-ttu-id="45f1a-212">使用 caseInsensitive 和 ignoredDelimiters 欄位的可設定比對</span><span class="sxs-lookup"><span data-stu-id="45f1a-212">Configurable match using the caseInsensitive and ignoredDelimiters fields</span></span>

<span data-ttu-id="45f1a-213">上列 XML 範例利用 `caseInsensitive` 和 `ignoredDelimiters` 欄位。</span><span class="sxs-lookup"><span data-stu-id="45f1a-213">The above XML sample makes use of the `caseInsensitive` and the `ignoredDelimiters` fields.</span></span> 

<span data-ttu-id="45f1a-214">當您將設定為 `true` 值的 \***caseInsensitive** _欄位包括在您的結構描述定義中，EDM 將會因 `PatientID` 欄位大小寫的不同而排除項目。</span><span class="sxs-lookup"><span data-stu-id="45f1a-214">When you include the \***caseInsensitive** _ field set to the value of `true` in your schema definition, EDM will not exclude an item based on case differences for `PatientID` field.</span></span> <span data-ttu-id="45f1a-215">因此， EDM 將會認爲 `PatientID` _ *FOO-1234*\* 和 **fOo-1234** 是一樣的。</span><span class="sxs-lookup"><span data-stu-id="45f1a-215">So EDM will see, `PatientID` _ *FOO-1234*\* and **fOo-1234** as being identical.</span></span>

<span data-ttu-id="45f1a-216">當您在 **ignoredDelimiters** _ 欄位中包括受支援的字元時，EDM 將會略過 `PatientID` 中的字元。</span><span class="sxs-lookup"><span data-stu-id="45f1a-216">When you include the \***ignoredDelimiters** _ field with supported characters,  EDM will ignore those characters in the `PatientID`.</span></span> <span data-ttu-id="45f1a-217">因此，EDM 會將 `PatientID` _ *FOO-1234*\* 和 `PatientID` **FOO#1234** 視為一樣的。</span><span class="sxs-lookup"><span data-stu-id="45f1a-217">So EDM will see, `PatientID` _ *FOO-1234*\* and `PatientID` **FOO#1234** as being identical.</span></span> <span data-ttu-id="45f1a-218">`ignoredDelimiters` 旗標支援任何非英數字元的字元，這裡有些範例：</span><span class="sxs-lookup"><span data-stu-id="45f1a-218">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="45f1a-219">\.</span><span class="sxs-lookup"><span data-stu-id="45f1a-219">\.</span></span>
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \; 

<span data-ttu-id="45f1a-220">`ignoredDelimiters` 旗標不支援：</span><span class="sxs-lookup"><span data-stu-id="45f1a-220">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="45f1a-221">0-9 字元</span><span class="sxs-lookup"><span data-stu-id="45f1a-221">characters 0-9</span></span>
- <span data-ttu-id="45f1a-222">A-Z</span><span class="sxs-lookup"><span data-stu-id="45f1a-222">A-Z</span></span>
- <span data-ttu-id="45f1a-223">a-z</span><span class="sxs-lookup"><span data-stu-id="45f1a-223">a-z</span></span>
- \"
- \,

<span data-ttu-id="45f1a-224">在這個範例中，當 `caseInsensitive` 和 `ignoredDelimiters` 均被使用時，EDM 會認爲 **FOO-1234** 和 **fOo#1234** 是一樣的，並且以病歷敏感性資訊類型來分類項目。</span><span class="sxs-lookup"><span data-stu-id="45f1a-224">In this example, where both `caseInsensitive` and `ignoredDelimiters` are used, EDM would see **FOO-1234** and **fOo#1234** as  identical and classify the item as a patient record sensitive information type.</span></span> 

4. <span data-ttu-id="45f1a-225">使用[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的程序，連線到安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="45f1a-225">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="45f1a-226">若要上傳資料庫結構描述，請執行下列 Cmdlet，一次一個：</span><span class="sxs-lookup"><span data-stu-id="45f1a-226">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="45f1a-227">系統會提示您確認，如下所示：</span><span class="sxs-lookup"><span data-stu-id="45f1a-227">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="45f1a-228">確認</span><span class="sxs-lookup"><span data-stu-id="45f1a-228">Confirm</span></span>
      >
      > <span data-ttu-id="45f1a-229">是否確定要執行此動作？</span><span class="sxs-lookup"><span data-stu-id="45f1a-229">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="45f1a-230">將匯入資料存放區 'patientrecords' 的新 EDM 結構描述。</span><span class="sxs-lookup"><span data-stu-id="45f1a-230">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="45f1a-231">\[Y\] 是 \[A\] 全部皆是 \[N\] 否 \[L\] 全部皆否 \[?\] 說明 (預設值為 "Y")：</span><span class="sxs-lookup"><span data-stu-id="45f1a-231">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="45f1a-232">若要直接變更而不進行確認，請在步驟 5 中改用此 Cmdlet：New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="45f1a-232">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="45f1a-233">這可能要花 10 到 60 分鐘的時間，才能將 EDMSchema 更新為新增項目。</span><span class="sxs-lookup"><span data-stu-id="45f1a-233">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="45f1a-234">在您執行使用新增項目的步驟之前，必須先完成更新。</span><span class="sxs-lookup"><span data-stu-id="45f1a-234">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="45f1a-235">設定規則套件</span><span class="sxs-lookup"><span data-stu-id="45f1a-235">Set up a rule package</span></span>

1. <span data-ttu-id="45f1a-236">以 XML 格式建立規則套件 (使用 Unicode 編碼方式)，類似下列範例。</span><span class="sxs-lookup"><span data-stu-id="45f1a-236">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="45f1a-237">(您可以複製、修改及使用我們的範例)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-237">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="45f1a-238">當您設定規則套件時，請務必正確參考您的 .csv 或 tsv 檔案，並 **edm.xml** 檔案。</span><span class="sxs-lookup"><span data-stu-id="45f1a-238">When you set up your rule package, make sure to correctly reference your .csv or .tsv file and **edm.xml** file.</span></span> <span data-ttu-id="45f1a-239">您可以複製、修改及使用我們的範例。</span><span class="sxs-lookup"><span data-stu-id="45f1a-239">You can copy, modify, and use our example.</span></span> <span data-ttu-id="45f1a-240">在此範例 xml 中，必須自訂下列欄位，才能建立您的 EDM 敏感性類型：</span><span class="sxs-lookup"><span data-stu-id="45f1a-240">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="45f1a-241">**RulePack id 與 ExactMatch id**：使用 [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) 產生 GUID。</span><span class="sxs-lookup"><span data-stu-id="45f1a-241">**RulePack id & ExactMatch id**: Use [New-GUID](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="45f1a-242">**資料存放區**：此欄位會指定要使用的 EDM 查閱資料存放區。</span><span class="sxs-lookup"><span data-stu-id="45f1a-242">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="45f1a-243">您要提供已設定之 EDM 結構描述的資料來源名稱。</span><span class="sxs-lookup"><span data-stu-id="45f1a-243">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="45f1a-244">**idMatch**：此欄位會指向 EDM 的主要元素。</span><span class="sxs-lookup"><span data-stu-id="45f1a-244">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="45f1a-245">相符項目：指定要在完全查閱中使用的欄位。</span><span class="sxs-lookup"><span data-stu-id="45f1a-245">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="45f1a-246">您要在資料存放區的 EDM 結構描述中，提供可搜尋的欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="45f1a-246">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="45f1a-247">分類：此欄位會指定可觸發 EDM 查閱的敏感性類型符合項目。</span><span class="sxs-lookup"><span data-stu-id="45f1a-247">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="45f1a-248">您可以提供現有內建或自訂敏感性資訊類型的名稱或 GUID。</span><span class="sxs-lookup"><span data-stu-id="45f1a-248">You can provide the Name or GUID of an existing built-in or custom sensitive information type.</span></span> <span data-ttu-id="45f1a-249">請注意，任何符合所提供之敏感性資訊類型的字串都會經過雜湊，並與敏感性資訊表中的每個項目進行比較。</span><span class="sxs-lookup"><span data-stu-id="45f1a-249">Be aware that any string that matches the sensitive information type provided will be hashed and compared to every entry in the sensitive information table.</span></span> <span data-ttu-id="45f1a-250">為了避免造成效能問題，如果您使用自訂敏感性資訊類型做為 EDM 中的分類元素，請避免使用將符合大量內容 (例如「任意數字」或「任意五個字母」的字」) 的字串，方法是在自訂分類敏感性資訊類型的定義中新增支援關鍵字或格式設定。</span><span class="sxs-lookup"><span data-stu-id="45f1a-250">In order to avoid causing performance issues, if you use a custom sensitive information type as the Classification element in EDM, avoid using one that will match a large percentage of content (such as "any number" or "any five-letter word") by adding supporting keywords or including formatting in the definition of the custom classification sensitive information type.</span></span> 

      - <span data-ttu-id="45f1a-251">**相符項目：** 此欄位會指向 idMatch 鄰近位置的其他辨識項。</span><span class="sxs-lookup"><span data-stu-id="45f1a-251">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="45f1a-252">相符項目：您要在資料存放區的 EDM 結構描述中，提供任何欄位名稱。</span><span class="sxs-lookup"><span data-stu-id="45f1a-252">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="45f1a-253">**資源：** 此區段會在多個地區設定中，指定敏感性類型的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="45f1a-253">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="45f1a-254">idRef：您要提供 ExactMatch ID 的 GUID。</span><span class="sxs-lookup"><span data-stu-id="45f1a-254">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="45f1a-255">名稱與描述：視需要自訂。</span><span class="sxs-lookup"><span data-stu-id="45f1a-255">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

2. <span data-ttu-id="45f1a-256">執行下列 PowerShell Cmdlet 以上傳規則套件，一次一個：</span><span class="sxs-lookup"><span data-stu-id="45f1a-256">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="45f1a-257">此時，您已設定以 EDM 為基礎的分類。</span><span class="sxs-lookup"><span data-stu-id="45f1a-257">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="45f1a-258">下一個步驟是要對敏感性資料雜湊，然後上傳用於編製索引的雜湊。</span><span class="sxs-lookup"><span data-stu-id="45f1a-258">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="45f1a-259">回想一下前面的程序，我們的 PatientRecords 結構描述將五個欄位定義為可搜尋：*PatientID*、*MRN*、*SSN*、*Phone* 和 *DOB*。</span><span class="sxs-lookup"><span data-stu-id="45f1a-259">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="45f1a-260">我們的範例規則套件包含這些欄位，並會參照資料庫結構描述檔案 (**edm.xml**)，一個 *ExactMatch* 項目會有一個可搜尋欄位。</span><span class="sxs-lookup"><span data-stu-id="45f1a-260">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="45f1a-261">請考慮下列 ExactMatch 項目：</span><span class="sxs-lookup"><span data-stu-id="45f1a-261">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="45f1a-262">請注意本範例中的下列重點：</span><span class="sxs-lookup"><span data-stu-id="45f1a-262">In this example, note that:</span></span>

- <span data-ttu-id="45f1a-263">資料存放區名稱會參照稍早建立的 .csv 檔案：**dataStore = "PatientRecords"**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-263">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="45f1a-264">IdMatch 值會參照可供搜尋的欄位，其列於資料庫結構描述檔案：**idMatch matches = "SSN"**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-264">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="45f1a-265">分類值會參照現有或自訂機密資訊類型：**classification = "U.S. Social Security Number (SSN)"**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-265">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="45f1a-266">(在此案例中，我們使用美國社會安全號碼作為現有的敏感性資訊類型)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-266">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="45f1a-267">這可能要花 10 到 60 分鐘的時間，才能將 EDMSchema 更新為新增項目。</span><span class="sxs-lookup"><span data-stu-id="45f1a-267">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="45f1a-268">在您執行使用新增項目的步驟之前，必須先完成更新。</span><span class="sxs-lookup"><span data-stu-id="45f1a-268">The update must complete before you execute steps that use the additions.</span></span>
 
<span data-ttu-id="45f1a-269">使用 EDM 敏感性資訊類型來匯入規則套件並匯入敏感性運算列表之後，您可以使用在合規性中心之 EDM 精靈中的 **[測試]** 函數來測試新建立的類型。</span><span class="sxs-lookup"><span data-stu-id="45f1a-269">After you have imported your rule package with your EDM sensitive info type and have imported your sensitive data table, you can test your newly created type by using the **Test** function in the EDM wizard in the compliance center.</span></span> <span data-ttu-id="45f1a-270">請參閱 [使用精確資料比對結構描述和敏感性資訊類型精靈](sit-edm-wizard.md) 有關使用此功能的指示。</span><span class="sxs-lookup"><span data-stu-id="45f1a-270">See [Use the Exact Data Match Schema and Sensitive Information Type Wizard](sit-edm-wizard.md) for instructions on using this functionality.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="45f1a-271">編輯以 EDM 為基礎的分類的結構描述</span><span class="sxs-lookup"><span data-stu-id="45f1a-271">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="45f1a-272">如果您想要變更 **edm.xml** 檔案，例如變更哪些欄位用於以 EDM 為基礎的分類，請遵循下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="45f1a-272">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

> [!TIP]
> <span data-ttu-id="45f1a-273">您可以變更您的 EDM 結構描述和資料檔案以利用 **可設定比對**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-273">You can change your EDM schema and data file to take advantage of **configurable match**.</span></span> <span data-ttu-id="45f1a-274">設定以後，EDM 將會在評估項目時，略過大小寫不同和一些分隔符。</span><span class="sxs-lookup"><span data-stu-id="45f1a-274">When configured, EDM will ignore case differences and some delimiters when it evaluates an item.</span></span> <span data-ttu-id="45f1a-275">這會讓您更容易定義您的 XML 結構描述和敏感性資料檔案。</span><span class="sxs-lookup"><span data-stu-id="45f1a-275">This makes defining your xml schema and your sensitive data files easier.</span></span> <span data-ttu-id="45f1a-276">若想深入了解，請參閲 [修改精確資料比對模式以使用可設定比對](sit-modify-edm-schema-configurable-match.md)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-276">To learn more see, [Modify Exact Data Match schema to use configurable match](sit-modify-edm-schema-configurable-match.md).</span></span>

1. <span data-ttu-id="45f1a-277">編輯您的 **edm.xml** 檔案 (這是本文 [定義結構描述](#define-the-schema-for-your-database-of-sensitive-information)這一節所討論的檔案)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-277">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="45f1a-278">使用[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的程序，連線到安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="45f1a-278">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="45f1a-279">若要更新資料庫結構描述，請執行下列 Cmdlet，一次一個：</span><span class="sxs-lookup"><span data-stu-id="45f1a-279">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="45f1a-280">系統會提示您確認，如下所示：</span><span class="sxs-lookup"><span data-stu-id="45f1a-280">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="45f1a-281">確認</span><span class="sxs-lookup"><span data-stu-id="45f1a-281">Confirm</span></span>
      >
      > <span data-ttu-id="45f1a-282">是否確定要執行此動作？</span><span class="sxs-lookup"><span data-stu-id="45f1a-282">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="45f1a-283">將更新資料存放區 'patientrecords' 的 EDM 結構描述。</span><span class="sxs-lookup"><span data-stu-id="45f1a-283">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="45f1a-284">\[Y\] 是 \[A\] 全部皆是 \[N\] 否 \[L\] 全部皆否 \[?\] 說明 (預設值為 "Y")：</span><span class="sxs-lookup"><span data-stu-id="45f1a-284">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="45f1a-285">若要直接變更而不進行確認，請在步驟 3 中改用此 Cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="45f1a-285">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="45f1a-286">這可能要花 10 到 60 分鐘的時間，才能將 EDMSchema 更新為新增項目。</span><span class="sxs-lookup"><span data-stu-id="45f1a-286">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="45f1a-287">在您執行使用新增項目的步驟之前，必須先完成更新。</span><span class="sxs-lookup"><span data-stu-id="45f1a-287">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="45f1a-288">移除以 EDM 為基礎的分類的結構描述</span><span class="sxs-lookup"><span data-stu-id="45f1a-288">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="45f1a-289">(如有需要) 如果您想要移除 EDM 型分類使用的結構描述，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="45f1a-289">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="45f1a-290">使用[連線到安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的程序，連線到安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="45f1a-290">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="45f1a-291">執行下列 PowerShell Cmdlet，將 "patientrecords" 的資料存放區名稱取代為您要移除的資料存放區名稱：</span><span class="sxs-lookup"><span data-stu-id="45f1a-291">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="45f1a-292">系統會提示您確認：</span><span class="sxs-lookup"><span data-stu-id="45f1a-292">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="45f1a-293">確認</span><span class="sxs-lookup"><span data-stu-id="45f1a-293">Confirm</span></span>
      >
      > <span data-ttu-id="45f1a-294">是否確定要執行此動作？</span><span class="sxs-lookup"><span data-stu-id="45f1a-294">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="45f1a-295">將移除資料存放區 'patientrecords' 的 EDM 結構描述。</span><span class="sxs-lookup"><span data-stu-id="45f1a-295">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="45f1a-296">\[Y\] 是 \[A\] 全部皆是 \[N\] 否 \[L\] 全部皆否 \[?\] 說明 (預設值為 "Y")：</span><span class="sxs-lookup"><span data-stu-id="45f1a-296">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="45f1a-297">若要直接變更而不進行確認，請在步驟 2 中改用此 Cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="45f1a-297">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="45f1a-298">第 2 部分：雜湊及上傳敏感性資料</span><span class="sxs-lookup"><span data-stu-id="45f1a-298">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="45f1a-299">在此階段中，您要設定自訂安全性群組和使用者帳戶，並設定 EDM Upload Agent tool 上傳代理工具。</span><span class="sxs-lookup"><span data-stu-id="45f1a-299">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="45f1a-300">然後，您可以對敏感數據使用該工具在雜湊中加入字串，然後將其上傳。</span><span class="sxs-lookup"><span data-stu-id="45f1a-300">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="45f1a-301">雜湊和上傳可以使用一部電腦來完成，或者您也可以將雜湊步驟與上傳步驟分開，以提高安全性。</span><span class="sxs-lookup"><span data-stu-id="45f1a-301">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="45f1a-302">如果您想要從一部電腦進行雜湊和上傳，您必須從一部可直接連線至 Microsoft 365 租用者的電腦執行。</span><span class="sxs-lookup"><span data-stu-id="45f1a-302">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="45f1a-303">這要求您明文的敏感性資料在該電腦上進行雜湊。</span><span class="sxs-lookup"><span data-stu-id="45f1a-303">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="45f1a-p129">如果您不想公開純文字敏感性資料檔案，可以在安全位置的電腦上雜湊，然後將雜湊檔案和 Salt 檔案複製到可直接連線到您 Microsoft 365 租用戶的電腦以進行上傳。在這個案例中，您將需要在兩部電腦上都有 EDMUploadAgent。</span><span class="sxs-lookup"><span data-stu-id="45f1a-p129">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload. In this scenario, you will need the EDMUploadAgent on both computers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45f1a-306">如果您使用「精確資料比對」結構描述和敏感性資訊類型精靈來建立結構描述和模式檔案，則 ***必須*** 下載此程序的結構描述。</span><span class="sxs-lookup"><span data-stu-id="45f1a-306">If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, you ***must*** download the schema for this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="45f1a-307">如果您的組織已[在承租人層級為 Microsoft 365 設定客戶金鑰](customer-key-overview.md)，則完全相符的資料就會自動使用其加密功能。</span><span class="sxs-lookup"><span data-stu-id="45f1a-307">If your organization has set up [Customer Key for Microsoft 365 at the tenant level](customer-key-overview.md), Exact data match will make use of its encryption functionality automatically.</span></span> <span data-ttu-id="45f1a-308">這僅適用商業雲端中的 E5 授權租用戶。</span><span class="sxs-lookup"><span data-stu-id="45f1a-308">This is available only to E5 licensed tenants in the Commercial cloud.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="45f1a-309">必要條件</span><span class="sxs-lookup"><span data-stu-id="45f1a-309">Prerequisites</span></span>

- <span data-ttu-id="45f1a-310">Microsoft 365的工作或學校帳戶, 該帳戶將新增至 **EDM\_DataUploaders** 的安全性群組</span><span class="sxs-lookup"><span data-stu-id="45f1a-310">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="45f1a-311">Windows 10 或 Windows Server 2016 電腦，其中包含執行 EDMUploadAgent 的 .NET 版本4.6.2</span><span class="sxs-lookup"><span data-stu-id="45f1a-311">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="45f1a-312">在你所上傳電腦上的目錄有：</span><span class="sxs-lookup"><span data-stu-id="45f1a-312">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="45f1a-313">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="45f1a-313">EDMUploadAgent</span></span>
    - <span data-ttu-id="45f1a-314">您的敏感專案檔案，格式為 .csv 或 tsv 格式，在我們的範例中 **PatientRecords.csv**</span><span class="sxs-lookup"><span data-stu-id="45f1a-314">your sensitive item file in .csv or .tsv format, **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="45f1a-315">以及輸出雜湊和鹽數值檔案</span><span class="sxs-lookup"><span data-stu-id="45f1a-315">and the output hash and salt files</span></span>
    - <span data-ttu-id="45f1a-316">從 **edm.xml** 檔案的資料存儲名稱，在這個範例中的如其 `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="45f1a-316">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>
- <span data-ttu-id="45f1a-317">如果您使用 [完全符合結構描述和敏感性資訊類型的資料類型精靈](sit-edm-wizard.md)，您 ***必須*** 下載它</span><span class="sxs-lookup"><span data-stu-id="45f1a-317">If you used the [Exact Data Match schema and sensitive information type wizard](sit-edm-wizard.md) you ***must*** download it</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="45f1a-318">設定安全性群組和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="45f1a-318">Set up the security group and user account</span></span>

1. <span data-ttu-id="45f1a-319">以全域系統管理員身分，使用 [適用於您訂閱的連結](#portal-links-for-your-subscription)前往系統管理中心，並建立名為 **EDM\_DataUploaders** 的 [安全性群組](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-319">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="45f1a-320">將一或多個使用者新增至 **EDM\_DataUploaders** 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="45f1a-320">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="45f1a-321">(這些使用者將管理敏感性資訊的資料庫)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-321">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="45f1a-322">雜湊並從一部電腦上傳</span><span class="sxs-lookup"><span data-stu-id="45f1a-322">Hash and upload from one computer</span></span>

<span data-ttu-id="45f1a-323">此電腦必須能夠直接存取您的 Microsoft 365 租用者。</span><span class="sxs-lookup"><span data-stu-id="45f1a-323">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="45f1a-324">開始此程序之前，請確認您是 **EDM\_DataUploaders** 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="45f1a-324">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

> [!TIP]
> <span data-ttu-id="45f1a-325">（選用）您可以在上傳之前，先執行 .csv 或 tsv 檔案的驗證：</span><span class="sxs-lookup"><span data-stu-id="45f1a-325">Optionally, you can run a validation against your .csv or .tsv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
><span data-ttu-id="45f1a-326">所有 EdmUploadAgent.exe 的相關資訊 > 已支援的參數執行</span><span class="sxs-lookup"><span data-stu-id="45f1a-326">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`


#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="45f1a-327">依訂閱類型的 EDM 上傳代理程式連結</span><span class="sxs-lookup"><span data-stu-id="45f1a-327">Links to EDM upload agent by subscription type</span></span>

- <span data-ttu-id="45f1a-328">[商業客戶 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 大多數商業客戶應使用這個</span><span class="sxs-lookup"><span data-stu-id="45f1a-328">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
- <span data-ttu-id="45f1a-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 專門針對高安全性政府雲端用戶</span><span class="sxs-lookup"><span data-stu-id="45f1a-329">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
- <span data-ttu-id="45f1a-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 專門針對美國國防部雲端客戶</span><span class="sxs-lookup"><span data-stu-id="45f1a-330">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

1. <span data-ttu-id="45f1a-331">為 EDMUploadAgent 建立工作目錄。</span><span class="sxs-lookup"><span data-stu-id="45f1a-331">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="45f1a-332">例如， **C:\EDM\Data**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-332">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="45f1a-333">將 **PatientRecords** 檔案放在這裡。</span><span class="sxs-lookup"><span data-stu-id="45f1a-333">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="45f1a-334">把適合您的訂閱, 下載並安裝到[EDM 上傳代理](#links-to-edm-upload-agent-by-subscription-type), 步驟1您所建立目錄中 。</span><span class="sxs-lookup"><span data-stu-id="45f1a-334">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

   > [!NOTE]
   > <span data-ttu-id="45f1a-335">上方連結的 EDMUploadAgent 已更新，可自動為雜湊資料新增鹽值。</span><span class="sxs-lookup"><span data-stu-id="45f1a-335">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="45f1a-336">或者，您也可以提供自己的鹽值。</span><span class="sxs-lookup"><span data-stu-id="45f1a-336">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="45f1a-337">使用此版本後，您將無法使用舊版的 EDMUploadAgent。</span><span class="sxs-lookup"><span data-stu-id="45f1a-337">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
   >
   > <span data-ttu-id="45f1a-338">您每天最多可以使用 EDMUploadAgent 將資料上傳到任何指定的資料儲存區兩次。</span><span class="sxs-lookup"><span data-stu-id="45f1a-338">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

   > [!TIP]
   > <span data-ttu-id="45f1a-p134">若要取得所支援命令參數的清單，請執行代理程式無引數。例如，'EdmUploadAgentexe'。</span><span class="sxs-lookup"><span data-stu-id="45f1a-p134">To a get a list out of the supported command parameters, run the agent no arguments. For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="45f1a-341">授權 EDM 上傳代理、開啟命令提示字元視窗（以系統管理員身分），切換至 **C:\EDM\Data** 目錄，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-341">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="45f1a-342">用您已加入EDM_DataUploaders 安全性群組的Microsoft 365的工作或學校帳戶來登入.</span><span class="sxs-lookup"><span data-stu-id="45f1a-342">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="45f1a-343">您的租戶信息將從用戶帳戶中提取出來以建立連接。</span><span class="sxs-lookup"><span data-stu-id="45f1a-343">Your tenant information is extracted from the user account to make the connection.</span></span>

   <span data-ttu-id="45f1a-344">選用：如果您使用完全符合結構描述和敏感性資料類型精靈建立結構描述和模式檔案，請在命令提示字元視窗中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-344">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

   `EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

4. <span data-ttu-id="45f1a-345">若要為敏感性資料雜湊並上傳，請在Command Prompt 命令提示字元視窗中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-345">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"]`

   <span data-ttu-id="45f1a-346">範例： **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="45f1a-346">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="45f1a-347">機密資料檔案的預設格式為以逗號分隔的值。</span><span class="sxs-lookup"><span data-stu-id="45f1a-347">The default format for the sensitive data file is comma-separated values.</span></span> <span data-ttu-id="45f1a-348">您可以指定索引標籤分隔的檔案，方法是使用/ColumnSeparator 參數指出 [{Tab}}] 選項，或者，您也可以指定 "|" 選項來指定管道分隔的檔案。</span><span class="sxs-lookup"><span data-stu-id="45f1a-348">You can specify a tab-separated file by indicating the "{Tab}" option with the /ColumnSeparator parameter, or you can specify a pipe-separated file by indicating the "|" option.</span></span>  
   <span data-ttu-id="45f1a-349">這個命令會自動將隨機產生的加密鹽值新增至雜湊，以提高安全性。</span><span class="sxs-lookup"><span data-stu-id="45f1a-349">This command will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="45f1a-350">或者，如果您想要使用自己的加密鹽值，請在命令列中新增 **/Salt <saltvalue>**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-350">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="45f1a-351">此值必須是64個字元，且只能包含 a-z 和0-9 個字元。</span><span class="sxs-lookup"><span data-stu-id="45f1a-351">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="45f1a-352">執行此命令以查看上傳狀態：</span><span class="sxs-lookup"><span data-stu-id="45f1a-352">Check the upload status by running this command:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

   <span data-ttu-id="45f1a-353">範例： **EdmUploadAgent/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="45f1a-353">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

   <span data-ttu-id="45f1a-354">尋找 **ProcessingInProgress** 的狀態。</span><span class="sxs-lookup"><span data-stu-id="45f1a-354">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="45f1a-355">每隔幾分鐘再次檢查，直到狀態變更為 **完成**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-355">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="45f1a-356">狀態完成後，您的 EDM 資料就可以使用了。</span><span class="sxs-lookup"><span data-stu-id="45f1a-356">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="45f1a-357">雜湊和上傳分開</span><span class="sxs-lookup"><span data-stu-id="45f1a-357">Separate Hash and upload</span></span>

<span data-ttu-id="45f1a-358">在安全的環境中，在電腦上執行雜湊。</span><span class="sxs-lookup"><span data-stu-id="45f1a-358">Perform the hash on a computer in a secure environment.</span></span>

<span data-ttu-id="45f1a-359">選用：如果您使用完全符合結構描述和敏感性資料類型精靈建立結構描述和模式檔案，請在命令提示字元視窗中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-359">OPTIONAL: If you used the Exact Data Match schema and sensitive information type wizard to create your schema and pattern files, run the following command in a Command Prompt window:</span></span>

`EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>`

1. <span data-ttu-id="45f1a-360">在Command Prompt 命令提示視窗中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-360">Run the following command in Command Prompt windows:</span></span>

   `EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] >`

   <span data-ttu-id="45f1a-361">例如：</span><span class="sxs-lookup"><span data-stu-id="45f1a-361">For example:</span></span>

   > <span data-ttu-id="45f1a-362">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span><span class="sxs-lookup"><span data-stu-id="45f1a-362">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml**</span></span>

   <span data-ttu-id="45f1a-363">如果您沒有指定 [**/Salt <saltvalue>**] 選項，則會輸出雜湊檔和含這些副檔名的鹽值檔案：</span><span class="sxs-lookup"><span data-stu-id="45f1a-363">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
   - <span data-ttu-id="45f1a-364">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="45f1a-364">.EdmHash</span></span>
   - <span data-ttu-id="45f1a-365">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="45f1a-365">.EdmSalt</span></span>

2. <span data-ttu-id="45f1a-366">請以安全方式將這些檔案複製到您要用來上傳機密專案 .csv 或 tsv 檔案 (PatientRecords) 至您的租使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="45f1a-366">Copy these files in a secure fashion to the computer you will use to upload your sensitive items .csv or .tsv file (PatientRecords) to your tenant.</span></span>

   <span data-ttu-id="45f1a-367">若要上傳已雜湊的資料，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-367">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

   `EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

   <span data-ttu-id="45f1a-368">例如：</span><span class="sxs-lookup"><span data-stu-id="45f1a-368">For example:</span></span>

   > <span data-ttu-id="45f1a-369">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="45f1a-369">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


   <span data-ttu-id="45f1a-370">若要確認您的敏感性資料已上傳，請在命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-370">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>

   `EdmUploadAgent.exe /GetDataStore`

   <span data-ttu-id="45f1a-371">您會看到資料存放區的清單，以及其上次更新時間。</span><span class="sxs-lookup"><span data-stu-id="45f1a-371">You'll see a list of data stores and when they were last updated.</span></span>

   <span data-ttu-id="45f1a-372">如果您想要查看上傳到特定儲存區的所有資料，請在 Windows 命令提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="45f1a-372">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

   `EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

   <span data-ttu-id="45f1a-373">針對[重新整理您的敏感性資訊資料庫](#refreshing-your-sensitive-information-database)，繼續設定程序和排程。</span><span class="sxs-lookup"><span data-stu-id="45f1a-373">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="45f1a-374">此時，您已準備好使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="45f1a-374">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="45f1a-375">例如，您可以[使用以 EDM 為基礎的分類來設定 DLP 原則](#to-create-a-dlp-policy-with-edm)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-375">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="45f1a-376">重新整理您的敏感性資訊資料庫</span><span class="sxs-lookup"><span data-stu-id="45f1a-376">Refreshing your sensitive information database</span></span>

<span data-ttu-id="45f1a-377">您可以每天重新整理您的機密資訊資料庫，而 EDM 上傳工具可以將機密資料重新編制索引，然後重新上傳 已編制索引的資料。</span><span class="sxs-lookup"><span data-stu-id="45f1a-377">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="45f1a-378">決定您重新整理敏感性資訊資料庫的程序和頻率 (每日或每週)。</span><span class="sxs-lookup"><span data-stu-id="45f1a-378">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="45f1a-379">將敏感性資料重新匯出至應用程式，例如 Microsoft Excel，並將檔案儲存為 .csv 或 tsv 格式。</span><span class="sxs-lookup"><span data-stu-id="45f1a-379">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv or .tsv format.</span></span> <span data-ttu-id="45f1a-380">遵循[雜湊及上傳敏感性資料](#part-2-hash-and-upload-the-sensitive-data)中所述的步驟時，請保留所使用的相同檔案名稱和位置。</span><span class="sxs-lookup"><span data-stu-id="45f1a-380">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="45f1a-381">若 .csv 或 tsv 檔的結構沒有任何變更 (功能變數名稱稱) ，您不需要在重新整理資料時對資料庫架構檔案進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="45f1a-381">If there are no changes to the structure (field names) of the .csv or .tsv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="45f1a-382">但如果您必須進行變更，請務必相應地編輯資料庫結構描述和規則套件。</span><span class="sxs-lookup"><span data-stu-id="45f1a-382">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="45f1a-383">使用[工作排程器](/windows/desktop/TaskSchd/task-scheduler-start-page)來將[雜湊及上傳敏感性資料](#part-2-hash-and-upload-the-sensitive-data)程序中的步驟 2 和 3 自動化。</span><span class="sxs-lookup"><span data-stu-id="45f1a-383">Use [Task Scheduler](/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="45f1a-384">您可以使用數個方法來排程工作：</span><span class="sxs-lookup"><span data-stu-id="45f1a-384">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="45f1a-385">方法</span><span class="sxs-lookup"><span data-stu-id="45f1a-385">Method</span></span>             | <span data-ttu-id="45f1a-386">處理方式</span><span class="sxs-lookup"><span data-stu-id="45f1a-386">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="45f1a-387">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f1a-387">Windows PowerShell</span></span>     | <span data-ttu-id="45f1a-388">請參閱 [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) 文件，以及本文中的[範例 PowerShell 指令碼](#example-powershell-script-for-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="45f1a-388">See the [ScheduledTasks](/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="45f1a-389">工作排程器 API</span><span class="sxs-lookup"><span data-stu-id="45f1a-389">Task Scheduler API</span></span>     | <span data-ttu-id="45f1a-390">請參閱[工作排程器](/windows/desktop/TaskSchd/using-the-task-scheduler)文件</span><span class="sxs-lookup"><span data-stu-id="45f1a-390">See the [Task Scheduler](/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="45f1a-391">Windows 使用者介面</span><span class="sxs-lookup"><span data-stu-id="45f1a-391">Windows user interface</span></span> | <span data-ttu-id="45f1a-392">在 Windows 中，按一下 [開始 **]**，然後輸入「工作排程器」。</span><span class="sxs-lookup"><span data-stu-id="45f1a-392">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="45f1a-393">然後在結果清單中，以滑鼠右鍵按一下 [工作排程器 **]**，然後選擇 [以系統管理員身分執行 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-393">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="45f1a-394">工作排程器的範例 PowerShell 指令碼</span><span class="sxs-lookup"><span data-stu-id="45f1a-394">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="45f1a-395">本節包含的範例 PowerShell 指令碼，可供您用來對雜湊資料及上傳已雜湊的資料工作進行排程：</span><span class="sxs-lookup"><span data-stu-id="45f1a-395">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="45f1a-396">在相同的步驟中排程雜湊並上傳</span><span class="sxs-lookup"><span data-stu-id="45f1a-396">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext"
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation + ' /Schema ' + $schemaFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="45f1a-397">在個別的步驟中排程雜湊和上傳</span><span class="sxs-lookup"><span data-stu-id="45f1a-397">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
$schemaext = '.xml'
\# Assuming file name is same as data store name and file is in .csv format
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming Schema file name is same as data store name
$schemaFile = "$fileLocation\\$dataStoreName$schemaext "

\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation + ' /Schema ' + $schemaFile
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password

```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="45f1a-398">第 3 部分：使用以 EDM 為基礎的分類搭配 Microsoft 雲端服務</span><span class="sxs-lookup"><span data-stu-id="45f1a-398">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="45f1a-399">這些位置支援 EDM 敏感性資訊類型：</span><span class="sxs-lookup"><span data-stu-id="45f1a-399">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="45f1a-400">適用於 Exchange Online 的 DLP (電子郵件)</span><span class="sxs-lookup"><span data-stu-id="45f1a-400">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="45f1a-401">商務用 OneDrive (檔案)</span><span class="sxs-lookup"><span data-stu-id="45f1a-401">OneDrive for Business (files)</span></span>
- <span data-ttu-id="45f1a-402">Microsoft Teams (交談)</span><span class="sxs-lookup"><span data-stu-id="45f1a-402">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="45f1a-403">適用於 SharePoint 的 DLP (檔案)</span><span class="sxs-lookup"><span data-stu-id="45f1a-403">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="45f1a-404">Microsoft Cloud App Security DLP 原則</span><span class="sxs-lookup"><span data-stu-id="45f1a-404">Microsoft Cloud App Security DLP policies</span></span>
- <span data-ttu-id="45f1a-405">伺服器端自動標籤原則-適用于商業雲端客戶和政府雲端客戶</span><span class="sxs-lookup"><span data-stu-id="45f1a-405">Server-side auto-labeling policies - available for commercial cloud customers and government cloud customers</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="45f1a-406">使用 EDM 建立 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="45f1a-406">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="45f1a-407">使用[適用於您的訂閱的連結](#portal-links-for-your-subscription)，移至安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="45f1a-407">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="45f1a-408">選擇 [資料外洩防護 **]** \> [原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-408">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="45f1a-409">選擇 [建立原則 **]** \> [自訂 **]** \> [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-409">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="45f1a-410">在 [為您的原則命名 **]** 索引標籤下，指定名稱和描述，然後選擇 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-410">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="45f1a-411">在 [選擇位置 **]** 索引標籤上，選取 [讓我選擇特定位置 **]**，然後選擇 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-411">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="45f1a-412">在 [狀態] 欄位中，選取 [Exchange 電子郵件、OneDrive 帳戶、Teams 聊天和頻道訊息]，然後選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="45f1a-412">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message**, and then choose **Next**.</span></span>

7. <span data-ttu-id="45f1a-413">在 [原則設定 **]** 索引標籤上，選擇 [使用進階設定 **]**，然後選擇 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-413">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="45f1a-414">選擇 [+ 新增規則 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-414">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="45f1a-415">在 [名稱 **]** 區段中，指定規則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="45f1a-415">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="45f1a-416">在 [條件 **]** 區段中，於 [+ 新增條件 **]** 清單中，選擇 [內容包含敏感性類型 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-416">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![內容包含敏感性資訊類型](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="45f1a-418">搜尋您設定規則套件時建立的敏感性資訊類型，然後選擇 [+ 新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-418">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="45f1a-419">然後選擇 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="45f1a-419">Then choose **Done**.</span></span>

12. <span data-ttu-id="45f1a-420">完成選取規則的選項，例如 **使用者通知**、**使用者覆寫**、**事件報告**，依此類推，然後選擇 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="45f1a-420">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="45f1a-421">在 [原則設定] 索引標籤上，檢閱您的規則，然後選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="45f1a-421">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="45f1a-422">指定是否立即開啟原則、測試它，或是保持關閉。</span><span class="sxs-lookup"><span data-stu-id="45f1a-422">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="45f1a-423">接著選擇 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="45f1a-423">Then choose **Next**.</span></span>

15. <span data-ttu-id="45f1a-424">在 [檢閱您的設定] 索引標籤上，檢閱您的原則。</span><span class="sxs-lookup"><span data-stu-id="45f1a-424">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="45f1a-425">視需要進行變更。</span><span class="sxs-lookup"><span data-stu-id="45f1a-425">Make any needed changes.</span></span> <span data-ttu-id="45f1a-426">完成後，選擇 [建立]。</span><span class="sxs-lookup"><span data-stu-id="45f1a-426">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="45f1a-427">允許大約一小時的時間，讓您的新 DLP 原則在您的整個資料中心生效。</span><span class="sxs-lookup"><span data-stu-id="45f1a-427">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="45f1a-428">相關文章</span><span class="sxs-lookup"><span data-stu-id="45f1a-428">Related articles</span></span>

- [<span data-ttu-id="45f1a-429">敏感性資訊類型實體定義</span><span class="sxs-lookup"><span data-stu-id="45f1a-429">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="45f1a-430">瞭解敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="45f1a-430">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="45f1a-431">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="45f1a-431">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="45f1a-432">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="45f1a-432">Microsoft Cloud App Security</span></span>](/cloud-app-security)
- [<span data-ttu-id="45f1a-433">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="45f1a-433">New-DlpEdmSchema</span></span>](/powershell/module/exchange/new-dlpedmschema)
- [<span data-ttu-id="45f1a-434">修改精確資料比對模式以使用可設定比對</span><span class="sxs-lookup"><span data-stu-id="45f1a-434">Modify Exact Data Match schema to use configurable match</span></span>](sit-modify-edm-schema-configurable-match.md)
