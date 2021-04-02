---
title: Microsoft 365 Defender advanced 搜尋架構中的命名變更
description: 追蹤和審閱高級搜尋架構中的命名變更表格和欄
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、資料、命名變更、重新命名、Microsoft 威脅防護
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ab6bdefb457fb31df98d829ee801b72f4c8ae70a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499694"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="2fae0-104">高級搜尋架構命名變更</span><span class="sxs-lookup"><span data-stu-id="2fae0-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2fae0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2fae0-105">**Applies to:**</span></span>
- <span data-ttu-id="2fae0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2fae0-107">「 [高級搜尋」架構](advanced-hunting-schema-tables.md) 會定期更新，以加入新的資料表和欄。</span><span class="sxs-lookup"><span data-stu-id="2fae0-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="2fae0-108">在某些情況下，會重新命名或取代現有的欄名，以提升使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="2fae0-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="2fae0-109">請參閱本文，以複查可能影響查詢的命名變更。</span><span class="sxs-lookup"><span data-stu-id="2fae0-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="2fae0-110">命名變更會自動套用至儲存在 [安全性中心] 中的查詢，包括自訂偵測規則所使用的查詢。</span><span class="sxs-lookup"><span data-stu-id="2fae0-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="2fae0-111">您不需要手動更新這些查詢。</span><span class="sxs-lookup"><span data-stu-id="2fae0-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="2fae0-112">不過，您將需要更新下列查詢：</span><span class="sxs-lookup"><span data-stu-id="2fae0-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="2fae0-113">使用 API 執行的查詢</span><span class="sxs-lookup"><span data-stu-id="2fae0-113">Queries that are run using the API</span></span>
- <span data-ttu-id="2fae0-114">儲存在安全性中心以外其他位置的查詢</span><span class="sxs-lookup"><span data-stu-id="2fae0-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="2fae0-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="2fae0-115">December 2020</span></span>

