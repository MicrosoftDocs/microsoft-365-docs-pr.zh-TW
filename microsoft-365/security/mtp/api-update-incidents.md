---
title: 更新事件 API
description: 瞭解如何使用 Microsoft 365 Defender API 更新事件
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
ms.openlocfilehash: 6fc1ff730994f03aa500ad9a4559b66970e32d87
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719401"
---
# <a name="update-incidents-api"></a><span data-ttu-id="95611-104">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="95611-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="95611-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="95611-105">**Applies to:**</span></span>

- <span data-ttu-id="95611-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95611-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95611-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="95611-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="95611-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="95611-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="95611-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="95611-109">API description</span></span>

<span data-ttu-id="95611-110">更新現有事件的屬性。</span><span class="sxs-lookup"><span data-stu-id="95611-110">Updates properties of existing incident.</span></span> <span data-ttu-id="95611-111">可更新的屬性包括：、、、 ```status``` ```determination``` ```classification``` ```assignedTo``` 和 ```tags``` 。</span><span class="sxs-lookup"><span data-stu-id="95611-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="95611-112">配額、資源配置及其他限制</span><span class="sxs-lookup"><span data-stu-id="95611-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="95611-113">您最多可以每分鐘撥打50個通話或每小時1500個通話，然後再按節流臨界值。</span><span class="sxs-lookup"><span data-stu-id="95611-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="95611-114">`determination`只有在設定為 TruePositive 時，您才可以設定屬性 `classification` 。</span><span class="sxs-lookup"><span data-stu-id="95611-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="95611-115">如果您的要求遭到限制，它會傳回 `429` 回應碼。</span><span class="sxs-lookup"><span data-stu-id="95611-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="95611-116">回應內文會指出您可以開始進行新呼叫的時間。</span><span class="sxs-lookup"><span data-stu-id="95611-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="95611-117">權限</span><span class="sxs-lookup"><span data-stu-id="95611-117">Permissions</span></span>

<span data-ttu-id="95611-118">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="95611-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="95611-119">若要深入瞭解，包括如何選擇許可權，請參閱 [Access The Microsoft 365 Defender APIs](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="95611-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="95611-120">許可權類型</span><span class="sxs-lookup"><span data-stu-id="95611-120">Permission type</span></span> | <span data-ttu-id="95611-121">權限</span><span class="sxs-lookup"><span data-stu-id="95611-121">Permission</span></span> | <span data-ttu-id="95611-122">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="95611-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="95611-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="95611-123">Application</span></span> | <span data-ttu-id="95611-124">Incident。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="95611-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="95611-125">讀取和寫入所有事件</span><span class="sxs-lookup"><span data-stu-id="95611-125">Read and write all incidents</span></span>
<span data-ttu-id="95611-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="95611-126">Delegated (work or school account)</span></span> | <span data-ttu-id="95611-127">Incident。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="95611-127">Incident.ReadWrite</span></span> | <span data-ttu-id="95611-128">讀取和寫入事件</span><span class="sxs-lookup"><span data-stu-id="95611-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="95611-129">使用使用者認證取得權杖時，使用者必須具有更新入口網站中的事件的許可權。</span><span class="sxs-lookup"><span data-stu-id="95611-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="95611-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="95611-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="95611-131">要求標頭</span><span class="sxs-lookup"><span data-stu-id="95611-131">Request headers</span></span>

<span data-ttu-id="95611-132">名稱</span><span class="sxs-lookup"><span data-stu-id="95611-132">Name</span></span> | <span data-ttu-id="95611-133">類型</span><span class="sxs-lookup"><span data-stu-id="95611-133">Type</span></span> | <span data-ttu-id="95611-134">描述</span><span class="sxs-lookup"><span data-stu-id="95611-134">Description</span></span>
-|-|-
<span data-ttu-id="95611-135">授權</span><span class="sxs-lookup"><span data-stu-id="95611-135">Authorization</span></span> | <span data-ttu-id="95611-136">字串</span><span class="sxs-lookup"><span data-stu-id="95611-136">String</span></span> | <span data-ttu-id="95611-137">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="95611-137">Bearer {token}.</span></span> <span data-ttu-id="95611-138">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="95611-138">**Required**.</span></span>
<span data-ttu-id="95611-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="95611-139">Content-Type</span></span> | <span data-ttu-id="95611-140">字串</span><span class="sxs-lookup"><span data-stu-id="95611-140">String</span></span> | <span data-ttu-id="95611-141">application/json。</span><span class="sxs-lookup"><span data-stu-id="95611-141">application/json.</span></span> <span data-ttu-id="95611-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="95611-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="95611-143">要求正文</span><span class="sxs-lookup"><span data-stu-id="95611-143">Request body</span></span>

