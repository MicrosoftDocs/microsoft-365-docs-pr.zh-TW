---
title: 每個裝置匯出軟體清查評估
description: 會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。
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
ms.openlocfilehash: 3a65fb6d5d3e5c6e68e100aa3ea2b4cf896dc281
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789345"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="e2c0d-104">每個裝置匯出軟體清查評估</span><span class="sxs-lookup"><span data-stu-id="e2c0d-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2c0d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e2c0d-105">**Applies to:**</span></span>

- [<span data-ttu-id="e2c0d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e2c0d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e2c0d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2c0d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e2c0d-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="e2c0d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e2c0d-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="e2c0d-110">有不同的 API 呼叫可取得不同的資料類型。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="e2c0d-111">因為資料量可能很大，所以可供檢索的方式有兩種：</span><span class="sxs-lookup"><span data-stu-id="e2c0d-111">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="e2c0d-112">[匯出軟體清查評估 **OData**](#1-export-software-inventory-assessment-odata) API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-112">[Export software inventory assessment **OData**](#1-export-software-inventory-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="e2c0d-113">這種方法最適合 _小型組織，且少於 100 K 裝置_。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-113">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="e2c0d-114">回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="e2c0d-115">透過[檔案匯出軟體清查評估](#2-export-software-inventory-assessment-via-files) 此 API 解決方案可讓大量的資料更快速且可靠地進行。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="e2c0d-116">因此，建議大型組織使用超過 100 K 的裝置。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-116">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="e2c0d-117">此 API 會將組織中的所有資料都提取為下載檔案。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="e2c0d-118">回應包含從 Azure 儲存體下載所有資料的 URLs。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="e2c0d-119">此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e2c0d-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="e2c0d-120">呼叫 API 以取得所有組織資料的下載 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="e2c0d-121">使用下載 URLs 下載所有檔案，並視需要處理資料。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="e2c0d-122">使用 _OData_ _或透過_ 檔案收集 (所收集的資料，) 目前狀態的目前快照，且不包含歷史資料。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="e2c0d-123">為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="e2c0d-124">除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="e2c0d-125">1. 匯出軟體清查評估 (OData) </span><span class="sxs-lookup"><span data-stu-id="e2c0d-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="e2c0d-126">1.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="e2c0d-126">1.1 API method description</span></span>

<span data-ttu-id="e2c0d-127">此 API 回應包含每個裝置已安裝軟體的所有資料。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="e2c0d-128">會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="e2c0d-129">限制</span><span class="sxs-lookup"><span data-stu-id="e2c0d-129">Limitations</span></span>

- <span data-ttu-id="e2c0d-130">頁面大小上限為200000。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="e2c0d-131">此 API 的速率限制為每分鐘30個通話，每小時1000個通話。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="e2c0d-132">1.2 許可權</span><span class="sxs-lookup"><span data-stu-id="e2c0d-132">1.2 Permissions</span></span>

<span data-ttu-id="e2c0d-133">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e2c0d-134">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e2c0d-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="e2c0d-135">許可權類型</span><span class="sxs-lookup"><span data-stu-id="e2c0d-135">Permission type</span></span> | <span data-ttu-id="e2c0d-136">權限</span><span class="sxs-lookup"><span data-stu-id="e2c0d-136">Permission</span></span> | <span data-ttu-id="e2c0d-137">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="e2c0d-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="e2c0d-138">應用程式</span><span class="sxs-lookup"><span data-stu-id="e2c0d-138">Application</span></span> | <span data-ttu-id="e2c0d-139">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="e2c0d-139">Software.Read.All</span></span> | <span data-ttu-id="e2c0d-140">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="e2c0d-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="e2c0d-141">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="e2c0d-141">Delegated (work or school account)</span></span> | <span data-ttu-id="e2c0d-142">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="e2c0d-142">Software.Read</span></span> | <span data-ttu-id="e2c0d-143">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="e2c0d-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="e2c0d-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="e2c0d-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="e2c0d-145">1.4 參數</span><span class="sxs-lookup"><span data-stu-id="e2c0d-145">1.4 Parameters</span></span>

- <span data-ttu-id="e2c0d-146">pageSize (預設值 = 50000) –回應的結果數目。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="e2c0d-147">$top –傳回的結果數 (不會傳回 @odata nextLink，因此不會拉入所有資料) </span><span class="sxs-lookup"><span data-stu-id="e2c0d-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="e2c0d-148">1.5 屬性</span><span class="sxs-lookup"><span data-stu-id="e2c0d-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="e2c0d-149">-每筆記錄大約 0.5 KB 的資料。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="e2c0d-150">為您選擇正確的 pageSize 參數時，您應該考慮使用此帳戶。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="e2c0d-151">-在下表中定義的屬性依屬性識別碼列出字母順序。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-151">-The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="e2c0d-152">執行此 API 時，所產生的輸出不一定會依照此表中所列的順序傳回。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
><span data-ttu-id="e2c0d-153">-回應中可能傳回其他一些欄。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="e2c0d-154">這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="e2c0d-155">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="e2c0d-155">Property (ID)</span></span> | <span data-ttu-id="e2c0d-156">資料類型</span><span class="sxs-lookup"><span data-stu-id="e2c0d-156">Data type</span></span> | <span data-ttu-id="e2c0d-157">描述</span><span class="sxs-lookup"><span data-stu-id="e2c0d-157">Description</span></span> | <span data-ttu-id="e2c0d-158">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="e2c0d-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="e2c0d-159">DeviceId</span></span> | <span data-ttu-id="e2c0d-160">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-160">string</span></span> | <span data-ttu-id="e2c0d-161">服務中裝置的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="e2c0d-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="e2c0d-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="e2c0d-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="e2c0d-163">DeviceName</span></span> | <span data-ttu-id="e2c0d-164">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-164">string</span></span> | <span data-ttu-id="e2c0d-165">裝置 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="e2c0d-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e2c0d-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="e2c0d-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="e2c0d-167">DiskPaths</span></span> | <span data-ttu-id="e2c0d-168">陣列 [字串]</span><span class="sxs-lookup"><span data-stu-id="e2c0d-168">Array[string]</span></span>  | <span data-ttu-id="e2c0d-169">在裝置上安裝產品的磁片證據。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="e2c0d-170">[C： \\ (x86) \\ Microsoft \\ Silverlight \\ 應用程式 \\silverlight.exe "] 的程式檔案</span><span class="sxs-lookup"><span data-stu-id="e2c0d-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="e2c0d-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="e2c0d-171">EndOfSupportDate</span></span> | <span data-ttu-id="e2c0d-172">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-172">string</span></span> | <span data-ttu-id="e2c0d-173">此軟體支援或會結束的日期。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="e2c0d-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="e2c0d-174">2020-12-30</span></span>
<span data-ttu-id="e2c0d-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="e2c0d-175">EndOfSupportStatus</span></span> | <span data-ttu-id="e2c0d-176">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-176">string</span></span> | <span data-ttu-id="e2c0d-177">支援狀態的結束。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-177">End of support status.</span></span> <span data-ttu-id="e2c0d-178">可以包含這些可能的值：無、EOS 版本、即將發生的 EOS 版本、EOS 軟體（即將進行的 EOS 軟體）。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="e2c0d-179">即將進行的 EOS</span><span class="sxs-lookup"><span data-stu-id="e2c0d-179">Upcoming EOS</span></span>
<span data-ttu-id="e2c0d-180">識別碼</span><span class="sxs-lookup"><span data-stu-id="e2c0d-180">Id</span></span> | <span data-ttu-id="e2c0d-181">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-181">string</span></span> | <span data-ttu-id="e2c0d-182">記錄的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-182">Unique identifier for the record.</span></span> | <span data-ttu-id="e2c0d-183">123ABG55_573AG&mnp！</span><span class="sxs-lookup"><span data-stu-id="e2c0d-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="e2c0d-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="e2c0d-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="e2c0d-185">int</span><span class="sxs-lookup"><span data-stu-id="e2c0d-185">int</span></span> | <span data-ttu-id="e2c0d-186">此裝置上的此軟體弱點數目</span><span class="sxs-lookup"><span data-stu-id="e2c0d-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="e2c0d-187">個</span><span class="sxs-lookup"><span data-stu-id="e2c0d-187">3</span></span>
<span data-ttu-id="e2c0d-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="e2c0d-188">OSPlatform</span></span> | <span data-ttu-id="e2c0d-189">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-189">string</span></span> | <span data-ttu-id="e2c0d-190">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e2c0d-191">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="e2c0d-192">如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="e2c0d-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="e2c0d-193">Windows10</span></span>
<span data-ttu-id="e2c0d-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="e2c0d-194">RbacGroupName</span></span> | <span data-ttu-id="e2c0d-195">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-195">string</span></span> | <span data-ttu-id="e2c0d-196">以角色為基礎的存取控制 (RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="e2c0d-197">如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="e2c0d-198">如果組織不包含任何 RBAC 群組，則此值會是 "None"。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="e2c0d-199">伺服器</span><span class="sxs-lookup"><span data-stu-id="e2c0d-199">Servers</span></span>
<span data-ttu-id="e2c0d-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="e2c0d-200">RegistryPaths</span></span> | <span data-ttu-id="e2c0d-201">陣列 [字串]</span><span class="sxs-lookup"><span data-stu-id="e2c0d-201">Array[string]</span></span> | <span data-ttu-id="e2c0d-202">產品已安裝在裝置中的登錄證據。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="e2c0d-203">["HKEY_LOCAL_MACHINE \\軟體 \\ WOW6432Node \\ microsoft \\ Windows \\ CurrentVersion \\ 卸載 \\ microsoft Silverlight "]</span><span class="sxs-lookup"><span data-stu-id="e2c0d-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="e2c0d-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="e2c0d-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="e2c0d-205">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-205">string</span></span> | <span data-ttu-id="e2c0d-206">此軟體第一次出現于此裝置上。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="e2c0d-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="e2c0d-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="e2c0d-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="e2c0d-208">SoftwareName</span></span> | <span data-ttu-id="e2c0d-209">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-209">string</span></span> | <span data-ttu-id="e2c0d-210">軟體產品的名稱。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-210">Name of the software product.</span></span> | <span data-ttu-id="e2c0d-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="e2c0d-211">Silverlight</span></span>
<span data-ttu-id="e2c0d-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="e2c0d-212">SoftwareVendor</span></span> | <span data-ttu-id="e2c0d-213">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-213">string</span></span> | <span data-ttu-id="e2c0d-214">軟體廠商的名稱。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-214">Name of the software vendor.</span></span> | <span data-ttu-id="e2c0d-215">微軟</span><span class="sxs-lookup"><span data-stu-id="e2c0d-215">microsoft</span></span>
<span data-ttu-id="e2c0d-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="e2c0d-216">SoftwareVersion</span></span> | <span data-ttu-id="e2c0d-217">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-217">string</span></span> | <span data-ttu-id="e2c0d-218">軟體產品的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-218">Version number of the software product.</span></span> | <span data-ttu-id="e2c0d-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="e2c0d-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="e2c0d-220">1.6 範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="e2c0d-221">1.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="e2c0d-222">1.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="e2c0d-223">2. 透過檔案匯出軟體清查評估 () </span><span class="sxs-lookup"><span data-stu-id="e2c0d-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="e2c0d-224">2.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="e2c0d-224">2.1 API method description</span></span>

<span data-ttu-id="e2c0d-225">此 API 回應包含每個裝置已安裝軟體的所有資料。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="e2c0d-226">會傳回資料表，其中包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="e2c0d-227">2.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="e2c0d-227">2.1.1 Limitations</span></span>

<span data-ttu-id="e2c0d-228">此 API 的速率限制是每分鐘5個通話，每小時20個通話。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="e2c0d-229">2.2 許可權</span><span class="sxs-lookup"><span data-stu-id="e2c0d-229">2.2 Permissions</span></span>

<span data-ttu-id="e2c0d-230">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e2c0d-231">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e2c0d-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="e2c0d-232">許可權類型</span><span class="sxs-lookup"><span data-stu-id="e2c0d-232">Permission type</span></span> | <span data-ttu-id="e2c0d-233">權限</span><span class="sxs-lookup"><span data-stu-id="e2c0d-233">Permission</span></span> | <span data-ttu-id="e2c0d-234">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="e2c0d-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="e2c0d-235">應用程式</span><span class="sxs-lookup"><span data-stu-id="e2c0d-235">Application</span></span> | <span data-ttu-id="e2c0d-236">已讀取軟體。所有</span><span class="sxs-lookup"><span data-stu-id="e2c0d-236">Software.Read.All</span></span> | <span data-ttu-id="e2c0d-237">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="e2c0d-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="e2c0d-238">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="e2c0d-238">Delegated (work or school account)</span></span> | <span data-ttu-id="e2c0d-239">軟體. 讀取</span><span class="sxs-lookup"><span data-stu-id="e2c0d-239">Software.Read</span></span> | <span data-ttu-id="e2c0d-240">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="e2c0d-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="e2c0d-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="e2c0d-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="e2c0d-242">參數</span><span class="sxs-lookup"><span data-stu-id="e2c0d-242">Parameters</span></span>

- <span data-ttu-id="e2c0d-243">sasValidHours –下載 URLs (最長24小時內的有效時數) </span><span class="sxs-lookup"><span data-stu-id="e2c0d-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="e2c0d-244">2.5 屬性</span><span class="sxs-lookup"><span data-stu-id="e2c0d-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="e2c0d-245">這些檔案是以多行 Json 格式的 gzip 壓縮 &。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="e2c0d-246">下載 URLs 只會在3小時內有效。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="e2c0d-247">否則您可以使用參數。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="e2c0d-248">_ 若要下載最大的資料下載速度，您可以確定從資料所在的相同 Azure 地區下載。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="e2c0d-249">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="e2c0d-249">Property (ID)</span></span> | <span data-ttu-id="e2c0d-250">資料類型</span><span class="sxs-lookup"><span data-stu-id="e2c0d-250">Data type</span></span> | <span data-ttu-id="e2c0d-251">描述</span><span class="sxs-lookup"><span data-stu-id="e2c0d-251">Description</span></span> | <span data-ttu-id="e2c0d-252">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="e2c0d-253">匯出檔案</span><span class="sxs-lookup"><span data-stu-id="e2c0d-253">Export files</span></span> | <span data-ttu-id="e2c0d-254">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="e2c0d-254">array\[string\]</span></span> | <span data-ttu-id="e2c0d-255">用於存放組織目前快照之檔案的下載 URLs 清單</span><span class="sxs-lookup"><span data-stu-id="e2c0d-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="e2c0d-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="e2c0d-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="e2c0d-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="e2c0d-257">GeneratedTime</span></span> | <span data-ttu-id="e2c0d-258">string</span><span class="sxs-lookup"><span data-stu-id="e2c0d-258">string</span></span> | <span data-ttu-id="e2c0d-259">產生匯出的時間。</span><span class="sxs-lookup"><span data-stu-id="e2c0d-259">The time that the export was generated.</span></span> | <span data-ttu-id="e2c0d-260">2021-05-20T08：00： 00Z]</span><span class="sxs-lookup"><span data-stu-id="e2c0d-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="e2c0d-261">2.6 範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="e2c0d-262">2.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="e2c0d-263">2.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="e2c0d-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="e2c0d-264">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e2c0d-264">See also</span></span>

- [<span data-ttu-id="e2c0d-265">匯出每台裝置的評估方法和屬性</span><span class="sxs-lookup"><span data-stu-id="e2c0d-265">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="e2c0d-266">匯出每個裝置的安全設定評估</span><span class="sxs-lookup"><span data-stu-id="e2c0d-266">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="e2c0d-267">每個裝置的匯出軟體漏洞評估</span><span class="sxs-lookup"><span data-stu-id="e2c0d-267">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="e2c0d-268">其他相關</span><span class="sxs-lookup"><span data-stu-id="e2c0d-268">Other related</span></span>

- [<span data-ttu-id="e2c0d-269">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="e2c0d-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="e2c0d-270">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="e2c0d-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
