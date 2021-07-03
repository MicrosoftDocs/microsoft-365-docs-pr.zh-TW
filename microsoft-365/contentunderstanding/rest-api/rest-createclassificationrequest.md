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
ms.openlocfilehash: b1022787d6e11ebe36c88ecd29936a777289dd74
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287230"
---
# <a name="create-classification-request"></a><span data-ttu-id="7cac4-103">建立分類要求</span><span class="sxs-lookup"><span data-stu-id="7cac4-103">Create classification request</span></span>

<span data-ttu-id="7cac4-104">建立要求來使用已套用的文件了解模型分類一或多個文件 (請參閱 [範例](rest-createclassificationrequest.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="7cac4-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="7cac4-105">SharePoint Online (以及 SharePoint 2016 及更高版本內部部署) REST 服務支援合併多個要求。</span><span class="sxs-lookup"><span data-stu-id="7cac4-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="7cac4-106">要求會使用 OData $batch 查詢選項合併為對服務的單一呼叫。</span><span class="sxs-lookup"><span data-stu-id="7cac4-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="7cac4-107">這個方法可用來一次將數百份文件的分類工作項目加入佇列。</span><span class="sxs-lookup"><span data-stu-id="7cac4-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="7cac4-108">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="7cac4-108">HTTP request</span></span>

```http
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="7cac4-109">URI 參數</span><span class="sxs-lookup"><span data-stu-id="7cac4-109">URI Parameters</span></span>

<span data-ttu-id="7cac4-110">無</span><span class="sxs-lookup"><span data-stu-id="7cac4-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="7cac4-111">要求標頭</span><span class="sxs-lookup"><span data-stu-id="7cac4-111">Request headers</span></span>

| <span data-ttu-id="7cac4-112">頁首</span><span class="sxs-lookup"><span data-stu-id="7cac4-112">Header</span></span> | <span data-ttu-id="7cac4-113">值</span><span class="sxs-lookup"><span data-stu-id="7cac4-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="7cac4-114">Accept</span><span class="sxs-lookup"><span data-stu-id="7cac4-114">Accept</span></span>|<span data-ttu-id="7cac4-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="7cac4-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="7cac4-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7cac4-116">Content-Type</span></span>|<span data-ttu-id="7cac4-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="7cac4-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="7cac4-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="7cac4-118">x-requestdigest</span></span>|<span data-ttu-id="7cac4-119">目前網站的適當摘要</span><span class="sxs-lookup"><span data-stu-id="7cac4-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="7cac4-120">要求內文</span><span class="sxs-lookup"><span data-stu-id="7cac4-120">Request body</span></span>

|<span data-ttu-id="7cac4-121">名稱</span><span class="sxs-lookup"><span data-stu-id="7cac4-121">Name</span></span>    |<span data-ttu-id="7cac4-122">類型</span><span class="sxs-lookup"><span data-stu-id="7cac4-122">Type</span></span>   |<span data-ttu-id="7cac4-123">描述</span><span class="sxs-lookup"><span data-stu-id="7cac4-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="7cac4-124">中繼資料(_M)</span><span class="sxs-lookup"><span data-stu-id="7cac4-124">_metadata</span></span>|<span data-ttu-id="7cac4-125">string</span><span class="sxs-lookup"><span data-stu-id="7cac4-125">string</span></span> |<span data-ttu-id="7cac4-126">在 SPO 上設定物件 Meta。</span><span class="sxs-lookup"><span data-stu-id="7cac4-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="7cac4-127">一律使用值: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}。</span><span class="sxs-lookup"><span data-stu-id="7cac4-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="7cac4-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="7cac4-128">TargetSiteId</span></span>|<span data-ttu-id="7cac4-129">GUID</span><span class="sxs-lookup"><span data-stu-id="7cac4-129">guid</span></span>|<span data-ttu-id="7cac4-130">要分類之檔案所在的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="7cac4-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="7cac4-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="7cac4-131">TargetWebId</span></span>|<span data-ttu-id="7cac4-132">GUID</span><span class="sxs-lookup"><span data-stu-id="7cac4-132">guid</span></span>|<span data-ttu-id="7cac4-133">要分類之檔案所在的網頁識別碼。</span><span class="sxs-lookup"><span data-stu-id="7cac4-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="7cac4-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="7cac4-134">TargetUniqueId</span></span>|<span data-ttu-id="7cac4-135">GUID</span><span class="sxs-lookup"><span data-stu-id="7cac4-135">guid</span></span>|<span data-ttu-id="7cac4-136">要分類之檔案的識別碼。</span><span class="sxs-lookup"><span data-stu-id="7cac4-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="7cac4-137">回應</span><span class="sxs-lookup"><span data-stu-id="7cac4-137">Responses</span></span>

| <span data-ttu-id="7cac4-138">名稱</span><span class="sxs-lookup"><span data-stu-id="7cac4-138">Name</span></span>   | <span data-ttu-id="7cac4-139">類型</span><span class="sxs-lookup"><span data-stu-id="7cac4-139">Type</span></span>  | <span data-ttu-id="7cac4-140">描述</span><span class="sxs-lookup"><span data-stu-id="7cac4-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="7cac4-141">201 已建立</span><span class="sxs-lookup"><span data-stu-id="7cac4-141">201 Created</span></span>| |<span data-ttu-id="7cac4-142">成功</span><span class="sxs-lookup"><span data-stu-id="7cac4-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="7cac4-143">範例</span><span class="sxs-lookup"><span data-stu-id="7cac4-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="7cac4-144">將識別碼為 "e6cff8b7-c90c-4564-b5b8-033449090932" 的檔案分類要求加入佇列</span><span class="sxs-lookup"><span data-stu-id="7cac4-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="7cac4-145">範例要求</span><span class="sxs-lookup"><span data-stu-id="7cac4-145">Sample request</span></span>

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="7cac4-146">範例回應</span><span class="sxs-lookup"><span data-stu-id="7cac4-146">Sample response</span></span>

<span data-ttu-id="7cac4-147">**狀態碼:** 201</span><span class="sxs-lookup"><span data-stu-id="7cac4-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="7cac4-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7cac4-148">See also</span></span>

[<span data-ttu-id="7cac4-149">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="7cac4-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
