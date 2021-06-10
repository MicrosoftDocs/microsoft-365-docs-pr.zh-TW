---
title: 取得網域相關的電腦 API
description: 瞭解如何使用「取得網域相關的電腦 API」，以取得與 Microsoft Defender for Endpoint 中的網域通訊的電腦。
keywords: api、graph api、支援的 api、get、domain、相關的裝置
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772218"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="3e1e4-104">取得網域相關的電腦 API</span><span class="sxs-lookup"><span data-stu-id="3e1e4-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3e1e4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3e1e4-105">**Applies to:**</span></span>
- [<span data-ttu-id="3e1e4-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3e1e4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3e1e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e1e4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3e1e4-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="3e1e4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3e1e4-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3e1e4-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="3e1e4-110">API description</span></span>
<span data-ttu-id="3e1e4-111">檢索已傳送至或來自特定網域位址的 [電腦](machine.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="3e1e4-112">限制</span><span class="sxs-lookup"><span data-stu-id="3e1e4-112">Limitations</span></span>
1. <span data-ttu-id="3e1e4-113">您可以根據您設定的保留期間，查詢上次更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3e1e4-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3e1e4-115">權限</span><span class="sxs-lookup"><span data-stu-id="3e1e4-115">Permissions</span></span>
<span data-ttu-id="3e1e4-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3e1e4-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3e1e4-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3e1e4-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3e1e4-118">Permission type</span></span> |   <span data-ttu-id="3e1e4-119">權限</span><span class="sxs-lookup"><span data-stu-id="3e1e4-119">Permission</span></span>  |   <span data-ttu-id="3e1e4-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3e1e4-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3e1e4-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="3e1e4-121">Application</span></span> |   <span data-ttu-id="3e1e4-122">Read。所有</span><span class="sxs-lookup"><span data-stu-id="3e1e4-122">Machine.Read.All</span></span> |  <span data-ttu-id="3e1e4-123">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="3e1e4-123">'Read all machine profiles'</span></span>
<span data-ttu-id="3e1e4-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="3e1e4-124">Application</span></span> |   <span data-ttu-id="3e1e4-125">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="3e1e4-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="3e1e4-126">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="3e1e4-126">'Read and write all machine information'</span></span>
<span data-ttu-id="3e1e4-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3e1e4-127">Delegated (work or school account)</span></span> | <span data-ttu-id="3e1e4-128">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="3e1e4-128">Machine.Read</span></span> | <span data-ttu-id="3e1e4-129">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="3e1e4-129">'Read machine information'</span></span>
<span data-ttu-id="3e1e4-130">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3e1e4-130">Delegated (work or school account)</span></span> | <span data-ttu-id="3e1e4-131">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3e1e4-131">Machine.ReadWrite</span></span> | <span data-ttu-id="3e1e4-132">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="3e1e4-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="3e1e4-133">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="3e1e4-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3e1e4-134">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="3e1e4-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3e1e4-135">回應僅包含使用者可以存取的裝置，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="3e1e4-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3e1e4-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3e1e4-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="3e1e4-137">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3e1e4-137">Request headers</span></span>

<span data-ttu-id="3e1e4-138">名稱</span><span class="sxs-lookup"><span data-stu-id="3e1e4-138">Name</span></span> | <span data-ttu-id="3e1e4-139">類型</span><span class="sxs-lookup"><span data-stu-id="3e1e4-139">Type</span></span> | <span data-ttu-id="3e1e4-140">描述</span><span class="sxs-lookup"><span data-stu-id="3e1e4-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="3e1e4-141">授權</span><span class="sxs-lookup"><span data-stu-id="3e1e4-141">Authorization</span></span> | <span data-ttu-id="3e1e4-142">字串</span><span class="sxs-lookup"><span data-stu-id="3e1e4-142">String</span></span> | <span data-ttu-id="3e1e4-143">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-143">Bearer {token}.</span></span> <span data-ttu-id="3e1e4-144">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3e1e4-145">要求正文</span><span class="sxs-lookup"><span data-stu-id="3e1e4-145">Request body</span></span>
<span data-ttu-id="3e1e4-146">空白</span><span class="sxs-lookup"><span data-stu-id="3e1e4-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3e1e4-147">回應</span><span class="sxs-lookup"><span data-stu-id="3e1e4-147">Response</span></span>
<span data-ttu-id="3e1e4-148">如果成功且網域存在，則為 [電腦](machine.md) 實體清單的 200 OK。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="3e1e4-149">如果網域不存在-找不到404。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3e1e4-150">範例</span><span class="sxs-lookup"><span data-stu-id="3e1e4-150">Example</span></span>

<span data-ttu-id="3e1e4-151">**請求**</span><span class="sxs-lookup"><span data-stu-id="3e1e4-151">**Request**</span></span>

<span data-ttu-id="3e1e4-152">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3e1e4-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
