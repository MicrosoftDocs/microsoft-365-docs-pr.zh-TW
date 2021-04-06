---
title: 取得機器相關的警示 API
description: 瞭解如何使用「取得機器相關的警示 API」，以在 Microsoft Defender for Endpoint 中檢索與特定裝置相關的所有警示。
keywords: api、graph api、支援的 api、get、裝置、相關的警示
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199248"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="ca75e-104">取得機器相關的警示 API</span><span class="sxs-lookup"><span data-stu-id="ca75e-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca75e-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ca75e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ca75e-106">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ca75e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca75e-107">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ca75e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ca75e-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="ca75e-108">API description</span></span>
<span data-ttu-id="ca75e-109">會檢索與特定裝置相關的所有 [警示](alerts.md) 。</span><span class="sxs-lookup"><span data-stu-id="ca75e-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="ca75e-110">限制</span><span class="sxs-lookup"><span data-stu-id="ca75e-110">Limitations</span></span>
1. <span data-ttu-id="ca75e-111">您可以根據您設定的保留期間，查詢上次更新的裝置。</span><span class="sxs-lookup"><span data-stu-id="ca75e-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="ca75e-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="ca75e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="ca75e-113">許可權類型</span><span class="sxs-lookup"><span data-stu-id="ca75e-113">Permission type</span></span> |   <span data-ttu-id="ca75e-114">權限</span><span class="sxs-lookup"><span data-stu-id="ca75e-114">Permission</span></span>  |   <span data-ttu-id="ca75e-115">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="ca75e-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ca75e-116">應用程式</span><span class="sxs-lookup"><span data-stu-id="ca75e-116">Application</span></span> |   <span data-ttu-id="ca75e-117">警示。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="ca75e-117">Alert.Read.All</span></span> |    <span data-ttu-id="ca75e-118">「讀取所有警示」</span><span class="sxs-lookup"><span data-stu-id="ca75e-118">'Read all alerts'</span></span>
<span data-ttu-id="ca75e-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="ca75e-119">Application</span></span> |   <span data-ttu-id="ca75e-120">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="ca75e-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="ca75e-121">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="ca75e-121">'Read and write all alerts'</span></span>
<span data-ttu-id="ca75e-122">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="ca75e-122">Delegated (work or school account)</span></span> | <span data-ttu-id="ca75e-123">警示。讀取</span><span class="sxs-lookup"><span data-stu-id="ca75e-123">Alert.Read</span></span> | <span data-ttu-id="ca75e-124">「讀取警示」</span><span class="sxs-lookup"><span data-stu-id="ca75e-124">'Read alerts'</span></span>
<span data-ttu-id="ca75e-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="ca75e-125">Delegated (work or school account)</span></span> | <span data-ttu-id="ca75e-126">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ca75e-126">Alert.ReadWrite</span></span> | <span data-ttu-id="ca75e-127">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="ca75e-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="ca75e-128">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="ca75e-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ca75e-129">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="ca75e-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="ca75e-130">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="ca75e-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ca75e-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ca75e-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="ca75e-132">要求標頭</span><span class="sxs-lookup"><span data-stu-id="ca75e-132">Request headers</span></span>

<span data-ttu-id="ca75e-133">名稱</span><span class="sxs-lookup"><span data-stu-id="ca75e-133">Name</span></span> | <span data-ttu-id="ca75e-134">類型</span><span class="sxs-lookup"><span data-stu-id="ca75e-134">Type</span></span> | <span data-ttu-id="ca75e-135">描述</span><span class="sxs-lookup"><span data-stu-id="ca75e-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="ca75e-136">授權</span><span class="sxs-lookup"><span data-stu-id="ca75e-136">Authorization</span></span> | <span data-ttu-id="ca75e-137">字串</span><span class="sxs-lookup"><span data-stu-id="ca75e-137">String</span></span> | <span data-ttu-id="ca75e-138">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="ca75e-138">Bearer {token}.</span></span> <span data-ttu-id="ca75e-139">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="ca75e-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ca75e-140">要求正文</span><span class="sxs-lookup"><span data-stu-id="ca75e-140">Request body</span></span>
<span data-ttu-id="ca75e-141">空白</span><span class="sxs-lookup"><span data-stu-id="ca75e-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ca75e-142">回應</span><span class="sxs-lookup"><span data-stu-id="ca75e-142">Response</span></span>
<span data-ttu-id="ca75e-143">如果成功和裝置存在-200 OK （含）內文中的 [警示](alerts.md) 實體清單。</span><span class="sxs-lookup"><span data-stu-id="ca75e-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="ca75e-144">如果找不到裝置-找不到404。</span><span class="sxs-lookup"><span data-stu-id="ca75e-144">If device was not found - 404 Not Found.</span></span>