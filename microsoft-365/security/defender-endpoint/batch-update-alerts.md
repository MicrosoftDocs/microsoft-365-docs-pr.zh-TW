---
title: 批次更新警示實體 API
description: 瞭解如何使用此 API 更新批次中的 Microsoft Defender for Endpoint 警示。 您可以更新狀態、判斷、分類及分配屬性。
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
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290204"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="295f7-105">批次更新提醒</span><span class="sxs-lookup"><span data-stu-id="295f7-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="295f7-106">**適用于：** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="295f7-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="295f7-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="295f7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="295f7-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="295f7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="295f7-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="295f7-109">API description</span></span>

<span data-ttu-id="295f7-110">更新現有 [警示](alerts.md)批次的屬性。</span><span class="sxs-lookup"><span data-stu-id="295f7-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>

<span data-ttu-id="295f7-111">提交 **批註** 可用於或不更新屬性。</span><span class="sxs-lookup"><span data-stu-id="295f7-111">Submission of **comment** is available with or without updating properties.</span></span>

<span data-ttu-id="295f7-112">可更新的屬性包括： `status` 、 `determination` 、 `classification` 和 `assignedTo` 。</span><span class="sxs-lookup"><span data-stu-id="295f7-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>

## <a name="limitations"></a><span data-ttu-id="295f7-113">限制</span><span class="sxs-lookup"><span data-stu-id="295f7-113">Limitations</span></span>

1. <span data-ttu-id="295f7-114">您可以更新 API 中可用的警示。</span><span class="sxs-lookup"><span data-stu-id="295f7-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="295f7-115">如需詳細資訊，請參閱 [清單提醒](get-alerts.md) 。</span><span class="sxs-lookup"><span data-stu-id="295f7-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="295f7-116">此 API 的速率限制為每分鐘10個通話，每小時500個通話。</span><span class="sxs-lookup"><span data-stu-id="295f7-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="295f7-117">權限</span><span class="sxs-lookup"><span data-stu-id="295f7-117">Permissions</span></span>

