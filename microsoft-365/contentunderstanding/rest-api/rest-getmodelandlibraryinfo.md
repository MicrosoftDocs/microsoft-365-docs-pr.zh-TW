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
ms.openlocfilehash: 29240a6210e2079a082be6c3a07aae890d932719
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288752"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="212bc-103">取得模型和程式庫資訊</span><span class="sxs-lookup"><span data-stu-id="212bc-103">Get model and library information</span></span>

<span data-ttu-id="212bc-104">取得模型及套用其所在程式庫的相關資訊 (請參閱[範例](rest-getmodelandlibraryinfo.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="212bc-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="212bc-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="212bc-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbymodeluniqueid('{modelUniqueId}') HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="212bc-106">URI 參數</span><span class="sxs-lookup"><span data-stu-id="212bc-106">URI parameters</span></span>

| <span data-ttu-id="212bc-107">名稱</span><span class="sxs-lookup"><span data-stu-id="212bc-107">Name</span></span> | <span data-ttu-id="212bc-108">於</span><span class="sxs-lookup"><span data-stu-id="212bc-108">In</span></span> | <span data-ttu-id="212bc-109">必要項目</span><span class="sxs-lookup"><span data-stu-id="212bc-109">Required</span></span> | <span data-ttu-id="212bc-110">類型</span><span class="sxs-lookup"><span data-stu-id="212bc-110">Type</span></span> | <span data-ttu-id="212bc-111">描述</span><span class="sxs-lookup"><span data-stu-id="212bc-111">Description</span></span> |
|--------|-------|--------|------------|-----------|
|<span data-ttu-id="212bc-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="212bc-112">ModelUniqueId</span></span>|<span data-ttu-id="212bc-113">查詢</span><span class="sxs-lookup"><span data-stu-id="212bc-113">query</span></span>|<span data-ttu-id="212bc-114">True</span><span class="sxs-lookup"><span data-stu-id="212bc-114">True</span></span>|<span data-ttu-id="212bc-115">GUID</span><span class="sxs-lookup"><span data-stu-id="212bc-115">GUID</span></span>|<span data-ttu-id="212bc-116">模型檔案的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="212bc-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="212bc-117">要求標頭</span><span class="sxs-lookup"><span data-stu-id="212bc-117">Request headers</span></span>

| <span data-ttu-id="212bc-118">頁首</span><span class="sxs-lookup"><span data-stu-id="212bc-118">Header</span></span> | <span data-ttu-id="212bc-119">值</span><span class="sxs-lookup"><span data-stu-id="212bc-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="212bc-120">Accept</span><span class="sxs-lookup"><span data-stu-id="212bc-120">Accept</span></span>|<span data-ttu-id="212bc-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="212bc-121">application/json;odata=verbose</span></span>|


## <a name="response"></a><span data-ttu-id="212bc-122">回應</span><span class="sxs-lookup"><span data-stu-id="212bc-122">Response</span></span>

| <span data-ttu-id="212bc-123">名稱</span><span class="sxs-lookup"><span data-stu-id="212bc-123">Name</span></span>   | <span data-ttu-id="212bc-124">類型</span><span class="sxs-lookup"><span data-stu-id="212bc-124">Type</span></span>  | <span data-ttu-id="212bc-125">描述</span><span class="sxs-lookup"><span data-stu-id="212bc-125">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="212bc-126">200 OK</span><span class="sxs-lookup"><span data-stu-id="212bc-126">200 OK</span></span>| |<span data-ttu-id="212bc-127">成功</span><span class="sxs-lookup"><span data-stu-id="212bc-127">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="212bc-128">範例</span><span class="sxs-lookup"><span data-stu-id="212bc-128">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="212bc-129">取得存放庫網站中合約模型和主要文件庫的資訊</span><span class="sxs-lookup"><span data-stu-id="212bc-129">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="212bc-130">在此範例中，Contoso 合約文件瞭解模型的識別碼為 `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`。</span><span class="sxs-lookup"><span data-stu-id="212bc-130">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="212bc-131">範例要求</span><span class="sxs-lookup"><span data-stu-id="212bc-131">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc') HTTP/1.1
```

#### <a name="sample-response"></a><span data-ttu-id="212bc-132">範例回應</span><span class="sxs-lookup"><span data-stu-id="212bc-132">Sample response</span></span>

<span data-ttu-id="212bc-133">**狀態碼：** 200</span><span class="sxs-lookup"><span data-stu-id="212bc-133">**Status code:** 200</span></span>

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
}
```

## <a name="see-also"></a><span data-ttu-id="212bc-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="212bc-134">See also</span></span>

[<span data-ttu-id="212bc-135">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="212bc-135">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
