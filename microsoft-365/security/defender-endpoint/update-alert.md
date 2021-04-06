---
title: 更新警示實體 API
description: 瞭解如何使用此 API 更新 Microsoft Defender ATP 警示。 您可以更新狀態、判斷、分類及分配屬性。
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
ms.technology: mde
ms.openlocfilehash: 7dd3ab3da34efa6cb954db2a596d7a1e48efedf1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199306"
---
# <a name="update-alert"></a><span data-ttu-id="3a19e-105">更新警示</span><span class="sxs-lookup"><span data-stu-id="3a19e-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3a19e-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3a19e-106">**Applies to:**</span></span>
- [<span data-ttu-id="3a19e-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3a19e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3a19e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a19e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3a19e-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3a19e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3a19e-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3a19e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3a19e-111">API 描述</span><span class="sxs-lookup"><span data-stu-id="3a19e-111">API description</span></span>
<span data-ttu-id="3a19e-112">更新現有 [警示](alerts.md)的屬性。</span><span class="sxs-lookup"><span data-stu-id="3a19e-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="3a19e-113">提交 **批註** 可用於或不更新屬性。</span><span class="sxs-lookup"><span data-stu-id="3a19e-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="3a19e-114">可更新的屬性包括： ```status``` 、 ```determination``` 、 ```classification``` 和 ```assignedTo``` 。</span><span class="sxs-lookup"><span data-stu-id="3a19e-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="3a19e-115">限制</span><span class="sxs-lookup"><span data-stu-id="3a19e-115">Limitations</span></span>
1. <span data-ttu-id="3a19e-116">您可以更新可在 API 中使用的警示。</span><span class="sxs-lookup"><span data-stu-id="3a19e-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="3a19e-117">如需詳細資訊，請參閱 [清單提醒](get-alerts.md) 。</span><span class="sxs-lookup"><span data-stu-id="3a19e-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="3a19e-118">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="3a19e-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3a19e-119">權限</span><span class="sxs-lookup"><span data-stu-id="3a19e-119">Permissions</span></span>
<span data-ttu-id="3a19e-120">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="3a19e-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3a19e-121">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3a19e-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3a19e-122">許可權類型</span><span class="sxs-lookup"><span data-stu-id="3a19e-122">Permission type</span></span> |   <span data-ttu-id="3a19e-123">權限</span><span class="sxs-lookup"><span data-stu-id="3a19e-123">Permission</span></span>  |   <span data-ttu-id="3a19e-124">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="3a19e-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3a19e-125">應用程式</span><span class="sxs-lookup"><span data-stu-id="3a19e-125">Application</span></span> |   <span data-ttu-id="3a19e-126">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="3a19e-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="3a19e-127">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="3a19e-127">'Read and write all alerts'</span></span>
<span data-ttu-id="3a19e-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="3a19e-128">Delegated (work or school account)</span></span> | <span data-ttu-id="3a19e-129">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3a19e-129">Alert.ReadWrite</span></span> | <span data-ttu-id="3a19e-130">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="3a19e-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="3a19e-131">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="3a19e-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3a19e-132">使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="3a19e-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3a19e-133">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="3a19e-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3a19e-134">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="3a19e-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="3a19e-135">要求標頭</span><span class="sxs-lookup"><span data-stu-id="3a19e-135">Request headers</span></span>

<span data-ttu-id="3a19e-136">名稱</span><span class="sxs-lookup"><span data-stu-id="3a19e-136">Name</span></span> | <span data-ttu-id="3a19e-137">類型</span><span class="sxs-lookup"><span data-stu-id="3a19e-137">Type</span></span> | <span data-ttu-id="3a19e-138">描述</span><span class="sxs-lookup"><span data-stu-id="3a19e-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="3a19e-139">授權</span><span class="sxs-lookup"><span data-stu-id="3a19e-139">Authorization</span></span> | <span data-ttu-id="3a19e-140">字串</span><span class="sxs-lookup"><span data-stu-id="3a19e-140">String</span></span> | <span data-ttu-id="3a19e-141">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="3a19e-141">Bearer {token}.</span></span> <span data-ttu-id="3a19e-142">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3a19e-142">**Required**.</span></span>
<span data-ttu-id="3a19e-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3a19e-143">Content-Type</span></span> | <span data-ttu-id="3a19e-144">字串</span><span class="sxs-lookup"><span data-stu-id="3a19e-144">String</span></span> | <span data-ttu-id="3a19e-145">application/json。</span><span class="sxs-lookup"><span data-stu-id="3a19e-145">application/json.</span></span> <span data-ttu-id="3a19e-146">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="3a19e-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3a19e-147">要求正文</span><span class="sxs-lookup"><span data-stu-id="3a19e-147">Request body</span></span>
<span data-ttu-id="3a19e-148">在要求內文中，提供應該更新之相關欄位的值。</span><span class="sxs-lookup"><span data-stu-id="3a19e-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="3a19e-149">在要求內文中未包含的現有屬性會維持先前的值，或根據其他屬性值的變更重新計算。</span><span class="sxs-lookup"><span data-stu-id="3a19e-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="3a19e-150">為了達到最佳效能，您不應包含尚未變更的現有值。</span><span class="sxs-lookup"><span data-stu-id="3a19e-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="3a19e-151">屬性	</span><span class="sxs-lookup"><span data-stu-id="3a19e-151">Property</span></span> | <span data-ttu-id="3a19e-152">類型</span><span class="sxs-lookup"><span data-stu-id="3a19e-152">Type</span></span> | <span data-ttu-id="3a19e-153">描述</span><span class="sxs-lookup"><span data-stu-id="3a19e-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="3a19e-154">地位</span><span class="sxs-lookup"><span data-stu-id="3a19e-154">status</span></span> | <span data-ttu-id="3a19e-155">字串</span><span class="sxs-lookup"><span data-stu-id="3a19e-155">String</span></span> | <span data-ttu-id="3a19e-156">指定警示的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="3a19e-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="3a19e-157">屬性值為： ' New '、' InProgress ' 和 ' 已解析」。</span><span class="sxs-lookup"><span data-stu-id="3a19e-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="3a19e-158">分配</span><span class="sxs-lookup"><span data-stu-id="3a19e-158">assignedTo</span></span> | <span data-ttu-id="3a19e-159">字串</span><span class="sxs-lookup"><span data-stu-id="3a19e-159">String</span></span> | <span data-ttu-id="3a19e-160">警示的擁有者</span><span class="sxs-lookup"><span data-stu-id="3a19e-160">Owner of the alert</span></span>
<span data-ttu-id="3a19e-161">分類</span><span class="sxs-lookup"><span data-stu-id="3a19e-161">classification</span></span> | <span data-ttu-id="3a19e-162">字串</span><span class="sxs-lookup"><span data-stu-id="3a19e-162">String</span></span> | <span data-ttu-id="3a19e-163">指定警示的規格。</span><span class="sxs-lookup"><span data-stu-id="3a19e-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="3a19e-164">屬性值為： ' Unknown '、' FalsePositive '、' TruePositive '。</span><span class="sxs-lookup"><span data-stu-id="3a19e-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="3a19e-165">測定</span><span class="sxs-lookup"><span data-stu-id="3a19e-165">determination</span></span> | <span data-ttu-id="3a19e-166">字串</span><span class="sxs-lookup"><span data-stu-id="3a19e-166">String</span></span> | <span data-ttu-id="3a19e-167">指定報警的決定。</span><span class="sxs-lookup"><span data-stu-id="3a19e-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="3a19e-168">屬性值為： "NotAvailable"、"Apt"、"Malware"、"SecurityPersonnel"、"SecurityTesting"、"UnwantedSoftware"、"Other"</span><span class="sxs-lookup"><span data-stu-id="3a19e-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="3a19e-169">註解</span><span class="sxs-lookup"><span data-stu-id="3a19e-169">comment</span></span> | <span data-ttu-id="3a19e-170">字串</span><span class="sxs-lookup"><span data-stu-id="3a19e-170">String</span></span> | <span data-ttu-id="3a19e-171">要新增至警示的批註。</span><span class="sxs-lookup"><span data-stu-id="3a19e-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="3a19e-172">回應</span><span class="sxs-lookup"><span data-stu-id="3a19e-172">Response</span></span>
<span data-ttu-id="3a19e-173">如果成功，這個方法會傳回 200 OK，以及回應內文中的 [警示](alerts.md) 實體具有更新的屬性。</span><span class="sxs-lookup"><span data-stu-id="3a19e-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="3a19e-174">如果找不到具有指定識別碼的警示-找不到404。</span><span class="sxs-lookup"><span data-stu-id="3a19e-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3a19e-175">範例</span><span class="sxs-lookup"><span data-stu-id="3a19e-175">Example</span></span>

<span data-ttu-id="3a19e-176">**請求**</span><span class="sxs-lookup"><span data-stu-id="3a19e-176">**Request**</span></span>

<span data-ttu-id="3a19e-177">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="3a19e-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```