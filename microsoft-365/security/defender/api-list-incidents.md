---
title: Microsoft 365 Defender 中的列出事件 API
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7fb0de4f8dc67331e7acca59e70d061fe7c19493
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935734"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="52251-104">Microsoft 365 Defender 中的列出事件 API</span><span class="sxs-lookup"><span data-stu-id="52251-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="52251-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="52251-105">**Applies to:**</span></span>

- <span data-ttu-id="52251-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52251-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52251-107">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="52251-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="52251-108">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="52251-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="52251-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="52251-109">API description</span></span>

<span data-ttu-id="52251-110">清單事件 API 可讓您排序事件，以建立已獲悉的 cybersecurity 回應。</span><span class="sxs-lookup"><span data-stu-id="52251-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="52251-111">它會針對您在環境保留原則中所指定的時間範圍內，公開網路上所標示的事件集合。</span><span class="sxs-lookup"><span data-stu-id="52251-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="52251-112">最近的事件會顯示在清單頂端。</span><span class="sxs-lookup"><span data-stu-id="52251-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="52251-113">每個事件都包含相關警示的陣列及其相關實體。</span><span class="sxs-lookup"><span data-stu-id="52251-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="52251-114">API 支援下列 **OData** 運算子：</span><span class="sxs-lookup"><span data-stu-id="52251-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="52251-115">`$filter` 在 `lastUpdateTime` 、、 `createdTime` `status` 、和 `assignedTo` 屬性</span><span class="sxs-lookup"><span data-stu-id="52251-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="52251-116">`$top`，最大值為 **100**</span><span class="sxs-lookup"><span data-stu-id="52251-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="52251-117">限制</span><span class="sxs-lookup"><span data-stu-id="52251-117">Limitations</span></span>

1. <span data-ttu-id="52251-118">頁面大小上限為 **100 事件**。</span><span class="sxs-lookup"><span data-stu-id="52251-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="52251-119">要求的最大速率為 **每分鐘50個通話** ， **每小時1500個通話**。</span><span class="sxs-lookup"><span data-stu-id="52251-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="52251-120">權限</span><span class="sxs-lookup"><span data-stu-id="52251-120">Permissions</span></span>

<span data-ttu-id="52251-121">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="52251-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="52251-122">若要深入瞭解，包括如何選擇許可權，請參閱 [Access Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="52251-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="52251-123">許可權類型</span><span class="sxs-lookup"><span data-stu-id="52251-123">Permission type</span></span> | <span data-ttu-id="52251-124">權限</span><span class="sxs-lookup"><span data-stu-id="52251-124">Permission</span></span> | <span data-ttu-id="52251-125">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="52251-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="52251-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="52251-126">Application</span></span> | <span data-ttu-id="52251-127">Incident。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="52251-127">Incident.Read.All</span></span> | <span data-ttu-id="52251-128">讀取所有事件</span><span class="sxs-lookup"><span data-stu-id="52251-128">Read all incidents</span></span>
<span data-ttu-id="52251-129">應用程式</span><span class="sxs-lookup"><span data-stu-id="52251-129">Application</span></span> | <span data-ttu-id="52251-130">Incident。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="52251-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="52251-131">讀取和寫入所有事件</span><span class="sxs-lookup"><span data-stu-id="52251-131">Read and write all incidents</span></span>
<span data-ttu-id="52251-132">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="52251-132">Delegated (work or school account)</span></span> | <span data-ttu-id="52251-133">事件。讀取</span><span class="sxs-lookup"><span data-stu-id="52251-133">Incident.Read</span></span> | <span data-ttu-id="52251-134">讀取事件</span><span class="sxs-lookup"><span data-stu-id="52251-134">Read incidents</span></span>
<span data-ttu-id="52251-135">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="52251-135">Delegated (work or school account)</span></span> | <span data-ttu-id="52251-136">Incident。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="52251-136">Incident.ReadWrite</span></span> | <span data-ttu-id="52251-137">讀取和寫入事件</span><span class="sxs-lookup"><span data-stu-id="52251-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="52251-138">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="52251-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="52251-139">使用者必須要有入口網站中的事件的「查看」許可權。</span><span class="sxs-lookup"><span data-stu-id="52251-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="52251-140">回應只會包含使用者所公開的事件。</span><span class="sxs-lookup"><span data-stu-id="52251-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="52251-141">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="52251-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="52251-142">要求標頭</span><span class="sxs-lookup"><span data-stu-id="52251-142">Request headers</span></span>

