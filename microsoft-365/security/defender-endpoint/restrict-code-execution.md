---
title: 限制應用程式執行 API
description: 使用此 API 來建立與限制應用程式執行相關的呼叫。
keywords: api、graph api、支援的 api、收集調查套件
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
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186773"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="2d83f-104">限制應用程式執行 API</span><span class="sxs-lookup"><span data-stu-id="2d83f-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d83f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2d83f-105">**Applies to:**</span></span>
- [<span data-ttu-id="2d83f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2d83f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2d83f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d83f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="2d83f-108">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2d83f-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2d83f-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2d83f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2d83f-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2d83f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2d83f-111">API 描述</span><span class="sxs-lookup"><span data-stu-id="2d83f-111">API description</span></span>
<span data-ttu-id="2d83f-112">限制裝置上除預先定義的集合以外的所有應用程式的執行。</span><span class="sxs-lookup"><span data-stu-id="2d83f-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="2d83f-113">限制</span><span class="sxs-lookup"><span data-stu-id="2d83f-113">Limitations</span></span>
1. <span data-ttu-id="2d83f-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="2d83f-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="2d83f-115">權限</span><span class="sxs-lookup"><span data-stu-id="2d83f-115">Permissions</span></span>
<span data-ttu-id="2d83f-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="2d83f-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2d83f-117">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2d83f-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2d83f-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="2d83f-118">Permission type</span></span> |   <span data-ttu-id="2d83f-119">權限</span><span class="sxs-lookup"><span data-stu-id="2d83f-119">Permission</span></span>  |   <span data-ttu-id="2d83f-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="2d83f-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2d83f-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="2d83f-121">Application</span></span> |   <span data-ttu-id="2d83f-122">RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="2d83f-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="2d83f-123">「限制程式碼執行」</span><span class="sxs-lookup"><span data-stu-id="2d83f-123">'Restrict code execution'</span></span>
<span data-ttu-id="2d83f-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="2d83f-124">Delegated (work or school account)</span></span> | <span data-ttu-id="2d83f-125">RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="2d83f-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="2d83f-126">「限制程式碼執行」</span><span class="sxs-lookup"><span data-stu-id="2d83f-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="2d83f-127">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="2d83f-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2d83f-128">使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="2d83f-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2d83f-129">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="2d83f-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2d83f-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="2d83f-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="2d83f-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="2d83f-131">Request headers</span></span>

<span data-ttu-id="2d83f-132">名稱</span><span class="sxs-lookup"><span data-stu-id="2d83f-132">Name</span></span> | <span data-ttu-id="2d83f-133">類型</span><span class="sxs-lookup"><span data-stu-id="2d83f-133">Type</span></span> | <span data-ttu-id="2d83f-134">描述</span><span class="sxs-lookup"><span data-stu-id="2d83f-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d83f-135">授權</span><span class="sxs-lookup"><span data-stu-id="2d83f-135">Authorization</span></span> | <span data-ttu-id="2d83f-136">字串</span><span class="sxs-lookup"><span data-stu-id="2d83f-136">String</span></span> | <span data-ttu-id="2d83f-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="2d83f-137">Bearer {token}.</span></span> <span data-ttu-id="2d83f-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="2d83f-138">**Required**.</span></span>
<span data-ttu-id="2d83f-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="2d83f-139">Content-Type</span></span> | <span data-ttu-id="2d83f-140">string</span><span class="sxs-lookup"><span data-stu-id="2d83f-140">string</span></span> | <span data-ttu-id="2d83f-141">application/json。</span><span class="sxs-lookup"><span data-stu-id="2d83f-141">application/json.</span></span> <span data-ttu-id="2d83f-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="2d83f-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2d83f-143">要求正文</span><span class="sxs-lookup"><span data-stu-id="2d83f-143">Request body</span></span>
<span data-ttu-id="2d83f-144">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="2d83f-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="2d83f-145">參數</span><span class="sxs-lookup"><span data-stu-id="2d83f-145">Parameter</span></span> | <span data-ttu-id="2d83f-146">類型</span><span class="sxs-lookup"><span data-stu-id="2d83f-146">Type</span></span>    | <span data-ttu-id="2d83f-147">描述</span><span class="sxs-lookup"><span data-stu-id="2d83f-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="2d83f-148">留言</span><span class="sxs-lookup"><span data-stu-id="2d83f-148">Comment</span></span> |   <span data-ttu-id="2d83f-149">字串</span><span class="sxs-lookup"><span data-stu-id="2d83f-149">String</span></span> |    <span data-ttu-id="2d83f-150">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="2d83f-150">Comment to associate with the action.</span></span> <span data-ttu-id="2d83f-151">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="2d83f-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="2d83f-152">回應</span><span class="sxs-lookup"><span data-stu-id="2d83f-152">Response</span></span>
<span data-ttu-id="2d83f-153">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="2d83f-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="2d83f-154">範例</span><span class="sxs-lookup"><span data-stu-id="2d83f-154">Example</span></span>

<span data-ttu-id="2d83f-155">**請求**</span><span class="sxs-lookup"><span data-stu-id="2d83f-155">**Request**</span></span>

<span data-ttu-id="2d83f-156">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="2d83f-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="2d83f-157">若要移除裝置的程式碼執行限制，請參閱 [移除應用程式限制](unrestrict-code-execution.md)。</span><span class="sxs-lookup"><span data-stu-id="2d83f-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>