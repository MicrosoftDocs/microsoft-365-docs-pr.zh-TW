---
title: Microsoft 365Defender 高級搜尋 API
description: 瞭解如何使用 Microsoft 365 Defender 的高級搜尋 API 執行高級搜尋查詢
keywords: 高級搜尋、APIs、api、M365 defender、Microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769582"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="df8cf-104">Microsoft 365Defender 高級搜尋 API</span><span class="sxs-lookup"><span data-stu-id="df8cf-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="df8cf-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="df8cf-105">**Applies to:**</span></span>

- <span data-ttu-id="df8cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df8cf-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df8cf-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="df8cf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="df8cf-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="df8cf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="df8cf-109">「[高級搜尋](advanced-hunting-overview.md)」是一個威脅搜尋工具，使用[專門構造的查詢](advanced-hunting-query-language.md)來檢查過去30天中 Microsoft 365 Defender 的事件資料。</span><span class="sxs-lookup"><span data-stu-id="df8cf-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="df8cf-110">您可以使用高級搜尋查詢檢查不尋常的活動、偵測可能的威脅，甚至回應攻擊。</span><span class="sxs-lookup"><span data-stu-id="df8cf-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="df8cf-111">Advanced 搜尋 API 可讓您以程式設計方式查詢事件資料。</span><span class="sxs-lookup"><span data-stu-id="df8cf-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="df8cf-112">配額和資源配置</span><span class="sxs-lookup"><span data-stu-id="df8cf-112">Quotas and resource allocation</span></span>

<span data-ttu-id="df8cf-113">下列條件會與所有查詢相關。</span><span class="sxs-lookup"><span data-stu-id="df8cf-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="df8cf-114">查詢會探索和傳回過去30天的資料。</span><span class="sxs-lookup"><span data-stu-id="df8cf-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="df8cf-115">結果最多可返回100000列。</span><span class="sxs-lookup"><span data-stu-id="df8cf-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="df8cf-116">每個租使用者最多可讓15個通話每分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="df8cf-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="df8cf-117">如果租使用者到達100%，直到接下來的15分鐘週期過後，便會封鎖查詢。</span><span class="sxs-lookup"><span data-stu-id="df8cf-117">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span>
5. <span data-ttu-id="df8cf-118">如果單一要求的執行時間超過10分鐘，它會超時並傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="df8cf-118">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
6. <span data-ttu-id="df8cf-119">`429`HTTP 回應碼表示您已到達配額（按傳送的要求數目，或已分派的執行時間）。</span><span class="sxs-lookup"><span data-stu-id="df8cf-119">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="df8cf-120">請閱讀回應本文，以瞭解您已達到的限制。</span><span class="sxs-lookup"><span data-stu-id="df8cf-120">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="df8cf-121">以上所列的所有配額 (例如每個承租人大小每分鐘15個通話) 。</span><span class="sxs-lookup"><span data-stu-id="df8cf-121">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="df8cf-122">這些配額是最小值。</span><span class="sxs-lookup"><span data-stu-id="df8cf-122">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="df8cf-123">權限</span><span class="sxs-lookup"><span data-stu-id="df8cf-123">Permissions</span></span>