<span data-ttu-id="52251-143">名稱</span><span class="sxs-lookup"><span data-stu-id="52251-143">Name</span></span> | <span data-ttu-id="52251-144">類型</span><span class="sxs-lookup"><span data-stu-id="52251-144">Type</span></span> | <span data-ttu-id="52251-145">描述</span><span class="sxs-lookup"><span data-stu-id="52251-145">Description</span></span>
-|-|-
<span data-ttu-id="52251-146">授權</span><span class="sxs-lookup"><span data-stu-id="52251-146">Authorization</span></span> | <span data-ttu-id="52251-147">字串</span><span class="sxs-lookup"><span data-stu-id="52251-147">String</span></span> | <span data-ttu-id="52251-148">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="52251-148">Bearer {token}.</span></span> <span data-ttu-id="52251-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="52251-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="52251-150">要求正文</span><span class="sxs-lookup"><span data-stu-id="52251-150">Request body</span></span>

<span data-ttu-id="52251-151">無。</span><span class="sxs-lookup"><span data-stu-id="52251-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="52251-152">回應</span><span class="sxs-lookup"><span data-stu-id="52251-152">Response</span></span>

<span data-ttu-id="52251-153">如果成功，此方法會傳回 `200 OK` ，以及回應內文中的 [事件](api-incident.md) 清單。</span><span class="sxs-lookup"><span data-stu-id="52251-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="52251-154">架構對應</span><span class="sxs-lookup"><span data-stu-id="52251-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="52251-155">事件中繼資料</span><span class="sxs-lookup"><span data-stu-id="52251-155">Incident metadata</span></span>

