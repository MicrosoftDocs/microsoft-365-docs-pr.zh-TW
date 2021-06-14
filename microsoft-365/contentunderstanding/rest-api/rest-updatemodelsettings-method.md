---
title: UpdateModelSettings
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
description: 使用 REST API 來更新 SharePoint Syntex 文件了解模型的可用模型設定。
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904189"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="e3797-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="e3797-103">UpdateModelSettings</span></span>

<span data-ttu-id="e3797-104">更新 SharePoint Syntex 文件瞭解模型的可用模型設定 (相關聯的保留標籤和模型描述)(查看[範例](rest-updatemodelsettings-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="e3797-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="e3797-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="e3797-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="e3797-106">URI 參數</span><span class="sxs-lookup"><span data-stu-id="e3797-106">URI parameters</span></span>

<span data-ttu-id="e3797-107">無</span><span class="sxs-lookup"><span data-stu-id="e3797-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="e3797-108">要求標頭</span><span class="sxs-lookup"><span data-stu-id="e3797-108">Request headers</span></span>

| <span data-ttu-id="e3797-109">頁首</span><span class="sxs-lookup"><span data-stu-id="e3797-109">Header</span></span> | <span data-ttu-id="e3797-110">值</span><span class="sxs-lookup"><span data-stu-id="e3797-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="e3797-111">接受</span><span class="sxs-lookup"><span data-stu-id="e3797-111">Accept</span></span>|<span data-ttu-id="e3797-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="e3797-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="e3797-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e3797-113">Content-Type</span></span>|<span data-ttu-id="e3797-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="e3797-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="e3797-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="e3797-115">x-requestdigest</span></span>|<span data-ttu-id="e3797-116">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="e3797-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="e3797-117">要求內文</span><span class="sxs-lookup"><span data-stu-id="e3797-117">Request body</span></span>

|<span data-ttu-id="e3797-118">名稱</span><span class="sxs-lookup"><span data-stu-id="e3797-118">Name</span></span>    |<span data-ttu-id="e3797-119">類型</span><span class="sxs-lookup"><span data-stu-id="e3797-119">Type</span></span>   |<span data-ttu-id="e3797-120">描述</span><span class="sxs-lookup"><span data-stu-id="e3797-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="e3797-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="e3797-121">ModelSettings</span></span>|<span data-ttu-id="e3797-122">string</span><span class="sxs-lookup"><span data-stu-id="e3797-122">string</span></span>|<span data-ttu-id="e3797-123">模型設定 JSON。</span><span class="sxs-lookup"><span data-stu-id="e3797-123">JSON of model settings.</span></span>|
|<span data-ttu-id="e3797-124">描述</span><span class="sxs-lookup"><span data-stu-id="e3797-124">Description</span></span>|<span data-ttu-id="e3797-125">string</span><span class="sxs-lookup"><span data-stu-id="e3797-125">string</span></span>|<span data-ttu-id="e3797-126">模型描述。</span><span class="sxs-lookup"><span data-stu-id="e3797-126">The model description.</span></span>|
|<span data-ttu-id="e3797-127">保留標籤</span><span class="sxs-lookup"><span data-stu-id="e3797-127">RetentionLabel</span></span>| |<span data-ttu-id="e3797-128">相關聯標籤的資訊 (標籤識別碼和名稱)。</span><span class="sxs-lookup"><span data-stu-id="e3797-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="e3797-129">回應</span><span class="sxs-lookup"><span data-stu-id="e3797-129">Responses</span></span>

| <span data-ttu-id="e3797-130">名稱</span><span class="sxs-lookup"><span data-stu-id="e3797-130">Name</span></span>   | <span data-ttu-id="e3797-131">類型</span><span class="sxs-lookup"><span data-stu-id="e3797-131">Type</span></span>  | <span data-ttu-id="e3797-132">描述</span><span class="sxs-lookup"><span data-stu-id="e3797-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="e3797-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="e3797-133">200 OK</span></span>| |<span data-ttu-id="e3797-134">成功</span><span class="sxs-lookup"><span data-stu-id="e3797-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="e3797-135">範例</span><span class="sxs-lookup"><span data-stu-id="e3797-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="e3797-136">更新 Contoso 合約的模型設定</span><span class="sxs-lookup"><span data-stu-id="e3797-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="e3797-137">在此範例中，模型描述和「標準保留」保留標籤會更新。</span><span class="sxs-lookup"><span data-stu-id="e3797-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="e3797-138">保留標籤的識別碼為 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。</span><span class="sxs-lookup"><span data-stu-id="e3797-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="e3797-139">範例要求</span><span class="sxs-lookup"><span data-stu-id="e3797-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="e3797-140">範例回應</span><span class="sxs-lookup"><span data-stu-id="e3797-140">Sample response</span></span>

<span data-ttu-id="e3797-141">**狀態碼:** 200</span><span class="sxs-lookup"><span data-stu-id="e3797-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="e3797-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e3797-142">See also</span></span>

[<span data-ttu-id="e3797-143">Syntex 文件了解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="e3797-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
