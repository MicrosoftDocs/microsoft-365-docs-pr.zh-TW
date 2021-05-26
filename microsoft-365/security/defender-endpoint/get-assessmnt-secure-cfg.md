---
title: 匯出每個裝置的安全設定評估
description: 傳回 DeviceId，ConfigurationId 的每個唯一組合的專案。
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
ms.openlocfilehash: f2e20415cb64903e8dfe2c82646c1970036b8f6b
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653628"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="a7a46-104">匯出每個裝置的安全設定評估</span><span class="sxs-lookup"><span data-stu-id="a7a46-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a7a46-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a7a46-105">**Applies to:**</span></span>

- [<span data-ttu-id="a7a46-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a7a46-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a7a46-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7a46-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a7a46-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="a7a46-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7a46-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a7a46-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="a7a46-110">以每個裝置為基礎，傳回所有設定及其狀態。</span><span class="sxs-lookup"><span data-stu-id="a7a46-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="a7a46-111">有不同的 API 呼叫可取得不同的資料類型。</span><span class="sxs-lookup"><span data-stu-id="a7a46-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="a7a46-112">因為資料量可能非常大，所以可供檢索的方式有兩種：</span><span class="sxs-lookup"><span data-stu-id="a7a46-112">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="a7a46-113">**OData**  API 將組織中的所有資料都提取為 Json 回應，遵循 OData 的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="a7a46-113">**OData**  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="a7a46-114">這種方法最適合 _使用小於100k 裝置的小型組織_。</span><span class="sxs-lookup"><span data-stu-id="a7a46-114">This method is best for _small organizations with less than 100K devices_.</span></span> <span data-ttu-id="a7a46-115">回應已分頁，所以您可以使用 \@ nextLink 欄位從回應讀取下一個結果。</span><span class="sxs-lookup"><span data-stu-id="a7a46-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="a7a46-116">透過檔案此 API 解決方案可讓大量的資料更快速且可靠地進行。</span><span class="sxs-lookup"><span data-stu-id="a7a46-116">**via files** This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="a7a46-117">因此，建議大型組織使用超過10個裝置。</span><span class="sxs-lookup"><span data-stu-id="a7a46-117">Therefore, it is recommended for large organizations, with more than 100K devices.</span></span> <span data-ttu-id="a7a46-118">此 API 會將組織中的所有資料都提取為下載檔案。</span><span class="sxs-lookup"><span data-stu-id="a7a46-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="a7a46-119">回應包含從 Azure 儲存體下載所有資料的 URLs。</span><span class="sxs-lookup"><span data-stu-id="a7a46-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="a7a46-120">此 API 可讓您從 Azure 儲存體下載所有資料，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a7a46-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="a7a46-121">呼叫 API 以取得所有組織資料的下載 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="a7a46-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="a7a46-122">使用下載 URLs 下載所有檔案，並視需要處理資料。</span><span class="sxs-lookup"><span data-stu-id="a7a46-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="a7a46-123"> (_OData_ _或透過_ 檔案所收集的資料，) 是目前狀態的目前快照，而且不包含歷史資料。</span><span class="sxs-lookup"><span data-stu-id="a7a46-123">The data that is collected (for either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="a7a46-124">為了收集歷史資料，客戶必須將資料儲存在自己的資料儲存中。</span><span class="sxs-lookup"><span data-stu-id="a7a46-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

<span data-ttu-id="a7a46-125">除非另有說明，否則所列的所有出口評估方法都是 **_完整匯出_** ，而且 **_依裝置_** (也稱為 **_每個裝置_**) 。</span><span class="sxs-lookup"><span data-stu-id="a7a46-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="a7a46-126">1. 匯出 secure configuration 評估 (OData) </span><span class="sxs-lookup"><span data-stu-id="a7a46-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="a7a46-127">1.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="a7a46-127">1.1 API method description</span></span>

<span data-ttu-id="a7a46-128">此 API 回應包含您已公開裝置上的安全設定評估，並傳回 DeviceId，ConfigurationId 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="a7a46-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="a7a46-129">1.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="a7a46-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="a7a46-130">頁面大小上限為200000。</span><span class="sxs-lookup"><span data-stu-id="a7a46-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="a7a46-131">此 API 的速率限制為每分鐘30個通話，每小時1000個通話。</span><span class="sxs-lookup"><span data-stu-id="a7a46-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="a7a46-132">1.2 許可權</span><span class="sxs-lookup"><span data-stu-id="a7a46-132">1.2 Permissions</span></span>

<span data-ttu-id="a7a46-133">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="a7a46-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a7a46-134">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a7a46-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a7a46-135">許可權類型</span><span class="sxs-lookup"><span data-stu-id="a7a46-135">Permission type</span></span> | <span data-ttu-id="a7a46-136">權限</span><span class="sxs-lookup"><span data-stu-id="a7a46-136">Permission</span></span> | <span data-ttu-id="a7a46-137">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a7a46-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="a7a46-138">應用程式</span><span class="sxs-lookup"><span data-stu-id="a7a46-138">Application</span></span> | <span data-ttu-id="a7a46-139">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="a7a46-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="a7a46-140">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="a7a46-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="a7a46-141">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a7a46-141">Delegated (work or school account)</span></span> | <span data-ttu-id="a7a46-142">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="a7a46-142">Vulnerability.Read</span></span> | <span data-ttu-id="a7a46-143">\'讀取威脅及弱點管理弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="a7a46-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="a7a46-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="a7a46-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="a7a46-145">1.4 參數</span><span class="sxs-lookup"><span data-stu-id="a7a46-145">1.4 Parameters</span></span>

- <span data-ttu-id="a7a46-146">pageSize \( 預設值 = 50000 \) –回應的結果數目</span><span class="sxs-lookup"><span data-stu-id="a7a46-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="a7a46-147">\$top –傳回的結果數 \( 不會傳回 \@ Odata。 nextLink，因此不會拉入所有資料\)</span><span class="sxs-lookup"><span data-stu-id="a7a46-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="a7a46-148">1.5 屬性</span><span class="sxs-lookup"><span data-stu-id="a7a46-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="a7a46-149">下表中所定義的屬性，依屬性識別碼列出英數順序。</span><span class="sxs-lookup"><span data-stu-id="a7a46-149">The properties defined in the following table are listed alphanumerically, by property ID.</span></span>  <span data-ttu-id="a7a46-150">執行此 API 時，所產生的輸出不一定會以這些表格中所列的相同順序傳回。</span><span class="sxs-lookup"><span data-stu-id="a7a46-150">When running this API, the resulting output will not necessarily be returned in the same order listed in these tables.</span></span>
>
>- <span data-ttu-id="a7a46-151">其他一些欄可能會在回應中傳回。</span><span class="sxs-lookup"><span data-stu-id="a7a46-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="a7a46-152">這些欄是暫存檔的，而且可能會被移除，請只使用記錄的資料行。</span><span class="sxs-lookup"><span data-stu-id="a7a46-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="a7a46-153">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="a7a46-153">Property (id)</span></span> | <span data-ttu-id="a7a46-154">資料類型</span><span class="sxs-lookup"><span data-stu-id="a7a46-154">Data type</span></span> | <span data-ttu-id="a7a46-155">描述</span><span class="sxs-lookup"><span data-stu-id="a7a46-155">Description</span></span> | <span data-ttu-id="a7a46-156">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a7a46-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="a7a46-157">ConfigurationCategory</span></span> | <span data-ttu-id="a7a46-158">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-158">string</span></span> | <span data-ttu-id="a7a46-159">設定所屬的類別或群組：應用程式、作業系統、網路、帳戶、安全性控制</span><span class="sxs-lookup"><span data-stu-id="a7a46-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="a7a46-160">安全性控制</span><span class="sxs-lookup"><span data-stu-id="a7a46-160">Security controls</span></span>
<span data-ttu-id="a7a46-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="a7a46-161">ConfigurationId</span></span> | <span data-ttu-id="a7a46-162">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-162">string</span></span> | <span data-ttu-id="a7a46-163">特定設定的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="a7a46-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="a7a46-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="a7a46-164">scid-10000</span></span>
<span data-ttu-id="a7a46-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="a7a46-165">ConfigurationImpact</span></span> | <span data-ttu-id="a7a46-166">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-166">string</span></span> | <span data-ttu-id="a7a46-167">設定對整個設定分數 (1-10) 的評分影響</span><span class="sxs-lookup"><span data-stu-id="a7a46-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="a7a46-168">9 </span><span class="sxs-lookup"><span data-stu-id="a7a46-168">9</span></span>
<span data-ttu-id="a7a46-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="a7a46-169">ConfigurationName</span></span> | <span data-ttu-id="a7a46-170">字串</span><span class="sxs-lookup"><span data-stu-id="a7a46-170">string</span></span> | <span data-ttu-id="a7a46-171">組態的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a7a46-171">Display name of the configuration</span></span> | <span data-ttu-id="a7a46-172">將裝置上線至適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a7a46-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="a7a46-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="a7a46-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="a7a46-174">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-174">string</span></span> | <span data-ttu-id="a7a46-175">設定所屬的子類別或子群組。</span><span class="sxs-lookup"><span data-stu-id="a7a46-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="a7a46-176">在許多情況下，這會描述特定性能或功能。</span><span class="sxs-lookup"><span data-stu-id="a7a46-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="a7a46-177">板載裝置</span><span class="sxs-lookup"><span data-stu-id="a7a46-177">Onboard Devices</span></span>
<span data-ttu-id="a7a46-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="a7a46-178">DeviceId</span></span> | <span data-ttu-id="a7a46-179">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-179">string</span></span> | <span data-ttu-id="a7a46-180">服務中裝置的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a7a46-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="a7a46-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="a7a46-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="a7a46-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="a7a46-182">DeviceName</span></span> | <span data-ttu-id="a7a46-183">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-183">string</span></span> | <span data-ttu-id="a7a46-184">裝置 (FQDN) 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="a7a46-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="a7a46-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7a46-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="a7a46-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="a7a46-186">IsApplicable</span></span> | <span data-ttu-id="a7a46-187">bool</span><span class="sxs-lookup"><span data-stu-id="a7a46-187">bool</span></span> | <span data-ttu-id="a7a46-188">指出設定或原則是否適用</span><span class="sxs-lookup"><span data-stu-id="a7a46-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="a7a46-189">真</span><span class="sxs-lookup"><span data-stu-id="a7a46-189">true</span></span>
<span data-ttu-id="a7a46-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="a7a46-190">IsCompliant</span></span> | <span data-ttu-id="a7a46-191">bool</span><span class="sxs-lookup"><span data-stu-id="a7a46-191">bool</span></span> | <span data-ttu-id="a7a46-192">指出設定或原則是否已正確設定</span><span class="sxs-lookup"><span data-stu-id="a7a46-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="a7a46-193">假</span><span class="sxs-lookup"><span data-stu-id="a7a46-193">false</span></span>
<span data-ttu-id="a7a46-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="a7a46-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="a7a46-195">bool</span><span class="sxs-lookup"><span data-stu-id="a7a46-195">bool</span></span> | <span data-ttu-id="a7a46-196">會指出若要套用設定，是否會影響使用者</span><span class="sxs-lookup"><span data-stu-id="a7a46-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="a7a46-197">真</span><span class="sxs-lookup"><span data-stu-id="a7a46-197">true</span></span>
<span data-ttu-id="a7a46-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="a7a46-198">OSPlatform</span></span> | <span data-ttu-id="a7a46-199">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-199">string</span></span> | <span data-ttu-id="a7a46-200">裝置上所執行作業系統的平臺。</span><span class="sxs-lookup"><span data-stu-id="a7a46-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="a7a46-201">這表示特定作業系統，包括相同系列內的變體，例如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="a7a46-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="a7a46-202">如需詳細資訊，請參閱 tvm 支援的作業系統和平臺。</span><span class="sxs-lookup"><span data-stu-id="a7a46-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="a7a46-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="a7a46-203">Windows10</span></span>
<span data-ttu-id="a7a46-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="a7a46-204">RbacGroupName</span></span> | <span data-ttu-id="a7a46-205">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-205">string</span></span> | <span data-ttu-id="a7a46-206">以角色為基礎的存取控制 (RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="a7a46-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="a7a46-207">如果此裝置並未指派給任何 RBAC 群組，此值將會是「未指派」。</span><span class="sxs-lookup"><span data-stu-id="a7a46-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="a7a46-208">如果組織不包含任何 RBAC 群組，則此值會是 "None"。</span><span class="sxs-lookup"><span data-stu-id="a7a46-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="a7a46-209">伺服器</span><span class="sxs-lookup"><span data-stu-id="a7a46-209">Servers</span></span>
<span data-ttu-id="a7a46-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="a7a46-210">RecommendationReference</span></span> | <span data-ttu-id="a7a46-211">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-211">string</span></span> | <span data-ttu-id="a7a46-212">與此軟體相關的建議識別碼參照。</span><span class="sxs-lookup"><span data-stu-id="a7a46-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="a7a46-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="a7a46-213">sca-_-scid-20000</span></span>
<span data-ttu-id="a7a46-214">時間 戳</span><span class="sxs-lookup"><span data-stu-id="a7a46-214">Timestamp</span></span> | <span data-ttu-id="a7a46-215">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-215">string</span></span> | <span data-ttu-id="a7a46-216">最近一次在裝置上看到的設定</span><span class="sxs-lookup"><span data-stu-id="a7a46-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="a7a46-217">2020-11-03 10：13：34.8476880</span><span class="sxs-lookup"><span data-stu-id="a7a46-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="a7a46-218">1.6 範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="a7a46-219">1.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="a7a46-220">1.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="a7a46-221">2. 透過檔案匯出 secure configuration 評估 () </span><span class="sxs-lookup"><span data-stu-id="a7a46-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="a7a46-222">2.1 API 方法描述</span><span class="sxs-lookup"><span data-stu-id="a7a46-222">2.1 API method description</span></span>

<span data-ttu-id="a7a46-223">此 API 回應包含您已公開裝置上的安全設定評估，並傳回 DeviceId，ConfigurationId 的每個唯一組合的專案。</span><span class="sxs-lookup"><span data-stu-id="a7a46-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="a7a46-224">2.1.2 限制</span><span class="sxs-lookup"><span data-stu-id="a7a46-224">2.1.2 Limitations</span></span>

<span data-ttu-id="a7a46-225">此 API 的速率限制是每分鐘5個通話，每小時20個通話。</span><span class="sxs-lookup"><span data-stu-id="a7a46-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="a7a46-226">2.2 許可權</span><span class="sxs-lookup"><span data-stu-id="a7a46-226">2.2 Permissions</span></span>

<span data-ttu-id="a7a46-227">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="a7a46-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a7a46-228">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs 以取得詳細資訊。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a7a46-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="a7a46-229">許可權類型</span><span class="sxs-lookup"><span data-stu-id="a7a46-229">Permission type</span></span> | <span data-ttu-id="a7a46-230">權限</span><span class="sxs-lookup"><span data-stu-id="a7a46-230">Permission</span></span> | <span data-ttu-id="a7a46-231">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a7a46-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="a7a46-232">應用程式</span><span class="sxs-lookup"><span data-stu-id="a7a46-232">Application</span></span> | <span data-ttu-id="a7a46-233">弱點。 Read。 All</span><span class="sxs-lookup"><span data-stu-id="a7a46-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="a7a46-234">\'讀取「威脅與弱點管理」弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="a7a46-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="a7a46-235">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a7a46-235">Delegated (work or school account)</span></span> | <span data-ttu-id="a7a46-236">弱點。讀取</span><span class="sxs-lookup"><span data-stu-id="a7a46-236">Vulnerability.Read</span></span> | <span data-ttu-id="a7a46-237">\'讀取「威脅與弱點管理」弱點資訊\'</span><span class="sxs-lookup"><span data-stu-id="a7a46-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="a7a46-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="a7a46-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="a7a46-239">參數</span><span class="sxs-lookup"><span data-stu-id="a7a46-239">Parameters</span></span>

- <span data-ttu-id="a7a46-240">sasValidHours –下載 URLs (最長24小時) 時可有效的小時數。</span><span class="sxs-lookup"><span data-stu-id="a7a46-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="a7a46-241">2.5 屬性</span><span class="sxs-lookup"><span data-stu-id="a7a46-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="a7a46-242">這些檔案是以多行 Json 格式的 gzip 壓縮 &。</span><span class="sxs-lookup"><span data-stu-id="a7a46-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="a7a46-243">下載 URLs 只會在3小時內有效;否則您可以使用參數。</span><span class="sxs-lookup"><span data-stu-id="a7a46-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="a7a46-244">為了獲得最大的下載速度，您可以確保從您的資料所在的相同 Azure 地區下載。</span><span class="sxs-lookup"><span data-stu-id="a7a46-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="a7a46-245">屬性 (識別碼) </span><span class="sxs-lookup"><span data-stu-id="a7a46-245">Property (id)</span></span> | <span data-ttu-id="a7a46-246">資料類型</span><span class="sxs-lookup"><span data-stu-id="a7a46-246">Data type</span></span> | <span data-ttu-id="a7a46-247">描述</span><span class="sxs-lookup"><span data-stu-id="a7a46-247">Description</span></span> | <span data-ttu-id="a7a46-248">傳回值的範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="a7a46-249">匯出檔案</span><span class="sxs-lookup"><span data-stu-id="a7a46-249">Export files</span></span> | <span data-ttu-id="a7a46-250">陣列 \[ 字串\]</span><span class="sxs-lookup"><span data-stu-id="a7a46-250">array\[string\]</span></span> | <span data-ttu-id="a7a46-251">用於存放組織目前快照之檔案的下載 URLs 清單</span><span class="sxs-lookup"><span data-stu-id="a7a46-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="a7a46-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="a7a46-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="a7a46-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="a7a46-253">GeneratedTime</span></span> | <span data-ttu-id="a7a46-254">string</span><span class="sxs-lookup"><span data-stu-id="a7a46-254">string</span></span> | <span data-ttu-id="a7a46-255">產生匯出的時間。</span><span class="sxs-lookup"><span data-stu-id="a7a46-255">The time that the export was generated.</span></span> | <span data-ttu-id="a7a46-256">2021-05-20T08：00： 00Z]</span><span class="sxs-lookup"><span data-stu-id="a7a46-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="a7a46-257">2.6 範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="a7a46-258">2.6.1 要求範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="a7a46-259">2.6.2 回應範例</span><span class="sxs-lookup"><span data-stu-id="a7a46-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="a7a46-260">請參閱</span><span class="sxs-lookup"><span data-stu-id="a7a46-260">See also</span></span>

- [<span data-ttu-id="a7a46-261">匯出每台裝置的評估方法和屬性</span><span class="sxs-lookup"><span data-stu-id="a7a46-261">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="a7a46-262">每個裝置匯出軟體清查評估</span><span class="sxs-lookup"><span data-stu-id="a7a46-262">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

- [<span data-ttu-id="a7a46-263">每個裝置的匯出軟體漏洞評估</span><span class="sxs-lookup"><span data-stu-id="a7a46-263">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="a7a46-264">其他相關</span><span class="sxs-lookup"><span data-stu-id="a7a46-264">Other related</span></span>

- [<span data-ttu-id="a7a46-265">風險威脅 & 弱點管理</span><span class="sxs-lookup"><span data-stu-id="a7a46-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="a7a46-266">組織中的薄弱環節</span><span class="sxs-lookup"><span data-stu-id="a7a46-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
