---
title: 取得提醒 API
description: 深入瞭解 Microsoft Defender for Endpoint 中的警示資源類型的方法和屬性。
keywords: api、graph api、支援的 api、get、警示、最近
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
ms.openlocfilehash: c935df1abddc3d0ebee74e09280d6e3ec961ca97
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769806"
---
# <a name="alert-resource-type"></a><span data-ttu-id="cd635-104">警示資源類型</span><span class="sxs-lookup"><span data-stu-id="cd635-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cd635-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cd635-105">**Applies to:**</span></span>
- [<span data-ttu-id="cd635-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cd635-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="cd635-107">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="cd635-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cd635-108">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="cd635-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="cd635-109">方法</span><span class="sxs-lookup"><span data-stu-id="cd635-109">Methods</span></span>

<span data-ttu-id="cd635-110">方法	</span><span class="sxs-lookup"><span data-stu-id="cd635-110">Method</span></span> |<span data-ttu-id="cd635-111">傳回類型</span><span class="sxs-lookup"><span data-stu-id="cd635-111">Return Type</span></span> |<span data-ttu-id="cd635-112">描述</span><span class="sxs-lookup"><span data-stu-id="cd635-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="cd635-113">取得警示</span><span class="sxs-lookup"><span data-stu-id="cd635-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="cd635-114">警示</span><span class="sxs-lookup"><span data-stu-id="cd635-114">Alert</span></span>](alerts.md) | <span data-ttu-id="cd635-115">取得單一 [警示](alerts.md) 物件。</span><span class="sxs-lookup"><span data-stu-id="cd635-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="cd635-116">列出警示</span><span class="sxs-lookup"><span data-stu-id="cd635-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="cd635-117">[警示](alerts.md) 集合</span><span class="sxs-lookup"><span data-stu-id="cd635-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="cd635-118">清單 [警示](alerts.md) 收集。</span><span class="sxs-lookup"><span data-stu-id="cd635-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="cd635-119">更新警示</span><span class="sxs-lookup"><span data-stu-id="cd635-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="cd635-120">警示</span><span class="sxs-lookup"><span data-stu-id="cd635-120">Alert</span></span>](alerts.md) | <span data-ttu-id="cd635-121">更新特定 [警示](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="cd635-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="cd635-122">批次更新提醒</span><span class="sxs-lookup"><span data-stu-id="cd635-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="cd635-123">更新批次 [警示](alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="cd635-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="cd635-124">建立警示</span><span class="sxs-lookup"><span data-stu-id="cd635-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="cd635-125">警示</span><span class="sxs-lookup"><span data-stu-id="cd635-125">Alert</span></span>](alerts.md)|<span data-ttu-id="cd635-126">根據從 [高級搜尋](run-advanced-query-api.md)取得的事件資料來建立警示。</span><span class="sxs-lookup"><span data-stu-id="cd635-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="cd635-127">清單相關的網域</span><span class="sxs-lookup"><span data-stu-id="cd635-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="cd635-128">網域集合</span><span class="sxs-lookup"><span data-stu-id="cd635-128">Domain collection</span></span>| <span data-ttu-id="cd635-129">與警示相關聯的清單 URLs。</span><span class="sxs-lookup"><span data-stu-id="cd635-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="cd635-130">清單相關檔案</span><span class="sxs-lookup"><span data-stu-id="cd635-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="cd635-131">[檔](files.md) 集合</span><span class="sxs-lookup"><span data-stu-id="cd635-131">[File](files.md) collection</span></span> |  <span data-ttu-id="cd635-132">列出與[警示](alerts.md)相關[聯的檔案實體。](files.md)</span><span class="sxs-lookup"><span data-stu-id="cd635-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="cd635-133">清單相關的 Ip</span><span class="sxs-lookup"><span data-stu-id="cd635-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="cd635-134">IP 集合</span><span class="sxs-lookup"><span data-stu-id="cd635-134">IP collection</span></span> | <span data-ttu-id="cd635-135">列出與警示相關聯的 Ip。</span><span class="sxs-lookup"><span data-stu-id="cd635-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="cd635-136">取得相關的電腦</span><span class="sxs-lookup"><span data-stu-id="cd635-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="cd635-137">機器</span><span class="sxs-lookup"><span data-stu-id="cd635-137">Machine</span></span>](machine.md) | <span data-ttu-id="cd635-138">與[警示](alerts.md)相關聯的[電腦](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="cd635-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="cd635-139">取得相關的使用者</span><span class="sxs-lookup"><span data-stu-id="cd635-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="cd635-140">使用者</span><span class="sxs-lookup"><span data-stu-id="cd635-140">User</span></span>](user.md) | <span data-ttu-id="cd635-141">與[警示](alerts.md)相關聯的[使用者](user.md)。</span><span class="sxs-lookup"><span data-stu-id="cd635-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="cd635-142">屬性</span><span class="sxs-lookup"><span data-stu-id="cd635-142">Properties</span></span>

