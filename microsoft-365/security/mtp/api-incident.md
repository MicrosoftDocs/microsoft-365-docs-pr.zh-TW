---
title: Microsoft 365 Defender 事件 API 和事件資源類型
description: 瞭解 Microsoft 365 Defender 中事件資源類型的方法和屬性
keywords: 事件、事件、api
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
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928351"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="019be-104">Microsoft 365 Defender 事件 API 和事件資源類型</span><span class="sxs-lookup"><span data-stu-id="019be-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="019be-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="019be-105">**Applies to:**</span></span>

- <span data-ttu-id="019be-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="019be-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="019be-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="019be-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="019be-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="019be-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="019be-109">事件 [是](incidents-overview.md) 相關警示的集合，可協助描述攻擊。</span><span class="sxs-lookup"><span data-stu-id="019be-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="019be-110">Microsoft 365 Defender 會自動匯總貴組織中不同實體的事件。</span><span class="sxs-lookup"><span data-stu-id="019be-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="019be-111">您可以使用事件 API 以程式方式存取貴組織的事件和相關警示。</span><span class="sxs-lookup"><span data-stu-id="019be-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="019be-112">配額和資源配置</span><span class="sxs-lookup"><span data-stu-id="019be-112">Quotas and resource allocation</span></span>

<span data-ttu-id="019be-113">您每分鐘可要求多達 50 個通話或每小時 1500 個通話。</span><span class="sxs-lookup"><span data-stu-id="019be-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="019be-114">每種方法也有自己的配額。</span><span class="sxs-lookup"><span data-stu-id="019be-114">Each method also has its own quotas.</span></span> <span data-ttu-id="019be-115">有關特定方法配額詳細資訊，請參閱您想要使用之方法的各自文章。</span><span class="sxs-lookup"><span data-stu-id="019be-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="019be-116">HTTP 回應碼表示您已達到配額，可以是已傳送的要求數，或是已分配 `429` 執行時間。</span><span class="sxs-lookup"><span data-stu-id="019be-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="019be-117">回復內體會包含重設您達到的配額之前的時間。</span><span class="sxs-lookup"><span data-stu-id="019be-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="019be-118">權限</span><span class="sxs-lookup"><span data-stu-id="019be-118">Permissions</span></span>

<span data-ttu-id="019be-119">事件 API 會針對每個方法要求不同類型的許可權。</span><span class="sxs-lookup"><span data-stu-id="019be-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="019be-120">有關所需許可權詳細資訊，請參閱各自方法的文章。</span><span class="sxs-lookup"><span data-stu-id="019be-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="019be-121">方法</span><span class="sxs-lookup"><span data-stu-id="019be-121">Methods</span></span>

