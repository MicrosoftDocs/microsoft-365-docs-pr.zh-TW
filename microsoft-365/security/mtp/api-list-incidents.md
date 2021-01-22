---
title: Microsoft 365 Defender 中的清單事件 API
description: 瞭解如何在 Microsoft 365 Defender 中列出事件 API
keywords: 清單、事件、事件、api
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
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932067"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="f9129-104">Microsoft 365 Defender 中的清單事件 API</span><span class="sxs-lookup"><span data-stu-id="f9129-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f9129-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="f9129-105">**Applies to:**</span></span>

- <span data-ttu-id="f9129-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9129-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9129-107">部分與發行前產品有關的資訊，在正式發行之前可能會大幅修改。</span><span class="sxs-lookup"><span data-stu-id="f9129-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f9129-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f9129-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="f9129-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="f9129-109">API description</span></span>

<span data-ttu-id="f9129-110">清單事件 API 可讓您針對事件進行排序，以建立明智的網路安全性回應。</span><span class="sxs-lookup"><span data-stu-id="f9129-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="f9129-111">它會公開在環境保留政策所指定的時間範圍內，已標出您網路中已標出之事件的集合。</span><span class="sxs-lookup"><span data-stu-id="f9129-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="f9129-112">最新的事件會顯示在清單頂端。</span><span class="sxs-lookup"><span data-stu-id="f9129-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="f9129-113">每個事件都包含相關警示陣列及其相關實體。</span><span class="sxs-lookup"><span data-stu-id="f9129-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="f9129-114">API 支援下列 **OData** 運算子：</span><span class="sxs-lookup"><span data-stu-id="f9129-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="f9129-115">`$filter``lastUpdateTime`、 `createdTime` `status` 和 `assignedTo` 屬性</span><span class="sxs-lookup"><span data-stu-id="f9129-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="f9129-116">`$top`，最大值為 **100**</span><span class="sxs-lookup"><span data-stu-id="f9129-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="f9129-117">限制</span><span class="sxs-lookup"><span data-stu-id="f9129-117">Limitations</span></span>

1. <span data-ttu-id="f9129-118">頁面大小上限為 **100 個事件**。</span><span class="sxs-lookup"><span data-stu-id="f9129-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="f9129-119">要求最高速率為每分鐘 **50 個通話，\*\*\*\*以及每小時 1500 個通話**。</span><span class="sxs-lookup"><span data-stu-id="f9129-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="f9129-120">權限</span><span class="sxs-lookup"><span data-stu-id="f9129-120">Permissions</span></span>