<span data-ttu-id="df8cf-124">需要有下列其中一個許可權，才能呼叫高級搜尋 API。</span><span class="sxs-lookup"><span data-stu-id="df8cf-124">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="df8cf-125">若要深入瞭解，包括如何選擇許可權，請參閱[Access the Microsoft 365 Defender Protection APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="df8cf-125">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="df8cf-126">許可權類型</span><span class="sxs-lookup"><span data-stu-id="df8cf-126">Permission type</span></span> | <span data-ttu-id="df8cf-127">權限</span><span class="sxs-lookup"><span data-stu-id="df8cf-127">Permission</span></span> | <span data-ttu-id="df8cf-128">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="df8cf-128">Permission display name</span></span>
-|-|-
<span data-ttu-id="df8cf-129">應用程式</span><span class="sxs-lookup"><span data-stu-id="df8cf-129">Application</span></span> | <span data-ttu-id="df8cf-130">AdvancedHunting Read。 All</span><span class="sxs-lookup"><span data-stu-id="df8cf-130">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="df8cf-131">執行高級查詢</span><span class="sxs-lookup"><span data-stu-id="df8cf-131">Run advanced queries</span></span>
<span data-ttu-id="df8cf-132">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="df8cf-132">Delegated (work or school account)</span></span> | <span data-ttu-id="df8cf-133">AdvancedHunting 讀取</span><span class="sxs-lookup"><span data-stu-id="df8cf-133">AdvancedHunting.Read</span></span> | <span data-ttu-id="df8cf-134">執行高級查詢</span><span class="sxs-lookup"><span data-stu-id="df8cf-134">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="df8cf-135">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="df8cf-135">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="df8cf-136">使用者必須具有「查看資料 ' AD 角色</span><span class="sxs-lookup"><span data-stu-id="df8cf-136">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="df8cf-137">使用者必須根據裝置群組設定，才能存取裝置。</span><span class="sxs-lookup"><span data-stu-id="df8cf-137">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="df8cf-138">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="df8cf-138">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="df8cf-139">要求標頭</span><span class="sxs-lookup"><span data-stu-id="df8cf-139">Request headers</span></span>

<span data-ttu-id="df8cf-140">頁首</span><span class="sxs-lookup"><span data-stu-id="df8cf-140">Header</span></span> | <span data-ttu-id="df8cf-141">值</span><span class="sxs-lookup"><span data-stu-id="df8cf-141">Value</span></span>
-|-
<span data-ttu-id="df8cf-142">授權</span><span class="sxs-lookup"><span data-stu-id="df8cf-142">Authorization</span></span> | <span data-ttu-id="df8cf-143">載荷 {token} **附注：必要**</span><span class="sxs-lookup"><span data-stu-id="df8cf-143">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="df8cf-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="df8cf-144">Content-Type</span></span> | <span data-ttu-id="df8cf-145">application/json</span><span class="sxs-lookup"><span data-stu-id="df8cf-145">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="df8cf-146">要求正文</span><span class="sxs-lookup"><span data-stu-id="df8cf-146">Request body</span></span>

<span data-ttu-id="df8cf-147">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="df8cf-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="df8cf-148">參數</span><span class="sxs-lookup"><span data-stu-id="df8cf-148">Parameter</span></span> | <span data-ttu-id="df8cf-149">類型</span><span class="sxs-lookup"><span data-stu-id="df8cf-149">Type</span></span> | <span data-ttu-id="df8cf-150">描述</span><span class="sxs-lookup"><span data-stu-id="df8cf-150">Description</span></span>
-|-|-
<span data-ttu-id="df8cf-151">查詢</span><span class="sxs-lookup"><span data-stu-id="df8cf-151">Query</span></span> | <span data-ttu-id="df8cf-152">文字</span><span class="sxs-lookup"><span data-stu-id="df8cf-152">Text</span></span> | <span data-ttu-id="df8cf-153">要執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="df8cf-153">The query to run.</span></span> <span data-ttu-id="df8cf-154">**附注：必要**</span><span class="sxs-lookup"><span data-stu-id="df8cf-154">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="df8cf-155">回應</span><span class="sxs-lookup"><span data-stu-id="df8cf-155">Response</span></span>

<span data-ttu-id="df8cf-156">如果成功，此方法將會傳回 `200 OK` ，以及回應內文中的 _QueryResponse_ 物件。</span><span class="sxs-lookup"><span data-stu-id="df8cf-156">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="df8cf-157">Response 物件包含三個最上層的屬性：</span><span class="sxs-lookup"><span data-stu-id="df8cf-157">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="df8cf-158">Stats-查詢效能統計資料的字典。</span><span class="sxs-lookup"><span data-stu-id="df8cf-158">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="df8cf-159">架構-回應的架構，每個資料欄的 Name-Type 對的清單。</span><span class="sxs-lookup"><span data-stu-id="df8cf-159">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="df8cf-160">結果-高級搜尋事件清單。</span><span class="sxs-lookup"><span data-stu-id="df8cf-160">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="df8cf-161">範例</span><span class="sxs-lookup"><span data-stu-id="df8cf-161">Example</span></span>

<span data-ttu-id="df8cf-162">在下列範例中，使用者會傳送下列查詢並接收包含、和的 API 回應 `Stats` 物件 `Schema` `Results` 。</span><span class="sxs-lookup"><span data-stu-id="df8cf-162">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="df8cf-163">查詢</span><span class="sxs-lookup"><span data-stu-id="df8cf-163">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="df8cf-164">Response 物件</span><span class="sxs-lookup"><span data-stu-id="df8cf-164">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="df8cf-165">相關文章</span><span class="sxs-lookup"><span data-stu-id="df8cf-165">Related articles</span></span>

- [<span data-ttu-id="df8cf-166">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="df8cf-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="df8cf-167">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="df8cf-167">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="df8cf-168">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="df8cf-168">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="df8cf-169">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="df8cf-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
