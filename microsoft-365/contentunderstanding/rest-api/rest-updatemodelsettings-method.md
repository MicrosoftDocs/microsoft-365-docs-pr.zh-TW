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
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177162"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="42ce4-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="42ce4-103">UpdateModelSettings</span></span>

<span data-ttu-id="42ce4-104">更新 SharePoint Syntex 文件瞭解模型的可用模型設定 (相關聯的保留標籤和模型描述)(查看[範例](rest-updatemodelsettings-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="42ce4-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="42ce4-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="42ce4-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="42ce4-106">URI 參數</span><span class="sxs-lookup"><span data-stu-id="42ce4-106">URI parameters</span></span>

|<span data-ttu-id="42ce4-107">名稱</span><span class="sxs-lookup"><span data-stu-id="42ce4-107">Name</span></span> |<span data-ttu-id="42ce4-108">於</span><span class="sxs-lookup"><span data-stu-id="42ce4-108">In</span></span> |<span data-ttu-id="42ce4-109">必要項目</span><span class="sxs-lookup"><span data-stu-id="42ce4-109">Required</span></span>|<span data-ttu-id="42ce4-110">類型</span><span class="sxs-lookup"><span data-stu-id="42ce4-110">Type</span></span>|<span data-ttu-id="42ce4-111">描述</span><span class="sxs-lookup"><span data-stu-id="42ce4-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="42ce4-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="42ce4-112">modelFileName</span></span>|<span data-ttu-id="42ce4-113">查詢</span><span class="sxs-lookup"><span data-stu-id="42ce4-113">query</span></span>|<span data-ttu-id="42ce4-114">對</span><span class="sxs-lookup"><span data-stu-id="42ce4-114">True</span></span>|<span data-ttu-id="42ce4-115">string</span><span class="sxs-lookup"><span data-stu-id="42ce4-115">string</span></span>|<span data-ttu-id="42ce4-116">Syntex 模型檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="42ce4-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="42ce4-117">要求標頭</span><span class="sxs-lookup"><span data-stu-id="42ce4-117">Request headers</span></span>

| <span data-ttu-id="42ce4-118">標頭</span><span class="sxs-lookup"><span data-stu-id="42ce4-118">Header</span></span> | <span data-ttu-id="42ce4-119">值</span><span class="sxs-lookup"><span data-stu-id="42ce4-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="42ce4-120">Accept</span><span class="sxs-lookup"><span data-stu-id="42ce4-120">Accept</span></span>|<span data-ttu-id="42ce4-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="42ce4-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="42ce4-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="42ce4-122">Content-Type</span></span>|<span data-ttu-id="42ce4-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="42ce4-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="42ce4-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="42ce4-124">x-requestdigest</span></span>|<span data-ttu-id="42ce4-125">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="42ce4-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="42ce4-126">要求內文</span><span class="sxs-lookup"><span data-stu-id="42ce4-126">Request body</span></span>

|<span data-ttu-id="42ce4-127">名稱</span><span class="sxs-lookup"><span data-stu-id="42ce4-127">Name</span></span>    |<span data-ttu-id="42ce4-128">類型</span><span class="sxs-lookup"><span data-stu-id="42ce4-128">Type</span></span>   |<span data-ttu-id="42ce4-129">描述</span><span class="sxs-lookup"><span data-stu-id="42ce4-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="42ce4-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="42ce4-130">ModelSettings</span></span>|<span data-ttu-id="42ce4-131">string</span><span class="sxs-lookup"><span data-stu-id="42ce4-131">string</span></span>|<span data-ttu-id="42ce4-132">模型設定 JSON。</span><span class="sxs-lookup"><span data-stu-id="42ce4-132">JSON of model settings.</span></span>|
|<span data-ttu-id="42ce4-133">描述</span><span class="sxs-lookup"><span data-stu-id="42ce4-133">Description</span></span>|<span data-ttu-id="42ce4-134">string</span><span class="sxs-lookup"><span data-stu-id="42ce4-134">string</span></span>|<span data-ttu-id="42ce4-135">模型描述。</span><span class="sxs-lookup"><span data-stu-id="42ce4-135">The model description.</span></span>|
|<span data-ttu-id="42ce4-136">保留標籤</span><span class="sxs-lookup"><span data-stu-id="42ce4-136">RetentionLabel</span></span>| |<span data-ttu-id="42ce4-137">相關聯標籤的資訊 (標籤識別碼和名稱)。</span><span class="sxs-lookup"><span data-stu-id="42ce4-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="42ce4-138">回應</span><span class="sxs-lookup"><span data-stu-id="42ce4-138">Responses</span></span>

| <span data-ttu-id="42ce4-139">名稱</span><span class="sxs-lookup"><span data-stu-id="42ce4-139">Name</span></span>   | <span data-ttu-id="42ce4-140">類型</span><span class="sxs-lookup"><span data-stu-id="42ce4-140">Type</span></span>  | <span data-ttu-id="42ce4-141">描述</span><span class="sxs-lookup"><span data-stu-id="42ce4-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="42ce4-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="42ce4-142">200 OK</span></span>| |<span data-ttu-id="42ce4-143">成功</span><span class="sxs-lookup"><span data-stu-id="42ce4-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="42ce4-144">範例</span><span class="sxs-lookup"><span data-stu-id="42ce4-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="42ce4-145">更新 Contoso 合約的模型設定</span><span class="sxs-lookup"><span data-stu-id="42ce4-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="42ce4-146">在此範例中，模型描述和「標準保留」保留標籤會更新。</span><span class="sxs-lookup"><span data-stu-id="42ce4-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="42ce4-147">保留標籤的識別碼為 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。</span><span class="sxs-lookup"><span data-stu-id="42ce4-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="42ce4-148">範例要求</span><span class="sxs-lookup"><span data-stu-id="42ce4-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="42ce4-149">範例回應</span><span class="sxs-lookup"><span data-stu-id="42ce4-149">Sample response</span></span>

<span data-ttu-id="42ce4-150">**狀態碼：** 200</span><span class="sxs-lookup"><span data-stu-id="42ce4-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="42ce4-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="42ce4-151">See also</span></span>

[<span data-ttu-id="42ce4-152">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="42ce4-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
