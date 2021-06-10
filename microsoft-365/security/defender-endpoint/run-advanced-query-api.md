---
title: 進階搜捕 API
ms.reviewer: ''
description: 瞭解如何使用高級搜尋 API，在 Microsoft Defender for Endpoint 上執行高級查詢。 深入瞭解限制，並查看範例。
keywords: api、支援的 api、高級搜尋、查詢
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0173e271967a1b5b18d69713e9e6540e9cd11a87
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772398"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="79f07-105">高級搜尋 API</span><span class="sxs-lookup"><span data-stu-id="79f07-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="79f07-106">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="79f07-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="79f07-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="79f07-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="79f07-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="79f07-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="79f07-109">限制</span><span class="sxs-lookup"><span data-stu-id="79f07-109">Limitations</span></span>

1. <span data-ttu-id="79f07-110">您只可對過去30天的資料執行查詢。</span><span class="sxs-lookup"><span data-stu-id="79f07-110">You can only run a query on data from the last 30 days.</span></span>

2. <span data-ttu-id="79f07-111">結果最多會包含100000列。</span><span class="sxs-lookup"><span data-stu-id="79f07-111">The results will include a maximum of 100,000 rows.</span></span>

3. <span data-ttu-id="79f07-112">每個租使用者的執行數目有限：</span><span class="sxs-lookup"><span data-stu-id="79f07-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="79f07-113">API 呼叫：每分鐘最多45個通話，每小時最多1500個通話。</span><span class="sxs-lookup"><span data-stu-id="79f07-113">API calls: Up to 45 calls per minute, up to 1500 calls per hour.</span></span>
   - <span data-ttu-id="79f07-114">執行時間：每小時10分鐘的執行時間，以及一天的執行時間的3個小時的執行時間。</span><span class="sxs-lookup"><span data-stu-id="79f07-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>

4. <span data-ttu-id="79f07-115">單一要求的最長執行時間為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="79f07-115">The maximal execution time of a single request is 10 minutes.</span></span>

5. <span data-ttu-id="79f07-116">429回應會以要求數目或 CPU 來表示達到配額限制。</span><span class="sxs-lookup"><span data-stu-id="79f07-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="79f07-117">閱讀回應正文，以瞭解已達到的限制。</span><span class="sxs-lookup"><span data-stu-id="79f07-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="79f07-118">權限</span><span class="sxs-lookup"><span data-stu-id="79f07-118">Permissions</span></span>

<span data-ttu-id="79f07-119">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="79f07-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="79f07-120">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="79f07-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="79f07-121">許可權類型</span><span class="sxs-lookup"><span data-stu-id="79f07-121">Permission type</span></span> |   <span data-ttu-id="79f07-122">權限</span><span class="sxs-lookup"><span data-stu-id="79f07-122">Permission</span></span>  |   <span data-ttu-id="79f07-123">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="79f07-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="79f07-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="79f07-124">Application</span></span> |   <span data-ttu-id="79f07-125">AdvancedQuery Read。 All</span><span class="sxs-lookup"><span data-stu-id="79f07-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="79f07-126">「執行高級查詢」</span><span class="sxs-lookup"><span data-stu-id="79f07-126">'Run advanced queries'</span></span>
<span data-ttu-id="79f07-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="79f07-127">Delegated (work or school account)</span></span> | <span data-ttu-id="79f07-128">AdvancedQuery 讀取</span><span class="sxs-lookup"><span data-stu-id="79f07-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="79f07-129">「執行高級查詢」</span><span class="sxs-lookup"><span data-stu-id="79f07-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="79f07-130">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="79f07-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="79f07-131">使用者必須具有「查看資料 ' AD 角色</span><span class="sxs-lookup"><span data-stu-id="79f07-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="79f07-132">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="79f07-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="79f07-133">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="79f07-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="79f07-134">要求標頭</span><span class="sxs-lookup"><span data-stu-id="79f07-134">Request headers</span></span>

<span data-ttu-id="79f07-135">頁首</span><span class="sxs-lookup"><span data-stu-id="79f07-135">Header</span></span> | <span data-ttu-id="79f07-136">值</span><span class="sxs-lookup"><span data-stu-id="79f07-136">Value</span></span> 
:---|:---
<span data-ttu-id="79f07-137">授權</span><span class="sxs-lookup"><span data-stu-id="79f07-137">Authorization</span></span> | <span data-ttu-id="79f07-138">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="79f07-138">Bearer {token}.</span></span> <span data-ttu-id="79f07-139">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="79f07-139">**Required**.</span></span>
<span data-ttu-id="79f07-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="79f07-140">Content-Type</span></span>    | <span data-ttu-id="79f07-141">application/json</span><span class="sxs-lookup"><span data-stu-id="79f07-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="79f07-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="79f07-142">Request body</span></span>

<span data-ttu-id="79f07-143">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="79f07-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="79f07-144">參數</span><span class="sxs-lookup"><span data-stu-id="79f07-144">Parameter</span></span> | <span data-ttu-id="79f07-145">類型</span><span class="sxs-lookup"><span data-stu-id="79f07-145">Type</span></span>    | <span data-ttu-id="79f07-146">描述</span><span class="sxs-lookup"><span data-stu-id="79f07-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="79f07-147">查詢</span><span class="sxs-lookup"><span data-stu-id="79f07-147">Query</span></span> | <span data-ttu-id="79f07-148">文字</span><span class="sxs-lookup"><span data-stu-id="79f07-148">Text</span></span> |  <span data-ttu-id="79f07-149">要執行的查詢。</span><span class="sxs-lookup"><span data-stu-id="79f07-149">The query to run.</span></span> <span data-ttu-id="79f07-150">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="79f07-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="79f07-151">回應</span><span class="sxs-lookup"><span data-stu-id="79f07-151">Response</span></span>

<span data-ttu-id="79f07-152">如果成功，這個方法會傳回 200 OK，並在回應內文中 _QueryResponse_ 物件。</span><span class="sxs-lookup"><span data-stu-id="79f07-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="79f07-153">範例</span><span class="sxs-lookup"><span data-stu-id="79f07-153">Example</span></span>

##### <a name="request"></a><span data-ttu-id="79f07-154">請求</span><span class="sxs-lookup"><span data-stu-id="79f07-154">Request</span></span>

<span data-ttu-id="79f07-155">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="79f07-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a><span data-ttu-id="79f07-156">回應</span><span class="sxs-lookup"><span data-stu-id="79f07-156">Response</span></span>

<span data-ttu-id="79f07-157">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="79f07-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="79f07-158">在這裡顯示的回應物件可能會因簡潔而截斷。</span><span class="sxs-lookup"><span data-stu-id="79f07-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="79f07-159">所有屬性都將從實際通話傳回。</span><span class="sxs-lookup"><span data-stu-id="79f07-159">All of the properties will be returned from an actual call.</span></span>

```json
{
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
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="79f07-160">相關主題</span><span class="sxs-lookup"><span data-stu-id="79f07-160">Related topics</span></span>

- [<span data-ttu-id="79f07-161">Microsoft Defender for Endpoint APIs 簡介</span><span class="sxs-lookup"><span data-stu-id="79f07-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="79f07-162">從入口網站的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="79f07-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="79f07-163">使用 PowerShell 進階搜尋</span><span class="sxs-lookup"><span data-stu-id="79f07-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
