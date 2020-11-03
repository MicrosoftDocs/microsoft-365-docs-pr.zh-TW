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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846005"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="b58da-104">常見的 Microsoft 365 Defender REST API 錯誤碼</span><span class="sxs-lookup"><span data-stu-id="b58da-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b58da-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="b58da-105">**Applies to:**</span></span>
- <span data-ttu-id="b58da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b58da-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="b58da-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="b58da-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b58da-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b58da-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b58da-109">下表所列的錯誤代碼可能會由任何 Microsoft 365 Defender APIs 上的操作所傳回。</span><span class="sxs-lookup"><span data-stu-id="b58da-109">The error codes listed in the following table may be returned by an operation on any of Microsoft 365 Defender APIs.</span></span>

<span data-ttu-id="b58da-110">每個錯誤回應都會包含一則錯誤訊息，可協助您解決問題。</span><span class="sxs-lookup"><span data-stu-id="b58da-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="b58da-111">郵件是可變更的普通文字。</span><span class="sxs-lookup"><span data-stu-id="b58da-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="b58da-112">在頁面底部，您可以找到回應範例。</span><span class="sxs-lookup"><span data-stu-id="b58da-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="b58da-113">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="b58da-113">Error code</span></span> |<span data-ttu-id="b58da-114">HTTP 狀態碼</span><span class="sxs-lookup"><span data-stu-id="b58da-114">HTTP status code</span></span> |<span data-ttu-id="b58da-115">訊息</span><span class="sxs-lookup"><span data-stu-id="b58da-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="b58da-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="b58da-116">BadRequest</span></span> | <span data-ttu-id="b58da-117">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-117">BadRequest (400)</span></span> | <span data-ttu-id="b58da-118">一般錯誤要求錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b58da-118">General Bad Request error message.</span></span>
<span data-ttu-id="b58da-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="b58da-119">ODataError</span></span> | <span data-ttu-id="b58da-120">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-120">BadRequest (400)</span></span> | <span data-ttu-id="b58da-121">OData URI 查詢無效 () 指定特定錯誤。</span><span class="sxs-lookup"><span data-stu-id="b58da-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="b58da-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="b58da-122">InvalidInput</span></span> | <span data-ttu-id="b58da-123">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-123">BadRequest (400)</span></span> | <span data-ttu-id="b58da-124">不正確輸入 {不正確輸入}。</span><span class="sxs-lookup"><span data-stu-id="b58da-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="b58da-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="b58da-125">InvalidRequestBody</span></span> | <span data-ttu-id="b58da-126">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-126">BadRequest (400)</span></span> | <span data-ttu-id="b58da-127">不正確要求正文。</span><span class="sxs-lookup"><span data-stu-id="b58da-127">Invalid request body.</span></span>
<span data-ttu-id="b58da-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="b58da-128">InvalidHashValue</span></span> | <span data-ttu-id="b58da-129">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-129">BadRequest (400)</span></span> | <span data-ttu-id="b58da-130">雜湊值 {不正確雜湊} 無效。</span><span class="sxs-lookup"><span data-stu-id="b58da-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="b58da-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="b58da-131">InvalidDomainName</span></span> | <span data-ttu-id="b58da-132">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-132">BadRequest (400)</span></span> | <span data-ttu-id="b58da-133">功能變數名稱 {不正確網域} 無效。</span><span class="sxs-lookup"><span data-stu-id="b58da-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="b58da-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="b58da-134">InvalidIpAddress</span></span> | <span data-ttu-id="b58da-135">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-135">BadRequest (400)</span></span> | <span data-ttu-id="b58da-136">IP 位址 {不正確 IP} 無效。</span><span class="sxs-lookup"><span data-stu-id="b58da-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="b58da-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="b58da-137">InvalidUrl</span></span> | <span data-ttu-id="b58da-138">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-138">BadRequest (400)</span></span> | <span data-ttu-id="b58da-139">URL {不正確 URL} 無效。</span><span class="sxs-lookup"><span data-stu-id="b58da-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="b58da-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="b58da-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="b58da-141">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-141">BadRequest (400)</span></span> | <span data-ttu-id="b58da-142">超過批次大小上限。</span><span class="sxs-lookup"><span data-stu-id="b58da-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="b58da-143">已接收： {已接收的批次大小}，允許： {允許的批次大小}。</span><span class="sxs-lookup"><span data-stu-id="b58da-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="b58da-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="b58da-144">MissingRequiredParameter</span></span> | <span data-ttu-id="b58da-145">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-145">BadRequest (400)</span></span> | <span data-ttu-id="b58da-146">參數 {遺失的參數} 缺失。</span><span class="sxs-lookup"><span data-stu-id="b58da-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="b58da-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="b58da-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="b58da-148">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-148">BadRequest (400)</span></span> | <span data-ttu-id="b58da-149">作業系統平臺 {用戶端作業系統平臺} 不支援此動作。</span><span class="sxs-lookup"><span data-stu-id="b58da-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="b58da-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="b58da-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="b58da-151">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="b58da-151">BadRequest (400)</span></span> | <span data-ttu-id="b58da-152">{用戶端版本 {支援的用戶端版本} 和更新版本支援要求的動作}。</span><span class="sxs-lookup"><span data-stu-id="b58da-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="b58da-153">未經 授權</span><span class="sxs-lookup"><span data-stu-id="b58da-153">Unauthorized</span></span> | <span data-ttu-id="b58da-154">未經授權的 (401) </span><span class="sxs-lookup"><span data-stu-id="b58da-154">Unauthorized (401)</span></span> | <span data-ttu-id="b58da-155">未經授權的 (通常會無效或過期的授權標頭) 。</span><span class="sxs-lookup"><span data-stu-id="b58da-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="b58da-156">禁止</span><span class="sxs-lookup"><span data-stu-id="b58da-156">Forbidden</span></span> | <span data-ttu-id="b58da-157">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="b58da-157">Forbidden (403)</span></span> | <span data-ttu-id="b58da-158">已禁止 (有效的權杖，但動作) 的許可權不足。</span><span class="sxs-lookup"><span data-stu-id="b58da-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="b58da-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="b58da-159">DisabledFeature</span></span> | <span data-ttu-id="b58da-160">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="b58da-160">Forbidden (403)</span></span> | <span data-ttu-id="b58da-161">未啟用租使用者功能。</span><span class="sxs-lookup"><span data-stu-id="b58da-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="b58da-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="b58da-162">DisallowedOperation</span></span> | <span data-ttu-id="b58da-163">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="b58da-163">Forbidden (403)</span></span> | <span data-ttu-id="b58da-164">{不允許的作業及原因}。</span><span class="sxs-lookup"><span data-stu-id="b58da-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="b58da-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="b58da-165">NotFound</span></span> | <span data-ttu-id="b58da-166">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="b58da-166">Not Found (404)</span></span> | <span data-ttu-id="b58da-167">找不到一般錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b58da-167">General Not Found error message.</span></span>
<span data-ttu-id="b58da-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="b58da-168">ResourceNotFound</span></span> | <span data-ttu-id="b58da-169">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="b58da-169">Not Found (404)</span></span> | <span data-ttu-id="b58da-170">Resource {找不到要求的資源}。</span><span class="sxs-lookup"><span data-stu-id="b58da-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="b58da-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="b58da-171">InternalServerError</span></span> | <span data-ttu-id="b58da-172">內部伺服器錯誤 (500) </span><span class="sxs-lookup"><span data-stu-id="b58da-172">Internal Server Error (500)</span></span> | <span data-ttu-id="b58da-173"> (沒有錯誤訊息，請重試此作業，或與我們聯繫（如果它未解決）) </span><span class="sxs-lookup"><span data-stu-id="b58da-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="b58da-174">主體參數區分大小寫</span><span class="sxs-lookup"><span data-stu-id="b58da-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="b58da-175">提交的主體參數目前是區分大小寫的。</span><span class="sxs-lookup"><span data-stu-id="b58da-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="b58da-176">如果您遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 錯誤，這可能是由錯誤的參數大寫或小寫字母所導致。</span><span class="sxs-lookup"><span data-stu-id="b58da-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="b58da-177">建議您複查 API 檔頁面，並檢查提交的參數是否符合相關的範例。</span><span class="sxs-lookup"><span data-stu-id="b58da-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="b58da-178">關聯要求識別碼</span><span class="sxs-lookup"><span data-stu-id="b58da-178">Correlation request ID</span></span>

<span data-ttu-id="b58da-179">每個錯誤回應都包含一個用於追蹤的唯一識別碼參數。</span><span class="sxs-lookup"><span data-stu-id="b58da-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="b58da-180">此參數的屬性名稱為 "target"。</span><span class="sxs-lookup"><span data-stu-id="b58da-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="b58da-181">當您聯繫我們有關錯誤的資訊時，附加此識別碼會協助找出問題的根本原因。</span><span class="sxs-lookup"><span data-stu-id="b58da-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="b58da-182">範例</span><span class="sxs-lookup"><span data-stu-id="b58da-182">Examples</span></span>

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

