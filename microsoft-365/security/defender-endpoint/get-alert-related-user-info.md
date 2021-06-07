---
title: 取得警示相關使用者資訊
description: 瞭解如何使用 [取得警示相關的使用者資訊 API]，在 Microsoft Defender for Endpoint 中取得與特定警示相關的使用者。
keywords: api、graph api、支援的 api、get、警示、資訊、相關的使用者
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
ms.openlocfilehash: e895885a638c60a845ed4857c682cd472e42615c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772314"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="228df-104">取得與提醒相關的使用者資訊 API</span><span class="sxs-lookup"><span data-stu-id="228df-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="228df-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="228df-105">**Applies to:**</span></span>
- [<span data-ttu-id="228df-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="228df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="228df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="228df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="228df-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="228df-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="228df-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="228df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="228df-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="228df-110">API description</span></span>
<span data-ttu-id="228df-111">會檢索與特定警示相關的使用者。</span><span class="sxs-lookup"><span data-stu-id="228df-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="228df-112">限制</span><span class="sxs-lookup"><span data-stu-id="228df-112">Limitations</span></span>
1. <span data-ttu-id="228df-113">您可以根據您設定的保留期間，查詢上次更新的警示。</span><span class="sxs-lookup"><span data-stu-id="228df-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="228df-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="228df-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="228df-115">權限</span><span class="sxs-lookup"><span data-stu-id="228df-115">Permissions</span></span>
<span data-ttu-id="228df-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="228df-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="228df-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="228df-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="228df-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="228df-118">Permission type</span></span> |   <span data-ttu-id="228df-119">權限</span><span class="sxs-lookup"><span data-stu-id="228df-119">Permission</span></span>  |   <span data-ttu-id="228df-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="228df-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="228df-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="228df-121">Application</span></span> |   <span data-ttu-id="228df-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="228df-122">User.Read.All</span></span> | <span data-ttu-id="228df-123">「讀取使用者設定檔」</span><span class="sxs-lookup"><span data-stu-id="228df-123">'Read user profiles'</span></span>
<span data-ttu-id="228df-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="228df-124">Delegated (work or school account)</span></span> | <span data-ttu-id="228df-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="228df-125">User.Read.All</span></span> | <span data-ttu-id="228df-126">「讀取使用者設定檔」</span><span class="sxs-lookup"><span data-stu-id="228df-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="228df-127">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="228df-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="228df-128">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="228df-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="228df-129">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="228df-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="228df-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="228df-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="228df-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="228df-131">Request headers</span></span>

<span data-ttu-id="228df-132">名稱</span><span class="sxs-lookup"><span data-stu-id="228df-132">Name</span></span> | <span data-ttu-id="228df-133">類型</span><span class="sxs-lookup"><span data-stu-id="228df-133">Type</span></span> | <span data-ttu-id="228df-134">描述</span><span class="sxs-lookup"><span data-stu-id="228df-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="228df-135">授權</span><span class="sxs-lookup"><span data-stu-id="228df-135">Authorization</span></span> | <span data-ttu-id="228df-136">字串</span><span class="sxs-lookup"><span data-stu-id="228df-136">String</span></span> | <span data-ttu-id="228df-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="228df-137">Bearer {token}.</span></span> <span data-ttu-id="228df-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="228df-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="228df-139">要求正文</span><span class="sxs-lookup"><span data-stu-id="228df-139">Request body</span></span>
<span data-ttu-id="228df-140">空白</span><span class="sxs-lookup"><span data-stu-id="228df-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="228df-141">回應</span><span class="sxs-lookup"><span data-stu-id="228df-141">Response</span></span>
<span data-ttu-id="228df-142">如果成功及警示和使用者存在-200 確定正文中的使用者。</span><span class="sxs-lookup"><span data-stu-id="228df-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="228df-143">如果找不到警示或使用者-找不到404。</span><span class="sxs-lookup"><span data-stu-id="228df-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="228df-144">範例</span><span class="sxs-lookup"><span data-stu-id="228df-144">Example</span></span>

<span data-ttu-id="228df-145">**請求**</span><span class="sxs-lookup"><span data-stu-id="228df-145">**Request**</span></span>

<span data-ttu-id="228df-146">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="228df-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="228df-147">**回應**</span><span class="sxs-lookup"><span data-stu-id="228df-147">**Response**</span></span>

<span data-ttu-id="228df-148">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="228df-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
