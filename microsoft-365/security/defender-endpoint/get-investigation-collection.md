---
title: 清單調查 API
description: 使用此 API 來建立與取得調查集合相關的呼叫
keywords: api，graph api，支援的 api，調查集合
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
ms.technology: mde
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166458"
---
# <a name="list-investigations-api"></a><span data-ttu-id="578f9-104">清單調查 API</span><span class="sxs-lookup"><span data-stu-id="578f9-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="578f9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="578f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="578f9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="578f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="578f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="578f9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="578f9-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="578f9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="578f9-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="578f9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="578f9-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="578f9-110">API description</span></span>
<span data-ttu-id="578f9-111">會檢索 [調查](investigation.md)的集合。</span><span class="sxs-lookup"><span data-stu-id="578f9-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="578f9-112">支援 [OData V4 查詢](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="578f9-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="578f9-113">支援 OData 的 ```$filter``` 查詢： ```startTime``` 、 ```state``` ```machineId``` 和 ```triggeringAlertId``` 屬性。</span><span class="sxs-lookup"><span data-stu-id="578f9-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="578f9-114">請參閱[使用 Microsoft Defender For Endpoint 的 OData 查詢](exposed-apis-odata-samples.md)中的範例</span><span class="sxs-lookup"><span data-stu-id="578f9-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="578f9-115">限制</span><span class="sxs-lookup"><span data-stu-id="578f9-115">Limitations</span></span>
1. <span data-ttu-id="578f9-116">頁面大小上限為10000。</span><span class="sxs-lookup"><span data-stu-id="578f9-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="578f9-117">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="578f9-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="578f9-118">權限</span><span class="sxs-lookup"><span data-stu-id="578f9-118">Permissions</span></span>
<span data-ttu-id="578f9-119">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="578f9-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="578f9-120">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="578f9-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="578f9-121">許可權類型</span><span class="sxs-lookup"><span data-stu-id="578f9-121">Permission type</span></span> |   <span data-ttu-id="578f9-122">權限</span><span class="sxs-lookup"><span data-stu-id="578f9-122">Permission</span></span>  |   <span data-ttu-id="578f9-123">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="578f9-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="578f9-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="578f9-124">Application</span></span> |   <span data-ttu-id="578f9-125">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="578f9-125">Alert.Read.All</span></span> |    <span data-ttu-id="578f9-126">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="578f9-126">'Read all alerts'</span></span>
<span data-ttu-id="578f9-127">應用程式</span><span class="sxs-lookup"><span data-stu-id="578f9-127">Application</span></span> |   <span data-ttu-id="578f9-128">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="578f9-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="578f9-129">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="578f9-129">'Read and write all alerts'</span></span>
<span data-ttu-id="578f9-130">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="578f9-130">Delegated (work or school account)</span></span> | <span data-ttu-id="578f9-131">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="578f9-131">Alert.Read</span></span> | <span data-ttu-id="578f9-132">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="578f9-132">'Read alerts'</span></span>
<span data-ttu-id="578f9-133">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="578f9-133">Delegated (work or school account)</span></span> | <span data-ttu-id="578f9-134">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="578f9-134">Alert.ReadWrite</span></span> | <span data-ttu-id="578f9-135">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="578f9-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="578f9-136">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="578f9-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="578f9-137">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="578f9-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="578f9-138">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="578f9-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="578f9-139">要求標頭</span><span class="sxs-lookup"><span data-stu-id="578f9-139">Request headers</span></span>

<span data-ttu-id="578f9-140">名稱</span><span class="sxs-lookup"><span data-stu-id="578f9-140">Name</span></span> | <span data-ttu-id="578f9-141">類型</span><span class="sxs-lookup"><span data-stu-id="578f9-141">Type</span></span> | <span data-ttu-id="578f9-142">描述</span><span class="sxs-lookup"><span data-stu-id="578f9-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="578f9-143">授權</span><span class="sxs-lookup"><span data-stu-id="578f9-143">Authorization</span></span> | <span data-ttu-id="578f9-144">字串</span><span class="sxs-lookup"><span data-stu-id="578f9-144">String</span></span> | <span data-ttu-id="578f9-145">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="578f9-145">Bearer {token}.</span></span> <span data-ttu-id="578f9-146">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="578f9-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="578f9-147">要求正文</span><span class="sxs-lookup"><span data-stu-id="578f9-147">Request body</span></span>
<span data-ttu-id="578f9-148">空白</span><span class="sxs-lookup"><span data-stu-id="578f9-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="578f9-149">回應</span><span class="sxs-lookup"><span data-stu-id="578f9-149">Response</span></span>
<span data-ttu-id="578f9-150">若成功，這個方法會以 [調查](investigation.md) 條目的集合傳回200、Ok 回應碼。</span><span class="sxs-lookup"><span data-stu-id="578f9-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="578f9-151">範例</span><span class="sxs-lookup"><span data-stu-id="578f9-151">Example</span></span>

<span data-ttu-id="578f9-152">**請求**</span><span class="sxs-lookup"><span data-stu-id="578f9-152">**Request**</span></span>

<span data-ttu-id="578f9-153">以下是取得所有調查之要求的範例：</span><span class="sxs-lookup"><span data-stu-id="578f9-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="578f9-154">**回應**</span><span class="sxs-lookup"><span data-stu-id="578f9-154">**Response**</span></span>

<span data-ttu-id="578f9-155">以下是回應的範例：</span><span class="sxs-lookup"><span data-stu-id="578f9-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
