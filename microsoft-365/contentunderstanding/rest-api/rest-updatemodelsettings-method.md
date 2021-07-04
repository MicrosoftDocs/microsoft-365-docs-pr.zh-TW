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
ms.openlocfilehash: c75f669913f16233c6015230a60643cf86f33f5a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288644"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="3d823-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="3d823-103">UpdateModelSettings</span></span>

<span data-ttu-id="3d823-104">更新 SharePoint Syntex 文件瞭解模型的可用模型設定 (相關聯的保留標籤和模型描述)(查看[範例](rest-updatemodelsettings-method.md#examples))。</span><span class="sxs-lookup"><span data-stu-id="3d823-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="3d823-105">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3d823-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="3d823-106">URI 參數</span><span class="sxs-lookup"><span data-stu-id="3d823-106">URI parameters</span></span>

|<span data-ttu-id="3d823-107">名稱</span><span class="sxs-lookup"><span data-stu-id="3d823-107">Name</span></span> |<span data-ttu-id="3d823-108">於</span><span class="sxs-lookup"><span data-stu-id="3d823-108">In</span></span> |<span data-ttu-id="3d823-109">必要項目</span><span class="sxs-lookup"><span data-stu-id="3d823-109">Required</span></span>|<span data-ttu-id="3d823-110">類型</span><span class="sxs-lookup"><span data-stu-id="3d823-110">Type</span></span>|<span data-ttu-id="3d823-111">描述</span><span class="sxs-lookup"><span data-stu-id="3d823-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="3d823-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="3d823-112">modelFileName</span></span>|<span data-ttu-id="3d823-113">查詢</span><span class="sxs-lookup"><span data-stu-id="3d823-113">query</span></span>|<span data-ttu-id="3d823-114">對</span><span class="sxs-lookup"><span data-stu-id="3d823-114">True</span></span>|<span data-ttu-id="3d823-115">string</span><span class="sxs-lookup"><span data-stu-id="3d823-115">string</span></span>|<span data-ttu-id="3d823-116">Syntex 模型檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="3d823-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="3d823-117">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3d823-117">Request headers</span></span>

| <span data-ttu-id="3d823-118">頁首</span><span class="sxs-lookup"><span data-stu-id="3d823-118">Header</span></span> | <span data-ttu-id="3d823-119">值</span><span class="sxs-lookup"><span data-stu-id="3d823-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="3d823-120">Accept</span><span class="sxs-lookup"><span data-stu-id="3d823-120">Accept</span></span>|<span data-ttu-id="3d823-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="3d823-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="3d823-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3d823-122">Content-Type</span></span>|<span data-ttu-id="3d823-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="3d823-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="3d823-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="3d823-124">x-requestdigest</span></span>|<span data-ttu-id="3d823-125">目前網站的適當摘要。</span><span class="sxs-lookup"><span data-stu-id="3d823-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="3d823-126">要求內文</span><span class="sxs-lookup"><span data-stu-id="3d823-126">Request body</span></span>

|<span data-ttu-id="3d823-127">名稱</span><span class="sxs-lookup"><span data-stu-id="3d823-127">Name</span></span>    |<span data-ttu-id="3d823-128">類型</span><span class="sxs-lookup"><span data-stu-id="3d823-128">Type</span></span>   |<span data-ttu-id="3d823-129">描述</span><span class="sxs-lookup"><span data-stu-id="3d823-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="3d823-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="3d823-130">ModelSettings</span></span>|<span data-ttu-id="3d823-131">string</span><span class="sxs-lookup"><span data-stu-id="3d823-131">string</span></span>|<span data-ttu-id="3d823-132">模型設定 JSON。</span><span class="sxs-lookup"><span data-stu-id="3d823-132">JSON of model settings.</span></span>|
|<span data-ttu-id="3d823-133">描述</span><span class="sxs-lookup"><span data-stu-id="3d823-133">Description</span></span>|<span data-ttu-id="3d823-134">string</span><span class="sxs-lookup"><span data-stu-id="3d823-134">string</span></span>|<span data-ttu-id="3d823-135">模型描述。</span><span class="sxs-lookup"><span data-stu-id="3d823-135">The model description.</span></span>|
|<span data-ttu-id="3d823-136">保留標籤</span><span class="sxs-lookup"><span data-stu-id="3d823-136">RetentionLabel</span></span>| |<span data-ttu-id="3d823-137">相關聯標籤的資訊 (標籤識別碼和名稱)。</span><span class="sxs-lookup"><span data-stu-id="3d823-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="3d823-138">回應</span><span class="sxs-lookup"><span data-stu-id="3d823-138">Responses</span></span>

| <span data-ttu-id="3d823-139">名稱</span><span class="sxs-lookup"><span data-stu-id="3d823-139">Name</span></span>   | <span data-ttu-id="3d823-140">類型</span><span class="sxs-lookup"><span data-stu-id="3d823-140">Type</span></span>  | <span data-ttu-id="3d823-141">描述</span><span class="sxs-lookup"><span data-stu-id="3d823-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="3d823-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="3d823-142">200 OK</span></span>| |<span data-ttu-id="3d823-143">成功</span><span class="sxs-lookup"><span data-stu-id="3d823-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="3d823-144">範例</span><span class="sxs-lookup"><span data-stu-id="3d823-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="3d823-145">更新 Contoso 合約的模型設定</span><span class="sxs-lookup"><span data-stu-id="3d823-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="3d823-146">在此範例中，模型描述和「標準保留」保留標籤會更新。</span><span class="sxs-lookup"><span data-stu-id="3d823-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="3d823-147">保留標籤的識別碼為 `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`。</span><span class="sxs-lookup"><span data-stu-id="3d823-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="3d823-148">範例要求</span><span class="sxs-lookup"><span data-stu-id="3d823-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="3d823-149">範例回應</span><span class="sxs-lookup"><span data-stu-id="3d823-149">Sample response</span></span>

<span data-ttu-id="3d823-150">**狀態碼：** 200</span><span class="sxs-lookup"><span data-stu-id="3d823-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="3d823-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3d823-151">See also</span></span>

[<span data-ttu-id="3d823-152">Syntex 文件瞭解模型 REST API</span><span class="sxs-lookup"><span data-stu-id="3d823-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