<span data-ttu-id="52251-156">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="52251-156">Field name</span></span> | <span data-ttu-id="52251-157">描述</span><span class="sxs-lookup"><span data-stu-id="52251-157">Description</span></span> | <span data-ttu-id="52251-158">範例值</span><span class="sxs-lookup"><span data-stu-id="52251-158">Example value</span></span>
-|-|-
<span data-ttu-id="52251-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="52251-159">incidentId</span></span> | <span data-ttu-id="52251-160">代表事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="52251-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="52251-161">924565</span><span class="sxs-lookup"><span data-stu-id="52251-161">924565</span></span>
<span data-ttu-id="52251-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="52251-162">redirectIncidentId</span></span> | <span data-ttu-id="52251-163">只會填入事件處理邏輯的一部分，以案例事件與另一個事件群組在一起。</span><span class="sxs-lookup"><span data-stu-id="52251-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="52251-164">924569</span><span class="sxs-lookup"><span data-stu-id="52251-164">924569</span></span>
<span data-ttu-id="52251-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="52251-165">incidentName</span></span> | <span data-ttu-id="52251-166">每個事件可用的字串值。</span><span class="sxs-lookup"><span data-stu-id="52251-166">String value available for every incident.</span></span> | <span data-ttu-id="52251-167">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="52251-167">Ransomware activity</span></span>
<span data-ttu-id="52251-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="52251-168">createdTime</span></span> | <span data-ttu-id="52251-169">第一次建立事件的時間。</span><span class="sxs-lookup"><span data-stu-id="52251-169">Time when incident was first created.</span></span> | <span data-ttu-id="52251-170">2020-09-06T14：46： 57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="52251-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="52251-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="52251-171">lastUpdateTime</span></span> | <span data-ttu-id="52251-172">最後在後端更新事件的時間。</span><span class="sxs-lookup"><span data-stu-id="52251-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="52251-173">當您為已檢索事件的時間範圍設定要求參數時，可以使用此欄位。</span><span class="sxs-lookup"><span data-stu-id="52251-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="52251-174">2020-09-06T14：46： 57.29 Z</span><span class="sxs-lookup"><span data-stu-id="52251-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="52251-175">分配</span><span class="sxs-lookup"><span data-stu-id="52251-175">assignedTo</span></span> | <span data-ttu-id="52251-176">事件的擁有者，如果未指派任何擁有者，則 *為 null* 。</span><span class="sxs-lookup"><span data-stu-id="52251-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="52251-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="52251-177">secop2@contoso.com</span></span>
<span data-ttu-id="52251-178">分類</span><span class="sxs-lookup"><span data-stu-id="52251-178">classification</span></span> | <span data-ttu-id="52251-179">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="52251-179">The specification for the incident.</span></span> <span data-ttu-id="52251-180">屬性值為： *Unknown*、 *FalsePositive*、 *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="52251-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="52251-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="52251-181">Unknown</span></span>
<span data-ttu-id="52251-182">測定</span><span class="sxs-lookup"><span data-stu-id="52251-182">determination</span></span> | <span data-ttu-id="52251-183">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="52251-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="52251-184">屬性值為： *NotAvailable*、 *Apt*、 *惡意* 代碼、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *其他*</span><span class="sxs-lookup"><span data-stu-id="52251-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="52251-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="52251-185">NotAvailable</span></span>
<span data-ttu-id="52251-186">地位</span><span class="sxs-lookup"><span data-stu-id="52251-186">status</span></span> | <span data-ttu-id="52251-187">將事件分類 (*為使用* 中，或 *已解決*) 。</span><span class="sxs-lookup"><span data-stu-id="52251-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="52251-188">它可以協助您組織和管理事件的回應。</span><span class="sxs-lookup"><span data-stu-id="52251-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="52251-189">作用中</span><span class="sxs-lookup"><span data-stu-id="52251-189">Active</span></span>
<span data-ttu-id="52251-190">嚴重性</span><span class="sxs-lookup"><span data-stu-id="52251-190">severity</span></span> | <span data-ttu-id="52251-191">會指出對資產的可能影響。</span><span class="sxs-lookup"><span data-stu-id="52251-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="52251-192">嚴重程度越高，影響越大。</span><span class="sxs-lookup"><span data-stu-id="52251-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="52251-193">通常較高的嚴重性專案需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="52251-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="52251-194">下列其中一個值： *資訊*、 *低*、\* 中和 *高*。</span><span class="sxs-lookup"><span data-stu-id="52251-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="52251-195">中</span><span class="sxs-lookup"><span data-stu-id="52251-195">Medium</span></span>
<span data-ttu-id="52251-196">標籤</span><span class="sxs-lookup"><span data-stu-id="52251-196">tags</span></span> | <span data-ttu-id="52251-197">與事件關聯之自訂標記的陣列，例如，用來標示具有共同特性的事件群組。</span><span class="sxs-lookup"><span data-stu-id="52251-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="52251-198">警報</span><span class="sxs-lookup"><span data-stu-id="52251-198">alerts</span></span> | <span data-ttu-id="52251-199">包含與該事件相關的所有警示的陣列，以及其他資訊，例如嚴重性、警示中所涉及的實體及警示來源。</span><span class="sxs-lookup"><span data-stu-id="52251-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="52251-200">\[\] (查看以下警示欄位的詳細資料) </span><span class="sxs-lookup"><span data-stu-id="52251-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="52251-201">警示中繼資料</span><span class="sxs-lookup"><span data-stu-id="52251-201">Alerts metadata</span></span>

