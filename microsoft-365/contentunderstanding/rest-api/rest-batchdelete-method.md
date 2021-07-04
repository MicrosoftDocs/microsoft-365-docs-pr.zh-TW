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
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287450"
---
# <a name="batchdelete"></a><span data-ttu-id="13327-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="13327-103">BatchDelete</span></span>

<span data-ttu-id="13327-104">從一或多個程式庫移除已套用的文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="13327-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="13327-105">請注意，必須先從所有程式庫移除模型，才能刪除模型 (請參閱[範例](rest-batchdelete-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="13327-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="13327-106">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="13327-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="13327-107">URI 參數</span><span class="sxs-lookup"><span data-stu-id="13327-107">URI parameters</span></span>

<span data-ttu-id="13327-108">無</span><span class="sxs-lookup"><span data-stu-id="13327-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="13327-109">要求標頭</span><span class="sxs-lookup"><span data-stu-id="13327-109">Request headers</span></span>

| <span data-ttu-id="13327-110">頁首</span><span class="sxs-lookup"><span data-stu-id="13327-110">Header</span></span> | <span data-ttu-id="13327-111">值</span><span class="sxs-lookup"><span data-stu-id="13327-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="13327-112">Accept</span><span class="sxs-lookup"><span data-stu-id="13327-112">Accept</span></span>|<span data-ttu-id="13327-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="13327-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="13327-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="13327-114">Content-Type</span></span>|<span data-ttu-id="13327-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="13327-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="13327-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="13327-116">x-requestdigest</span></span>|<span data-ttu-id="13327-117">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="13327-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="13327-118">要求內文</span><span class="sxs-lookup"><span data-stu-id="13327-118">Request body</span></span>

| <span data-ttu-id="13327-119">名稱</span><span class="sxs-lookup"><span data-stu-id="13327-119">Name</span></span> | <span data-ttu-id="13327-120">必要項目</span><span class="sxs-lookup"><span data-stu-id="13327-120">Required</span></span> | <span data-ttu-id="13327-121">類型</span><span class="sxs-lookup"><span data-stu-id="13327-121">Type</span></span> | <span data-ttu-id="13327-122">說明</span><span class="sxs-lookup"><span data-stu-id="13327-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="13327-123">出版物</span><span class="sxs-lookup"><span data-stu-id="13327-123">Publications</span></span>|<span data-ttu-id="13327-124">是</span><span class="sxs-lookup"><span data-stu-id="13327-124">yes</span></span>|<span data-ttu-id="13327-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="13327-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="13327-126">MachineLearningPublicationEntityData 的集合，每個集合會指定模型和目的文件庫。</span><span class="sxs-lookup"><span data-stu-id="13327-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="13327-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="13327-127">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="13327-128">名稱</span><span class="sxs-lookup"><span data-stu-id="13327-128">Name</span></span> | <span data-ttu-id="13327-129">必要項目</span><span class="sxs-lookup"><span data-stu-id="13327-129">Required</span></span> | <span data-ttu-id="13327-130">類型</span><span class="sxs-lookup"><span data-stu-id="13327-130">Type</span></span> | <span data-ttu-id="13327-131">描述</span><span class="sxs-lookup"><span data-stu-id="13327-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="13327-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="13327-132">ModelUniqueId</span></span>|<span data-ttu-id="13327-133">是</span><span class="sxs-lookup"><span data-stu-id="13327-133">yes</span></span>|<span data-ttu-id="13327-134">string</span><span class="sxs-lookup"><span data-stu-id="13327-134">string</span></span>|<span data-ttu-id="13327-135">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="13327-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="13327-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="13327-136">TargetSiteUrl</span></span>|<span data-ttu-id="13327-137">是</span><span class="sxs-lookup"><span data-stu-id="13327-137">yes</span></span>|<span data-ttu-id="13327-138">string</span><span class="sxs-lookup"><span data-stu-id="13327-138">string</span></span>|<span data-ttu-id="13327-139">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="13327-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="13327-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="13327-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="13327-141">是</span><span class="sxs-lookup"><span data-stu-id="13327-141">yes</span></span>|<span data-ttu-id="13327-142">string</span><span class="sxs-lookup"><span data-stu-id="13327-142">string</span></span>|<span data-ttu-id="13327-143">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="13327-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="13327-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="13327-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="13327-145">是</span><span class="sxs-lookup"><span data-stu-id="13327-145">yes</span></span>|<span data-ttu-id="13327-146">string</span><span class="sxs-lookup"><span data-stu-id="13327-146">string</span></span>|<span data-ttu-id="13327-147">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="13327-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="13327-148">回應</span><span class="sxs-lookup"><span data-stu-id="13327-148">Response</span></span>

| <span data-ttu-id="13327-149">名稱</span><span class="sxs-lookup"><span data-stu-id="13327-149">Name</span></span>   | <span data-ttu-id="13327-150">類型</span><span class="sxs-lookup"><span data-stu-id="13327-150">Type</span></span>  | <span data-ttu-id="13327-151">描述</span><span class="sxs-lookup"><span data-stu-id="13327-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="13327-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="13327-152">200 OK</span></span>||<span data-ttu-id="13327-p102">這是自訂的 API，用來支援從多個文件庫移除模型。在部分成功的情況下，仍可以傳回 200 OK，而且呼叫者必須檢查回應內文，以了解是否已成功從文件庫移除模型。</span><span class="sxs-lookup"><span data-stu-id="13327-p102">This is a customized API to support removing a model from multi document libraries. In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="13327-155">回應本文</span><span class="sxs-lookup"><span data-stu-id="13327-155">Response Body</span></span>