<span data-ttu-id="019be-122">方法	</span><span class="sxs-lookup"><span data-stu-id="019be-122">Method</span></span> | <span data-ttu-id="019be-123">傳回類型</span><span class="sxs-lookup"><span data-stu-id="019be-123">Return Type</span></span> | <span data-ttu-id="019be-124">描述</span><span class="sxs-lookup"><span data-stu-id="019be-124">Description</span></span>
-|-|-
[<span data-ttu-id="019be-125">列出事件</span><span class="sxs-lookup"><span data-stu-id="019be-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="019be-126">[事件](api-incident.md) 清單</span><span class="sxs-lookup"><span data-stu-id="019be-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="019be-127">取得事件清單。</span><span class="sxs-lookup"><span data-stu-id="019be-127">Get a list of incidents.</span></span>
[<span data-ttu-id="019be-128">更新事件</span><span class="sxs-lookup"><span data-stu-id="019be-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="019be-129">事件</span><span class="sxs-lookup"><span data-stu-id="019be-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="019be-130">更新特定事件。</span><span class="sxs-lookup"><span data-stu-id="019be-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="019be-131">要求本文、回應和範例</span><span class="sxs-lookup"><span data-stu-id="019be-131">Request body, response, and examples</span></span>

<span data-ttu-id="019be-132">請參閱其各自的方法文章，以瞭解如何建構要求或剖析回應的詳細資訊，以及實用範例。</span><span class="sxs-lookup"><span data-stu-id="019be-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="019be-133">一般屬性</span><span class="sxs-lookup"><span data-stu-id="019be-133">Common properties</span></span>

<span data-ttu-id="019be-134">屬性	</span><span class="sxs-lookup"><span data-stu-id="019be-134">Property</span></span> | <span data-ttu-id="019be-135">類型</span><span class="sxs-lookup"><span data-stu-id="019be-135">Type</span></span> | <span data-ttu-id="019be-136">說明</span><span class="sxs-lookup"><span data-stu-id="019be-136">Description</span></span>
-|-|-
<span data-ttu-id="019be-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="019be-137">incidentId</span></span> | <span data-ttu-id="019be-138">long</span><span class="sxs-lookup"><span data-stu-id="019be-138">long</span></span> | <span data-ttu-id="019be-139">事件唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="019be-139">Incident unique ID.</span></span>
<span data-ttu-id="019be-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="019be-140">redirectIncidentId</span></span> | <span data-ttu-id="019be-141">可 Null long</span><span class="sxs-lookup"><span data-stu-id="019be-141">nullable long</span></span> | <span data-ttu-id="019be-142">合併目前事件的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="019be-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="019be-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="019be-143">incidentName</span></span> | <span data-ttu-id="019be-144">string</span><span class="sxs-lookup"><span data-stu-id="019be-144">string</span></span> | <span data-ttu-id="019be-145">事件的名稱。</span><span class="sxs-lookup"><span data-stu-id="019be-145">The name of the Incident.</span></span>
<span data-ttu-id="019be-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="019be-146">createdTime</span></span> | <span data-ttu-id="019be-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="019be-147">DateTimeOffset</span></span> | <span data-ttu-id="019be-148">事件建立後 (以 UTC) 日期及時間。</span><span class="sxs-lookup"><span data-stu-id="019be-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="019be-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="019be-149">lastUpdateTime</span></span> | <span data-ttu-id="019be-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="019be-150">DateTimeOffset</span></span> | <span data-ttu-id="019be-151">事件上次更新的 (時間) 以 UTC 表示。</span><span class="sxs-lookup"><span data-stu-id="019be-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="019be-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="019be-152">assignedTo</span></span> | <span data-ttu-id="019be-153">string</span><span class="sxs-lookup"><span data-stu-id="019be-153">string</span></span> | <span data-ttu-id="019be-154">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="019be-154">Owner of the Incident.</span></span>
<span data-ttu-id="019be-155">嚴重性</span><span class="sxs-lookup"><span data-stu-id="019be-155">severity</span></span> | <span data-ttu-id="019be-156">Enum</span><span class="sxs-lookup"><span data-stu-id="019be-156">Enum</span></span> | <span data-ttu-id="019be-157">事件的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="019be-157">Severity of the Incident.</span></span> <span data-ttu-id="019be-158">可能的值有 ```UnSpecified``` ：、 ```Informational``` ```Low``` ```Medium``` 及 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="019be-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="019be-159">地位</span><span class="sxs-lookup"><span data-stu-id="019be-159">status</span></span> | <span data-ttu-id="019be-160">Enum</span><span class="sxs-lookup"><span data-stu-id="019be-160">Enum</span></span> | <span data-ttu-id="019be-161">指定事件目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="019be-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="019be-162">可能的值有：、 ```Active``` ```Resolved``` 及 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="019be-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="019be-163">分類</span><span class="sxs-lookup"><span data-stu-id="019be-163">classification</span></span> | <span data-ttu-id="019be-164">Enum</span><span class="sxs-lookup"><span data-stu-id="019be-164">Enum</span></span> | <span data-ttu-id="019be-165">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="019be-165">Specification of the incident.</span></span> <span data-ttu-id="019be-166">可能的值有 ```Unknown``` ```FalsePositive``` ```TruePositive``` ：、、。</span><span class="sxs-lookup"><span data-stu-id="019be-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="019be-167">測定</span><span class="sxs-lookup"><span data-stu-id="019be-167">determination</span></span> | <span data-ttu-id="019be-168">Enum</span><span class="sxs-lookup"><span data-stu-id="019be-168">Enum</span></span> | <span data-ttu-id="019be-169">指定事件判定。</span><span class="sxs-lookup"><span data-stu-id="019be-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="019be-170">可能的值有 ```NotAvailable``` ：、 ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="019be-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="019be-171">標籤</span><span class="sxs-lookup"><span data-stu-id="019be-171">tags</span></span> | <span data-ttu-id="019be-172">字串清單</span><span class="sxs-lookup"><span data-stu-id="019be-172">string List</span></span> | <span data-ttu-id="019be-173">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="019be-173">List of Incident tags.</span></span>
<span data-ttu-id="019be-174">警報</span><span class="sxs-lookup"><span data-stu-id="019be-174">alerts</span></span> | <span data-ttu-id="019be-175">警示清單</span><span class="sxs-lookup"><span data-stu-id="019be-175">Alert List</span></span> | <span data-ttu-id="019be-176">相關警示清單。</span><span class="sxs-lookup"><span data-stu-id="019be-176">List of related alerts.</span></span> <span data-ttu-id="019be-177">請參閱清單事件 API [檔的](api-list-incidents.md) 範例。</span><span class="sxs-lookup"><span data-stu-id="019be-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="019be-178">相關文章</span><span class="sxs-lookup"><span data-stu-id="019be-178">Related articles</span></span>

- [<span data-ttu-id="019be-179">Microsoft 365 Defender API 概觀</span><span class="sxs-lookup"><span data-stu-id="019be-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="019be-180">事件概觀</span><span class="sxs-lookup"><span data-stu-id="019be-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="019be-181">清單事件 API</span><span class="sxs-lookup"><span data-stu-id="019be-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="019be-182">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="019be-182">Update incident API</span></span>](api-update-incidents.md)