<span data-ttu-id="52251-202">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="52251-202">Field name</span></span> | <span data-ttu-id="52251-203">描述</span><span class="sxs-lookup"><span data-stu-id="52251-203">Description</span></span> | <span data-ttu-id="52251-204">範例值</span><span class="sxs-lookup"><span data-stu-id="52251-204">Example value</span></span>
-|-|-
<span data-ttu-id="52251-205">為 alertid</span><span class="sxs-lookup"><span data-stu-id="52251-205">alertId</span></span> | <span data-ttu-id="52251-206">代表警示的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="52251-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="52251-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="52251-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="52251-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="52251-208">incidentId</span></span> | <span data-ttu-id="52251-209">代表此警示相關聯之事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="52251-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="52251-210">924565</span><span class="sxs-lookup"><span data-stu-id="52251-210">924565</span></span>
<span data-ttu-id="52251-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="52251-211">serviceSource</span></span> | <span data-ttu-id="52251-212">警示產生來源的服務，例如 Microsoft Defender for Endpoint、Microsoft Cloud App Security、Microsoft Defender 身分識別或 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="52251-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="52251-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="52251-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="52251-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="52251-214">creationTime</span></span> | <span data-ttu-id="52251-215">第一次建立警示的時間。</span><span class="sxs-lookup"><span data-stu-id="52251-215">Time when alert was first created.</span></span> | <span data-ttu-id="52251-216">2020-09-06T14：46： 55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="52251-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="52251-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="52251-217">lastUpdatedTime</span></span> | <span data-ttu-id="52251-218">後端最後更新警示的時間。</span><span class="sxs-lookup"><span data-stu-id="52251-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="52251-219">2020-09-06T14：46： 57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="52251-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="52251-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="52251-220">resolvedTime</span></span> | <span data-ttu-id="52251-221">解決警示的時間。</span><span class="sxs-lookup"><span data-stu-id="52251-221">Time when alert was resolved.</span></span> | <span data-ttu-id="52251-222">2020-09-10T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="52251-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="52251-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="52251-223">firstActivity</span></span> | <span data-ttu-id="52251-224">警示第一次報告在後端更新活動的時間。</span><span class="sxs-lookup"><span data-stu-id="52251-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="52251-225">2020-09-04T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="52251-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="52251-226">標題</span><span class="sxs-lookup"><span data-stu-id="52251-226">title</span></span> | <span data-ttu-id="52251-227">可用於每個警示的簡短識別字串值。</span><span class="sxs-lookup"><span data-stu-id="52251-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="52251-228">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="52251-228">Ransomware activity</span></span>
<span data-ttu-id="52251-229">描述</span><span class="sxs-lookup"><span data-stu-id="52251-229">description</span></span> | <span data-ttu-id="52251-230">描述每個警示的字串值。</span><span class="sxs-lookup"><span data-stu-id="52251-230">String value describing each alert.</span></span> | <span data-ttu-id="52251-231">User Test 使用者 2 (testUser2@contoso.com) 會操縱使用多個副檔名（以不 *常見副檔名為* 結尾）的99檔案。</span><span class="sxs-lookup"><span data-stu-id="52251-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="52251-232">這是不尋常的檔案運算元目，也表示有潛在的勒索軟體攻擊。</span><span class="sxs-lookup"><span data-stu-id="52251-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="52251-233">類別</span><span class="sxs-lookup"><span data-stu-id="52251-233">category</span></span> | <span data-ttu-id="52251-234">攻擊在終止鏈中的進展程度的視覺和數值視圖。</span><span class="sxs-lookup"><span data-stu-id="52251-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="52251-235">對應至 [MITRE ATT&CK™ framework](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="52251-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="52251-236">影響</span><span class="sxs-lookup"><span data-stu-id="52251-236">Impact</span></span>
<span data-ttu-id="52251-237">地位</span><span class="sxs-lookup"><span data-stu-id="52251-237">status</span></span> | <span data-ttu-id="52251-238">將警示分類 (為新 *、使用中或\*\*已解決*) 。</span><span class="sxs-lookup"><span data-stu-id="52251-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="52251-239">它可以協助您組織和管理提醒的回應。</span><span class="sxs-lookup"><span data-stu-id="52251-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="52251-240">新增</span><span class="sxs-lookup"><span data-stu-id="52251-240">New</span></span>
<span data-ttu-id="52251-241">嚴重性</span><span class="sxs-lookup"><span data-stu-id="52251-241">severity</span></span> | <span data-ttu-id="52251-242">會指出對資產的可能影響。</span><span class="sxs-lookup"><span data-stu-id="52251-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="52251-243">嚴重程度越高，影響越大。</span><span class="sxs-lookup"><span data-stu-id="52251-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="52251-244">通常較高的嚴重性專案需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="52251-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="52251-245">下列其中一個值： *資訊*、 *低*、\* 中和 *高*。</span><span class="sxs-lookup"><span data-stu-id="52251-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="52251-246">中</span><span class="sxs-lookup"><span data-stu-id="52251-246">Medium</span></span>
<span data-ttu-id="52251-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="52251-247">investigationId</span></span> | <span data-ttu-id="52251-248">此警示所觸發的自動調查識別碼。</span><span class="sxs-lookup"><span data-stu-id="52251-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="52251-249">1234</span><span class="sxs-lookup"><span data-stu-id="52251-249">1234</span></span>
<span data-ttu-id="52251-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="52251-250">investigationState</span></span> | <span data-ttu-id="52251-251">調查目前狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="52251-251">Information on the investigation's current status.</span></span> <span data-ttu-id="52251-252">下列其中一個值： *Unknown*、*離職*、 *SuccessfullyRemediated*、*良性*、*失敗*、 *PartiallyRemediated*、執行 *、* *PendingApproval*、 *PendingResource*、 *PartiallyInvestigated*、 *TerminatedByUser*、 *TerminatedBySystem*、InnerFailure *、PreexistingAlert*、UnsupportedOs、UnsupportedAlertType、SuppressedAlert、 *、*、、、、、、、    </span><span class="sxs-lookup"><span data-stu-id="52251-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="52251-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="52251-253">UnsupportedAlertType</span></span>
<span data-ttu-id="52251-254">分類</span><span class="sxs-lookup"><span data-stu-id="52251-254">classification</span></span> | <span data-ttu-id="52251-255">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="52251-255">The specification for the incident.</span></span> <span data-ttu-id="52251-256">屬性值為： *Unknown*、 *FalsePositive*、 *TruePositive* 或 *null*</span><span class="sxs-lookup"><span data-stu-id="52251-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="52251-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="52251-257">Unknown</span></span>
<span data-ttu-id="52251-258">測定</span><span class="sxs-lookup"><span data-stu-id="52251-258">determination</span></span> | <span data-ttu-id="52251-259">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="52251-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="52251-260">屬性值為： *NotAvailable*、 *Apt*、 *惡意* 代碼、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *Other* 或  *null*</span><span class="sxs-lookup"><span data-stu-id="52251-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="52251-261">容易</span><span class="sxs-lookup"><span data-stu-id="52251-261">Apt</span></span>
<span data-ttu-id="52251-262">分配</span><span class="sxs-lookup"><span data-stu-id="52251-262">assignedTo</span></span> | <span data-ttu-id="52251-263">事件的擁有者，如果未指派任何擁有者，則 *為 null* 。</span><span class="sxs-lookup"><span data-stu-id="52251-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="52251-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="52251-264">secop2@contoso.com</span></span>
<span data-ttu-id="52251-265">actorName</span><span class="sxs-lookup"><span data-stu-id="52251-265">actorName</span></span> | <span data-ttu-id="52251-266">與此警示相關聯的活動群組（若有的話）。</span><span class="sxs-lookup"><span data-stu-id="52251-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="52251-267">硼</span><span class="sxs-lookup"><span data-stu-id="52251-267">BORON</span></span>
<span data-ttu-id="52251-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="52251-268">threatFamilyName</span></span> | <span data-ttu-id="52251-269">與此警示相關聯的威脅系列。</span><span class="sxs-lookup"><span data-stu-id="52251-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="52251-270">Null</span><span class="sxs-lookup"><span data-stu-id="52251-270">null</span></span>
<span data-ttu-id="52251-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="52251-271">mitreTechniques</span></span> | <span data-ttu-id="52251-272">攻擊技巧，與 [MITRE ATT&](https://attack.mitre.org/)™ framework 對齊。</span><span class="sxs-lookup"><span data-stu-id="52251-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="52251-273">設備</span><span class="sxs-lookup"><span data-stu-id="52251-273">devices</span></span> | <span data-ttu-id="52251-274">傳送與該事件相關之提醒的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="52251-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="52251-275">\[\] (查看下列實體欄位的詳細資料) </span><span class="sxs-lookup"><span data-stu-id="52251-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="52251-276">裝置格式</span><span class="sxs-lookup"><span data-stu-id="52251-276">Device format</span></span>

