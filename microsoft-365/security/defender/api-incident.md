---
title: Microsoft 365Defender 事件 APIs 和事件資源類型
description: 深入瞭解 Microsoft 365 Defender 中的事件資源類型的方法和屬性
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888430"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="d04f8-104">Microsoft 365Defender 事件 API 和事件資源類型</span><span class="sxs-lookup"><span data-stu-id="d04f8-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d04f8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d04f8-105">**Applies to:**</span></span>

- [<span data-ttu-id="d04f8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d04f8-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="d04f8-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="d04f8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d04f8-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="d04f8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d04f8-109">[事件](incidents-overview.md)是協助描述攻擊的相關警示集合。</span><span class="sxs-lookup"><span data-stu-id="d04f8-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="d04f8-110">您組織中不同實體的事件會透過 Microsoft 365 Defender 自動匯總。</span><span class="sxs-lookup"><span data-stu-id="d04f8-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="d04f8-111">您可以使用事件 API，以程式設計方式存取您組織的事件及相關警示。</span><span class="sxs-lookup"><span data-stu-id="d04f8-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="d04f8-112">配額和資源配置</span><span class="sxs-lookup"><span data-stu-id="d04f8-112">Quotas and resource allocation</span></span>

<span data-ttu-id="d04f8-113">您最多可以每分鐘要求50個通話或每小時1500通話。</span><span class="sxs-lookup"><span data-stu-id="d04f8-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="d04f8-114">每個方法也有它自己的配額。</span><span class="sxs-lookup"><span data-stu-id="d04f8-114">Each method also has its own quotas.</span></span> <span data-ttu-id="d04f8-115">如需方法特定配額的詳細資訊，請參閱對應于您要使用之方法的各篇文章。</span><span class="sxs-lookup"><span data-stu-id="d04f8-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="d04f8-116">`429`HTTP 回應碼表示您已到達配額（按傳送的要求數目，或已分派的執行時間）。</span><span class="sxs-lookup"><span data-stu-id="d04f8-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="d04f8-117">回應內文會包含時間，直到您到達的配額會重設。</span><span class="sxs-lookup"><span data-stu-id="d04f8-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="d04f8-118">權限</span><span class="sxs-lookup"><span data-stu-id="d04f8-118">Permissions</span></span>

<span data-ttu-id="d04f8-119">事件 API 需要不同類型的許可權才能提供其所有方法。</span><span class="sxs-lookup"><span data-stu-id="d04f8-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="d04f8-120">如需有關所需許可權的詳細資訊，請參閱各自的方法的文章。</span><span class="sxs-lookup"><span data-stu-id="d04f8-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="d04f8-121">方法</span><span class="sxs-lookup"><span data-stu-id="d04f8-121">Methods</span></span>

<span data-ttu-id="d04f8-122">方法	</span><span class="sxs-lookup"><span data-stu-id="d04f8-122">Method</span></span> | <span data-ttu-id="d04f8-123">傳回類型</span><span class="sxs-lookup"><span data-stu-id="d04f8-123">Return Type</span></span> | <span data-ttu-id="d04f8-124">描述</span><span class="sxs-lookup"><span data-stu-id="d04f8-124">Description</span></span>
-|-|-
[<span data-ttu-id="d04f8-125">列出事件</span><span class="sxs-lookup"><span data-stu-id="d04f8-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="d04f8-126">[事件](api-incident.md) 清單</span><span class="sxs-lookup"><span data-stu-id="d04f8-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="d04f8-127">取得事件清單。</span><span class="sxs-lookup"><span data-stu-id="d04f8-127">Get a list of incidents.</span></span>
[<span data-ttu-id="d04f8-128">更新事件</span><span class="sxs-lookup"><span data-stu-id="d04f8-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="d04f8-129">事件</span><span class="sxs-lookup"><span data-stu-id="d04f8-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="d04f8-130">更新特定的事件。</span><span class="sxs-lookup"><span data-stu-id="d04f8-130">Update a specific incident.</span></span>
[<span data-ttu-id="d04f8-131">取得事件</span><span class="sxs-lookup"><span data-stu-id="d04f8-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="d04f8-132">事件</span><span class="sxs-lookup"><span data-stu-id="d04f8-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="d04f8-133">取得單一事件。</span><span class="sxs-lookup"><span data-stu-id="d04f8-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="d04f8-134">要求的主體、回應和範例</span><span class="sxs-lookup"><span data-stu-id="d04f8-134">Request body, response, and examples</span></span>

<span data-ttu-id="d04f8-135">如需如何建立要求或剖析回應的詳細資訊，以及實際範例，請參閱各自的方法文章。</span><span class="sxs-lookup"><span data-stu-id="d04f8-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="d04f8-136">一般屬性</span><span class="sxs-lookup"><span data-stu-id="d04f8-136">Common properties</span></span>

<span data-ttu-id="d04f8-137">屬性	</span><span class="sxs-lookup"><span data-stu-id="d04f8-137">Property</span></span> | <span data-ttu-id="d04f8-138">類型</span><span class="sxs-lookup"><span data-stu-id="d04f8-138">Type</span></span> | <span data-ttu-id="d04f8-139">描述</span><span class="sxs-lookup"><span data-stu-id="d04f8-139">Description</span></span>
-|-|-
<span data-ttu-id="d04f8-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="d04f8-140">incidentId</span></span> | <span data-ttu-id="d04f8-141">long</span><span class="sxs-lookup"><span data-stu-id="d04f8-141">long</span></span> | <span data-ttu-id="d04f8-142">事件唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d04f8-142">Incident unique ID.</span></span>
<span data-ttu-id="d04f8-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="d04f8-143">redirectIncidentId</span></span> | <span data-ttu-id="d04f8-144">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="d04f8-144">nullable long</span></span> | <span data-ttu-id="d04f8-145">目前的事件彙總至的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="d04f8-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="d04f8-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="d04f8-146">incidentName</span></span> | <span data-ttu-id="d04f8-147">string</span><span class="sxs-lookup"><span data-stu-id="d04f8-147">string</span></span> | <span data-ttu-id="d04f8-148">事件的名稱。</span><span class="sxs-lookup"><span data-stu-id="d04f8-148">The name of the Incident.</span></span>
<span data-ttu-id="d04f8-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="d04f8-149">createdTime</span></span> | <span data-ttu-id="d04f8-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d04f8-150">DateTimeOffset</span></span> | <span data-ttu-id="d04f8-151">在 UTC) 建立事件的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="d04f8-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="d04f8-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="d04f8-152">lastUpdateTime</span></span> | <span data-ttu-id="d04f8-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d04f8-153">DateTimeOffset</span></span> | <span data-ttu-id="d04f8-154">上次更新事件) 的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="d04f8-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="d04f8-155">分配</span><span class="sxs-lookup"><span data-stu-id="d04f8-155">assignedTo</span></span> | <span data-ttu-id="d04f8-156">string</span><span class="sxs-lookup"><span data-stu-id="d04f8-156">string</span></span> | <span data-ttu-id="d04f8-157">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="d04f8-157">Owner of the Incident.</span></span>
<span data-ttu-id="d04f8-158">嚴重性</span><span class="sxs-lookup"><span data-stu-id="d04f8-158">severity</span></span> | <span data-ttu-id="d04f8-159">Enum</span><span class="sxs-lookup"><span data-stu-id="d04f8-159">Enum</span></span> | <span data-ttu-id="d04f8-160">事件的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="d04f8-160">Severity of the Incident.</span></span> <span data-ttu-id="d04f8-161">可能的值為：、、、 ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` 、和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="d04f8-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="d04f8-162">地位</span><span class="sxs-lookup"><span data-stu-id="d04f8-162">status</span></span> | <span data-ttu-id="d04f8-163">Enum</span><span class="sxs-lookup"><span data-stu-id="d04f8-163">Enum</span></span> | <span data-ttu-id="d04f8-164">指定事件目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="d04f8-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="d04f8-165">可能的值為： ```Active``` 、 ```Resolved``` 、和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="d04f8-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="d04f8-166">分類</span><span class="sxs-lookup"><span data-stu-id="d04f8-166">classification</span></span> | <span data-ttu-id="d04f8-167">Enum</span><span class="sxs-lookup"><span data-stu-id="d04f8-167">Enum</span></span> | <span data-ttu-id="d04f8-168">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="d04f8-168">Specification of the incident.</span></span> <span data-ttu-id="d04f8-169">可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。</span><span class="sxs-lookup"><span data-stu-id="d04f8-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="d04f8-170">測定</span><span class="sxs-lookup"><span data-stu-id="d04f8-170">determination</span></span> | <span data-ttu-id="d04f8-171">Enum</span><span class="sxs-lookup"><span data-stu-id="d04f8-171">Enum</span></span> | <span data-ttu-id="d04f8-172">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="d04f8-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="d04f8-173">可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="d04f8-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="d04f8-174">標籤</span><span class="sxs-lookup"><span data-stu-id="d04f8-174">tags</span></span> | <span data-ttu-id="d04f8-175">字串清單</span><span class="sxs-lookup"><span data-stu-id="d04f8-175">string List</span></span> | <span data-ttu-id="d04f8-176">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="d04f8-176">List of Incident tags.</span></span>
<span data-ttu-id="d04f8-177">註解</span><span class="sxs-lookup"><span data-stu-id="d04f8-177">comments</span></span> | <span data-ttu-id="d04f8-178">事件批註清單</span><span class="sxs-lookup"><span data-stu-id="d04f8-178">List of incident comments</span></span> | <span data-ttu-id="d04f8-179">事件 Comment 物件包含：批註字串、createdBy 字串及 createTime date time。</span><span class="sxs-lookup"><span data-stu-id="d04f8-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="d04f8-180">警報</span><span class="sxs-lookup"><span data-stu-id="d04f8-180">alerts</span></span> | <span data-ttu-id="d04f8-181">警示清單</span><span class="sxs-lookup"><span data-stu-id="d04f8-181">Alert List</span></span> | <span data-ttu-id="d04f8-182">相關警示的清單。</span><span class="sxs-lookup"><span data-stu-id="d04f8-182">List of related alerts.</span></span> <span data-ttu-id="d04f8-183">請參閱 [List 事件](api-list-incidents.md) API 檔中的範例。</span><span class="sxs-lookup"><span data-stu-id="d04f8-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d04f8-184">相關文章</span><span class="sxs-lookup"><span data-stu-id="d04f8-184">Related articles</span></span>

- [<span data-ttu-id="d04f8-185">Microsoft 365Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="d04f8-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d04f8-186">事件概觀</span><span class="sxs-lookup"><span data-stu-id="d04f8-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d04f8-187">列出事件 API</span><span class="sxs-lookup"><span data-stu-id="d04f8-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="d04f8-188">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="d04f8-188">Update incident API</span></span>](api-update-incidents.md)
