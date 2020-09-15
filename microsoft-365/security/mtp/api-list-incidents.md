---
title: 在 Microsoft 威脅防護中列出事件 API
description: 瞭解如何在 Microsoft 威脅防護中列出事件 API
keywords: 清單、事件、事件、api
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
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775108"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="10223-104">在 Microsoft 威脅防護中列出事件 API</span><span class="sxs-lookup"><span data-stu-id="10223-104">List incidents API in Microsoft Threat Protection</span></span>

<span data-ttu-id="10223-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="10223-105">**Applies to:**</span></span>

- <span data-ttu-id="10223-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="10223-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10223-107">一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="10223-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="10223-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="10223-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="10223-109">API 描述</span><span class="sxs-lookup"><span data-stu-id="10223-109">API description</span></span>

<span data-ttu-id="10223-110">Incident API 可讓您排序事件，以排定優先順序並建立已獲悉的 cybersecurity 回應。</span><span class="sxs-lookup"><span data-stu-id="10223-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="10223-111">它會公開從您的環境保留原則中所指定的時間範圍內，以裝置、電子郵件帳戶和網路中的使用者標示的事件集合。</span><span class="sxs-lookup"><span data-stu-id="10223-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="10223-112">最近的事件會顯示在清單頂端。</span><span class="sxs-lookup"><span data-stu-id="10223-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="10223-113">每個事件都包含相關警示的陣列及其相關實體。</span><span class="sxs-lookup"><span data-stu-id="10223-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="10223-114">API 支援下列 **OData** 運算子：</span><span class="sxs-lookup"><span data-stu-id="10223-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="10223-115">```$filter``` on： ```lastUpdateTime``` 、 ```createdTime``` ```status``` 和 ```assignedTo``` 屬性。</span><span class="sxs-lookup"><span data-stu-id="10223-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="10223-116">```$top```**100**的最大值為</span><span class="sxs-lookup"><span data-stu-id="10223-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="10223-117">限制</span><span class="sxs-lookup"><span data-stu-id="10223-117">Limitations</span></span>

1. <span data-ttu-id="10223-118">頁面大小上限為 **100 事件**。</span><span class="sxs-lookup"><span data-stu-id="10223-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="10223-119">要求的最大速率為 **每分鐘50個通話** ， **每小時1500個通話**。</span><span class="sxs-lookup"><span data-stu-id="10223-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="10223-120">權限</span><span class="sxs-lookup"><span data-stu-id="10223-120">Permissions</span></span>

<span data-ttu-id="10223-121">需要有下列其中一個許可權才能呼叫此 API。</span><span class="sxs-lookup"><span data-stu-id="10223-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="10223-122">若要深入瞭解，包括如何選擇許可權，請參閱 [Access Microsoft 威脅防護 APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="10223-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="10223-123">許可權類型</span><span class="sxs-lookup"><span data-stu-id="10223-123">Permission type</span></span> |   <span data-ttu-id="10223-124">權限</span><span class="sxs-lookup"><span data-stu-id="10223-124">Permission</span></span>  |   <span data-ttu-id="10223-125">許可權顯示名稱</span><span class="sxs-lookup"><span data-stu-id="10223-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="10223-126">應用程式</span><span class="sxs-lookup"><span data-stu-id="10223-126">Application</span></span> |   <span data-ttu-id="10223-127">Incident。已讀取。所有</span><span class="sxs-lookup"><span data-stu-id="10223-127">Incident.Read.All</span></span> | <span data-ttu-id="10223-128">「讀取所有事件」</span><span class="sxs-lookup"><span data-stu-id="10223-128">'Read all incidents'</span></span>
<span data-ttu-id="10223-129">應用程式</span><span class="sxs-lookup"><span data-stu-id="10223-129">Application</span></span> |   <span data-ttu-id="10223-130">Incident。 ReadWrite。</span><span class="sxs-lookup"><span data-stu-id="10223-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="10223-131">「讀取和寫入所有事件」</span><span class="sxs-lookup"><span data-stu-id="10223-131">'Read and write all incidents'</span></span>
<span data-ttu-id="10223-132">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="10223-132">Delegated (work or school account)</span></span> | <span data-ttu-id="10223-133">事件。讀取</span><span class="sxs-lookup"><span data-stu-id="10223-133">Incident.Read</span></span> | <span data-ttu-id="10223-134">「讀取事件」</span><span class="sxs-lookup"><span data-stu-id="10223-134">'Read incidents'</span></span>
<span data-ttu-id="10223-135">委派 (工作或學校帳戶) </span><span class="sxs-lookup"><span data-stu-id="10223-135">Delegated (work or school account)</span></span> | <span data-ttu-id="10223-136">Incident。 ReadWrite</span><span class="sxs-lookup"><span data-stu-id="10223-136">Incident.ReadWrite</span></span> | <span data-ttu-id="10223-137">「讀取和寫入事件」</span><span class="sxs-lookup"><span data-stu-id="10223-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="10223-138">使用使用者認證取得權杖時：</span><span class="sxs-lookup"><span data-stu-id="10223-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="10223-139">使用者必須要有入口網站中的事件的「查看」許可權。</span><span class="sxs-lookup"><span data-stu-id="10223-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="10223-140">回應只會包含使用者所公開的事件。</span><span class="sxs-lookup"><span data-stu-id="10223-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="10223-141">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="10223-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="10223-142">要求標頭</span><span class="sxs-lookup"><span data-stu-id="10223-142">Request headers</span></span>

