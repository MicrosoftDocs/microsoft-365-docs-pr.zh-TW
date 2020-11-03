---
title: Microsoft 365 Defender API 中的事件資源類型
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844017"
---
# <a name="incident-resource-type"></a><span data-ttu-id="054cf-104">事件資源類型</span><span class="sxs-lookup"><span data-stu-id="054cf-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="054cf-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="054cf-105">**Applies to:**</span></span>
- <span data-ttu-id="054cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="054cf-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="054cf-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="054cf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="054cf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="054cf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="054cf-109">方法</span><span class="sxs-lookup"><span data-stu-id="054cf-109">Methods</span></span>

<span data-ttu-id="054cf-110">方法	</span><span class="sxs-lookup"><span data-stu-id="054cf-110">Method</span></span> |<span data-ttu-id="054cf-111">傳回類型</span><span class="sxs-lookup"><span data-stu-id="054cf-111">Return Type</span></span> |<span data-ttu-id="054cf-112">描述</span><span class="sxs-lookup"><span data-stu-id="054cf-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="054cf-113">列出事件</span><span class="sxs-lookup"><span data-stu-id="054cf-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="054cf-114">[事件](api-incident.md) 清單</span><span class="sxs-lookup"><span data-stu-id="054cf-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="054cf-115">取得事件清單。</span><span class="sxs-lookup"><span data-stu-id="054cf-115">Get a list of incidents.</span></span>
[<span data-ttu-id="054cf-116">更新事件</span><span class="sxs-lookup"><span data-stu-id="054cf-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="054cf-117">事件</span><span class="sxs-lookup"><span data-stu-id="054cf-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="054cf-118">更新特定的事件。</span><span class="sxs-lookup"><span data-stu-id="054cf-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="054cf-119">屬性</span><span class="sxs-lookup"><span data-stu-id="054cf-119">Properties</span></span>

<span data-ttu-id="054cf-120">屬性	</span><span class="sxs-lookup"><span data-stu-id="054cf-120">Property</span></span> |    <span data-ttu-id="054cf-121">類型</span><span class="sxs-lookup"><span data-stu-id="054cf-121">Type</span></span>    |    <span data-ttu-id="054cf-122">描述</span><span class="sxs-lookup"><span data-stu-id="054cf-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="054cf-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="054cf-123">incidentId</span></span> | <span data-ttu-id="054cf-124">long</span><span class="sxs-lookup"><span data-stu-id="054cf-124">long</span></span> | <span data-ttu-id="054cf-125">事件唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="054cf-125">Incident unique ID.</span></span>
<span data-ttu-id="054cf-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="054cf-126">redirectIncidentId</span></span> | <span data-ttu-id="054cf-127">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="054cf-127">nullable long</span></span> | <span data-ttu-id="054cf-128">目前的事件彙總至的事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="054cf-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="054cf-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="054cf-129">incidentName</span></span> | <span data-ttu-id="054cf-130">string</span><span class="sxs-lookup"><span data-stu-id="054cf-130">string</span></span> | <span data-ttu-id="054cf-131">事件的名稱。</span><span class="sxs-lookup"><span data-stu-id="054cf-131">The name of the Incident.</span></span>
<span data-ttu-id="054cf-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="054cf-132">createdTime</span></span> | <span data-ttu-id="054cf-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="054cf-133">DateTimeOffset</span></span> | <span data-ttu-id="054cf-134">在 UTC) 建立事件的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="054cf-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="054cf-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="054cf-135">lastUpdateTime</span></span> | <span data-ttu-id="054cf-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="054cf-136">DateTimeOffset</span></span> | <span data-ttu-id="054cf-137">上次更新事件) 的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="054cf-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="054cf-138">分配</span><span class="sxs-lookup"><span data-stu-id="054cf-138">assignedTo</span></span> | <span data-ttu-id="054cf-139">string</span><span class="sxs-lookup"><span data-stu-id="054cf-139">string</span></span> | <span data-ttu-id="054cf-140">事件的擁有者。</span><span class="sxs-lookup"><span data-stu-id="054cf-140">Owner of the Incident.</span></span>
<span data-ttu-id="054cf-141">嚴重性</span><span class="sxs-lookup"><span data-stu-id="054cf-141">severity</span></span> | <span data-ttu-id="054cf-142">Enum</span><span class="sxs-lookup"><span data-stu-id="054cf-142">Enum</span></span> | <span data-ttu-id="054cf-143">事件的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="054cf-143">Severity of the Incident.</span></span> <span data-ttu-id="054cf-144">可能的值為： ```UnSpecified``` 、、 ```Informational``` ```Low``` 、 ```Medium``` 和 ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="054cf-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="054cf-145">地位</span><span class="sxs-lookup"><span data-stu-id="054cf-145">status</span></span> | <span data-ttu-id="054cf-146">Enum</span><span class="sxs-lookup"><span data-stu-id="054cf-146">Enum</span></span> | <span data-ttu-id="054cf-147">指定事件目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="054cf-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="054cf-148">可能的值為 ```Active``` ： ```Resolved``` 和 ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="054cf-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="054cf-149">分類</span><span class="sxs-lookup"><span data-stu-id="054cf-149">classification</span></span> | <span data-ttu-id="054cf-150">Enum</span><span class="sxs-lookup"><span data-stu-id="054cf-150">Enum</span></span> | <span data-ttu-id="054cf-151">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="054cf-151">Specification of the incident.</span></span> <span data-ttu-id="054cf-152">可能的值為： ```Unknown``` 、 ```FalsePositive``` 、 ```TruePositive``` 。</span><span class="sxs-lookup"><span data-stu-id="054cf-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="054cf-153">測定</span><span class="sxs-lookup"><span data-stu-id="054cf-153">determination</span></span> | <span data-ttu-id="054cf-154">Enum</span><span class="sxs-lookup"><span data-stu-id="054cf-154">Enum</span></span> | <span data-ttu-id="054cf-155">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="054cf-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="054cf-156">可能的值為：、、、、、、 ```NotAvailable``` ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` ```Other``` 。</span><span class="sxs-lookup"><span data-stu-id="054cf-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="054cf-157">標籤</span><span class="sxs-lookup"><span data-stu-id="054cf-157">tags</span></span> | <span data-ttu-id="054cf-158">字串清單</span><span class="sxs-lookup"><span data-stu-id="054cf-158">string List</span></span> | <span data-ttu-id="054cf-159">事件標記清單。</span><span class="sxs-lookup"><span data-stu-id="054cf-159">List of Incident tags.</span></span>
<span data-ttu-id="054cf-160">警報</span><span class="sxs-lookup"><span data-stu-id="054cf-160">alerts</span></span> | <span data-ttu-id="054cf-161">警示清單</span><span class="sxs-lookup"><span data-stu-id="054cf-161">Alert List</span></span> | <span data-ttu-id="054cf-162">相關警示的清單。</span><span class="sxs-lookup"><span data-stu-id="054cf-162">List of related alerts.</span></span> <span data-ttu-id="054cf-163">請參閱 [List 事件](api-list-incidents.md) API 檔中的範例。</span><span class="sxs-lookup"><span data-stu-id="054cf-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
