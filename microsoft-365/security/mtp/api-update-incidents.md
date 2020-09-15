---
title: 更新事件 API
description: 瞭解如何使用 Microsoft 威脅防護 API 更新事件
keywords: update、api、incident
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650184"
---
# <a name="update-incidents-api"></a><span data-ttu-id="1d829-104">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="1d829-104">Update incidents API</span></span>

<span data-ttu-id="1d829-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1d829-105">**Applies to:**</span></span>
- <span data-ttu-id="1d829-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="1d829-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1d829-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="1d829-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1d829-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1d829-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="1d829-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="1d829-109">API description</span></span>
<span data-ttu-id="1d829-110">更新現有事件的屬性。</span><span class="sxs-lookup"><span data-stu-id="1d829-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="1d829-111">可更新的屬性包括： ```status``` 、、 ```determination``` ```classification``` 、 ```assignedTo``` 和 ```tags``` 。</span><span class="sxs-lookup"><span data-stu-id="1d829-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="1d829-112">限制</span><span class="sxs-lookup"><span data-stu-id="1d829-112">Limitations</span></span>
1. <span data-ttu-id="1d829-113">此 API 的速率限制為每分鐘50個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="1d829-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="1d829-114">您可以設定 [ ```determination``` 只有當分類已設定為 TruePositive]。</span><span class="sxs-lookup"><span data-stu-id="1d829-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="1d829-115">權限</span><span class="sxs-lookup"><span data-stu-id="1d829-115">Permissions</span></span>
<span data-ttu-id="1d829-116">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="1d829-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d829-117">若要深入瞭解，包括如何選擇許可權，請參閱 [Access The Microsoft 威脅防護 APIs](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1d829-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="1d829-118">許可權類型</span><span class="sxs-lookup"><span data-stu-id="1d829-118">Permission type</span></span> |   <span data-ttu-id="1d829-119">權限</span><span class="sxs-lookup"><span data-stu-id="1d829-119">Permission</span></span>  |   <span data-ttu-id="1d829-120">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="1d829-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d829-121">應用程式</span><span class="sxs-lookup"><span data-stu-id="1d829-121">Application</span></span> |   <span data-ttu-id="1d829-122">Incident。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="1d829-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="1d829-123">「讀取和寫入所有事件」</span><span class="sxs-lookup"><span data-stu-id="1d829-123">'Read and write all incidents'</span></span>
<span data-ttu-id="1d829-124">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="1d829-124">Delegated (work or school account)</span></span> | <span data-ttu-id="1d829-125">Incident。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1d829-125">Incident.ReadWrite</span></span> | <span data-ttu-id="1d829-126">「讀取和寫入事件」</span><span class="sxs-lookup"><span data-stu-id="1d829-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="1d829-127">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="1d829-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1d829-128">使用者必須具有更新入口網站中之事件的許可權。</span><span class="sxs-lookup"><span data-stu-id="1d829-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="1d829-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="1d829-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="1d829-130">要求標頭</span><span class="sxs-lookup"><span data-stu-id="1d829-130">Request headers</span></span>

<span data-ttu-id="1d829-131">名稱</span><span class="sxs-lookup"><span data-stu-id="1d829-131">Name</span></span> | <span data-ttu-id="1d829-132">類型</span><span class="sxs-lookup"><span data-stu-id="1d829-132">Type</span></span> | <span data-ttu-id="1d829-133">描述</span><span class="sxs-lookup"><span data-stu-id="1d829-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d829-134">授權</span><span class="sxs-lookup"><span data-stu-id="1d829-134">Authorization</span></span> | <span data-ttu-id="1d829-135">字串</span><span class="sxs-lookup"><span data-stu-id="1d829-135">String</span></span> | <span data-ttu-id="1d829-136">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="1d829-136">Bearer {token}.</span></span> <span data-ttu-id="1d829-137">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="1d829-137">**Required**.</span></span>
<span data-ttu-id="1d829-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1d829-138">Content-Type</span></span> | <span data-ttu-id="1d829-139">字串</span><span class="sxs-lookup"><span data-stu-id="1d829-139">String</span></span> | <span data-ttu-id="1d829-140">application/json。</span><span class="sxs-lookup"><span data-stu-id="1d829-140">application/json.</span></span> <span data-ttu-id="1d829-141">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="1d829-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1d829-142">要求正文</span><span class="sxs-lookup"><span data-stu-id="1d829-142">Request body</span></span>
<span data-ttu-id="1d829-143">在要求內文中，提供應該更新之相關欄位的值。</span><span class="sxs-lookup"><span data-stu-id="1d829-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="1d829-144">在要求內文中未包含的現有屬性會維持先前的值，或根據其他屬性值的變更重新計算。</span><span class="sxs-lookup"><span data-stu-id="1d829-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="1d829-145">為了達到最佳效能，您不應包含尚未變更的現有值。</span><span class="sxs-lookup"><span data-stu-id="1d829-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="1d829-146">屬性	</span><span class="sxs-lookup"><span data-stu-id="1d829-146">Property</span></span> | <span data-ttu-id="1d829-147">類型</span><span class="sxs-lookup"><span data-stu-id="1d829-147">Type</span></span> | <span data-ttu-id="1d829-148">描述</span><span class="sxs-lookup"><span data-stu-id="1d829-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d829-149">地位</span><span class="sxs-lookup"><span data-stu-id="1d829-149">status</span></span> | <span data-ttu-id="1d829-150">Enum</span><span class="sxs-lookup"><span data-stu-id="1d829-150">Enum</span></span> | <span data-ttu-id="1d829-151">指定警示的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="1d829-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="1d829-152">可能的值為 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="1d829-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="1d829-153">分配</span><span class="sxs-lookup"><span data-stu-id="1d829-153">assignedTo</span></span> | <span data-ttu-id="1d829-154">string</span><span class="sxs-lookup"><span data-stu-id="1d829-154">string</span></span> | <span data-ttu-id="1d829-155">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="1d829-155">Owner of the incident.</span></span>
<span data-ttu-id="1d829-156">分類</span><span class="sxs-lookup"><span data-stu-id="1d829-156">classification</span></span> | <span data-ttu-id="1d829-157">Enum</span><span class="sxs-lookup"><span data-stu-id="1d829-157">Enum</span></span> | <span data-ttu-id="1d829-158">警示的規格。</span><span class="sxs-lookup"><span data-stu-id="1d829-158">Specification of the alert.</span></span> <span data-ttu-id="1d829-159">可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。</span><span class="sxs-lookup"><span data-stu-id="1d829-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="1d829-160">測定</span><span class="sxs-lookup"><span data-stu-id="1d829-160">determination</span></span> | <span data-ttu-id="1d829-161">Enum</span><span class="sxs-lookup"><span data-stu-id="1d829-161">Enum</span></span> | <span data-ttu-id="1d829-162">指定報警的決定。</span><span class="sxs-lookup"><span data-stu-id="1d829-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="1d829-163">可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="1d829-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="1d829-164">標籤</span><span class="sxs-lookup"><span data-stu-id="1d829-164">tags</span></span> | <span data-ttu-id="1d829-165">字串清單</span><span class="sxs-lookup"><span data-stu-id="1d829-165">string List</span></span> | <span data-ttu-id="1d829-166">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="1d829-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="1d829-167">回應</span><span class="sxs-lookup"><span data-stu-id="1d829-167">Response</span></span>
<span data-ttu-id="1d829-168">如果成功，這個方法會傳回 200 OK，以及回應內文中的事件實體具有更新的屬性。</span><span class="sxs-lookup"><span data-stu-id="1d829-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="1d829-169">如果找不到具有指定識別碼的事件-找不到404。</span><span class="sxs-lookup"><span data-stu-id="1d829-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1d829-170">範例</span><span class="sxs-lookup"><span data-stu-id="1d829-170">Example</span></span>

<span data-ttu-id="1d829-171">**請求**</span><span class="sxs-lookup"><span data-stu-id="1d829-171">**Request**</span></span>

<span data-ttu-id="1d829-172">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="1d829-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="1d829-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="1d829-173">Related topic</span></span>
- [<span data-ttu-id="1d829-174">事件 APIs</span><span class="sxs-lookup"><span data-stu-id="1d829-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="1d829-175">列出事件</span><span class="sxs-lookup"><span data-stu-id="1d829-175">List incidents</span></span>](api-list-incidents.md)