---
title: 取得警示相關檔案資訊
description: 使用 Microsoft Defender for Endpoint，取回與特定警示相關的所有檔案。
keywords: api、graph api、支援的 api、取得警示資訊、警示資訊、相關檔案
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
ms.openlocfilehash: 369dd35c65094d5a5985b471bec506cb5d266e59
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772345"
---
# <a name="get-alert-related-files-information-api"></a><span data-ttu-id="df32a-104">取得警示相關檔案資訊 API</span><span class="sxs-lookup"><span data-stu-id="df32a-104">Get alert related files information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="df32a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="df32a-105">**Applies to:**</span></span>
- [<span data-ttu-id="df32a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="df32a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="df32a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df32a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
 
> <span data-ttu-id="df32a-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="df32a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="df32a-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="df32a-109">Sign up for free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="df32a-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="df32a-110">API description</span></span>
<span data-ttu-id="df32a-111">會檢索與特定警示相關的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="df32a-111">Retrieves all files related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="df32a-112">限制</span><span class="sxs-lookup"><span data-stu-id="df32a-112">Limitations</span></span>
1. <span data-ttu-id="df32a-113">您可以根據您設定的保留期間，查詢上次更新的警示。</span><span class="sxs-lookup"><span data-stu-id="df32a-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="df32a-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="df32a-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="df32a-115">權限</span><span class="sxs-lookup"><span data-stu-id="df32a-115">Permissions</span></span>
<span data-ttu-id="df32a-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="df32a-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="df32a-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="df32a-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="df32a-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="df32a-118">Permission type</span></span> | <span data-ttu-id="df32a-119">權限</span><span class="sxs-lookup"><span data-stu-id="df32a-119">Permission</span></span> | <span data-ttu-id="df32a-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="df32a-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="df32a-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="df32a-121">Application</span></span> | <span data-ttu-id="df32a-122">Read。 All</span><span class="sxs-lookup"><span data-stu-id="df32a-122">File.Read.All</span></span> | <span data-ttu-id="df32a-123">「讀取檔案設定檔」</span><span class="sxs-lookup"><span data-stu-id="df32a-123">'Read file profiles'</span></span>
<span data-ttu-id="df32a-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="df32a-124">Delegated (work or school account)</span></span> | <span data-ttu-id="df32a-125">Read。 All</span><span class="sxs-lookup"><span data-stu-id="df32a-125">File.Read.All</span></span> | <span data-ttu-id="df32a-126">「讀取檔案設定檔」</span><span class="sxs-lookup"><span data-stu-id="df32a-126">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="df32a-127">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="df32a-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="df32a-128">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="df32a-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="df32a-129">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="df32a-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="df32a-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="df32a-130">HTTP request</span></span>
```
GET /api/alerts/{id}/files
```

## <a name="request-headers"></a><span data-ttu-id="df32a-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="df32a-131">Request headers</span></span>

<span data-ttu-id="df32a-132">名稱</span><span class="sxs-lookup"><span data-stu-id="df32a-132">Name</span></span> | <span data-ttu-id="df32a-133">類型</span><span class="sxs-lookup"><span data-stu-id="df32a-133">Type</span></span> | <span data-ttu-id="df32a-134">描述</span><span class="sxs-lookup"><span data-stu-id="df32a-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="df32a-135">授權</span><span class="sxs-lookup"><span data-stu-id="df32a-135">Authorization</span></span> | <span data-ttu-id="df32a-136">字串</span><span class="sxs-lookup"><span data-stu-id="df32a-136">String</span></span> | <span data-ttu-id="df32a-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="df32a-137">Bearer {token}.</span></span> <span data-ttu-id="df32a-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="df32a-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="df32a-139">要求正文</span><span class="sxs-lookup"><span data-stu-id="df32a-139">Request body</span></span>
<span data-ttu-id="df32a-140">空白</span><span class="sxs-lookup"><span data-stu-id="df32a-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="df32a-141">回應</span><span class="sxs-lookup"><span data-stu-id="df32a-141">Response</span></span>
<span data-ttu-id="df32a-142">如果成功及警示和檔案存在-200 確定。</span><span class="sxs-lookup"><span data-stu-id="df32a-142">If successful and alert and files exist - 200 OK.</span></span> <span data-ttu-id="df32a-143">如果找不到警示-找不到404。</span><span class="sxs-lookup"><span data-stu-id="df32a-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="df32a-144">範例</span><span class="sxs-lookup"><span data-stu-id="df32a-144">Example</span></span>

<span data-ttu-id="df32a-145">**請求**</span><span class="sxs-lookup"><span data-stu-id="df32a-145">**Request**</span></span>

<span data-ttu-id="df32a-146">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="df32a-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/files
```

<span data-ttu-id="df32a-147">**回應**</span><span class="sxs-lookup"><span data-stu-id="df32a-147">**Response**</span></span>

<span data-ttu-id="df32a-148">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="df32a-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files",
    "value": [
        {
            "sha1": "f2a00fd2f2de1be0214b8529f1e9f67096c1aa70",
            "sha256": "dcd71ef5fff4362a9f64cf3f96f14f2b11d6f428f3badbedcb9ff3361e7079aa",
            "md5": "8d5b7cc9a832e21d22503057e1fec8e9",
            "globalPrevalence": 29,
            "globalFirstObserved": "2019-03-23T23:54:06.0135204Z",
            "globalLastObserved": "2019-04-23T00:43:20.0489831Z",
            "size": 113984,
            "fileType": null,
            "isPeFile": true,
            "filePublisher": "Microsoft Corporation",
            "fileProductName": "Microsoft� Windows� Operating System",
            "signer": "Microsoft Corporation",
            "issuer": "Microsoft Code Signing PCA",
            "signerHash": "9dc17888b5cfad98b3cb35c1994e96227f061675",
            "isValidCertificate": true,
            "determinationType": "Unknown",
            "determinationValue": null
        }
        ...
    ]
}
```
