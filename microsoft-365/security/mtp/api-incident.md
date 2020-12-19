---
title: Microsoft 365 Defender 事件 APIs 和事件資源類型
description: 深入瞭解 Microsoft 365 Defender 中的事件資源類型的方法和屬性
keywords: 事件、事件、api
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719331"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="36d91-104">Microsoft 365 Defender 事件 API 和事件資源類型</span><span class="sxs-lookup"><span data-stu-id="36d91-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="36d91-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="36d91-105">**Applies to:**</span></span>

- <span data-ttu-id="36d91-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36d91-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36d91-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="36d91-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="36d91-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="36d91-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="36d91-109">[事件](incidents-overview.md)是協助描述攻擊的相關警示集合。</span><span class="sxs-lookup"><span data-stu-id="36d91-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="36d91-110">您組織中不同實體的事件會由 Microsoft 365 Defender 自動匯總。</span><span class="sxs-lookup"><span data-stu-id="36d91-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="36d91-111">您可以使用事件 API，以程式設計方式存取您組織的事件及相關警示。</span><span class="sxs-lookup"><span data-stu-id="36d91-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="36d91-112">配額和資源配置</span><span class="sxs-lookup"><span data-stu-id="36d91-112">Quotas and resource allocation</span></span>

<span data-ttu-id="36d91-113">您最多可以每分鐘要求50個通話或每小時1500通話。</span><span class="sxs-lookup"><span data-stu-id="36d91-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="36d91-114">每個方法也有它自己的配額。</span><span class="sxs-lookup"><span data-stu-id="36d91-114">Each method also has its own quotas.</span></span> <span data-ttu-id="36d91-115">如需方法特定配額的詳細資訊，請參閱對應于您要使用之方法的各篇文章。</span><span class="sxs-lookup"><span data-stu-id="36d91-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="36d91-116">`429`HTTP 回應碼表示您已到達配額（按傳送的要求數目，或已分派的執行時間）。</span><span class="sxs-lookup"><span data-stu-id="36d91-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="36d91-117">回應內文會包含時間，直到您到達的配額會重設。</span><span class="sxs-lookup"><span data-stu-id="36d91-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="36d91-118">權限</span><span class="sxs-lookup"><span data-stu-id="36d91-118">Permissions</span></span>

<span data-ttu-id="36d91-119">事件 API 需要不同類型的許可權才能提供其所有方法。</span><span class="sxs-lookup"><span data-stu-id="36d91-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="36d91-120">如需有關所需許可權的詳細資訊，請參閱各自的方法的文章。</span><span class="sxs-lookup"><span data-stu-id="36d91-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="36d91-121">方法</span><span class="sxs-lookup"><span data-stu-id="36d91-121">Methods</span></span>

