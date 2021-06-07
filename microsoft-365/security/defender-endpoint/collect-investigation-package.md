---
title: 收集調查套件 API
description: 使用此 API 來建立與從裝置收集調查套件相關的呼叫。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0083d806f3e52307e6dce30f74e255073a09c16a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770490"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="888fa-104">收集調查套件 API</span><span class="sxs-lookup"><span data-stu-id="888fa-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="888fa-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="888fa-105">**Applies to:**</span></span>
- [<span data-ttu-id="888fa-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="888fa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="888fa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="888fa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="888fa-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="888fa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="888fa-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="888fa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="888fa-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="888fa-110">API description</span></span>
<span data-ttu-id="888fa-111">從裝置收集調查套件。</span><span class="sxs-lookup"><span data-stu-id="888fa-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="888fa-112">限制</span><span class="sxs-lookup"><span data-stu-id="888fa-112">Limitations</span></span>
1. <span data-ttu-id="888fa-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="888fa-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="888fa-114">權限</span><span class="sxs-lookup"><span data-stu-id="888fa-114">Permissions</span></span>
<span data-ttu-id="888fa-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="888fa-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="888fa-116">若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="888fa-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="888fa-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="888fa-117">Permission type</span></span> |   <span data-ttu-id="888fa-118">權限</span><span class="sxs-lookup"><span data-stu-id="888fa-118">Permission</span></span>  |   <span data-ttu-id="888fa-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="888fa-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="888fa-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="888fa-120">Application</span></span> |   <span data-ttu-id="888fa-121">CollectForensics</span><span class="sxs-lookup"><span data-stu-id="888fa-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="888fa-122">「收集辯論」</span><span class="sxs-lookup"><span data-stu-id="888fa-122">'Collect forensics'</span></span>
<span data-ttu-id="888fa-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="888fa-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="888fa-124">CollectForensics</span><span class="sxs-lookup"><span data-stu-id="888fa-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="888fa-125">「收集辯論」</span><span class="sxs-lookup"><span data-stu-id="888fa-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="888fa-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="888fa-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="888fa-127">使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="888fa-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="888fa-128">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="888fa-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="888fa-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="888fa-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="888fa-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="888fa-130">Request headers</span></span>

<span data-ttu-id="888fa-131">名稱</span><span class="sxs-lookup"><span data-stu-id="888fa-131">Name</span></span> | <span data-ttu-id="888fa-132">類型</span><span class="sxs-lookup"><span data-stu-id="888fa-132">Type</span></span> | <span data-ttu-id="888fa-133">描述</span><span class="sxs-lookup"><span data-stu-id="888fa-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="888fa-134">授權</span><span class="sxs-lookup"><span data-stu-id="888fa-134">Authorization</span></span> | <span data-ttu-id="888fa-135">字串</span><span class="sxs-lookup"><span data-stu-id="888fa-135">String</span></span> | <span data-ttu-id="888fa-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="888fa-136">Bearer {token}.</span></span> <span data-ttu-id="888fa-137">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="888fa-137">**Required**.</span></span>
<span data-ttu-id="888fa-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="888fa-138">Content-Type</span></span> | <span data-ttu-id="888fa-139">string</span><span class="sxs-lookup"><span data-stu-id="888fa-139">string</span></span> | <span data-ttu-id="888fa-140">application/json。</span><span class="sxs-lookup"><span data-stu-id="888fa-140">application/json.</span></span> <span data-ttu-id="888fa-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="888fa-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="888fa-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="888fa-142">Request body</span></span>
<span data-ttu-id="888fa-143">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="888fa-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="888fa-144">參數</span><span class="sxs-lookup"><span data-stu-id="888fa-144">Parameter</span></span> | <span data-ttu-id="888fa-145">類型</span><span class="sxs-lookup"><span data-stu-id="888fa-145">Type</span></span>    | <span data-ttu-id="888fa-146">描述</span><span class="sxs-lookup"><span data-stu-id="888fa-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="888fa-147">留言</span><span class="sxs-lookup"><span data-stu-id="888fa-147">Comment</span></span> |   <span data-ttu-id="888fa-148">字串</span><span class="sxs-lookup"><span data-stu-id="888fa-148">String</span></span> |    <span data-ttu-id="888fa-149">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="888fa-149">Comment to associate with the action.</span></span> <span data-ttu-id="888fa-150">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="888fa-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="888fa-151">回應</span><span class="sxs-lookup"><span data-stu-id="888fa-151">Response</span></span>
<span data-ttu-id="888fa-152">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="888fa-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="888fa-153">範例</span><span class="sxs-lookup"><span data-stu-id="888fa-153">Example</span></span>

<span data-ttu-id="888fa-154">**請求**</span><span class="sxs-lookup"><span data-stu-id="888fa-154">**Request**</span></span>

<span data-ttu-id="888fa-155">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="888fa-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
