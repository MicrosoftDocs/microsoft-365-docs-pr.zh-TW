---
title: 套用模型
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
description: 使用 REST API 將文件了解模型套用至一或多個文件庫。
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904205"
---
# <a name="apply-model"></a><span data-ttu-id="1fe57-103">套用模型</span><span class="sxs-lookup"><span data-stu-id="1fe57-103">Apply model</span></span>

<span data-ttu-id="1fe57-104">將訓練過的文件瞭解模型套用 (或同步處理) 至一或多個文件庫 (查看[範例](rest-applymodel-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="1fe57-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="1fe57-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1fe57-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="1fe57-106">URI 參數</span><span class="sxs-lookup"><span data-stu-id="1fe57-106">URI parameters</span></span>

<span data-ttu-id="1fe57-107">無</span><span class="sxs-lookup"><span data-stu-id="1fe57-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="1fe57-108">要求標頭</span><span class="sxs-lookup"><span data-stu-id="1fe57-108">Request headers</span></span>

| <span data-ttu-id="1fe57-109">頁首</span><span class="sxs-lookup"><span data-stu-id="1fe57-109">Header</span></span> | <span data-ttu-id="1fe57-110">值</span><span class="sxs-lookup"><span data-stu-id="1fe57-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="1fe57-111">接受</span><span class="sxs-lookup"><span data-stu-id="1fe57-111">Accept</span></span>|<span data-ttu-id="1fe57-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="1fe57-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="1fe57-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1fe57-113">Content-Type</span></span>|<span data-ttu-id="1fe57-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="1fe57-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="1fe57-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="1fe57-115">x-requestdigest</span></span>|<span data-ttu-id="1fe57-116">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="1fe57-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="1fe57-117">要求內文</span><span class="sxs-lookup"><span data-stu-id="1fe57-117">Request body</span></span>

| <span data-ttu-id="1fe57-118">名稱</span><span class="sxs-lookup"><span data-stu-id="1fe57-118">Name</span></span> | <span data-ttu-id="1fe57-119">必要項目</span><span class="sxs-lookup"><span data-stu-id="1fe57-119">Required</span></span> | <span data-ttu-id="1fe57-120">類型</span><span class="sxs-lookup"><span data-stu-id="1fe57-120">Type</span></span> | <span data-ttu-id="1fe57-121">描述</span><span class="sxs-lookup"><span data-stu-id="1fe57-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="1fe57-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="1fe57-122">ModelUniqueId</span></span>|<span data-ttu-id="1fe57-123">是</span><span class="sxs-lookup"><span data-stu-id="1fe57-123">yes</span></span>|<span data-ttu-id="1fe57-124">string</span><span class="sxs-lookup"><span data-stu-id="1fe57-124">string</span></span>|<span data-ttu-id="1fe57-125">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1fe57-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="1fe57-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="1fe57-126">TargetSiteUrl</span></span>|<span data-ttu-id="1fe57-127">是</span><span class="sxs-lookup"><span data-stu-id="1fe57-127">yes</span></span>|<span data-ttu-id="1fe57-128">string</span><span class="sxs-lookup"><span data-stu-id="1fe57-128">string</span></span>|<span data-ttu-id="1fe57-129">目的文件庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="1fe57-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="1fe57-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="1fe57-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="1fe57-131">是</span><span class="sxs-lookup"><span data-stu-id="1fe57-131">yes</span></span>|<span data-ttu-id="1fe57-132">string</span><span class="sxs-lookup"><span data-stu-id="1fe57-132">string</span></span>|<span data-ttu-id="1fe57-133">目的文件庫之網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="1fe57-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="1fe57-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="1fe57-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="1fe57-135">是</span><span class="sxs-lookup"><span data-stu-id="1fe57-135">yes</span></span>|<span data-ttu-id="1fe57-136">string</span><span class="sxs-lookup"><span data-stu-id="1fe57-136">string</span></span>|<span data-ttu-id="1fe57-137">目的文件庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="1fe57-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="1fe57-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="1fe57-138">ViewOption</span></span>|<span data-ttu-id="1fe57-139">否</span><span class="sxs-lookup"><span data-stu-id="1fe57-139">no</span></span>|<span data-ttu-id="1fe57-140">string</span><span class="sxs-lookup"><span data-stu-id="1fe57-140">string</span></span>|<span data-ttu-id="1fe57-141">指定是否要將新模型檢視設定為文件庫預設值。</span><span class="sxs-lookup"><span data-stu-id="1fe57-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="1fe57-142">回應</span><span class="sxs-lookup"><span data-stu-id="1fe57-142">Response</span></span>

| <span data-ttu-id="1fe57-143">名稱</span><span class="sxs-lookup"><span data-stu-id="1fe57-143">Name</span></span>   | <span data-ttu-id="1fe57-144">類型</span><span class="sxs-lookup"><span data-stu-id="1fe57-144">Type</span></span>  | <span data-ttu-id="1fe57-145">描述</span><span class="sxs-lookup"><span data-stu-id="1fe57-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="1fe57-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="1fe57-146">200 OK</span></span>| |<span data-ttu-id="1fe57-147">成功</span><span class="sxs-lookup"><span data-stu-id="1fe57-147">Success</span></span>|
|<span data-ttu-id="1fe57-148">201 已建立</span><span class="sxs-lookup"><span data-stu-id="1fe57-148">201 Created</span></span>| |<span data-ttu-id="1fe57-149">請注意，由於此 API 支援將模型套用至多個程式庫，因此即使將模型套用至其中一個程式庫失敗，也可讓 201 返回。</span><span class="sxs-lookup"><span data-stu-id="1fe57-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="1fe57-150">檢查回應本文，了解模型是否成功套用至所有指定的程式庫。</span><span class="sxs-lookup"><span data-stu-id="1fe57-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="1fe57-151">請參閱[要求本文](rest-applymodel-method.md#request-body)取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1fe57-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="1fe57-152">範例</span><span class="sxs-lookup"><span data-stu-id="1fe57-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="1fe57-153">將模型套用至存放庫網站中的合約文件庫</span><span class="sxs-lookup"><span data-stu-id="1fe57-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="1fe57-154">在此範例中，Contoso 合約文件了解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="1fe57-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="1fe57-155">範例要求</span><span class="sxs-lookup"><span data-stu-id="1fe57-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="1fe57-156">範例回應</span><span class="sxs-lookup"><span data-stu-id="1fe57-156">Sample response</span></span>

<span data-ttu-id="1fe57-157">在回應中，TotalFailures 和 TotalSuccesses 是指要套用至指定程式庫之模型的失敗和成功次數。</span><span class="sxs-lookup"><span data-stu-id="1fe57-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="1fe57-158">**狀態碼:** 200</span><span class="sxs-lookup"><span data-stu-id="1fe57-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1fe57-159">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1fe57-159">See also</span></span>

[<span data-ttu-id="1fe57-160">Syntex 文件了解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="1fe57-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
