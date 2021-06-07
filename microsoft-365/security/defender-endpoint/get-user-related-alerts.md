---
title: 取得使用者相關的警示 API
description: 使用 Microsoft Defender for Endpoint，檢索與指定之使用者識別碼相關的提醒集合。
keywords: api、graph api、支援的 api、get、user、相關的警示
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769926"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="a4ad1-104">取得使用者相關的警示 API</span><span class="sxs-lookup"><span data-stu-id="a4ad1-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4ad1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a4ad1-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4ad1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a4ad1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a4ad1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4ad1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a4ad1-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a4ad1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a4ad1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a4ad1-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="a4ad1-110">API description</span></span>
<span data-ttu-id="a4ad1-111">會檢索與指定之使用者識別碼相關的警示集合。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="a4ad1-112">限制</span><span class="sxs-lookup"><span data-stu-id="a4ad1-112">Limitations</span></span>
1. <span data-ttu-id="a4ad1-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a4ad1-114">權限</span><span class="sxs-lookup"><span data-stu-id="a4ad1-114">Permissions</span></span>
<span data-ttu-id="a4ad1-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a4ad1-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a4ad1-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a4ad1-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="a4ad1-117">Permission type</span></span> |   <span data-ttu-id="a4ad1-118">權限</span><span class="sxs-lookup"><span data-stu-id="a4ad1-118">Permission</span></span>  |   <span data-ttu-id="a4ad1-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a4ad1-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a4ad1-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="a4ad1-120">Application</span></span> |   <span data-ttu-id="a4ad1-121">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="a4ad1-121">Alert.Read.All</span></span> |    <span data-ttu-id="a4ad1-122">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="a4ad1-122">'Read all alerts'</span></span>
<span data-ttu-id="a4ad1-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="a4ad1-123">Application</span></span> |   <span data-ttu-id="a4ad1-124">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="a4ad1-125">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="a4ad1-125">'Read and write all alerts'</span></span>
<span data-ttu-id="a4ad1-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a4ad1-126">Delegated (work or school account)</span></span> | <span data-ttu-id="a4ad1-127">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="a4ad1-127">Alert.Read</span></span> | <span data-ttu-id="a4ad1-128">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="a4ad1-128">'Read alerts'</span></span>
<span data-ttu-id="a4ad1-129">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a4ad1-129">Delegated (work or school account)</span></span> | <span data-ttu-id="a4ad1-130">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a4ad1-130">Alert.ReadWrite</span></span> | <span data-ttu-id="a4ad1-131">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="a4ad1-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="a4ad1-132">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="a4ad1-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a4ad1-133">使用者至少必須具備下列角色許可權：「View Data」。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="a4ad1-134">如需詳細資訊，請參閱 [Create and manage roles](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="a4ad1-135">回應只會包含使用者有權存取之裝置的警示（取決於裝置群組設定） (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="a4ad1-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a4ad1-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a4ad1-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="a4ad1-137">**識別碼不是完整的 UPN，只是使用者名稱。 (例如，若要取得 user1@contoso.com 的警示，請使用/api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="a4ad1-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="a4ad1-138">要求標頭</span><span class="sxs-lookup"><span data-stu-id="a4ad1-138">Request headers</span></span>

<span data-ttu-id="a4ad1-139">名稱</span><span class="sxs-lookup"><span data-stu-id="a4ad1-139">Name</span></span> | <span data-ttu-id="a4ad1-140">類型</span><span class="sxs-lookup"><span data-stu-id="a4ad1-140">Type</span></span> | <span data-ttu-id="a4ad1-141">描述</span><span class="sxs-lookup"><span data-stu-id="a4ad1-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="a4ad1-142">授權</span><span class="sxs-lookup"><span data-stu-id="a4ad1-142">Authorization</span></span> | <span data-ttu-id="a4ad1-143">字串</span><span class="sxs-lookup"><span data-stu-id="a4ad1-143">String</span></span> | <span data-ttu-id="a4ad1-144">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-144">Bearer {token}.</span></span> <span data-ttu-id="a4ad1-145">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a4ad1-146">要求正文</span><span class="sxs-lookup"><span data-stu-id="a4ad1-146">Request body</span></span>
<span data-ttu-id="a4ad1-147">空白</span><span class="sxs-lookup"><span data-stu-id="a4ad1-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a4ad1-148">回應</span><span class="sxs-lookup"><span data-stu-id="a4ad1-148">Response</span></span>
<span data-ttu-id="a4ad1-149">如果成功且使用者存在-200 OK。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="a4ad1-150">如果使用者不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="a4ad1-151">範例</span><span class="sxs-lookup"><span data-stu-id="a4ad1-151">Example</span></span>

<span data-ttu-id="a4ad1-152">**請求**</span><span class="sxs-lookup"><span data-stu-id="a4ad1-152">**Request**</span></span>

<span data-ttu-id="a4ad1-153">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="a4ad1-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
