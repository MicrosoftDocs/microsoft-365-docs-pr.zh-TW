---
title: 常見的 Microsoft 365 Defender REST API 錯誤碼
description: 深入瞭解常見的 Microsoft 365 Defender REST API 錯誤碼
keywords: api、錯誤、代碼、常見錯誤、mtp、api 錯誤碼
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719211"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="527a1-104">常見的 Microsoft 365 Defender REST API 錯誤碼</span><span class="sxs-lookup"><span data-stu-id="527a1-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="527a1-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="527a1-105">**Applies to:**</span></span>

- <span data-ttu-id="527a1-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="527a1-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="527a1-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="527a1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="527a1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="527a1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="527a1-109">錯誤代碼可能會在任何 Microsoft 365 Defender APIs 上的操作傳回。</span><span class="sxs-lookup"><span data-stu-id="527a1-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="527a1-110">每個錯誤回應都會包含一則錯誤訊息，可協助您解決問題。</span><span class="sxs-lookup"><span data-stu-id="527a1-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="527a1-111">[資料表] 區段中的 [錯誤訊息] 欄提供一些範例訊息。</span><span class="sxs-lookup"><span data-stu-id="527a1-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="527a1-112">實際郵件的內容會因觸發回應的因素而異。</span><span class="sxs-lookup"><span data-stu-id="527a1-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="527a1-113">在表格中，依角括弧顯示變數內容。</span><span class="sxs-lookup"><span data-stu-id="527a1-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="527a1-114">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="527a1-114">Error codes</span></span>

