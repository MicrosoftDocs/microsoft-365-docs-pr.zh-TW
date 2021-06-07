---
title: 依標記 API 尋找裝置
description: 尋找所有包含 specifc 標記的裝置
keywords: api，支援的 api，get，裝置，尋找，尋找裝置，依標記，標記
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 88ad63d8b7cc71f7d3f809c7cb0371fc41bb9f5d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771162"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="6ab05-104">依標記 API 尋找裝置</span><span class="sxs-lookup"><span data-stu-id="6ab05-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6ab05-105">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6ab05-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6ab05-106">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="6ab05-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ab05-107">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6ab05-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6ab05-108">API 描述</span><span class="sxs-lookup"><span data-stu-id="6ab05-108">API description</span></span>
<span data-ttu-id="6ab05-109">依[標記](machine-tags.md)尋找[電腦](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="6ab05-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="6ab05-110">```startswith``` 支援查詢。</span><span class="sxs-lookup"><span data-stu-id="6ab05-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="6ab05-111">限制</span><span class="sxs-lookup"><span data-stu-id="6ab05-111">Limitations</span></span>
1. <span data-ttu-id="6ab05-112">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="6ab05-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="6ab05-113">權限</span><span class="sxs-lookup"><span data-stu-id="6ab05-113">Permissions</span></span>
<span data-ttu-id="6ab05-114">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="6ab05-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6ab05-115">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6ab05-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6ab05-116">許可權類型</span><span class="sxs-lookup"><span data-stu-id="6ab05-116">Permission type</span></span> |   <span data-ttu-id="6ab05-117">權限</span><span class="sxs-lookup"><span data-stu-id="6ab05-117">Permission</span></span>  |   <span data-ttu-id="6ab05-118">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="6ab05-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6ab05-119">應用程式</span><span class="sxs-lookup"><span data-stu-id="6ab05-119">Application</span></span> |   <span data-ttu-id="6ab05-120">Read。所有</span><span class="sxs-lookup"><span data-stu-id="6ab05-120">Machine.Read.All</span></span> |  <span data-ttu-id="6ab05-121">「讀取所有機器設定檔」</span><span class="sxs-lookup"><span data-stu-id="6ab05-121">'Read all machine profiles'</span></span>
<span data-ttu-id="6ab05-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="6ab05-122">Application</span></span> |   <span data-ttu-id="6ab05-123">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="6ab05-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="6ab05-124">「讀取及寫入所有機器資訊」</span><span class="sxs-lookup"><span data-stu-id="6ab05-124">'Read and write all machine information'</span></span>
<span data-ttu-id="6ab05-125">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="6ab05-125">Delegated (work or school account)</span></span> | <span data-ttu-id="6ab05-126">電腦. 讀取</span><span class="sxs-lookup"><span data-stu-id="6ab05-126">Machine.Read</span></span> | <span data-ttu-id="6ab05-127">「讀取機器資訊」</span><span class="sxs-lookup"><span data-stu-id="6ab05-127">'Read machine information'</span></span>
<span data-ttu-id="6ab05-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="6ab05-128">Delegated (work or school account)</span></span> | <span data-ttu-id="6ab05-129">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6ab05-129">Machine.ReadWrite</span></span> | <span data-ttu-id="6ab05-130">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="6ab05-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="6ab05-131">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="6ab05-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="6ab05-132">回應只會包含使用者依據裝置群組設定存取的裝置 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="6ab05-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="6ab05-133">使用者至少必須具備下列角色許可權：「View Data ' (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="6ab05-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="6ab05-134">回應只會包含使用者依據裝置群組設定存取的裝置 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="6ab05-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6ab05-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="6ab05-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="6ab05-136">要求標頭</span><span class="sxs-lookup"><span data-stu-id="6ab05-136">Request headers</span></span>

<span data-ttu-id="6ab05-137">名稱</span><span class="sxs-lookup"><span data-stu-id="6ab05-137">Name</span></span> | <span data-ttu-id="6ab05-138">類型</span><span class="sxs-lookup"><span data-stu-id="6ab05-138">Type</span></span> | <span data-ttu-id="6ab05-139">描述</span><span class="sxs-lookup"><span data-stu-id="6ab05-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="6ab05-140">授權</span><span class="sxs-lookup"><span data-stu-id="6ab05-140">Authorization</span></span> | <span data-ttu-id="6ab05-141">字串</span><span class="sxs-lookup"><span data-stu-id="6ab05-141">String</span></span> | <span data-ttu-id="6ab05-142">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="6ab05-142">Bearer {token}.</span></span> <span data-ttu-id="6ab05-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="6ab05-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="6ab05-144">要求 URI 參數</span><span class="sxs-lookup"><span data-stu-id="6ab05-144">Request URI parameters</span></span>

<span data-ttu-id="6ab05-145">名稱</span><span class="sxs-lookup"><span data-stu-id="6ab05-145">Name</span></span> | <span data-ttu-id="6ab05-146">類型</span><span class="sxs-lookup"><span data-stu-id="6ab05-146">Type</span></span> | <span data-ttu-id="6ab05-147">描述</span><span class="sxs-lookup"><span data-stu-id="6ab05-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="6ab05-148">Tag</span><span class="sxs-lookup"><span data-stu-id="6ab05-148">tag</span></span> | <span data-ttu-id="6ab05-149">字串</span><span class="sxs-lookup"><span data-stu-id="6ab05-149">String</span></span> | <span data-ttu-id="6ab05-150">標記名稱。</span><span class="sxs-lookup"><span data-stu-id="6ab05-150">The tag name.</span></span> <span data-ttu-id="6ab05-151">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="6ab05-151">**Required**.</span></span>
<span data-ttu-id="6ab05-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="6ab05-152">useStartsWithFilter</span></span> | <span data-ttu-id="6ab05-153">布林值</span><span class="sxs-lookup"><span data-stu-id="6ab05-153">Boolean</span></span> | <span data-ttu-id="6ab05-154">設為 true 時，搜尋會尋找所有具有標籤名稱的標籤以查詢中指定的標記開始的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="6ab05-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="6ab05-155">預設值為 false。</span><span class="sxs-lookup"><span data-stu-id="6ab05-155">Defaults to false.</span></span> <span data-ttu-id="6ab05-156">此為選擇性欄位。</span><span class="sxs-lookup"><span data-stu-id="6ab05-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="6ab05-157">要求正文</span><span class="sxs-lookup"><span data-stu-id="6ab05-157">Request body</span></span>
<span data-ttu-id="6ab05-158">空白</span><span class="sxs-lookup"><span data-stu-id="6ab05-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6ab05-159">回應</span><span class="sxs-lookup"><span data-stu-id="6ab05-159">Response</span></span>
<span data-ttu-id="6ab05-160">如果成功-200 OK （含回應內的機器清單）。</span><span class="sxs-lookup"><span data-stu-id="6ab05-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="6ab05-161">範例</span><span class="sxs-lookup"><span data-stu-id="6ab05-161">Example</span></span>

<span data-ttu-id="6ab05-162">**請求**</span><span class="sxs-lookup"><span data-stu-id="6ab05-162">**Request**</span></span>

<span data-ttu-id="6ab05-163">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="6ab05-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```