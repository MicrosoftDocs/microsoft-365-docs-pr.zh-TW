---
title: 取得警示相關的 IPs 資訊
description: 使用 Microsoft Defender for Endpoint，取回與特定警示相關的所有 Ip。
keywords: api、graph api、支援的 api、取得警示資訊、警示資訊、相關的 ip
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
ms.openlocfilehash: 970f82038bd7feb4f0c568ed13b285f75bf1ab19
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166438"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="4ca78-104">取得警示相關的 IPs 資訊 API</span><span class="sxs-lookup"><span data-stu-id="4ca78-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4ca78-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="4ca78-105">**Applies to:**</span></span>
- [<span data-ttu-id="4ca78-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ca78-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4ca78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ca78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4ca78-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4ca78-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4ca78-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="4ca78-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4ca78-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="4ca78-110">API description</span></span>
<span data-ttu-id="4ca78-111">會檢索與特定警示相關的所有 Ip。</span><span class="sxs-lookup"><span data-stu-id="4ca78-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="4ca78-112">限制</span><span class="sxs-lookup"><span data-stu-id="4ca78-112">Limitations</span></span>
1. <span data-ttu-id="4ca78-113">您可以根據您設定的保留期間，查詢上次更新的警示。</span><span class="sxs-lookup"><span data-stu-id="4ca78-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="4ca78-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="4ca78-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4ca78-115">權限</span><span class="sxs-lookup"><span data-stu-id="4ca78-115">Permissions</span></span>
<span data-ttu-id="4ca78-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="4ca78-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4ca78-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4ca78-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4ca78-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="4ca78-118">Permission type</span></span> |   <span data-ttu-id="4ca78-119">權限</span><span class="sxs-lookup"><span data-stu-id="4ca78-119">Permission</span></span>  |   <span data-ttu-id="4ca78-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="4ca78-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4ca78-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="4ca78-121">Application</span></span> |   <span data-ttu-id="4ca78-122">已讀取的 Ip。全部</span><span class="sxs-lookup"><span data-stu-id="4ca78-122">Ip.Read.All</span></span> |   <span data-ttu-id="4ca78-123">「讀取 IP 位址設定檔」</span><span class="sxs-lookup"><span data-stu-id="4ca78-123">'Read IP address profiles'</span></span>
<span data-ttu-id="4ca78-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="4ca78-124">Delegated (work or school account)</span></span> | <span data-ttu-id="4ca78-125">已讀取的 Ip。全部</span><span class="sxs-lookup"><span data-stu-id="4ca78-125">Ip.Read.All</span></span> |  <span data-ttu-id="4ca78-126">「讀取 IP 位址設定檔」</span><span class="sxs-lookup"><span data-stu-id="4ca78-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="4ca78-127">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="4ca78-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4ca78-128">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="4ca78-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4ca78-129">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="4ca78-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4ca78-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="4ca78-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="4ca78-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="4ca78-131">Request headers</span></span>

<span data-ttu-id="4ca78-132">名稱</span><span class="sxs-lookup"><span data-stu-id="4ca78-132">Name</span></span> | <span data-ttu-id="4ca78-133">類型</span><span class="sxs-lookup"><span data-stu-id="4ca78-133">Type</span></span> | <span data-ttu-id="4ca78-134">描述</span><span class="sxs-lookup"><span data-stu-id="4ca78-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="4ca78-135">授權</span><span class="sxs-lookup"><span data-stu-id="4ca78-135">Authorization</span></span> | <span data-ttu-id="4ca78-136">字串</span><span class="sxs-lookup"><span data-stu-id="4ca78-136">String</span></span> | <span data-ttu-id="4ca78-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="4ca78-137">Bearer {token}.</span></span> <span data-ttu-id="4ca78-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="4ca78-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4ca78-139">要求正文</span><span class="sxs-lookup"><span data-stu-id="4ca78-139">Request body</span></span>
<span data-ttu-id="4ca78-140">空白</span><span class="sxs-lookup"><span data-stu-id="4ca78-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4ca78-141">回應</span><span class="sxs-lookup"><span data-stu-id="4ca78-141">Response</span></span>
<span data-ttu-id="4ca78-142">如果成功及警示和 IP 存在-200 確定。</span><span class="sxs-lookup"><span data-stu-id="4ca78-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="4ca78-143">如果找不到警示-找不到404。</span><span class="sxs-lookup"><span data-stu-id="4ca78-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4ca78-144">範例</span><span class="sxs-lookup"><span data-stu-id="4ca78-144">Example</span></span>

<span data-ttu-id="4ca78-145">**請求**</span><span class="sxs-lookup"><span data-stu-id="4ca78-145">**Request**</span></span>

<span data-ttu-id="4ca78-146">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="4ca78-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="4ca78-147">**回應**</span><span class="sxs-lookup"><span data-stu-id="4ca78-147">**Response**</span></span>

<span data-ttu-id="4ca78-148">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="4ca78-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```
