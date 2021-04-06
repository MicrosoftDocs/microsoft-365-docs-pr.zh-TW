---
title: 取得網域統計資料 API
description: 瞭解如何使用取得網域統計資料 API，在 Microsoft Defender for Endpoint 中取得指定網域上的統計資料。
keywords: api、graph api、支援的 api、get、domain、domain 相關裝置
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
ms.openlocfilehash: eef06657d7f691a89e5985640431c2cc706557b4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166465"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="82eb1-104">取得網域統計資料 API</span><span class="sxs-lookup"><span data-stu-id="82eb1-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="82eb1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="82eb1-105">**Applies to:**</span></span>
- [<span data-ttu-id="82eb1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="82eb1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="82eb1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="82eb1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="82eb1-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="82eb1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="82eb1-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="82eb1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="82eb1-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="82eb1-110">API description</span></span>
<span data-ttu-id="82eb1-111">在指定的網域上檢索統計資料。</span><span class="sxs-lookup"><span data-stu-id="82eb1-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="82eb1-112">限制</span><span class="sxs-lookup"><span data-stu-id="82eb1-112">Limitations</span></span>
1. <span data-ttu-id="82eb1-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="82eb1-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="82eb1-114">權限</span><span class="sxs-lookup"><span data-stu-id="82eb1-114">Permissions</span></span>
<span data-ttu-id="82eb1-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="82eb1-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="82eb1-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="82eb1-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="82eb1-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="82eb1-117">Permission type</span></span> |   <span data-ttu-id="82eb1-118">權限</span><span class="sxs-lookup"><span data-stu-id="82eb1-118">Permission</span></span>  |   <span data-ttu-id="82eb1-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="82eb1-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="82eb1-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="82eb1-120">Application</span></span> |   <span data-ttu-id="82eb1-121">URL:。Read。所有</span><span class="sxs-lookup"><span data-stu-id="82eb1-121">URL.Read.All</span></span> |  <span data-ttu-id="82eb1-122">「讀取 URLs '</span><span class="sxs-lookup"><span data-stu-id="82eb1-122">'Read URLs'</span></span>
<span data-ttu-id="82eb1-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="82eb1-123">Delegated (work or school account)</span></span> | <span data-ttu-id="82eb1-124">URL:。Read。所有</span><span class="sxs-lookup"><span data-stu-id="82eb1-124">URL.Read.All</span></span> | <span data-ttu-id="82eb1-125">「讀取 URLs '</span><span class="sxs-lookup"><span data-stu-id="82eb1-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="82eb1-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="82eb1-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="82eb1-127">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="82eb1-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="82eb1-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="82eb1-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="82eb1-129">要求標頭</span><span class="sxs-lookup"><span data-stu-id="82eb1-129">Request headers</span></span>

<span data-ttu-id="82eb1-130">Header</span><span class="sxs-lookup"><span data-stu-id="82eb1-130">Header</span></span> | <span data-ttu-id="82eb1-131">值</span><span class="sxs-lookup"><span data-stu-id="82eb1-131">Value</span></span> 
:---|:---
<span data-ttu-id="82eb1-132">授權</span><span class="sxs-lookup"><span data-stu-id="82eb1-132">Authorization</span></span> | <span data-ttu-id="82eb1-133">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="82eb1-133">Bearer {token}.</span></span> <span data-ttu-id="82eb1-134">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="82eb1-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="82eb1-135">要求 URI 參數</span><span class="sxs-lookup"><span data-stu-id="82eb1-135">Request URI parameters</span></span>

<span data-ttu-id="82eb1-136">名稱</span><span class="sxs-lookup"><span data-stu-id="82eb1-136">Name</span></span> | <span data-ttu-id="82eb1-137">類型</span><span class="sxs-lookup"><span data-stu-id="82eb1-137">Type</span></span> | <span data-ttu-id="82eb1-138">描述</span><span class="sxs-lookup"><span data-stu-id="82eb1-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="82eb1-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="82eb1-139">lookBackHours</span></span> | <span data-ttu-id="82eb1-140">Int32</span><span class="sxs-lookup"><span data-stu-id="82eb1-140">Int32</span></span> | <span data-ttu-id="82eb1-141">定義我們回叫以取得統計資料的小時數。</span><span class="sxs-lookup"><span data-stu-id="82eb1-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="82eb1-142">預設為30天。</span><span class="sxs-lookup"><span data-stu-id="82eb1-142">Defaults to 30 days.</span></span> <span data-ttu-id="82eb1-143">此為選擇性欄位。</span><span class="sxs-lookup"><span data-stu-id="82eb1-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="82eb1-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="82eb1-144">Request body</span></span>
<span data-ttu-id="82eb1-145">空白</span><span class="sxs-lookup"><span data-stu-id="82eb1-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="82eb1-146">回應</span><span class="sxs-lookup"><span data-stu-id="82eb1-146">Response</span></span>
<span data-ttu-id="82eb1-147">如果成功且網域存在-200 OK，包含回應內文的統計資料物件。</span><span class="sxs-lookup"><span data-stu-id="82eb1-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="82eb1-148">如果網域不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="82eb1-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="82eb1-149">範例</span><span class="sxs-lookup"><span data-stu-id="82eb1-149">Example</span></span>

<span data-ttu-id="82eb1-150">**請求**</span><span class="sxs-lookup"><span data-stu-id="82eb1-150">**Request**</span></span>

<span data-ttu-id="82eb1-151">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="82eb1-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="82eb1-152">**回應**</span><span class="sxs-lookup"><span data-stu-id="82eb1-152">**Response**</span></span>

<span data-ttu-id="82eb1-153">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="82eb1-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```