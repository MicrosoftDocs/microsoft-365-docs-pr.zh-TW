---
title: 更新事件 API
description: 瞭解如何使用 Microsoft 365 Defender API 更新事件
keywords: 更新、api、事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929067"
---
# <a name="update-incidents-api"></a><span data-ttu-id="a877c-104">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="a877c-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a877c-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="a877c-105">**Applies to:**</span></span>

- <span data-ttu-id="a877c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a877c-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a877c-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="a877c-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a877c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="a877c-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="a877c-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="a877c-109">API description</span></span>

<span data-ttu-id="a877c-110">更新現有事件的屬性。</span><span class="sxs-lookup"><span data-stu-id="a877c-110">Updates properties of existing incident.</span></span> <span data-ttu-id="a877c-111">可更新的屬性為 ```status``` ：、 ```determination``` ```classification``` ```assignedTo``` 及 ```tags``` 。</span><span class="sxs-lookup"><span data-stu-id="a877c-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="a877c-112">配額、資源配置及其他限制</span><span class="sxs-lookup"><span data-stu-id="a877c-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="a877c-113">您每分鐘可以撥打多達 50 個通話，或是每小時撥打 1500 個通話，然後再達到節流閾值。</span><span class="sxs-lookup"><span data-stu-id="a877c-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="a877c-114">只有在設為 `determination` `classification` TruePositive 時，您才能設定屬性。</span><span class="sxs-lookup"><span data-stu-id="a877c-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="a877c-115">如果您的要求已節流，它會返回 `429` 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="a877c-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="a877c-116">回復內體會指出您可以開始撥打新電話的時間。</span><span class="sxs-lookup"><span data-stu-id="a877c-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="a877c-117">權限</span><span class="sxs-lookup"><span data-stu-id="a877c-117">Permissions</span></span>

