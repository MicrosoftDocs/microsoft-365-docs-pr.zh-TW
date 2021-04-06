---
title: 依識別碼取得警示資訊 API
description: 瞭解如何在 Microsoft Defender for Endpoint 中，使用 [依識別碼取得警示資訊] API 來透過其識別碼來取得特定警示。
keywords: api、graph api、支援的 api、get、警示、資訊、識別碼
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
ms.openlocfilehash: f9130b054ccea762e6c5cc4f2952bbfa82d24b83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200422"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="a7ea1-104">依識別碼取得警示資訊 API</span><span class="sxs-lookup"><span data-stu-id="a7ea1-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a7ea1-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a7ea1-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a7ea1-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a7ea1-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7ea1-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a7ea1-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="a7ea1-108">API description</span></span>
<span data-ttu-id="a7ea1-109">依識別碼來檢索特定 [警示](alerts.md) 。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="a7ea1-110">限制</span><span class="sxs-lookup"><span data-stu-id="a7ea1-110">Limitations</span></span>
1. <span data-ttu-id="a7ea1-111">您可以根據您設定的保留期間，取得最後更新的警示。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="a7ea1-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a7ea1-113">權限</span><span class="sxs-lookup"><span data-stu-id="a7ea1-113">Permissions</span></span>
<span data-ttu-id="a7ea1-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a7ea1-115">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a7ea1-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a7ea1-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="a7ea1-116">Permission type</span></span> |   <span data-ttu-id="a7ea1-117">權限</span><span class="sxs-lookup"><span data-stu-id="a7ea1-117">Permission</span></span>  |   <span data-ttu-id="a7ea1-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a7ea1-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a7ea1-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="a7ea1-119">Application</span></span> |   <span data-ttu-id="a7ea1-120">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="a7ea1-120">Alert.Read.All</span></span> |    <span data-ttu-id="a7ea1-121">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="a7ea1-121">'Read all alerts'</span></span>
<span data-ttu-id="a7ea1-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="a7ea1-122">Application</span></span> |   <span data-ttu-id="a7ea1-123">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="a7ea1-124">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="a7ea1-124">'Read and write all alerts'</span></span>
<span data-ttu-id="a7ea1-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a7ea1-125">Delegated (work or school account)</span></span> | <span data-ttu-id="a7ea1-126">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="a7ea1-126">Alert.Read</span></span> | <span data-ttu-id="a7ea1-127">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="a7ea1-127">'Read alerts'</span></span>
<span data-ttu-id="a7ea1-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a7ea1-128">Delegated (work or school account)</span></span> | <span data-ttu-id="a7ea1-129">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a7ea1-129">Alert.ReadWrite</span></span> | <span data-ttu-id="a7ea1-130">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="a7ea1-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="a7ea1-131">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="a7ea1-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a7ea1-132">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="a7ea1-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="a7ea1-133">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="a7ea1-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a7ea1-134">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a7ea1-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="a7ea1-135">要求標頭</span><span class="sxs-lookup"><span data-stu-id="a7ea1-135">Request headers</span></span>

<span data-ttu-id="a7ea1-136">名稱</span><span class="sxs-lookup"><span data-stu-id="a7ea1-136">Name</span></span> | <span data-ttu-id="a7ea1-137">類型</span><span class="sxs-lookup"><span data-stu-id="a7ea1-137">Type</span></span> | <span data-ttu-id="a7ea1-138">描述</span><span class="sxs-lookup"><span data-stu-id="a7ea1-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="a7ea1-139">授權</span><span class="sxs-lookup"><span data-stu-id="a7ea1-139">Authorization</span></span> | <span data-ttu-id="a7ea1-140">字串</span><span class="sxs-lookup"><span data-stu-id="a7ea1-140">String</span></span> | <span data-ttu-id="a7ea1-141">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-141">Bearer {token}.</span></span> <span data-ttu-id="a7ea1-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a7ea1-143">要求正文</span><span class="sxs-lookup"><span data-stu-id="a7ea1-143">Request body</span></span>
<span data-ttu-id="a7ea1-144">空白</span><span class="sxs-lookup"><span data-stu-id="a7ea1-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a7ea1-145">回應</span><span class="sxs-lookup"><span data-stu-id="a7ea1-145">Response</span></span>
<span data-ttu-id="a7ea1-146">如果成功，這個方法會傳回 200 OK 和 response body 中的 [警示](alerts.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="a7ea1-147">如果找不到具有指定識別碼的警示-找不到404。</span><span class="sxs-lookup"><span data-stu-id="a7ea1-147">If alert with the specified id was not found - 404 Not Found.</span></span>