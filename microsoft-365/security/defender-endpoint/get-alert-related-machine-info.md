---
title: 取得與警示相關的機器資訊
description: 使用 Microsoft Defender for Endpoint，取回與特定警示相關的所有裝置。
keywords: api，graph api，支援的 api，取得警示資訊，警示資訊，相關裝置
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
ms.openlocfilehash: ef10d2bd7193fc7b4a1604658f496ef38ef33555
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772338"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="65629-104">取得警示相關的機器資訊 API</span><span class="sxs-lookup"><span data-stu-id="65629-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="65629-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="65629-105">**Applies to:**</span></span>
- [<span data-ttu-id="65629-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="65629-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65629-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65629-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="65629-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="65629-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65629-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="65629-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="65629-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="65629-110">API description</span></span>
<span data-ttu-id="65629-111">會檢索與特定警示相關的 [裝置](machine.md) 。</span><span class="sxs-lookup"><span data-stu-id="65629-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="65629-112">限制</span><span class="sxs-lookup"><span data-stu-id="65629-112">Limitations</span></span>
1. <span data-ttu-id="65629-113">您可以根據您設定的保留期間，查詢上次更新的警示。</span><span class="sxs-lookup"><span data-stu-id="65629-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="65629-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="65629-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="65629-115">權限</span><span class="sxs-lookup"><span data-stu-id="65629-115">Permissions</span></span>
<span data-ttu-id="65629-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="65629-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="65629-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="65629-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="65629-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="65629-118">Permission type</span></span> |   <span data-ttu-id="65629-119">權限</span><span class="sxs-lookup"><span data-stu-id="65629-119">Permission</span></span>  |   <span data-ttu-id="65629-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="65629-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="65629-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="65629-121">Application</span></span> |   <span data-ttu-id="65629-122">Read。所有</span><span class="sxs-lookup"><span data-stu-id="65629-122">Machine.Read.All</span></span> |  <span data-ttu-id="65629-123">「讀取所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="65629-123">'Read all machine information'</span></span>
<span data-ttu-id="65629-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="65629-124">Application</span></span> |   <span data-ttu-id="65629-125">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="65629-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="65629-126">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="65629-126">'Read and write all machine information'</span></span>
<span data-ttu-id="65629-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="65629-127">Delegated (work or school account)</span></span> | <span data-ttu-id="65629-128">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="65629-128">Machine.Read</span></span> | <span data-ttu-id="65629-129">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="65629-129">'Read machine information'</span></span>
<span data-ttu-id="65629-130">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="65629-130">Delegated (work or school account)</span></span> | <span data-ttu-id="65629-131">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="65629-131">Machine.ReadWrite</span></span> | <span data-ttu-id="65629-132">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="65629-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="65629-133">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="65629-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="65629-134">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="65629-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="65629-135">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="65629-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="65629-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="65629-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="65629-137">要求標頭</span><span class="sxs-lookup"><span data-stu-id="65629-137">Request headers</span></span>

<span data-ttu-id="65629-138">名稱</span><span class="sxs-lookup"><span data-stu-id="65629-138">Name</span></span> | <span data-ttu-id="65629-139">類型</span><span class="sxs-lookup"><span data-stu-id="65629-139">Type</span></span> | <span data-ttu-id="65629-140">描述</span><span class="sxs-lookup"><span data-stu-id="65629-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="65629-141">授權</span><span class="sxs-lookup"><span data-stu-id="65629-141">Authorization</span></span> | <span data-ttu-id="65629-142">字串</span><span class="sxs-lookup"><span data-stu-id="65629-142">String</span></span> | <span data-ttu-id="65629-143">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="65629-143">Bearer {token}.</span></span> <span data-ttu-id="65629-144">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="65629-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="65629-145">要求正文</span><span class="sxs-lookup"><span data-stu-id="65629-145">Request body</span></span>
<span data-ttu-id="65629-146">空白</span><span class="sxs-lookup"><span data-stu-id="65629-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="65629-147">回應</span><span class="sxs-lookup"><span data-stu-id="65629-147">Response</span></span>
<span data-ttu-id="65629-148">如果成功及警示和裝置都存在-200 OK。</span><span class="sxs-lookup"><span data-stu-id="65629-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="65629-149">如果找不到警示或未找到裝置-找不到404。</span><span class="sxs-lookup"><span data-stu-id="65629-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="65629-150">範例</span><span class="sxs-lookup"><span data-stu-id="65629-150">Example</span></span>

<span data-ttu-id="65629-151">**請求**</span><span class="sxs-lookup"><span data-stu-id="65629-151">**Request**</span></span>

<span data-ttu-id="65629-152">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="65629-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="65629-153">**回應**</span><span class="sxs-lookup"><span data-stu-id="65629-153">**Response**</span></span>

<span data-ttu-id="65629-154">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="65629-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
