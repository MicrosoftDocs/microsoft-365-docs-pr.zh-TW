---
title: 建立分類要求
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
description: 使用 REST API 建立要求，以使用訓練過的文件了解模型來分類一或多個文件。
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177078"
---
# <a name="create-classification-request"></a><span data-ttu-id="24096-103">建立分類要求</span><span class="sxs-lookup"><span data-stu-id="24096-103">Create classification request</span></span>

<span data-ttu-id="24096-104">建立要求來使用已套用的文件了解模型分類一或多個文件 (請參閱 [範例](rest-createclassificationrequest.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="24096-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="24096-105">SharePoint Online (以及 SharePoint 2016 及更高版本內部部署) REST 服務支援合併多個要求。</span><span class="sxs-lookup"><span data-stu-id="24096-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="24096-106">要求會使用 OData $batch 查詢選項合併為對服務的單一呼叫。</span><span class="sxs-lookup"><span data-stu-id="24096-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="24096-107">這個方法可用來一次將數百份文件的分類工作項目加入佇列。</span><span class="sxs-lookup"><span data-stu-id="24096-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="24096-108">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="24096-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="24096-109">URI 參數</span><span class="sxs-lookup"><span data-stu-id="24096-109">URI Parameters</span></span>

<span data-ttu-id="24096-110">無</span><span class="sxs-lookup"><span data-stu-id="24096-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="24096-111">要求標頭</span><span class="sxs-lookup"><span data-stu-id="24096-111">Request headers</span></span>

| <span data-ttu-id="24096-112">標頭</span><span class="sxs-lookup"><span data-stu-id="24096-112">Header</span></span> | <span data-ttu-id="24096-113">值</span><span class="sxs-lookup"><span data-stu-id="24096-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="24096-114">Accept</span><span class="sxs-lookup"><span data-stu-id="24096-114">Accept</span></span>|<span data-ttu-id="24096-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="24096-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="24096-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="24096-116">Content-Type</span></span>|<span data-ttu-id="24096-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="24096-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="24096-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="24096-118">x-requestdigest</span></span>|<span data-ttu-id="24096-119">目前網站的適當摘要</span><span class="sxs-lookup"><span data-stu-id="24096-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="24096-120">要求內文</span><span class="sxs-lookup"><span data-stu-id="24096-120">Request body</span></span>

|<span data-ttu-id="24096-121">名稱</span><span class="sxs-lookup"><span data-stu-id="24096-121">Name</span></span>    |<span data-ttu-id="24096-122">類型</span><span class="sxs-lookup"><span data-stu-id="24096-122">Type</span></span>   |<span data-ttu-id="24096-123">描述</span><span class="sxs-lookup"><span data-stu-id="24096-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="24096-124">中繼資料(_M)</span><span class="sxs-lookup"><span data-stu-id="24096-124">_metadata</span></span>|<span data-ttu-id="24096-125">string</span><span class="sxs-lookup"><span data-stu-id="24096-125">string</span></span> |<span data-ttu-id="24096-126">在 SPO 上設定物件 Meta。</span><span class="sxs-lookup"><span data-stu-id="24096-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="24096-127">一律使用值: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}。</span><span class="sxs-lookup"><span data-stu-id="24096-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="24096-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="24096-128">TargetSiteId</span></span>|<span data-ttu-id="24096-129">GUID</span><span class="sxs-lookup"><span data-stu-id="24096-129">guid</span></span>|<span data-ttu-id="24096-130">要分類之檔案所在的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="24096-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="24096-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="24096-131">TargetWebId</span></span>|<span data-ttu-id="24096-132">GUID</span><span class="sxs-lookup"><span data-stu-id="24096-132">guid</span></span>|<span data-ttu-id="24096-133">要分類之檔案所在的網頁識別碼。</span><span class="sxs-lookup"><span data-stu-id="24096-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="24096-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="24096-134">TargetUniqueId</span></span>|<span data-ttu-id="24096-135">GUID</span><span class="sxs-lookup"><span data-stu-id="24096-135">guid</span></span>|<span data-ttu-id="24096-136">要分類之檔案的識別碼。</span><span class="sxs-lookup"><span data-stu-id="24096-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="24096-137">回應</span><span class="sxs-lookup"><span data-stu-id="24096-137">Responses</span></span>

| <span data-ttu-id="24096-138">名稱</span><span class="sxs-lookup"><span data-stu-id="24096-138">Name</span></span>   | <span data-ttu-id="24096-139">類型</span><span class="sxs-lookup"><span data-stu-id="24096-139">Type</span></span>  | <span data-ttu-id="24096-140">描述</span><span class="sxs-lookup"><span data-stu-id="24096-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="24096-141">201 已建立</span><span class="sxs-lookup"><span data-stu-id="24096-141">201 Created</span></span>| |<span data-ttu-id="24096-142">成功</span><span class="sxs-lookup"><span data-stu-id="24096-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="24096-143">範例</span><span class="sxs-lookup"><span data-stu-id="24096-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="24096-144">將識別碼為 "e6cff8b7-c90c-4564-b5b8-033449090932" 的檔案分類要求加入佇列</span><span class="sxs-lookup"><span data-stu-id="24096-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="24096-145">範例要求</span><span class="sxs-lookup"><span data-stu-id="24096-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="24096-146">範例回應</span><span class="sxs-lookup"><span data-stu-id="24096-146">Sample response</span></span>

<span data-ttu-id="24096-147">**狀態碼:** 201</span><span class="sxs-lookup"><span data-stu-id="24096-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="24096-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="24096-148">See also</span></span>

[<span data-ttu-id="24096-149">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="24096-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
