---
title: 取得使用者資訊 API
description: 瞭解如何使用 [取得使用者資訊 API]，在 Microsoft Defender for Endpoint 中以按鍵或使用者名稱來檢索使用者實體。
keywords: api、graph api、支援的 api、get、user、user 資訊
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198538"
---
# <a name="get-user-information-api"></a><span data-ttu-id="a804f-104">取得使用者資訊 API</span><span class="sxs-lookup"><span data-stu-id="a804f-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a804f-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a804f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a804f-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="a804f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a804f-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a804f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="a804f-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a804f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a804f-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a804f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="a804f-110">使用按鍵 (使用者名稱) 來找回使用者實體。</span><span class="sxs-lookup"><span data-stu-id="a804f-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="a804f-111">權限</span><span class="sxs-lookup"><span data-stu-id="a804f-111">Permissions</span></span>
<span data-ttu-id="a804f-112">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="a804f-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a804f-113">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a804f-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a804f-114">許可權類型</span><span class="sxs-lookup"><span data-stu-id="a804f-114">Permission type</span></span> |   <span data-ttu-id="a804f-115">權限</span><span class="sxs-lookup"><span data-stu-id="a804f-115">Permission</span></span>  |   <span data-ttu-id="a804f-116">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a804f-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a804f-117">應用程式</span><span class="sxs-lookup"><span data-stu-id="a804f-117">Application</span></span> |   <span data-ttu-id="a804f-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="a804f-118">User.Read.All</span></span> | <span data-ttu-id="a804f-119">「讀取所有使用者設定檔」</span><span class="sxs-lookup"><span data-stu-id="a804f-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="a804f-120">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a804f-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="a804f-121">要求標頭</span><span class="sxs-lookup"><span data-stu-id="a804f-121">Request headers</span></span>

<span data-ttu-id="a804f-122">名稱</span><span class="sxs-lookup"><span data-stu-id="a804f-122">Name</span></span> | <span data-ttu-id="a804f-123">類型</span><span class="sxs-lookup"><span data-stu-id="a804f-123">Type</span></span> | <span data-ttu-id="a804f-124">描述</span><span class="sxs-lookup"><span data-stu-id="a804f-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="a804f-125">授權</span><span class="sxs-lookup"><span data-stu-id="a804f-125">Authorization</span></span> | <span data-ttu-id="a804f-126">字串</span><span class="sxs-lookup"><span data-stu-id="a804f-126">String</span></span> | <span data-ttu-id="a804f-127">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="a804f-127">Bearer {token}.</span></span> <span data-ttu-id="a804f-128">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="a804f-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a804f-129">要求正文</span><span class="sxs-lookup"><span data-stu-id="a804f-129">Request body</span></span>
<span data-ttu-id="a804f-130">空白</span><span class="sxs-lookup"><span data-stu-id="a804f-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a804f-131">回應</span><span class="sxs-lookup"><span data-stu-id="a804f-131">Response</span></span>
<span data-ttu-id="a804f-132">如果成功且使用者存在，則為主體中的 [使用者](user.md) 實體的 200 OK。</span><span class="sxs-lookup"><span data-stu-id="a804f-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="a804f-133">如果使用者不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="a804f-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="a804f-134">範例</span><span class="sxs-lookup"><span data-stu-id="a804f-134">Example</span></span>

<span data-ttu-id="a804f-135">**請求**</span><span class="sxs-lookup"><span data-stu-id="a804f-135">**Request**</span></span>

<span data-ttu-id="a804f-136">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="a804f-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="a804f-137">**回應**</span><span class="sxs-lookup"><span data-stu-id="a804f-137">**Response**</span></span>

<span data-ttu-id="a804f-138">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="a804f-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