<span data-ttu-id="36d91-122">方法	</span><span class="sxs-lookup"><span data-stu-id="36d91-122">Method</span></span> | <span data-ttu-id="36d91-123">傳回類型</span><span class="sxs-lookup"><span data-stu-id="36d91-123">Return Type</span></span> | <span data-ttu-id="36d91-124">描述</span><span class="sxs-lookup"><span data-stu-id="36d91-124">Description</span></span>
-|-|-
[<span data-ttu-id="36d91-125">列出事件</span><span class="sxs-lookup"><span data-stu-id="36d91-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="36d91-126">[事件](api-incident.md) 清單</span><span class="sxs-lookup"><span data-stu-id="36d91-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="36d91-127">取得事件清單。</span><span class="sxs-lookup"><span data-stu-id="36d91-127">Get a list of incidents.</span></span>
[<span data-ttu-id="36d91-128">更新事件</span><span class="sxs-lookup"><span data-stu-id="36d91-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="36d91-129">事件</span><span class="sxs-lookup"><span data-stu-id="36d91-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="36d91-130">更新特定的事件。</span><span class="sxs-lookup"><span data-stu-id="36d91-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="36d91-131">要求的主體、回應和範例</span><span class="sxs-lookup"><span data-stu-id="36d91-131">Request body, response, and examples</span></span>

<span data-ttu-id="36d91-132">如需如何建立要求或剖析回應的詳細資訊，以及實際範例，請參閱各自的方法文章。</span><span class="sxs-lookup"><span data-stu-id="36d91-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="36d91-133">一般屬性</span><span class="sxs-lookup"><span data-stu-id="36d91-133">Common properties</span></span>

<span data-ttu-id="36d91-134">屬性	</span><span class="sxs-lookup"><span data-stu-id="36d91-134">Property</span></span> | <span data-ttu-id="36d91-135">類型</span><span class="sxs-lookup"><span data-stu-id="36d91-135">Type</span></span> | <span data-ttu-id="36d91-136">描述</span><span class="sxs-lookup"><span data-stu-id="36d91-136">Description</span></span>
-|-|-
<span data-ttu-id="36d91-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="36d91-137">incidentId</span></span> | <span data-ttu-id="36d91-138">long</span><span class="sxs-lookup"><span data-stu-id="36d91-138">long</span></span> | <span data-ttu-id="36d91-139">事件唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="36d91-139">Incident unique ID.</span></span>
<span data-ttu-id="36d91-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="36d91-140">redirectIncidentId</span></span> | <span data-ttu-id="36d91-141">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="36d91-141">nullable long</span></span> | <span data-ttu-id="36d91-142">目前的事件彙總至的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="36d91-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="36d91-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="36d91-143">incidentName</span></span> | <span data-ttu-id="36d91-144">string</span><span class="sxs-lookup"><span data-stu-id="36d91-144">string</span></span> | <span data-ttu-id="36d91-145">事件的名稱。</span><span class="sxs-lookup"><span data-stu-id="36d91-145">The name of the Incident.</span></span>
<span data-ttu-id="36d91-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="36d91-146">createdTime</span></span> | <span data-ttu-id="36d91-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="36d91-147">DateTimeOffset</span></span> | <span data-ttu-id="36d91-148">在 UTC) 建立事件的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="36d91-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="36d91-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="36d91-149">lastUpdateTime</span></span> | <span data-ttu-id="36d91-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="36d91-150">DateTimeOffset</span></span> | <span data-ttu-id="36d91-151">上次更新事件) 的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="36d91-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="36d91-152">分配</span><span class="sxs-lookup"><span data-stu-id="36d91-152">assignedTo</span></span> | <span data-ttu-id="36d91-153">string</span><span class="sxs-lookup"><span data-stu-id="36d91-153">string</span></span> | <span data-ttu-id="36d91-154">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="36d91-154">Owner of the Incident.</span></span>
<span data-ttu-id="36d91-155">嚴重性</span><span class="sxs-lookup"><span data-stu-id="36d91-155">severity</span></span> | <span data-ttu-id="36d91-156">Enum</span><span class="sxs-lookup"><span data-stu-id="36d91-156">Enum</span></span> | <span data-ttu-id="36d91-157">事件的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="36d91-157">Severity of the Incident.</span></span> <span data-ttu-id="36d91-158">可能的值為：、、、 ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` 、和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="36d91-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="36d91-159">地位</span><span class="sxs-lookup"><span data-stu-id="36d91-159">status</span></span> | <span data-ttu-id="36d91-160">Enum</span><span class="sxs-lookup"><span data-stu-id="36d91-160">Enum</span></span> | <span data-ttu-id="36d91-161">指定事件目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="36d91-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="36d91-162">可能的值為： ```Active``` 、 ```Resolved``` 、和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="36d91-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="36d91-163">分類</span><span class="sxs-lookup"><span data-stu-id="36d91-163">classification</span></span> | <span data-ttu-id="36d91-164">Enum</span><span class="sxs-lookup"><span data-stu-id="36d91-164">Enum</span></span> | <span data-ttu-id="36d91-165">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="36d91-165">Specification of the incident.</span></span> <span data-ttu-id="36d91-166">可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。</span><span class="sxs-lookup"><span data-stu-id="36d91-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="36d91-167">測定</span><span class="sxs-lookup"><span data-stu-id="36d91-167">determination</span></span> | <span data-ttu-id="36d91-168">Enum</span><span class="sxs-lookup"><span data-stu-id="36d91-168">Enum</span></span> | <span data-ttu-id="36d91-169">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="36d91-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="36d91-170">可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="36d91-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="36d91-171">標籤</span><span class="sxs-lookup"><span data-stu-id="36d91-171">tags</span></span> | <span data-ttu-id="36d91-172">字串清單</span><span class="sxs-lookup"><span data-stu-id="36d91-172">string List</span></span> | <span data-ttu-id="36d91-173">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="36d91-173">List of Incident tags.</span></span>
<span data-ttu-id="36d91-174">警報</span><span class="sxs-lookup"><span data-stu-id="36d91-174">alerts</span></span> | <span data-ttu-id="36d91-175">警示清單</span><span class="sxs-lookup"><span data-stu-id="36d91-175">Alert List</span></span> | <span data-ttu-id="36d91-176">相關警示的清單。</span><span class="sxs-lookup"><span data-stu-id="36d91-176">List of related alerts.</span></span> <span data-ttu-id="36d91-177">請參閱 [List 事件](api-list-incidents.md) API 檔中的範例。</span><span class="sxs-lookup"><span data-stu-id="36d91-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="36d91-178">相關文章</span><span class="sxs-lookup"><span data-stu-id="36d91-178">Related articles</span></span>

- [<span data-ttu-id="36d91-179">Microsoft 365 Defender APIs 概述</span><span class="sxs-lookup"><span data-stu-id="36d91-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="36d91-180">事件概觀</span><span class="sxs-lookup"><span data-stu-id="36d91-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="36d91-181">列出事件 API</span><span class="sxs-lookup"><span data-stu-id="36d91-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="36d91-182">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="36d91-182">Update incident API</span></span>](api-update-incidents.md)
