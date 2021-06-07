---
title: 取得 MachineAction 物件 API
description: 瞭解如何使用 Get MachineAction API，以在 Microsoft Defender for Endpoint 中以其識別碼來取得特定的電腦動作。
keywords: api，graph api，支援的 api，machineaction 物件
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
ms.openlocfilehash: dcb00d0d2afc7f873ea9c4afa3174ac46babf879
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770778"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="6a575-104">取得 machineAction API</span><span class="sxs-lookup"><span data-stu-id="6a575-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a575-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6a575-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6a575-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="6a575-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a575-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6a575-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6a575-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="6a575-108">API description</span></span>
<span data-ttu-id="6a575-109">依識別碼檢索特定的 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="6a575-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="6a575-110">限制</span><span class="sxs-lookup"><span data-stu-id="6a575-110">Limitations</span></span>
1. <span data-ttu-id="6a575-111">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="6a575-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6a575-112">權限</span><span class="sxs-lookup"><span data-stu-id="6a575-112">Permissions</span></span>
<span data-ttu-id="6a575-113">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="6a575-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6a575-114">若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6a575-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6a575-115">許可權類型</span><span class="sxs-lookup"><span data-stu-id="6a575-115">Permission type</span></span> |   <span data-ttu-id="6a575-116">權限</span><span class="sxs-lookup"><span data-stu-id="6a575-116">Permission</span></span>  |   <span data-ttu-id="6a575-117">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="6a575-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6a575-118">應用程式</span><span class="sxs-lookup"><span data-stu-id="6a575-118">Application</span></span> |   <span data-ttu-id="6a575-119">Read。所有</span><span class="sxs-lookup"><span data-stu-id="6a575-119">Machine.Read.All</span></span> |  <span data-ttu-id="6a575-120">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="6a575-120">'Read all machine profiles'</span></span>
<span data-ttu-id="6a575-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="6a575-121">Application</span></span> |   <span data-ttu-id="6a575-122">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="6a575-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="6a575-123">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="6a575-123">'Read and write all machine information'</span></span>
<span data-ttu-id="6a575-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="6a575-124">Delegated (work or school account)</span></span> | <span data-ttu-id="6a575-125">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="6a575-125">Machine.Read</span></span> | <span data-ttu-id="6a575-126">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="6a575-126">'Read machine information'</span></span>
<span data-ttu-id="6a575-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="6a575-127">Delegated (work or school account)</span></span> | <span data-ttu-id="6a575-128">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6a575-128">Machine.ReadWrite</span></span> | <span data-ttu-id="6a575-129">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="6a575-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="6a575-130">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="6a575-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6a575-131">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="6a575-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6a575-132">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="6a575-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="6a575-133">要求標頭</span><span class="sxs-lookup"><span data-stu-id="6a575-133">Request headers</span></span>

<span data-ttu-id="6a575-134">名稱</span><span class="sxs-lookup"><span data-stu-id="6a575-134">Name</span></span> | <span data-ttu-id="6a575-135">類型</span><span class="sxs-lookup"><span data-stu-id="6a575-135">Type</span></span> | <span data-ttu-id="6a575-136">描述</span><span class="sxs-lookup"><span data-stu-id="6a575-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="6a575-137">授權</span><span class="sxs-lookup"><span data-stu-id="6a575-137">Authorization</span></span> | <span data-ttu-id="6a575-138">字串</span><span class="sxs-lookup"><span data-stu-id="6a575-138">String</span></span> | <span data-ttu-id="6a575-139">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="6a575-139">Bearer {token}.</span></span> <span data-ttu-id="6a575-140">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="6a575-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6a575-141">要求正文</span><span class="sxs-lookup"><span data-stu-id="6a575-141">Request body</span></span>
<span data-ttu-id="6a575-142">空白</span><span class="sxs-lookup"><span data-stu-id="6a575-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6a575-143">回應</span><span class="sxs-lookup"><span data-stu-id="6a575-143">Response</span></span>
<span data-ttu-id="6a575-144">若成功，這個方法會傳回200，具有 [機器動作](machineaction.md) 實體的 Ok 回應碼。</span><span class="sxs-lookup"><span data-stu-id="6a575-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="6a575-145">如果找不到具有指定識別碼的 machine action 實體-找不到404。</span><span class="sxs-lookup"><span data-stu-id="6a575-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="6a575-146">範例</span><span class="sxs-lookup"><span data-stu-id="6a575-146">Example</span></span>

<span data-ttu-id="6a575-147">**請求**</span><span class="sxs-lookup"><span data-stu-id="6a575-147">**Request**</span></span>

<span data-ttu-id="6a575-148">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="6a575-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="6a575-149">**回應**</span><span class="sxs-lookup"><span data-stu-id="6a575-149">**Response**</span></span>

<span data-ttu-id="6a575-150">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="6a575-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```