<span data-ttu-id="10223-143">名稱</span><span class="sxs-lookup"><span data-stu-id="10223-143">Name</span></span> | <span data-ttu-id="10223-144">類型</span><span class="sxs-lookup"><span data-stu-id="10223-144">Type</span></span> | <span data-ttu-id="10223-145">描述</span><span class="sxs-lookup"><span data-stu-id="10223-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="10223-146">授權</span><span class="sxs-lookup"><span data-stu-id="10223-146">Authorization</span></span> | <span data-ttu-id="10223-147">字串</span><span class="sxs-lookup"><span data-stu-id="10223-147">String</span></span> | <span data-ttu-id="10223-148">載荷 {token}。</span><span class="sxs-lookup"><span data-stu-id="10223-148">Bearer {token}.</span></span> <span data-ttu-id="10223-149">**必要欄位**。</span><span class="sxs-lookup"><span data-stu-id="10223-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="10223-150">要求正文</span><span class="sxs-lookup"><span data-stu-id="10223-150">Request body</span></span>
<span data-ttu-id="10223-151">無。</span><span class="sxs-lookup"><span data-stu-id="10223-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="10223-152">回應</span><span class="sxs-lookup"><span data-stu-id="10223-152">Response</span></span>
<span data-ttu-id="10223-153">如果成功，這個方法會傳回 200 OK，以及回應內文中的 [事件](api-incident.md) 清單。</span><span class="sxs-lookup"><span data-stu-id="10223-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="10223-154">架構對應</span><span class="sxs-lookup"><span data-stu-id="10223-154">Schema mapping</span></span>

