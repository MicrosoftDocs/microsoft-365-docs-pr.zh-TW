---
title: 取得模型和程式庫資訊
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
description: 使用 REST API 來取得模型及套用其所在程式庫的相關資訊。
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904188"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="cad88-103">取得模型和程式庫資訊</span><span class="sxs-lookup"><span data-stu-id="cad88-103">Get model and library information</span></span>

<span data-ttu-id="cad88-104">取得模型及套用其所在程式庫的相關資訊 (請參閱[範例](rest-getmodelandlibraryinfo.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="cad88-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="cad88-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="cad88-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="cad88-106">URI 參數</span><span class="sxs-lookup"><span data-stu-id="cad88-106">URI parameters</span></span>

| <span data-ttu-id="cad88-107">名稱</span><span class="sxs-lookup"><span data-stu-id="cad88-107">Name</span></span> | <span data-ttu-id="cad88-108">於</span><span class="sxs-lookup"><span data-stu-id="cad88-108">In</span></span> | <span data-ttu-id="cad88-109">必要項目</span><span class="sxs-lookup"><span data-stu-id="cad88-109">Required</span></span> | <span data-ttu-id="cad88-110">類型</span><span class="sxs-lookup"><span data-stu-id="cad88-110">Type</span></span> | <span data-ttu-id="cad88-111">描述</span><span class="sxs-lookup"><span data-stu-id="cad88-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="cad88-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="cad88-112">ModelUniqueId</span></span>|<span data-ttu-id="cad88-113">查詢</span><span class="sxs-lookup"><span data-stu-id="cad88-113">query</span></span>|<span data-ttu-id="cad88-114">True</span><span class="sxs-lookup"><span data-stu-id="cad88-114">True</span></span>|<span data-ttu-id="cad88-115">GUID</span><span class="sxs-lookup"><span data-stu-id="cad88-115">GUID</span></span>|<span data-ttu-id="cad88-116">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cad88-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="cad88-117">要求標頭</span><span class="sxs-lookup"><span data-stu-id="cad88-117">Request headers</span></span>

| <span data-ttu-id="cad88-118">標頭</span><span class="sxs-lookup"><span data-stu-id="cad88-118">Header</span></span> | <span data-ttu-id="cad88-119">值</span><span class="sxs-lookup"><span data-stu-id="cad88-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="cad88-120">Accept</span><span class="sxs-lookup"><span data-stu-id="cad88-120">Accept</span></span>|<span data-ttu-id="cad88-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="cad88-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="cad88-122">要求內文</span><span class="sxs-lookup"><span data-stu-id="cad88-122">Request body</span></span>

| <span data-ttu-id="cad88-123">名稱</span><span class="sxs-lookup"><span data-stu-id="cad88-123">Name</span></span> | <span data-ttu-id="cad88-124">必要項目</span><span class="sxs-lookup"><span data-stu-id="cad88-124">Required</span></span> | <span data-ttu-id="cad88-125">類型</span><span class="sxs-lookup"><span data-stu-id="cad88-125">Type</span></span> | <span data-ttu-id="cad88-126">描述</span><span class="sxs-lookup"><span data-stu-id="cad88-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="cad88-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="cad88-127">ModelUniqueId</span></span>|<span data-ttu-id="cad88-128">是</span><span class="sxs-lookup"><span data-stu-id="cad88-128">yes</span></span>|<span data-ttu-id="cad88-129">string</span><span class="sxs-lookup"><span data-stu-id="cad88-129">string</span></span>|<span data-ttu-id="cad88-130">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cad88-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="cad88-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="cad88-131">TargetSiteUrl</span></span>|<span data-ttu-id="cad88-132">是</span><span class="sxs-lookup"><span data-stu-id="cad88-132">yes</span></span>|<span data-ttu-id="cad88-133">string</span><span class="sxs-lookup"><span data-stu-id="cad88-133">string</span></span>|<span data-ttu-id="cad88-134">目標程式庫網站的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="cad88-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="cad88-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="cad88-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="cad88-136">是</span><span class="sxs-lookup"><span data-stu-id="cad88-136">yes</span></span>|<span data-ttu-id="cad88-137">string</span><span class="sxs-lookup"><span data-stu-id="cad88-137">string</span></span>|<span data-ttu-id="cad88-138">目標程式庫網頁的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="cad88-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="cad88-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="cad88-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="cad88-140">是</span><span class="sxs-lookup"><span data-stu-id="cad88-140">yes</span></span>|<span data-ttu-id="cad88-141">string</span><span class="sxs-lookup"><span data-stu-id="cad88-141">string</span></span>|<span data-ttu-id="cad88-142">目標程式庫的伺服器相對 URL。</span><span class="sxs-lookup"><span data-stu-id="cad88-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="cad88-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="cad88-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="cad88-144">是</span><span class="sxs-lookup"><span data-stu-id="cad88-144">yes</span></span>|<span data-ttu-id="cad88-145">int</span><span class="sxs-lookup"><span data-stu-id="cad88-145">int</span></span>|<span data-ttu-id="cad88-146">指出是否已移除目標程式庫的旗標。</span><span class="sxs-lookup"><span data-stu-id="cad88-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="cad88-147">回應</span><span class="sxs-lookup"><span data-stu-id="cad88-147">Response</span></span>

| <span data-ttu-id="cad88-148">名稱</span><span class="sxs-lookup"><span data-stu-id="cad88-148">Name</span></span>   | <span data-ttu-id="cad88-149">類型</span><span class="sxs-lookup"><span data-stu-id="cad88-149">Type</span></span>  | <span data-ttu-id="cad88-150">描述</span><span class="sxs-lookup"><span data-stu-id="cad88-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="cad88-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="cad88-151">200 OK</span></span>| |<span data-ttu-id="cad88-152">成功</span><span class="sxs-lookup"><span data-stu-id="cad88-152">Success</span></span>|
|<span data-ttu-id="cad88-153">201 已建立</span><span class="sxs-lookup"><span data-stu-id="cad88-153">201 Created</span></span>| |<span data-ttu-id="cad88-154">請注意，由於此 API 支援將模型套用至多個程式庫，因此即使將模型套用至其中一個程式庫失敗，也可能傳回 201。</span><span class="sxs-lookup"><span data-stu-id="cad88-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="cad88-155">檢查回應內文，了解模型是否成功套用至所有指定的程式庫。</span><span class="sxs-lookup"><span data-stu-id="cad88-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="cad88-156">如需詳細資料，請參閱[要求內文](rest-getmodelandlibraryinfo.md#request-body)。</span><span class="sxs-lookup"><span data-stu-id="cad88-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="cad88-157">範例</span><span class="sxs-lookup"><span data-stu-id="cad88-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="cad88-158">取得存放庫網站中合約模型和主要文件庫的資訊</span><span class="sxs-lookup"><span data-stu-id="cad88-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="cad88-159">在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="cad88-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="cad88-160">範例要求</span><span class="sxs-lookup"><span data-stu-id="cad88-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="cad88-161">範例回應</span><span class="sxs-lookup"><span data-stu-id="cad88-161">Sample response</span></span>

<span data-ttu-id="cad88-162">**狀態碼：** 200</span><span class="sxs-lookup"><span data-stu-id="cad88-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="cad88-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cad88-163">See also</span></span>

[<span data-ttu-id="cad88-164">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="cad88-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
