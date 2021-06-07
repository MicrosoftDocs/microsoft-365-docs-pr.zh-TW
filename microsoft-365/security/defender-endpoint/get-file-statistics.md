---
title: 取得檔統計資料 API
description: 瞭解如何使用 [取得檔案統計資料] API，在 Microsoft Defender for Endpoint 中取得指定檔案的統計資料。
keywords: api、graph api、支援的 api、get、file、statistics
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
ms.openlocfilehash: 6063d29562be40aed3060e241b52b1a2936aa36d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770202"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="1e2b0-104">取得檔統計資料 API</span><span class="sxs-lookup"><span data-stu-id="1e2b0-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e2b0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="1e2b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e2b0-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1e2b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e2b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e2b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1e2b0-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="1e2b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1e2b0-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1e2b0-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="1e2b0-110">API description</span></span>
<span data-ttu-id="1e2b0-111">會檢索指定檔案的統計資料。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="1e2b0-112">限制</span><span class="sxs-lookup"><span data-stu-id="1e2b0-112">Limitations</span></span>
1. <span data-ttu-id="1e2b0-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1e2b0-114">權限</span><span class="sxs-lookup"><span data-stu-id="1e2b0-114">Permissions</span></span>
<span data-ttu-id="1e2b0-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1e2b0-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1e2b0-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1e2b0-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="1e2b0-117">Permission type</span></span> |   <span data-ttu-id="1e2b0-118">權限</span><span class="sxs-lookup"><span data-stu-id="1e2b0-118">Permission</span></span>  |   <span data-ttu-id="1e2b0-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="1e2b0-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1e2b0-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="1e2b0-120">Application</span></span> |   <span data-ttu-id="1e2b0-121">Read。 All</span><span class="sxs-lookup"><span data-stu-id="1e2b0-121">File.Read.All</span></span> | <span data-ttu-id="1e2b0-122">「讀取檔案設定檔」</span><span class="sxs-lookup"><span data-stu-id="1e2b0-122">'Read file profiles'</span></span>
<span data-ttu-id="1e2b0-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="1e2b0-123">Delegated (work or school account)</span></span> | <span data-ttu-id="1e2b0-124">Read。 All</span><span class="sxs-lookup"><span data-stu-id="1e2b0-124">File.Read.All</span></span> | <span data-ttu-id="1e2b0-125">「讀取檔案設定檔」</span><span class="sxs-lookup"><span data-stu-id="1e2b0-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="1e2b0-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="1e2b0-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1e2b0-127">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="1e2b0-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1e2b0-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1e2b0-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="1e2b0-129">要求標頭</span><span class="sxs-lookup"><span data-stu-id="1e2b0-129">Request headers</span></span>

<span data-ttu-id="1e2b0-130">名稱</span><span class="sxs-lookup"><span data-stu-id="1e2b0-130">Name</span></span> | <span data-ttu-id="1e2b0-131">類型</span><span class="sxs-lookup"><span data-stu-id="1e2b0-131">Type</span></span> | <span data-ttu-id="1e2b0-132">描述</span><span class="sxs-lookup"><span data-stu-id="1e2b0-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="1e2b0-133">授權</span><span class="sxs-lookup"><span data-stu-id="1e2b0-133">Authorization</span></span> | <span data-ttu-id="1e2b0-134">字串</span><span class="sxs-lookup"><span data-stu-id="1e2b0-134">String</span></span> | <span data-ttu-id="1e2b0-135">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-135">Bearer {token}.</span></span> <span data-ttu-id="1e2b0-136">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="1e2b0-137">要求 URI 參數</span><span class="sxs-lookup"><span data-stu-id="1e2b0-137">Request URI parameters</span></span>

<span data-ttu-id="1e2b0-138">名稱</span><span class="sxs-lookup"><span data-stu-id="1e2b0-138">Name</span></span> | <span data-ttu-id="1e2b0-139">類型</span><span class="sxs-lookup"><span data-stu-id="1e2b0-139">Type</span></span> | <span data-ttu-id="1e2b0-140">描述</span><span class="sxs-lookup"><span data-stu-id="1e2b0-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="1e2b0-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="1e2b0-141">lookBackHours</span></span> | <span data-ttu-id="1e2b0-142">Int32</span><span class="sxs-lookup"><span data-stu-id="1e2b0-142">Int32</span></span> | <span data-ttu-id="1e2b0-143">定義我們回叫以取得統計資料的小時數。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="1e2b0-144">預設為30天。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-144">Defaults to 30 days.</span></span> <span data-ttu-id="1e2b0-145">此為選擇性欄位。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1e2b0-146">要求正文</span><span class="sxs-lookup"><span data-stu-id="1e2b0-146">Request body</span></span>
<span data-ttu-id="1e2b0-147">空白</span><span class="sxs-lookup"><span data-stu-id="1e2b0-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1e2b0-148">回應</span><span class="sxs-lookup"><span data-stu-id="1e2b0-148">Response</span></span>
<span data-ttu-id="1e2b0-149">如果成功且檔案存在-200 會顯示正文中的統計資料。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="1e2b0-150">如果檔案不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1e2b0-151">範例</span><span class="sxs-lookup"><span data-stu-id="1e2b0-151">Example</span></span>

<span data-ttu-id="1e2b0-152">**請求**</span><span class="sxs-lookup"><span data-stu-id="1e2b0-152">**Request**</span></span>

<span data-ttu-id="1e2b0-153">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="1e2b0-154">**回應**</span><span class="sxs-lookup"><span data-stu-id="1e2b0-154">**Response**</span></span>

<span data-ttu-id="1e2b0-155">以下是回應的範例。</span><span class="sxs-lookup"><span data-stu-id="1e2b0-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