| <span data-ttu-id="10223-155">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="10223-155">Field name</span></span>                                | <span data-ttu-id="10223-156">描述</span><span class="sxs-lookup"><span data-stu-id="10223-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-157">範例值</span><span class="sxs-lookup"><span data-stu-id="10223-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="10223-158">**事件中繼資料**</span><span class="sxs-lookup"><span data-stu-id="10223-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="10223-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="10223-159">incidentId</span></span>                                | <span data-ttu-id="10223-160">代表該事件的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="10223-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-161">924565</span><span class="sxs-lookup"><span data-stu-id="10223-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="10223-162">redirectIncidentId</span></span>                        | <span data-ttu-id="10223-163">只會填入事件處理邏輯的一部分，以案例事件與另一個事件群組在一起。</span><span class="sxs-lookup"><span data-stu-id="10223-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="10223-164">924569</span><span class="sxs-lookup"><span data-stu-id="10223-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="10223-165">incidentName</span></span>                              | <span data-ttu-id="10223-166">每個事件可用的字串值。</span><span class="sxs-lookup"><span data-stu-id="10223-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="10223-167">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="10223-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="10223-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="10223-168">createdTime</span></span>                               | <span data-ttu-id="10223-169">第一次建立事件的時間。</span><span class="sxs-lookup"><span data-stu-id="10223-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="10223-170">2020-09-06T14：46： 57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="10223-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="10223-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="10223-171">lastUpdateTime</span></span>                            | <span data-ttu-id="10223-172">最後在後更新事件的時間。</span><span class="sxs-lookup"><span data-stu-id="10223-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="10223-173">當您為已取得事件的時間範圍設定 request 參數時，可以使用此欄位。</span><span class="sxs-lookup"><span data-stu-id="10223-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="10223-174">2020-09-06T14：46： 57.29 Z</span><span class="sxs-lookup"><span data-stu-id="10223-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="10223-175">分配</span><span class="sxs-lookup"><span data-stu-id="10223-175">assignedTo</span></span>                                | <span data-ttu-id="10223-176">事件的擁有者，如果未指派任何擁有者，則 *為 null* 。</span><span class="sxs-lookup"><span data-stu-id="10223-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="10223-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="10223-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="10223-178">分類</span><span class="sxs-lookup"><span data-stu-id="10223-178">classification</span></span>                            | <span data-ttu-id="10223-179">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="10223-179">The specification for the incident.</span></span> <span data-ttu-id="10223-180">屬性值為： *Unknown*、 *FalsePositive*、 *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="10223-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="10223-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="10223-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="10223-182">測定</span><span class="sxs-lookup"><span data-stu-id="10223-182">determination</span></span>                             | <span data-ttu-id="10223-183">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="10223-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="10223-184">屬性值為： *NotAvailable*、 *Apt*、 *惡意*代碼、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *其他*</span><span class="sxs-lookup"><span data-stu-id="10223-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="10223-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="10223-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="10223-186">地位</span><span class="sxs-lookup"><span data-stu-id="10223-186">status</span></span>                                    | <span data-ttu-id="10223-187">將事件分類 (*為使用*中，或 *已解決*) 。</span><span class="sxs-lookup"><span data-stu-id="10223-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="10223-188">這可協助您組織和管理事件的回應。</span><span class="sxs-lookup"><span data-stu-id="10223-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="10223-189">作用中</span><span class="sxs-lookup"><span data-stu-id="10223-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-190">嚴重性</span><span class="sxs-lookup"><span data-stu-id="10223-190">severity</span></span>                                  | <span data-ttu-id="10223-191">會指出對資產的可能影響。</span><span class="sxs-lookup"><span data-stu-id="10223-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="10223-192">嚴重程度越高，影響越大。</span><span class="sxs-lookup"><span data-stu-id="10223-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="10223-193">通常較高的嚴重性專案需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="10223-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="10223-194">下列其中一個值： *資訊*、 *低*、\* 中和 *高*。</span><span class="sxs-lookup"><span data-stu-id="10223-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="10223-195">中</span><span class="sxs-lookup"><span data-stu-id="10223-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-196">標籤</span><span class="sxs-lookup"><span data-stu-id="10223-196">tags</span></span>                                      | <span data-ttu-id="10223-197">與事件關聯之自訂標記的陣列，例如，用來標示具有共同特性的事件群組。</span><span class="sxs-lookup"><span data-stu-id="10223-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-198">警報</span><span class="sxs-lookup"><span data-stu-id="10223-198">alerts</span></span>                                    | <span data-ttu-id="10223-199">與事件相關的所有警示及其他資訊的陣列，例如嚴重性、警示相關的實體，以及警示的來源。</span><span class="sxs-lookup"><span data-stu-id="10223-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="10223-200">\[\] (查看以下警示欄位的詳細資料) </span><span class="sxs-lookup"><span data-stu-id="10223-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="10223-201">**警示中繼資料**</span><span class="sxs-lookup"><span data-stu-id="10223-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="10223-202">為 alertid</span><span class="sxs-lookup"><span data-stu-id="10223-202">alertId</span></span>                                   | <span data-ttu-id="10223-203">代表警示的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="10223-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="10223-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="10223-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="10223-205">incidentId</span><span class="sxs-lookup"><span data-stu-id="10223-205">incidentId</span></span>                                | <span data-ttu-id="10223-206">代表此警示相關聯之事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="10223-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="10223-207">924565</span><span class="sxs-lookup"><span data-stu-id="10223-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-208">serviceSource</span><span class="sxs-lookup"><span data-stu-id="10223-208">serviceSource</span></span>                             | <span data-ttu-id="10223-209">警示產生來源的服務，例如 Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP 或 Office 365 ATP。</span><span class="sxs-lookup"><span data-stu-id="10223-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="10223-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="10223-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="10223-211">creationTime</span></span>                              | <span data-ttu-id="10223-212">第一次建立警示的時間。</span><span class="sxs-lookup"><span data-stu-id="10223-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="10223-213">2020-09-06T14：46： 55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="10223-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="10223-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="10223-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="10223-215">後端最後更新警示的時間。</span><span class="sxs-lookup"><span data-stu-id="10223-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="10223-216">2020-09-06T14：46： 57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="10223-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="10223-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="10223-217">resolvedTime</span></span>                              | <span data-ttu-id="10223-218">解決警示的時間。</span><span class="sxs-lookup"><span data-stu-id="10223-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="10223-219">2020-09-10T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="10223-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="10223-220">firstActivity</span></span>                             | <span data-ttu-id="10223-221">警示第一次報告在後端更新活動的時間。</span><span class="sxs-lookup"><span data-stu-id="10223-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="10223-222">2020-09-04T05：22：59Z</span><span class="sxs-lookup"><span data-stu-id="10223-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-223">標題</span><span class="sxs-lookup"><span data-stu-id="10223-223">title</span></span>                                     | <span data-ttu-id="10223-224">可用於每個警示的簡短識別字串值。</span><span class="sxs-lookup"><span data-stu-id="10223-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-225">勒索軟體活動</span><span class="sxs-lookup"><span data-stu-id="10223-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="10223-226">描述</span><span class="sxs-lookup"><span data-stu-id="10223-226">description</span></span>                               | <span data-ttu-id="10223-227">描述每個警示的字串值。</span><span class="sxs-lookup"><span data-stu-id="10223-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="10223-228">User Test 使用者 2 (testUser2@contoso.com) 會操縱使用多個副檔名（以不 *常見副檔名為*結尾）的99檔案。</span><span class="sxs-lookup"><span data-stu-id="10223-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="10223-229">這是不尋常的檔案運算元目，也表示有潛在的勒索軟體攻擊。</span><span class="sxs-lookup"><span data-stu-id="10223-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="10223-230">類別</span><span class="sxs-lookup"><span data-stu-id="10223-230">category</span></span>                                  | <span data-ttu-id="10223-231">攻擊在終止鏈中的進展程度的視覺和數值視圖。</span><span class="sxs-lookup"><span data-stu-id="10223-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="10223-232">對應至 [MITRE ATT&CK™ framework](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="10223-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="10223-233">影響</span><span class="sxs-lookup"><span data-stu-id="10223-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-234">地位</span><span class="sxs-lookup"><span data-stu-id="10223-234">status</span></span>                                    | <span data-ttu-id="10223-235">將警示分類 (*New*為新 *、使用中或\*\*已解決*) 。</span><span class="sxs-lookup"><span data-stu-id="10223-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="10223-236">這可協助您組織和管理提醒的回應。</span><span class="sxs-lookup"><span data-stu-id="10223-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="10223-237">新增</span><span class="sxs-lookup"><span data-stu-id="10223-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="10223-238">嚴重性</span><span class="sxs-lookup"><span data-stu-id="10223-238">severity</span></span>                                  | <span data-ttu-id="10223-239">會指出對資產的可能影響。</span><span class="sxs-lookup"><span data-stu-id="10223-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="10223-240">嚴重程度越高，影響越大。</span><span class="sxs-lookup"><span data-stu-id="10223-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="10223-241">通常較高的嚴重性專案需要最直接的注意。</span><span class="sxs-lookup"><span data-stu-id="10223-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="10223-242">下列其中一個值： *資訊*、 *低*、\* 中和 *高*。</span><span class="sxs-lookup"><span data-stu-id="10223-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="10223-243">中</span><span class="sxs-lookup"><span data-stu-id="10223-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="10223-244">investigationId</span></span>                           | <span data-ttu-id="10223-245">此警示所觸發的自動調查識別碼。</span><span class="sxs-lookup"><span data-stu-id="10223-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-246">1234</span><span class="sxs-lookup"><span data-stu-id="10223-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="10223-247">investigationState</span></span>                        | <span data-ttu-id="10223-248">調查目前狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="10223-248">Information on the investigation's current status.</span></span> <span data-ttu-id="10223-249">下列其中一項： *Unknown*、*離職*、 *SuccessfullyRemediated*、*良性*、 *Failed*、 *PartiallyRemediated*、 *Running* *PendingApproval*、 *PendingResource*、 *PartiallyInvestigated*、 *TerminatedByUser*、 *TerminatedBySystem*、InnerFailure、 *PreexistingAlert*、 *UnsupportedOs、UnsupportedAlertType*、SuppressedAlert、、 \* \*、、、、、、、 *PreexistingAlert* *UnsupportedOs* *UnsupportedAlertType*</span><span class="sxs-lookup"><span data-stu-id="10223-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="10223-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="10223-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-251">分類</span><span class="sxs-lookup"><span data-stu-id="10223-251">classification</span></span>                            | <span data-ttu-id="10223-252">事件的規格。</span><span class="sxs-lookup"><span data-stu-id="10223-252">The specification for the incident.</span></span> <span data-ttu-id="10223-253">屬性值為： *Unknown*、 *FalsePositive*、 *TruePositive* 或 *null*</span><span class="sxs-lookup"><span data-stu-id="10223-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="10223-254">Unknown</span><span class="sxs-lookup"><span data-stu-id="10223-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="10223-255">測定</span><span class="sxs-lookup"><span data-stu-id="10223-255">determination</span></span>                             | <span data-ttu-id="10223-256">指定事件的確定。</span><span class="sxs-lookup"><span data-stu-id="10223-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="10223-257">屬性值為： *NotAvailable*、 *Apt*、 *惡意*代碼、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、 *Other* 或  *null*</span><span class="sxs-lookup"><span data-stu-id="10223-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="10223-258">容易</span><span class="sxs-lookup"><span data-stu-id="10223-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="10223-259">分配</span><span class="sxs-lookup"><span data-stu-id="10223-259">assignedTo</span></span>                                | <span data-ttu-id="10223-260">事件的擁有者，如果未指派任何擁有者，則 *為 null* 。</span><span class="sxs-lookup"><span data-stu-id="10223-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="10223-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="10223-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="10223-262">actorName</span><span class="sxs-lookup"><span data-stu-id="10223-262">actorName</span></span>                                 | <span data-ttu-id="10223-263">與此警示相關聯的活動群組（若有的話）。</span><span class="sxs-lookup"><span data-stu-id="10223-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="10223-264">硼</span><span class="sxs-lookup"><span data-stu-id="10223-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="10223-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="10223-265">threatFamilyName</span></span>                          | <span data-ttu-id="10223-266">與此警示相關聯的威脅系列。</span><span class="sxs-lookup"><span data-stu-id="10223-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="10223-267">Null</span><span class="sxs-lookup"><span data-stu-id="10223-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="10223-268">mitreTechniques</span></span>                           | <span data-ttu-id="10223-269">攻擊技巧，與 [MITRE ATT&](https://attack.mitre.org/)™ framework 對齊。</span><span class="sxs-lookup"><span data-stu-id="10223-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-270">設備</span><span class="sxs-lookup"><span data-stu-id="10223-270">devices</span></span>                                   | <span data-ttu-id="10223-271">傳送與該事件相關之提醒的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="10223-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-272">\[\] (查看下列實體欄位的詳細資料) </span><span class="sxs-lookup"><span data-stu-id="10223-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="10223-273">**裝置格式**</span><span class="sxs-lookup"><span data-stu-id="10223-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="10223-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="10223-274">DeviceId</span></span>                                  | <span data-ttu-id="10223-275">Microsoft Defender ATP 中所指定的裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="10223-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="10223-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="10223-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="10223-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="10223-277">aadDeviceId</span></span>                               |  <span data-ttu-id="10223-278">在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD) 中指定的裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="10223-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="10223-279">僅適用于已加入網域的裝置。</span><span class="sxs-lookup"><span data-stu-id="10223-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="10223-280">Null</span><span class="sxs-lookup"><span data-stu-id="10223-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="10223-281">deviceDnsName</span></span>                             | <span data-ttu-id="10223-282">裝置的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="10223-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="10223-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="10223-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="10223-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="10223-284">osPlatform</span></span>                                | <span data-ttu-id="10223-285">裝置正在執行的作業系統平臺。</span><span class="sxs-lookup"><span data-stu-id="10223-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="10223-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="10223-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="10223-287">osBuild</span></span>                                   | <span data-ttu-id="10223-288">裝置執行的 OS 組建版本。</span><span class="sxs-lookup"><span data-stu-id="10223-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-289">14393</span><span class="sxs-lookup"><span data-stu-id="10223-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="10223-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="10223-290">rbacGroupName</span></span>                             | <span data-ttu-id="10223-291">以 [角色為基礎的存取控制](https://docs.microsoft.com/azure/role-based-access-control/overview) (與裝置相關聯的 RBAC) 群組。</span><span class="sxs-lookup"><span data-stu-id="10223-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="10223-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="10223-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="10223-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="10223-293">firstSeen</span></span>                                 | <span data-ttu-id="10223-294">第一次看到裝置的時間。</span><span class="sxs-lookup"><span data-stu-id="10223-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="10223-295">2020-02-06T14：16： 01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="10223-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="10223-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="10223-296">healthStatus</span></span>                              | <span data-ttu-id="10223-297">裝置的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="10223-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="10223-298">作用中</span><span class="sxs-lookup"><span data-stu-id="10223-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="10223-299">riskScore</span></span>                                 | <span data-ttu-id="10223-300">裝置的風險分數。</span><span class="sxs-lookup"><span data-stu-id="10223-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="10223-301">高</span><span class="sxs-lookup"><span data-stu-id="10223-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-302">實體</span><span class="sxs-lookup"><span data-stu-id="10223-302">entities</span></span>                                  | <span data-ttu-id="10223-303">已識別為特定警示之一部分或與其相關的所有實體。</span><span class="sxs-lookup"><span data-stu-id="10223-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-304">\[\] (查看下列實體欄位的詳細資料) </span><span class="sxs-lookup"><span data-stu-id="10223-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="10223-305">**實體格式**</span><span class="sxs-lookup"><span data-stu-id="10223-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="10223-306">entityType</span><span class="sxs-lookup"><span data-stu-id="10223-306">entityType</span></span>                                | <span data-ttu-id="10223-307">識別為屬於指定警示或與其相關的實體。</span><span class="sxs-lookup"><span data-stu-id="10223-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="10223-308">屬性值包括： *User*， *Ip*， *Url*， *File*， *Process*， *MailBox*， *MailMessage*， *MailCluster*， *Registry*</span><span class="sxs-lookup"><span data-stu-id="10223-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="10223-309">User</span><span class="sxs-lookup"><span data-stu-id="10223-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-310">sha1</span><span class="sxs-lookup"><span data-stu-id="10223-310">sha1</span></span>                                      | <span data-ttu-id="10223-311">當 entityType 為 *File*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="10223-312">與檔案或處理常式相關聯之警示的檔案雜湊。</span><span class="sxs-lookup"><span data-stu-id="10223-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="10223-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="10223-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="10223-314">sha256</span><span class="sxs-lookup"><span data-stu-id="10223-314">sha256</span></span>                                    | <span data-ttu-id="10223-315">當 entityType 為 *File*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="10223-316">與檔案或處理常式相關聯之警示的檔案雜湊。</span><span class="sxs-lookup"><span data-stu-id="10223-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="10223-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="10223-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="10223-318">檔案名</span><span class="sxs-lookup"><span data-stu-id="10223-318">fileName</span></span>                                  | <span data-ttu-id="10223-319">當 entityType 為 *File*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="10223-320">與檔案或處理常式相關聯的警示檔案名</span><span class="sxs-lookup"><span data-stu-id="10223-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="10223-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="10223-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-322">filePath</span><span class="sxs-lookup"><span data-stu-id="10223-322">filePath</span></span>                                  | <span data-ttu-id="10223-323">當 entityType 為 *File*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="10223-324">與檔案或處理常式相關聯之警示的檔路徑</span><span class="sxs-lookup"><span data-stu-id="10223-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="10223-325">C： \\ \\ 代理人 \\ \\ \_ 工作 \\ \\ \_ temp \\ \\ 部署 \_ 系統 2020-09-06 12 \_ 14 \_ 54 \\ \\ 輸出</span><span class="sxs-lookup"><span data-stu-id="10223-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="10223-326">Id</span><span class="sxs-lookup"><span data-stu-id="10223-326">processId</span></span>                                 | <span data-ttu-id="10223-327">可用於 entityType 為 *處理*程式。</span><span class="sxs-lookup"><span data-stu-id="10223-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-328">24348</span><span class="sxs-lookup"><span data-stu-id="10223-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="10223-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="10223-329">processCommandLine</span></span>                        | <span data-ttu-id="10223-330">可用於 entityType 為 *處理*程式。</span><span class="sxs-lookup"><span data-stu-id="10223-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-331">「 \\ 您的檔案已準備好下載 \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="10223-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="10223-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="10223-332">processCreationTime</span></span>                       | <span data-ttu-id="10223-333">可用於 entityType 為 *處理*程式。</span><span class="sxs-lookup"><span data-stu-id="10223-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-334">2020-18T03：25： 38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="10223-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="10223-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="10223-335">parentProcessId</span></span>                           | <span data-ttu-id="10223-336">可用於 entityType 為 *處理*程式。</span><span class="sxs-lookup"><span data-stu-id="10223-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="10223-337">16840</span><span class="sxs-lookup"><span data-stu-id="10223-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="10223-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="10223-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="10223-339">可用於 entityType 為 *處理*程式。</span><span class="sxs-lookup"><span data-stu-id="10223-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-340">2020-07-18T02：12： 32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="10223-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="10223-341">址</span><span class="sxs-lookup"><span data-stu-id="10223-341">ipAddress</span></span>                                 | <span data-ttu-id="10223-342">可在 entityType 為 *Ip*時使用。</span><span class="sxs-lookup"><span data-stu-id="10223-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="10223-343">與網路事件相關聯之警示的 IP 位址，例如與 *惡意網路目標的通訊*。</span><span class="sxs-lookup"><span data-stu-id="10223-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="10223-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="10223-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="10223-345">URL</span><span class="sxs-lookup"><span data-stu-id="10223-345">url</span></span>                                       | <span data-ttu-id="10223-346">可供 entityType 為 *Url*。</span><span class="sxs-lookup"><span data-stu-id="10223-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="10223-347">與網路事件相關聯之警示的 Url，例如， *與惡意網路目標的通訊*。</span><span class="sxs-lookup"><span data-stu-id="10223-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="10223-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="10223-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="10223-349">名</span><span class="sxs-lookup"><span data-stu-id="10223-349">accountName</span></span>                               | <span data-ttu-id="10223-350">當 entityType 為 *User*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="10223-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="10223-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="10223-352">domainName</span><span class="sxs-lookup"><span data-stu-id="10223-352">domainName</span></span>                                | <span data-ttu-id="10223-353">當 entityType 為 *User*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="10223-354">東歐公司 contoso</span><span class="sxs-lookup"><span data-stu-id="10223-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-355">userSid</span><span class="sxs-lookup"><span data-stu-id="10223-355">userSid</span></span>                                   | <span data-ttu-id="10223-356">當 entityType 為 *User*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="10223-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="10223-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="10223-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="10223-358">aadUserId</span></span>                                 | <span data-ttu-id="10223-359">當 entityType 為 *User*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="10223-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="10223-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="10223-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="10223-361">userPrincipalName</span></span>                         | <span data-ttu-id="10223-362">當 entityType 是*使用者* / *MailBox* / *MailMessage*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="10223-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="10223-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="10223-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="10223-365">在 *MailBox*entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-366">測試使用者2</span><span class="sxs-lookup"><span data-stu-id="10223-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="10223-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="10223-367">mailboxAddress</span></span>                            | <span data-ttu-id="10223-368">當 entityType 是*使用者* / *MailBox* / *MailMessage*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="10223-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="10223-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="10223-370">clusterBy</span></span>                                 | <span data-ttu-id="10223-371">可用於  *MailCluster*的 entityType。</span><span class="sxs-lookup"><span data-stu-id="10223-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="10223-372">話題P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="10223-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="10223-373">sender</span><span class="sxs-lookup"><span data-stu-id="10223-373">sender</span></span>                                    | <span data-ttu-id="10223-374">當 entityType 是*使用者* / *MailBox* / *MailMessage*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="10223-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="10223-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="10223-376">recipient</span><span class="sxs-lookup"><span data-stu-id="10223-376">recipient</span></span>                                 | <span data-ttu-id="10223-377">在 *MailMessage*entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="10223-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="10223-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="10223-379">主題</span><span class="sxs-lookup"><span data-stu-id="10223-379">subject</span></span>                                   | <span data-ttu-id="10223-380">在 *MailMessage*entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="10223-381">\[外部 \] 注意</span><span class="sxs-lookup"><span data-stu-id="10223-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="10223-382">deliveryAction</span></span>                            | <span data-ttu-id="10223-383">在 *MailMessage*entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="10223-384">已傳遞</span><span class="sxs-lookup"><span data-stu-id="10223-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="10223-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="10223-385">securityGroupId</span></span>                           | <span data-ttu-id="10223-386">在  *SecurityGroup*entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="10223-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="10223-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="10223-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="10223-388">securityGroupName</span></span>                         | <span data-ttu-id="10223-389">在  *SecurityGroup*entityType 時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="10223-390">網路設定運算子</span><span class="sxs-lookup"><span data-stu-id="10223-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="10223-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="10223-391">registryHive</span></span>                              | <span data-ttu-id="10223-392">當 entityType 為  *Registry*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="10223-393">HKEY \_ 本機 \_ 電腦</span><span class="sxs-lookup"><span data-stu-id="10223-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="10223-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="10223-394">registryKey</span></span>                               | <span data-ttu-id="10223-395">當 entityType 為  *Registry*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="10223-396">軟體 \\ \\ MICROSOFT \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="10223-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="10223-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="10223-397">registryValueType</span></span>                         | <span data-ttu-id="10223-398">當 entityType 為  *Registry*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="10223-399">字串</span><span class="sxs-lookup"><span data-stu-id="10223-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="10223-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="10223-400">registryValue</span></span>                             | <span data-ttu-id="10223-401">當 entityType 為  *Registry*時可用。</span><span class="sxs-lookup"><span data-stu-id="10223-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="10223-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="10223-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="10223-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="10223-403">deviceId</span></span>                                  | <span data-ttu-id="10223-404">與實體相關之裝置的識別碼（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="10223-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="10223-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="10223-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="10223-406">範例</span><span class="sxs-lookup"><span data-stu-id="10223-406">Example</span></span>

<span data-ttu-id="10223-407">**請求**</span><span class="sxs-lookup"><span data-stu-id="10223-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="10223-408">**回應**</span><span class="sxs-lookup"><span data-stu-id="10223-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="10223-409">相關主題</span><span class="sxs-lookup"><span data-stu-id="10223-409">Related topic</span></span>
- [<span data-ttu-id="10223-410">事件 APIs</span><span class="sxs-lookup"><span data-stu-id="10223-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="10223-411">更新事件</span><span class="sxs-lookup"><span data-stu-id="10223-411">Update incident</span></span>](api-update-incidents.md)