<span data-ttu-id="95611-144">在要求內文中，提供應該更新之欄位的值。</span><span class="sxs-lookup"><span data-stu-id="95611-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="95611-145">在要求內文中未包含的現有屬性會維持其值，除非因相關值的變更而必須重新計算這些屬性。</span><span class="sxs-lookup"><span data-stu-id="95611-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="95611-146">為了達到最佳效能，您應該省略尚未變更的現有值。</span><span class="sxs-lookup"><span data-stu-id="95611-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="95611-147">屬性	</span><span class="sxs-lookup"><span data-stu-id="95611-147">Property</span></span> | <span data-ttu-id="95611-148">類型</span><span class="sxs-lookup"><span data-stu-id="95611-148">Type</span></span> | <span data-ttu-id="95611-149">描述</span><span class="sxs-lookup"><span data-stu-id="95611-149">Description</span></span>
-|-|-
<span data-ttu-id="95611-150">地位</span><span class="sxs-lookup"><span data-stu-id="95611-150">status</span></span> | <span data-ttu-id="95611-151">Enum</span><span class="sxs-lookup"><span data-stu-id="95611-151">Enum</span></span> | <span data-ttu-id="95611-152">指定警示的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="95611-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="95611-153">可能的值為： ```Active``` 、 ```Resolved``` 、和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="95611-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="95611-154">分配</span><span class="sxs-lookup"><span data-stu-id="95611-154">assignedTo</span></span> | <span data-ttu-id="95611-155">string</span><span class="sxs-lookup"><span data-stu-id="95611-155">string</span></span> | <span data-ttu-id="95611-156">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="95611-156">Owner of the incident.</span></span>
<span data-ttu-id="95611-157">分類</span><span class="sxs-lookup"><span data-stu-id="95611-157">classification</span></span> | <span data-ttu-id="95611-158">Enum</span><span class="sxs-lookup"><span data-stu-id="95611-158">Enum</span></span> | <span data-ttu-id="95611-159">警示的規格。</span><span class="sxs-lookup"><span data-stu-id="95611-159">Specification of the alert.</span></span> <span data-ttu-id="95611-160">可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。</span><span class="sxs-lookup"><span data-stu-id="95611-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="95611-161">測定</span><span class="sxs-lookup"><span data-stu-id="95611-161">determination</span></span> | <span data-ttu-id="95611-162">Enum</span><span class="sxs-lookup"><span data-stu-id="95611-162">Enum</span></span> | <span data-ttu-id="95611-163">指定報警的決定。</span><span class="sxs-lookup"><span data-stu-id="95611-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="95611-164">可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="95611-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="95611-165">標籤</span><span class="sxs-lookup"><span data-stu-id="95611-165">tags</span></span> | <span data-ttu-id="95611-166">字串清單</span><span class="sxs-lookup"><span data-stu-id="95611-166">string List</span></span> | <span data-ttu-id="95611-167">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="95611-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="95611-168">回應</span><span class="sxs-lookup"><span data-stu-id="95611-168">Response</span></span>

<span data-ttu-id="95611-169">如果成功，則此方法會傳回 `200 OK` 。</span><span class="sxs-lookup"><span data-stu-id="95611-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="95611-170">回應內文會包含具有更新屬性的 incident 實體。</span><span class="sxs-lookup"><span data-stu-id="95611-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="95611-171">如果找不到具有指定識別碼的事件，此方法就會傳回 `404 Not Found` 。</span><span class="sxs-lookup"><span data-stu-id="95611-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="95611-172">範例</span><span class="sxs-lookup"><span data-stu-id="95611-172">Example</span></span>

<span data-ttu-id="95611-173">**請求**</span><span class="sxs-lookup"><span data-stu-id="95611-173">**Request**</span></span>

<span data-ttu-id="95611-174">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="95611-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="95611-175">**回應**</span><span class="sxs-lookup"><span data-stu-id="95611-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="95611-176">相關文章</span><span class="sxs-lookup"><span data-stu-id="95611-176">Related articles</span></span>

- [<span data-ttu-id="95611-177">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="95611-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="95611-178">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="95611-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="95611-179">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="95611-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="95611-180">事件 API</span><span class="sxs-lookup"><span data-stu-id="95611-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="95611-181">列出事件</span><span class="sxs-lookup"><span data-stu-id="95611-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="95611-182">事件概觀</span><span class="sxs-lookup"><span data-stu-id="95611-182">Incidents overview</span></span>](incidents-overview.md)
