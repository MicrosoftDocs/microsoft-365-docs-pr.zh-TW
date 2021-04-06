---
title: 取得調查物件 API
description: 使用此 API 來建立與取得調查物件相關的呼叫
keywords: api，graph api，支援的 api，調查物件
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
ms.openlocfilehash: 9f011f10a9fe3c3aec535e157abee2367998b1a4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166384"
---
# <a name="get-investigation-api"></a><span data-ttu-id="cb70a-104">取得調查 API</span><span class="sxs-lookup"><span data-stu-id="cb70a-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cb70a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cb70a-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb70a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cb70a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb70a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb70a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cb70a-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="cb70a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb70a-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="cb70a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cb70a-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="cb70a-110">API description</span></span>
<span data-ttu-id="cb70a-111">依識別碼來檢索特定 [調查](investigation.md) 。</span><span class="sxs-lookup"><span data-stu-id="cb70a-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="cb70a-112">識別碼可以是調查識別碼或觸發警示識別碼的調查。</span><span class="sxs-lookup"><span data-stu-id="cb70a-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="cb70a-113">限制</span><span class="sxs-lookup"><span data-stu-id="cb70a-113">Limitations</span></span>
1. <span data-ttu-id="cb70a-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="cb70a-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="cb70a-115">權限</span><span class="sxs-lookup"><span data-stu-id="cb70a-115">Permissions</span></span>
<span data-ttu-id="cb70a-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="cb70a-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cb70a-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cb70a-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cb70a-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="cb70a-118">Permission type</span></span> |   <span data-ttu-id="cb70a-119">權限</span><span class="sxs-lookup"><span data-stu-id="cb70a-119">Permission</span></span>  |   <span data-ttu-id="cb70a-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="cb70a-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cb70a-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="cb70a-121">Application</span></span> |   <span data-ttu-id="cb70a-122">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="cb70a-122">Alert.Read.All</span></span> |    <span data-ttu-id="cb70a-123">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="cb70a-123">'Read all alerts'</span></span>
<span data-ttu-id="cb70a-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="cb70a-124">Application</span></span> |   <span data-ttu-id="cb70a-125">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="cb70a-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="cb70a-126">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="cb70a-126">'Read and write all alerts'</span></span>
<span data-ttu-id="cb70a-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="cb70a-127">Delegated (work or school account)</span></span> | <span data-ttu-id="cb70a-128">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="cb70a-128">Alert.Read</span></span> | <span data-ttu-id="cb70a-129">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="cb70a-129">'Read alerts'</span></span>
<span data-ttu-id="cb70a-130">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="cb70a-130">Delegated (work or school account)</span></span> | <span data-ttu-id="cb70a-131">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cb70a-131">Alert.ReadWrite</span></span> | <span data-ttu-id="cb70a-132">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="cb70a-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="cb70a-133">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="cb70a-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cb70a-134">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="cb70a-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cb70a-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="cb70a-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="cb70a-136">要求標頭</span><span class="sxs-lookup"><span data-stu-id="cb70a-136">Request headers</span></span>

<span data-ttu-id="cb70a-137">名稱</span><span class="sxs-lookup"><span data-stu-id="cb70a-137">Name</span></span> | <span data-ttu-id="cb70a-138">類型</span><span class="sxs-lookup"><span data-stu-id="cb70a-138">Type</span></span> | <span data-ttu-id="cb70a-139">描述</span><span class="sxs-lookup"><span data-stu-id="cb70a-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="cb70a-140">授權</span><span class="sxs-lookup"><span data-stu-id="cb70a-140">Authorization</span></span> | <span data-ttu-id="cb70a-141">字串</span><span class="sxs-lookup"><span data-stu-id="cb70a-141">String</span></span> | <span data-ttu-id="cb70a-142">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="cb70a-142">Bearer {token}.</span></span> <span data-ttu-id="cb70a-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="cb70a-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cb70a-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="cb70a-144">Request body</span></span>
<span data-ttu-id="cb70a-145">空白</span><span class="sxs-lookup"><span data-stu-id="cb70a-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cb70a-146">回應</span><span class="sxs-lookup"><span data-stu-id="cb70a-146">Response</span></span>
<span data-ttu-id="cb70a-147">若成功，這個方法會傳回200，具有 [調查](investigation.md) 實體的 Ok 回應碼。</span><span class="sxs-lookup"><span data-stu-id="cb70a-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>
