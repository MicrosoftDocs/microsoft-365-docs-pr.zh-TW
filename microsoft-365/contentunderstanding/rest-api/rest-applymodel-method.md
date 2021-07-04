---
title: 批次套用模型
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
description: 使用 REST API 將文件瞭解模型套用至一或多個程式庫。
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286534"
---
# <a name="batch-apply-model"></a><span data-ttu-id="6d296-103">批次套用模型</span><span class="sxs-lookup"><span data-stu-id="6d296-103">Batch Apply model</span></span>

<span data-ttu-id="6d296-104">將訓練過的文件瞭解模型套用 (或同步處理) 至一或多個文件庫 (查看[範例](rest-applymodel-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="6d296-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="6d296-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="6d296-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="6d296-106">URI 參數</span><span class="sxs-lookup"><span data-stu-id="6d296-106">URI parameters</span></span>

<span data-ttu-id="6d296-107">無</span><span class="sxs-lookup"><span data-stu-id="6d296-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="6d296-108">要求標頭</span><span class="sxs-lookup"><span data-stu-id="6d296-108">Request headers</span></span>

| <span data-ttu-id="6d296-109">頁首</span><span class="sxs-lookup"><span data-stu-id="6d296-109">Header</span></span> | <span data-ttu-id="6d296-110">值</span><span class="sxs-lookup"><span data-stu-id="6d296-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="6d296-111">Accept</span><span class="sxs-lookup"><span data-stu-id="6d296-111">Accept</span></span>|<span data-ttu-id="6d296-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="6d296-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="6d296-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6d296-113">Content-Type</span></span>|<span data-ttu-id="6d296-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="6d296-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="6d296-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="6d296-115">x-requestdigest</span></span>|<span data-ttu-id="6d296-116">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="6d296-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="6d296-117">要求內文</span><span class="sxs-lookup"><span data-stu-id="6d296-117">Request body</span></span>

| <span data-ttu-id="6d296-118">名稱</span><span class="sxs-lookup"><span data-stu-id="6d296-118">Name</span></span> | <span data-ttu-id="6d296-119">必要項目</span><span class="sxs-lookup"><span data-stu-id="6d296-119">Required</span></span> | <span data-ttu-id="6d296-120">類型</span><span class="sxs-lookup"><span data-stu-id="6d296-120">Type</span></span> | <span data-ttu-id="6d296-121">說明</span><span class="sxs-lookup"><span data-stu-id="6d296-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="6d296-122">__中繼資料</span><span class="sxs-lookup"><span data-stu-id="6d296-122">__metadata</span></span>|<span data-ttu-id="6d296-123">是</span><span class="sxs-lookup"><span data-stu-id="6d296-123">yes</span></span>|<span data-ttu-id="6d296-124">string</span><span class="sxs-lookup"><span data-stu-id="6d296-124">string</span></span>|<span data-ttu-id="6d296-125">在 SPO 上設定物件 Meta。</span><span class="sxs-lookup"><span data-stu-id="6d296-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="6d296-126">一律使用值: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}。</span><span class="sxs-lookup"><span data-stu-id="6d296-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="6d296-127">出版物</span><span class="sxs-lookup"><span data-stu-id="6d296-127">Publications</span></span>|<span data-ttu-id="6d296-128">是</span><span class="sxs-lookup"><span data-stu-id="6d296-128">yes</span></span>|<span data-ttu-id="6d296-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="6d296-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="6d296-130">MachineLearningPublicationEntityData 的集合，每個集合會指定模型和目的文件庫。</span><span class="sxs-lookup"><span data-stu-id="6d296-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="6d296-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="6d296-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="6d296-132">名稱</span><span class="sxs-lookup"><span data-stu-id="6d296-132">Name</span></span> | <span data-ttu-id="6d296-133">必要項目</span><span class="sxs-lookup"><span data-stu-id="6d296-133">Required</span></span> | <span data-ttu-id="6d296-134">類型</span><span class="sxs-lookup"><span data-stu-id="6d296-134">Type</span></span> | <span data-ttu-id="6d296-135">描述</span><span class="sxs-lookup"><span data-stu-id="6d296-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="6d296-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="6d296-136">ModelUniqueId</span></span>|<span data-ttu-id="6d296-137">是</span><span class="sxs-lookup"><span data-stu-id="6d296-137">yes</span></span>|<span data-ttu-id="6d296-138">string</span><span class="sxs-lookup"><span data-stu-id="6d296-138">string</span></span>|<span data-ttu-id="6d296-139">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="6d296-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="6d296-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="6d296-140">TargetSiteUrl</span></span>|<span data-ttu-id="6d296-141">是</span><span class="sxs-lookup"><span data-stu-id="6d296-141">yes</span></span>|<span data-ttu-id="6d296-142">string</span><span class="sxs-lookup"><span data-stu-id="6d296-142">string</span></span>|<span data-ttu-id="6d296-143">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="6d296-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="6d296-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6d296-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="6d296-145">是</span><span class="sxs-lookup"><span data-stu-id="6d296-145">yes</span></span>|<span data-ttu-id="6d296-146">string</span><span class="sxs-lookup"><span data-stu-id="6d296-146">string</span></span>|<span data-ttu-id="6d296-147">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="6d296-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="6d296-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6d296-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="6d296-149">是</span><span class="sxs-lookup"><span data-stu-id="6d296-149">yes</span></span>|<span data-ttu-id="6d296-150">string</span><span class="sxs-lookup"><span data-stu-id="6d296-150">string</span></span>|<span data-ttu-id="6d296-151">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="6d296-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="6d296-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="6d296-152">ViewOption</span></span>|<span data-ttu-id="6d296-153">否</span><span class="sxs-lookup"><span data-stu-id="6d296-153">no</span></span>|<span data-ttu-id="6d296-154">string</span><span class="sxs-lookup"><span data-stu-id="6d296-154">string</span></span>|<span data-ttu-id="6d296-155">指定是否要將新模型檢視設定為程式庫預設值。</span><span class="sxs-lookup"><span data-stu-id="6d296-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="6d296-156">回應</span><span class="sxs-lookup"><span data-stu-id="6d296-156">Response</span></span>

| <span data-ttu-id="6d296-157">名稱</span><span class="sxs-lookup"><span data-stu-id="6d296-157">Name</span></span>   | <span data-ttu-id="6d296-158">類型</span><span class="sxs-lookup"><span data-stu-id="6d296-158">Type</span></span>  | <span data-ttu-id="6d296-159">描述</span><span class="sxs-lookup"><span data-stu-id="6d296-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6d296-160">201 已建立</span><span class="sxs-lookup"><span data-stu-id="6d296-160">201 Created</span></span>||<span data-ttu-id="6d296-p102">這是自訂的 API，用來支援套用模型至多個文件庫。在部分成功的情況下，仍可以傳回 201 已建立，而且呼叫者必須檢查回應內文，以了解是否已成功將模型套用至文件庫。</span><span class="sxs-lookup"><span data-stu-id="6d296-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="6d296-163">回應本文</span><span class="sxs-lookup"><span data-stu-id="6d296-163">Response Body</span></span>

| <span data-ttu-id="6d296-164">名稱</span><span class="sxs-lookup"><span data-stu-id="6d296-164">Name</span></span>   | <span data-ttu-id="6d296-165">類型</span><span class="sxs-lookup"><span data-stu-id="6d296-165">Type</span></span>  | <span data-ttu-id="6d296-166">說明</span><span class="sxs-lookup"><span data-stu-id="6d296-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6d296-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="6d296-167">TotalSuccesses</span></span>|<span data-ttu-id="6d296-168">int</span><span class="sxs-lookup"><span data-stu-id="6d296-168">int</span></span>|<span data-ttu-id="6d296-169">成功套用至文件庫的模型總數。</span><span class="sxs-lookup"><span data-stu-id="6d296-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="6d296-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="6d296-170">TotalFailures</span></span>|<span data-ttu-id="6d296-171">int</span><span class="sxs-lookup"><span data-stu-id="6d296-171">int</span></span>|<span data-ttu-id="6d296-172">無法套用至文件庫的模型總數。</span><span class="sxs-lookup"><span data-stu-id="6d296-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="6d296-173">詳細資料</span><span class="sxs-lookup"><span data-stu-id="6d296-173">Details</span></span>|<span data-ttu-id="6d296-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="6d296-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="6d296-175">MachineLearningPublicationResult 的集合，每個集合會指定將模型套用至文件庫的詳細結果。</span><span class="sxs-lookup"><span data-stu-id="6d296-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="6d296-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="6d296-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="6d296-177">名稱</span><span class="sxs-lookup"><span data-stu-id="6d296-177">Name</span></span>   | <span data-ttu-id="6d296-178">類型</span><span class="sxs-lookup"><span data-stu-id="6d296-178">Type</span></span>  | <span data-ttu-id="6d296-179">說明</span><span class="sxs-lookup"><span data-stu-id="6d296-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6d296-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="6d296-180">StatusCode</span></span>|<span data-ttu-id="6d296-181">int</span><span class="sxs-lookup"><span data-stu-id="6d296-181">int</span></span>|<span data-ttu-id="6d296-182">HTTP 狀態碼。</span><span class="sxs-lookup"><span data-stu-id="6d296-182">The HTTP status code.</span></span>|
|<span data-ttu-id="6d296-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="6d296-183">ErrorMessage</span></span>|<span data-ttu-id="6d296-184">字串</span><span class="sxs-lookup"><span data-stu-id="6d296-184">string</span></span>|<span data-ttu-id="6d296-185">錯誤訊息，說明將模型套用至文件庫時發生的錯誤。</span><span class="sxs-lookup"><span data-stu-id="6d296-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="6d296-186">出版物</span><span class="sxs-lookup"><span data-stu-id="6d296-186">Publication</span></span>|<span data-ttu-id="6d296-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="6d296-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="6d296-188">它會指定模型資訊和目的文件庫。</span><span class="sxs-lookup"><span data-stu-id="6d296-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="6d296-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="6d296-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="6d296-190">名稱</span><span class="sxs-lookup"><span data-stu-id="6d296-190">Name</span></span> | <span data-ttu-id="6d296-191">類型</span><span class="sxs-lookup"><span data-stu-id="6d296-191">Type</span></span> | <span data-ttu-id="6d296-192">描述</span><span class="sxs-lookup"><span data-stu-id="6d296-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="6d296-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="6d296-193">ModelUniqueId</span></span>|<span data-ttu-id="6d296-194">string</span><span class="sxs-lookup"><span data-stu-id="6d296-194">string</span></span>|<span data-ttu-id="6d296-195">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="6d296-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="6d296-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="6d296-196">TargetSiteUrl</span></span>|<span data-ttu-id="6d296-197">string</span><span class="sxs-lookup"><span data-stu-id="6d296-197">string</span></span>|<span data-ttu-id="6d296-198">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="6d296-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="6d296-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6d296-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="6d296-200">string</span><span class="sxs-lookup"><span data-stu-id="6d296-200">string</span></span>|<span data-ttu-id="6d296-201">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="6d296-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="6d296-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="6d296-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="6d296-203">string</span><span class="sxs-lookup"><span data-stu-id="6d296-203">string</span></span>|<span data-ttu-id="6d296-204">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="6d296-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="6d296-205">範例</span><span class="sxs-lookup"><span data-stu-id="6d296-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="6d296-206">將模型套用至存放庫網站中的合約文件庫</span><span class="sxs-lookup"><span data-stu-id="6d296-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="6d296-207">在此範例中，Contoso 合約文件了解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="6d296-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="6d296-208">範例要求</span><span class="sxs-lookup"><span data-stu-id="6d296-208">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="6d296-209">範例回應</span><span class="sxs-lookup"><span data-stu-id="6d296-209">Sample response</span></span>

<span data-ttu-id="6d296-210">在回應中，TotalFailures 和 TotalSuccesses 是指要套用至指定程式庫之模型的失敗和成功次數。</span><span class="sxs-lookup"><span data-stu-id="6d296-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="6d296-211">**狀態碼:** 201</span><span class="sxs-lookup"><span data-stu-id="6d296-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="6d296-212">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6d296-212">See also</span></span>

[<span data-ttu-id="6d296-213">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="6d296-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
