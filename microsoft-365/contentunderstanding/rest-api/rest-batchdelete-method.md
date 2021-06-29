---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: 使用 REST API 從一或多個程式庫移除已套用的文件瞭解模型。
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177234"
---
# <a name="batchdelete"></a><span data-ttu-id="f8c77-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="f8c77-103">BatchDelete</span></span>

<span data-ttu-id="f8c77-104">從一或多個程式庫移除已套用的文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="f8c77-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="f8c77-105">請注意，必須先從所有程式庫移除模型，才能刪除模型 (請參閱[範例](rest-batchdelete-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="f8c77-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="f8c77-106">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f8c77-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="f8c77-107">URI 參數</span><span class="sxs-lookup"><span data-stu-id="f8c77-107">URI parameters</span></span>

<span data-ttu-id="f8c77-108">無</span><span class="sxs-lookup"><span data-stu-id="f8c77-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="f8c77-109">要求標頭</span><span class="sxs-lookup"><span data-stu-id="f8c77-109">Request headers</span></span>

| <span data-ttu-id="f8c77-110">標頭</span><span class="sxs-lookup"><span data-stu-id="f8c77-110">Header</span></span> | <span data-ttu-id="f8c77-111">值</span><span class="sxs-lookup"><span data-stu-id="f8c77-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="f8c77-112">Accept</span><span class="sxs-lookup"><span data-stu-id="f8c77-112">Accept</span></span>|<span data-ttu-id="f8c77-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="f8c77-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="f8c77-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f8c77-114">Content-Type</span></span>|<span data-ttu-id="f8c77-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="f8c77-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="f8c77-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="f8c77-116">x-requestdigest</span></span>|<span data-ttu-id="f8c77-117">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="f8c77-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="f8c77-118">要求內文</span><span class="sxs-lookup"><span data-stu-id="f8c77-118">Request body</span></span>

| <span data-ttu-id="f8c77-119">名稱</span><span class="sxs-lookup"><span data-stu-id="f8c77-119">Name</span></span> | <span data-ttu-id="f8c77-120">必要項目</span><span class="sxs-lookup"><span data-stu-id="f8c77-120">Required</span></span> | <span data-ttu-id="f8c77-121">類型</span><span class="sxs-lookup"><span data-stu-id="f8c77-121">Type</span></span> | <span data-ttu-id="f8c77-122">說明</span><span class="sxs-lookup"><span data-stu-id="f8c77-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="f8c77-123">出版物</span><span class="sxs-lookup"><span data-stu-id="f8c77-123">Publications</span></span>|<span data-ttu-id="f8c77-124">是</span><span class="sxs-lookup"><span data-stu-id="f8c77-124">yes</span></span>|<span data-ttu-id="f8c77-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="f8c77-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="f8c77-126">MachineLearningPublicationEntityData 的集合，每個集合會指定模型和目的文件庫。</span><span class="sxs-lookup"><span data-stu-id="f8c77-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="f8c77-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="f8c77-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="f8c77-128">名稱</span><span class="sxs-lookup"><span data-stu-id="f8c77-128">Name</span></span> | <span data-ttu-id="f8c77-129">必要項目</span><span class="sxs-lookup"><span data-stu-id="f8c77-129">Required</span></span> | <span data-ttu-id="f8c77-130">類型</span><span class="sxs-lookup"><span data-stu-id="f8c77-130">Type</span></span> | <span data-ttu-id="f8c77-131">描述</span><span class="sxs-lookup"><span data-stu-id="f8c77-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="f8c77-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="f8c77-132">ModelUniqueId</span></span>|<span data-ttu-id="f8c77-133">是</span><span class="sxs-lookup"><span data-stu-id="f8c77-133">yes</span></span>|<span data-ttu-id="f8c77-134">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-134">string</span></span>|<span data-ttu-id="f8c77-135">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8c77-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="f8c77-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="f8c77-136">TargetSiteUrl</span></span>|<span data-ttu-id="f8c77-137">是</span><span class="sxs-lookup"><span data-stu-id="f8c77-137">yes</span></span>|<span data-ttu-id="f8c77-138">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-138">string</span></span>|<span data-ttu-id="f8c77-139">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="f8c77-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="f8c77-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="f8c77-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="f8c77-141">是</span><span class="sxs-lookup"><span data-stu-id="f8c77-141">yes</span></span>|<span data-ttu-id="f8c77-142">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-142">string</span></span>|<span data-ttu-id="f8c77-143">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="f8c77-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="f8c77-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="f8c77-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="f8c77-145">是</span><span class="sxs-lookup"><span data-stu-id="f8c77-145">yes</span></span>|<span data-ttu-id="f8c77-146">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-146">string</span></span>|<span data-ttu-id="f8c77-147">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="f8c77-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="f8c77-148">回應</span><span class="sxs-lookup"><span data-stu-id="f8c77-148">Response</span></span>

