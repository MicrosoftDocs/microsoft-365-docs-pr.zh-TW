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
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730927"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="61416-104">Microsoft 365Defender 事件 API 和事件資源類型</span><span class="sxs-lookup"><span data-stu-id="61416-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="61416-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="61416-105">**Applies to:**</span></span>

- [<span data-ttu-id="61416-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61416-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="61416-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="61416-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="61416-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="61416-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="61416-109">[事件](incidents-overview.md)是協助描述攻擊的相關警示集合。</span><span class="sxs-lookup"><span data-stu-id="61416-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="61416-110">您組織中不同實體的事件會透過 Microsoft 365 Defender 自動匯總。</span><span class="sxs-lookup"><span data-stu-id="61416-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="61416-111">您可以使用事件 API，以程式設計方式存取您組織的事件及相關警示。</span><span class="sxs-lookup"><span data-stu-id="61416-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="61416-112">配額和資源配置</span><span class="sxs-lookup"><span data-stu-id="61416-112">Quotas and resource allocation</span></span>

<span data-ttu-id="61416-113">您最多可以每分鐘要求50個通話或每小時1500通話。</span><span class="sxs-lookup"><span data-stu-id="61416-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="61416-114">每個方法也有它自己的配額。</span><span class="sxs-lookup"><span data-stu-id="61416-114">Each method also has its own quotas.</span></span> <span data-ttu-id="61416-115">如需方法特定配額的詳細資訊，請參閱對應于您要使用之方法的各篇文章。</span><span class="sxs-lookup"><span data-stu-id="61416-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="61416-116">`429`HTTP 回應碼表示您已到達配額（按傳送的要求數目，或已分派的執行時間）。</span><span class="sxs-lookup"><span data-stu-id="61416-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="61416-117">回應內文會包含時間，直到您到達的配額會重設。</span><span class="sxs-lookup"><span data-stu-id="61416-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="61416-118">權限</span><span class="sxs-lookup"><span data-stu-id="61416-118">Permissions</span></span>

<span data-ttu-id="61416-119">事件 API 需要不同類型的許可權才能提供其所有方法。</span><span class="sxs-lookup"><span data-stu-id="61416-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="61416-120">如需有關所需許可權的詳細資訊，請參閱各自的方法的文章。</span><span class="sxs-lookup"><span data-stu-id="61416-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="61416-121">方法</span><span class="sxs-lookup"><span data-stu-id="61416-121">Methods</span></span>

<span data-ttu-id="61416-122">方法	</span><span class="sxs-lookup"><span data-stu-id="61416-122">Method</span></span> | <span data-ttu-id="61416-123">傳回類型</span><span class="sxs-lookup"><span data-stu-id="61416-123">Return Type</span></span> | <span data-ttu-id="61416-124">描述</span><span class="sxs-lookup"><span data-stu-id="61416-124">Description</span></span>
-|-|-
[<span data-ttu-id="61416-125">列出事件</span><span class="sxs-lookup"><span data-stu-id="61416-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="61416-126">[事件](api-incident.md) 清單</span><span class="sxs-lookup"><span data-stu-id="61416-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="61416-127">取得事件清單。</span><span class="sxs-lookup"><span data-stu-id="61416-127">Get a list of incidents.</span></span>
[<span data-ttu-id="61416-128">更新事件</span><span class="sxs-lookup"><span data-stu-id="61416-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="61416-129">事件</span><span class="sxs-lookup"><span data-stu-id="61416-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="61416-130">更新特定的事件。</span><span class="sxs-lookup"><span data-stu-id="61416-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="61416-131">要求的主體、回應和範例</span><span class="sxs-lookup"><span data-stu-id="61416-131">Request body, response, and examples</span></span>

<span data-ttu-id="61416-132">如需如何建立要求或剖析回應的詳細資訊，以及實際範例，請參閱各自的方法文章。</span><span class="sxs-lookup"><span data-stu-id="61416-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="61416-133">一般屬性</span><span class="sxs-lookup"><span data-stu-id="61416-133">Common properties</span></span>

<span data-ttu-id="61416-134">屬性	</span><span class="sxs-lookup"><span data-stu-id="61416-134">Property</span></span> | <span data-ttu-id="61416-135">類型</span><span class="sxs-lookup"><span data-stu-id="61416-135">Type</span></span> | <span data-ttu-id="61416-136">描述</span><span class="sxs-lookup"><span data-stu-id="61416-136">Description</span></span>
-|-|-
<span data-ttu-id="61416-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="61416-137">incidentId</span></span> | <span data-ttu-id="61416-138">long</span><span class="sxs-lookup"><span data-stu-id="61416-138">long</span></span> | <span data-ttu-id="61416-139">事件唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="61416-139">Incident unique ID.</span></span>
<span data-ttu-id="61416-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="61416-140">redirectIncidentId</span></span> | <span data-ttu-id="61416-141">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="61416-141">nullable long</span></span> | <span data-ttu-id="61416-142">目前的事件彙總至的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="61416-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="61416-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="61416-143">incidentName</span></span> | <span data-ttu-id="61416-144">string</span><span class="sxs-lookup"><span data-stu-id="61416-144">string</span></span> | <span data-ttu-id="61416-145">事件的名稱。</span><span class="sxs-lookup"><span data-stu-id="61416-145">The name of the Incident.</span></span>
<span data-ttu-id="61416-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="61416-146">createdTime</span></span> | <span data-ttu-id="61416-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="61416-147">DateTimeOffset</span></span> | <span data-ttu-id="61416-148">在 UTC) 建立事件的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="61416-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="61416-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="61416-149">lastUpdateTime</span></span> | <span data-ttu-id="61416-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="61416-150">DateTimeOffset</span></span> | <span data-ttu-id="61416-151">上次更新事件) 的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="61416-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="61416-152">分配</span><span class="sxs-lookup"><span data-stu-id="61416-152">assignedTo</span></span> | <span data-ttu-id="61416-153">string</span><span class="sxs-lookup"><span data-stu-id="61416-153">string</span></span> | <span data-ttu-id="61416-154">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="61416-154">Owner of the Incident.</span></span>
<span data-ttu-id="61416-155">嚴重性</span><span class="sxs-lookup"><span data-stu-id="61416-155">severity</span></span> | <span data-ttu-id="61416-156">Enum</span><span class="sxs-lookup"><span data-stu-id="61416-156">Enum</span></span> | <span data-ttu-id="61416-157">事件的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="61416-157">Severity of the Incident.</span></span> <span data-ttu-id="61416-158">可能的值為：、、、 ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` 、和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="61416-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="61416-159">地位</span><span class="sxs-lookup"><span data-stu-id="61416-159">status</span></span> | <span data-ttu-id="61416-160">Enum</span><span class="sxs-lookup"><span data-stu-id="61416-160">Enum</span></span> | <span data-ttu-id="61416-161">指定事件目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="61416-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="61416-162">可能的值為： ```Active``` 、 ```Resolved``` 、和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="61416-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="61416-163">分類</span><span class="sxs-lookup"><span data-stu-id="61416-163">classification</span></span> | <span data-ttu-id="61416-164">Enum</span><span class="sxs-lookup"><span data-stu-id="61416-164">Enum</span></span> | <span data-ttu-id="61416-165">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="61416-165">Specification of the incident.</span></span> <span data-ttu-id="61416-166">可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。</span><span class="sxs-lookup"><span data-stu-id="61416-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="61416-167">測定</span><span class="sxs-lookup"><span data-stu-id="61416-167">determination</span></span> | <span data-ttu-id="61416-168">Enum</span><span class="sxs-lookup"><span data-stu-id="61416-168">Enum</span></span> | <span data-ttu-id="61416-169">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="61416-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="61416-170">可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="61416-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="61416-171">標籤</span><span class="sxs-lookup"><span data-stu-id="61416-171">tags</span></span> | <span data-ttu-id="61416-172">字串清單</span><span class="sxs-lookup"><span data-stu-id="61416-172">string List</span></span> | <span data-ttu-id="61416-173">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="61416-173">List of Incident tags.</span></span>
<span data-ttu-id="61416-174">註解</span><span class="sxs-lookup"><span data-stu-id="61416-174">comments</span></span> | <span data-ttu-id="61416-175">事件批註清單</span><span class="sxs-lookup"><span data-stu-id="61416-175">List of incident comments</span></span> | <span data-ttu-id="61416-176">事件 Comment 物件包含：批註字串、createdBy 字串及 createTime date time。</span><span class="sxs-lookup"><span data-stu-id="61416-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="61416-177">警報</span><span class="sxs-lookup"><span data-stu-id="61416-177">alerts</span></span> | <span data-ttu-id="61416-178">警示清單</span><span class="sxs-lookup"><span data-stu-id="61416-178">Alert List</span></span> | <span data-ttu-id="61416-179">相關警示的清單。</span><span class="sxs-lookup"><span data-stu-id="61416-179">List of related alerts.</span></span> <span data-ttu-id="61416-180">請參閱 [List 事件](api-list-incidents.md) API 檔中的範例。</span><span class="sxs-lookup"><span data-stu-id="61416-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="61416-181">相關文章</span><span class="sxs-lookup"><span data-stu-id="61416-181">Related articles</span></span>

- [<span data-ttu-id="61416-182">Microsoft 365Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="61416-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="61416-183">事件概觀</span><span class="sxs-lookup"><span data-stu-id="61416-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="61416-184">列出事件 API</span><span class="sxs-lookup"><span data-stu-id="61416-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="61416-185">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="61416-185">Update incident API</span></span>](api-update-incidents.md)
