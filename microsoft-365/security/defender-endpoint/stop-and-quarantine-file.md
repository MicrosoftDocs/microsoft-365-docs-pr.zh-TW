---
title: 停止與隔離檔 API
description: 瞭解如何停止在裝置上執行檔，並在 Microsoft Defender for Endpoint 中刪除檔案。 請參閱範例。
keywords: api、graph api、支援的 api、停止和隔離檔案
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
ms.openlocfilehash: ac14f1ecda2b6256dc19223869b8878e6e725b96
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771395"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="9faee-105">停止與隔離檔 API</span><span class="sxs-lookup"><span data-stu-id="9faee-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9faee-106">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9faee-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9faee-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="9faee-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9faee-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="9faee-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9faee-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="9faee-109">API description</span></span>
<span data-ttu-id="9faee-110">停止執行裝置上的檔案，並將它刪除。</span><span class="sxs-lookup"><span data-stu-id="9faee-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="9faee-111">限制</span><span class="sxs-lookup"><span data-stu-id="9faee-111">Limitations</span></span>
1. <span data-ttu-id="9faee-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="9faee-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="9faee-113">權限</span><span class="sxs-lookup"><span data-stu-id="9faee-113">Permissions</span></span>
<span data-ttu-id="9faee-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="9faee-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9faee-115">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9faee-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9faee-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="9faee-116">Permission type</span></span> |   <span data-ttu-id="9faee-117">權限</span><span class="sxs-lookup"><span data-stu-id="9faee-117">Permission</span></span>  |   <span data-ttu-id="9faee-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="9faee-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9faee-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="9faee-119">Application</span></span> |   <span data-ttu-id="9faee-120">StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="9faee-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="9faee-121">「停止與隔離」</span><span class="sxs-lookup"><span data-stu-id="9faee-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="9faee-122">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="9faee-122">Delegated (work or school account)</span></span> | <span data-ttu-id="9faee-123">StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="9faee-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="9faee-124">「停止與隔離」</span><span class="sxs-lookup"><span data-stu-id="9faee-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="9faee-125">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="9faee-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9faee-126">使用者至少必須具備下列角色許可權：「作用中的修復動作」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="9faee-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9faee-127">使用者必須具有裝置的存取權，視裝置群組設定而定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="9faee-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9faee-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="9faee-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="9faee-129">要求標頭</span><span class="sxs-lookup"><span data-stu-id="9faee-129">Request headers</span></span>

<span data-ttu-id="9faee-130">名稱</span><span class="sxs-lookup"><span data-stu-id="9faee-130">Name</span></span> | <span data-ttu-id="9faee-131">類型</span><span class="sxs-lookup"><span data-stu-id="9faee-131">Type</span></span> | <span data-ttu-id="9faee-132">描述</span><span class="sxs-lookup"><span data-stu-id="9faee-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="9faee-133">授權</span><span class="sxs-lookup"><span data-stu-id="9faee-133">Authorization</span></span> | <span data-ttu-id="9faee-134">字串</span><span class="sxs-lookup"><span data-stu-id="9faee-134">String</span></span> | <span data-ttu-id="9faee-135">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="9faee-135">Bearer {token}.</span></span> <span data-ttu-id="9faee-136">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="9faee-136">**Required**.</span></span>
<span data-ttu-id="9faee-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9faee-137">Content-Type</span></span> | <span data-ttu-id="9faee-138">string</span><span class="sxs-lookup"><span data-stu-id="9faee-138">string</span></span> | <span data-ttu-id="9faee-139">application/json。</span><span class="sxs-lookup"><span data-stu-id="9faee-139">application/json.</span></span> <span data-ttu-id="9faee-140">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="9faee-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9faee-141">要求正文</span><span class="sxs-lookup"><span data-stu-id="9faee-141">Request body</span></span>
<span data-ttu-id="9faee-142">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="9faee-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="9faee-143">參數</span><span class="sxs-lookup"><span data-stu-id="9faee-143">Parameter</span></span> | <span data-ttu-id="9faee-144">類型</span><span class="sxs-lookup"><span data-stu-id="9faee-144">Type</span></span>    | <span data-ttu-id="9faee-145">描述</span><span class="sxs-lookup"><span data-stu-id="9faee-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="9faee-146">留言</span><span class="sxs-lookup"><span data-stu-id="9faee-146">Comment</span></span> |   <span data-ttu-id="9faee-147">字串</span><span class="sxs-lookup"><span data-stu-id="9faee-147">String</span></span> |    <span data-ttu-id="9faee-148">與動作相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="9faee-148">Comment to associate with the action.</span></span> <span data-ttu-id="9faee-149">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="9faee-149">**Required**.</span></span>
<span data-ttu-id="9faee-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="9faee-150">Sha1</span></span> |  <span data-ttu-id="9faee-151">字串</span><span class="sxs-lookup"><span data-stu-id="9faee-151">String</span></span>   | <span data-ttu-id="9faee-152">在裝置上停止和隔離之檔案的 Sha1。</span><span class="sxs-lookup"><span data-stu-id="9faee-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="9faee-153">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="9faee-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="9faee-154">回應</span><span class="sxs-lookup"><span data-stu-id="9faee-154">Response</span></span>
<span data-ttu-id="9faee-155">如果成功，這個方法會傳回201在回應內文中建立的回應程式碼和 [電腦動作](machineaction.md) 。</span><span class="sxs-lookup"><span data-stu-id="9faee-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="9faee-156">範例</span><span class="sxs-lookup"><span data-stu-id="9faee-156">Example</span></span>

<span data-ttu-id="9faee-157">**請求**</span><span class="sxs-lookup"><span data-stu-id="9faee-157">**Request**</span></span>

<span data-ttu-id="9faee-158">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="9faee-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
