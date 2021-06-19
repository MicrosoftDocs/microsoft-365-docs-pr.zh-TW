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
ms.openlocfilehash: 6243da415c5cc509be33eabffd12516367164bff
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022867"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="c1e58-105">每個裝置的匯出軟體漏洞評估</span><span class="sxs-lookup"><span data-stu-id="c1e58-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1e58-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="c1e58-106">**Applies to:**</span></span>

- [<span data-ttu-id="c1e58-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c1e58-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c1e58-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1e58-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c1e58-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="c1e58-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c1e58-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="c1e58-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="c1e58-111">以每個裝置為基礎，傳回所有裝置的所有已知軟體弱點及其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="c1e58-112">有不同的 API 呼叫可取得不同的資料類型。</span><span class="sxs-lookup"><span data-stu-id="c1e58-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="c1e58-113">因為資料量可能非常大，所以可供檢索的方式有兩種：</span><span class="sxs-lookup"><span data-stu-id="c1e58-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="c1e58-114">[匯出軟體漏洞評估 **JSON 回應**](#1-export-software-vulnerabilities-assessment-json-response)  API 將組織中的所有資料都提取為 Json 回應。</span><span class="sxs-lookup"><span data-stu-id="c1e58-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="c1e58-115">這種方法適用于 _低於 100 K 裝置的小型組織_。</span><span class="sxs-lookup"><span data-stu-id="c1e58-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="c1e58-116">回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。</span><span class="sxs-lookup"><span data-stu-id="c1e58-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="c1e58-117">透過檔案[匯出軟體漏洞評估](#2-export-software-vulnerabilities-assessment-via-files)此 API 解決方案可讓大量的資料更快速且可靠地進行。</span><span class="sxs-lookup"><span data-stu-id="c1e58-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="c1e58-118">針對大型組織，建議使用透過檔案，且包含超過 100 K 個裝置。</span><span class="sxs-lookup"><span data-stu-id="c1e58-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="c1e58-119">此 API 會將組織中的所有資料都提取為下載檔案。</span><span class="sxs-lookup"><span data-stu-id="c1e58-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="c1e58-120">回應包含從 Azure 儲存體下載所有資料的 URLs。</span><span class="sxs-lookup"><span data-stu-id="c1e58-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="c1e58-121">此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c1e58-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="c1e58-122">呼叫 API 以取得所有組織資料的下載 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="c1e58-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="c1e58-123">使用下載 URLs 下載所有檔案，並視需要處理資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="c1e58-124">[Delta export 軟體漏洞評估 **JSON 回應**](#3-delta-export-software-vulnerabilities-assessment-json-response)  會傳回表格，其中每個唯一的組合： DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 及 EventTimestamp。</span><span class="sxs-lookup"><span data-stu-id="c1e58-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="c1e58-125">API 將組織中的資料提取為 Json 回應。</span><span class="sxs-lookup"><span data-stu-id="c1e58-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="c1e58-126">回應已分頁，所以您可以 @odata 使用來自回應的 nextLink 欄位，以提取下一個結果。</span><span class="sxs-lookup"><span data-stu-id="c1e58-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="c1e58-127">與完整的「軟體弱點評估 (JSON 回應) 」（用來取得組織的軟體漏洞評估整個快照）不同（「增量匯出 OData API 呼叫）是用來只提取選取日期和目前日期之間所發生的變更 (「delta」 API 通話) 。</span><span class="sxs-lookup"><span data-stu-id="c1e58-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="c1e58-128">您不需要每次獲得大量資料的完整匯出，只會取得新的、已修復和更新之弱點的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="c1e58-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="c1e58-129">Delta export JSON 回應 API 通話也可以用來計算不同的 KPIs 例如「修復多少個漏洞？」。</span><span class="sxs-lookup"><span data-stu-id="c1e58-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="c1e58-130">或「我的組織新增了多少個新的漏洞？」</span><span class="sxs-lookup"><span data-stu-id="c1e58-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="c1e58-131">因為軟體弱點的 Delta export JSON 回應 API 呼叫只會傳回目標日期範圍的資料，所以不會被視為 _完整匯出_。</span><span class="sxs-lookup"><span data-stu-id="c1e58-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="c1e58-132">使用 _OData_ _或透過_ 檔案收集 (所收集的資料，) 目前狀態的目前快照，且不包含歷史資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="c1e58-133">為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。</span><span class="sxs-lookup"><span data-stu-id="c1e58-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="c1e58-134">除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。</span><span class="sxs-lookup"><span data-stu-id="c1e58-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="c1e58-135">1. 匯出軟體漏洞評估 (JSON 回應) </span><span class="sxs-lookup"><span data-stu-id="c1e58-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="c1e58-136">1.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="c1e58-136">1.1 API method description</span></span>

<span data-ttu-id="c1e58-137">此 API 回應包含每個裝置已安裝軟體的所有資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="c1e58-138">會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="c1e58-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="c1e58-139">1.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="c1e58-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="c1e58-140">頁面大小上限為200000。</span><span class="sxs-lookup"><span data-stu-id="c1e58-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="c1e58-141">此 API 的速率限制為每分鐘30個通話，每小時1000個通話。</span><span class="sxs-lookup"><span data-stu-id="c1e58-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="c1e58-142">1.2 許可權</span><span class="sxs-lookup"><span data-stu-id="c1e58-142">1.2 Permissions</span></span>

<span data-ttu-id="c1e58-143">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="c1e58-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c1e58-144">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c1e58-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="c1e58-145">許可權類型</span><span class="sxs-lookup"><span data-stu-id="c1e58-145">Permission type</span></span> | <span data-ttu-id="c1e58-146">權限</span><span class="sxs-lookup"><span data-stu-id="c1e58-146">Permission</span></span> | <span data-ttu-id="c1e58-147">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c1e58-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="c1e58-148">應用程式</span><span class="sxs-lookup"><span data-stu-id="c1e58-148">Application</span></span> | <span data-ttu-id="c1e58-149">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="c1e58-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="c1e58-150">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="c1e58-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="c1e58-151">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="c1e58-151">Delegated (work or school account)</span></span> | <span data-ttu-id="c1e58-152">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="c1e58-152">Vulnerability.Read</span></span> | <span data-ttu-id="c1e58-153">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="c1e58-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="c1e58-154">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="c1e58-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="c1e58-155">1.4 參數</span><span class="sxs-lookup"><span data-stu-id="c1e58-155">1.4 Parameters</span></span>

- <span data-ttu-id="c1e58-156">pageSize (預設值 = 50000) –回應的結果數目</span><span class="sxs-lookup"><span data-stu-id="c1e58-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="c1e58-157">$top –傳回的結果數 (不會傳回 @odata nextLink，因此不會拉入所有資料) </span><span class="sxs-lookup"><span data-stu-id="c1e58-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="c1e58-158">1.5 屬性</span><span class="sxs-lookup"><span data-stu-id="c1e58-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="c1e58-159">每筆記錄大約是 1 KB 的資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="c1e58-160">為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。</span><span class="sxs-lookup"><span data-stu-id="c1e58-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="c1e58-161">其他一些欄可能會在回應中傳回。</span><span class="sxs-lookup"><span data-stu-id="c1e58-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="c1e58-162">這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。</span><span class="sxs-lookup"><span data-stu-id="c1e58-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="c1e58-163">下表中所定義的屬性依字母順序依屬性識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="c1e58-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="c1e58-164">執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。</span><span class="sxs-lookup"><span data-stu-id="c1e58-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="c1e58-165">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="c1e58-165">Property (ID)</span></span> | <span data-ttu-id="c1e58-166">資料類型</span><span class="sxs-lookup"><span data-stu-id="c1e58-166">Data type</span></span> | <span data-ttu-id="c1e58-167">描述</span><span class="sxs-lookup"><span data-stu-id="c1e58-167">Description</span></span> | <span data-ttu-id="c1e58-168">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="c1e58-169">CveId</span><span class="sxs-lookup"><span data-stu-id="c1e58-169">CveId</span></span> | <span data-ttu-id="c1e58-170">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-170">string</span></span> | <span data-ttu-id="c1e58-171">指派給常見漏洞及披露 (CVE) system 的安全性弱點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="c1e58-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="c1e58-172">CVE-2020-15992</span></span>
<span data-ttu-id="c1e58-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="c1e58-173">CvssScore</span></span> | <span data-ttu-id="c1e58-174">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-174">string</span></span> | <span data-ttu-id="c1e58-175">CVE 的 CVSS 分數。</span><span class="sxs-lookup"><span data-stu-id="c1e58-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="c1e58-176">6.2</span><span class="sxs-lookup"><span data-stu-id="c1e58-176">6.2</span></span>
<span data-ttu-id="c1e58-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="c1e58-177">DeviceId</span></span> | <span data-ttu-id="c1e58-178">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-178">string</span></span> | <span data-ttu-id="c1e58-179">服務中裝置的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="c1e58-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="c1e58-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="c1e58-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="c1e58-181">DeviceName</span></span> | <span data-ttu-id="c1e58-182">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-182">string</span></span> | <span data-ttu-id="c1e58-183">裝置 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="c1e58-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="c1e58-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c1e58-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="c1e58-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="c1e58-185">DiskPaths</span></span>  | <span data-ttu-id="c1e58-186">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="c1e58-186">Array\[string\]</span></span> | <span data-ttu-id="c1e58-187">在裝置上安裝產品的磁片證據。</span><span class="sxs-lookup"><span data-stu-id="c1e58-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="c1e58-188">["C:\Program (x86) \Microsoft\Silverlight\Application\silverlight.exe 的檔案]]</span><span class="sxs-lookup"><span data-stu-id="c1e58-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="c1e58-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="c1e58-189">ExploitabilityLevel</span></span> | <span data-ttu-id="c1e58-190">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-190">string</span></span> | <span data-ttu-id="c1e58-191">此弱點的 exploitability 層級 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) </span><span class="sxs-lookup"><span data-stu-id="c1e58-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="c1e58-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="c1e58-192">ExploitIsInKit</span></span>
<span data-ttu-id="c1e58-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c1e58-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="c1e58-194">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-194">string</span></span> | <span data-ttu-id="c1e58-195">第一次在裝置上看到此項產品的 CVE。</span><span class="sxs-lookup"><span data-stu-id="c1e58-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="c1e58-196">2020-11-03 10：13：34.8476880</span><span class="sxs-lookup"><span data-stu-id="c1e58-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="c1e58-197">識別碼</span><span class="sxs-lookup"><span data-stu-id="c1e58-197">Id</span></span> | <span data-ttu-id="c1e58-198">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-198">string</span></span> | <span data-ttu-id="c1e58-199">記錄的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-199">Unique identifier for the record.</span></span> | <span data-ttu-id="c1e58-200">123ABG55_573AG&mnp！</span><span class="sxs-lookup"><span data-stu-id="c1e58-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="c1e58-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c1e58-201">LastSeenTimestamp</span></span> | <span data-ttu-id="c1e58-202">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-202">string</span></span> | <span data-ttu-id="c1e58-203">最後一次在裝置上看到 CVE。</span><span class="sxs-lookup"><span data-stu-id="c1e58-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="c1e58-204">2020-11-03 10：13：34.8476880</span><span class="sxs-lookup"><span data-stu-id="c1e58-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="c1e58-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="c1e58-205">OSPlatform</span></span> | <span data-ttu-id="c1e58-206">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-206">string</span></span> | <span data-ttu-id="c1e58-207">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="c1e58-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="c1e58-208">此屬性會指出特定的作業系統，包括相同家族內的變化，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="c1e58-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="c1e58-209">如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。</span><span class="sxs-lookup"><span data-stu-id="c1e58-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="c1e58-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="c1e58-210">Windows10</span></span>
<span data-ttu-id="c1e58-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c1e58-211">RbacGroupName</span></span>  | <span data-ttu-id="c1e58-212">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-212">string</span></span> | <span data-ttu-id="c1e58-213">以角色為基礎的存取控制 (RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="c1e58-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="c1e58-214">如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。</span><span class="sxs-lookup"><span data-stu-id="c1e58-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="c1e58-215">如果組織不包含任何 RBAC 群組，則此值會是 "None"。</span><span class="sxs-lookup"><span data-stu-id="c1e58-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="c1e58-216">伺服器</span><span class="sxs-lookup"><span data-stu-id="c1e58-216">Servers</span></span>
<span data-ttu-id="c1e58-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="c1e58-217">RecommendationReference</span></span> | <span data-ttu-id="c1e58-218">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-218">string</span></span> | <span data-ttu-id="c1e58-219">與此軟體相關的建議識別碼參照。</span><span class="sxs-lookup"><span data-stu-id="c1e58-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="c1e58-220">va-_-_ silverlight</span><span class="sxs-lookup"><span data-stu-id="c1e58-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="c1e58-221">RecommendedSecurityUpdate (選用) </span><span class="sxs-lookup"><span data-stu-id="c1e58-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="c1e58-222">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-222">string</span></span> | <span data-ttu-id="c1e58-223">軟體廠商提供的安全性更新名稱或描述，以解決此弱點。</span><span class="sxs-lookup"><span data-stu-id="c1e58-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="c1e58-224">2020年4月安全性更新</span><span class="sxs-lookup"><span data-stu-id="c1e58-224">April 2020 Security Updates</span></span>
<span data-ttu-id="c1e58-225">RecommendedSecurityUpdateId (選用) </span><span class="sxs-lookup"><span data-stu-id="c1e58-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="c1e58-226">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-226">string</span></span> | <span data-ttu-id="c1e58-227">對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼</span><span class="sxs-lookup"><span data-stu-id="c1e58-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="c1e58-228">4550961</span><span class="sxs-lookup"><span data-stu-id="c1e58-228">4550961</span></span>
<span data-ttu-id="c1e58-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="c1e58-229">RegistryPaths</span></span>  | <span data-ttu-id="c1e58-230">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="c1e58-230">Array\[string\]</span></span> | <span data-ttu-id="c1e58-231">產品已安裝在裝置中的登錄證據。</span><span class="sxs-lookup"><span data-stu-id="c1e58-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="c1e58-232">["HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight"]</span><span class="sxs-lookup"><span data-stu-id="c1e58-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="c1e58-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="c1e58-233">SoftwareName</span></span> | <span data-ttu-id="c1e58-234">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-234">string</span></span> | <span data-ttu-id="c1e58-235">軟體產品的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1e58-235">Name of the software product.</span></span> | <span data-ttu-id="c1e58-236">鉻</span><span class="sxs-lookup"><span data-stu-id="c1e58-236">chrome</span></span>
<span data-ttu-id="c1e58-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="c1e58-237">SoftwareVendor</span></span> | <span data-ttu-id="c1e58-238">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-238">string</span></span> | <span data-ttu-id="c1e58-239">軟體廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1e58-239">Name of the software vendor.</span></span> | <span data-ttu-id="c1e58-240">谷歌</span><span class="sxs-lookup"><span data-stu-id="c1e58-240">google</span></span>
<span data-ttu-id="c1e58-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="c1e58-241">SoftwareVersion</span></span> | <span data-ttu-id="c1e58-242">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-242">string</span></span> | <span data-ttu-id="c1e58-243">軟體產品的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-243">Version number of the software product.</span></span> | <span data-ttu-id="c1e58-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="c1e58-244">81.0.4044.138</span></span>
<span data-ttu-id="c1e58-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="c1e58-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="c1e58-246">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-246">string</span></span> | <span data-ttu-id="c1e58-247">依威脅環境影響的 CVSS 分數和動態因素所指派給安全性弱點的嚴重性等級。</span><span class="sxs-lookup"><span data-stu-id="c1e58-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="c1e58-248">中</span><span class="sxs-lookup"><span data-stu-id="c1e58-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="c1e58-249">1.6 範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="c1e58-250">1.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="c1e58-251">1.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-251">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="c1e58-252">2. 透過檔案匯出軟體漏洞評估 () </span><span class="sxs-lookup"><span data-stu-id="c1e58-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="c1e58-253">2.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="c1e58-253">2.1 API method description</span></span>

<span data-ttu-id="c1e58-254">此 API 回應包含每個裝置已安裝軟體的所有資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="c1e58-255">會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="c1e58-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="c1e58-256">2.1.2 限制</span><span class="sxs-lookup"><span data-stu-id="c1e58-256">2.1.2 Limitations</span></span>

<span data-ttu-id="c1e58-257">此 API 的速率限制是每分鐘5個通話，每小時20個通話。</span><span class="sxs-lookup"><span data-stu-id="c1e58-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="c1e58-258">2.2 許可權</span><span class="sxs-lookup"><span data-stu-id="c1e58-258">2.2 Permissions</span></span>

<span data-ttu-id="c1e58-259">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="c1e58-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c1e58-260">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e58-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="c1e58-261">許可權類型</span><span class="sxs-lookup"><span data-stu-id="c1e58-261">Permission type</span></span> | <span data-ttu-id="c1e58-262">權限</span><span class="sxs-lookup"><span data-stu-id="c1e58-262">Permission</span></span> | <span data-ttu-id="c1e58-263">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c1e58-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="c1e58-264">應用程式</span><span class="sxs-lookup"><span data-stu-id="c1e58-264">Application</span></span> | <span data-ttu-id="c1e58-265">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="c1e58-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="c1e58-266">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="c1e58-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="c1e58-267">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="c1e58-267">Delegated (work or school account)</span></span> | <span data-ttu-id="c1e58-268">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="c1e58-268">Vulnerability.Read</span></span> | <span data-ttu-id="c1e58-269">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="c1e58-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="c1e58-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="c1e58-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="c1e58-271">2.4 參數</span><span class="sxs-lookup"><span data-stu-id="c1e58-271">2.4 Parameters</span></span>

- <span data-ttu-id="c1e58-272">sasValidHours –下載 URLs (最長24小時內的有效時數) </span><span class="sxs-lookup"><span data-stu-id="c1e58-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="c1e58-273">2.5 屬性</span><span class="sxs-lookup"><span data-stu-id="c1e58-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="c1e58-274">這些檔案是以多行 Json 格式的 gzip 壓縮 &。</span><span class="sxs-lookup"><span data-stu-id="c1e58-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="c1e58-275">下載 URLs 只會在3小時內有效;否則您可以使用參數。</span><span class="sxs-lookup"><span data-stu-id="c1e58-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="c1e58-276">為了獲得最大的下載速度，您可以確保從您的資料所在的相同 Azure 地區下載。</span><span class="sxs-lookup"><span data-stu-id="c1e58-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="c1e58-277">每筆記錄大約是1KB 的資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="c1e58-278">為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。</span><span class="sxs-lookup"><span data-stu-id="c1e58-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="c1e58-279">其他一些欄可能會在回應中傳回。</span><span class="sxs-lookup"><span data-stu-id="c1e58-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="c1e58-280">這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。</span><span class="sxs-lookup"><span data-stu-id="c1e58-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="c1e58-281">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="c1e58-281">Property (ID)</span></span> | <span data-ttu-id="c1e58-282">資料類型</span><span class="sxs-lookup"><span data-stu-id="c1e58-282">Data type</span></span> | <span data-ttu-id="c1e58-283">描述</span><span class="sxs-lookup"><span data-stu-id="c1e58-283">Description</span></span> | <span data-ttu-id="c1e58-284">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="c1e58-285">匯出檔案</span><span class="sxs-lookup"><span data-stu-id="c1e58-285">Export files</span></span> | <span data-ttu-id="c1e58-286">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="c1e58-286">array\[string\]</span></span>  | <span data-ttu-id="c1e58-287">用於存放組織目前快照之檔案的下載 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="c1e58-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="c1e58-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="c1e58-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="c1e58-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="c1e58-289">GeneratedTime</span></span> | <span data-ttu-id="c1e58-290">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-290">string</span></span> | <span data-ttu-id="c1e58-291">產生匯出的時間。</span><span class="sxs-lookup"><span data-stu-id="c1e58-291">The time that the export was generated.</span></span> | <span data-ttu-id="c1e58-292">2021-05-20T08：00：00Z</span><span class="sxs-lookup"><span data-stu-id="c1e58-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="c1e58-293">2.6 範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="c1e58-294">2.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="c1e58-295">2.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-295">2.6.2 Response example</span></span>

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

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="c1e58-296">3. 增量匯出軟體漏洞評估 (JSON 回應) </span><span class="sxs-lookup"><span data-stu-id="c1e58-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="c1e58-297">3.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="c1e58-297">3.1 API method description</span></span>

<span data-ttu-id="c1e58-298">會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="c1e58-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="c1e58-299">API 將組織中的資料提取為 Json 回應。</span><span class="sxs-lookup"><span data-stu-id="c1e58-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="c1e58-300">回應已分頁，所以您可以 @odata 使用來自回應的 nextLink 欄位，以提取下一個結果。</span><span class="sxs-lookup"><span data-stu-id="c1e58-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="c1e58-301">與完整的軟體漏洞評估 (JSON 回應) （用來取得組織的軟體漏洞評估整個快照）不同時，會使用 delta export JSON 回應 API 呼叫，只提取選取日期和目前日期之間所發生的變更， ("delta" API 呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="c1e58-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="c1e58-302">您不需要每次獲得大量資料的完整匯出，只會取得新的、已修復和更新之弱點的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="c1e58-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="c1e58-303">Delta export JSON 回應 API 通話也可以用來計算不同的 KPIs 例如「修復多少個漏洞？」。</span><span class="sxs-lookup"><span data-stu-id="c1e58-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="c1e58-304">或「我的組織新增了多少個新的漏洞？」</span><span class="sxs-lookup"><span data-stu-id="c1e58-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="c1e58-305">強烈建議您在一周內至少使用一次裝置 API 呼叫的完整匯出軟體漏洞評估，而裝置 (delta) API 將此額外的匯出軟體弱點變更為一周的所有其他日子。</span><span class="sxs-lookup"><span data-stu-id="c1e58-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="c1e58-306">與其他評估 JSON 回應 APIs 不同的是，「delta export」不是完整匯出。</span><span class="sxs-lookup"><span data-stu-id="c1e58-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="c1e58-307">Delta export 只會包含選取日期和目前日期之間所發生的變更 (「delta」 API 呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="c1e58-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="c1e58-308">3.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="c1e58-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="c1e58-309">頁面大小上限為200000。</span><span class="sxs-lookup"><span data-stu-id="c1e58-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="c1e58-310">SinceTime 參數的最大值為14天。</span><span class="sxs-lookup"><span data-stu-id="c1e58-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="c1e58-311">此 API 的速率限制為每分鐘30個通話，每小時1000個通話。</span><span class="sxs-lookup"><span data-stu-id="c1e58-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="c1e58-312">3.2 許可權</span><span class="sxs-lookup"><span data-stu-id="c1e58-312">3.2 Permissions</span></span>

<span data-ttu-id="c1e58-313">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="c1e58-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c1e58-314">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c1e58-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="c1e58-315">許可權類型</span><span class="sxs-lookup"><span data-stu-id="c1e58-315">Permission type</span></span> | <span data-ttu-id="c1e58-316">權限</span><span class="sxs-lookup"><span data-stu-id="c1e58-316">Permission</span></span> | <span data-ttu-id="c1e58-317">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c1e58-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="c1e58-318">應用程式</span><span class="sxs-lookup"><span data-stu-id="c1e58-318">Application</span></span> | <span data-ttu-id="c1e58-319">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="c1e58-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="c1e58-320">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="c1e58-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="c1e58-321">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="c1e58-321">Delegated (work or school account)</span></span> | <span data-ttu-id="c1e58-322">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="c1e58-322">Vulnerability.Read</span></span> | <span data-ttu-id="c1e58-323">「讀取威脅及弱點管理弱點資訊」</span><span class="sxs-lookup"><span data-stu-id="c1e58-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="c1e58-324">3.3 URL</span><span class="sxs-lookup"><span data-stu-id="c1e58-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="c1e58-325">3.4 參數</span><span class="sxs-lookup"><span data-stu-id="c1e58-325">3.4 Parameters</span></span>

- <span data-ttu-id="c1e58-326">sinceTime (必要) –所選時間與今天之間的資料。</span><span class="sxs-lookup"><span data-stu-id="c1e58-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="c1e58-327">pageSize (預設值 = 50000) –回應的結果數目</span><span class="sxs-lookup"><span data-stu-id="c1e58-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="c1e58-328">$top –傳回的結果數 (不會傳回 @odata nextLink，因此不會拉入所有資料) </span><span class="sxs-lookup"><span data-stu-id="c1e58-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="c1e58-329">3.5 屬性</span><span class="sxs-lookup"><span data-stu-id="c1e58-329">3.5 Properties</span></span>

<span data-ttu-id="c1e58-330">每個傳回的記錄包含由裝置 OData API 的完整出口軟體漏洞評估中的所有資料，另外還有兩個額外的欄位：  _**EventTimestamp**_ 和 _**Status**_。</span><span class="sxs-lookup"><span data-stu-id="c1e58-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="c1e58-331">其他一些欄可能會在回應中傳回。</span><span class="sxs-lookup"><span data-stu-id="c1e58-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="c1e58-332">這些欄是暫存檔的，而且可能會被移除，所以請只使用記錄的資料行。</span><span class="sxs-lookup"><span data-stu-id="c1e58-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="c1e58-333">下表中所定義的屬性依字母順序依屬性識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="c1e58-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="c1e58-334">執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。</span><span class="sxs-lookup"><span data-stu-id="c1e58-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="c1e58-335">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="c1e58-335">Property (ID)</span></span> | <span data-ttu-id="c1e58-336">資料類型</span><span class="sxs-lookup"><span data-stu-id="c1e58-336">Data type</span></span> | <span data-ttu-id="c1e58-337">描述</span><span class="sxs-lookup"><span data-stu-id="c1e58-337">Description</span></span> | <span data-ttu-id="c1e58-338">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="c1e58-339">CveId</span><span class="sxs-lookup"><span data-stu-id="c1e58-339">CveId</span></span> | <span data-ttu-id="c1e58-340">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-340">string</span></span> | <span data-ttu-id="c1e58-341">指派給常見漏洞及披露 (CVE) system 的安全性弱點的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="c1e58-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="c1e58-342">CVE-2020-15992</span></span>  
<span data-ttu-id="c1e58-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="c1e58-343">CvssScore</span></span> | <span data-ttu-id="c1e58-344">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-344">string</span></span> | <span data-ttu-id="c1e58-345">CVE 的 CVSS 分數。</span><span class="sxs-lookup"><span data-stu-id="c1e58-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="c1e58-346">6.2</span><span class="sxs-lookup"><span data-stu-id="c1e58-346">6.2</span></span>  
<span data-ttu-id="c1e58-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="c1e58-347">DeviceId</span></span> | <span data-ttu-id="c1e58-348">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-348">string</span></span> | <span data-ttu-id="c1e58-349">服務中裝置的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="c1e58-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="c1e58-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="c1e58-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="c1e58-351">DeviceName</span></span> | <span data-ttu-id="c1e58-352">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-352">string</span></span> | <span data-ttu-id="c1e58-353">裝置 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="c1e58-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="c1e58-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c1e58-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="c1e58-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="c1e58-355">DiskPaths</span></span> | <span data-ttu-id="c1e58-356">陣列 [字串]</span><span class="sxs-lookup"><span data-stu-id="c1e58-356">Array[string]</span></span> | <span data-ttu-id="c1e58-357">在裝置上安裝產品的磁片證據。</span><span class="sxs-lookup"><span data-stu-id="c1e58-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="c1e58-358">["C:\Program (x86) \Microsoft\Silverlight\Application\silverlight.exe 的檔案]]</span><span class="sxs-lookup"><span data-stu-id="c1e58-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="c1e58-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="c1e58-359">EventTimestamp</span></span> | <span data-ttu-id="c1e58-360">字串</span><span class="sxs-lookup"><span data-stu-id="c1e58-360">String</span></span> | <span data-ttu-id="c1e58-361">找到此 delta 事件的時間。</span><span class="sxs-lookup"><span data-stu-id="c1e58-361">The time this delta event was found.</span></span> | <span data-ttu-id="c1e58-362">2021-01-11T11：06： 08.291 Z</span><span class="sxs-lookup"><span data-stu-id="c1e58-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="c1e58-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="c1e58-363">ExploitabilityLevel</span></span> | <span data-ttu-id="c1e58-364">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-364">string</span></span> | <span data-ttu-id="c1e58-365">此弱點的 exploitability 層級 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) </span><span class="sxs-lookup"><span data-stu-id="c1e58-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="c1e58-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="c1e58-366">ExploitIsInKit</span></span>  
<span data-ttu-id="c1e58-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c1e58-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="c1e58-368">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-368">string</span></span> | <span data-ttu-id="c1e58-369">第一次在裝置上看到此項產品的 CVE。</span><span class="sxs-lookup"><span data-stu-id="c1e58-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="c1e58-370">2020-11-03 10：13：34.8476880</span><span class="sxs-lookup"><span data-stu-id="c1e58-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="c1e58-371">識別碼</span><span class="sxs-lookup"><span data-stu-id="c1e58-371">Id</span></span> | <span data-ttu-id="c1e58-372">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-372">string</span></span> | <span data-ttu-id="c1e58-373">記錄的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-373">Unique identifier for the record.</span></span> | <span data-ttu-id="c1e58-374">123ABG55_573AG&mnp！</span><span class="sxs-lookup"><span data-stu-id="c1e58-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="c1e58-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="c1e58-375">LastSeenTimestamp</span></span> | <span data-ttu-id="c1e58-376">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-376">string</span></span> | <span data-ttu-id="c1e58-377">最後一次在裝置上看到 CVE。</span><span class="sxs-lookup"><span data-stu-id="c1e58-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="c1e58-378">2020-11-03 10：13：34.8476880</span><span class="sxs-lookup"><span data-stu-id="c1e58-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="c1e58-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="c1e58-379">OSPlatform</span></span> | <span data-ttu-id="c1e58-380">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-380">string</span></span> | <span data-ttu-id="c1e58-381">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="c1e58-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="c1e58-382">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="c1e58-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="c1e58-383">如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。</span><span class="sxs-lookup"><span data-stu-id="c1e58-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="c1e58-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="c1e58-384">Windows10</span></span>  
<span data-ttu-id="c1e58-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c1e58-385">RbacGroupName</span></span> | <span data-ttu-id="c1e58-386">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-386">string</span></span> | <span data-ttu-id="c1e58-387">以角色為基礎的存取控制 (RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="c1e58-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="c1e58-388">如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。</span><span class="sxs-lookup"><span data-stu-id="c1e58-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="c1e58-389">如果組織不包含任何 RBAC 群組，則此值會是 "None"。</span><span class="sxs-lookup"><span data-stu-id="c1e58-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="c1e58-390">伺服器</span><span class="sxs-lookup"><span data-stu-id="c1e58-390">Servers</span></span>  
<span data-ttu-id="c1e58-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="c1e58-391">RecommendationReference</span></span> | <span data-ttu-id="c1e58-392">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-392">string</span></span> | <span data-ttu-id="c1e58-393">與此軟體相關的建議識別碼參照。</span><span class="sxs-lookup"><span data-stu-id="c1e58-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="c1e58-394">va--silverlight</span><span class="sxs-lookup"><span data-stu-id="c1e58-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="c1e58-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="c1e58-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="c1e58-396">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-396">string</span></span> | <span data-ttu-id="c1e58-397">軟體廠商提供的安全性更新名稱或描述，以解決此弱點。</span><span class="sxs-lookup"><span data-stu-id="c1e58-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="c1e58-398">2020年4月安全性更新</span><span class="sxs-lookup"><span data-stu-id="c1e58-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="c1e58-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="c1e58-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="c1e58-400">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-400">string</span></span> | <span data-ttu-id="c1e58-401">對應的指導或知識庫 (KB) 文章的適用安全性更新或識別碼識別碼</span><span class="sxs-lookup"><span data-stu-id="c1e58-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="c1e58-402">4550961</span><span class="sxs-lookup"><span data-stu-id="c1e58-402">4550961</span></span>  
<span data-ttu-id="c1e58-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="c1e58-403">RegistryPaths</span></span>  | <span data-ttu-id="c1e58-404">陣列 [字串]</span><span class="sxs-lookup"><span data-stu-id="c1e58-404">Array[string]</span></span> | <span data-ttu-id="c1e58-405">產品已安裝在裝置中的登錄證據。</span><span class="sxs-lookup"><span data-stu-id="c1e58-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="c1e58-406">["HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome"]</span><span class="sxs-lookup"><span data-stu-id="c1e58-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="c1e58-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="c1e58-407">SoftwareName</span></span> | <span data-ttu-id="c1e58-408">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-408">string</span></span> | <span data-ttu-id="c1e58-409">軟體產品的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1e58-409">Name of the software product.</span></span> | <span data-ttu-id="c1e58-410">鉻</span><span class="sxs-lookup"><span data-stu-id="c1e58-410">chrome</span></span>  
<span data-ttu-id="c1e58-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="c1e58-411">SoftwareVendor</span></span> | <span data-ttu-id="c1e58-412">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-412">string</span></span> | <span data-ttu-id="c1e58-413">軟體廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="c1e58-413">Name of the software vendor.</span></span> | <span data-ttu-id="c1e58-414">谷歌</span><span class="sxs-lookup"><span data-stu-id="c1e58-414">google</span></span>  
<span data-ttu-id="c1e58-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="c1e58-415">SoftwareVersion</span></span> | <span data-ttu-id="c1e58-416">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-416">string</span></span> | <span data-ttu-id="c1e58-417">軟體產品的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="c1e58-417">Version number of the software product.</span></span> | <span data-ttu-id="c1e58-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="c1e58-418">81.0.4044.138</span></span>  
<span data-ttu-id="c1e58-419">狀態</span><span class="sxs-lookup"><span data-stu-id="c1e58-419">Status</span></span> | <span data-ttu-id="c1e58-420">字串</span><span class="sxs-lookup"><span data-stu-id="c1e58-420">String</span></span> | <span data-ttu-id="c1e58-421">**新**  針對裝置上引進的新弱點 ()  (1) **固定**   (如果此弱點不再存在於裝置上，表示它已修正) 。</span><span class="sxs-lookup"><span data-stu-id="c1e58-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="c1e58-422"> (2)  **更新**，   (如果裝置上的某個弱點已變更。</span><span class="sxs-lookup"><span data-stu-id="c1e58-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="c1e58-423">可能的變更如下： CVSS 評分、exploitability 層級、嚴重性層級、DiskPaths、RegistryPaths、RecommendedSecurityUpdate) 。</span><span class="sxs-lookup"><span data-stu-id="c1e58-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="c1e58-424">Fixed</span><span class="sxs-lookup"><span data-stu-id="c1e58-424">Fixed</span></span>
<span data-ttu-id="c1e58-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="c1e58-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="c1e58-426">string</span><span class="sxs-lookup"><span data-stu-id="c1e58-426">string</span></span> | <span data-ttu-id="c1e58-427">依威脅環境影響的 CVSS 分數和動態因素所指派給安全性弱點的嚴重性等級。</span><span class="sxs-lookup"><span data-stu-id="c1e58-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="c1e58-428">中</span><span class="sxs-lookup"><span data-stu-id="c1e58-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="c1e58-429">澄清</span><span class="sxs-lookup"><span data-stu-id="c1e58-429">Clarifications</span></span>

- <span data-ttu-id="c1e58-430">若軟體從版本1.0 更新為版本2.0，而且這兩個版本都會公開至 CVE-A，您會收到2個不同的事件：</span><span class="sxs-lookup"><span data-stu-id="c1e58-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="c1e58-431">固定– CVE-已修正版本1。0</span><span class="sxs-lookup"><span data-stu-id="c1e58-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="c1e58-432">新增– CVE-已新增版本2。0</span><span class="sxs-lookup"><span data-stu-id="c1e58-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="c1e58-433">例如，如果特定弱點 (例如，在特定時間內第一 (次看到) （例如，1.0 年1月10日) ），而軟體更新至版本2.0 （也是對相同的 CVE-A 所公開），您將會收到這兩個分隔的事件：</span><span class="sxs-lookup"><span data-stu-id="c1e58-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="c1e58-434">Fixed – CVE-X，FirstSeenTimestamp 年1月10日，第1版，0。</span><span class="sxs-lookup"><span data-stu-id="c1e58-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="c1e58-435">新增– CVE-X，FirstSeenTimestamp 年1月10日，版本2.0。</span><span class="sxs-lookup"><span data-stu-id="c1e58-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="c1e58-436">3.6 範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="c1e58-437">3.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="c1e58-438">3.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="c1e58-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="c1e58-439">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c1e58-439">See also</span></span>

- [<span data-ttu-id="c1e58-440">匯出每台裝置的評估方法和屬性</span><span class="sxs-lookup"><span data-stu-id="c1e58-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="c1e58-441">匯出每個裝置的安全設定評估</span><span class="sxs-lookup"><span data-stu-id="c1e58-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="c1e58-442">每個裝置匯出軟體清查評估</span><span class="sxs-lookup"><span data-stu-id="c1e58-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="c1e58-443">其他相關</span><span class="sxs-lookup"><span data-stu-id="c1e58-443">Other related</span></span>

- [<span data-ttu-id="c1e58-444">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="c1e58-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="c1e58-445">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="c1e58-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
