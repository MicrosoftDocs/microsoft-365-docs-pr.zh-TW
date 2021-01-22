---
title: Microsoft 365 Defender 進位搜尋 API
description: 瞭解如何使用 Microsoft 365 Defender 進位搜尋 API 執行進位搜尋查詢
keywords: 進位搜尋、API、api、MTP、M365 Defender、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4213773c3305c28f0913013d8f7634c083811f52
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932079"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="510c9-104">Microsoft 365 Defender Advanced 搜尋 API</span><span class="sxs-lookup"><span data-stu-id="510c9-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="510c9-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="510c9-105">**Applies to:**</span></span>

- <span data-ttu-id="510c9-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="510c9-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="510c9-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="510c9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="510c9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="510c9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="510c9-109">[進位](advanced-hunting-overview.md) 搜尋是威脅搜尋工具，使用 [特殊](advanced-hunting-query-language.md) 建構的查詢來檢查過去 30 天 Microsoft 365 Defender 中的事件資料。</span><span class="sxs-lookup"><span data-stu-id="510c9-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="510c9-110">您可以使用進一步搜尋查詢來檢查異常活動、偵測可能的威脅，甚至回應攻擊。</span><span class="sxs-lookup"><span data-stu-id="510c9-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="510c9-111">進位搜尋 API 可讓您程式化查詢事件資料。</span><span class="sxs-lookup"><span data-stu-id="510c9-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="510c9-112">配額和資源配置</span><span class="sxs-lookup"><span data-stu-id="510c9-112">Quotas and resource allocation</span></span>

<span data-ttu-id="510c9-113">下列條件會與其他查詢相關。</span><span class="sxs-lookup"><span data-stu-id="510c9-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="510c9-114">查詢會探索並返回過去 30 天的資料。</span><span class="sxs-lookup"><span data-stu-id="510c9-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="510c9-115">結果可返回最多 100，000 列。</span><span class="sxs-lookup"><span data-stu-id="510c9-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="510c9-116">您每一個租使用者每分鐘可以撥打多達 10 個通話。</span><span class="sxs-lookup"><span data-stu-id="510c9-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="510c9-117">每個租使用者每小時有 10 分鐘的執行時間。</span><span class="sxs-lookup"><span data-stu-id="510c9-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="510c9-118">每個租使用者都有四個總執行時間。</span><span class="sxs-lookup"><span data-stu-id="510c9-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="510c9-119">如果單一要求執行時間超過 10 分鐘，就會將時間用完並退回錯誤。</span><span class="sxs-lookup"><span data-stu-id="510c9-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="510c9-120">HTTP 回應碼表示您已達到配額，可以是已傳送的要求數，或是已分配 `429` 執行時間。</span><span class="sxs-lookup"><span data-stu-id="510c9-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="510c9-121">回復內體會包含重設您達到之配額之前的時間。</span><span class="sxs-lookup"><span data-stu-id="510c9-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="510c9-122">權限</span><span class="sxs-lookup"><span data-stu-id="510c9-122">Permissions</span></span>

