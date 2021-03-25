---
title: 取得檔相關的電腦 API
description: 瞭解如何使用 [取得檔案相關的電腦 API]，以取得與 Microsoft Defender for Endpoint 中的檔案雜湊相關的電腦集合。
keywords: api、graph api、支援的 api、get、裝置、雜湊
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
ms.openlocfilehash: 051bdad362e142446d248e90fad608fe5c0f016f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166387"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="31433-104">取得檔相關的電腦 API</span><span class="sxs-lookup"><span data-stu-id="31433-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31433-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="31433-105">**Applies to:**</span></span>
- [<span data-ttu-id="31433-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="31433-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="31433-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31433-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="31433-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="31433-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31433-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="31433-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="31433-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="31433-110">API description</span></span>
<span data-ttu-id="31433-111">會檢索與指定的檔案雜湊相關的 [電腦](machine.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="31433-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="31433-112">限制</span><span class="sxs-lookup"><span data-stu-id="31433-112">Limitations</span></span>
1. <span data-ttu-id="31433-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="31433-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="31433-114">權限</span><span class="sxs-lookup"><span data-stu-id="31433-114">Permissions</span></span>
<span data-ttu-id="31433-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="31433-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31433-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="31433-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="31433-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="31433-117">Permission type</span></span> |   <span data-ttu-id="31433-118">權限</span><span class="sxs-lookup"><span data-stu-id="31433-118">Permission</span></span>  |   <span data-ttu-id="31433-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="31433-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31433-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="31433-120">Application</span></span> |   <span data-ttu-id="31433-121">Read。所有</span><span class="sxs-lookup"><span data-stu-id="31433-121">Machine.Read.All</span></span> |  <span data-ttu-id="31433-122">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="31433-122">'Read all machine profiles'</span></span>
<span data-ttu-id="31433-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="31433-123">Application</span></span> |   <span data-ttu-id="31433-124">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="31433-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="31433-125">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="31433-125">'Read and write all machine information'</span></span>
<span data-ttu-id="31433-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="31433-126">Delegated (work or school account)</span></span> | <span data-ttu-id="31433-127">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="31433-127">Machine.Read</span></span> | <span data-ttu-id="31433-128">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="31433-128">'Read machine information'</span></span>
<span data-ttu-id="31433-129">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="31433-129">Delegated (work or school account)</span></span> | <span data-ttu-id="31433-130">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="31433-130">Machine.ReadWrite</span></span> | <span data-ttu-id="31433-131">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="31433-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="31433-132">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="31433-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="31433-133">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="31433-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="31433-134">回應僅包含使用者有權存取的裝置，並根據裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="31433-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="31433-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="31433-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="31433-136">要求標頭</span><span class="sxs-lookup"><span data-stu-id="31433-136">Request headers</span></span>

<span data-ttu-id="31433-137">名稱</span><span class="sxs-lookup"><span data-stu-id="31433-137">Name</span></span> | <span data-ttu-id="31433-138">類型</span><span class="sxs-lookup"><span data-stu-id="31433-138">Type</span></span> | <span data-ttu-id="31433-139">描述</span><span class="sxs-lookup"><span data-stu-id="31433-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="31433-140">授權</span><span class="sxs-lookup"><span data-stu-id="31433-140">Authorization</span></span> | <span data-ttu-id="31433-141">字串</span><span class="sxs-lookup"><span data-stu-id="31433-141">String</span></span> | <span data-ttu-id="31433-142">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="31433-142">Bearer {token}.</span></span> <span data-ttu-id="31433-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="31433-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="31433-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="31433-144">Request body</span></span>
<span data-ttu-id="31433-145">空白</span><span class="sxs-lookup"><span data-stu-id="31433-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="31433-146">回應</span><span class="sxs-lookup"><span data-stu-id="31433-146">Response</span></span>
<span data-ttu-id="31433-147">如果成功和檔案存在-200 OK （含）主體中的 [機器](machine.md) 實體清單。</span><span class="sxs-lookup"><span data-stu-id="31433-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="31433-148">如果檔案不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="31433-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="31433-149">範例</span><span class="sxs-lookup"><span data-stu-id="31433-149">Example</span></span>

<span data-ttu-id="31433-150">**請求**</span><span class="sxs-lookup"><span data-stu-id="31433-150">**Request**</span></span>

<span data-ttu-id="31433-151">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="31433-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