<span data-ttu-id="295f7-118">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="295f7-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="295f7-119">若要深入瞭解，包括如何選擇許可權，請參閱 [使用 Microsoft Defender For Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="295f7-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="295f7-120">許可權類型</span><span class="sxs-lookup"><span data-stu-id="295f7-120">Permission type</span></span> | <span data-ttu-id="295f7-121">權限</span><span class="sxs-lookup"><span data-stu-id="295f7-121">Permission</span></span> | <span data-ttu-id="295f7-122">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="295f7-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="295f7-123">應用程式</span><span class="sxs-lookup"><span data-stu-id="295f7-123">Application</span></span> | <span data-ttu-id="295f7-124">警示。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="295f7-124">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="295f7-125">「讀取及寫入所有警示」</span><span class="sxs-lookup"><span data-stu-id="295f7-125">'Read and write all alerts'</span></span>
<span data-ttu-id="295f7-126">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="295f7-126">Delegated (work or school account)</span></span> | <span data-ttu-id="295f7-127">警示。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="295f7-127">Alert.ReadWrite</span></span> | <span data-ttu-id="295f7-128">「讀取及寫入警示」</span><span class="sxs-lookup"><span data-stu-id="295f7-128">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="295f7-129">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="295f7-129">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="295f7-130">使用者至少必須具備下列角色許可權：「警示調查」 (請參閱 [建立及管理角色](user-roles.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="295f7-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="295f7-131">使用者必須能夠存取與警示相關聯的裝置，其基礎取決於裝置群組設定 (請參閱 [建立及管理裝置群組](machine-groups.md) 以取得詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="295f7-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="295f7-132">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="295f7-132">HTTP request</span></span>

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="295f7-133">要求標頭</span><span class="sxs-lookup"><span data-stu-id="295f7-133">Request headers</span></span>

<span data-ttu-id="295f7-134">名稱</span><span class="sxs-lookup"><span data-stu-id="295f7-134">Name</span></span> | <span data-ttu-id="295f7-135">類型</span><span class="sxs-lookup"><span data-stu-id="295f7-135">Type</span></span> | <span data-ttu-id="295f7-136">說明</span><span class="sxs-lookup"><span data-stu-id="295f7-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="295f7-137">授權</span><span class="sxs-lookup"><span data-stu-id="295f7-137">Authorization</span></span> | <span data-ttu-id="295f7-138">字串</span><span class="sxs-lookup"><span data-stu-id="295f7-138">String</span></span> | <span data-ttu-id="295f7-139">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="295f7-139">Bearer {token}.</span></span> <span data-ttu-id="295f7-140">**必要**。</span><span class="sxs-lookup"><span data-stu-id="295f7-140">**Required**.</span></span>
<span data-ttu-id="295f7-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="295f7-141">Content-Type</span></span> | <span data-ttu-id="295f7-142">字串</span><span class="sxs-lookup"><span data-stu-id="295f7-142">String</span></span> | <span data-ttu-id="295f7-143">application/json。</span><span class="sxs-lookup"><span data-stu-id="295f7-143">application/json.</span></span> <span data-ttu-id="295f7-144">**必要**。</span><span class="sxs-lookup"><span data-stu-id="295f7-144">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="295f7-145">要求內文</span><span class="sxs-lookup"><span data-stu-id="295f7-145">Request body</span></span>

<span data-ttu-id="295f7-146">在 [要求內文] 中，提供要更新之警示的 IDs，以及您想要更新這些警示之相關欄位的值。</span><span class="sxs-lookup"><span data-stu-id="295f7-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>

<span data-ttu-id="295f7-147">在要求內文中未包含的現有屬性會維持先前的值，或根據其他屬性值的變更重新計算。</span><span class="sxs-lookup"><span data-stu-id="295f7-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span>

<span data-ttu-id="295f7-148">為了達到最佳效能，您不應包含尚未變更的現有值。</span><span class="sxs-lookup"><span data-stu-id="295f7-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="295f7-149">屬性	</span><span class="sxs-lookup"><span data-stu-id="295f7-149">Property</span></span> | <span data-ttu-id="295f7-150">類型</span><span class="sxs-lookup"><span data-stu-id="295f7-150">Type</span></span> | <span data-ttu-id="295f7-151">說明</span><span class="sxs-lookup"><span data-stu-id="295f7-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="295f7-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="295f7-152">alertIds</span></span> | <span data-ttu-id="295f7-153">清單 &lt; 字串&gt;</span><span class="sxs-lookup"><span data-stu-id="295f7-153">List&lt;String&gt;</span></span>| <span data-ttu-id="295f7-154">要更新之警示的 IDs 清單。</span><span class="sxs-lookup"><span data-stu-id="295f7-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="295f7-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="295f7-155">**Required**</span></span>
<span data-ttu-id="295f7-156">地位</span><span class="sxs-lookup"><span data-stu-id="295f7-156">status</span></span> | <span data-ttu-id="295f7-157">字串</span><span class="sxs-lookup"><span data-stu-id="295f7-157">String</span></span> | <span data-ttu-id="295f7-158">指定所指定警示的更新狀態。</span><span class="sxs-lookup"><span data-stu-id="295f7-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="295f7-159">屬性值為： ' New '、' InProgress ' 和 ' 已解析」。</span><span class="sxs-lookup"><span data-stu-id="295f7-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="295f7-160">分配</span><span class="sxs-lookup"><span data-stu-id="295f7-160">assignedTo</span></span> | <span data-ttu-id="295f7-161">字串</span><span class="sxs-lookup"><span data-stu-id="295f7-161">String</span></span> | <span data-ttu-id="295f7-162">指定警示的擁有者</span><span class="sxs-lookup"><span data-stu-id="295f7-162">Owner of the specified alerts</span></span>
<span data-ttu-id="295f7-163">分類</span><span class="sxs-lookup"><span data-stu-id="295f7-163">classification</span></span> | <span data-ttu-id="295f7-164">字串</span><span class="sxs-lookup"><span data-stu-id="295f7-164">String</span></span> | <span data-ttu-id="295f7-165">指定所指定警示的規格。</span><span class="sxs-lookup"><span data-stu-id="295f7-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="295f7-166">屬性值為： ' Unknown '、' FalsePositive '、' TruePositive '。</span><span class="sxs-lookup"><span data-stu-id="295f7-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="295f7-167">測定</span><span class="sxs-lookup"><span data-stu-id="295f7-167">determination</span></span> | <span data-ttu-id="295f7-168">字串</span><span class="sxs-lookup"><span data-stu-id="295f7-168">String</span></span> | <span data-ttu-id="295f7-169">指定所指定提醒的確定。</span><span class="sxs-lookup"><span data-stu-id="295f7-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="295f7-170">屬性值為： "NotAvailable"、"Apt"、"Malware"、"SecurityPersonnel"、"SecurityTesting"、"UnwantedSoftware"、"Other"</span><span class="sxs-lookup"><span data-stu-id="295f7-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="295f7-171">註解</span><span class="sxs-lookup"><span data-stu-id="295f7-171">comment</span></span> | <span data-ttu-id="295f7-172">字串</span><span class="sxs-lookup"><span data-stu-id="295f7-172">String</span></span> | <span data-ttu-id="295f7-173">要新增至指定提醒的批註。</span><span class="sxs-lookup"><span data-stu-id="295f7-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="295f7-174">回應</span><span class="sxs-lookup"><span data-stu-id="295f7-174">Response</span></span>

<span data-ttu-id="295f7-175">如果成功，這個方法會傳回 200 OK，並提供空白的回應內文。</span><span class="sxs-lookup"><span data-stu-id="295f7-175">If successful, this method returns 200 OK, with an empty response body.</span></span>

## <a name="example"></a><span data-ttu-id="295f7-176">範例</span><span class="sxs-lookup"><span data-stu-id="295f7-176">Example</span></span>

### <a name="request"></a><span data-ttu-id="295f7-177">請求</span><span class="sxs-lookup"><span data-stu-id="295f7-177">Request</span></span>

<span data-ttu-id="295f7-178">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="295f7-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
