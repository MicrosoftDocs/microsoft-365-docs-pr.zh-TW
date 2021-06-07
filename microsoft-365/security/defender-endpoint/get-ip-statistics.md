---
title: 取得 IP 統計資料 API
description: 使用 Microsoft Defender for Endpoint 取得 IP 的最新統計資訊。
keywords: api、graph api、支援的 api、get、ip、統計資料、流行
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
ms.openlocfilehash: 55bf10d01093c17ba2d186ce0a1d1313db2c3a75
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770082"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="ab5f7-104">取得 IP 統計資料 API</span><span class="sxs-lookup"><span data-stu-id="ab5f7-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab5f7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ab5f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab5f7-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ab5f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab5f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab5f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ab5f7-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ab5f7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab5f7-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ab5f7-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="ab5f7-110">API description</span></span>
<span data-ttu-id="ab5f7-111">取得指定 IP 的統計資料。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="ab5f7-112">限制</span><span class="sxs-lookup"><span data-stu-id="ab5f7-112">Limitations</span></span>
1. <span data-ttu-id="ab5f7-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="ab5f7-114">權限</span><span class="sxs-lookup"><span data-stu-id="ab5f7-114">Permissions</span></span>
<span data-ttu-id="ab5f7-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ab5f7-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ab5f7-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ab5f7-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="ab5f7-117">Permission type</span></span> |   <span data-ttu-id="ab5f7-118">權限</span><span class="sxs-lookup"><span data-stu-id="ab5f7-118">Permission</span></span>  |   <span data-ttu-id="ab5f7-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="ab5f7-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ab5f7-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="ab5f7-120">Application</span></span> |   <span data-ttu-id="ab5f7-121">已讀取的 Ip。全部</span><span class="sxs-lookup"><span data-stu-id="ab5f7-121">Ip.Read.All</span></span> |   <span data-ttu-id="ab5f7-122">「讀取 IP 位址設定檔」</span><span class="sxs-lookup"><span data-stu-id="ab5f7-122">'Read IP address profiles'</span></span>
<span data-ttu-id="ab5f7-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="ab5f7-123">Delegated (work or school account)</span></span> | <span data-ttu-id="ab5f7-124">已讀取的 Ip。全部</span><span class="sxs-lookup"><span data-stu-id="ab5f7-124">Ip.Read.All</span></span> |  <span data-ttu-id="ab5f7-125">「讀取 IP 位址設定檔」</span><span class="sxs-lookup"><span data-stu-id="ab5f7-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="ab5f7-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="ab5f7-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ab5f7-127">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="ab5f7-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ab5f7-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ab5f7-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="ab5f7-129">要求標頭</span><span class="sxs-lookup"><span data-stu-id="ab5f7-129">Request headers</span></span>

<span data-ttu-id="ab5f7-130">名稱</span><span class="sxs-lookup"><span data-stu-id="ab5f7-130">Name</span></span> | <span data-ttu-id="ab5f7-131">類型</span><span class="sxs-lookup"><span data-stu-id="ab5f7-131">Type</span></span> | <span data-ttu-id="ab5f7-132">描述</span><span class="sxs-lookup"><span data-stu-id="ab5f7-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="ab5f7-133">授權</span><span class="sxs-lookup"><span data-stu-id="ab5f7-133">Authorization</span></span> | <span data-ttu-id="ab5f7-134">字串</span><span class="sxs-lookup"><span data-stu-id="ab5f7-134">String</span></span> | <span data-ttu-id="ab5f7-135">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-135">Bearer {token}.</span></span> <span data-ttu-id="ab5f7-136">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="ab5f7-137">要求 URI 參數</span><span class="sxs-lookup"><span data-stu-id="ab5f7-137">Request URI parameters</span></span>

<span data-ttu-id="ab5f7-138">名稱</span><span class="sxs-lookup"><span data-stu-id="ab5f7-138">Name</span></span> | <span data-ttu-id="ab5f7-139">類型</span><span class="sxs-lookup"><span data-stu-id="ab5f7-139">Type</span></span> | <span data-ttu-id="ab5f7-140">描述</span><span class="sxs-lookup"><span data-stu-id="ab5f7-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="ab5f7-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="ab5f7-141">lookBackHours</span></span> | <span data-ttu-id="ab5f7-142">Int32</span><span class="sxs-lookup"><span data-stu-id="ab5f7-142">Int32</span></span> | <span data-ttu-id="ab5f7-143">定義我們回叫以取得統計資料的小時數。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="ab5f7-144">預設為30天。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-144">Defaults to 30 days.</span></span> <span data-ttu-id="ab5f7-145">此為選擇性欄位。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ab5f7-146">要求正文</span><span class="sxs-lookup"><span data-stu-id="ab5f7-146">Request body</span></span>
<span data-ttu-id="ab5f7-147">空白</span><span class="sxs-lookup"><span data-stu-id="ab5f7-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ab5f7-148">回應</span><span class="sxs-lookup"><span data-stu-id="ab5f7-148">Response</span></span>
<span data-ttu-id="ab5f7-149">如果成功，且 ip 存在-200，包含正文中的統計資料。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="ab5f7-150">IP 不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ab5f7-151">範例</span><span class="sxs-lookup"><span data-stu-id="ab5f7-151">Example</span></span>

<span data-ttu-id="ab5f7-152">**請求**</span><span class="sxs-lookup"><span data-stu-id="ab5f7-152">**Request**</span></span>

<span data-ttu-id="ab5f7-153">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="ab5f7-154">**回應**</span><span class="sxs-lookup"><span data-stu-id="ab5f7-154">**Response**</span></span>

<span data-ttu-id="ab5f7-155">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="ab5f7-156">名稱</span><span class="sxs-lookup"><span data-stu-id="ab5f7-156">Name</span></span> | <span data-ttu-id="ab5f7-157">描述</span><span class="sxs-lookup"><span data-stu-id="ab5f7-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="ab5f7-158">組織的流行</span><span class="sxs-lookup"><span data-stu-id="ab5f7-158">Org prevalence</span></span> | <span data-ttu-id="ab5f7-159">開啟此 IP 之網路連線的裝置的 distinct 計數。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="ab5f7-160">第一次查看的組織</span><span class="sxs-lookup"><span data-stu-id="ab5f7-160">Org first seen</span></span> | <span data-ttu-id="ab5f7-161">組織中第一個此 IP 的連線。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="ab5f7-162">上次查看的組織</span><span class="sxs-lookup"><span data-stu-id="ab5f7-162">Org last seen</span></span>  | <span data-ttu-id="ab5f7-163">組織中此 IP 的最後一個連接。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="ab5f7-164">這項統計資料是以過去30天內的資料為基礎。</span><span class="sxs-lookup"><span data-stu-id="ab5f7-164">This statistic information is based on data from the past 30 days.</span></span> 
