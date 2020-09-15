---
title: 高級搜尋 APIs
description: 瞭解如何使用 Microsoft 威脅防護 API 執行高級搜尋查詢
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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650216"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="e0332-104">高級搜尋 APIs</span><span class="sxs-lookup"><span data-stu-id="e0332-104">Advanced hunting APIs</span></span>

<span data-ttu-id="e0332-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e0332-105">**Applies to:**</span></span>
- <span data-ttu-id="e0332-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="e0332-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e0332-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="e0332-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e0332-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e0332-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="e0332-109">限制</span><span class="sxs-lookup"><span data-stu-id="e0332-109">Limitations</span></span>
1. <span data-ttu-id="e0332-110">您只可對過去30天的資料執行查詢。</span><span class="sxs-lookup"><span data-stu-id="e0332-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="e0332-111">結果最多會包含100000列。</span><span class="sxs-lookup"><span data-stu-id="e0332-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="e0332-112">執行數目限制為每個租使用者：每分鐘最多15個通話、每小時15分鐘的執行時間，以及一天的執行時間的4小時。</span><span class="sxs-lookup"><span data-stu-id="e0332-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="e0332-113">單一要求的最長執行時間為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="e0332-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="e0332-114">權限</span><span class="sxs-lookup"><span data-stu-id="e0332-114">Permissions</span></span>
<span data-ttu-id="e0332-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="e0332-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e0332-116">若要深入瞭解，包括如何選擇許可權，請參閱 [Access The Microsoft 威脅防護 APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="e0332-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="e0332-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="e0332-117">Permission type</span></span> |   <span data-ttu-id="e0332-118">權限</span><span class="sxs-lookup"><span data-stu-id="e0332-118">Permission</span></span>  |   <span data-ttu-id="e0332-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="e0332-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e0332-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="e0332-120">Application</span></span> |   <span data-ttu-id="e0332-121">AdvancedHunting Read。 All</span><span class="sxs-lookup"><span data-stu-id="e0332-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="e0332-122">「執行高級查詢」</span><span class="sxs-lookup"><span data-stu-id="e0332-122">'Run advanced queries'</span></span>
<span data-ttu-id="e0332-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="e0332-123">Delegated (work or school account)</span></span> | <span data-ttu-id="e0332-124">AdvancedHunting 讀取</span><span class="sxs-lookup"><span data-stu-id="e0332-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="e0332-125">「執行高級查詢」</span><span class="sxs-lookup"><span data-stu-id="e0332-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="e0332-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="e0332-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e0332-127">使用者必須具有「查看資料 ' AD 角色</span><span class="sxs-lookup"><span data-stu-id="e0332-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="e0332-128">使用者必須根據裝置群組設定，才能存取裝置。</span><span class="sxs-lookup"><span data-stu-id="e0332-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="e0332-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="e0332-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="e0332-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="e0332-130">Request headers</span></span>

<span data-ttu-id="e0332-131">Header</span><span class="sxs-lookup"><span data-stu-id="e0332-131">Header</span></span> | <span data-ttu-id="e0332-132">值</span><span class="sxs-lookup"><span data-stu-id="e0332-132">Value</span></span> 
:---|:---
<span data-ttu-id="e0332-133">授權</span><span class="sxs-lookup"><span data-stu-id="e0332-133">Authorization</span></span> | <span data-ttu-id="e0332-134">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="e0332-134">Bearer {token}.</span></span> <span data-ttu-id="e0332-135">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="e0332-135">**Required**.</span></span>
<span data-ttu-id="e0332-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e0332-136">Content-Type</span></span>    | <span data-ttu-id="e0332-137">application/json</span><span class="sxs-lookup"><span data-stu-id="e0332-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="e0332-138">要求正文</span><span class="sxs-lookup"><span data-stu-id="e0332-138">Request body</span></span>
<span data-ttu-id="e0332-139">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="e0332-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="e0332-140">參數</span><span class="sxs-lookup"><span data-stu-id="e0332-140">Parameter</span></span> | <span data-ttu-id="e0332-141">類型</span><span class="sxs-lookup"><span data-stu-id="e0332-141">Type</span></span>    | <span data-ttu-id="e0332-142">描述</span><span class="sxs-lookup"><span data-stu-id="e0332-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="e0332-143">查詢</span><span class="sxs-lookup"><span data-stu-id="e0332-143">Query</span></span> | <span data-ttu-id="e0332-144">文字</span><span class="sxs-lookup"><span data-stu-id="e0332-144">Text</span></span> |  <span data-ttu-id="e0332-145">要執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="e0332-145">The query to run.</span></span> <span data-ttu-id="e0332-146">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="e0332-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="e0332-147">回應</span><span class="sxs-lookup"><span data-stu-id="e0332-147">Response</span></span>
<span data-ttu-id="e0332-148">如果成功，這個方法會傳回 200 OK，並在回應內文中 _QueryResponse_ 物件。</span><span class="sxs-lookup"><span data-stu-id="e0332-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="e0332-149">Response 物件會劃分成3個部分 (屬性) ：</span><span class="sxs-lookup"><span data-stu-id="e0332-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="e0332-150">```Stats``` -查詢效能統計資料。</span><span class="sxs-lookup"><span data-stu-id="e0332-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="e0332-151">```Schema``` -回應的架構，每個資料行的名稱類型組的清單。</span><span class="sxs-lookup"><span data-stu-id="e0332-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="e0332-152">```Results``` -高級搜尋事件清單。</span><span class="sxs-lookup"><span data-stu-id="e0332-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="e0332-153">範例</span><span class="sxs-lookup"><span data-stu-id="e0332-153">Example</span></span>

<span data-ttu-id="e0332-154">請求</span><span class="sxs-lookup"><span data-stu-id="e0332-154">Request</span></span>

<span data-ttu-id="e0332-155">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="e0332-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="e0332-156">回應</span><span class="sxs-lookup"><span data-stu-id="e0332-156">Response</span></span>

<span data-ttu-id="e0332-157">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="e0332-157">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="e0332-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="e0332-158">Related topic</span></span>
- [<span data-ttu-id="e0332-159">存取 Microsoft 威脅防護 APIs</span><span class="sxs-lookup"><span data-stu-id="e0332-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
