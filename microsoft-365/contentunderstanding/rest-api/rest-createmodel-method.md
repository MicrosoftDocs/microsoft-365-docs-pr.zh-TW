---
title: 建立模型
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
description: 使用 REST API 建立模型及其相關聯的內容類型。
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287242"
---
# <a name="create-model"></a><span data-ttu-id="82ed1-103">建立模型</span><span class="sxs-lookup"><span data-stu-id="82ed1-103">Create model</span></span>

<span data-ttu-id="82ed1-104">建立模型及其相關聯的內容類型。</span><span class="sxs-lookup"><span data-stu-id="82ed1-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="82ed1-105">請注意，這只會建立模型。</span><span class="sxs-lookup"><span data-stu-id="82ed1-105">Note that this only creates the model.</span></span> <span data-ttu-id="82ed1-106">它仍然需要在內容中心進行訓練 (請參閱[範例](rest-createmodel-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="82ed1-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="82ed1-107">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="82ed1-107">HTTP request</span></span>

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="82ed1-108">URI 參數</span><span class="sxs-lookup"><span data-stu-id="82ed1-108">URI Parameters</span></span>

<span data-ttu-id="82ed1-109">無</span><span class="sxs-lookup"><span data-stu-id="82ed1-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="82ed1-110">要求標頭</span><span class="sxs-lookup"><span data-stu-id="82ed1-110">Request headers</span></span>

| <span data-ttu-id="82ed1-111">頁首</span><span class="sxs-lookup"><span data-stu-id="82ed1-111">Header</span></span> | <span data-ttu-id="82ed1-112">值</span><span class="sxs-lookup"><span data-stu-id="82ed1-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="82ed1-113">Accept</span><span class="sxs-lookup"><span data-stu-id="82ed1-113">Accept</span></span>|<span data-ttu-id="82ed1-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="82ed1-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="82ed1-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="82ed1-115">Content-Type</span></span>|<span data-ttu-id="82ed1-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="82ed1-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="82ed1-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="82ed1-117">x-requestdigest</span></span>|<span data-ttu-id="82ed1-118">目前網站的適當摘要</span><span class="sxs-lookup"><span data-stu-id="82ed1-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="82ed1-119">要求內文</span><span class="sxs-lookup"><span data-stu-id="82ed1-119">Request body</span></span>

|<span data-ttu-id="82ed1-120">名稱</span><span class="sxs-lookup"><span data-stu-id="82ed1-120">Name</span></span>    |<span data-ttu-id="82ed1-121">類型</span><span class="sxs-lookup"><span data-stu-id="82ed1-121">Type</span></span>   |<span data-ttu-id="82ed1-122">描述</span><span class="sxs-lookup"><span data-stu-id="82ed1-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="82ed1-123">中繼資料(_M)</span><span class="sxs-lookup"><span data-stu-id="82ed1-123">_metadata</span></span>|  |<span data-ttu-id="82ed1-124">在 SPO 上設定物件 Meta。</span><span class="sxs-lookup"><span data-stu-id="82ed1-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="82ed1-125">一律使用值: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}。</span><span class="sxs-lookup"><span data-stu-id="82ed1-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="82ed1-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="82ed1-126">ContentTypeGroup</span></span>|<span data-ttu-id="82ed1-127">string</span><span class="sxs-lookup"><span data-stu-id="82ed1-127">string</span></span>|<span data-ttu-id="82ed1-128">與模型相關聯的相關聯內容類型群組。</span><span class="sxs-lookup"><span data-stu-id="82ed1-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="82ed1-129">預設為「智慧型文件內容類型」。</span><span class="sxs-lookup"><span data-stu-id="82ed1-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="82ed1-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="82ed1-130">ContentTypeName</span></span>|<span data-ttu-id="82ed1-131">string</span><span class="sxs-lookup"><span data-stu-id="82ed1-131">string</span></span>|<span data-ttu-id="82ed1-132">關聯的內容類型名稱。</span><span class="sxs-lookup"><span data-stu-id="82ed1-132">The associated content type name.</span></span> <span data-ttu-id="82ed1-133">建立的模型檔案將會有相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="82ed1-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="82ed1-134">回應</span><span class="sxs-lookup"><span data-stu-id="82ed1-134">Responses</span></span>

| <span data-ttu-id="82ed1-135">名稱</span><span class="sxs-lookup"><span data-stu-id="82ed1-135">Name</span></span>   | <span data-ttu-id="82ed1-136">類型</span><span class="sxs-lookup"><span data-stu-id="82ed1-136">Type</span></span>  | <span data-ttu-id="82ed1-137">描述</span><span class="sxs-lookup"><span data-stu-id="82ed1-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="82ed1-138">201 已建立</span><span class="sxs-lookup"><span data-stu-id="82ed1-138">201 Created</span></span>| |<span data-ttu-id="82ed1-139">成功</span><span class="sxs-lookup"><span data-stu-id="82ed1-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="82ed1-140">範例</span><span class="sxs-lookup"><span data-stu-id="82ed1-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="82ed1-141">建立名為「Contoso 合約」的新文件了解模型</span><span class="sxs-lookup"><span data-stu-id="82ed1-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="82ed1-142">範例要求</span><span class="sxs-lookup"><span data-stu-id="82ed1-142">Sample request</span></span>

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="82ed1-143">範例回應</span><span class="sxs-lookup"><span data-stu-id="82ed1-143">Sample response</span></span>

<span data-ttu-id="82ed1-144">**狀態碼:** 201</span><span class="sxs-lookup"><span data-stu-id="82ed1-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="82ed1-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="82ed1-145">See also</span></span>

[<span data-ttu-id="82ed1-146">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="82ed1-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
