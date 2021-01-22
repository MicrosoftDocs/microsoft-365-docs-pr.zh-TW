---
title: 常見的 Microsoft 365 Defender REST API 錯誤碼
description: 瞭解常見的 Microsoft 365 Defender REST API 錯誤碼
keywords: api， 錯誤， 程式碼， 常見錯誤， mtp， api 錯誤碼
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928387"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="74ef8-104">常見的 Microsoft 365 Defender REST API 錯誤碼</span><span class="sxs-lookup"><span data-stu-id="74ef8-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="74ef8-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="74ef8-105">**Applies to:**</span></span>

- <span data-ttu-id="74ef8-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="74ef8-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74ef8-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="74ef8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="74ef8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="74ef8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="74ef8-109">任何 Microsoft 365 Defender API 上的作業可能會返回錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="74ef8-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="74ef8-110">每個錯誤回應都會包含錯誤訊息，可協助解決問題。</span><span class="sxs-lookup"><span data-stu-id="74ef8-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="74ef8-111">表格區段的錯誤訊息欄提供一些範例訊息。</span><span class="sxs-lookup"><span data-stu-id="74ef8-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="74ef8-112">實際郵件的內容會根據觸發回應的因素而不同。</span><span class="sxs-lookup"><span data-stu-id="74ef8-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="74ef8-113">在表格中以角括弧表示變數內容。</span><span class="sxs-lookup"><span data-stu-id="74ef8-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="74ef8-114">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="74ef8-114">Error codes</span></span>

