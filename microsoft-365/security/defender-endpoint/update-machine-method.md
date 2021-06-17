---
title: 更新電腦實體 API
description: 瞭解如何使用此 API 更新電腦標記。 您可以更新 tags 和 devicevalue 屬性。
keywords: api、graph api、支援的 api、get、警示、資訊、識別碼
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985628"
---
# <a name="update-machine"></a><span data-ttu-id="3b748-105">更新電腦</span><span class="sxs-lookup"><span data-stu-id="3b748-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b748-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3b748-106">**Applies to:**</span></span>
- [<span data-ttu-id="3b748-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b748-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3b748-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b748-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b748-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="3b748-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3b748-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3b748-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3b748-111">API 描述</span><span class="sxs-lookup"><span data-stu-id="3b748-111">API description</span></span>
<span data-ttu-id="3b748-112">更新現有 [電腦](machine.md)的屬性。</span><span class="sxs-lookup"><span data-stu-id="3b748-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="3b748-113">可更新的屬性為： ```machineTags``` 和 ```deviceValue``` 。</span><span class="sxs-lookup"><span data-stu-id="3b748-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="3b748-114">限制</span><span class="sxs-lookup"><span data-stu-id="3b748-114">Limitations</span></span>
1. <span data-ttu-id="3b748-115">您可以更新 API 中提供的電腦。</span><span class="sxs-lookup"><span data-stu-id="3b748-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="3b748-116">更新機器只會將標記附加到 tag 集合。</span><span class="sxs-lookup"><span data-stu-id="3b748-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="3b748-117">如果有標籤存在，必須將它們包含在本文的 tags 集合中。</span><span class="sxs-lookup"><span data-stu-id="3b748-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="3b748-118">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="3b748-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3b748-119">權限</span><span class="sxs-lookup"><span data-stu-id="3b748-119">Permissions</span></span>
<span data-ttu-id="3b748-120">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3b748-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3b748-121">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3b748-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3b748-122">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3b748-122">Permission type</span></span> |   <span data-ttu-id="3b748-123">權限</span><span class="sxs-lookup"><span data-stu-id="3b748-123">Permission</span></span>  |   <span data-ttu-id="3b748-124">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3b748-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3b748-125">應用程式</span><span class="sxs-lookup"><span data-stu-id="3b748-125">Application</span></span> |   <span data-ttu-id="3b748-126">ReadWrite。所有</span><span class="sxs-lookup"><span data-stu-id="3b748-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="3b748-127">「讀取及寫入所有機器的機器資訊」</span><span class="sxs-lookup"><span data-stu-id="3b748-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="3b748-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3b748-128">Delegated (work or school account)</span></span> | <span data-ttu-id="3b748-129">ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3b748-129">Machine.ReadWrite</span></span> | <span data-ttu-id="3b748-130">「讀取及寫入機器資訊」</span><span class="sxs-lookup"><span data-stu-id="3b748-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="3b748-131">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="3b748-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3b748-132">使用者至少必須具備下列角色許可權：「警示調查」。</span><span class="sxs-lookup"><span data-stu-id="3b748-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="3b748-133">如需詳細資訊，請參閱 [Create and manage roles](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="3b748-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="3b748-134">使用者必須根據裝置群組設定，才能存取與警示相關聯的裝置。</span><span class="sxs-lookup"><span data-stu-id="3b748-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="3b748-135">如需詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="3b748-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="3b748-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3b748-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="3b748-137">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3b748-137">Request headers</span></span>

<span data-ttu-id="3b748-138">名稱</span><span class="sxs-lookup"><span data-stu-id="3b748-138">Name</span></span> | <span data-ttu-id="3b748-139">類型</span><span class="sxs-lookup"><span data-stu-id="3b748-139">Type</span></span> | <span data-ttu-id="3b748-140">描述</span><span class="sxs-lookup"><span data-stu-id="3b748-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="3b748-141">授權</span><span class="sxs-lookup"><span data-stu-id="3b748-141">Authorization</span></span> | <span data-ttu-id="3b748-142">字串</span><span class="sxs-lookup"><span data-stu-id="3b748-142">String</span></span> | <span data-ttu-id="3b748-143">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="3b748-143">Bearer {token}.</span></span> <span data-ttu-id="3b748-144">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3b748-144">**Required**.</span></span>
<span data-ttu-id="3b748-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3b748-145">Content-Type</span></span> | <span data-ttu-id="3b748-146">字串</span><span class="sxs-lookup"><span data-stu-id="3b748-146">String</span></span> | <span data-ttu-id="3b748-147">application/json。</span><span class="sxs-lookup"><span data-stu-id="3b748-147">application/json.</span></span> <span data-ttu-id="3b748-148">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3b748-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3b748-149">要求內文</span><span class="sxs-lookup"><span data-stu-id="3b748-149">Request body</span></span>
<span data-ttu-id="3b748-150">在要求內文中，提供應該更新之相關欄位的值。</span><span class="sxs-lookup"><span data-stu-id="3b748-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="3b748-151">在要求內文中未包含的現有屬性會維持先前的值，或根據其他屬性值的變更重新計算。</span><span class="sxs-lookup"><span data-stu-id="3b748-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="3b748-152">為了達到最佳效能，您不應包含尚未變更的現有值。</span><span class="sxs-lookup"><span data-stu-id="3b748-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="3b748-153">屬性	</span><span class="sxs-lookup"><span data-stu-id="3b748-153">Property</span></span> | <span data-ttu-id="3b748-154">類型</span><span class="sxs-lookup"><span data-stu-id="3b748-154">Type</span></span> | <span data-ttu-id="3b748-155">描述</span><span class="sxs-lookup"><span data-stu-id="3b748-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="3b748-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="3b748-156">machineTags</span></span> | <span data-ttu-id="3b748-157">String 集合</span><span class="sxs-lookup"><span data-stu-id="3b748-157">String collection</span></span> | <span data-ttu-id="3b748-158">[電腦](machine.md)標記的集合。</span><span class="sxs-lookup"><span data-stu-id="3b748-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="3b748-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="3b748-159">deviceValue</span></span> | <span data-ttu-id="3b748-160">可為 null 的列舉</span><span class="sxs-lookup"><span data-stu-id="3b748-160">Nullable Enum</span></span> | <span data-ttu-id="3b748-161">[裝置的值](tvm-assign-device-value.md)。</span><span class="sxs-lookup"><span data-stu-id="3b748-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="3b748-162">可能的值為： ' Normal '、' Low ' 和 ' High '。</span><span class="sxs-lookup"><span data-stu-id="3b748-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="3b748-163">回應</span><span class="sxs-lookup"><span data-stu-id="3b748-163">Response</span></span>
<span data-ttu-id="3b748-164">如果成功，這個方法會傳回 200 OK，以及回應內文中的 [machine](machine.md) 實體具有更新的屬性。</span><span class="sxs-lookup"><span data-stu-id="3b748-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="3b748-165">如果本文中的機器標記集合中不包含現有的電腦標記-400 無效輸入，以及通知遺失標記/s 的訊息。</span><span class="sxs-lookup"><span data-stu-id="3b748-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="3b748-166">如果找不到具有指定識別碼的電腦-找不到404。</span><span class="sxs-lookup"><span data-stu-id="3b748-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3b748-167">範例</span><span class="sxs-lookup"><span data-stu-id="3b748-167">Example</span></span>

<span data-ttu-id="3b748-168">**請求**</span><span class="sxs-lookup"><span data-stu-id="3b748-168">**Request**</span></span>

<span data-ttu-id="3b748-169">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3b748-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
