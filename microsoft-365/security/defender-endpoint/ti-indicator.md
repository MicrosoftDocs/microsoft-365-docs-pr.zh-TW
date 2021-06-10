---
title: 指示器資源類型
description: 使用 Microsoft Defender for Endpoint 指定實體詳細資料及定義指示器的到期日。
keywords: api、支援的 api、get、TiIndicator、指示器、最近
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
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771378"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="8a70f-104">指示器資源類型</span><span class="sxs-lookup"><span data-stu-id="8a70f-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a70f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8a70f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a70f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8a70f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8a70f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a70f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8a70f-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="8a70f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8a70f-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8a70f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="8a70f-110">請參閱入口網站中的對應 [指示器頁面](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) 。</span><span class="sxs-lookup"><span data-stu-id="8a70f-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="8a70f-111">方法</span><span class="sxs-lookup"><span data-stu-id="8a70f-111">Method</span></span>|<span data-ttu-id="8a70f-112">傳回類型</span><span class="sxs-lookup"><span data-stu-id="8a70f-112">Return Type</span></span> |<span data-ttu-id="8a70f-113">描述</span><span class="sxs-lookup"><span data-stu-id="8a70f-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="8a70f-114">清單指示器</span><span class="sxs-lookup"><span data-stu-id="8a70f-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="8a70f-115">[指標](ti-indicator.md) 收集</span><span class="sxs-lookup"><span data-stu-id="8a70f-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="8a70f-116">清單 [指示器](ti-indicator.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="8a70f-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="8a70f-117">提交指示器</span><span class="sxs-lookup"><span data-stu-id="8a70f-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="8a70f-118">指標</span><span class="sxs-lookup"><span data-stu-id="8a70f-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="8a70f-119">提交或更新 [指示器](ti-indicator.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="8a70f-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="8a70f-120">匯入指標</span><span class="sxs-lookup"><span data-stu-id="8a70f-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="8a70f-121">[指標](ti-indicator.md) 收集</span><span class="sxs-lookup"><span data-stu-id="8a70f-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="8a70f-122">提交或更新 [指示器](ti-indicator.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="8a70f-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="8a70f-123">刪除指示器</span><span class="sxs-lookup"><span data-stu-id="8a70f-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="8a70f-124">無內容</span><span class="sxs-lookup"><span data-stu-id="8a70f-124">No Content</span></span> | <span data-ttu-id="8a70f-125">會刪除 [指示器](ti-indicator.md) 實體。</span><span class="sxs-lookup"><span data-stu-id="8a70f-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="8a70f-126">屬性</span><span class="sxs-lookup"><span data-stu-id="8a70f-126">Properties</span></span>
<span data-ttu-id="8a70f-127">屬性	</span><span class="sxs-lookup"><span data-stu-id="8a70f-127">Property</span></span> |  <span data-ttu-id="8a70f-128">類型</span><span class="sxs-lookup"><span data-stu-id="8a70f-128">Type</span></span>    |   <span data-ttu-id="8a70f-129">描述</span><span class="sxs-lookup"><span data-stu-id="8a70f-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="8a70f-130">id</span><span class="sxs-lookup"><span data-stu-id="8a70f-130">id</span></span> | <span data-ttu-id="8a70f-131">字串</span><span class="sxs-lookup"><span data-stu-id="8a70f-131">String</span></span> | <span data-ttu-id="8a70f-132">[指示器](ti-indicator.md)實體的身分識別。</span><span class="sxs-lookup"><span data-stu-id="8a70f-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="8a70f-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="8a70f-133">indicatorValue</span></span> | <span data-ttu-id="8a70f-134">字串</span><span class="sxs-lookup"><span data-stu-id="8a70f-134">String</span></span> | <span data-ttu-id="8a70f-135">[指標](ti-indicator.md)的值。</span><span class="sxs-lookup"><span data-stu-id="8a70f-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="8a70f-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="8a70f-136">indicatorType</span></span> | <span data-ttu-id="8a70f-137">Enum</span><span class="sxs-lookup"><span data-stu-id="8a70f-137">Enum</span></span> | <span data-ttu-id="8a70f-138">指標的類型。</span><span class="sxs-lookup"><span data-stu-id="8a70f-138">Type of the indicator.</span></span> <span data-ttu-id="8a70f-139">可能的值為： "FileSha1"、"FileSha256"、"IpAddress"、"DomainName" 和 "Url"。</span><span class="sxs-lookup"><span data-stu-id="8a70f-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="8a70f-140">應用程式</span><span class="sxs-lookup"><span data-stu-id="8a70f-140">application</span></span> | <span data-ttu-id="8a70f-141">字串</span><span class="sxs-lookup"><span data-stu-id="8a70f-141">String</span></span> | <span data-ttu-id="8a70f-142">與指示器相關聯的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8a70f-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="8a70f-143">action</span><span class="sxs-lookup"><span data-stu-id="8a70f-143">action</span></span> | <span data-ttu-id="8a70f-144">Enum</span><span class="sxs-lookup"><span data-stu-id="8a70f-144">Enum</span></span> | <span data-ttu-id="8a70f-145">將在組織中探索指示器時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="8a70f-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="8a70f-146">可能的值為： "Alert"、"AlertAndBlock" 和 "允許"。</span><span class="sxs-lookup"><span data-stu-id="8a70f-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="8a70f-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="8a70f-147">sourceType</span></span> | <span data-ttu-id="8a70f-148">Enum</span><span class="sxs-lookup"><span data-stu-id="8a70f-148">Enum</span></span> | <span data-ttu-id="8a70f-149">若使用者 (所建立的指標，則為 "user"，例如，從入口網站) 「AadApp」，以防它透過 API 使用自動應用程式提交。</span><span class="sxs-lookup"><span data-stu-id="8a70f-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="8a70f-150">源</span><span class="sxs-lookup"><span data-stu-id="8a70f-150">source</span></span> | <span data-ttu-id="8a70f-151">string</span><span class="sxs-lookup"><span data-stu-id="8a70f-151">string</span></span> | <span data-ttu-id="8a70f-152">提交指標的使用者/應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="8a70f-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="8a70f-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="8a70f-153">createdBy</span></span> | <span data-ttu-id="8a70f-154">字串</span><span class="sxs-lookup"><span data-stu-id="8a70f-154">String</span></span> | <span data-ttu-id="8a70f-155">提交指標之使用者/應用程式的唯一身分識別。</span><span class="sxs-lookup"><span data-stu-id="8a70f-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="8a70f-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8a70f-156">lastUpdatedBy</span></span> | <span data-ttu-id="8a70f-157">字串</span><span class="sxs-lookup"><span data-stu-id="8a70f-157">String</span></span> | <span data-ttu-id="8a70f-158">上次更新標記的使用者/應用程式的身分識別。</span><span class="sxs-lookup"><span data-stu-id="8a70f-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="8a70f-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="8a70f-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="8a70f-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8a70f-160">DateTimeOffset</span></span> | <span data-ttu-id="8a70f-161">建立指示器的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="8a70f-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="8a70f-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="8a70f-162">expirationTime</span></span> | <span data-ttu-id="8a70f-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8a70f-163">DateTimeOffset</span></span> | <span data-ttu-id="8a70f-164">指示器的到期時間。</span><span class="sxs-lookup"><span data-stu-id="8a70f-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="8a70f-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="8a70f-165">lastUpdateTime</span></span> | <span data-ttu-id="8a70f-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8a70f-166">DateTimeOffset</span></span> | <span data-ttu-id="8a70f-167">上次更新指示器的時間。</span><span class="sxs-lookup"><span data-stu-id="8a70f-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="8a70f-168">嚴重性</span><span class="sxs-lookup"><span data-stu-id="8a70f-168">severity</span></span> | <span data-ttu-id="8a70f-169">Enum</span><span class="sxs-lookup"><span data-stu-id="8a70f-169">Enum</span></span> | <span data-ttu-id="8a70f-170">指標的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="8a70f-170">The severity of the indicator.</span></span> <span data-ttu-id="8a70f-171">可能的值為：「資訊」、「低」、「中」和「高」。</span><span class="sxs-lookup"><span data-stu-id="8a70f-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="8a70f-172">標題</span><span class="sxs-lookup"><span data-stu-id="8a70f-172">title</span></span> | <span data-ttu-id="8a70f-173">String</span><span class="sxs-lookup"><span data-stu-id="8a70f-173">String</span></span> | <span data-ttu-id="8a70f-174">指示器標題。</span><span class="sxs-lookup"><span data-stu-id="8a70f-174">Indicator title.</span></span>
<span data-ttu-id="8a70f-175">描述</span><span class="sxs-lookup"><span data-stu-id="8a70f-175">description</span></span> | <span data-ttu-id="8a70f-176">字串</span><span class="sxs-lookup"><span data-stu-id="8a70f-176">String</span></span> | <span data-ttu-id="8a70f-177">標記的描述。</span><span class="sxs-lookup"><span data-stu-id="8a70f-177">Description of the indicator.</span></span>
<span data-ttu-id="8a70f-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="8a70f-178">recommendedActions</span></span> | <span data-ttu-id="8a70f-179">字串</span><span class="sxs-lookup"><span data-stu-id="8a70f-179">String</span></span> | <span data-ttu-id="8a70f-180">標記的建議動作。</span><span class="sxs-lookup"><span data-stu-id="8a70f-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="8a70f-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="8a70f-181">rbacGroupNames</span></span> | <span data-ttu-id="8a70f-182">字串清單</span><span class="sxs-lookup"><span data-stu-id="8a70f-182">List of strings</span></span> | <span data-ttu-id="8a70f-183">RBAC 設備群組名稱，其標記是公開和作用中的。</span><span class="sxs-lookup"><span data-stu-id="8a70f-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="8a70f-184">空清單，以防它公開至所有裝置。</span><span class="sxs-lookup"><span data-stu-id="8a70f-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="8a70f-185">Json 標記法</span><span class="sxs-lookup"><span data-stu-id="8a70f-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