| <span data-ttu-id="13327-156">名稱</span><span class="sxs-lookup"><span data-stu-id="13327-156">Name</span></span>   | <span data-ttu-id="13327-157">類型</span><span class="sxs-lookup"><span data-stu-id="13327-157">Type</span></span>  | <span data-ttu-id="13327-158">說明</span><span class="sxs-lookup"><span data-stu-id="13327-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="13327-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="13327-159">TotalSuccesses</span></span>|<span data-ttu-id="13327-160">int</span><span class="sxs-lookup"><span data-stu-id="13327-160">int</span></span>|<span data-ttu-id="13327-161">成功從文件庫移除的模型總數。</span><span class="sxs-lookup"><span data-stu-id="13327-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="13327-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="13327-162">TotalFailures</span></span>|<span data-ttu-id="13327-163">int</span><span class="sxs-lookup"><span data-stu-id="13327-163">int</span></span>|<span data-ttu-id="13327-164">無法從文件庫中移除的模型總數。</span><span class="sxs-lookup"><span data-stu-id="13327-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="13327-165">詳細資料</span><span class="sxs-lookup"><span data-stu-id="13327-165">Details</span></span>|<span data-ttu-id="13327-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="13327-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="13327-167">MachineLearningPublicationResult 的集合，每個集合會指定將模型從文件庫中移除的詳細結果。</span><span class="sxs-lookup"><span data-stu-id="13327-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="13327-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="13327-168">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="13327-169">名稱</span><span class="sxs-lookup"><span data-stu-id="13327-169">Name</span></span>   | <span data-ttu-id="13327-170">類型</span><span class="sxs-lookup"><span data-stu-id="13327-170">Type</span></span>  | <span data-ttu-id="13327-171">說明</span><span class="sxs-lookup"><span data-stu-id="13327-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="13327-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="13327-172">StatusCode</span></span>|<span data-ttu-id="13327-173">int</span><span class="sxs-lookup"><span data-stu-id="13327-173">int</span></span>|<span data-ttu-id="13327-174">HTTP 狀態碼。</span><span class="sxs-lookup"><span data-stu-id="13327-174">The HTTP status code.</span></span>|
|<span data-ttu-id="13327-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="13327-175">ErrorMessage</span></span>|<span data-ttu-id="13327-176">字串</span><span class="sxs-lookup"><span data-stu-id="13327-176">string</span></span>|<span data-ttu-id="13327-177">錯誤訊息，說明將模型套用至文件庫時發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="13327-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="13327-178">出版物</span><span class="sxs-lookup"><span data-stu-id="13327-178">Publication</span></span>|<span data-ttu-id="13327-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="13327-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="13327-180">它會指定模型資訊和目的文件庫。</span><span class="sxs-lookup"><span data-stu-id="13327-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="13327-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="13327-181">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="13327-182">名稱</span><span class="sxs-lookup"><span data-stu-id="13327-182">Name</span></span> | <span data-ttu-id="13327-183">類型</span><span class="sxs-lookup"><span data-stu-id="13327-183">Type</span></span> | <span data-ttu-id="13327-184">描述</span><span class="sxs-lookup"><span data-stu-id="13327-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="13327-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="13327-185">ModelUniqueId</span></span>|<span data-ttu-id="13327-186">string</span><span class="sxs-lookup"><span data-stu-id="13327-186">string</span></span>|<span data-ttu-id="13327-187">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="13327-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="13327-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="13327-188">TargetSiteUrl</span></span>|<span data-ttu-id="13327-189">string</span><span class="sxs-lookup"><span data-stu-id="13327-189">string</span></span>|<span data-ttu-id="13327-190">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="13327-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="13327-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="13327-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="13327-192">string</span><span class="sxs-lookup"><span data-stu-id="13327-192">string</span></span>|<span data-ttu-id="13327-193">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="13327-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="13327-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="13327-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="13327-195">string</span><span class="sxs-lookup"><span data-stu-id="13327-195">string</span></span>|<span data-ttu-id="13327-196">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="13327-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="13327-197">範例</span><span class="sxs-lookup"><span data-stu-id="13327-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="13327-198">從存放庫網站中的合約文件庫移除模型</span><span class="sxs-lookup"><span data-stu-id="13327-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="13327-199">在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="13327-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="13327-200">範例要求</span><span class="sxs-lookup"><span data-stu-id="13327-200">Sample request</span></span>

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

#### <a name="sample-response"></a><span data-ttu-id="13327-201">範例回應</span><span class="sxs-lookup"><span data-stu-id="13327-201">Sample response</span></span>

<span data-ttu-id="13327-202">在回應中，TotalFailures 和 TotalSuccesses 是指從指定程式庫中移除之模型的失敗和成功次數。</span><span class="sxs-lookup"><span data-stu-id="13327-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="13327-203">**狀態碼：** 200</span><span class="sxs-lookup"><span data-stu-id="13327-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="13327-204">另請參閱</span><span class="sxs-lookup"><span data-stu-id="13327-204">See also</span></span>

[<span data-ttu-id="13327-205">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="13327-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