<span data-ttu-id="a877c-118">呼叫此 API 需要下列其中一個許可權。</span><span class="sxs-lookup"><span data-stu-id="a877c-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a877c-119">若要深入瞭解，包括如何選擇許可權，請參閱[存取 Microsoft 365 Defender API。](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="a877c-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="a877c-120">許可權類型</span><span class="sxs-lookup"><span data-stu-id="a877c-120">Permission type</span></span> | <span data-ttu-id="a877c-121">權限</span><span class="sxs-lookup"><span data-stu-id="a877c-121">Permission</span></span> | <span data-ttu-id="a877c-122">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="a877c-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="a877c-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="a877c-123">Application</span></span> | <span data-ttu-id="a877c-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a877c-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="a877c-125">讀取及寫入所有事件</span><span class="sxs-lookup"><span data-stu-id="a877c-125">Read and write all incidents</span></span>
<span data-ttu-id="a877c-126">已委派 (公司或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="a877c-126">Delegated (work or school account)</span></span> | <span data-ttu-id="a877c-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a877c-127">Incident.ReadWrite</span></span> | <span data-ttu-id="a877c-128">讀取和寫入事件</span><span class="sxs-lookup"><span data-stu-id="a877c-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="a877c-129">使用使用者認證取得權杖時，使用者需要有更新入口網站中事件的許可權。</span><span class="sxs-lookup"><span data-stu-id="a877c-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="a877c-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="a877c-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="a877c-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="a877c-131">Request headers</span></span>

<span data-ttu-id="a877c-132">名稱</span><span class="sxs-lookup"><span data-stu-id="a877c-132">Name</span></span> | <span data-ttu-id="a877c-133">類型</span><span class="sxs-lookup"><span data-stu-id="a877c-133">Type</span></span> | <span data-ttu-id="a877c-134">說明</span><span class="sxs-lookup"><span data-stu-id="a877c-134">Description</span></span>
-|-|-
<span data-ttu-id="a877c-135">授權</span><span class="sxs-lookup"><span data-stu-id="a877c-135">Authorization</span></span> | <span data-ttu-id="a877c-136">字串</span><span class="sxs-lookup"><span data-stu-id="a877c-136">String</span></span> | <span data-ttu-id="a877c-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a877c-137">Bearer {token}.</span></span> <span data-ttu-id="a877c-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="a877c-138">**Required**.</span></span>
<span data-ttu-id="a877c-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a877c-139">Content-Type</span></span> | <span data-ttu-id="a877c-140">字串</span><span class="sxs-lookup"><span data-stu-id="a877c-140">String</span></span> | <span data-ttu-id="a877c-141">application/json。</span><span class="sxs-lookup"><span data-stu-id="a877c-141">application/json.</span></span> <span data-ttu-id="a877c-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="a877c-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a877c-143">要求內體</span><span class="sxs-lookup"><span data-stu-id="a877c-143">Request body</span></span>

<span data-ttu-id="a877c-144">在要求內內容中，提供應該更新之欄位的值。</span><span class="sxs-lookup"><span data-stu-id="a877c-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="a877c-145">要求內內容中未包含的現有屬性會維持其值，除非因為相關值變更而必須重新計算。</span><span class="sxs-lookup"><span data-stu-id="a877c-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="a877c-146">為獲得最佳效果，您應省略未變更的現有值。</span><span class="sxs-lookup"><span data-stu-id="a877c-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="a877c-147">屬性	</span><span class="sxs-lookup"><span data-stu-id="a877c-147">Property</span></span> | <span data-ttu-id="a877c-148">類型</span><span class="sxs-lookup"><span data-stu-id="a877c-148">Type</span></span> | <span data-ttu-id="a877c-149">說明</span><span class="sxs-lookup"><span data-stu-id="a877c-149">Description</span></span>
-|-|-
<span data-ttu-id="a877c-150">地位</span><span class="sxs-lookup"><span data-stu-id="a877c-150">status</span></span> | <span data-ttu-id="a877c-151">Enum</span><span class="sxs-lookup"><span data-stu-id="a877c-151">Enum</span></span> | <span data-ttu-id="a877c-152">指定警示的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="a877c-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="a877c-153">可能的值有：、 ```Active``` ```Resolved``` 及 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="a877c-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="a877c-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a877c-154">assignedTo</span></span> | <span data-ttu-id="a877c-155">string</span><span class="sxs-lookup"><span data-stu-id="a877c-155">string</span></span> | <span data-ttu-id="a877c-156">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="a877c-156">Owner of the incident.</span></span>
<span data-ttu-id="a877c-157">分類</span><span class="sxs-lookup"><span data-stu-id="a877c-157">classification</span></span> | <span data-ttu-id="a877c-158">Enum</span><span class="sxs-lookup"><span data-stu-id="a877c-158">Enum</span></span> | <span data-ttu-id="a877c-159">警示的規格。</span><span class="sxs-lookup"><span data-stu-id="a877c-159">Specification of the alert.</span></span> <span data-ttu-id="a877c-160">可能的值有 ```Unknown``` ```FalsePositive``` ```TruePositive``` ：、、。</span><span class="sxs-lookup"><span data-stu-id="a877c-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a877c-161">測定</span><span class="sxs-lookup"><span data-stu-id="a877c-161">determination</span></span> | <span data-ttu-id="a877c-162">Enum</span><span class="sxs-lookup"><span data-stu-id="a877c-162">Enum</span></span> | <span data-ttu-id="a877c-163">指定警示決定。</span><span class="sxs-lookup"><span data-stu-id="a877c-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="a877c-164">可能的值有 ```NotAvailable``` ：、 ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="a877c-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a877c-165">標籤</span><span class="sxs-lookup"><span data-stu-id="a877c-165">tags</span></span> | <span data-ttu-id="a877c-166">字串清單</span><span class="sxs-lookup"><span data-stu-id="a877c-166">string List</span></span> | <span data-ttu-id="a877c-167">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="a877c-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="a877c-168">回應</span><span class="sxs-lookup"><span data-stu-id="a877c-168">Response</span></span>

<span data-ttu-id="a877c-169">如果成功，此方法會返回 `200 OK` 。</span><span class="sxs-lookup"><span data-stu-id="a877c-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="a877c-170">回應內內容會包含具有更新屬性的事件實體。</span><span class="sxs-lookup"><span data-stu-id="a877c-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="a877c-171">如果找不到具有指定識別碼的事件，方法會返回 `404 Not Found` 。</span><span class="sxs-lookup"><span data-stu-id="a877c-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="a877c-172">範例</span><span class="sxs-lookup"><span data-stu-id="a877c-172">Example</span></span>

<span data-ttu-id="a877c-173">**請求**</span><span class="sxs-lookup"><span data-stu-id="a877c-173">**Request**</span></span>

<span data-ttu-id="a877c-174">以下是要求範例。</span><span class="sxs-lookup"><span data-stu-id="a877c-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="a877c-175">**回應**</span><span class="sxs-lookup"><span data-stu-id="a877c-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="a877c-176">相關文章</span><span class="sxs-lookup"><span data-stu-id="a877c-176">Related articles</span></span>

- [<span data-ttu-id="a877c-177">存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="a877c-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="a877c-178">瞭解 API 限制與授權</span><span class="sxs-lookup"><span data-stu-id="a877c-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="a877c-179">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="a877c-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="a877c-180">事件 API</span><span class="sxs-lookup"><span data-stu-id="a877c-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="a877c-181">列出事件</span><span class="sxs-lookup"><span data-stu-id="a877c-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="a877c-182">事件概觀</span><span class="sxs-lookup"><span data-stu-id="a877c-182">Incidents overview</span></span>](incidents-overview.md)
