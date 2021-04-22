---
title: 常見的 Microsoft 365 Defender REST API 錯誤碼
description: 深入瞭解常見的 Microsoft 365 Defender REST API 錯誤碼
keywords: api、錯誤、代碼、常見錯誤、Microsoft 365 Defender、api 錯誤碼
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932878"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="314f7-104">常見的 Microsoft 365 Defender REST API 錯誤碼</span><span class="sxs-lookup"><span data-stu-id="314f7-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="314f7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="314f7-105">**Applies to:**</span></span>

- <span data-ttu-id="314f7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="314f7-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="314f7-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="314f7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="314f7-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="314f7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="314f7-109">錯誤代碼可能會在任何 Microsoft 365 Defender APIs 上的操作傳回。</span><span class="sxs-lookup"><span data-stu-id="314f7-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="314f7-110">每個錯誤回應都會包含一則錯誤訊息，可協助您解決問題。</span><span class="sxs-lookup"><span data-stu-id="314f7-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="314f7-111">[資料表] 區段中的 [錯誤訊息] 欄提供一些範例訊息。</span><span class="sxs-lookup"><span data-stu-id="314f7-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="314f7-112">實際郵件的內容會因觸發回應的因素而異。</span><span class="sxs-lookup"><span data-stu-id="314f7-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="314f7-113">在表格中，依角括弧顯示變數內容。</span><span class="sxs-lookup"><span data-stu-id="314f7-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="314f7-114">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="314f7-114">Error codes</span></span>

