---
title: 隔離電腦 API
description: 瞭解如何使用隔離機器 API，隔離裝置，使其無法存取 Microsoft Defender for Endpoint 中的外部網路。
keywords: api，graph api，支援的 api，隔離裝置
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187827"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="14aad-104">隔離電腦 API</span><span class="sxs-lookup"><span data-stu-id="14aad-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="14aad-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="14aad-105">**Applies to:**</span></span>
- [<span data-ttu-id="14aad-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="14aad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="14aad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14aad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="14aad-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="14aad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="14aad-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="14aad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="14aad-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="14aad-110">API description</span></span>
<span data-ttu-id="14aad-111">隔離裝置以存取外部網路。</span><span class="sxs-lookup"><span data-stu-id="14aad-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="14aad-112">限制</span><span class="sxs-lookup"><span data-stu-id="14aad-112">Limitations</span></span>
1. <span data-ttu-id="14aad-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="14aad-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="14aad-114">權限</span><span class="sxs-lookup"><span data-stu-id="14aad-114">Permissions</span></span>
<span data-ttu-id="14aad-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="14aad-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="14aad-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="14aad-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="14aad-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="14aad-117">Permission type</span></span> |   <span data-ttu-id="14aad-118">權限</span><span class="sxs-lookup"><span data-stu-id="14aad-118">Permission</span></span>  |   <span data-ttu-id="14aad-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="14aad-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="14aad-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="14aad-120">Application</span></span> |   <span data-ttu-id="14aad-121">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="14aad-121">Machine.Isolate</span></span> |   <span data-ttu-id="14aad-122">「隔離電腦」</span><span class="sxs-lookup"><span data-stu-id="14aad-122">'Isolate machine'</span></span>
<span data-ttu-id="14aad-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="14aad-123">Delegated (work or school account)</span></span> | <span data-ttu-id="14aad-124">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="14aad-124">Machine.Isolate</span></span> |  <span data-ttu-id="14aad-125">「隔離電腦」</span><span class="sxs-lookup"><span data-stu-id="14aad-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="14aad-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="14aad-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="14aad-127">使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="14aad-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="14aad-128">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="14aad-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="14aad-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="14aad-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="14aad-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="14aad-130">Request headers</span></span>

<span data-ttu-id="14aad-131">名稱</span><span class="sxs-lookup"><span data-stu-id="14aad-131">Name</span></span> | <span data-ttu-id="14aad-132">類型</span><span class="sxs-lookup"><span data-stu-id="14aad-132">Type</span></span> | <span data-ttu-id="14aad-133">描述</span><span class="sxs-lookup"><span data-stu-id="14aad-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="14aad-134">授權</span><span class="sxs-lookup"><span data-stu-id="14aad-134">Authorization</span></span> | <span data-ttu-id="14aad-135">字串</span><span class="sxs-lookup"><span data-stu-id="14aad-135">String</span></span> | <span data-ttu-id="14aad-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="14aad-136">Bearer {token}.</span></span> <span data-ttu-id="14aad-137">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="14aad-137">**Required**.</span></span>
<span data-ttu-id="14aad-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="14aad-138">Content-Type</span></span> | <span data-ttu-id="14aad-139">string</span><span class="sxs-lookup"><span data-stu-id="14aad-139">string</span></span> | <span data-ttu-id="14aad-140">application/json。</span><span class="sxs-lookup"><span data-stu-id="14aad-140">application/json.</span></span> <span data-ttu-id="14aad-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="14aad-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="14aad-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="14aad-142">Request body</span></span>
<span data-ttu-id="14aad-143">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="14aad-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="14aad-144">參數</span><span class="sxs-lookup"><span data-stu-id="14aad-144">Parameter</span></span> | <span data-ttu-id="14aad-145">類型</span><span class="sxs-lookup"><span data-stu-id="14aad-145">Type</span></span>    | <span data-ttu-id="14aad-146">描述</span><span class="sxs-lookup"><span data-stu-id="14aad-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="14aad-147">留言</span><span class="sxs-lookup"><span data-stu-id="14aad-147">Comment</span></span> |   <span data-ttu-id="14aad-148">字串</span><span class="sxs-lookup"><span data-stu-id="14aad-148">String</span></span> |    <span data-ttu-id="14aad-149">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="14aad-149">Comment to associate with the action.</span></span> <span data-ttu-id="14aad-150">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="14aad-150">**Required**.</span></span>
<span data-ttu-id="14aad-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="14aad-151">IsolationType</span></span>   | <span data-ttu-id="14aad-152">字串</span><span class="sxs-lookup"><span data-stu-id="14aad-152">String</span></span> |  <span data-ttu-id="14aad-153">隔離類型。</span><span class="sxs-lookup"><span data-stu-id="14aad-153">Type of the isolation.</span></span> <span data-ttu-id="14aad-154">允許的值為： "Full" 或 "選擇性"。</span><span class="sxs-lookup"><span data-stu-id="14aad-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="14aad-155">**IsolationType** 控制要執行的隔離類型，可以是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="14aad-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="14aad-156">完整-完全隔離</span><span class="sxs-lookup"><span data-stu-id="14aad-156">Full – Full isolation</span></span>
- <span data-ttu-id="14aad-157">選擇性–只限制有限的應用程式存取網路 (請參閱 [隔離裝置的網路](respond-machine-alerts.md#isolate-devices-from-the-network) 以取得詳細資料) </span><span class="sxs-lookup"><span data-stu-id="14aad-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="14aad-158">回應</span><span class="sxs-lookup"><span data-stu-id="14aad-158">Response</span></span>
<span data-ttu-id="14aad-159">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="14aad-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="14aad-160">範例</span><span class="sxs-lookup"><span data-stu-id="14aad-160">Example</span></span>

<span data-ttu-id="14aad-161">**請求**</span><span class="sxs-lookup"><span data-stu-id="14aad-161">**Request**</span></span>

<span data-ttu-id="14aad-162">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="14aad-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="14aad-163">若要從隔離釋放裝置，請參閱 [從隔離裝置發行裝置](unisolate-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="14aad-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
