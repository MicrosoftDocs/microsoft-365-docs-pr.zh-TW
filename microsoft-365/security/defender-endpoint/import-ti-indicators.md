---
title: 匯入指示器 API
description: 瞭解如何在 Microsoft Defender for Endpoint 中使用指示器 API 的匯入批次。
keywords: api，支援的 api，submit，ti，指示器，更新
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198242"
---
# <a name="import-indicators-api"></a><span data-ttu-id="33e84-104">匯入指示器 API</span><span class="sxs-lookup"><span data-stu-id="33e84-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="33e84-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="33e84-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="33e84-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="33e84-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="33e84-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="33e84-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="33e84-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="33e84-108">API description</span></span>
<span data-ttu-id="33e84-109">提交或更新 [指示器](ti-indicator.md) 實體的批次。</span><span class="sxs-lookup"><span data-stu-id="33e84-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="33e84-110">不支援 IPs 的 CIDR 標記法。</span><span class="sxs-lookup"><span data-stu-id="33e84-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="33e84-111">限制</span><span class="sxs-lookup"><span data-stu-id="33e84-111">Limitations</span></span>
1. <span data-ttu-id="33e84-112">此 API 的速率限制為每分鐘30個通話。</span><span class="sxs-lookup"><span data-stu-id="33e84-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="33e84-113">每個租使用者的活動 [指示器](ti-indicator.md) 限制為15000。</span><span class="sxs-lookup"><span data-stu-id="33e84-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="33e84-114">一個 API 呼叫的批次大小上限為500。</span><span class="sxs-lookup"><span data-stu-id="33e84-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="33e84-115">權限</span><span class="sxs-lookup"><span data-stu-id="33e84-115">Permissions</span></span>
<span data-ttu-id="33e84-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="33e84-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="33e84-117">若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="33e84-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="33e84-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="33e84-118">Permission type</span></span> |   <span data-ttu-id="33e84-119">權限</span><span class="sxs-lookup"><span data-stu-id="33e84-119">Permission</span></span>  |   <span data-ttu-id="33e84-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="33e84-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="33e84-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="33e84-121">Application</span></span> |   <span data-ttu-id="33e84-122">Ti ReadWrite</span><span class="sxs-lookup"><span data-stu-id="33e84-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="33e84-123">「讀取和寫入指示器」</span><span class="sxs-lookup"><span data-stu-id="33e84-123">'Read and write Indicators'</span></span>
<span data-ttu-id="33e84-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="33e84-124">Application</span></span> |   <span data-ttu-id="33e84-125">Ti ReadWrite 所有</span><span class="sxs-lookup"><span data-stu-id="33e84-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="33e84-126">「讀取及寫入所有指示器」</span><span class="sxs-lookup"><span data-stu-id="33e84-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="33e84-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="33e84-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="33e84-128">Ti ReadWrite</span><span class="sxs-lookup"><span data-stu-id="33e84-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="33e84-129">「讀取和寫入指示器」</span><span class="sxs-lookup"><span data-stu-id="33e84-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="33e84-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="33e84-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="33e84-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="33e84-131">Request headers</span></span>

<span data-ttu-id="33e84-132">名稱</span><span class="sxs-lookup"><span data-stu-id="33e84-132">Name</span></span> | <span data-ttu-id="33e84-133">類型</span><span class="sxs-lookup"><span data-stu-id="33e84-133">Type</span></span> | <span data-ttu-id="33e84-134">描述</span><span class="sxs-lookup"><span data-stu-id="33e84-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="33e84-135">授權</span><span class="sxs-lookup"><span data-stu-id="33e84-135">Authorization</span></span> | <span data-ttu-id="33e84-136">字串</span><span class="sxs-lookup"><span data-stu-id="33e84-136">String</span></span> | <span data-ttu-id="33e84-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="33e84-137">Bearer {token}.</span></span> <span data-ttu-id="33e84-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="33e84-138">**Required**.</span></span>
<span data-ttu-id="33e84-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="33e84-139">Content-Type</span></span> | <span data-ttu-id="33e84-140">string</span><span class="sxs-lookup"><span data-stu-id="33e84-140">string</span></span> | <span data-ttu-id="33e84-141">application/json。</span><span class="sxs-lookup"><span data-stu-id="33e84-141">application/json.</span></span> <span data-ttu-id="33e84-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="33e84-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="33e84-143">要求正文</span><span class="sxs-lookup"><span data-stu-id="33e84-143">Request body</span></span>
<span data-ttu-id="33e84-144">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="33e84-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="33e84-145">參數</span><span class="sxs-lookup"><span data-stu-id="33e84-145">Parameter</span></span> | <span data-ttu-id="33e84-146">類型</span><span class="sxs-lookup"><span data-stu-id="33e84-146">Type</span></span>    | <span data-ttu-id="33e84-147">描述</span><span class="sxs-lookup"><span data-stu-id="33e84-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="33e84-148">指標</span><span class="sxs-lookup"><span data-stu-id="33e84-148">Indicators</span></span> | <span data-ttu-id="33e84-149">清單<[指示器](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="33e84-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="33e84-150">[指示器](ti-indicator.md)清單。</span><span class="sxs-lookup"><span data-stu-id="33e84-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="33e84-151">**Required**</span><span class="sxs-lookup"><span data-stu-id="33e84-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="33e84-152">回應</span><span class="sxs-lookup"><span data-stu-id="33e84-152">Response</span></span>
- <span data-ttu-id="33e84-153">如果成功，這個方法會傳回 200-OK 回應碼，其中包含每個指標的匯入結果清單，請參閱下列範例。</span><span class="sxs-lookup"><span data-stu-id="33e84-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="33e84-154">若失敗：此方法會傳回 400-錯誤要求。</span><span class="sxs-lookup"><span data-stu-id="33e84-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="33e84-155">錯誤的要求通常會指出不正確的正文。</span><span class="sxs-lookup"><span data-stu-id="33e84-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="33e84-156">範例</span><span class="sxs-lookup"><span data-stu-id="33e84-156">Example</span></span>

<span data-ttu-id="33e84-157">**請求**</span><span class="sxs-lookup"><span data-stu-id="33e84-157">**Request**</span></span>

<span data-ttu-id="33e84-158">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="33e84-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="33e84-159">**回應**</span><span class="sxs-lookup"><span data-stu-id="33e84-159">**Response**</span></span>

<span data-ttu-id="33e84-160">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="33e84-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="33e84-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="33e84-161">Related topic</span></span>
- [<span data-ttu-id="33e84-162">管理指示器</span><span class="sxs-lookup"><span data-stu-id="33e84-162">Manage indicators</span></span>](manage-indicators.md)
