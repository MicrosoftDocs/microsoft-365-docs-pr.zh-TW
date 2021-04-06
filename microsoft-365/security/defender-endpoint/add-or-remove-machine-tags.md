---
title: 新增或移除電腦標記 API
description: 瞭解如何使用 [新增或移除電腦標記 API]，新增或移除 Microsoft Defender for Endpoint 中電腦的標記。
keywords: api、graph api、支援的 api、標記、電腦標記
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199769"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="06070-104">新增或移除電腦標記 API</span><span class="sxs-lookup"><span data-stu-id="06070-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="06070-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="06070-105">**Applies to:**</span></span>

- [<span data-ttu-id="06070-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="06070-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="06070-107">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="06070-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06070-108">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="06070-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="06070-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="06070-109">API description</span></span>

<span data-ttu-id="06070-110">新增或移除特定 [電腦](machine.md)的標記。</span><span class="sxs-lookup"><span data-stu-id="06070-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="06070-111">限制</span><span class="sxs-lookup"><span data-stu-id="06070-111">Limitations</span></span>

1. <span data-ttu-id="06070-112">您可以根據您設定的保留期間，在上次查看的機器上進行開機自檢。</span><span class="sxs-lookup"><span data-stu-id="06070-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="06070-113">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="06070-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="06070-114">權限</span><span class="sxs-lookup"><span data-stu-id="06070-114">Permissions</span></span>

<span data-ttu-id="06070-115">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="06070-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="06070-116">若要深入瞭解（包括如何選擇許可權），請參閱 [使用 Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="06070-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="06070-117">許可權類型</span><span class="sxs-lookup"><span data-stu-id="06070-117">Permission type</span></span> |    <span data-ttu-id="06070-118">權限</span><span class="sxs-lookup"><span data-stu-id="06070-118">Permission</span></span>    |    <span data-ttu-id="06070-119">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="06070-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="06070-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="06070-120">Application</span></span> |    <span data-ttu-id="06070-121">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="06070-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="06070-122">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="06070-122">'Read and write all machine information'</span></span>
<span data-ttu-id="06070-123">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="06070-123">Delegated (work or school account)</span></span> | <span data-ttu-id="06070-124">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="06070-124">Machine.ReadWrite</span></span> | <span data-ttu-id="06070-125">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="06070-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="06070-126">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="06070-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="06070-127">使用者至少必須具備下列角色許可權：「管理安全性設定」。</span><span class="sxs-lookup"><span data-stu-id="06070-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="06070-128">如需詳細資訊，請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊 () </span><span class="sxs-lookup"><span data-stu-id="06070-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="06070-129">使用者必須能夠存取機器（根據電腦群組設定） (請參閱 [建立及管理電腦群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="06070-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="06070-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="06070-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="06070-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="06070-131">Request headers</span></span>

<span data-ttu-id="06070-132">名稱</span><span class="sxs-lookup"><span data-stu-id="06070-132">Name</span></span> | <span data-ttu-id="06070-133">類型</span><span class="sxs-lookup"><span data-stu-id="06070-133">Type</span></span> | <span data-ttu-id="06070-134">描述</span><span class="sxs-lookup"><span data-stu-id="06070-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="06070-135">授權</span><span class="sxs-lookup"><span data-stu-id="06070-135">Authorization</span></span> | <span data-ttu-id="06070-136">字串</span><span class="sxs-lookup"><span data-stu-id="06070-136">String</span></span> | <span data-ttu-id="06070-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="06070-137">Bearer {token}.</span></span> <span data-ttu-id="06070-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="06070-138">**Required**.</span></span>
<span data-ttu-id="06070-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="06070-139">Content-Type</span></span> | <span data-ttu-id="06070-140">string</span><span class="sxs-lookup"><span data-stu-id="06070-140">string</span></span> | <span data-ttu-id="06070-141">application/json。</span><span class="sxs-lookup"><span data-stu-id="06070-141">application/json.</span></span> <span data-ttu-id="06070-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="06070-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="06070-143">要求正文</span><span class="sxs-lookup"><span data-stu-id="06070-143">Request body</span></span>

<span data-ttu-id="06070-144">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="06070-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="06070-145">參數</span><span class="sxs-lookup"><span data-stu-id="06070-145">Parameter</span></span> |    <span data-ttu-id="06070-146">類型</span><span class="sxs-lookup"><span data-stu-id="06070-146">Type</span></span>    | <span data-ttu-id="06070-147">描述</span><span class="sxs-lookup"><span data-stu-id="06070-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="06070-148">值</span><span class="sxs-lookup"><span data-stu-id="06070-148">Value</span></span> |    <span data-ttu-id="06070-149">字串</span><span class="sxs-lookup"><span data-stu-id="06070-149">String</span></span> |    <span data-ttu-id="06070-150">標記名稱。</span><span class="sxs-lookup"><span data-stu-id="06070-150">The tag name.</span></span> <span data-ttu-id="06070-151">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="06070-151">**Required**.</span></span>
<span data-ttu-id="06070-152">動作</span><span class="sxs-lookup"><span data-stu-id="06070-152">Action</span></span>    | <span data-ttu-id="06070-153">Enum</span><span class="sxs-lookup"><span data-stu-id="06070-153">Enum</span></span> |    <span data-ttu-id="06070-154">新增或移除。</span><span class="sxs-lookup"><span data-stu-id="06070-154">Add or Remove.</span></span> <span data-ttu-id="06070-155">允許的值為： "Add" 或 "Remove"。</span><span class="sxs-lookup"><span data-stu-id="06070-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="06070-156">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="06070-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="06070-157">回應</span><span class="sxs-lookup"><span data-stu-id="06070-157">Response</span></span>

<span data-ttu-id="06070-158">如果成功，這個方法會傳回 200-Ok 回應碼和回應內文中的更新電腦。</span><span class="sxs-lookup"><span data-stu-id="06070-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="06070-159">範例</span><span class="sxs-lookup"><span data-stu-id="06070-159">Example</span></span>

<span data-ttu-id="06070-160">**請求**</span><span class="sxs-lookup"><span data-stu-id="06070-160">**Request**</span></span>

<span data-ttu-id="06070-161">以下是新增電腦標記之要求的範例。</span><span class="sxs-lookup"><span data-stu-id="06070-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="06070-162">若要移除電腦標記，請將動作設定為 "Remove"，而不是在要求主體中的 ' Add '。</span><span class="sxs-lookup"><span data-stu-id="06070-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>