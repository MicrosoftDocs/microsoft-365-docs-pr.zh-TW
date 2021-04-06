---
title: 取得使用者相關的電腦 API
description: 瞭解如何使用 [取得使用者相關的電腦 API]，以取得與 Microsoft Defender for Endpoint 中的使用者識別碼相關的裝置集合。
keywords: api、graph api、支援的 api、get、user、user 相關聯的警示
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
ms.openlocfilehash: 135dc1d76a1a90cd7fffba0638211d716865cb0c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166385"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="a0945-104">取得使用者相關的電腦 API</span><span class="sxs-lookup"><span data-stu-id="a0945-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0945-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a0945-105">**Applies to:**</span></span>
- [<span data-ttu-id="a0945-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a0945-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a0945-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0945-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a0945-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a0945-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a0945-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a0945-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a0945-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="a0945-110">API description</span></span>
<span data-ttu-id="a0945-111">會檢索與指定之使用者識別碼相關的裝置集合。</span><span class="sxs-lookup"><span data-stu-id="a0945-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="a0945-112">限制</span><span class="sxs-lookup"><span data-stu-id="a0945-112">Limitations</span></span>
1. <span data-ttu-id="a0945-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="a0945-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a0945-114">權限</span><span class="sxs-lookup"><span data-stu-id="a0945-114">Permissions</span></span>
<span data-ttu-id="a0945-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="a0945-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a0945-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a0945-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a0945-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="a0945-117">Permission type</span></span> |   <span data-ttu-id="a0945-118">權限</span><span class="sxs-lookup"><span data-stu-id="a0945-118">Permission</span></span>  |   <span data-ttu-id="a0945-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a0945-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a0945-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="a0945-120">Application</span></span> |   <span data-ttu-id="a0945-121">Read。所有</span><span class="sxs-lookup"><span data-stu-id="a0945-121">Machine.Read.All</span></span> |  <span data-ttu-id="a0945-122">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="a0945-122">'Read all machine profiles'</span></span>
<span data-ttu-id="a0945-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="a0945-123">Application</span></span> |   <span data-ttu-id="a0945-124">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="a0945-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="a0945-125">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="a0945-125">'Read and write all machine information'</span></span>
<span data-ttu-id="a0945-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a0945-126">Delegated (work or school account)</span></span> | <span data-ttu-id="a0945-127">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="a0945-127">Machine.Read</span></span> | <span data-ttu-id="a0945-128">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="a0945-128">'Read machine information'</span></span>
<span data-ttu-id="a0945-129">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a0945-129">Delegated (work or school account)</span></span> | <span data-ttu-id="a0945-130">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a0945-130">Machine.ReadWrite</span></span> | <span data-ttu-id="a0945-131">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="a0945-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="a0945-132">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="a0945-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a0945-133">使用者至少必須具備下列角色許可權：「View Data」。</span><span class="sxs-lookup"><span data-stu-id="a0945-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="a0945-134">如需詳細資訊，請參閱 [Create and manage roles](user-roles.md) ) </span><span class="sxs-lookup"><span data-stu-id="a0945-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="a0945-135">回應只會包含使用者可以存取的裝置（根據裝置群組設定）。</span><span class="sxs-lookup"><span data-stu-id="a0945-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="a0945-136">如需詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="a0945-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="a0945-137">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a0945-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="a0945-138">**識別碼不是完整的 UPN，只是使用者名稱。 (例如，若要取得 user1@contoso.com 的機器使用/api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="a0945-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="a0945-139">要求標頭</span><span class="sxs-lookup"><span data-stu-id="a0945-139">Request headers</span></span>

<span data-ttu-id="a0945-140">名稱</span><span class="sxs-lookup"><span data-stu-id="a0945-140">Name</span></span> | <span data-ttu-id="a0945-141">類型</span><span class="sxs-lookup"><span data-stu-id="a0945-141">Type</span></span> | <span data-ttu-id="a0945-142">描述</span><span class="sxs-lookup"><span data-stu-id="a0945-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="a0945-143">授權</span><span class="sxs-lookup"><span data-stu-id="a0945-143">Authorization</span></span> | <span data-ttu-id="a0945-144">字串</span><span class="sxs-lookup"><span data-stu-id="a0945-144">String</span></span> | <span data-ttu-id="a0945-145">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="a0945-145">Bearer {token}.</span></span> <span data-ttu-id="a0945-146">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="a0945-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a0945-147">要求正文</span><span class="sxs-lookup"><span data-stu-id="a0945-147">Request body</span></span>
<span data-ttu-id="a0945-148">空白</span><span class="sxs-lookup"><span data-stu-id="a0945-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a0945-149">回應</span><span class="sxs-lookup"><span data-stu-id="a0945-149">Response</span></span>
<span data-ttu-id="a0945-150">如果成功，且使用者存在-200 與主體中 [電腦](machine.md) 實體的清單，則為 [！]。</span><span class="sxs-lookup"><span data-stu-id="a0945-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="a0945-151">如果使用者不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="a0945-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="a0945-152">範例</span><span class="sxs-lookup"><span data-stu-id="a0945-152">Example</span></span>

<span data-ttu-id="a0945-153">**請求**</span><span class="sxs-lookup"><span data-stu-id="a0945-153">**Request**</span></span>

<span data-ttu-id="a0945-154">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="a0945-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```