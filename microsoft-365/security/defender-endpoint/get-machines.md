---
title: 列出電腦 API
description: 瞭解如何使用清單電腦 API，以取得與 Microsoft Defender for Endpoint cloud 通訊的電腦集合。
keywords: api、graph api、支援的 api、get、裝置
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
ms.topic: article
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d52e1b69311c26144684b90545e17934d1223332
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287852"
---
# <a name="list-machines-api"></a><span data-ttu-id="0cd19-104">列出電腦 API</span><span class="sxs-lookup"><span data-stu-id="0cd19-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0cd19-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0cd19-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0cd19-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="0cd19-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0cd19-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0cd19-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="0cd19-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="0cd19-108">API description</span></span>
<span data-ttu-id="0cd19-109">檢索與 Microsoft Defender for Endpoint cloud 通訊的 [電腦](machine.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="0cd19-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="0cd19-110">支援 [OData V4 查詢](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="0cd19-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="0cd19-111">支援 OData 的 `$filter` 查詢：、、、 `computerDnsName` `lastSeen` `healthStatus` `osPlatform` `riskScore` 和 `rbacGroupId` 。</span><span class="sxs-lookup"><span data-stu-id="0cd19-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="0cd19-112">在[使用 Defender For Endpoint 的 OData 查詢](exposed-apis-odata-samples.md)中，請參閱範例</span><span class="sxs-lookup"><span data-stu-id="0cd19-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="0cd19-113">限制</span><span class="sxs-lookup"><span data-stu-id="0cd19-113">Limitations</span></span>
1. <span data-ttu-id="0cd19-114">您可以根據您設定的保留期間，取得上一個看到的裝置。</span><span class="sxs-lookup"><span data-stu-id="0cd19-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="0cd19-115">頁面大小上限為10000。</span><span class="sxs-lookup"><span data-stu-id="0cd19-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="0cd19-116">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="0cd19-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="0cd19-117">權限</span><span class="sxs-lookup"><span data-stu-id="0cd19-117">Permissions</span></span>

<span data-ttu-id="0cd19-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="0cd19-118">Permission type</span></span> |   <span data-ttu-id="0cd19-119">權限</span><span class="sxs-lookup"><span data-stu-id="0cd19-119">Permission</span></span>  |   <span data-ttu-id="0cd19-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="0cd19-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0cd19-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="0cd19-121">Application</span></span> |   <span data-ttu-id="0cd19-122">Read。所有</span><span class="sxs-lookup"><span data-stu-id="0cd19-122">Machine.Read.All</span></span> |  <span data-ttu-id="0cd19-123">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="0cd19-123">'Read all machine profiles'</span></span>
<span data-ttu-id="0cd19-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="0cd19-124">Application</span></span> |   <span data-ttu-id="0cd19-125">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="0cd19-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="0cd19-126">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="0cd19-126">'Read and write all machine information'</span></span>
<span data-ttu-id="0cd19-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="0cd19-127">Delegated (work or school account)</span></span> | <span data-ttu-id="0cd19-128">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="0cd19-128">Machine.Read</span></span> | <span data-ttu-id="0cd19-129">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="0cd19-129">'Read machine information'</span></span>
<span data-ttu-id="0cd19-130">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="0cd19-130">Delegated (work or school account)</span></span> | <span data-ttu-id="0cd19-131">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0cd19-131">Machine.ReadWrite</span></span> | <span data-ttu-id="0cd19-132">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="0cd19-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="0cd19-133">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="0cd19-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0cd19-134">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="0cd19-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="0cd19-135">回應僅包含使用者有權存取的裝置，並根據裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="0cd19-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0cd19-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="0cd19-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="0cd19-137">要求標頭</span><span class="sxs-lookup"><span data-stu-id="0cd19-137">Request headers</span></span>

<span data-ttu-id="0cd19-138">名稱</span><span class="sxs-lookup"><span data-stu-id="0cd19-138">Name</span></span> | <span data-ttu-id="0cd19-139">類型</span><span class="sxs-lookup"><span data-stu-id="0cd19-139">Type</span></span> | <span data-ttu-id="0cd19-140">說明</span><span class="sxs-lookup"><span data-stu-id="0cd19-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="0cd19-141">授權</span><span class="sxs-lookup"><span data-stu-id="0cd19-141">Authorization</span></span> | <span data-ttu-id="0cd19-142">字串</span><span class="sxs-lookup"><span data-stu-id="0cd19-142">String</span></span> | <span data-ttu-id="0cd19-143">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="0cd19-143">Bearer {token}.</span></span> <span data-ttu-id="0cd19-144">**必要**。</span><span class="sxs-lookup"><span data-stu-id="0cd19-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0cd19-145">要求內文</span><span class="sxs-lookup"><span data-stu-id="0cd19-145">Request body</span></span>
<span data-ttu-id="0cd19-146">空白</span><span class="sxs-lookup"><span data-stu-id="0cd19-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0cd19-147">回應</span><span class="sxs-lookup"><span data-stu-id="0cd19-147">Response</span></span>
<span data-ttu-id="0cd19-148">如果成功且機器存在-200 OK （含）主體中的 [機器](machine.md) 實體清單。</span><span class="sxs-lookup"><span data-stu-id="0cd19-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="0cd19-149">如果沒有找到最近的電腦-404。</span><span class="sxs-lookup"><span data-stu-id="0cd19-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="0cd19-150">範例</span><span class="sxs-lookup"><span data-stu-id="0cd19-150">Example</span></span>

<span data-ttu-id="0cd19-151">**請求**</span><span class="sxs-lookup"><span data-stu-id="0cd19-151">**Request**</span></span>

<span data-ttu-id="0cd19-152">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="0cd19-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="0cd19-153">**回應**</span><span class="sxs-lookup"><span data-stu-id="0cd19-153">**Response**</span></span>

<span data-ttu-id="0cd19-154">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="0cd19-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
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
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="0cd19-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="0cd19-155">Related topics</span></span>
- [<span data-ttu-id="0cd19-156">使用 Microsoft Defender for Endpoint OData 查詢</span><span class="sxs-lookup"><span data-stu-id="0cd19-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