<span data-ttu-id="52251-277">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="52251-277">Field name</span></span> | <span data-ttu-id="52251-278">描述</span><span class="sxs-lookup"><span data-stu-id="52251-278">Description</span></span> | <span data-ttu-id="52251-279">範例值</span><span class="sxs-lookup"><span data-stu-id="52251-279">Example value</span></span>
-|-|-
<span data-ttu-id="52251-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="52251-280">DeviceId</span></span> | <span data-ttu-id="52251-281">在 Microsoft Defender for Endpoint 中指定的裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="52251-281">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="52251-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="52251-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="52251-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="52251-283">aadDeviceId</span></span> |  <span data-ttu-id="52251-284">在 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)中指定的裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="52251-284">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="52251-285">僅適用于已加入網域的裝置。</span><span class="sxs-lookup"><span data-stu-id="52251-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="52251-286">Null</span><span class="sxs-lookup"><span data-stu-id="52251-286">null</span></span>
<span data-ttu-id="52251-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="52251-287">deviceDnsName</span></span> | <span data-ttu-id="52251-288">裝置的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="52251-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="52251-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="52251-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="52251-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="52251-290">osPlatform</span></span> | <span data-ttu-id="52251-291">裝置正在執行的作業系統平臺。</span><span class="sxs-lookup"><span data-stu-id="52251-291">The OS platform the device is running.</span></span>| <span data-ttu-id="52251-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="52251-292">WindowsServer2016</span></span>
<span data-ttu-id="52251-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="52251-293">osBuild</span></span> | <span data-ttu-id="52251-294">裝置執行的 OS 組建版本。</span><span class="sxs-lookup"><span data-stu-id="52251-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="52251-295">14393</span><span class="sxs-lookup"><span data-stu-id="52251-295">14393</span></span>
<span data-ttu-id="52251-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="52251-296">rbacGroupName</span></span> | <span data-ttu-id="52251-297">以 [角色為基礎的存取控制](/azure/role-based-access-control/overview) (與裝置相關聯的 RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="52251-297">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="52251-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="52251-298">WDATP-Ring0</span></span>
<span data-ttu-id="52251-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="52251-299">firstSeen</span></span> | <span data-ttu-id="52251-300">第一次看到裝置的時間。</span><span class="sxs-lookup"><span data-stu-id="52251-300">Time when device was first seen.</span></span> | <span data-ttu-id="52251-301">2020-02-06T14：16： 01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="52251-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="52251-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="52251-302">healthStatus</span></span> | <span data-ttu-id="52251-303">裝置的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="52251-303">The health state of the device.</span></span> | <span data-ttu-id="52251-304">作用中</span><span class="sxs-lookup"><span data-stu-id="52251-304">Active</span></span>
<span data-ttu-id="52251-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="52251-305">riskScore</span></span> | <span data-ttu-id="52251-306">裝置的風險分數。</span><span class="sxs-lookup"><span data-stu-id="52251-306">The risk score for the  device.</span></span> | <span data-ttu-id="52251-307">高</span><span class="sxs-lookup"><span data-stu-id="52251-307">High</span></span>
<span data-ttu-id="52251-308">實體</span><span class="sxs-lookup"><span data-stu-id="52251-308">entities</span></span> | <span data-ttu-id="52251-309">已識別為特定警示之一部分或與其相關的所有實體。</span><span class="sxs-lookup"><span data-stu-id="52251-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="52251-310">\[\] (查看下列實體欄位的詳細資料) </span><span class="sxs-lookup"><span data-stu-id="52251-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="52251-311">實體格式</span><span class="sxs-lookup"><span data-stu-id="52251-311">Entity Format</span></span>

