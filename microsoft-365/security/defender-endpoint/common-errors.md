---
title: 常見 Microsoft Defender for Endpoint API 錯誤
description: 使用說明的常見 Microsoft Defender 的端點 API 錯誤清單。
keywords: api、mdatp api、錯誤、疑難排解
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fc2aeb6ee5a95f7eb121abdcf4431dc6d34cd49
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893458"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="9eafa-104">常見的 REST API 錯誤碼</span><span class="sxs-lookup"><span data-stu-id="9eafa-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="9eafa-105">下表所列的錯誤碼可能會由任何 Microsoft Defender for Endpoint APIs 上的操作所傳回。</span><span class="sxs-lookup"><span data-stu-id="9eafa-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="9eafa-106">除了錯誤碼之外，每個錯誤回應都會包含錯誤訊息，可協助您解決問題。</span><span class="sxs-lookup"><span data-stu-id="9eafa-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="9eafa-107">郵件是可變更的普通文字。</span><span class="sxs-lookup"><span data-stu-id="9eafa-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="9eafa-108">在頁面底部，您可以找到回應範例。</span><span class="sxs-lookup"><span data-stu-id="9eafa-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="9eafa-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="9eafa-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9eafa-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="9eafa-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="9eafa-111">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="9eafa-111">Error code</span></span> |<span data-ttu-id="9eafa-112">HTTP 狀態碼</span><span class="sxs-lookup"><span data-stu-id="9eafa-112">HTTP status code</span></span> |<span data-ttu-id="9eafa-113">訊息</span><span class="sxs-lookup"><span data-stu-id="9eafa-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="9eafa-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="9eafa-114">BadRequest</span></span> | <span data-ttu-id="9eafa-115">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-115">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-116">一般錯誤要求錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="9eafa-116">General Bad Request error message.</span></span>
<span data-ttu-id="9eafa-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="9eafa-117">ODataError</span></span> | <span data-ttu-id="9eafa-118">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-118">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-119">OData URI 查詢無效 () 指定特定錯誤。</span><span class="sxs-lookup"><span data-stu-id="9eafa-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="9eafa-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="9eafa-120">InvalidInput</span></span> | <span data-ttu-id="9eafa-121">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-121">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-122">不正確輸入 {不正確輸入}。</span><span class="sxs-lookup"><span data-stu-id="9eafa-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="9eafa-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="9eafa-123">InvalidRequestBody</span></span> | <span data-ttu-id="9eafa-124">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-124">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-125">不正確要求正文。</span><span class="sxs-lookup"><span data-stu-id="9eafa-125">Invalid request body.</span></span>
<span data-ttu-id="9eafa-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="9eafa-126">InvalidHashValue</span></span> | <span data-ttu-id="9eafa-127">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-127">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-128">雜湊值 {不正確雜湊} 無效。</span><span class="sxs-lookup"><span data-stu-id="9eafa-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="9eafa-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="9eafa-129">InvalidDomainName</span></span> | <span data-ttu-id="9eafa-130">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-130">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-131">功能變數名稱 {不正確網域} 無效。</span><span class="sxs-lookup"><span data-stu-id="9eafa-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="9eafa-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="9eafa-132">InvalidIpAddress</span></span> | <span data-ttu-id="9eafa-133">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-133">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-134">IP 位址 {不正確 IP} 無效。</span><span class="sxs-lookup"><span data-stu-id="9eafa-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="9eafa-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="9eafa-135">InvalidUrl</span></span> | <span data-ttu-id="9eafa-136">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-136">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-137">URL {不正確 URL} 無效。</span><span class="sxs-lookup"><span data-stu-id="9eafa-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="9eafa-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="9eafa-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="9eafa-139">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-139">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-140">超過批次大小上限。</span><span class="sxs-lookup"><span data-stu-id="9eafa-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="9eafa-141">已接收： {已接收的批次大小}，允許： {允許的批次大小}。</span><span class="sxs-lookup"><span data-stu-id="9eafa-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="9eafa-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="9eafa-142">MissingRequiredParameter</span></span> | <span data-ttu-id="9eafa-143">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-143">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-144">參數 {遺失的參數} 缺失。</span><span class="sxs-lookup"><span data-stu-id="9eafa-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="9eafa-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="9eafa-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="9eafa-146">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-146">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-147">作業系統平臺 {用戶端作業系統平臺} 不支援此動作。</span><span class="sxs-lookup"><span data-stu-id="9eafa-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="9eafa-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="9eafa-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="9eafa-149">BadRequest (400) </span><span class="sxs-lookup"><span data-stu-id="9eafa-149">BadRequest (400)</span></span> | <span data-ttu-id="9eafa-150">{用戶端版本 {支援的用戶端版本} 和更新版本支援要求的動作}。</span><span class="sxs-lookup"><span data-stu-id="9eafa-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="9eafa-151">未經 授權</span><span class="sxs-lookup"><span data-stu-id="9eafa-151">Unauthorized</span></span> | <span data-ttu-id="9eafa-152">未經授權的 (401) </span><span class="sxs-lookup"><span data-stu-id="9eafa-152">Unauthorized (401)</span></span> | <span data-ttu-id="9eafa-153">未授權 (無效或過期的授權標頭) 。</span><span class="sxs-lookup"><span data-stu-id="9eafa-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="9eafa-154">禁止</span><span class="sxs-lookup"><span data-stu-id="9eafa-154">Forbidden</span></span> | <span data-ttu-id="9eafa-155">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="9eafa-155">Forbidden (403)</span></span> | <span data-ttu-id="9eafa-156">已禁止 (有效的權杖，但動作) 的許可權不足。</span><span class="sxs-lookup"><span data-stu-id="9eafa-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="9eafa-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="9eafa-157">DisabledFeature</span></span> | <span data-ttu-id="9eafa-158">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="9eafa-158">Forbidden (403)</span></span> | <span data-ttu-id="9eafa-159">未啟用租使用者功能。</span><span class="sxs-lookup"><span data-stu-id="9eafa-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="9eafa-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="9eafa-160">DisallowedOperation</span></span> | <span data-ttu-id="9eafa-161">禁止 (403) </span><span class="sxs-lookup"><span data-stu-id="9eafa-161">Forbidden (403)</span></span> | <span data-ttu-id="9eafa-162">{不允許的作業及原因}。</span><span class="sxs-lookup"><span data-stu-id="9eafa-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="9eafa-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="9eafa-163">NotFound</span></span> | <span data-ttu-id="9eafa-164">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="9eafa-164">Not Found (404)</span></span> | <span data-ttu-id="9eafa-165">找不到一般錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="9eafa-165">General Not Found error message.</span></span>
<span data-ttu-id="9eafa-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="9eafa-166">ResourceNotFound</span></span> | <span data-ttu-id="9eafa-167">找不到 (404) </span><span class="sxs-lookup"><span data-stu-id="9eafa-167">Not Found (404)</span></span> | <span data-ttu-id="9eafa-168">Resource {找不到要求的資源}。</span><span class="sxs-lookup"><span data-stu-id="9eafa-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="9eafa-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="9eafa-169">InternalServerError</span></span> | <span data-ttu-id="9eafa-170">內部伺服器錯誤 (500) </span><span class="sxs-lookup"><span data-stu-id="9eafa-170">Internal Server Error (500)</span></span> | <span data-ttu-id="9eafa-171"> (無錯誤訊息，請重試作業) </span><span class="sxs-lookup"><span data-stu-id="9eafa-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="9eafa-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="9eafa-172">TooManyRequests</span></span> | <span data-ttu-id="9eafa-173"> (429 的要求太多) </span><span class="sxs-lookup"><span data-stu-id="9eafa-173">Too Many Requests (429)</span></span> | <span data-ttu-id="9eafa-174">回應會以要求數目或 CPU 來表示達到配額限制。</span><span class="sxs-lookup"><span data-stu-id="9eafa-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="9eafa-175">主體參數區分大小寫</span><span class="sxs-lookup"><span data-stu-id="9eafa-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="9eafa-176">提交的主體參數目前是區分大小寫的。</span><span class="sxs-lookup"><span data-stu-id="9eafa-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="9eafa-177">如果您遇到 **InvalidRequestBody** 或 **MissingRequiredParameter** 錯誤，這可能是由錯誤的參數大寫或小寫字母所導致。</span><span class="sxs-lookup"><span data-stu-id="9eafa-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="9eafa-178">請參閱 API 檔頁面，並檢查提交的參數是否符合相關的範例。</span><span class="sxs-lookup"><span data-stu-id="9eafa-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="9eafa-179">關聯要求識別碼</span><span class="sxs-lookup"><span data-stu-id="9eafa-179">Correlation request ID</span></span>

<span data-ttu-id="9eafa-180">每個錯誤回應都包含一個用於追蹤的唯一識別碼參數。</span><span class="sxs-lookup"><span data-stu-id="9eafa-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="9eafa-181">此參數的屬性名稱為 "target"。</span><span class="sxs-lookup"><span data-stu-id="9eafa-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="9eafa-182">當您聯繫我們有關錯誤的資訊時，附加此識別碼會協助找出問題的根本原因。</span><span class="sxs-lookup"><span data-stu-id="9eafa-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="9eafa-183">範例</span><span class="sxs-lookup"><span data-stu-id="9eafa-183">Examples</span></span>

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
