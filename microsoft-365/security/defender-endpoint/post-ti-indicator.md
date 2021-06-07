---
title: 提交或更新指示器 API
description: 瞭解如何使用提交或更新指示器 API，在 Microsoft Defender for Endpoint 中提交或更新新的指示器實體。
keywords: api，graph api，支援的 api，submit，ti，標記，更新
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
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771702"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="ec10b-104">提交或更新指示器 API</span><span class="sxs-lookup"><span data-stu-id="ec10b-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec10b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ec10b-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec10b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ec10b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ec10b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec10b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ec10b-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ec10b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ec10b-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ec10b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ec10b-110">API 描述</span><span class="sxs-lookup"><span data-stu-id="ec10b-110">API description</span></span>
<span data-ttu-id="ec10b-111">提交或更新新的 [指示器](ti-indicator.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="ec10b-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="ec10b-112">不支援 IPs 的 CIDR 標記法。</span><span class="sxs-lookup"><span data-stu-id="ec10b-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="ec10b-113">限制</span><span class="sxs-lookup"><span data-stu-id="ec10b-113">Limitations</span></span>
1. <span data-ttu-id="ec10b-114">此 API 的速率限制為每分鐘100個通話，每小時1500個通話。</span><span class="sxs-lookup"><span data-stu-id="ec10b-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="ec10b-115">每個租使用者的活動指示器限制為15000。</span><span class="sxs-lookup"><span data-stu-id="ec10b-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="ec10b-116">權限</span><span class="sxs-lookup"><span data-stu-id="ec10b-116">Permissions</span></span>
<span data-ttu-id="ec10b-117">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="ec10b-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ec10b-118">若要深入瞭解，包括如何選擇許可權，請參閱 [入門](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ec10b-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="ec10b-119">許可權類型</span><span class="sxs-lookup"><span data-stu-id="ec10b-119">Permission type</span></span> |   <span data-ttu-id="ec10b-120">權限</span><span class="sxs-lookup"><span data-stu-id="ec10b-120">Permission</span></span>  |   <span data-ttu-id="ec10b-121">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="ec10b-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ec10b-122">應用程式</span><span class="sxs-lookup"><span data-stu-id="ec10b-122">Application</span></span> |   <span data-ttu-id="ec10b-123">Ti ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ec10b-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="ec10b-124">「讀取和寫入指示器」</span><span class="sxs-lookup"><span data-stu-id="ec10b-124">'Read and write Indicators'</span></span>
<span data-ttu-id="ec10b-125">應用程式</span><span class="sxs-lookup"><span data-stu-id="ec10b-125">Application</span></span> |   <span data-ttu-id="ec10b-126">Ti ReadWrite 所有</span><span class="sxs-lookup"><span data-stu-id="ec10b-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="ec10b-127">「讀取及寫入所有指示器」</span><span class="sxs-lookup"><span data-stu-id="ec10b-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="ec10b-128">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="ec10b-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="ec10b-129">Ti ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ec10b-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="ec10b-130">「讀取和寫入指示器」</span><span class="sxs-lookup"><span data-stu-id="ec10b-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="ec10b-131">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="ec10b-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="ec10b-132">要求標頭</span><span class="sxs-lookup"><span data-stu-id="ec10b-132">Request headers</span></span>

<span data-ttu-id="ec10b-133">名稱</span><span class="sxs-lookup"><span data-stu-id="ec10b-133">Name</span></span> | <span data-ttu-id="ec10b-134">類型</span><span class="sxs-lookup"><span data-stu-id="ec10b-134">Type</span></span> | <span data-ttu-id="ec10b-135">描述</span><span class="sxs-lookup"><span data-stu-id="ec10b-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="ec10b-136">授權</span><span class="sxs-lookup"><span data-stu-id="ec10b-136">Authorization</span></span> | <span data-ttu-id="ec10b-137">字串</span><span class="sxs-lookup"><span data-stu-id="ec10b-137">String</span></span> | <span data-ttu-id="ec10b-138">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="ec10b-138">Bearer {token}.</span></span> <span data-ttu-id="ec10b-139">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="ec10b-139">**Required**.</span></span>
<span data-ttu-id="ec10b-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ec10b-140">Content-Type</span></span> | <span data-ttu-id="ec10b-141">string</span><span class="sxs-lookup"><span data-stu-id="ec10b-141">string</span></span> | <span data-ttu-id="ec10b-142">application/json。</span><span class="sxs-lookup"><span data-stu-id="ec10b-142">application/json.</span></span> <span data-ttu-id="ec10b-143">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="ec10b-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ec10b-144">要求正文</span><span class="sxs-lookup"><span data-stu-id="ec10b-144">Request body</span></span>
<span data-ttu-id="ec10b-145">在要求主體中，提供具有下列參數的 JSON 物件：</span><span class="sxs-lookup"><span data-stu-id="ec10b-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="ec10b-146">參數</span><span class="sxs-lookup"><span data-stu-id="ec10b-146">Parameter</span></span> | <span data-ttu-id="ec10b-147">類型</span><span class="sxs-lookup"><span data-stu-id="ec10b-147">Type</span></span>    | <span data-ttu-id="ec10b-148">描述</span><span class="sxs-lookup"><span data-stu-id="ec10b-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="ec10b-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="ec10b-149">indicatorValue</span></span> | <span data-ttu-id="ec10b-150">字串</span><span class="sxs-lookup"><span data-stu-id="ec10b-150">String</span></span> | <span data-ttu-id="ec10b-151">[指示器](ti-indicator.md)實體的身分識別。</span><span class="sxs-lookup"><span data-stu-id="ec10b-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="ec10b-152">**Required**</span><span class="sxs-lookup"><span data-stu-id="ec10b-152">**Required**</span></span>
<span data-ttu-id="ec10b-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="ec10b-153">indicatorType</span></span> | <span data-ttu-id="ec10b-154">Enum</span><span class="sxs-lookup"><span data-stu-id="ec10b-154">Enum</span></span> | <span data-ttu-id="ec10b-155">指標的類型。</span><span class="sxs-lookup"><span data-stu-id="ec10b-155">Type of the indicator.</span></span> <span data-ttu-id="ec10b-156">可能的值為： "FileSha1"、"FileSha256"、"IpAddress"、"DomainName" 和 "Url"。</span><span class="sxs-lookup"><span data-stu-id="ec10b-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="ec10b-157">**Required**</span><span class="sxs-lookup"><span data-stu-id="ec10b-157">**Required**</span></span>
<span data-ttu-id="ec10b-158">action</span><span class="sxs-lookup"><span data-stu-id="ec10b-158">action</span></span> | <span data-ttu-id="ec10b-159">Enum</span><span class="sxs-lookup"><span data-stu-id="ec10b-159">Enum</span></span> | <span data-ttu-id="ec10b-160">將在組織中探索指示器時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="ec10b-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="ec10b-161">可能的值為： "Alert"、"AlertAndBlock" 和 "允許"。</span><span class="sxs-lookup"><span data-stu-id="ec10b-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="ec10b-162">**Required**</span><span class="sxs-lookup"><span data-stu-id="ec10b-162">**Required**</span></span>
<span data-ttu-id="ec10b-163">應用程式</span><span class="sxs-lookup"><span data-stu-id="ec10b-163">application</span></span> | <span data-ttu-id="ec10b-164">字串</span><span class="sxs-lookup"><span data-stu-id="ec10b-164">String</span></span> | <span data-ttu-id="ec10b-165">與指示器相關聯的應用程式。</span><span class="sxs-lookup"><span data-stu-id="ec10b-165">The application associated with the indicator.</span></span> <span data-ttu-id="ec10b-166">**Optional**</span><span class="sxs-lookup"><span data-stu-id="ec10b-166">**Optional**</span></span>
<span data-ttu-id="ec10b-167">標題</span><span class="sxs-lookup"><span data-stu-id="ec10b-167">title</span></span> | <span data-ttu-id="ec10b-168">String</span><span class="sxs-lookup"><span data-stu-id="ec10b-168">String</span></span> | <span data-ttu-id="ec10b-169">指示器警示標題。</span><span class="sxs-lookup"><span data-stu-id="ec10b-169">Indicator alert title.</span></span> <span data-ttu-id="ec10b-170">**Required**</span><span class="sxs-lookup"><span data-stu-id="ec10b-170">**Required**</span></span>
<span data-ttu-id="ec10b-171">描述</span><span class="sxs-lookup"><span data-stu-id="ec10b-171">description</span></span> | <span data-ttu-id="ec10b-172">字串</span><span class="sxs-lookup"><span data-stu-id="ec10b-172">String</span></span> | <span data-ttu-id="ec10b-173">標記的描述。</span><span class="sxs-lookup"><span data-stu-id="ec10b-173">Description of the indicator.</span></span> <span data-ttu-id="ec10b-174">**Required**</span><span class="sxs-lookup"><span data-stu-id="ec10b-174">**Required**</span></span>
<span data-ttu-id="ec10b-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="ec10b-175">expirationTime</span></span> | <span data-ttu-id="ec10b-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ec10b-176">DateTimeOffset</span></span> | <span data-ttu-id="ec10b-177">指示器的到期時間。</span><span class="sxs-lookup"><span data-stu-id="ec10b-177">The expiration time of the indicator.</span></span> <span data-ttu-id="ec10b-178">**Optional**</span><span class="sxs-lookup"><span data-stu-id="ec10b-178">**Optional**</span></span>
<span data-ttu-id="ec10b-179">嚴重性</span><span class="sxs-lookup"><span data-stu-id="ec10b-179">severity</span></span> | <span data-ttu-id="ec10b-180">Enum</span><span class="sxs-lookup"><span data-stu-id="ec10b-180">Enum</span></span> | <span data-ttu-id="ec10b-181">指標的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="ec10b-181">The severity of the indicator.</span></span> <span data-ttu-id="ec10b-182">可能的值為：「資訊」、「低」、「中」和「高」。</span><span class="sxs-lookup"><span data-stu-id="ec10b-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="ec10b-183">**Optional**</span><span class="sxs-lookup"><span data-stu-id="ec10b-183">**Optional**</span></span>
<span data-ttu-id="ec10b-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="ec10b-184">recommendedActions</span></span> | <span data-ttu-id="ec10b-185">字串</span><span class="sxs-lookup"><span data-stu-id="ec10b-185">String</span></span> | <span data-ttu-id="ec10b-186">TI 指標警示建議的動作。</span><span class="sxs-lookup"><span data-stu-id="ec10b-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="ec10b-187">**Optional**</span><span class="sxs-lookup"><span data-stu-id="ec10b-187">**Optional**</span></span>
<span data-ttu-id="ec10b-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="ec10b-188">rbacGroupNames</span></span> | <span data-ttu-id="ec10b-189">字串</span><span class="sxs-lookup"><span data-stu-id="ec10b-189">String</span></span> | <span data-ttu-id="ec10b-190">標記將套用到的 RBAC 群組名稱的以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="ec10b-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="ec10b-191">**Optional**</span><span class="sxs-lookup"><span data-stu-id="ec10b-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="ec10b-192">回應</span><span class="sxs-lookup"><span data-stu-id="ec10b-192">Response</span></span>
- <span data-ttu-id="ec10b-193">如果成功，這個方法會傳回 200-OK 回應碼，以及回應內文中建立/更新的 [指示器](ti-indicator.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="ec10b-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="ec10b-194">若失敗：此方法會傳回 400-錯誤要求。</span><span class="sxs-lookup"><span data-stu-id="ec10b-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="ec10b-195">錯誤的要求通常會指出不正確的正文。</span><span class="sxs-lookup"><span data-stu-id="ec10b-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="ec10b-196">範例</span><span class="sxs-lookup"><span data-stu-id="ec10b-196">Example</span></span>

<span data-ttu-id="ec10b-197">**請求**</span><span class="sxs-lookup"><span data-stu-id="ec10b-197">**Request**</span></span>

<span data-ttu-id="ec10b-198">以下是要求的範例。</span><span class="sxs-lookup"><span data-stu-id="ec10b-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="ec10b-199">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec10b-199">Related topic</span></span>
- [<span data-ttu-id="ec10b-200">管理指示器</span><span class="sxs-lookup"><span data-stu-id="ec10b-200">Manage indicators</span></span>](manage-indicators.md)
