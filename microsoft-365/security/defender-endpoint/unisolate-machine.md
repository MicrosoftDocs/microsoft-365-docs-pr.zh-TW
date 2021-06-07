---
title: 從隔離 API 發行裝置
description: 使用此 API 來建立與從隔離釋放裝置相關的呼叫。
keywords: api，graph api，支援的 api，從隔離中移除裝置
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
ms.openlocfilehash: 3ed2e7968464320e41e47ad734026bdd9b323ceb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771270"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="376ea-104">從隔離 API 發行裝置</span><span class="sxs-lookup"><span data-stu-id="376ea-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="376ea-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="376ea-105">**Applies to:**</span></span> 
- [<span data-ttu-id="376ea-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="376ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="376ea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="376ea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="376ea-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="376ea-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="376ea-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="376ea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="376ea-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="376ea-110">API description</span></span>
<span data-ttu-id="376ea-111">復原裝置的隔離。</span><span class="sxs-lookup"><span data-stu-id="376ea-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="376ea-112">限制</span><span class="sxs-lookup"><span data-stu-id="376ea-112">Limitations</span></span>
1. <span data-ttu-id="376ea-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="376ea-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="376ea-114">權限</span><span class="sxs-lookup"><span data-stu-id="376ea-114">Permissions</span></span>
<span data-ttu-id="376ea-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="376ea-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="376ea-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="376ea-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="376ea-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="376ea-117">Permission type</span></span> |   <span data-ttu-id="376ea-118">權限</span><span class="sxs-lookup"><span data-stu-id="376ea-118">Permission</span></span>  |   <span data-ttu-id="376ea-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="376ea-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="376ea-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="376ea-120">Application</span></span> |   <span data-ttu-id="376ea-121">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="376ea-121">Machine.Isolate</span></span> |   <span data-ttu-id="376ea-122">「隔離電腦」</span><span class="sxs-lookup"><span data-stu-id="376ea-122">'Isolate machine'</span></span>
<span data-ttu-id="376ea-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="376ea-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="376ea-124">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="376ea-124">Machine.Isolate</span></span> |   <span data-ttu-id="376ea-125">「隔離電腦」</span><span class="sxs-lookup"><span data-stu-id="376ea-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="376ea-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="376ea-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="376ea-127">使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="376ea-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="376ea-128">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="376ea-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="376ea-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="376ea-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="376ea-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="376ea-130">Request headers</span></span>

<span data-ttu-id="376ea-131">名稱</span><span class="sxs-lookup"><span data-stu-id="376ea-131">Name</span></span> | <span data-ttu-id="376ea-132">類型</span><span class="sxs-lookup"><span data-stu-id="376ea-132">Type</span></span> | <span data-ttu-id="376ea-133">描述</span><span class="sxs-lookup"><span data-stu-id="376ea-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="376ea-134">授權</span><span class="sxs-lookup"><span data-stu-id="376ea-134">Authorization</span></span> | <span data-ttu-id="376ea-135">字串</span><span class="sxs-lookup"><span data-stu-id="376ea-135">String</span></span> | <span data-ttu-id="376ea-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="376ea-136">Bearer {token}.</span></span> <span data-ttu-id="376ea-137">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="376ea-137">**Required**.</span></span>
<span data-ttu-id="376ea-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="376ea-138">Content-Type</span></span> | <span data-ttu-id="376ea-139">string</span><span class="sxs-lookup"><span data-stu-id="376ea-139">string</span></span> | <span data-ttu-id="376ea-140">application/json。</span><span class="sxs-lookup"><span data-stu-id="376ea-140">application/json.</span></span> <span data-ttu-id="376ea-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="376ea-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="376ea-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="376ea-142">Request body</span></span>
<span data-ttu-id="376ea-143">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="376ea-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="376ea-144">參數</span><span class="sxs-lookup"><span data-stu-id="376ea-144">Parameter</span></span> | <span data-ttu-id="376ea-145">類型</span><span class="sxs-lookup"><span data-stu-id="376ea-145">Type</span></span>    | <span data-ttu-id="376ea-146">描述</span><span class="sxs-lookup"><span data-stu-id="376ea-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="376ea-147">留言</span><span class="sxs-lookup"><span data-stu-id="376ea-147">Comment</span></span> |   <span data-ttu-id="376ea-148">字串</span><span class="sxs-lookup"><span data-stu-id="376ea-148">String</span></span> |    <span data-ttu-id="376ea-149">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="376ea-149">Comment to associate with the action.</span></span> <span data-ttu-id="376ea-150">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="376ea-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="376ea-151">回應</span><span class="sxs-lookup"><span data-stu-id="376ea-151">Response</span></span>
<span data-ttu-id="376ea-152">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="376ea-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="376ea-153">範例</span><span class="sxs-lookup"><span data-stu-id="376ea-153">Example</span></span>

<span data-ttu-id="376ea-154">**請求**</span><span class="sxs-lookup"><span data-stu-id="376ea-154">**Request**</span></span>

<span data-ttu-id="376ea-155">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="376ea-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="376ea-156">若要隔離裝置，請參閱 [隔離裝置](isolate-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="376ea-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

