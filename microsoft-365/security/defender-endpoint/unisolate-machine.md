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
ms.technology: mde
ms.openlocfilehash: 036eb6f589c13fb9232557c45619829149179148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199330"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="cc021-104">從隔離 API 發行裝置</span><span class="sxs-lookup"><span data-stu-id="cc021-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc021-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cc021-105">**Applies to:**</span></span> 
- [<span data-ttu-id="cc021-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cc021-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cc021-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc021-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="cc021-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="cc021-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc021-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="cc021-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cc021-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="cc021-110">API description</span></span>
<span data-ttu-id="cc021-111">復原裝置的隔離。</span><span class="sxs-lookup"><span data-stu-id="cc021-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="cc021-112">限制</span><span class="sxs-lookup"><span data-stu-id="cc021-112">Limitations</span></span>
1. <span data-ttu-id="cc021-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="cc021-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="cc021-114">權限</span><span class="sxs-lookup"><span data-stu-id="cc021-114">Permissions</span></span>
<span data-ttu-id="cc021-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="cc021-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cc021-116">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cc021-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cc021-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="cc021-117">Permission type</span></span> |   <span data-ttu-id="cc021-118">權限</span><span class="sxs-lookup"><span data-stu-id="cc021-118">Permission</span></span>  |   <span data-ttu-id="cc021-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="cc021-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cc021-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="cc021-120">Application</span></span> |   <span data-ttu-id="cc021-121">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="cc021-121">Machine.Isolate</span></span> |   <span data-ttu-id="cc021-122">「隔離電腦」</span><span class="sxs-lookup"><span data-stu-id="cc021-122">'Isolate machine'</span></span>
<span data-ttu-id="cc021-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="cc021-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="cc021-124">電腦隔離</span><span class="sxs-lookup"><span data-stu-id="cc021-124">Machine.Isolate</span></span> |   <span data-ttu-id="cc021-125">「隔離電腦」</span><span class="sxs-lookup"><span data-stu-id="cc021-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="cc021-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="cc021-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cc021-127">使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="cc021-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cc021-128">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="cc021-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cc021-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="cc021-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="cc021-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="cc021-130">Request headers</span></span>

<span data-ttu-id="cc021-131">名稱</span><span class="sxs-lookup"><span data-stu-id="cc021-131">Name</span></span> | <span data-ttu-id="cc021-132">類型</span><span class="sxs-lookup"><span data-stu-id="cc021-132">Type</span></span> | <span data-ttu-id="cc021-133">描述</span><span class="sxs-lookup"><span data-stu-id="cc021-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="cc021-134">授權</span><span class="sxs-lookup"><span data-stu-id="cc021-134">Authorization</span></span> | <span data-ttu-id="cc021-135">字串</span><span class="sxs-lookup"><span data-stu-id="cc021-135">String</span></span> | <span data-ttu-id="cc021-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="cc021-136">Bearer {token}.</span></span> <span data-ttu-id="cc021-137">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="cc021-137">**Required**.</span></span>
<span data-ttu-id="cc021-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cc021-138">Content-Type</span></span> | <span data-ttu-id="cc021-139">string</span><span class="sxs-lookup"><span data-stu-id="cc021-139">string</span></span> | <span data-ttu-id="cc021-140">application/json。</span><span class="sxs-lookup"><span data-stu-id="cc021-140">application/json.</span></span> <span data-ttu-id="cc021-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="cc021-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cc021-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="cc021-142">Request body</span></span>
<span data-ttu-id="cc021-143">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="cc021-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="cc021-144">參數</span><span class="sxs-lookup"><span data-stu-id="cc021-144">Parameter</span></span> | <span data-ttu-id="cc021-145">類型</span><span class="sxs-lookup"><span data-stu-id="cc021-145">Type</span></span>    | <span data-ttu-id="cc021-146">描述</span><span class="sxs-lookup"><span data-stu-id="cc021-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="cc021-147">留言</span><span class="sxs-lookup"><span data-stu-id="cc021-147">Comment</span></span> |   <span data-ttu-id="cc021-148">字串</span><span class="sxs-lookup"><span data-stu-id="cc021-148">String</span></span> |    <span data-ttu-id="cc021-149">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="cc021-149">Comment to associate with the action.</span></span> <span data-ttu-id="cc021-150">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="cc021-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="cc021-151">回應</span><span class="sxs-lookup"><span data-stu-id="cc021-151">Response</span></span>
<span data-ttu-id="cc021-152">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="cc021-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="cc021-153">範例</span><span class="sxs-lookup"><span data-stu-id="cc021-153">Example</span></span>

<span data-ttu-id="cc021-154">**請求**</span><span class="sxs-lookup"><span data-stu-id="cc021-154">**Request**</span></span>

<span data-ttu-id="cc021-155">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="cc021-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="cc021-156">若要隔離裝置，請參閱 [隔離裝置](isolate-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="cc021-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