<span data-ttu-id="52251-312">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="52251-312">Field name</span></span> | <span data-ttu-id="52251-313">描述</span><span class="sxs-lookup"><span data-stu-id="52251-313">Description</span></span> | <span data-ttu-id="52251-314">範例值</span><span class="sxs-lookup"><span data-stu-id="52251-314">Example value</span></span>
-|-|-
<span data-ttu-id="52251-315">entityType</span><span class="sxs-lookup"><span data-stu-id="52251-315">entityType</span></span> | <span data-ttu-id="52251-316">識別為屬於指定警示或與其相關的實體。</span><span class="sxs-lookup"><span data-stu-id="52251-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="52251-317">屬性值包括： *User*， *Ip*， *Url*， *File*， *Process*， *MailBox*， *MailMessage*， *MailCluster*， *Registry*</span><span class="sxs-lookup"><span data-stu-id="52251-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="52251-318">使用者</span><span class="sxs-lookup"><span data-stu-id="52251-318">User</span></span>
<span data-ttu-id="52251-319">sha1</span><span class="sxs-lookup"><span data-stu-id="52251-319">sha1</span></span> | <span data-ttu-id="52251-320">當 entityType 為 *File* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="52251-321">與檔案或處理常式相關聯之警示的檔案雜湊。</span><span class="sxs-lookup"><span data-stu-id="52251-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="52251-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="52251-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="52251-323">sha256</span><span class="sxs-lookup"><span data-stu-id="52251-323">sha256</span></span> | <span data-ttu-id="52251-324">當 entityType 為 *File* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="52251-325">與檔案或處理常式相關聯之警示的檔案雜湊。</span><span class="sxs-lookup"><span data-stu-id="52251-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="52251-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="52251-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="52251-327">檔案名</span><span class="sxs-lookup"><span data-stu-id="52251-327">fileName</span></span> | <span data-ttu-id="52251-328">當 entityType 為 *File* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="52251-329">與檔案或處理常式相關聯的警示檔案名</span><span class="sxs-lookup"><span data-stu-id="52251-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="52251-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="52251-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="52251-331">filePath</span><span class="sxs-lookup"><span data-stu-id="52251-331">filePath</span></span> | <span data-ttu-id="52251-332">當 entityType 為 *File* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="52251-333">與檔案或處理常式相關聯之警示的檔路徑</span><span class="sxs-lookup"><span data-stu-id="52251-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="52251-334">C： \\ \ agent_work_temp \deploy\system\2020-09-06 12_14_54 Out</span><span class="sxs-lookup"><span data-stu-id="52251-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="52251-335">Id</span><span class="sxs-lookup"><span data-stu-id="52251-335">processId</span></span> | <span data-ttu-id="52251-336">可用於 entityType 為 *處理* 程式。</span><span class="sxs-lookup"><span data-stu-id="52251-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="52251-337">24348</span><span class="sxs-lookup"><span data-stu-id="52251-337">24348</span></span>
<span data-ttu-id="52251-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="52251-338">processCommandLine</span></span> | <span data-ttu-id="52251-339">可用於 entityType 為 *處理* 程式。</span><span class="sxs-lookup"><span data-stu-id="52251-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="52251-340">「檔案可供下載1911150169.exe」 \_</span><span class="sxs-lookup"><span data-stu-id="52251-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="52251-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="52251-341">processCreationTime</span></span> | <span data-ttu-id="52251-342">可用於 entityType 為 *處理* 程式。</span><span class="sxs-lookup"><span data-stu-id="52251-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="52251-343">2020-18T03：25： 38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="52251-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="52251-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="52251-344">parentProcessId</span></span> | <span data-ttu-id="52251-345">可用於 entityType 為 *處理* 程式。</span><span class="sxs-lookup"><span data-stu-id="52251-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="52251-346">16840</span><span class="sxs-lookup"><span data-stu-id="52251-346">16840</span></span>
<span data-ttu-id="52251-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="52251-347">parentProcessCreationTime</span></span> | <span data-ttu-id="52251-348">可用於 entityType 為 *處理* 程式。</span><span class="sxs-lookup"><span data-stu-id="52251-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="52251-349">2020-07-18T02：12： 32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="52251-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="52251-350">址</span><span class="sxs-lookup"><span data-stu-id="52251-350">ipAddress</span></span> | <span data-ttu-id="52251-351">可在 entityType 為 *Ip* 時使用。</span><span class="sxs-lookup"><span data-stu-id="52251-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="52251-352">與網路事件相關聯之警示的 IP 位址，例如與 *惡意網路目標的通訊*。</span><span class="sxs-lookup"><span data-stu-id="52251-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="52251-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="52251-353">62.216.203.204</span></span>
<span data-ttu-id="52251-354">URL</span><span class="sxs-lookup"><span data-stu-id="52251-354">url</span></span> | <span data-ttu-id="52251-355">可供 entityType 為 *Url*。</span><span class="sxs-lookup"><span data-stu-id="52251-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="52251-356">與網路事件相關聯之警示的 Url，例如， *與惡意網路目標的通訊*。</span><span class="sxs-lookup"><span data-stu-id="52251-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="52251-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="52251-357">down.esales360.cn</span></span>
<span data-ttu-id="52251-358">名</span><span class="sxs-lookup"><span data-stu-id="52251-358">accountName</span></span> | <span data-ttu-id="52251-359">當 entityType 為 *User* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="52251-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="52251-360">testUser2</span></span>
<span data-ttu-id="52251-361">domainName</span><span class="sxs-lookup"><span data-stu-id="52251-361">domainName</span></span> | <span data-ttu-id="52251-362">當 entityType 為 *User* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="52251-363">東歐公司 contoso</span><span class="sxs-lookup"><span data-stu-id="52251-363">europe.corp.contoso</span></span>
<span data-ttu-id="52251-364">userSid</span><span class="sxs-lookup"><span data-stu-id="52251-364">userSid</span></span> | <span data-ttu-id="52251-365">當 entityType 為 *User* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="52251-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="52251-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="52251-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="52251-367">aadUserId</span></span> | <span data-ttu-id="52251-368">當 entityType 為 *User* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="52251-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="52251-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="52251-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="52251-370">userPrincipalName</span></span> | <span data-ttu-id="52251-371">當 entityType 是 *使用者* / *MailBox* / *MailMessage* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="52251-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="52251-372">testUser2@contoso.com</span></span>
<span data-ttu-id="52251-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="52251-373">mailboxDisplayName</span></span> | <span data-ttu-id="52251-374">在 *MailBox* entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="52251-375">測試使用者2</span><span class="sxs-lookup"><span data-stu-id="52251-375">test User2</span></span>
<span data-ttu-id="52251-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="52251-376">mailboxAddress</span></span> | <span data-ttu-id="52251-377">當 entityType 是 *使用者* / *MailBox* / *MailMessage* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="52251-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="52251-378">testUser2@contoso.com</span></span>
<span data-ttu-id="52251-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="52251-379">clusterBy</span></span> | <span data-ttu-id="52251-380">可用於  *MailCluster* 的 entityType。</span><span class="sxs-lookup"><span data-stu-id="52251-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="52251-381">話題P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="52251-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="52251-382">sender</span><span class="sxs-lookup"><span data-stu-id="52251-382">sender</span></span> | <span data-ttu-id="52251-383">當 entityType 是 *使用者* / *MailBox* / *MailMessage* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="52251-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="52251-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="52251-385">recipient</span><span class="sxs-lookup"><span data-stu-id="52251-385">recipient</span></span> | <span data-ttu-id="52251-386">在 *MailMessage* entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="52251-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="52251-387">testUser2@contoso.com</span></span>
<span data-ttu-id="52251-388">主題</span><span class="sxs-lookup"><span data-stu-id="52251-388">subject</span></span> | <span data-ttu-id="52251-389">在 *MailMessage* entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="52251-390">\[外部 \] 注意</span><span class="sxs-lookup"><span data-stu-id="52251-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="52251-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="52251-391">deliveryAction</span></span> | <span data-ttu-id="52251-392">在 *MailMessage* entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="52251-393">已傳遞</span><span class="sxs-lookup"><span data-stu-id="52251-393">Delivered</span></span>
<span data-ttu-id="52251-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="52251-394">securityGroupId</span></span> | <span data-ttu-id="52251-395">在  *SecurityGroup* entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="52251-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="52251-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="52251-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="52251-397">securityGroupName</span></span> | <span data-ttu-id="52251-398">在  *SecurityGroup* entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="52251-399">網路設定運算子</span><span class="sxs-lookup"><span data-stu-id="52251-399">Network Configuration Operators</span></span>
<span data-ttu-id="52251-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="52251-400">registryHive</span></span> | <span data-ttu-id="52251-401">當 entityType 為  *Registry* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="52251-402">HKEY \_ 本機 \_ 電腦</span><span class="sxs-lookup"><span data-stu-id="52251-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="52251-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="52251-403">registryKey</span></span> | <span data-ttu-id="52251-404">當 entityType 為  *Registry* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="52251-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="52251-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="52251-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="52251-406">registryValueType</span></span> | <span data-ttu-id="52251-407">當 entityType 為  *Registry* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="52251-408">字串</span><span class="sxs-lookup"><span data-stu-id="52251-408">String</span></span>
<span data-ttu-id="52251-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="52251-409">registryValue</span></span> | <span data-ttu-id="52251-410">當 entityType 為  *Registry* 時可用。</span><span class="sxs-lookup"><span data-stu-id="52251-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="52251-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="52251-411">31-00-00-00</span></span>
<span data-ttu-id="52251-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="52251-412">deviceId</span></span> | <span data-ttu-id="52251-413">與實體相關之裝置的識別碼（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="52251-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="52251-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="52251-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="52251-415">範例</span><span class="sxs-lookup"><span data-stu-id="52251-415">Example</span></span>

<span data-ttu-id="52251-416">**請求**</span><span class="sxs-lookup"><span data-stu-id="52251-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="52251-417">**回應**</span><span class="sxs-lookup"><span data-stu-id="52251-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="52251-418">相關文章</span><span class="sxs-lookup"><span data-stu-id="52251-418">Related articles</span></span>

- [<span data-ttu-id="52251-419">存取 Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="52251-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="52251-420">深入瞭解 API 限制和授權</span><span class="sxs-lookup"><span data-stu-id="52251-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="52251-421">瞭解錯誤碼</span><span class="sxs-lookup"><span data-stu-id="52251-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="52251-422">事件概觀</span><span class="sxs-lookup"><span data-stu-id="52251-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="52251-423">事件 API</span><span class="sxs-lookup"><span data-stu-id="52251-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="52251-424">更新事件 API</span><span class="sxs-lookup"><span data-stu-id="52251-424">Update incident API</span></span>](api-update-incidents.md)