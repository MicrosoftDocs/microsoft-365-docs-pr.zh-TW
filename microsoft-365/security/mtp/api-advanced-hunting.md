---
title: 高級搜尋 APIs
description: 瞭解如何使用 Microsoft 365 Defender API 執行高級搜尋查詢
keywords: 高級搜尋、APIs、api、MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844029"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="fc577-104">高級搜尋 APIs</span><span class="sxs-lookup"><span data-stu-id="fc577-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fc577-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="fc577-105">**Applies to:**</span></span>
- <span data-ttu-id="fc577-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc577-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="fc577-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="fc577-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fc577-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="fc577-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="fc577-109">限制</span><span class="sxs-lookup"><span data-stu-id="fc577-109">Limitations</span></span>
1. <span data-ttu-id="fc577-110">您只可對過去30天的資料執行查詢。</span><span class="sxs-lookup"><span data-stu-id="fc577-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="fc577-111">結果最多會包含100000列。</span><span class="sxs-lookup"><span data-stu-id="fc577-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="fc577-112">執行數目會限制于每個承租人：每分鐘最多10個通話量、每小時10分鐘的執行時間，以及一天的執行時間的4小時的執行時間。</span><span class="sxs-lookup"><span data-stu-id="fc577-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="fc577-113">單一要求的最長執行時間為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="fc577-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="fc577-114">429回應會以要求數目或 CPU 來表示達到配額限制。</span><span class="sxs-lookup"><span data-stu-id="fc577-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="fc577-115">429回應內文也會指出在更新配額之前所用的時間。</span><span class="sxs-lookup"><span data-stu-id="fc577-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="fc577-116">權限</span><span class="sxs-lookup"><span data-stu-id="fc577-116">Permissions</span></span>
<span data-ttu-id="fc577-117">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="fc577-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fc577-118">若要深入瞭解，包括如何選擇許可權，請參閱 [Access The Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="fc577-118">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="fc577-119">許可權類型</span><span class="sxs-lookup"><span data-stu-id="fc577-119">Permission type</span></span> |   <span data-ttu-id="fc577-120">權限</span><span class="sxs-lookup"><span data-stu-id="fc577-120">Permission</span></span>  |   <span data-ttu-id="fc577-121">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="fc577-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fc577-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="fc577-122">Application</span></span> |   <span data-ttu-id="fc577-123">AdvancedHunting Read。 All</span><span class="sxs-lookup"><span data-stu-id="fc577-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="fc577-124">「執行高級查詢」</span><span class="sxs-lookup"><span data-stu-id="fc577-124">'Run advanced queries'</span></span>
<span data-ttu-id="fc577-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="fc577-125">Delegated (work or school account)</span></span> | <span data-ttu-id="fc577-126">AdvancedHunting 讀取</span><span class="sxs-lookup"><span data-stu-id="fc577-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="fc577-127">「執行高級查詢」</span><span class="sxs-lookup"><span data-stu-id="fc577-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="fc577-128">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="fc577-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="fc577-129">使用者必須具有「查看資料 ' AD 角色</span><span class="sxs-lookup"><span data-stu-id="fc577-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="fc577-130">使用者必須根據裝置群組設定，才能存取裝置。</span><span class="sxs-lookup"><span data-stu-id="fc577-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="fc577-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="fc577-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="fc577-132">要求標頭</span><span class="sxs-lookup"><span data-stu-id="fc577-132">Request headers</span></span>

<span data-ttu-id="fc577-133">Header</span><span class="sxs-lookup"><span data-stu-id="fc577-133">Header</span></span> | <span data-ttu-id="fc577-134">值</span><span class="sxs-lookup"><span data-stu-id="fc577-134">Value</span></span> 
:---|:---
<span data-ttu-id="fc577-135">授權</span><span class="sxs-lookup"><span data-stu-id="fc577-135">Authorization</span></span> | <span data-ttu-id="fc577-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="fc577-136">Bearer {token}.</span></span> <span data-ttu-id="fc577-137">**必要欄位** 。</span><span class="sxs-lookup"><span data-stu-id="fc577-137">**Required**.</span></span>
<span data-ttu-id="fc577-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="fc577-138">Content-Type</span></span>    | <span data-ttu-id="fc577-139">application/json</span><span class="sxs-lookup"><span data-stu-id="fc577-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="fc577-140">要求正文</span><span class="sxs-lookup"><span data-stu-id="fc577-140">Request body</span></span>
<span data-ttu-id="fc577-141">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="fc577-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="fc577-142">參數</span><span class="sxs-lookup"><span data-stu-id="fc577-142">Parameter</span></span> | <span data-ttu-id="fc577-143">類型</span><span class="sxs-lookup"><span data-stu-id="fc577-143">Type</span></span>    | <span data-ttu-id="fc577-144">描述</span><span class="sxs-lookup"><span data-stu-id="fc577-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="fc577-145">查詢</span><span class="sxs-lookup"><span data-stu-id="fc577-145">Query</span></span> | <span data-ttu-id="fc577-146">文字</span><span class="sxs-lookup"><span data-stu-id="fc577-146">Text</span></span> |  <span data-ttu-id="fc577-147">要執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="fc577-147">The query to run.</span></span> <span data-ttu-id="fc577-148">**必要欄位** 。</span><span class="sxs-lookup"><span data-stu-id="fc577-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="fc577-149">回應</span><span class="sxs-lookup"><span data-stu-id="fc577-149">Response</span></span>
<span data-ttu-id="fc577-150">如果成功，這個方法會傳回 200 OK，並在回應內文中 _QueryResponse_ 物件。</span><span class="sxs-lookup"><span data-stu-id="fc577-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="fc577-151">Response 物件會劃分成3個部分 (屬性) ：</span><span class="sxs-lookup"><span data-stu-id="fc577-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="fc577-152">```Stats``` -查詢效能統計資料。</span><span class="sxs-lookup"><span data-stu-id="fc577-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="fc577-153">```Schema``` -回應的架構，每一欄的 Name-Type 組的清單。</span><span class="sxs-lookup"><span data-stu-id="fc577-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="fc577-154">```Results``` -高級搜尋事件清單。</span><span class="sxs-lookup"><span data-stu-id="fc577-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="fc577-155">範例</span><span class="sxs-lookup"><span data-stu-id="fc577-155">Example</span></span>

<span data-ttu-id="fc577-156">請求</span><span class="sxs-lookup"><span data-stu-id="fc577-156">Request</span></span>

<span data-ttu-id="fc577-157">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="fc577-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="fc577-158">回應</span><span class="sxs-lookup"><span data-stu-id="fc577-158">Response</span></span>

<span data-ttu-id="fc577-159">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="fc577-159">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="fc577-160">相關主題</span><span class="sxs-lookup"><span data-stu-id="fc577-160">Related topic</span></span>
- [<span data-ttu-id="fc577-161">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="fc577-161">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
