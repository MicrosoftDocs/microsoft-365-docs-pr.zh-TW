---
title: 每個裝置的匯出軟體漏洞評估
description: API 回應是每個裝置，並包含您已公開裝置上安裝的易受攻擊軟體，以及這些軟體產品中的任何已知弱點。 本表格也包含作業系統資訊、CVE 識別碼和弱點嚴重性的資訊。
keywords: api、api、export 評估、每個裝置評估、弱點評定報告、裝置弱點評估、裝置弱點報告、安全設定評估、安全設定報告、軟體漏洞評估、軟體弱點報告、依機器的弱點報告
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778308"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="d8b28-105">每個裝置的匯出軟體漏洞評估</span><span class="sxs-lookup"><span data-stu-id="d8b28-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d8b28-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d8b28-106">**Applies to:**</span></span>

- [<span data-ttu-id="d8b28-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d8b28-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8b28-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8b28-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d8b28-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d8b28-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d8b28-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d8b28-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="d8b28-111">以每個裝置為基礎，傳回所有裝置的所有已知軟體弱點及其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d8b28-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="d8b28-112">有不同的 API 呼叫可取得不同的資料類型。</span><span class="sxs-lookup"><span data-stu-id="d8b28-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="d8b28-113">因為資料量可能非常大，所以可供檢索的方式有兩種：</span><span class="sxs-lookup"><span data-stu-id="d8b28-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="d8b28-114">[匯出軟體漏洞評估 OData](#1-export-software-vulnerabilities-assessment-odata)  API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="d8b28-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="d8b28-115">這種方法適用于 _低於 100 K 裝置的小型組織_。</span><span class="sxs-lookup"><span data-stu-id="d8b28-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="d8b28-116">回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。</span><span class="sxs-lookup"><span data-stu-id="d8b28-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="d8b28-117">透過檔案[匯出軟體漏洞評估](#2-export-software-vulnerabilities-assessment-via-files)此 API 解決方案可讓大量的資料更快速且可靠地進行。</span><span class="sxs-lookup"><span data-stu-id="d8b28-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="d8b28-118">因此，建議大型組織使用超過 100 K 的裝置。</span><span class="sxs-lookup"><span data-stu-id="d8b28-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="d8b28-119">此 API 會將組織中的所有資料都提取為下載檔案。</span><span class="sxs-lookup"><span data-stu-id="d8b28-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="d8b28-120">回應包含從 Azure 儲存體下載所有資料的 URLs。</span><span class="sxs-lookup"><span data-stu-id="d8b28-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="d8b28-121">此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d8b28-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="d8b28-122">呼叫 API 以取得所有組織資料的下載 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="d8b28-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="d8b28-123">使用下載 URLs 下載所有檔案，並視需要處理資料。</span><span class="sxs-lookup"><span data-stu-id="d8b28-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="d8b28-124">使用 _OData_ _或透過_ 檔案收集 (所收集的資料，) 目前狀態的目前快照，且不包含歷史資料。</span><span class="sxs-lookup"><span data-stu-id="d8b28-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="d8b28-125">為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。</span><span class="sxs-lookup"><span data-stu-id="d8b28-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="d8b28-126">除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。</span><span class="sxs-lookup"><span data-stu-id="d8b28-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="d8b28-127">1. 匯出軟體漏洞評估 (OData) </span><span class="sxs-lookup"><span data-stu-id="d8b28-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="d8b28-128">1.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="d8b28-128">1.1 API method description</span></span>

<span data-ttu-id="d8b28-129">此 API 回應包含每個裝置已安裝軟體的所有資料。</span><span class="sxs-lookup"><span data-stu-id="d8b28-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="d8b28-130">會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="d8b28-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="d8b28-131">限制</span><span class="sxs-lookup"><span data-stu-id="d8b28-131">Limitations</span></span>

>- <span data-ttu-id="d8b28-132">頁面大小上限為200000。</span><span class="sxs-lookup"><span data-stu-id="d8b28-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="d8b28-133">此 API 的速率限制為每分鐘30個通話，每小時1000個通話。</span><span class="sxs-lookup"><span data-stu-id="d8b28-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="d8b28-134">1.2 許可權</span><span class="sxs-lookup"><span data-stu-id="d8b28-134">1.2 Permissions</span></span>

<span data-ttu-id="d8b28-135">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="d8b28-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d8b28-136">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d8b28-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="d8b28-137">許可權類型</span><span class="sxs-lookup"><span data-stu-id="d8b28-137">Permission type</span></span> | <span data-ttu-id="d8b28-138">權限</span><span class="sxs-lookup"><span data-stu-id="d8b28-138">Permission</span></span> | <span data-ttu-id="d8b28-139">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="d8b28-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="d8b28-140">應用程式</span><span class="sxs-lookup"><span data-stu-id="d8b28-140">Application</span></span> | <span data-ttu-id="d8b28-141">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="d8b28-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="d8b28-142">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="d8b28-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="d8b28-143">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="d8b28-143">Delegated (work or school account)</span></span> | <span data-ttu-id="d8b28-144">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="d8b28-144">Vulnerability.Read</span></span> | <span data-ttu-id="d8b28-145">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="d8b28-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="d8b28-146">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="d8b28-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="d8b28-147">1.4 參數</span><span class="sxs-lookup"><span data-stu-id="d8b28-147">1.4 Parameters</span></span>

- <span data-ttu-id="d8b28-148">pageSize (預設值 = 50000) –回應的結果數目</span><span class="sxs-lookup"><span data-stu-id="d8b28-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="d8b28-149">$top –傳回的結果數 (不會傳回 @odata nextLink，因此不會拉入所有資料) </span><span class="sxs-lookup"><span data-stu-id="d8b28-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="d8b28-150">1.5 屬性</span><span class="sxs-lookup"><span data-stu-id="d8b28-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="d8b28-151">每筆記錄大約是1KB 的資料。</span><span class="sxs-lookup"><span data-stu-id="d8b28-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="d8b28-152">為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。</span><span class="sxs-lookup"><span data-stu-id="d8b28-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="d8b28-153">其他一些欄可能會在回應中傳回。</span><span class="sxs-lookup"><span data-stu-id="d8b28-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="d8b28-154">這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。</span><span class="sxs-lookup"><span data-stu-id="d8b28-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="d8b28-155">下表中所定義的屬性依字母順序依屬性識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="d8b28-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="d8b28-156">執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。</span><span class="sxs-lookup"><span data-stu-id="d8b28-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="d8b28-157">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="d8b28-157">Property (ID)</span></span> | <span data-ttu-id="d8b28-158">資料類型</span><span class="sxs-lookup"><span data-stu-id="d8b28-158">Data type</span></span> | <span data-ttu-id="d8b28-159">描述</span><span class="sxs-lookup"><span data-stu-id="d8b28-159">Description</span></span> | <span data-ttu-id="d8b28-160">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="d8b28-161">CveId</span><span class="sxs-lookup"><span data-stu-id="d8b28-161">CveId</span></span> | <span data-ttu-id="d8b28-162">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-162">string</span></span> | <span data-ttu-id="d8b28-163">指派給常見漏洞及披露 (CVE) system 的安全性弱點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d8b28-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="d8b28-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="d8b28-164">CVE-2020-15992</span></span>
<span data-ttu-id="d8b28-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="d8b28-165">CvssScore</span></span> | <span data-ttu-id="d8b28-166">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-166">string</span></span> | <span data-ttu-id="d8b28-167">CVE 的 CVSS 分數。</span><span class="sxs-lookup"><span data-stu-id="d8b28-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="d8b28-168">6.2</span><span class="sxs-lookup"><span data-stu-id="d8b28-168">6.2</span></span>
<span data-ttu-id="d8b28-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="d8b28-169">DeviceId</span></span> | <span data-ttu-id="d8b28-170">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-170">string</span></span> | <span data-ttu-id="d8b28-171">服務中裝置的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d8b28-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="d8b28-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="d8b28-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="d8b28-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="d8b28-173">DeviceName</span></span> | <span data-ttu-id="d8b28-174">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-174">string</span></span> | <span data-ttu-id="d8b28-175">裝置 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="d8b28-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="d8b28-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8b28-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="d8b28-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="d8b28-177">DiskPaths</span></span>  | <span data-ttu-id="d8b28-178">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="d8b28-178">Array\[string\]</span></span> | <span data-ttu-id="d8b28-179">在裝置上安裝產品的磁片證據。</span><span class="sxs-lookup"><span data-stu-id="d8b28-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="d8b28-180">["C:\Program (x86) \Microsoft\Silverlight\Application\silverlight.exe 的檔案]]</span><span class="sxs-lookup"><span data-stu-id="d8b28-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="d8b28-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="d8b28-181">ExploitabilityLevel</span></span> | <span data-ttu-id="d8b28-182">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-182">string</span></span> | <span data-ttu-id="d8b28-183">此弱點的 exploitability 層級 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) </span><span class="sxs-lookup"><span data-stu-id="d8b28-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="d8b28-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="d8b28-184">ExploitIsInKit</span></span>
<span data-ttu-id="d8b28-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="d8b28-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="d8b28-186">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-186">string</span></span> | <span data-ttu-id="d8b28-187">第一次在裝置上看到此項產品的 CVE。</span><span class="sxs-lookup"><span data-stu-id="d8b28-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="d8b28-188">2020-11-03 10：13：34.8476880</span><span class="sxs-lookup"><span data-stu-id="d8b28-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="d8b28-189">識別碼</span><span class="sxs-lookup"><span data-stu-id="d8b28-189">Id</span></span> | <span data-ttu-id="d8b28-190">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-190">string</span></span> | <span data-ttu-id="d8b28-191">記錄的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d8b28-191">Unique identifier for the record.</span></span> | <span data-ttu-id="d8b28-192">123ABG55_573AG&mnp！</span><span class="sxs-lookup"><span data-stu-id="d8b28-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="d8b28-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="d8b28-193">LastSeenTimestamp</span></span> | <span data-ttu-id="d8b28-194">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-194">string</span></span> | <span data-ttu-id="d8b28-195">最後一次在裝置上看到 CVE。</span><span class="sxs-lookup"><span data-stu-id="d8b28-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="d8b28-196">2020-11-03 10：13：34.8476880</span><span class="sxs-lookup"><span data-stu-id="d8b28-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="d8b28-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="d8b28-197">OSPlatform</span></span> | <span data-ttu-id="d8b28-198">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-198">string</span></span> | <span data-ttu-id="d8b28-199">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="d8b28-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d8b28-200">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="d8b28-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="d8b28-201">如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。</span><span class="sxs-lookup"><span data-stu-id="d8b28-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="d8b28-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="d8b28-202">Windows10</span></span>
<span data-ttu-id="d8b28-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="d8b28-203">RbacGroupName</span></span>  | <span data-ttu-id="d8b28-204">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-204">string</span></span> | <span data-ttu-id="d8b28-205">以角色為基礎的存取控制 (RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="d8b28-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="d8b28-206">如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。</span><span class="sxs-lookup"><span data-stu-id="d8b28-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="d8b28-207">如果組織不包含任何 RBAC 群組，則此值會是 "None"。</span><span class="sxs-lookup"><span data-stu-id="d8b28-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="d8b28-208">伺服器</span><span class="sxs-lookup"><span data-stu-id="d8b28-208">Servers</span></span>
<span data-ttu-id="d8b28-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="d8b28-209">RecommendationReference</span></span> | <span data-ttu-id="d8b28-210">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-210">string</span></span> | <span data-ttu-id="d8b28-211">與此軟體相關的建議識別碼參照。</span><span class="sxs-lookup"><span data-stu-id="d8b28-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="d8b28-212">va-_-_ silverlight</span><span class="sxs-lookup"><span data-stu-id="d8b28-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="d8b28-213">RecommendedSecurityUpdate (選用) </span><span class="sxs-lookup"><span data-stu-id="d8b28-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="d8b28-214">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-214">string</span></span> | <span data-ttu-id="d8b28-215">軟體廠商提供的安全性更新名稱或描述，以解決此弱點。</span><span class="sxs-lookup"><span data-stu-id="d8b28-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="d8b28-216">2020年4月安全性更新</span><span class="sxs-lookup"><span data-stu-id="d8b28-216">April 2020 Security Updates</span></span>
<span data-ttu-id="d8b28-217">RecommendedSecurityUpdateId (選用) </span><span class="sxs-lookup"><span data-stu-id="d8b28-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="d8b28-218">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-218">string</span></span> | <span data-ttu-id="d8b28-219">對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼</span><span class="sxs-lookup"><span data-stu-id="d8b28-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="d8b28-220">4550961</span><span class="sxs-lookup"><span data-stu-id="d8b28-220">4550961</span></span>
<span data-ttu-id="d8b28-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="d8b28-221">RegistryPaths</span></span>  | <span data-ttu-id="d8b28-222">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="d8b28-222">Array\[string\]</span></span> | <span data-ttu-id="d8b28-223">產品已安裝在裝置中的登錄證據。</span><span class="sxs-lookup"><span data-stu-id="d8b28-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="d8b28-224">["HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight"]</span><span class="sxs-lookup"><span data-stu-id="d8b28-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="d8b28-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="d8b28-225">SoftwareName</span></span> | <span data-ttu-id="d8b28-226">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-226">string</span></span> | <span data-ttu-id="d8b28-227">軟體產品的名稱。</span><span class="sxs-lookup"><span data-stu-id="d8b28-227">Name of the software product.</span></span> | <span data-ttu-id="d8b28-228">鉻</span><span class="sxs-lookup"><span data-stu-id="d8b28-228">chrome</span></span>
<span data-ttu-id="d8b28-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="d8b28-229">SoftwareVendor</span></span> | <span data-ttu-id="d8b28-230">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-230">string</span></span> | <span data-ttu-id="d8b28-231">軟體廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="d8b28-231">Name of the software vendor.</span></span> | <span data-ttu-id="d8b28-232">谷歌</span><span class="sxs-lookup"><span data-stu-id="d8b28-232">google</span></span>
<span data-ttu-id="d8b28-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="d8b28-233">SoftwareVersion</span></span> | <span data-ttu-id="d8b28-234">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-234">string</span></span> | <span data-ttu-id="d8b28-235">軟體產品的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="d8b28-235">Version number of the software product.</span></span> | <span data-ttu-id="d8b28-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="d8b28-236">81.0.4044.138</span></span>
<span data-ttu-id="d8b28-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="d8b28-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="d8b28-238">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-238">string</span></span> | <span data-ttu-id="d8b28-239">依威脅環境影響的 CVSS 分數和動態因素所指派給安全性弱點的嚴重性等級。</span><span class="sxs-lookup"><span data-stu-id="d8b28-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="d8b28-240">中</span><span class="sxs-lookup"><span data-stu-id="d8b28-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="d8b28-241">1.6 範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="d8b28-242">1.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="d8b28-243">1.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-243">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="d8b28-244">2. 透過檔案匯出軟體漏洞評估 () </span><span class="sxs-lookup"><span data-stu-id="d8b28-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="d8b28-245">2.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="d8b28-245">2.1 API method description</span></span>

<span data-ttu-id="d8b28-246">此 API 回應包含每個裝置已安裝軟體的所有資料。</span><span class="sxs-lookup"><span data-stu-id="d8b28-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="d8b28-247">會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="d8b28-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="d8b28-248">2.1.2 限制</span><span class="sxs-lookup"><span data-stu-id="d8b28-248">2.1.2 Limitations</span></span>

<span data-ttu-id="d8b28-249">此 API 的速率限制是每分鐘5個通話，每小時20個通話。</span><span class="sxs-lookup"><span data-stu-id="d8b28-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="d8b28-250">2.2 許可權</span><span class="sxs-lookup"><span data-stu-id="d8b28-250">2.2 Permissions</span></span>

<span data-ttu-id="d8b28-251">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="d8b28-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d8b28-252">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="d8b28-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="d8b28-253">許可權類型</span><span class="sxs-lookup"><span data-stu-id="d8b28-253">Permission type</span></span> | <span data-ttu-id="d8b28-254">權限</span><span class="sxs-lookup"><span data-stu-id="d8b28-254">Permission</span></span> | <span data-ttu-id="d8b28-255">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="d8b28-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="d8b28-256">應用程式</span><span class="sxs-lookup"><span data-stu-id="d8b28-256">Application</span></span> | <span data-ttu-id="d8b28-257">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="d8b28-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="d8b28-258">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="d8b28-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="d8b28-259">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="d8b28-259">Delegated (work or school account)</span></span> | <span data-ttu-id="d8b28-260">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="d8b28-260">Vulnerability.Read</span></span> | <span data-ttu-id="d8b28-261">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="d8b28-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="d8b28-262">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="d8b28-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="d8b28-263">2.4 參數</span><span class="sxs-lookup"><span data-stu-id="d8b28-263">2.4 Parameters</span></span>

- <span data-ttu-id="d8b28-264">sasValidHours –下載 URLs (最長24小時內的有效時數) </span><span class="sxs-lookup"><span data-stu-id="d8b28-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="d8b28-265">2.5 屬性</span><span class="sxs-lookup"><span data-stu-id="d8b28-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="d8b28-266">這些檔案是以多行 Json 格式的 gzip 壓縮 &。</span><span class="sxs-lookup"><span data-stu-id="d8b28-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="d8b28-267">下載 URLs 只會在3小時內有效;否則您可以使用參數。</span><span class="sxs-lookup"><span data-stu-id="d8b28-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="d8b28-268">為了獲得最大的下載速度，您可以確保從您的資料所在的相同 Azure 地區下載。</span><span class="sxs-lookup"><span data-stu-id="d8b28-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="d8b28-269">每筆記錄大約是1KB 的資料。</span><span class="sxs-lookup"><span data-stu-id="d8b28-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="d8b28-270">為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。</span><span class="sxs-lookup"><span data-stu-id="d8b28-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="d8b28-271">其他一些欄可能會在回應中傳回。</span><span class="sxs-lookup"><span data-stu-id="d8b28-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="d8b28-272">這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。</span><span class="sxs-lookup"><span data-stu-id="d8b28-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="d8b28-273">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="d8b28-273">Property (ID)</span></span> | <span data-ttu-id="d8b28-274">資料類型</span><span class="sxs-lookup"><span data-stu-id="d8b28-274">Data type</span></span> | <span data-ttu-id="d8b28-275">描述</span><span class="sxs-lookup"><span data-stu-id="d8b28-275">Description</span></span> | <span data-ttu-id="d8b28-276">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="d8b28-277">匯出檔案</span><span class="sxs-lookup"><span data-stu-id="d8b28-277">Export files</span></span> | <span data-ttu-id="d8b28-278">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="d8b28-278">array\[string\]</span></span>  | <span data-ttu-id="d8b28-279">用於存放組織目前快照之檔案的下載 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="d8b28-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="d8b28-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="d8b28-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="d8b28-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="d8b28-281">GeneratedTime</span></span> | <span data-ttu-id="d8b28-282">string</span><span class="sxs-lookup"><span data-stu-id="d8b28-282">string</span></span> | <span data-ttu-id="d8b28-283">產生匯出的時間。</span><span class="sxs-lookup"><span data-stu-id="d8b28-283">The time that the export was generated.</span></span> | <span data-ttu-id="d8b28-284">2021-05-20T08：00：00Z</span><span class="sxs-lookup"><span data-stu-id="d8b28-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="d8b28-285">2.6 範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="d8b28-286">2.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="d8b28-287">2.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="d8b28-287">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="d8b28-288">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d8b28-288">See also</span></span>

- [<span data-ttu-id="d8b28-289">匯出每台裝置的評估方法和屬性</span><span class="sxs-lookup"><span data-stu-id="d8b28-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="d8b28-290">匯出每個裝置的安全設定評估</span><span class="sxs-lookup"><span data-stu-id="d8b28-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="d8b28-291">每個裝置匯出軟體清查評估</span><span class="sxs-lookup"><span data-stu-id="d8b28-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="d8b28-292">其他相關</span><span class="sxs-lookup"><span data-stu-id="d8b28-292">Other related</span></span>

- [<span data-ttu-id="d8b28-293">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="d8b28-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="d8b28-294">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="d8b28-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
