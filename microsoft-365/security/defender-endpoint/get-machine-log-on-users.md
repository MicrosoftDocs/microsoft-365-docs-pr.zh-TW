---
title: 取得電腦登入使用者 API
description: 瞭解如何使用「取得機器登入使用者」 API，在 Microsoft Defender for Endpoint 中的裝置上，取回已登入使用者的集合。
keywords: api、graph api、支援的 api、get、device、登入、使用者
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
ms.openlocfilehash: 1c81d2978677b751a8085f88b5c4732fd4a5a247
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770046"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="d55d1-104">取得電腦登入使用者 API</span><span class="sxs-lookup"><span data-stu-id="d55d1-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d55d1-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d55d1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="d55d1-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d55d1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d55d1-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d55d1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d55d1-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="d55d1-108">API description</span></span>
<span data-ttu-id="d55d1-109">在特定裝置上檢索登入使用者的集合。</span><span class="sxs-lookup"><span data-stu-id="d55d1-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="d55d1-110">限制</span><span class="sxs-lookup"><span data-stu-id="d55d1-110">Limitations</span></span>
1. <span data-ttu-id="d55d1-111">您可以根據您設定的保留期間，查詢上次更新的警示。</span><span class="sxs-lookup"><span data-stu-id="d55d1-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="d55d1-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="d55d1-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d55d1-113">權限</span><span class="sxs-lookup"><span data-stu-id="d55d1-113">Permissions</span></span>
<span data-ttu-id="d55d1-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="d55d1-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d55d1-115">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d55d1-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d55d1-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="d55d1-116">Permission type</span></span> |   <span data-ttu-id="d55d1-117">權限</span><span class="sxs-lookup"><span data-stu-id="d55d1-117">Permission</span></span>  |   <span data-ttu-id="d55d1-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="d55d1-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d55d1-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="d55d1-119">Application</span></span> |   <span data-ttu-id="d55d1-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="d55d1-120">User.Read.All</span></span> | <span data-ttu-id="d55d1-121">「讀取使用者設定檔」</span><span class="sxs-lookup"><span data-stu-id="d55d1-121">'Read user profiles'</span></span>
<span data-ttu-id="d55d1-122">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="d55d1-122">Delegated (work or school account)</span></span> | <span data-ttu-id="d55d1-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="d55d1-123">User.Read.All</span></span> | <span data-ttu-id="d55d1-124">「讀取使用者設定檔」</span><span class="sxs-lookup"><span data-stu-id="d55d1-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="d55d1-125">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="d55d1-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d55d1-126">使用者至少必須具備下列角色許可權：「View Data」。</span><span class="sxs-lookup"><span data-stu-id="d55d1-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="d55d1-127">如需詳細資訊，請參閱 [Create and manage roles](user-roles.md) ) </span><span class="sxs-lookup"><span data-stu-id="d55d1-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="d55d1-128">只有當使用者可以看見裝置時，回應才會包含使用者，視裝置群組設定而定。</span><span class="sxs-lookup"><span data-stu-id="d55d1-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="d55d1-129">如需詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="d55d1-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="d55d1-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="d55d1-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="d55d1-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="d55d1-131">Request headers</span></span>

<span data-ttu-id="d55d1-132">名稱</span><span class="sxs-lookup"><span data-stu-id="d55d1-132">Name</span></span> | <span data-ttu-id="d55d1-133">類型</span><span class="sxs-lookup"><span data-stu-id="d55d1-133">Type</span></span> | <span data-ttu-id="d55d1-134">描述</span><span class="sxs-lookup"><span data-stu-id="d55d1-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="d55d1-135">授權</span><span class="sxs-lookup"><span data-stu-id="d55d1-135">Authorization</span></span> | <span data-ttu-id="d55d1-136">字串</span><span class="sxs-lookup"><span data-stu-id="d55d1-136">String</span></span> | <span data-ttu-id="d55d1-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="d55d1-137">Bearer {token}.</span></span> <span data-ttu-id="d55d1-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="d55d1-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d55d1-139">要求正文</span><span class="sxs-lookup"><span data-stu-id="d55d1-139">Request body</span></span>
<span data-ttu-id="d55d1-140">空白</span><span class="sxs-lookup"><span data-stu-id="d55d1-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d55d1-141">回應</span><span class="sxs-lookup"><span data-stu-id="d55d1-141">Response</span></span>
<span data-ttu-id="d55d1-142">如果成功和裝置都存在-200 OK （含）主體中的 [使用者](user.md) 實體清單。</span><span class="sxs-lookup"><span data-stu-id="d55d1-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="d55d1-143">如果找不到裝置-找不到404。</span><span class="sxs-lookup"><span data-stu-id="d55d1-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="d55d1-144">範例</span><span class="sxs-lookup"><span data-stu-id="d55d1-144">Example</span></span>

<span data-ttu-id="d55d1-145">**請求**</span><span class="sxs-lookup"><span data-stu-id="d55d1-145">**Request**</span></span>

<span data-ttu-id="d55d1-146">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="d55d1-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="d55d1-147">**回應**</span><span class="sxs-lookup"><span data-stu-id="d55d1-147">**Response**</span></span>

<span data-ttu-id="d55d1-148">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="d55d1-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