<span data-ttu-id="527a1-115">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="527a1-115">Error code</span></span> | <span data-ttu-id="527a1-116">HTTP 狀態碼</span><span class="sxs-lookup"><span data-stu-id="527a1-116">HTTP status code</span></span> | <span data-ttu-id="527a1-117">訊息</span><span class="sxs-lookup"><span data-stu-id="527a1-117">Message</span></span>
-|-|-
<span data-ttu-id="527a1-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="527a1-118">BadRequest</span></span> | <span data-ttu-id="527a1-119">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-119">BadRequest (400)</span></span> | <span data-ttu-id="527a1-120">一般錯誤要求錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="527a1-120">General Bad Request error message.</span></span>
<span data-ttu-id="527a1-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="527a1-121">ODataError</span></span> | <span data-ttu-id="527a1-122">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-122">BadRequest (400)</span></span> | <span data-ttu-id="527a1-123">不正確 OData URI 查詢 \<the specific error is specified\> 。</span><span class="sxs-lookup"><span data-stu-id="527a1-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="527a1-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="527a1-124">InvalidInput</span></span> | <span data-ttu-id="527a1-125">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-125">BadRequest (400)</span></span> | <span data-ttu-id="527a1-126">輸入無效 \<the invalid input\> 。</span><span class="sxs-lookup"><span data-stu-id="527a1-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="527a1-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="527a1-127">InvalidRequestBody</span></span> | <span data-ttu-id="527a1-128">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-128">BadRequest (400)</span></span> | <span data-ttu-id="527a1-129">不正確要求正文。</span><span class="sxs-lookup"><span data-stu-id="527a1-129">Invalid request body.</span></span>
<span data-ttu-id="527a1-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="527a1-130">InvalidHashValue</span></span> | <span data-ttu-id="527a1-131">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-131">BadRequest (400)</span></span> | <span data-ttu-id="527a1-132">雜湊值 \<the invalid hash\> 無效。</span><span class="sxs-lookup"><span data-stu-id="527a1-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="527a1-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="527a1-133">InvalidDomainName</span></span> | <span data-ttu-id="527a1-134">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-134">BadRequest (400)</span></span> | <span data-ttu-id="527a1-135">功能變數名稱 \<the invalid domain\> 無效。</span><span class="sxs-lookup"><span data-stu-id="527a1-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="527a1-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="527a1-136">InvalidIpAddress</span></span> | <span data-ttu-id="527a1-137">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-137">BadRequest (400)</span></span> | <span data-ttu-id="527a1-138">IP 位址 \<the invalid IP\> 無效。</span><span class="sxs-lookup"><span data-stu-id="527a1-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="527a1-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="527a1-139">InvalidUrl</span></span> | <span data-ttu-id="527a1-140">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-140">BadRequest (400)</span></span> | <span data-ttu-id="527a1-141">URL \<the invalid URL\> 無效。</span><span class="sxs-lookup"><span data-stu-id="527a1-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="527a1-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="527a1-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="527a1-143">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-143">BadRequest (400)</span></span> | <span data-ttu-id="527a1-144">超過批次大小上限。</span><span class="sxs-lookup"><span data-stu-id="527a1-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="527a1-145">已接收： \<batch size received\> ，允許： {允許的批次大小}。</span><span class="sxs-lookup"><span data-stu-id="527a1-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="527a1-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="527a1-146">MissingRequiredParameter</span></span> | <span data-ttu-id="527a1-147">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-147">BadRequest (400)</span></span> | <span data-ttu-id="527a1-148">\<the missing parameter\>缺少參數。</span><span class="sxs-lookup"><span data-stu-id="527a1-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="527a1-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="527a1-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="527a1-150">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-150">BadRequest (400)</span></span> | <span data-ttu-id="527a1-151">\<the client OS Platform\>此動作不支援作業系統平臺。</span><span class="sxs-lookup"><span data-stu-id="527a1-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="527a1-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="527a1-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="527a1-153">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="527a1-153">BadRequest (400)</span></span> | <span data-ttu-id="527a1-154">\<The requested action\> 支援用戶端版本和更新版本 \<supported client version\> 。</span><span class="sxs-lookup"><span data-stu-id="527a1-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="527a1-155">未經 授權</span><span class="sxs-lookup"><span data-stu-id="527a1-155">Unauthorized</span></span> | <span data-ttu-id="527a1-156">未經授權的 (401) </span><span class="sxs-lookup"><span data-stu-id="527a1-156">Unauthorized (401)</span></span> | <span data-ttu-id="527a1-157">未經 授權</span><span class="sxs-lookup"><span data-stu-id="527a1-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="527a1-158">*附注：通常是由無效或過期的授權標頭所造成。*</span><span class="sxs-lookup"><span data-stu-id="527a1-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="527a1-159">禁止</span><span class="sxs-lookup"><span data-stu-id="527a1-159">Forbidden</span></span> | <span data-ttu-id="527a1-160">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="527a1-160">Forbidden (403)</span></span> | <span data-ttu-id="527a1-161">禁止</span><span class="sxs-lookup"><span data-stu-id="527a1-161">Forbidden</span></span> <br /><br /><span data-ttu-id="527a1-162">*附注：有效的權杖，但動作的許可權不足*。</span><span class="sxs-lookup"><span data-stu-id="527a1-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="527a1-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="527a1-163">DisabledFeature</span></span> | <span data-ttu-id="527a1-164">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="527a1-164">Forbidden (403)</span></span> | <span data-ttu-id="527a1-165">未啟用租使用者功能。</span><span class="sxs-lookup"><span data-stu-id="527a1-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="527a1-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="527a1-166">DisallowedOperation</span></span> | <span data-ttu-id="527a1-167">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="527a1-167">Forbidden (403)</span></span> | <span data-ttu-id="527a1-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="527a1-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="527a1-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="527a1-169">NotFound</span></span> | <span data-ttu-id="527a1-170">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="527a1-170">Not Found (404)</span></span> | <span data-ttu-id="527a1-171">找不到一般錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="527a1-171">General Not Found error message.</span></span>
<span data-ttu-id="527a1-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="527a1-172">ResourceNotFound</span></span> | <span data-ttu-id="527a1-173">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="527a1-173">Not Found (404)</span></span> | <span data-ttu-id="527a1-174">\<the requested resource\>找不到資源。</span><span class="sxs-lookup"><span data-stu-id="527a1-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="527a1-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="527a1-175">InternalServerError</span></span> | <span data-ttu-id="527a1-176">內部伺服器錯誤 (500) </span><span class="sxs-lookup"><span data-stu-id="527a1-176">Internal Server Error (500)</span></span> | <span data-ttu-id="527a1-177">*附注：沒有錯誤訊息，請重試作業，或與 Microsoft 聯繫（如果它未解決）*</span><span class="sxs-lookup"><span data-stu-id="527a1-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="527a1-178">範例</span><span class="sxs-lookup"><span data-stu-id="527a1-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="527a1-179">Body 參數</span><span class="sxs-lookup"><span data-stu-id="527a1-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="527a1-180">主體參數會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="527a1-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="527a1-181">如果您遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 錯誤，可能是因為鍵入錯誤所造成。</span><span class="sxs-lookup"><span data-stu-id="527a1-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="527a1-182">請複查 API 檔，並檢查提交的參數是否符合相關的範例。</span><span class="sxs-lookup"><span data-stu-id="527a1-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="527a1-183">追蹤識別碼</span><span class="sxs-lookup"><span data-stu-id="527a1-183">Tracking ID</span></span>

<span data-ttu-id="527a1-184">每個錯誤回應都包含一個用於追蹤的唯一識別碼參數。</span><span class="sxs-lookup"><span data-stu-id="527a1-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="527a1-185">此參數的屬性名稱為 *target*。</span><span class="sxs-lookup"><span data-stu-id="527a1-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="527a1-186">當您聯繫我們有關錯誤的資訊時，附加此識別碼會協助我們找出問題的根本原因。</span><span class="sxs-lookup"><span data-stu-id="527a1-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="527a1-187">相關文章</span><span class="sxs-lookup"><span data-stu-id="527a1-187">Related articles</span></span>

- [<span data-ttu-id="527a1-188">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="527a1-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="527a1-189">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="527a1-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="527a1-190">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="527a1-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="527a1-191">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="527a1-191">Learn about API limits and licensing</span></span>](api-terms.md)
