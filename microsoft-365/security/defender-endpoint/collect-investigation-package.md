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
ms.technology: mde
ms.openlocfilehash: 1e24236aae1922705c1711042f0426251a979ede
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166446"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="0e6e3-104">收集調查套件 API</span><span class="sxs-lookup"><span data-stu-id="0e6e3-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0e6e3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e6e3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0e6e3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e6e3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e6e3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="0e6e3-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0e6e3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e6e3-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0e6e3-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="0e6e3-110">API description</span></span>
<span data-ttu-id="0e6e3-111">從裝置收集調查套件。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="0e6e3-112">限制</span><span class="sxs-lookup"><span data-stu-id="0e6e3-112">Limitations</span></span>
1. <span data-ttu-id="0e6e3-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="0e6e3-114">權限</span><span class="sxs-lookup"><span data-stu-id="0e6e3-114">Permissions</span></span>
<span data-ttu-id="0e6e3-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0e6e3-116">若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0e6e3-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0e6e3-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="0e6e3-117">Permission type</span></span> |   <span data-ttu-id="0e6e3-118">權限</span><span class="sxs-lookup"><span data-stu-id="0e6e3-118">Permission</span></span>  |   <span data-ttu-id="0e6e3-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="0e6e3-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0e6e3-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="0e6e3-120">Application</span></span> |   <span data-ttu-id="0e6e3-121">CollectForensics</span><span class="sxs-lookup"><span data-stu-id="0e6e3-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="0e6e3-122">「收集辯論」</span><span class="sxs-lookup"><span data-stu-id="0e6e3-122">'Collect forensics'</span></span>
<span data-ttu-id="0e6e3-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="0e6e3-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="0e6e3-124">CollectForensics</span><span class="sxs-lookup"><span data-stu-id="0e6e3-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="0e6e3-125">「收集辯論」</span><span class="sxs-lookup"><span data-stu-id="0e6e3-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="0e6e3-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="0e6e3-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0e6e3-127">使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="0e6e3-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="0e6e3-128">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="0e6e3-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0e6e3-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="0e6e3-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="0e6e3-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="0e6e3-130">Request headers</span></span>

<span data-ttu-id="0e6e3-131">名稱</span><span class="sxs-lookup"><span data-stu-id="0e6e3-131">Name</span></span> | <span data-ttu-id="0e6e3-132">類型</span><span class="sxs-lookup"><span data-stu-id="0e6e3-132">Type</span></span> | <span data-ttu-id="0e6e3-133">描述</span><span class="sxs-lookup"><span data-stu-id="0e6e3-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="0e6e3-134">授權</span><span class="sxs-lookup"><span data-stu-id="0e6e3-134">Authorization</span></span> | <span data-ttu-id="0e6e3-135">字串</span><span class="sxs-lookup"><span data-stu-id="0e6e3-135">String</span></span> | <span data-ttu-id="0e6e3-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-136">Bearer {token}.</span></span> <span data-ttu-id="0e6e3-137">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-137">**Required**.</span></span>
<span data-ttu-id="0e6e3-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="0e6e3-138">Content-Type</span></span> | <span data-ttu-id="0e6e3-139">string</span><span class="sxs-lookup"><span data-stu-id="0e6e3-139">string</span></span> | <span data-ttu-id="0e6e3-140">application/json。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-140">application/json.</span></span> <span data-ttu-id="0e6e3-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="0e6e3-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="0e6e3-142">Request body</span></span>
<span data-ttu-id="0e6e3-143">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="0e6e3-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="0e6e3-144">參數</span><span class="sxs-lookup"><span data-stu-id="0e6e3-144">Parameter</span></span> | <span data-ttu-id="0e6e3-145">類型</span><span class="sxs-lookup"><span data-stu-id="0e6e3-145">Type</span></span>    | <span data-ttu-id="0e6e3-146">描述</span><span class="sxs-lookup"><span data-stu-id="0e6e3-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="0e6e3-147">留言</span><span class="sxs-lookup"><span data-stu-id="0e6e3-147">Comment</span></span> |   <span data-ttu-id="0e6e3-148">字串</span><span class="sxs-lookup"><span data-stu-id="0e6e3-148">String</span></span> |    <span data-ttu-id="0e6e3-149">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-149">Comment to associate with the action.</span></span> <span data-ttu-id="0e6e3-150">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="0e6e3-151">回應</span><span class="sxs-lookup"><span data-stu-id="0e6e3-151">Response</span></span>
<span data-ttu-id="0e6e3-152">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="0e6e3-153">範例</span><span class="sxs-lookup"><span data-stu-id="0e6e3-153">Example</span></span>

<span data-ttu-id="0e6e3-154">**請求**</span><span class="sxs-lookup"><span data-stu-id="0e6e3-154">**Request**</span></span>

<span data-ttu-id="0e6e3-155">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="0e6e3-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