| <span data-ttu-id="2fae0-116">表格名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-116">Table name</span></span> | <span data-ttu-id="2fae0-117">原始欄名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-117">Original column name</span></span> | <span data-ttu-id="2fae0-118">新欄名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-118">New column name</span></span> | <span data-ttu-id="2fae0-119">變更的原因</span><span class="sxs-lookup"><span data-stu-id="2fae0-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="2fae0-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2fae0-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="2fae0-121">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="2fae0-121">Customer feedback</span></span> |
| [<span data-ttu-id="2fae0-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2fae0-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="2fae0-123">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="2fae0-123">Customer feedback</span></span> |
| [<span data-ttu-id="2fae0-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2fae0-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="2fae0-125">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="2fae0-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="2fae0-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="2fae0-126">January 2021</span></span>

| <span data-ttu-id="2fae0-127">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-127">Column name</span></span> | <span data-ttu-id="2fae0-128">原始值名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-128">Original value name</span></span> | <span data-ttu-id="2fae0-129">新值名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-129">New value name</span></span> | <span data-ttu-id="2fae0-130">變更的原因</span><span class="sxs-lookup"><span data-stu-id="2fae0-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="2fae0-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="2fae0-131">MCAS</span></span> |    <span data-ttu-id="2fae0-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2fae0-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="2fae0-133">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="2fae0-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="2fae0-135">EDR</span><span class="sxs-lookup"><span data-stu-id="2fae0-135">EDR</span></span>| <span data-ttu-id="2fae0-136">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="2fae0-137">WindowsDefenderAv</span></span> | <span data-ttu-id="2fae0-138">防毒</span><span class="sxs-lookup"><span data-stu-id="2fae0-138">Antivirus</span></span> | <span data-ttu-id="2fae0-139">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="2fae0-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="2fae0-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="2fae0-141">SmartScreen</span></span> | <span data-ttu-id="2fae0-142">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="2fae0-143">CustomerTI</span></span> |  <span data-ttu-id="2fae0-144">自訂 TI</span><span class="sxs-lookup"><span data-stu-id="2fae0-144">Custom TI</span></span> | <span data-ttu-id="2fae0-145">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="2fae0-146">OfficeATP</span></span> | <span data-ttu-id="2fae0-147">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="2fae0-148">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-149">具有 MTP 之</span><span class="sxs-lookup"><span data-stu-id="2fae0-149">MTP</span></span>   | <span data-ttu-id="2fae0-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="2fae0-151">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="2fae0-152">AzureATP</span></span> |    <span data-ttu-id="2fae0-153">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="2fae0-154">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="2fae0-155">CustomDetection</span></span>   | <span data-ttu-id="2fae0-156">自訂偵測</span><span class="sxs-lookup"><span data-stu-id="2fae0-156">Custom detection</span></span> | <span data-ttu-id="2fae0-157">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="2fae0-158">AutomatedInvestigation</span></span> |<span data-ttu-id="2fae0-159">自動調查</span><span class="sxs-lookup"><span data-stu-id="2fae0-159">Automated investigation</span></span> | <span data-ttu-id="2fae0-160">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="2fae0-161">ThreatExperts</span></span> | <span data-ttu-id="2fae0-162">Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="2fae0-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="2fae0-163">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2fae0-164">協力廠商的 TI</span><span class="sxs-lookup"><span data-stu-id="2fae0-164">3rd party TI</span></span> | <span data-ttu-id="2fae0-165">協力廠商感應器</span><span class="sxs-lookup"><span data-stu-id="2fae0-165">3rd Party sensors</span></span> | <span data-ttu-id="2fae0-166">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="2fae0-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2fae0-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="2fae0-168">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="2fae0-169">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="2fae0-170">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="2fae0-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="2fae0-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="2fae0-172">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="2fae0-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="2fae0-173">Office 365 ATP</span></span>  |<span data-ttu-id="2fae0-174">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="2fae0-175">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="2fae0-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="2fae0-176">Azure ATP</span></span>    |<span data-ttu-id="2fae0-177">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2fae0-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="2fae0-178">..Org</span><span class="sxs-lookup"><span data-stu-id="2fae0-178">Rebranding</span></span> |

<span data-ttu-id="2fae0-179">`DetectionSource` 可用於 [AlertInfo](advanced-hunting-alertinfo-table.md) 表格。</span><span class="sxs-lookup"><span data-stu-id="2fae0-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="2fae0-180">`ServiceSource` 可用於 [AlertEvidence](advanced-hunting-alertevidence-table.md) 和 [AlertInfo](advanced-hunting-alertinfo-table.md) 資料表。</span><span class="sxs-lookup"><span data-stu-id="2fae0-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="2fae0-181">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="2fae0-181">February 2021</span></span>

1. <span data-ttu-id="2fae0-182">在 [ [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) ] 和 [ [EmailEvents](advanced-hunting-emailevents-table.md) ] 表格中，[ `MalwareFilterVerdict` 和] 欄已 `PhishFilterVerdict` 由欄所取代 `ThreatTypes` 。</span><span class="sxs-lookup"><span data-stu-id="2fae0-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="2fae0-183">`MalwareDetectionMethod`和 `PhishDetectionMethod` 欄也會取代 `DetectionMethods` 欄。</span><span class="sxs-lookup"><span data-stu-id="2fae0-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="2fae0-184">這種精簡功能可讓我們在新欄下提供更多資訊。</span><span class="sxs-lookup"><span data-stu-id="2fae0-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="2fae0-185">下圖提供對應。</span><span class="sxs-lookup"><span data-stu-id="2fae0-185">The mapping is provided below.</span></span>

| <span data-ttu-id="2fae0-186">表格名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-186">Table name</span></span> | <span data-ttu-id="2fae0-187">原始欄名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-187">Original column name</span></span> | <span data-ttu-id="2fae0-188">新欄名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-188">New column name</span></span> | <span data-ttu-id="2fae0-189">變更的原因</span><span class="sxs-lookup"><span data-stu-id="2fae0-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="2fae0-190">包含更多偵測方法</span><span class="sxs-lookup"><span data-stu-id="2fae0-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="2fae0-191">包含更多威脅類型</span><span class="sxs-lookup"><span data-stu-id="2fae0-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="2fae0-192">包含更多偵測方法</span><span class="sxs-lookup"><span data-stu-id="2fae0-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="2fae0-193">包含更多威脅類型</span><span class="sxs-lookup"><span data-stu-id="2fae0-193">Include more threat types</span></span> |


2. <span data-ttu-id="2fae0-194">在 [ `EmailAttachmentInfo` 和 `EmailEvents` 表格] 中， `ThreatNames` 新增欄以提供有關電子郵件威脅的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2fae0-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="2fae0-195">此欄包含垃圾郵件或網路釣魚詐騙等值。</span><span class="sxs-lookup"><span data-stu-id="2fae0-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="2fae0-196">在 [ [DeviceInfo](advanced-hunting-deviceinfo-table.md) ] 表格中，根據客戶的意見反應，欄會 `DeviceObjectId` 取代欄 `AadDeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="2fae0-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="2fae0-197">在 [ [DeviceEvents](advanced-hunting-deviceevents-table.md) ] 表格中，已修改數個 ActionType 名稱，以更好地反映動作的描述。</span><span class="sxs-lookup"><span data-stu-id="2fae0-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="2fae0-198">您可以在下面找到變更的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2fae0-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="2fae0-199">表格名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-199">Table name</span></span> | <span data-ttu-id="2fae0-200">原始 ActionType 名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-200">Original ActionType name</span></span> | <span data-ttu-id="2fae0-201">新 ActionType 名稱</span><span class="sxs-lookup"><span data-stu-id="2fae0-201">New ActionType name</span></span> | <span data-ttu-id="2fae0-202">變更的原因</span><span class="sxs-lookup"><span data-stu-id="2fae0-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="2fae0-203">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="2fae0-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="2fae0-204">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="2fae0-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="2fae0-205">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="2fae0-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="2fae0-206">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="2fae0-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="2fae0-207">相關主題</span><span class="sxs-lookup"><span data-stu-id="2fae0-207">Related topics</span></span>
- [<span data-ttu-id="2fae0-208">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="2fae0-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2fae0-209">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="2fae0-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)