<span data-ttu-id="510c9-123">需要下列其中一個許可權才能呼叫進一步搜尋 API。</span><span class="sxs-lookup"><span data-stu-id="510c9-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="510c9-124">若要深入瞭解，包括如何選擇許可權，請參閱 [存取 Microsoft 365 Defender Protection API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="510c9-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="510c9-125">許可權類型</span><span class="sxs-lookup"><span data-stu-id="510c9-125">Permission type</span></span> | <span data-ttu-id="510c9-126">權限</span><span class="sxs-lookup"><span data-stu-id="510c9-126">Permission</span></span> | <span data-ttu-id="510c9-127">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="510c9-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="510c9-128">應用程式</span><span class="sxs-lookup"><span data-stu-id="510c9-128">Application</span></span> | <span data-ttu-id="510c9-129">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="510c9-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="510c9-130">執行進位查詢</span><span class="sxs-lookup"><span data-stu-id="510c9-130">Run advanced queries</span></span>
<span data-ttu-id="510c9-131">已委派 (公司或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="510c9-131">Delegated (work or school account)</span></span> | <span data-ttu-id="510c9-132">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="510c9-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="510c9-133">執行進位查詢</span><span class="sxs-lookup"><span data-stu-id="510c9-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="510c9-134">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="510c9-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="510c9-135">使用者必須擁有 'View Data' AD 角色</span><span class="sxs-lookup"><span data-stu-id="510c9-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="510c9-136">使用者必須能根據裝置群組設定存取裝置。</span><span class="sxs-lookup"><span data-stu-id="510c9-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="510c9-137">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="510c9-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="510c9-138">要求標頭</span><span class="sxs-lookup"><span data-stu-id="510c9-138">Request headers</span></span>

<span data-ttu-id="510c9-139">Header</span><span class="sxs-lookup"><span data-stu-id="510c9-139">Header</span></span> | <span data-ttu-id="510c9-140">值</span><span class="sxs-lookup"><span data-stu-id="510c9-140">Value</span></span>
-|-
<span data-ttu-id="510c9-141">授權</span><span class="sxs-lookup"><span data-stu-id="510c9-141">Authorization</span></span> | <span data-ttu-id="510c9-142">Bearer {token} **Note： required**</span><span class="sxs-lookup"><span data-stu-id="510c9-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="510c9-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="510c9-143">Content-Type</span></span> | <span data-ttu-id="510c9-144">application/json</span><span class="sxs-lookup"><span data-stu-id="510c9-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="510c9-145">要求內體</span><span class="sxs-lookup"><span data-stu-id="510c9-145">Request body</span></span>

<span data-ttu-id="510c9-146">在要求內文中，提供 JSON 物件與下列參數：</span><span class="sxs-lookup"><span data-stu-id="510c9-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="510c9-147">參數</span><span class="sxs-lookup"><span data-stu-id="510c9-147">Parameter</span></span> | <span data-ttu-id="510c9-148">類型</span><span class="sxs-lookup"><span data-stu-id="510c9-148">Type</span></span> | <span data-ttu-id="510c9-149">說明</span><span class="sxs-lookup"><span data-stu-id="510c9-149">Description</span></span>
-|-|-
<span data-ttu-id="510c9-150">查詢</span><span class="sxs-lookup"><span data-stu-id="510c9-150">Query</span></span> | <span data-ttu-id="510c9-151">文字</span><span class="sxs-lookup"><span data-stu-id="510c9-151">Text</span></span> | <span data-ttu-id="510c9-152">要執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="510c9-152">The query to run.</span></span> <span data-ttu-id="510c9-153">**注意：必填**</span><span class="sxs-lookup"><span data-stu-id="510c9-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="510c9-154">回應</span><span class="sxs-lookup"><span data-stu-id="510c9-154">Response</span></span>

<span data-ttu-id="510c9-155">如果成功，此方法會傳回，且回應本文中會傳回 `200 OK` _QueryResponse_ 物件。</span><span class="sxs-lookup"><span data-stu-id="510c9-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="510c9-156">回應物件包含三個頂層屬性：</span><span class="sxs-lookup"><span data-stu-id="510c9-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="510c9-157">狀態 - 查詢績效統計的字典。</span><span class="sxs-lookup"><span data-stu-id="510c9-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="510c9-158">架構 - 回應的架構，一份每個Name-Type組的清單。</span><span class="sxs-lookup"><span data-stu-id="510c9-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="510c9-159">結果 - 進位搜尋事件的清單。</span><span class="sxs-lookup"><span data-stu-id="510c9-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="510c9-160">範例</span><span class="sxs-lookup"><span data-stu-id="510c9-160">Example</span></span>

<span data-ttu-id="510c9-161">在下列範例中，使用者傳送下列查詢並接收包含 、及 的 API `Stats` `Schema` 回應物件 `Results` 。</span><span class="sxs-lookup"><span data-stu-id="510c9-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="510c9-162">查詢</span><span class="sxs-lookup"><span data-stu-id="510c9-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="510c9-163">回應物件</span><span class="sxs-lookup"><span data-stu-id="510c9-163">Response object</span></span>

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="510c9-164">相關文章</span><span class="sxs-lookup"><span data-stu-id="510c9-164">Related articles</span></span>

- [<span data-ttu-id="510c9-165">存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="510c9-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="510c9-166">瞭解 API 限制與授權</span><span class="sxs-lookup"><span data-stu-id="510c9-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="510c9-167">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="510c9-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="510c9-168">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="510c9-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
