---
title: 依 ID 取得電腦 API
description: 瞭解如何使用 [透過識別碼取得機器] API，以在 Microsoft Defender for Endpoint 中以設備識別碼或電腦名稱稱來檢索電腦。
keywords: api、graph api、支援的 api、get、裝置、實體、識別碼
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
ms.openlocfilehash: e4ed5a68b0f4c5e9472702d3cc2798a810e4f84e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769470"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="d910a-104">依 ID 取得電腦 API</span><span class="sxs-lookup"><span data-stu-id="d910a-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d910a-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d910a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="d910a-106">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d910a-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d910a-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d910a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d910a-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="d910a-108">API description</span></span>
<span data-ttu-id="d910a-109">依設備識別碼或電腦名稱稱來檢索特定 [電腦](machine.md) 。</span><span class="sxs-lookup"><span data-stu-id="d910a-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="d910a-110">限制</span><span class="sxs-lookup"><span data-stu-id="d910a-110">Limitations</span></span>
1. <span data-ttu-id="d910a-111">您可以根據您設定的保留原則，取得最後一個看到的裝置。</span><span class="sxs-lookup"><span data-stu-id="d910a-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="d910a-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="d910a-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d910a-113">權限</span><span class="sxs-lookup"><span data-stu-id="d910a-113">Permissions</span></span>
<span data-ttu-id="d910a-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="d910a-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d910a-115">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d910a-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d910a-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="d910a-116">Permission type</span></span> |   <span data-ttu-id="d910a-117">權限</span><span class="sxs-lookup"><span data-stu-id="d910a-117">Permission</span></span>  |   <span data-ttu-id="d910a-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="d910a-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d910a-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="d910a-119">Application</span></span> |   <span data-ttu-id="d910a-120">Read。所有</span><span class="sxs-lookup"><span data-stu-id="d910a-120">Machine.Read.All</span></span> |  <span data-ttu-id="d910a-121">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="d910a-121">'Read all machine profiles'</span></span>
<span data-ttu-id="d910a-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="d910a-122">Application</span></span> |   <span data-ttu-id="d910a-123">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="d910a-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="d910a-124">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="d910a-124">'Read and write all machine information'</span></span>
<span data-ttu-id="d910a-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="d910a-125">Delegated (work or school account)</span></span> | <span data-ttu-id="d910a-126">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="d910a-126">Machine.Read</span></span> | <span data-ttu-id="d910a-127">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="d910a-127">'Read machine information'</span></span>
<span data-ttu-id="d910a-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="d910a-128">Delegated (work or school account)</span></span> | <span data-ttu-id="d910a-129">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d910a-129">Machine.ReadWrite</span></span> | <span data-ttu-id="d910a-130">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="d910a-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="d910a-131">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="d910a-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d910a-132">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="d910a-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d910a-133">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="d910a-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="d910a-134">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="d910a-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="d910a-135">要求標頭</span><span class="sxs-lookup"><span data-stu-id="d910a-135">Request headers</span></span>

<span data-ttu-id="d910a-136">名稱</span><span class="sxs-lookup"><span data-stu-id="d910a-136">Name</span></span> | <span data-ttu-id="d910a-137">類型</span><span class="sxs-lookup"><span data-stu-id="d910a-137">Type</span></span> | <span data-ttu-id="d910a-138">描述</span><span class="sxs-lookup"><span data-stu-id="d910a-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="d910a-139">授權</span><span class="sxs-lookup"><span data-stu-id="d910a-139">Authorization</span></span> | <span data-ttu-id="d910a-140">字串</span><span class="sxs-lookup"><span data-stu-id="d910a-140">String</span></span> | <span data-ttu-id="d910a-141">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="d910a-141">Bearer {token}.</span></span> <span data-ttu-id="d910a-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="d910a-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d910a-143">要求正文</span><span class="sxs-lookup"><span data-stu-id="d910a-143">Request body</span></span>
<span data-ttu-id="d910a-144">空白</span><span class="sxs-lookup"><span data-stu-id="d910a-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d910a-145">回應</span><span class="sxs-lookup"><span data-stu-id="d910a-145">Response</span></span>
<span data-ttu-id="d910a-146">如果成功和裝置存在，則為內部的 [machine](machine.md) 實體的 200 OK。</span><span class="sxs-lookup"><span data-stu-id="d910a-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="d910a-147">如果找不到具有指定識別碼的電腦-找不到404。</span><span class="sxs-lookup"><span data-stu-id="d910a-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d910a-148">範例</span><span class="sxs-lookup"><span data-stu-id="d910a-148">Example</span></span>

<span data-ttu-id="d910a-149">**請求**</span><span class="sxs-lookup"><span data-stu-id="d910a-149">**Request**</span></span>

<span data-ttu-id="d910a-150">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="d910a-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="d910a-151">**回應**</span><span class="sxs-lookup"><span data-stu-id="d910a-151">**Response**</span></span>

<span data-ttu-id="d910a-152">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="d910a-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}

```