<span data-ttu-id="f9129-121">呼叫此 API 需要下列其中一種許可權。</span><span class="sxs-lookup"><span data-stu-id="f9129-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f9129-122">若要深入瞭解，包括如何選擇許可權，請參閱 Access [Microsoft 365 Defender API](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="f9129-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="f9129-123">許可權類型</span><span class="sxs-lookup"><span data-stu-id="f9129-123">Permission type</span></span> | <span data-ttu-id="f9129-124">權限</span><span class="sxs-lookup"><span data-stu-id="f9129-124">Permission</span></span> | <span data-ttu-id="f9129-125">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="f9129-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="f9129-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="f9129-126">Application</span></span> | <span data-ttu-id="f9129-127">Incident.Read.all</span><span class="sxs-lookup"><span data-stu-id="f9129-127">Incident.Read.All</span></span> | <span data-ttu-id="f9129-128">讀取所有事件</span><span class="sxs-lookup"><span data-stu-id="f9129-128">Read all incidents</span></span>
<span data-ttu-id="f9129-129">應用程式</span><span class="sxs-lookup"><span data-stu-id="f9129-129">Application</span></span> | <span data-ttu-id="f9129-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f9129-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="f9129-131">讀取及寫入所有事件</span><span class="sxs-lookup"><span data-stu-id="f9129-131">Read and write all incidents</span></span>
<span data-ttu-id="f9129-132">已委派 (公司或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="f9129-132">Delegated (work or school account)</span></span> | <span data-ttu-id="f9129-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="f9129-133">Incident.Read</span></span> | <span data-ttu-id="f9129-134">讀取事件</span><span class="sxs-lookup"><span data-stu-id="f9129-134">Read incidents</span></span>
<span data-ttu-id="f9129-135">已委派 (公司或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="f9129-135">Delegated (work or school account)</span></span> | <span data-ttu-id="f9129-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f9129-136">Incident.ReadWrite</span></span> | <span data-ttu-id="f9129-137">讀取和寫入事件</span><span class="sxs-lookup"><span data-stu-id="f9129-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="f9129-138">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="f9129-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="f9129-139">使用者必須擁有入口網站中事件的查看許可權。</span><span class="sxs-lookup"><span data-stu-id="f9129-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="f9129-140">回應只會包括使用者受到公開的事件。</span><span class="sxs-lookup"><span data-stu-id="f9129-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="f9129-141">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="f9129-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="f9129-142">要求標頭</span><span class="sxs-lookup"><span data-stu-id="f9129-142">Request headers</span></span>

<span data-ttu-id="f9129-143">名稱</span><span class="sxs-lookup"><span data-stu-id="f9129-143">Name</span></span> | <span data-ttu-id="f9129-144">類型</span><span class="sxs-lookup"><span data-stu-id="f9129-144">Type</span></span> | <span data-ttu-id="f9129-145">說明</span><span class="sxs-lookup"><span data-stu-id="f9129-145">Description</span></span>
-|-|-
<span data-ttu-id="f9129-146">授權</span><span class="sxs-lookup"><span data-stu-id="f9129-146">Authorization</span></span> | <span data-ttu-id="f9129-147">字串</span><span class="sxs-lookup"><span data-stu-id="f9129-147">String</span></span> | <span data-ttu-id="f9129-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f9129-148">Bearer {token}.</span></span> <span data-ttu-id="f9129-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="f9129-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="f9129-150">要求內體</span><span class="sxs-lookup"><span data-stu-id="f9129-150">Request body</span></span>

<span data-ttu-id="f9129-151">無。</span><span class="sxs-lookup"><span data-stu-id="f9129-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="f9129-152">回應</span><span class="sxs-lookup"><span data-stu-id="f9129-152">Response</span></span>

<span data-ttu-id="f9129-153">如果成功，此方法會返回 `200 OK` 回應 [本文中的](api-incident.md) 事件清單。</span><span class="sxs-lookup"><span data-stu-id="f9129-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="f9129-154">架構地圖</span><span class="sxs-lookup"><span data-stu-id="f9129-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="f9129-155">事件中繼資料</span><span class="sxs-lookup"><span data-stu-id="f9129-155">Incident metadata</span></span>

<span data-ttu-id="f9129-156">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="f9129-156">Field name</span></span> | <span data-ttu-id="f9129-157">說明</span><span class="sxs-lookup"><span data-stu-id="f9129-157">Description</span></span> | <span data-ttu-id="f9129-158">範例值</span><span class="sxs-lookup"><span data-stu-id="f9129-158">Example value</span></span>
-|-|-
<span data-ttu-id="f9129-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="f9129-159">incidentId</span></span> | <span data-ttu-id="f9129-160">代表事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f9129-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="f9129-161">924565</span><span class="sxs-lookup"><span data-stu-id="f9129-161">924565</span></span>
<span data-ttu-id="f9129-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="f9129-162">redirectIncidentId</span></span> | <span data-ttu-id="f9129-163">只有在事件與另一個事件分組時，才填上專案，做為事件處理邏輯的一部分。</span><span class="sxs-lookup"><span data-stu-id="f9129-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="f9129-164">924569</span><span class="sxs-lookup"><span data-stu-id="f9129-164">924569</span></span>
<span data-ttu-id="f9129-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="f9129-165">incidentName</span></span> | <span data-ttu-id="f9129-166">每個事件都可用的字串值。</span><span class="sxs-lookup"><span data-stu-id="f9129-166">String value available for every incident.</span></span> | <span data-ttu-id="f9129-167">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="f9129-167">Ransomware activity</span></span>
<span data-ttu-id="f9129-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="f9129-168">createdTime</span></span> | <span data-ttu-id="f9129-169">第一次建立事件的時間。</span><span class="sxs-lookup"><span data-stu-id="f9129-169">Time when incident was first created.</span></span> | <span data-ttu-id="f9129-170">2020-09-06T14：46：57.073333Z</span><span class="sxs-lookup"><span data-stu-id="f9129-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="f9129-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="f9129-171">lastUpdateTime</span></span> | <span data-ttu-id="f9129-172">上次在後端更新事件的時間。</span><span class="sxs-lookup"><span data-stu-id="f9129-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="f9129-173">當您針對事件取回的時間範圍設定要求參數時，可以使用此欄位。</span><span class="sxs-lookup"><span data-stu-id="f9129-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="f9129-174">2020-09-06T14：46：57.29Z</span><span class="sxs-lookup"><span data-stu-id="f9129-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="f9129-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f9129-175">assignedTo</span></span> | <span data-ttu-id="f9129-176">事件的擁有者;如果沒有指派擁有者，則為 *Null。*</span><span class="sxs-lookup"><span data-stu-id="f9129-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="f9129-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9129-177">secop2@contoso.com</span></span>
<span data-ttu-id="f9129-178">分類</span><span class="sxs-lookup"><span data-stu-id="f9129-178">classification</span></span> | <span data-ttu-id="f9129-179">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="f9129-179">The specification for the incident.</span></span> <span data-ttu-id="f9129-180">屬性值為：*未知\*\*、FalsePositive、TruePositive* </span><span class="sxs-lookup"><span data-stu-id="f9129-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="f9129-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="f9129-181">Unknown</span></span>
<span data-ttu-id="f9129-182">測定</span><span class="sxs-lookup"><span data-stu-id="f9129-182">determination</span></span> | <span data-ttu-id="f9129-183">指定事件判定。</span><span class="sxs-lookup"><span data-stu-id="f9129-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="f9129-184">屬性值為 *：NotAvailable，* *Apt， Malware，* *SecurityPerson您*， *SecurityTesting，* *UnwantedSoftware，* *Other* </span><span class="sxs-lookup"><span data-stu-id="f9129-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="f9129-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="f9129-185">NotAvailable</span></span>
<span data-ttu-id="f9129-186">地位</span><span class="sxs-lookup"><span data-stu-id="f9129-186">status</span></span> | <span data-ttu-id="f9129-187">將事件分類 (*為使用中* 或 *已解決) 。*</span><span class="sxs-lookup"><span data-stu-id="f9129-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="f9129-188">它可協助組織及管理對事件的回應。</span><span class="sxs-lookup"><span data-stu-id="f9129-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="f9129-189">作用中</span><span class="sxs-lookup"><span data-stu-id="f9129-189">Active</span></span>
<span data-ttu-id="f9129-190">嚴重性</span><span class="sxs-lookup"><span data-stu-id="f9129-190">severity</span></span> | <span data-ttu-id="f9129-191">表示可能會影響資產。</span><span class="sxs-lookup"><span data-stu-id="f9129-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="f9129-192">嚴重性越高，影響越大。</span><span class="sxs-lookup"><span data-stu-id="f9129-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="f9129-193">一般來說，高嚴重性的專案需要立即引起注意。</span><span class="sxs-lookup"><span data-stu-id="f9129-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="f9129-194">下列其中一個值：*資訊、\*\*低*、*中、*高\*。</span><span class="sxs-lookup"><span data-stu-id="f9129-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="f9129-195">中</span><span class="sxs-lookup"><span data-stu-id="f9129-195">Medium</span></span>
<span data-ttu-id="f9129-196">標籤</span><span class="sxs-lookup"><span data-stu-id="f9129-196">tags</span></span> | <span data-ttu-id="f9129-197">與事件相關聯的自訂標記陣列，例如，以共同特性為事件群組標標。</span><span class="sxs-lookup"><span data-stu-id="f9129-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="f9129-198">警報</span><span class="sxs-lookup"><span data-stu-id="f9129-198">alerts</span></span> | <span data-ttu-id="f9129-199">包含與事件有關之所有警示的陣列，以及其他資訊，例如嚴重性、參與警示的實體，以及警示的來源。</span><span class="sxs-lookup"><span data-stu-id="f9129-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="f9129-200">\[\] (下方查看警示欄位) </span><span class="sxs-lookup"><span data-stu-id="f9129-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="f9129-201">提醒中繼資料</span><span class="sxs-lookup"><span data-stu-id="f9129-201">Alerts metadata</span></span>

<span data-ttu-id="f9129-202">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="f9129-202">Field name</span></span> | <span data-ttu-id="f9129-203">說明</span><span class="sxs-lookup"><span data-stu-id="f9129-203">Description</span></span> | <span data-ttu-id="f9129-204">範例值</span><span class="sxs-lookup"><span data-stu-id="f9129-204">Example value</span></span>
-|-|-
<span data-ttu-id="f9129-205">alertId</span><span class="sxs-lookup"><span data-stu-id="f9129-205">alertId</span></span> | <span data-ttu-id="f9129-206">代表警示的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f9129-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="f9129-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="f9129-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="f9129-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="f9129-208">incidentId</span></span> | <span data-ttu-id="f9129-209">代表與此警示相關聯之事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f9129-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="f9129-210">924565</span><span class="sxs-lookup"><span data-stu-id="f9129-210">924565</span></span>
<span data-ttu-id="f9129-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="f9129-211">serviceSource</span></span> | <span data-ttu-id="f9129-212">警示的來源服務，例如端點的 Microsoft Defender、Microsoft Cloud App 安全性、身分識別的 Microsoft Defender 或 Office 365 的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="f9129-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="f9129-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="f9129-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="f9129-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="f9129-214">creationTime</span></span> | <span data-ttu-id="f9129-215">第一次建立警示的時間。</span><span class="sxs-lookup"><span data-stu-id="f9129-215">Time when alert was first created.</span></span> | <span data-ttu-id="f9129-216">2020-09-06T14：46：55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="f9129-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="f9129-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="f9129-217">lastUpdatedTime</span></span> | <span data-ttu-id="f9129-218">上次在後端更新警示的時間。</span><span class="sxs-lookup"><span data-stu-id="f9129-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="f9129-219">2020-09-06T14：46：57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="f9129-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="f9129-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="f9129-220">resolvedTime</span></span> | <span data-ttu-id="f9129-221">警示已解決的時間。</span><span class="sxs-lookup"><span data-stu-id="f9129-221">Time when alert was resolved.</span></span> | <span data-ttu-id="f9129-222">2020-09-10T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="f9129-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="f9129-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="f9129-223">firstActivity</span></span> | <span data-ttu-id="f9129-224">第一次報告後端活動已更新的時間。</span><span class="sxs-lookup"><span data-stu-id="f9129-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="f9129-225">2020-09-04T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="f9129-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="f9129-226">標題</span><span class="sxs-lookup"><span data-stu-id="f9129-226">title</span></span> | <span data-ttu-id="f9129-227">每個警示的簡短識別字串值。</span><span class="sxs-lookup"><span data-stu-id="f9129-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="f9129-228">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="f9129-228">Ransomware activity</span></span>
<span data-ttu-id="f9129-229">描述</span><span class="sxs-lookup"><span data-stu-id="f9129-229">description</span></span> | <span data-ttu-id="f9129-230">描述每個警示的字串值。</span><span class="sxs-lookup"><span data-stu-id="f9129-230">String value describing each alert.</span></span> | <span data-ttu-id="f9129-231">使用者測試使用者2 (testUser2@contoso.com) 處理 99 個副檔名結尾為不常副檔名 *的檔案*。</span><span class="sxs-lookup"><span data-stu-id="f9129-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="f9129-232">這是一些異常數目的檔案操控，且有潛在的勒索軟體攻擊。</span><span class="sxs-lookup"><span data-stu-id="f9129-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="f9129-233">類別</span><span class="sxs-lookup"><span data-stu-id="f9129-233">category</span></span> | <span data-ttu-id="f9129-234">以視覺和數值方式查看攻擊在攻擊鏈中的進度。</span><span class="sxs-lookup"><span data-stu-id="f9129-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="f9129-235">與 [MITRE ATT&CK™對齊](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="f9129-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="f9129-236">影響</span><span class="sxs-lookup"><span data-stu-id="f9129-236">Impact</span></span>
<span data-ttu-id="f9129-237">地位</span><span class="sxs-lookup"><span data-stu-id="f9129-237">status</span></span> | <span data-ttu-id="f9129-238">將警示分類 (*新增、\*\*使用中* 或 *已解決) 。*</span><span class="sxs-lookup"><span data-stu-id="f9129-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="f9129-239">它可協助您將通知整理及管理。</span><span class="sxs-lookup"><span data-stu-id="f9129-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="f9129-240">新增</span><span class="sxs-lookup"><span data-stu-id="f9129-240">New</span></span>
<span data-ttu-id="f9129-241">嚴重性</span><span class="sxs-lookup"><span data-stu-id="f9129-241">severity</span></span> | <span data-ttu-id="f9129-242">表示可能會影響資產。</span><span class="sxs-lookup"><span data-stu-id="f9129-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="f9129-243">嚴重性越高，影響越大。</span><span class="sxs-lookup"><span data-stu-id="f9129-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="f9129-244">一般來說，高嚴重性的專案需要立即引起注意。</span><span class="sxs-lookup"><span data-stu-id="f9129-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="f9129-245">下列其中一個值：*資訊、\*\*低*、*中、*高\*。</span><span class="sxs-lookup"><span data-stu-id="f9129-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="f9129-246">中</span><span class="sxs-lookup"><span data-stu-id="f9129-246">Medium</span></span>
<span data-ttu-id="f9129-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="f9129-247">investigationId</span></span> | <span data-ttu-id="f9129-248">此警示所觸發的自動化調查識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9129-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="f9129-249">1234</span><span class="sxs-lookup"><span data-stu-id="f9129-249">1234</span></span>
<span data-ttu-id="f9129-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="f9129-250">investigationState</span></span> | <span data-ttu-id="f9129-251">調查目前狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="f9129-251">Information on the investigation's current status.</span></span> <span data-ttu-id="f9129-252">下列其中一個值：Unknown，*已* 終止 *，SuccessfullyRemediaed，* *Queue，* *Failed，* *PartiallyRemediaed，* *running，* *PendingApproval，* *PendingResource，* *PartiallyInvesed，*  *TerminatedByUser，* *TerminatedBySystem， Queued，* *InnerFailure，* *PreexingAlert，* *UnsupportedOs，* *UnsupportedAlertType，* *SuppressedAlert.* </span><span class="sxs-lookup"><span data-stu-id="f9129-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="f9129-253">不支援的AlertType</span><span class="sxs-lookup"><span data-stu-id="f9129-253">UnsupportedAlertType</span></span>
<span data-ttu-id="f9129-254">分類</span><span class="sxs-lookup"><span data-stu-id="f9129-254">classification</span></span> | <span data-ttu-id="f9129-255">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="f9129-255">The specification for the incident.</span></span> <span data-ttu-id="f9129-256">屬性值為：*未知\*\*、FalsePositive、TruePositive* 或 *Null* </span><span class="sxs-lookup"><span data-stu-id="f9129-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="f9129-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="f9129-257">Unknown</span></span>
<span data-ttu-id="f9129-258">測定</span><span class="sxs-lookup"><span data-stu-id="f9129-258">determination</span></span> | <span data-ttu-id="f9129-259">指定事件判定。</span><span class="sxs-lookup"><span data-stu-id="f9129-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="f9129-260">屬性值為 *：NotAvailable，* *Apt， Malware，* *SecurityPerson您*， *SecurityTesting，* *UnwantedSoftware，* *Other* or *null* </span><span class="sxs-lookup"><span data-stu-id="f9129-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="f9129-261">容易</span><span class="sxs-lookup"><span data-stu-id="f9129-261">Apt</span></span>
<span data-ttu-id="f9129-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f9129-262">assignedTo</span></span> | <span data-ttu-id="f9129-263">事件的擁有者;如果沒有指派擁有者，則為 *Null。*</span><span class="sxs-lookup"><span data-stu-id="f9129-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="f9129-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9129-264">secop2@contoso.com</span></span>
<span data-ttu-id="f9129-265">actorName</span><span class="sxs-lookup"><span data-stu-id="f9129-265">actorName</span></span> | <span data-ttu-id="f9129-266">活動群組 ，如果有，則與此警示相關聯。</span><span class="sxs-lookup"><span data-stu-id="f9129-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="f9129-267">硼</span><span class="sxs-lookup"><span data-stu-id="f9129-267">BORON</span></span>
<span data-ttu-id="f9129-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="f9129-268">threatFamilyName</span></span> | <span data-ttu-id="f9129-269">與此警示相關聯的威脅系列。</span><span class="sxs-lookup"><span data-stu-id="f9129-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="f9129-270">Null</span><span class="sxs-lookup"><span data-stu-id="f9129-270">null</span></span>
<span data-ttu-id="f9129-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="f9129-271">mitreTechniques</span></span> | <span data-ttu-id="f9129-272">符合MITRE ATT 和 [CK&架構™](https://attack.mitre.org/)技術。</span><span class="sxs-lookup"><span data-stu-id="f9129-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="f9129-273">設備</span><span class="sxs-lookup"><span data-stu-id="f9129-273">devices</span></span> | <span data-ttu-id="f9129-274">所有已送出事件相關警示的裝置。</span><span class="sxs-lookup"><span data-stu-id="f9129-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="f9129-275">\[\] (下方查看實體欄位的詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="f9129-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="f9129-276">裝置格式</span><span class="sxs-lookup"><span data-stu-id="f9129-276">Device format</span></span>

<span data-ttu-id="f9129-277">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="f9129-277">Field name</span></span> | <span data-ttu-id="f9129-278">說明</span><span class="sxs-lookup"><span data-stu-id="f9129-278">Description</span></span> | <span data-ttu-id="f9129-279">範例值</span><span class="sxs-lookup"><span data-stu-id="f9129-279">Example value</span></span>
-|-|-
<span data-ttu-id="f9129-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="f9129-280">DeviceId</span></span> | <span data-ttu-id="f9129-281">Microsoft Defender ATP 中指定的裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9129-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="f9129-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="f9129-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="f9129-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="f9129-283">aadDeviceId</span></span> |  <span data-ttu-id="f9129-284">Azure [Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)中指定的裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9129-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="f9129-285">僅適用于加入網域的裝置。</span><span class="sxs-lookup"><span data-stu-id="f9129-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="f9129-286">Null</span><span class="sxs-lookup"><span data-stu-id="f9129-286">null</span></span>
<span data-ttu-id="f9129-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="f9129-287">deviceDnsName</span></span> | <span data-ttu-id="f9129-288">裝置完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f9129-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="f9129-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9129-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="f9129-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="f9129-290">osPlatform</span></span> | <span data-ttu-id="f9129-291">裝置正在作業系統平臺中運作。</span><span class="sxs-lookup"><span data-stu-id="f9129-291">The OS platform the device is running.</span></span>| <span data-ttu-id="f9129-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="f9129-292">WindowsServer2016</span></span>
<span data-ttu-id="f9129-293">os在</span><span class="sxs-lookup"><span data-stu-id="f9129-293">osBuild</span></span> | <span data-ttu-id="f9129-294">裝置所作業系統的建立版本。</span><span class="sxs-lookup"><span data-stu-id="f9129-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="f9129-295">14393</span><span class="sxs-lookup"><span data-stu-id="f9129-295">14393</span></span>
<span data-ttu-id="f9129-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="f9129-296">rbacGroupName</span></span> | <span data-ttu-id="f9129-297">角色 [型存取控制是](https://docs.microsoft.com/azure/role-based-access-control/overview) (裝置) 的 RBAC 群組。</span><span class="sxs-lookup"><span data-stu-id="f9129-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="f9129-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="f9129-298">WDATP-Ring0</span></span>
<span data-ttu-id="f9129-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="f9129-299">firstSeen</span></span> | <span data-ttu-id="f9129-300">裝置第一次出現的時間。</span><span class="sxs-lookup"><span data-stu-id="f9129-300">Time when device was first seen.</span></span> | <span data-ttu-id="f9129-301">2020-02-06T14：16：01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="f9129-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="f9129-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="f9129-302">healthStatus</span></span> | <span data-ttu-id="f9129-303">裝置的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="f9129-303">The health state of the device.</span></span> | <span data-ttu-id="f9129-304">作用中</span><span class="sxs-lookup"><span data-stu-id="f9129-304">Active</span></span>
<span data-ttu-id="f9129-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="f9129-305">riskScore</span></span> | <span data-ttu-id="f9129-306">裝置的風險分數。</span><span class="sxs-lookup"><span data-stu-id="f9129-306">The risk score for the  device.</span></span> | <span data-ttu-id="f9129-307">高</span><span class="sxs-lookup"><span data-stu-id="f9129-307">High</span></span>
<span data-ttu-id="f9129-308">實體</span><span class="sxs-lookup"><span data-stu-id="f9129-308">entities</span></span> | <span data-ttu-id="f9129-309">所有已識別為所警示一部分或與它相關的實體。</span><span class="sxs-lookup"><span data-stu-id="f9129-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="f9129-310">\[\] (下方查看實體欄位的詳細資訊) </span><span class="sxs-lookup"><span data-stu-id="f9129-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="f9129-311">實體格式</span><span class="sxs-lookup"><span data-stu-id="f9129-311">Entity Format</span></span>

<span data-ttu-id="f9129-312">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="f9129-312">Field name</span></span> | <span data-ttu-id="f9129-313">說明</span><span class="sxs-lookup"><span data-stu-id="f9129-313">Description</span></span> | <span data-ttu-id="f9129-314">範例值</span><span class="sxs-lookup"><span data-stu-id="f9129-314">Example value</span></span>
-|-|-
<span data-ttu-id="f9129-315">entityType</span><span class="sxs-lookup"><span data-stu-id="f9129-315">entityType</span></span> | <span data-ttu-id="f9129-316">識別為屬於所提供警示之一部分或與它相關之實體。</span><span class="sxs-lookup"><span data-stu-id="f9129-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="f9129-317">屬性值為 *：User，* *Ip，* *Url，* *File，* *Process，* *MailBox，* *MailMessage，* *MailCluster，* *Registry*</span><span class="sxs-lookup"><span data-stu-id="f9129-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="f9129-318">User</span><span class="sxs-lookup"><span data-stu-id="f9129-318">User</span></span>
<span data-ttu-id="f9129-319">sha1</span><span class="sxs-lookup"><span data-stu-id="f9129-319">sha1</span></span> | <span data-ttu-id="f9129-320">如果 entityType 為 *File，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="f9129-321">與檔案或程式相關的警示之檔案雜湊。</span><span class="sxs-lookup"><span data-stu-id="f9129-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="f9129-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="f9129-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="f9129-323">sha256</span><span class="sxs-lookup"><span data-stu-id="f9129-323">sha256</span></span> | <span data-ttu-id="f9129-324">如果 entityType 為 *File，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="f9129-325">與檔案或程式相關的警示之檔案雜湊。</span><span class="sxs-lookup"><span data-stu-id="f9129-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="f9129-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="f9129-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="f9129-327">檔案名</span><span class="sxs-lookup"><span data-stu-id="f9129-327">fileName</span></span> | <span data-ttu-id="f9129-328">如果 entityType 為 *File，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="f9129-329">與檔案或程式相關聯的通知的檔案名</span><span class="sxs-lookup"><span data-stu-id="f9129-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="f9129-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="f9129-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="f9129-331">filePath</span><span class="sxs-lookup"><span data-stu-id="f9129-331">filePath</span></span> | <span data-ttu-id="f9129-332">如果 entityType 為 *File，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="f9129-333">與檔案或程式相關聯的警示之檔案路徑</span><span class="sxs-lookup"><span data-stu-id="f9129-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="f9129-334">\\C：\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="f9129-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="f9129-335">processId</span><span class="sxs-lookup"><span data-stu-id="f9129-335">processId</span></span> | <span data-ttu-id="f9129-336">如果 entityType 為 *Process，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f9129-337">24348</span><span class="sxs-lookup"><span data-stu-id="f9129-337">24348</span></span>
<span data-ttu-id="f9129-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="f9129-338">processCommandLine</span></span> | <span data-ttu-id="f9129-339">如果 entityType 為 *Process，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f9129-340">「您的檔案已經準備好下載檔案 \_1911150169.exe」</span><span class="sxs-lookup"><span data-stu-id="f9129-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="f9129-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="f9129-341">processCreationTime</span></span> | <span data-ttu-id="f9129-342">如果 entityType 為 *Process，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f9129-343">2020-07-18T03：25：38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="f9129-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="f9129-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="f9129-344">parentProcessId</span></span> | <span data-ttu-id="f9129-345">如果 entityType 為 *Process，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f9129-346">16840</span><span class="sxs-lookup"><span data-stu-id="f9129-346">16840</span></span>
<span data-ttu-id="f9129-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="f9129-347">parentProcessCreationTime</span></span> | <span data-ttu-id="f9129-348">如果 entityType 為 *Process，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="f9129-349">2020-07-18T02：12：32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="f9129-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="f9129-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="f9129-350">ipAddress</span></span> | <span data-ttu-id="f9129-351">如果 entityType 是 *Ip，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="f9129-352">與網路事件相關聯的警示之 IP 位址，例如與惡意網路目的地 *通訊。*</span><span class="sxs-lookup"><span data-stu-id="f9129-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="f9129-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="f9129-353">62.216.203.204</span></span>
<span data-ttu-id="f9129-354">URL</span><span class="sxs-lookup"><span data-stu-id="f9129-354">url</span></span> | <span data-ttu-id="f9129-355">如果 entityType 為 *URL，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="f9129-356">與網路事件相關聯的警示 URL，例如，與惡意 *網路* 目的地通訊。</span><span class="sxs-lookup"><span data-stu-id="f9129-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="f9129-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="f9129-357">down.esales360.cn</span></span>
<span data-ttu-id="f9129-358">accountName</span><span class="sxs-lookup"><span data-stu-id="f9129-358">accountName</span></span> | <span data-ttu-id="f9129-359">如果 entityType 為 *User，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="f9129-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="f9129-360">testUser2</span></span>
<span data-ttu-id="f9129-361">domainName</span><span class="sxs-lookup"><span data-stu-id="f9129-361">domainName</span></span> | <span data-ttu-id="f9129-362">如果 entityType 為 *User，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="f9129-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="f9129-363">europe.corp.contoso</span></span>
<span data-ttu-id="f9129-364">userSid</span><span class="sxs-lookup"><span data-stu-id="f9129-364">userSid</span></span> | <span data-ttu-id="f9129-365">如果 entityType 為 *User，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="f9129-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="f9129-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="f9129-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="f9129-367">aadUserId</span></span> | <span data-ttu-id="f9129-368">如果 entityType 為 *User，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="f9129-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="f9129-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="f9129-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f9129-370">userPrincipalName</span></span> | <span data-ttu-id="f9129-371">如果 entityType 為 *User* / *MailBox* / *MailMessage，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="f9129-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9129-372">testUser2@contoso.com</span></span>
<span data-ttu-id="f9129-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="f9129-373">mailboxDisplayName</span></span> | <span data-ttu-id="f9129-374">如果 entityType 為 *MailBox，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="f9129-375">測試 User2</span><span class="sxs-lookup"><span data-stu-id="f9129-375">test User2</span></span>
<span data-ttu-id="f9129-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="f9129-376">mailboxAddress</span></span> | <span data-ttu-id="f9129-377">如果 entityType 為 *User* / *MailBox* / *MailMessage，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="f9129-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9129-378">testUser2@contoso.com</span></span>
<span data-ttu-id="f9129-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="f9129-379">clusterBy</span></span> | <span data-ttu-id="f9129-380">如果 entityType 是  *MailCluster，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="f9129-381">Subject;P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="f9129-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="f9129-382">sender</span><span class="sxs-lookup"><span data-stu-id="f9129-382">sender</span></span> | <span data-ttu-id="f9129-383">如果 entityType 為 *User* / *MailBox* / *MailMessage，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="f9129-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="f9129-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="f9129-385">recipient</span><span class="sxs-lookup"><span data-stu-id="f9129-385">recipient</span></span> | <span data-ttu-id="f9129-386">如果 entityType 為 *MailMessage，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="f9129-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9129-387">testUser2@contoso.com</span></span>
<span data-ttu-id="f9129-388">主題</span><span class="sxs-lookup"><span data-stu-id="f9129-388">subject</span></span> | <span data-ttu-id="f9129-389">如果 entityType 為 *MailMessage，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="f9129-390">\[外部 \] 注意</span><span class="sxs-lookup"><span data-stu-id="f9129-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="f9129-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="f9129-391">deliveryAction</span></span> | <span data-ttu-id="f9129-392">如果 entityType 為 *MailMessage，則可用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="f9129-393">已傳遞</span><span class="sxs-lookup"><span data-stu-id="f9129-393">Delivered</span></span>
<span data-ttu-id="f9129-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="f9129-394">securityGroupId</span></span> | <span data-ttu-id="f9129-395">如果 entityType 為  *SecurityGroup，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="f9129-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="f9129-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="f9129-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="f9129-397">securityGroupName</span></span> | <span data-ttu-id="f9129-398">如果 entityType 為  *SecurityGroup，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="f9129-399">網路組組運算子</span><span class="sxs-lookup"><span data-stu-id="f9129-399">Network Configuration Operators</span></span>
<span data-ttu-id="f9129-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="f9129-400">registryHive</span></span> | <span data-ttu-id="f9129-401">如果 entityType 為  *Registry，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f9129-402">HKEY \_ LOCAL \_ MACHINE</span><span class="sxs-lookup"><span data-stu-id="f9129-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="f9129-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="f9129-403">registryKey</span></span> | <span data-ttu-id="f9129-404">如果 entityType 為  *Registry，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f9129-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="f9129-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="f9129-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="f9129-406">registryValueType</span></span> | <span data-ttu-id="f9129-407">如果 entityType 為  *Registry，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f9129-408">字串</span><span class="sxs-lookup"><span data-stu-id="f9129-408">String</span></span>
<span data-ttu-id="f9129-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="f9129-409">registryValue</span></span> | <span data-ttu-id="f9129-410">如果 entityType 為  *Registry，則可供使用*。</span><span class="sxs-lookup"><span data-stu-id="f9129-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="f9129-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="f9129-411">31-00-00-00</span></span>
<span data-ttu-id="f9129-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="f9129-412">deviceId</span></span> | <span data-ttu-id="f9129-413">與實體相關的裝置識別碼 ，如果有的話。</span><span class="sxs-lookup"><span data-stu-id="f9129-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="f9129-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="f9129-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="f9129-415">範例</span><span class="sxs-lookup"><span data-stu-id="f9129-415">Example</span></span>

<span data-ttu-id="f9129-416">**請求**</span><span class="sxs-lookup"><span data-stu-id="f9129-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="f9129-417">**回應**</span><span class="sxs-lookup"><span data-stu-id="f9129-417">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="f9129-418">相關文章</span><span class="sxs-lookup"><span data-stu-id="f9129-418">Related articles</span></span>

- [<span data-ttu-id="f9129-419">存取 Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="f9129-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="f9129-420">瞭解 API 限制與授權</span><span class="sxs-lookup"><span data-stu-id="f9129-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="f9129-421">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="f9129-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="f9129-422">事件概觀</span><span class="sxs-lookup"><span data-stu-id="f9129-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f9129-423">事件 API</span><span class="sxs-lookup"><span data-stu-id="f9129-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="f9129-424">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="f9129-424">Update incident API</span></span>](api-update-incidents.md)