<span data-ttu-id="314f7-115">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="314f7-115">Error code</span></span> | <span data-ttu-id="314f7-116">HTTP 狀態碼</span><span class="sxs-lookup"><span data-stu-id="314f7-116">HTTP status code</span></span> | <span data-ttu-id="314f7-117">訊息</span><span class="sxs-lookup"><span data-stu-id="314f7-117">Message</span></span>
-|-|-
<span data-ttu-id="314f7-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="314f7-118">BadRequest</span></span> | <span data-ttu-id="314f7-119">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-119">BadRequest (400)</span></span> | <span data-ttu-id="314f7-120">一般錯誤要求錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="314f7-120">General Bad Request error message.</span></span>
<span data-ttu-id="314f7-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="314f7-121">ODataError</span></span> | <span data-ttu-id="314f7-122">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-122">BadRequest (400)</span></span> | <span data-ttu-id="314f7-123">不正確 OData URI 查詢 \<the specific error is specified\> 。</span><span class="sxs-lookup"><span data-stu-id="314f7-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="314f7-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="314f7-124">InvalidInput</span></span> | <span data-ttu-id="314f7-125">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-125">BadRequest (400)</span></span> | <span data-ttu-id="314f7-126">輸入無效 \<the invalid input\> 。</span><span class="sxs-lookup"><span data-stu-id="314f7-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="314f7-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="314f7-127">InvalidRequestBody</span></span> | <span data-ttu-id="314f7-128">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-128">BadRequest (400)</span></span> | <span data-ttu-id="314f7-129">不正確要求正文。</span><span class="sxs-lookup"><span data-stu-id="314f7-129">Invalid request body.</span></span>
<span data-ttu-id="314f7-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="314f7-130">InvalidHashValue</span></span> | <span data-ttu-id="314f7-131">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-131">BadRequest (400)</span></span> | <span data-ttu-id="314f7-132">雜湊值 \<the invalid hash\> 無效。</span><span class="sxs-lookup"><span data-stu-id="314f7-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="314f7-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="314f7-133">InvalidDomainName</span></span> | <span data-ttu-id="314f7-134">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-134">BadRequest (400)</span></span> | <span data-ttu-id="314f7-135">功能變數名稱 \<the invalid domain\> 無效。</span><span class="sxs-lookup"><span data-stu-id="314f7-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="314f7-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="314f7-136">InvalidIpAddress</span></span> | <span data-ttu-id="314f7-137">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-137">BadRequest (400)</span></span> | <span data-ttu-id="314f7-138">IP 位址 \<the invalid IP\> 無效。</span><span class="sxs-lookup"><span data-stu-id="314f7-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="314f7-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="314f7-139">InvalidUrl</span></span> | <span data-ttu-id="314f7-140">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-140">BadRequest (400)</span></span> | <span data-ttu-id="314f7-141">URL \<the invalid URL\> 無效。</span><span class="sxs-lookup"><span data-stu-id="314f7-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="314f7-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="314f7-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="314f7-143">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-143">BadRequest (400)</span></span> | <span data-ttu-id="314f7-144">超過批次大小上限。</span><span class="sxs-lookup"><span data-stu-id="314f7-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="314f7-145">已接收： \<batch size received\> ，允許： {允許的批次大小}。</span><span class="sxs-lookup"><span data-stu-id="314f7-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="314f7-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="314f7-146">MissingRequiredParameter</span></span> | <span data-ttu-id="314f7-147">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-147">BadRequest (400)</span></span> | <span data-ttu-id="314f7-148">\<the missing parameter\>缺少參數。</span><span class="sxs-lookup"><span data-stu-id="314f7-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="314f7-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="314f7-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="314f7-150">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-150">BadRequest (400)</span></span> | <span data-ttu-id="314f7-151">\<the client OS Platform\>此動作不支援作業系統平臺。</span><span class="sxs-lookup"><span data-stu-id="314f7-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="314f7-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="314f7-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="314f7-153">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="314f7-153">BadRequest (400)</span></span> | <span data-ttu-id="314f7-154">\<The requested action\> 支援用戶端版本和更新版本 \<supported client version\> 。</span><span class="sxs-lookup"><span data-stu-id="314f7-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="314f7-155">未經 授權</span><span class="sxs-lookup"><span data-stu-id="314f7-155">Unauthorized</span></span> | <span data-ttu-id="314f7-156">未經授權的 (401) </span><span class="sxs-lookup"><span data-stu-id="314f7-156">Unauthorized (401)</span></span> | <span data-ttu-id="314f7-157">未經 授權</span><span class="sxs-lookup"><span data-stu-id="314f7-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="314f7-158">*附注：通常是由無效或過期的授權標頭所造成。*</span><span class="sxs-lookup"><span data-stu-id="314f7-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="314f7-159">禁止</span><span class="sxs-lookup"><span data-stu-id="314f7-159">Forbidden</span></span> | <span data-ttu-id="314f7-160">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="314f7-160">Forbidden (403)</span></span> | <span data-ttu-id="314f7-161">禁止</span><span class="sxs-lookup"><span data-stu-id="314f7-161">Forbidden</span></span> <br /><br /><span data-ttu-id="314f7-162">*附注：有效的權杖，但動作的許可權不足*。</span><span class="sxs-lookup"><span data-stu-id="314f7-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="314f7-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="314f7-163">DisabledFeature</span></span> | <span data-ttu-id="314f7-164">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="314f7-164">Forbidden (403)</span></span> | <span data-ttu-id="314f7-165">未啟用租使用者功能。</span><span class="sxs-lookup"><span data-stu-id="314f7-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="314f7-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="314f7-166">DisallowedOperation</span></span> | <span data-ttu-id="314f7-167">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="314f7-167">Forbidden (403)</span></span> | <span data-ttu-id="314f7-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="314f7-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="314f7-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="314f7-169">NotFound</span></span> | <span data-ttu-id="314f7-170">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="314f7-170">Not Found (404)</span></span> | <span data-ttu-id="314f7-171">找不到一般錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="314f7-171">General Not Found error message.</span></span>
<span data-ttu-id="314f7-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="314f7-172">ResourceNotFound</span></span> | <span data-ttu-id="314f7-173">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="314f7-173">Not Found (404)</span></span> | <span data-ttu-id="314f7-174">\<the requested resource\>找不到資源。</span><span class="sxs-lookup"><span data-stu-id="314f7-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="314f7-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="314f7-175">InternalServerError</span></span> | <span data-ttu-id="314f7-176">內部伺服器錯誤 (500) </span><span class="sxs-lookup"><span data-stu-id="314f7-176">Internal Server Error (500)</span></span> | <span data-ttu-id="314f7-177">*附注：沒有錯誤訊息，請重試作業，或與 Microsoft 聯繫（如果它未解決）*</span><span class="sxs-lookup"><span data-stu-id="314f7-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="314f7-178">範例</span><span class="sxs-lookup"><span data-stu-id="314f7-178">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a><span data-ttu-id="314f7-179">Body 參數</span><span class="sxs-lookup"><span data-stu-id="314f7-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="314f7-180">主體參數會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="314f7-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="314f7-181">如果您遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 錯誤，可能是因為鍵入錯誤所造成。</span><span class="sxs-lookup"><span data-stu-id="314f7-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="314f7-182">請複查 API 檔，並檢查提交的參數是否符合相關的範例。</span><span class="sxs-lookup"><span data-stu-id="314f7-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="314f7-183">追蹤識別碼</span><span class="sxs-lookup"><span data-stu-id="314f7-183">Tracking ID</span></span>

<span data-ttu-id="314f7-184">每個錯誤回應都包含一個用於追蹤的唯一識別碼參數。</span><span class="sxs-lookup"><span data-stu-id="314f7-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="314f7-185">此參數的屬性名稱為 *target*。</span><span class="sxs-lookup"><span data-stu-id="314f7-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="314f7-186">當您聯繫我們有關錯誤的資訊時，附加此識別碼會協助我們找出問題的根本原因。</span><span class="sxs-lookup"><span data-stu-id="314f7-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="314f7-187">相關文章</span><span class="sxs-lookup"><span data-stu-id="314f7-187">Related articles</span></span>

- [<span data-ttu-id="314f7-188">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="314f7-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="314f7-189">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="314f7-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="314f7-190">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="314f7-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="314f7-191">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="314f7-191">Learn about API limits and licensing</span></span>](api-terms.md)