<span data-ttu-id="cd635-143">屬性	</span><span class="sxs-lookup"><span data-stu-id="cd635-143">Property</span></span> |    <span data-ttu-id="cd635-144">類型</span><span class="sxs-lookup"><span data-stu-id="cd635-144">Type</span></span>    |    <span data-ttu-id="cd635-145">描述</span><span class="sxs-lookup"><span data-stu-id="cd635-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="cd635-146">id</span><span class="sxs-lookup"><span data-stu-id="cd635-146">id</span></span> | <span data-ttu-id="cd635-147">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-147">String</span></span> | <span data-ttu-id="cd635-148">警示識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd635-148">Alert ID.</span></span>
<span data-ttu-id="cd635-149">標題</span><span class="sxs-lookup"><span data-stu-id="cd635-149">title</span></span> | <span data-ttu-id="cd635-150">String</span><span class="sxs-lookup"><span data-stu-id="cd635-150">String</span></span> | <span data-ttu-id="cd635-151">警示標題。</span><span class="sxs-lookup"><span data-stu-id="cd635-151">Alert title.</span></span>
<span data-ttu-id="cd635-152">描述</span><span class="sxs-lookup"><span data-stu-id="cd635-152">description</span></span> | <span data-ttu-id="cd635-153">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-153">String</span></span> | <span data-ttu-id="cd635-154">警示描述。</span><span class="sxs-lookup"><span data-stu-id="cd635-154">Alert description.</span></span>
<span data-ttu-id="cd635-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="cd635-155">alertCreationTime</span></span> | <span data-ttu-id="cd635-156">可為 null 的 DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cd635-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cd635-157">在 UTC) 建立警示的日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="cd635-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="cd635-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="cd635-158">lastEventTime</span></span> | <span data-ttu-id="cd635-159">可為 null 的 DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cd635-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cd635-160">在相同裝置上觸發警示的事件的最後一個出現。</span><span class="sxs-lookup"><span data-stu-id="cd635-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="cd635-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="cd635-161">firstEventTime</span></span> | <span data-ttu-id="cd635-162">可為 null 的 DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cd635-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cd635-163">觸發該裝置上警示的事件第一次出現。</span><span class="sxs-lookup"><span data-stu-id="cd635-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="cd635-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="cd635-164">lastUpdateTime</span></span> | <span data-ttu-id="cd635-165">可為 null 的 DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cd635-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cd635-166">上次更新警示) 日期和時間 (。</span><span class="sxs-lookup"><span data-stu-id="cd635-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="cd635-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="cd635-167">resolvedTime</span></span> | <span data-ttu-id="cd635-168">可為 null 的 DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="cd635-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="cd635-169">警示狀態變更為「已解決」的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="cd635-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="cd635-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="cd635-170">incidentId</span></span> | <span data-ttu-id="cd635-171">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="cd635-171">Nullable Long</span></span> | <span data-ttu-id="cd635-172">警示的 [事件](view-incidents-queue.md) 識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd635-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="cd635-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="cd635-173">investigationId</span></span> | <span data-ttu-id="cd635-174">可為 null 的長</span><span class="sxs-lookup"><span data-stu-id="cd635-174">Nullable Long</span></span> | <span data-ttu-id="cd635-175">與提醒相關的 [調查](automated-investigations.md) 識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd635-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="cd635-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="cd635-176">investigationState</span></span> | <span data-ttu-id="cd635-177">可為 null 的列舉</span><span class="sxs-lookup"><span data-stu-id="cd635-177">Nullable Enum</span></span> | <span data-ttu-id="cd635-178">[調查](automated-investigations.md)的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="cd635-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="cd635-179">可能的值為： ' Unknown '、' 終止 '、' SuccessfullyRemediated '、' 良性 '、' Failed '、' PartiallyRemediated '、' PartiallyInvestigated '、' PendingApproval '、' PendingResource '、' TerminatedByUser '、' TerminatedBySystem '、' InnerFailure '、' PreexistingAlert '、' UnsupportedOs '、' UnsupportedAlertType '、' SuppressedAlert '、' '、' '。</span><span class="sxs-lookup"><span data-stu-id="cd635-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="cd635-180">分配</span><span class="sxs-lookup"><span data-stu-id="cd635-180">assignedTo</span></span> | <span data-ttu-id="cd635-181">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-181">String</span></span> | <span data-ttu-id="cd635-182">警示的擁有者。</span><span class="sxs-lookup"><span data-stu-id="cd635-182">Owner of the alert.</span></span>
<span data-ttu-id="cd635-183">嚴重性</span><span class="sxs-lookup"><span data-stu-id="cd635-183">severity</span></span> | <span data-ttu-id="cd635-184">Enum</span><span class="sxs-lookup"><span data-stu-id="cd635-184">Enum</span></span> | <span data-ttu-id="cd635-185">警示的嚴重性。</span><span class="sxs-lookup"><span data-stu-id="cd635-185">Severity of the alert.</span></span> <span data-ttu-id="cd635-186">可能的值為：「未指定的 '、' 資訊」、「低 '、' 中」及 ' High」。</span><span class="sxs-lookup"><span data-stu-id="cd635-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="cd635-187">地位</span><span class="sxs-lookup"><span data-stu-id="cd635-187">status</span></span> | <span data-ttu-id="cd635-188">Enum</span><span class="sxs-lookup"><span data-stu-id="cd635-188">Enum</span></span> | <span data-ttu-id="cd635-189">指定警示的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="cd635-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="cd635-190">可能的值為：「Unknown '、' New '、' InProgress ' 和 ' 已解析」。</span><span class="sxs-lookup"><span data-stu-id="cd635-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="cd635-191">分類</span><span class="sxs-lookup"><span data-stu-id="cd635-191">classification</span></span> | <span data-ttu-id="cd635-192">可為 null 的列舉</span><span class="sxs-lookup"><span data-stu-id="cd635-192">Nullable Enum</span></span> | <span data-ttu-id="cd635-193">警示的規格。</span><span class="sxs-lookup"><span data-stu-id="cd635-193">Specification of the alert.</span></span> <span data-ttu-id="cd635-194">可能的值為： ' Unknown '、' FalsePositive '、' TruePositive '。</span><span class="sxs-lookup"><span data-stu-id="cd635-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="cd635-195">測定</span><span class="sxs-lookup"><span data-stu-id="cd635-195">determination</span></span> | <span data-ttu-id="cd635-196">可為 null 的列舉</span><span class="sxs-lookup"><span data-stu-id="cd635-196">Nullable Enum</span></span> | <span data-ttu-id="cd635-197">指定報警的決定。</span><span class="sxs-lookup"><span data-stu-id="cd635-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="cd635-198">可能的值為： "NotAvailable"、"Apt"、"Malware"、"SecurityPersonnel"、"SecurityTesting"、"UnwantedSoftware"、"Other"。</span><span class="sxs-lookup"><span data-stu-id="cd635-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="cd635-199">類別</span><span class="sxs-lookup"><span data-stu-id="cd635-199">category</span></span>| <span data-ttu-id="cd635-200">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-200">String</span></span> | <span data-ttu-id="cd635-201">警示的類別。</span><span class="sxs-lookup"><span data-stu-id="cd635-201">Category of the alert.</span></span>
<span data-ttu-id="cd635-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="cd635-202">detectionSource</span></span> | <span data-ttu-id="cd635-203">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-203">String</span></span> | <span data-ttu-id="cd635-204">偵測來源。</span><span class="sxs-lookup"><span data-stu-id="cd635-204">Detection source.</span></span>
<span data-ttu-id="cd635-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="cd635-205">threatFamilyName</span></span> | <span data-ttu-id="cd635-206">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-206">String</span></span> | <span data-ttu-id="cd635-207">威脅系列。</span><span class="sxs-lookup"><span data-stu-id="cd635-207">Threat family.</span></span>
<span data-ttu-id="cd635-208">threatName</span><span class="sxs-lookup"><span data-stu-id="cd635-208">threatName</span></span> | <span data-ttu-id="cd635-209">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-209">String</span></span> | <span data-ttu-id="cd635-210">威脅名稱。</span><span class="sxs-lookup"><span data-stu-id="cd635-210">Threat name.</span></span>
<span data-ttu-id="cd635-211">machineId</span><span class="sxs-lookup"><span data-stu-id="cd635-211">machineId</span></span> | <span data-ttu-id="cd635-212">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-212">String</span></span> | <span data-ttu-id="cd635-213">與警示相關聯之 [電腦](machine.md) 實體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd635-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="cd635-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="cd635-214">computerDnsName</span></span> | <span data-ttu-id="cd635-215">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-215">String</span></span> | <span data-ttu-id="cd635-216">[電腦](machine.md) 完全限定名稱。</span><span class="sxs-lookup"><span data-stu-id="cd635-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="cd635-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="cd635-217">aadTenantId</span></span> | <span data-ttu-id="cd635-218">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-218">String</span></span> | <span data-ttu-id="cd635-219">Azure Active Directory 識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd635-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="cd635-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="cd635-220">detectorId</span></span> | <span data-ttu-id="cd635-221">字串</span><span class="sxs-lookup"><span data-stu-id="cd635-221">String</span></span> | <span data-ttu-id="cd635-222">觸發警示的檢測器識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd635-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="cd635-223">註解</span><span class="sxs-lookup"><span data-stu-id="cd635-223">comments</span></span> | <span data-ttu-id="cd635-224">警示批註清單</span><span class="sxs-lookup"><span data-stu-id="cd635-224">List of Alert comments</span></span> | <span data-ttu-id="cd635-225">警示 Comment 物件包含： comment string、createdBy string 及 createTime date time。</span><span class="sxs-lookup"><span data-stu-id="cd635-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="cd635-226">證據</span><span class="sxs-lookup"><span data-stu-id="cd635-226">Evidence</span></span> | <span data-ttu-id="cd635-227">警示證據清單</span><span class="sxs-lookup"><span data-stu-id="cd635-227">List of Alert evidence</span></span> | <span data-ttu-id="cd635-228">與警示相關的證據。</span><span class="sxs-lookup"><span data-stu-id="cd635-228">Evidence related to the alert.</span></span> <span data-ttu-id="cd635-229">請參閱下面範例。</span><span class="sxs-lookup"><span data-stu-id="cd635-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="cd635-230">取得單一警示的回應範例：</span><span class="sxs-lookup"><span data-stu-id="cd635-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
