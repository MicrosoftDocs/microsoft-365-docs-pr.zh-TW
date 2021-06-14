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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904177"
---
# <a name="batchdelete"></a><span data-ttu-id="c64d8-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="c64d8-103">BatchDelete</span></span>

<span data-ttu-id="c64d8-104">從一或多個程式庫移除已套用的文件瞭解模型。</span><span class="sxs-lookup"><span data-stu-id="c64d8-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="c64d8-105">請注意，必須先從所有程式庫移除模型，才能刪除模型 (請參閱[範例](rest-batchdelete-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="c64d8-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="c64d8-106">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="c64d8-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="c64d8-107">URI 參數</span><span class="sxs-lookup"><span data-stu-id="c64d8-107">URI parameters</span></span>

<span data-ttu-id="c64d8-108">無</span><span class="sxs-lookup"><span data-stu-id="c64d8-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="c64d8-109">要求標頭</span><span class="sxs-lookup"><span data-stu-id="c64d8-109">Request headers</span></span>

| <span data-ttu-id="c64d8-110">標頭</span><span class="sxs-lookup"><span data-stu-id="c64d8-110">Header</span></span> | <span data-ttu-id="c64d8-111">值</span><span class="sxs-lookup"><span data-stu-id="c64d8-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="c64d8-112">Accept</span><span class="sxs-lookup"><span data-stu-id="c64d8-112">Accept</span></span>|<span data-ttu-id="c64d8-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="c64d8-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="c64d8-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="c64d8-114">Content-Type</span></span>|<span data-ttu-id="c64d8-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="c64d8-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="c64d8-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="c64d8-116">x-requestdigest</span></span>|<span data-ttu-id="c64d8-117">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="c64d8-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="c64d8-118">要求內文</span><span class="sxs-lookup"><span data-stu-id="c64d8-118">Request body</span></span>

| <span data-ttu-id="c64d8-119">名稱</span><span class="sxs-lookup"><span data-stu-id="c64d8-119">Name</span></span> | <span data-ttu-id="c64d8-120">必要項目</span><span class="sxs-lookup"><span data-stu-id="c64d8-120">Required</span></span> | <span data-ttu-id="c64d8-121">類型</span><span class="sxs-lookup"><span data-stu-id="c64d8-121">Type</span></span> | <span data-ttu-id="c64d8-122">描述</span><span class="sxs-lookup"><span data-stu-id="c64d8-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="c64d8-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="c64d8-123">ModelUniqueId</span></span>|<span data-ttu-id="c64d8-124">是</span><span class="sxs-lookup"><span data-stu-id="c64d8-124">yes</span></span>|<span data-ttu-id="c64d8-125">string</span><span class="sxs-lookup"><span data-stu-id="c64d8-125">string</span></span>|<span data-ttu-id="c64d8-126">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c64d8-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="c64d8-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="c64d8-127">TargetSiteUrl</span></span>|<span data-ttu-id="c64d8-128">是</span><span class="sxs-lookup"><span data-stu-id="c64d8-128">yes</span></span>|<span data-ttu-id="c64d8-129">string</span><span class="sxs-lookup"><span data-stu-id="c64d8-129">string</span></span>|<span data-ttu-id="c64d8-130">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="c64d8-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="c64d8-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="c64d8-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="c64d8-132">是</span><span class="sxs-lookup"><span data-stu-id="c64d8-132">yes</span></span>|<span data-ttu-id="c64d8-133">string</span><span class="sxs-lookup"><span data-stu-id="c64d8-133">string</span></span>|<span data-ttu-id="c64d8-134">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="c64d8-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="c64d8-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="c64d8-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="c64d8-136">是</span><span class="sxs-lookup"><span data-stu-id="c64d8-136">yes</span></span>|<span data-ttu-id="c64d8-137">string</span><span class="sxs-lookup"><span data-stu-id="c64d8-137">string</span></span>|<span data-ttu-id="c64d8-138">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="c64d8-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="c64d8-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="c64d8-139">ViewOption</span></span>|<span data-ttu-id="c64d8-140">否</span><span class="sxs-lookup"><span data-stu-id="c64d8-140">no</span></span>|<span data-ttu-id="c64d8-141">string</span><span class="sxs-lookup"><span data-stu-id="c64d8-141">string</span></span>|<span data-ttu-id="c64d8-142">指定是否要將新模型檢視設定為程式庫預設值。</span><span class="sxs-lookup"><span data-stu-id="c64d8-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="c64d8-143">回應</span><span class="sxs-lookup"><span data-stu-id="c64d8-143">Response</span></span>

| <span data-ttu-id="c64d8-144">名稱</span><span class="sxs-lookup"><span data-stu-id="c64d8-144">Name</span></span>   | <span data-ttu-id="c64d8-145">類型</span><span class="sxs-lookup"><span data-stu-id="c64d8-145">Type</span></span>  | <span data-ttu-id="c64d8-146">描述</span><span class="sxs-lookup"><span data-stu-id="c64d8-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="c64d8-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="c64d8-147">200 OK</span></span>| |<span data-ttu-id="c64d8-148">成功</span><span class="sxs-lookup"><span data-stu-id="c64d8-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="c64d8-149">範例</span><span class="sxs-lookup"><span data-stu-id="c64d8-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="c64d8-150">從存放庫網站中的合約文件庫移除模型</span><span class="sxs-lookup"><span data-stu-id="c64d8-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="c64d8-151">在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="c64d8-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="c64d8-152">範例要求</span><span class="sxs-lookup"><span data-stu-id="c64d8-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="c64d8-153">範例回應</span><span class="sxs-lookup"><span data-stu-id="c64d8-153">Sample response</span></span>

<span data-ttu-id="c64d8-154">在回應中，TotalFailures 和 TotalSuccesses 是指要套用至指定程式庫之模型的失敗和成功次數。</span><span class="sxs-lookup"><span data-stu-id="c64d8-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="c64d8-155">**狀態碼：** 200</span><span class="sxs-lookup"><span data-stu-id="c64d8-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c64d8-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c64d8-156">See also</span></span>

[<span data-ttu-id="c64d8-157">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="c64d8-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