<span data-ttu-id="74ef8-115">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="74ef8-115">Error code</span></span> | <span data-ttu-id="74ef8-116">HTTP 狀態碼</span><span class="sxs-lookup"><span data-stu-id="74ef8-116">HTTP status code</span></span> | <span data-ttu-id="74ef8-117">訊息</span><span class="sxs-lookup"><span data-stu-id="74ef8-117">Message</span></span>
-|-|-
<span data-ttu-id="74ef8-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="74ef8-118">BadRequest</span></span> | <span data-ttu-id="74ef8-119">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-119">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-120">一般錯誤要求錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="74ef8-120">General Bad Request error message.</span></span>
<span data-ttu-id="74ef8-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="74ef8-121">ODataError</span></span> | <span data-ttu-id="74ef8-122">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-122">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-123">不正確 OData URI 查詢 \<the specific error is specified\> 。</span><span class="sxs-lookup"><span data-stu-id="74ef8-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="74ef8-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="74ef8-124">InvalidInput</span></span> | <span data-ttu-id="74ef8-125">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-125">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-126">不正確輸入 \<the invalid input\> 。</span><span class="sxs-lookup"><span data-stu-id="74ef8-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="74ef8-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="74ef8-127">InvalidRequestBody</span></span> | <span data-ttu-id="74ef8-128">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-128">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-129">不正確要求內方。</span><span class="sxs-lookup"><span data-stu-id="74ef8-129">Invalid request body.</span></span>
<span data-ttu-id="74ef8-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="74ef8-130">InvalidHashValue</span></span> | <span data-ttu-id="74ef8-131">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-131">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-132">雜湊 \<the invalid hash\> 值無效。</span><span class="sxs-lookup"><span data-stu-id="74ef8-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="74ef8-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="74ef8-133">InvalidDomainName</span></span> | <span data-ttu-id="74ef8-134">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-134">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-135">功能變數名稱 \<the invalid domain\> 無效。</span><span class="sxs-lookup"><span data-stu-id="74ef8-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="74ef8-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="74ef8-136">InvalidIpAddress</span></span> | <span data-ttu-id="74ef8-137">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-137">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-138">IP \<the invalid IP\> 位址無效。</span><span class="sxs-lookup"><span data-stu-id="74ef8-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="74ef8-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="74ef8-139">InvalidUrl</span></span> | <span data-ttu-id="74ef8-140">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-140">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-141">URL \<the invalid URL\> 無效。</span><span class="sxs-lookup"><span data-stu-id="74ef8-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="74ef8-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="74ef8-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="74ef8-143">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-143">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-144">已超過批次大小上限。</span><span class="sxs-lookup"><span data-stu-id="74ef8-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="74ef8-145">收到 \<batch size received\> ：，允許：{batch size allowed}。</span><span class="sxs-lookup"><span data-stu-id="74ef8-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="74ef8-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="74ef8-146">MissingRequiredParameter</span></span> | <span data-ttu-id="74ef8-147">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-147">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-148">參數 \<the missing parameter\> 遺失。</span><span class="sxs-lookup"><span data-stu-id="74ef8-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="74ef8-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="74ef8-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="74ef8-150">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-150">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-151">不支援 \<the client OS Platform\> 作業系統平臺執行此動作。</span><span class="sxs-lookup"><span data-stu-id="74ef8-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="74ef8-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="74ef8-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="74ef8-153">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="74ef8-153">BadRequest (400)</span></span> | <span data-ttu-id="74ef8-154">\<The requested action\> 支援用戶端版本及 \<supported client version\> 更新版本。</span><span class="sxs-lookup"><span data-stu-id="74ef8-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="74ef8-155">未經 授權</span><span class="sxs-lookup"><span data-stu-id="74ef8-155">Unauthorized</span></span> | <span data-ttu-id="74ef8-156">未經授權的 (401) </span><span class="sxs-lookup"><span data-stu-id="74ef8-156">Unauthorized (401)</span></span> | <span data-ttu-id="74ef8-157">未經 授權</span><span class="sxs-lookup"><span data-stu-id="74ef8-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="74ef8-158">*注意：通常是由無效或過期的授權標題所導致。*</span><span class="sxs-lookup"><span data-stu-id="74ef8-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="74ef8-159">禁止</span><span class="sxs-lookup"><span data-stu-id="74ef8-159">Forbidden</span></span> | <span data-ttu-id="74ef8-160">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="74ef8-160">Forbidden (403)</span></span> | <span data-ttu-id="74ef8-161">禁止</span><span class="sxs-lookup"><span data-stu-id="74ef8-161">Forbidden</span></span> <br /><br /><span data-ttu-id="74ef8-162">*注意：有效的權杖，但動作許可權不足*。</span><span class="sxs-lookup"><span data-stu-id="74ef8-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="74ef8-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="74ef8-163">DisabledFeature</span></span> | <span data-ttu-id="74ef8-164">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="74ef8-164">Forbidden (403)</span></span> | <span data-ttu-id="74ef8-165">未啟用租使用者功能。</span><span class="sxs-lookup"><span data-stu-id="74ef8-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="74ef8-166">不允許的Operation</span><span class="sxs-lookup"><span data-stu-id="74ef8-166">DisallowedOperation</span></span> | <span data-ttu-id="74ef8-167">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="74ef8-167">Forbidden (403)</span></span> | <span data-ttu-id="74ef8-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="74ef8-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="74ef8-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="74ef8-169">NotFound</span></span> | <span data-ttu-id="74ef8-170">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="74ef8-170">Not Found (404)</span></span> | <span data-ttu-id="74ef8-171">一般找不到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="74ef8-171">General Not Found error message.</span></span>
<span data-ttu-id="74ef8-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="74ef8-172">ResourceNotFound</span></span> | <span data-ttu-id="74ef8-173">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="74ef8-173">Not Found (404)</span></span> | <span data-ttu-id="74ef8-174">找不到 \<the requested resource\> 資源。</span><span class="sxs-lookup"><span data-stu-id="74ef8-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="74ef8-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="74ef8-175">InternalServerError</span></span> | <span data-ttu-id="74ef8-176">內部伺服器錯誤 (500) </span><span class="sxs-lookup"><span data-stu-id="74ef8-176">Internal Server Error (500)</span></span> | <span data-ttu-id="74ef8-177">*注意：沒有錯誤訊息，請重試作業，或如果無法解決，請聯絡 Microsoft*</span><span class="sxs-lookup"><span data-stu-id="74ef8-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="74ef8-178">範例</span><span class="sxs-lookup"><span data-stu-id="74ef8-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="74ef8-179">Body 參數</span><span class="sxs-lookup"><span data-stu-id="74ef8-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74ef8-180">本參數會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="74ef8-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="74ef8-181">如果您遇到 *InvalidRequestBody* 或 *MissingRequiredParameter* 錯誤，這可能是因為錯字所造成。</span><span class="sxs-lookup"><span data-stu-id="74ef8-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="74ef8-182">檢閱 API 檔，並檢查提交的參數是否與相關範例相符。</span><span class="sxs-lookup"><span data-stu-id="74ef8-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="74ef8-183">追蹤識別碼</span><span class="sxs-lookup"><span data-stu-id="74ef8-183">Tracking ID</span></span>

<span data-ttu-id="74ef8-184">每個錯誤回應都包含用於追蹤的唯一識別碼參數。</span><span class="sxs-lookup"><span data-stu-id="74ef8-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="74ef8-185">此參數的屬性名稱為 *目標*。</span><span class="sxs-lookup"><span data-stu-id="74ef8-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="74ef8-186">當我們詢問錯誤時，附加此識別碼將可協助我們找出問題的根本原因。</span><span class="sxs-lookup"><span data-stu-id="74ef8-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="74ef8-187">相關文章</span><span class="sxs-lookup"><span data-stu-id="74ef8-187">Related articles</span></span>

- [<span data-ttu-id="74ef8-188">Microsoft 365 Defender API 概觀</span><span class="sxs-lookup"><span data-stu-id="74ef8-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="74ef8-189">支援的 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="74ef8-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="74ef8-190">存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="74ef8-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="74ef8-191">瞭解 API 限制與授權</span><span class="sxs-lookup"><span data-stu-id="74ef8-191">Learn about API limits and licensing</span></span>](api-terms.md)