| <span data-ttu-id="f8c77-149">名稱</span><span class="sxs-lookup"><span data-stu-id="f8c77-149">Name</span></span>   | <span data-ttu-id="f8c77-150">類型</span><span class="sxs-lookup"><span data-stu-id="f8c77-150">Type</span></span>  | <span data-ttu-id="f8c77-151">描述</span><span class="sxs-lookup"><span data-stu-id="f8c77-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="f8c77-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="f8c77-152">200 OK</span></span>||<span data-ttu-id="f8c77-153">這是個自訂 API 用以將模型從多個文件庫中移除。</span><span class="sxs-lookup"><span data-stu-id="f8c77-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="f8c77-154">在部分成功的情況下，仍然可以返回 200 OK，而且呼叫者必須檢查回應本文，以了解模型是否成功從文件庫移除。</span><span class="sxs-lookup"><span data-stu-id="f8c77-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="f8c77-155">回應本文</span><span class="sxs-lookup"><span data-stu-id="f8c77-155">Response Body</span></span>
| <span data-ttu-id="f8c77-156">名稱</span><span class="sxs-lookup"><span data-stu-id="f8c77-156">Name</span></span>   | <span data-ttu-id="f8c77-157">類型</span><span class="sxs-lookup"><span data-stu-id="f8c77-157">Type</span></span>  | <span data-ttu-id="f8c77-158">說明</span><span class="sxs-lookup"><span data-stu-id="f8c77-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="f8c77-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="f8c77-159">TotalSuccesses</span></span>|<span data-ttu-id="f8c77-160">int</span><span class="sxs-lookup"><span data-stu-id="f8c77-160">int</span></span>|<span data-ttu-id="f8c77-161">成功從文件庫移除的模型總數。</span><span class="sxs-lookup"><span data-stu-id="f8c77-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="f8c77-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="f8c77-162">TotalFailures</span></span>|<span data-ttu-id="f8c77-163">int</span><span class="sxs-lookup"><span data-stu-id="f8c77-163">int</span></span>|<span data-ttu-id="f8c77-164">無法從文件庫中移除的模型總數。</span><span class="sxs-lookup"><span data-stu-id="f8c77-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="f8c77-165">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f8c77-165">Details</span></span>|<span data-ttu-id="f8c77-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="f8c77-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="f8c77-167">MachineLearningPublicationResult 的集合，每個集合會指定將模型從文件庫中移除的詳細結果。</span><span class="sxs-lookup"><span data-stu-id="f8c77-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="f8c77-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="f8c77-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="f8c77-169">名稱</span><span class="sxs-lookup"><span data-stu-id="f8c77-169">Name</span></span>   | <span data-ttu-id="f8c77-170">類型</span><span class="sxs-lookup"><span data-stu-id="f8c77-170">Type</span></span>  | <span data-ttu-id="f8c77-171">說明</span><span class="sxs-lookup"><span data-stu-id="f8c77-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="f8c77-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="f8c77-172">StatusCode</span></span>|<span data-ttu-id="f8c77-173">int</span><span class="sxs-lookup"><span data-stu-id="f8c77-173">int</span></span>|<span data-ttu-id="f8c77-174">HTTP 狀態碼。</span><span class="sxs-lookup"><span data-stu-id="f8c77-174">The HTTP status code.</span></span>|
|<span data-ttu-id="f8c77-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="f8c77-175">ErrorMessage</span></span>|<span data-ttu-id="f8c77-176">字串</span><span class="sxs-lookup"><span data-stu-id="f8c77-176">string</span></span>|<span data-ttu-id="f8c77-177">錯誤訊息，說明將模型套用至文件庫時發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="f8c77-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="f8c77-178">出版物</span><span class="sxs-lookup"><span data-stu-id="f8c77-178">Publication</span></span>|<span data-ttu-id="f8c77-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="f8c77-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="f8c77-180">它會指定模型資訊和目的文件庫。</span><span class="sxs-lookup"><span data-stu-id="f8c77-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="f8c77-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="f8c77-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="f8c77-182">名稱</span><span class="sxs-lookup"><span data-stu-id="f8c77-182">Name</span></span> | <span data-ttu-id="f8c77-183">類型</span><span class="sxs-lookup"><span data-stu-id="f8c77-183">Type</span></span> | <span data-ttu-id="f8c77-184">描述</span><span class="sxs-lookup"><span data-stu-id="f8c77-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="f8c77-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="f8c77-185">ModelUniqueId</span></span>|<span data-ttu-id="f8c77-186">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-186">string</span></span>|<span data-ttu-id="f8c77-187">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f8c77-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="f8c77-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="f8c77-188">TargetSiteUrl</span></span>|<span data-ttu-id="f8c77-189">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-189">string</span></span>|<span data-ttu-id="f8c77-190">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="f8c77-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="f8c77-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="f8c77-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="f8c77-192">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-192">string</span></span>|<span data-ttu-id="f8c77-193">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="f8c77-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="f8c77-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="f8c77-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="f8c77-195">string</span><span class="sxs-lookup"><span data-stu-id="f8c77-195">string</span></span>|<span data-ttu-id="f8c77-196">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="f8c77-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="f8c77-197">範例</span><span class="sxs-lookup"><span data-stu-id="f8c77-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="f8c77-198">從存放庫網站中的合約文件庫移除模型</span><span class="sxs-lookup"><span data-stu-id="f8c77-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="f8c77-199">在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="f8c77-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="f8c77-200">範例要求</span><span class="sxs-lookup"><span data-stu-id="f8c77-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="f8c77-201">範例回應</span><span class="sxs-lookup"><span data-stu-id="f8c77-201">Sample response</span></span>

<span data-ttu-id="f8c77-202">在回應中，TotalFailures 和 TotalSuccesses 是指從指定程式庫中移除之模型的失敗和成功次數。</span><span class="sxs-lookup"><span data-stu-id="f8c77-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="f8c77-203">**狀態碼：** 200</span><span class="sxs-lookup"><span data-stu-id="f8c77-203">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="f8c77-204">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f8c77-204">See also</span></span>

[<span data-ttu-id="f8c77-205">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="f8c77-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
