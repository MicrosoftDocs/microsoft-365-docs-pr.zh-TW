---
title: 取得警示相關的網域資訊
description: 使用 Microsoft Defender for Endpoint，取回與特定警示相關的所有網域。
keywords: api、graph api、支援的 api、取得警示資訊、警示資訊、相關的網域
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
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200410"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="2c16e-104">取得警示相關的網域資訊 API</span><span class="sxs-lookup"><span data-stu-id="2c16e-104">Get alert related domain information API</span></span>

<span data-ttu-id="2c16e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2c16e-105">**Applies to:**</span></span> 
- [<span data-ttu-id="2c16e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2c16e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="2c16e-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2c16e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2c16e-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2c16e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2c16e-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="2c16e-109">API description</span></span>
<span data-ttu-id="2c16e-110">會檢索與特定警示相關的所有網域。</span><span class="sxs-lookup"><span data-stu-id="2c16e-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="2c16e-111">限制</span><span class="sxs-lookup"><span data-stu-id="2c16e-111">Limitations</span></span>
1. <span data-ttu-id="2c16e-112">您可以根據您設定的保留期間，查詢上次更新的警示。</span><span class="sxs-lookup"><span data-stu-id="2c16e-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="2c16e-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="2c16e-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2c16e-114">權限</span><span class="sxs-lookup"><span data-stu-id="2c16e-114">Permissions</span></span>
<span data-ttu-id="2c16e-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="2c16e-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2c16e-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2c16e-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2c16e-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="2c16e-117">Permission type</span></span> | <span data-ttu-id="2c16e-118">權限</span><span class="sxs-lookup"><span data-stu-id="2c16e-118">Permission</span></span> | <span data-ttu-id="2c16e-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="2c16e-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2c16e-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="2c16e-120">Application</span></span> | <span data-ttu-id="2c16e-121">URL:。Read。所有</span><span class="sxs-lookup"><span data-stu-id="2c16e-121">URL.Read.All</span></span> | <span data-ttu-id="2c16e-122">「讀取 URLs '</span><span class="sxs-lookup"><span data-stu-id="2c16e-122">'Read URLs'</span></span>
<span data-ttu-id="2c16e-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="2c16e-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2c16e-124">URL:。Read。所有</span><span class="sxs-lookup"><span data-stu-id="2c16e-124">URL.Read.All</span></span> | <span data-ttu-id="2c16e-125">「讀取 URLs '</span><span class="sxs-lookup"><span data-stu-id="2c16e-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="2c16e-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="2c16e-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2c16e-127">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="2c16e-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2c16e-128">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="2c16e-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2c16e-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="2c16e-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="2c16e-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="2c16e-130">Request headers</span></span>

<span data-ttu-id="2c16e-131">名稱</span><span class="sxs-lookup"><span data-stu-id="2c16e-131">Name</span></span> | <span data-ttu-id="2c16e-132">類型</span><span class="sxs-lookup"><span data-stu-id="2c16e-132">Type</span></span> | <span data-ttu-id="2c16e-133">描述</span><span class="sxs-lookup"><span data-stu-id="2c16e-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="2c16e-134">授權</span><span class="sxs-lookup"><span data-stu-id="2c16e-134">Authorization</span></span> | <span data-ttu-id="2c16e-135">字串</span><span class="sxs-lookup"><span data-stu-id="2c16e-135">String</span></span> | <span data-ttu-id="2c16e-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="2c16e-136">Bearer {token}.</span></span> <span data-ttu-id="2c16e-137">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="2c16e-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2c16e-138">要求正文</span><span class="sxs-lookup"><span data-stu-id="2c16e-138">Request body</span></span>
<span data-ttu-id="2c16e-139">空白</span><span class="sxs-lookup"><span data-stu-id="2c16e-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2c16e-140">回應</span><span class="sxs-lookup"><span data-stu-id="2c16e-140">Response</span></span>
<span data-ttu-id="2c16e-141">如果成功且警示和網域存在-200 確定。</span><span class="sxs-lookup"><span data-stu-id="2c16e-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="2c16e-142">如果找不到警示-找不到404。</span><span class="sxs-lookup"><span data-stu-id="2c16e-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="2c16e-143">範例</span><span class="sxs-lookup"><span data-stu-id="2c16e-143">Example</span></span>

<span data-ttu-id="2c16e-144">**請求**</span><span class="sxs-lookup"><span data-stu-id="2c16e-144">**Request**</span></span>

<span data-ttu-id="2c16e-145">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="2c16e-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="2c16e-146">**回應**</span><span class="sxs-lookup"><span data-stu-id="2c16e-146">**Response**</span></span>

<span data-ttu-id="2c16e-147">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="2c16e-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
