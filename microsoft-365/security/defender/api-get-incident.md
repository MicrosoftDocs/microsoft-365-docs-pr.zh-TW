---
title: 取得事件 API
description: 瞭解如何使用取得事件 API，在 Microsoft 365 Defender 中取得單一事件。
keywords: api、graph api、支援的 api、get、file、hash
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
ms.openlocfilehash: c578a353501ac7b38ac541b0200ffaad1d6743e1
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888443"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="0c54e-104">取得事件資訊 API</span><span class="sxs-lookup"><span data-stu-id="0c54e-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c54e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0c54e-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c54e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c54e-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0c54e-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="0c54e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0c54e-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0c54e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0c54e-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="0c54e-109">API description</span></span>
<span data-ttu-id="0c54e-110">依識別碼來檢索特定事件</span><span class="sxs-lookup"><span data-stu-id="0c54e-110">Retrieves a specific incident by its ID</span></span>


## <a name="limitations"></a><span data-ttu-id="0c54e-111">限制</span><span class="sxs-lookup"><span data-stu-id="0c54e-111">Limitations</span></span>
1. <span data-ttu-id="0c54e-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="0c54e-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0c54e-113">權限</span><span class="sxs-lookup"><span data-stu-id="0c54e-113">Permissions</span></span>
<span data-ttu-id="0c54e-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="0c54e-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="0c54e-115">許可權類型</span><span class="sxs-lookup"><span data-stu-id="0c54e-115">Permission type</span></span> |   <span data-ttu-id="0c54e-116">權限</span><span class="sxs-lookup"><span data-stu-id="0c54e-116">Permission</span></span>  |   <span data-ttu-id="0c54e-117">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="0c54e-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0c54e-118">應用程式</span><span class="sxs-lookup"><span data-stu-id="0c54e-118">Application</span></span> |   <span data-ttu-id="0c54e-119">Incident。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="0c54e-119">Incident.Read.All</span></span> | <span data-ttu-id="0c54e-120">「讀取所有事件」</span><span class="sxs-lookup"><span data-stu-id="0c54e-120">'Read all Incidents'</span></span>
<span data-ttu-id="0c54e-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="0c54e-121">Application</span></span> |   <span data-ttu-id="0c54e-122">Incident。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="0c54e-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="0c54e-123">「讀取和寫入所有事件」</span><span class="sxs-lookup"><span data-stu-id="0c54e-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="0c54e-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="0c54e-124">Delegated (work or school account)</span></span> | <span data-ttu-id="0c54e-125">事件。讀取</span><span class="sxs-lookup"><span data-stu-id="0c54e-125">Incident.Read</span></span> | <span data-ttu-id="0c54e-126">「讀取事件」</span><span class="sxs-lookup"><span data-stu-id="0c54e-126">'Read Incidents'</span></span>
<span data-ttu-id="0c54e-127">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="0c54e-127">Delegated (work or school account)</span></span> | <span data-ttu-id="0c54e-128">Incident。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0c54e-128">Incident.ReadWrite</span></span> | <span data-ttu-id="0c54e-129">「讀取和寫入事件」</span><span class="sxs-lookup"><span data-stu-id="0c54e-129">'Read and write Incidents'</span></span>

>[!Note]
> <span data-ttu-id="0c54e-130">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="0c54e-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0c54e-131">使用者至少必須具備下列角色許可權：「View Data」</span><span class="sxs-lookup"><span data-stu-id="0c54e-131">The user needs to have at least the following role permission: 'View Data'</span></span>
>- <span data-ttu-id="0c54e-132">回應只會包含使用者所公開的事件</span><span class="sxs-lookup"><span data-stu-id="0c54e-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="0c54e-133">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="0c54e-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="0c54e-134">要求標頭</span><span class="sxs-lookup"><span data-stu-id="0c54e-134">Request headers</span></span>

<span data-ttu-id="0c54e-135">名稱</span><span class="sxs-lookup"><span data-stu-id="0c54e-135">Name</span></span> | <span data-ttu-id="0c54e-136">類型</span><span class="sxs-lookup"><span data-stu-id="0c54e-136">Type</span></span> | <span data-ttu-id="0c54e-137">描述</span><span class="sxs-lookup"><span data-stu-id="0c54e-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="0c54e-138">授權</span><span class="sxs-lookup"><span data-stu-id="0c54e-138">Authorization</span></span> | <span data-ttu-id="0c54e-139">字串</span><span class="sxs-lookup"><span data-stu-id="0c54e-139">String</span></span> | <span data-ttu-id="0c54e-140">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="0c54e-140">Bearer {token}.</span></span> <span data-ttu-id="0c54e-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="0c54e-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0c54e-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="0c54e-142">Request body</span></span>
<span data-ttu-id="0c54e-143">空白</span><span class="sxs-lookup"><span data-stu-id="0c54e-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0c54e-144">回應</span><span class="sxs-lookup"><span data-stu-id="0c54e-144">Response</span></span>

<span data-ttu-id="0c54e-145">如果成功，這個方法會傳回 200 OK，以及回應內文中的事件實體。</span><span class="sxs-lookup"><span data-stu-id="0c54e-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="0c54e-146">如果找不到具有指定識別碼的事件-找不到404。</span><span class="sxs-lookup"><span data-stu-id="0c54e-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="0c54e-147">範例</span><span class="sxs-lookup"><span data-stu-id="0c54e-147">Example</span></span>

<span data-ttu-id="0c54e-148">**請求**</span><span class="sxs-lookup"><span data-stu-id="0c54e-148">**Request**</span></span>

<span data-ttu-id="0c54e-149">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="0c54e-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
