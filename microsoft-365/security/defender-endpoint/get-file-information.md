---
title: 取得檔資訊 API
description: 瞭解如何使用 Get file information API，在 Microsoft Defender for Endpoint 中透過 Sha1、Sha256 或 MD5 識別碼取得檔案。
keywords: api、graph api、支援的 api、get、file、information、sha1、sha256、md5
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
ms.openlocfilehash: 181d808b465bfbf26eeff48a564e231b00a9a77f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166394"
---
# <a name="get-file-information-api"></a><span data-ttu-id="3695a-104">取得檔資訊 API</span><span class="sxs-lookup"><span data-stu-id="3695a-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3695a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3695a-105">**Applies to:**</span></span>
- [<span data-ttu-id="3695a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3695a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3695a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3695a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3695a-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3695a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3695a-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3695a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3695a-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="3695a-110">API description</span></span>
<span data-ttu-id="3695a-111">[依識別碼](files.md)Sha1 或 Sha256 來檢索檔案</span><span class="sxs-lookup"><span data-stu-id="3695a-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="3695a-112">限制</span><span class="sxs-lookup"><span data-stu-id="3695a-112">Limitations</span></span>
1. <span data-ttu-id="3695a-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="3695a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3695a-114">權限</span><span class="sxs-lookup"><span data-stu-id="3695a-114">Permissions</span></span>
<span data-ttu-id="3695a-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3695a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3695a-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3695a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3695a-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3695a-117">Permission type</span></span> |   <span data-ttu-id="3695a-118">權限</span><span class="sxs-lookup"><span data-stu-id="3695a-118">Permission</span></span>  |   <span data-ttu-id="3695a-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3695a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3695a-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="3695a-120">Application</span></span> |   <span data-ttu-id="3695a-121">Read。 All</span><span class="sxs-lookup"><span data-stu-id="3695a-121">File.Read.All</span></span> | <span data-ttu-id="3695a-122">「讀取所有檔案設定檔」</span><span class="sxs-lookup"><span data-stu-id="3695a-122">'Read all file profiles'</span></span>
<span data-ttu-id="3695a-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3695a-123">Delegated (work or school account)</span></span> | <span data-ttu-id="3695a-124">Read。 All</span><span class="sxs-lookup"><span data-stu-id="3695a-124">File.Read.All</span></span> |    <span data-ttu-id="3695a-125">「讀取所有檔案設定檔」</span><span class="sxs-lookup"><span data-stu-id="3695a-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="3695a-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="3695a-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3695a-127">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="3695a-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3695a-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3695a-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="3695a-129">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3695a-129">Request headers</span></span>

<span data-ttu-id="3695a-130">名稱</span><span class="sxs-lookup"><span data-stu-id="3695a-130">Name</span></span> | <span data-ttu-id="3695a-131">類型</span><span class="sxs-lookup"><span data-stu-id="3695a-131">Type</span></span> | <span data-ttu-id="3695a-132">描述</span><span class="sxs-lookup"><span data-stu-id="3695a-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="3695a-133">授權</span><span class="sxs-lookup"><span data-stu-id="3695a-133">Authorization</span></span> | <span data-ttu-id="3695a-134">字串</span><span class="sxs-lookup"><span data-stu-id="3695a-134">String</span></span> | <span data-ttu-id="3695a-135">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="3695a-135">Bearer {token}.</span></span> <span data-ttu-id="3695a-136">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3695a-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3695a-137">要求正文</span><span class="sxs-lookup"><span data-stu-id="3695a-137">Request body</span></span>
<span data-ttu-id="3695a-138">空白</span><span class="sxs-lookup"><span data-stu-id="3695a-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3695a-139">回應</span><span class="sxs-lookup"><span data-stu-id="3695a-139">Response</span></span>
<span data-ttu-id="3695a-140">如果成功和檔案存在-200 OK，與 body 中的[檔案實體。](files.md)</span><span class="sxs-lookup"><span data-stu-id="3695a-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="3695a-141">如果檔案不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="3695a-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3695a-142">範例</span><span class="sxs-lookup"><span data-stu-id="3695a-142">Example</span></span>

<span data-ttu-id="3695a-143">**請求**</span><span class="sxs-lookup"><span data-stu-id="3695a-143">**Request**</span></span>

<span data-ttu-id="3695a-144">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3695a-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="3695a-145">**回應**</span><span class="sxs-lookup"><span data-stu-id="3695a-145">**Response**</span></span>

<span data-ttu-id="3695a-146">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="3695a-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
