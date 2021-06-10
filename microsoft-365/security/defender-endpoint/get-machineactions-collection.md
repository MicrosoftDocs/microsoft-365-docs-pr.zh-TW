---
title: 清單 machineActions API
description: 瞭解如何使用清單 MachineActions API，在 Microsoft Defender for Endpoint 中檢索電腦動作的集合。
keywords: api，graph api，支援的 api，machineaction 集合
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771114"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="53a18-104">清單 MachineActions API</span><span class="sxs-lookup"><span data-stu-id="53a18-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="53a18-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="53a18-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="53a18-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="53a18-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53a18-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="53a18-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="53a18-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="53a18-108">API description</span></span>
<span data-ttu-id="53a18-109">會檢索 [電腦動作](machineaction.md)的集合。</span><span class="sxs-lookup"><span data-stu-id="53a18-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="53a18-110">支援 [OData V4 查詢](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="53a18-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="53a18-111">支援 OData 的 ```$filter``` 查詢： ```status``` 、、 ```machineId``` ```type``` ```requestor``` 和 ```creationDateTimeUtc``` 屬性。</span><span class="sxs-lookup"><span data-stu-id="53a18-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="53a18-112">請參閱[使用 Microsoft Defender For Endpoint 的 OData 查詢](exposed-apis-odata-samples.md)中的範例</span><span class="sxs-lookup"><span data-stu-id="53a18-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="53a18-113">限制</span><span class="sxs-lookup"><span data-stu-id="53a18-113">Limitations</span></span>
1. <span data-ttu-id="53a18-114">頁面大小上限為10000。</span><span class="sxs-lookup"><span data-stu-id="53a18-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="53a18-115">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="53a18-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="53a18-116">權限</span><span class="sxs-lookup"><span data-stu-id="53a18-116">Permissions</span></span>
<span data-ttu-id="53a18-117">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="53a18-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="53a18-118">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="53a18-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="53a18-119">許可權類型</span><span class="sxs-lookup"><span data-stu-id="53a18-119">Permission type</span></span> |   <span data-ttu-id="53a18-120">權限</span><span class="sxs-lookup"><span data-stu-id="53a18-120">Permission</span></span>  |   <span data-ttu-id="53a18-121">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="53a18-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="53a18-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="53a18-122">Application</span></span> |   <span data-ttu-id="53a18-123">Read。所有</span><span class="sxs-lookup"><span data-stu-id="53a18-123">Machine.Read.All</span></span> |  <span data-ttu-id="53a18-124">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="53a18-124">'Read all machine profiles'</span></span>
<span data-ttu-id="53a18-125">應用程式</span><span class="sxs-lookup"><span data-stu-id="53a18-125">Application</span></span> |   <span data-ttu-id="53a18-126">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="53a18-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="53a18-127">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="53a18-127">'Read and write all machine information'</span></span>
<span data-ttu-id="53a18-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="53a18-128">Delegated (work or school account)</span></span> | <span data-ttu-id="53a18-129">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="53a18-129">Machine.Read</span></span> | <span data-ttu-id="53a18-130">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="53a18-130">'Read machine information'</span></span>
<span data-ttu-id="53a18-131">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="53a18-131">Delegated (work or school account)</span></span> | <span data-ttu-id="53a18-132">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="53a18-132">Machine.ReadWrite</span></span> | <span data-ttu-id="53a18-133">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="53a18-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="53a18-134">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="53a18-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="53a18-135">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="53a18-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="53a18-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="53a18-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="53a18-137">要求標頭</span><span class="sxs-lookup"><span data-stu-id="53a18-137">Request headers</span></span>

<span data-ttu-id="53a18-138">名稱</span><span class="sxs-lookup"><span data-stu-id="53a18-138">Name</span></span> | <span data-ttu-id="53a18-139">類型</span><span class="sxs-lookup"><span data-stu-id="53a18-139">Type</span></span> | <span data-ttu-id="53a18-140">描述</span><span class="sxs-lookup"><span data-stu-id="53a18-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="53a18-141">授權</span><span class="sxs-lookup"><span data-stu-id="53a18-141">Authorization</span></span> | <span data-ttu-id="53a18-142">字串</span><span class="sxs-lookup"><span data-stu-id="53a18-142">String</span></span> | <span data-ttu-id="53a18-143">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="53a18-143">Bearer {token}.</span></span> <span data-ttu-id="53a18-144">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="53a18-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="53a18-145">要求正文</span><span class="sxs-lookup"><span data-stu-id="53a18-145">Request body</span></span>
<span data-ttu-id="53a18-146">空白</span><span class="sxs-lookup"><span data-stu-id="53a18-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="53a18-147">回應</span><span class="sxs-lookup"><span data-stu-id="53a18-147">Response</span></span>
<span data-ttu-id="53a18-148">如果成功，這個方法會以 [machineAction](machineaction.md) 實體的集合傳回200、Ok 回應碼。</span><span class="sxs-lookup"><span data-stu-id="53a18-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="53a18-149">範例 1</span><span class="sxs-lookup"><span data-stu-id="53a18-149">Example 1</span></span>

<span data-ttu-id="53a18-150">**請求**</span><span class="sxs-lookup"><span data-stu-id="53a18-150">**Request**</span></span>

<span data-ttu-id="53a18-151">以下是具有三個 MachineActions 之組織之要求的範例。</span><span class="sxs-lookup"><span data-stu-id="53a18-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="53a18-152">**回應**</span><span class="sxs-lookup"><span data-stu-id="53a18-152">**Response**</span></span>

<span data-ttu-id="53a18-153">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="53a18-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="53a18-154">範例 2</span><span class="sxs-lookup"><span data-stu-id="53a18-154">Example 2</span></span>

<span data-ttu-id="53a18-155">**請求**</span><span class="sxs-lookup"><span data-stu-id="53a18-155">**Request**</span></span>

<span data-ttu-id="53a18-156">以下是以電腦識別碼篩選 MachineActions 之要求的範例，並顯示最新的兩個 MachineActions。</span><span class="sxs-lookup"><span data-stu-id="53a18-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="53a18-157">**回應**</span><span class="sxs-lookup"><span data-stu-id="53a18-157">**Response**</span></span>

<span data-ttu-id="53a18-158">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="53a18-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="53a18-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="53a18-159">Related topics</span></span>
- [<span data-ttu-id="53a18-160">使用 Microsoft Defender for Endpoint OData 查詢</span><span class="sxs-lookup"><span data-stu-id="53a18-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
