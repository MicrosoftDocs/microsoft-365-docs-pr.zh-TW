---
title: 在 Microsoft 365 Defender 高級搜尋架構中命名變更
description: 追蹤和審閱高級搜尋架構中的命名變更表格和欄
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，schema reference，kusto，table，資料，命名變更，重新命名
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
ms.openlocfilehash: 9406653a2d16c83f974e2a0ce7597b5c4f833252
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289490"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="a2926-104">高級搜尋架構命名變更</span><span class="sxs-lookup"><span data-stu-id="a2926-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a2926-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a2926-105">**Applies to:**</span></span>
- <span data-ttu-id="a2926-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a2926-107">「 [高級搜尋」架構](advanced-hunting-schema-tables.md) 會定期更新，以加入新的資料表和欄。</span><span class="sxs-lookup"><span data-stu-id="a2926-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="a2926-108">在某些情況下，會重新命名或取代現有的欄名，以提升使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="a2926-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="a2926-109">請參閱本文，以複查可能影響查詢的命名變更。</span><span class="sxs-lookup"><span data-stu-id="a2926-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="a2926-110">命名變更會自動套用至儲存在 [安全性中心] 中的查詢，包括自訂偵測規則所使用的查詢。</span><span class="sxs-lookup"><span data-stu-id="a2926-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="a2926-111">您不需要手動更新這些查詢。</span><span class="sxs-lookup"><span data-stu-id="a2926-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="a2926-112">不過，您將需要更新下列查詢：</span><span class="sxs-lookup"><span data-stu-id="a2926-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="a2926-113">使用 API 執行的查詢</span><span class="sxs-lookup"><span data-stu-id="a2926-113">Queries that are run using the API</span></span>
- <span data-ttu-id="a2926-114">儲存在安全性中心以外其他位置的查詢</span><span class="sxs-lookup"><span data-stu-id="a2926-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="a2926-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="a2926-115">December 2020</span></span>

| <span data-ttu-id="a2926-116">表格名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-116">Table name</span></span> | <span data-ttu-id="a2926-117">原始欄名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-117">Original column name</span></span> | <span data-ttu-id="a2926-118">新欄名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-118">New column name</span></span> | <span data-ttu-id="a2926-119">變更的原因</span><span class="sxs-lookup"><span data-stu-id="a2926-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="a2926-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="a2926-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="a2926-121">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="a2926-121">Customer feedback</span></span> |
| [<span data-ttu-id="a2926-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="a2926-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="a2926-123">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="a2926-123">Customer feedback</span></span> |
| [<span data-ttu-id="a2926-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="a2926-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="a2926-125">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="a2926-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="a2926-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="a2926-126">January 2021</span></span>

| <span data-ttu-id="a2926-127">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-127">Column name</span></span> | <span data-ttu-id="a2926-128">原始值名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-128">Original value name</span></span> | <span data-ttu-id="a2926-129">新值名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-129">New value name</span></span> | <span data-ttu-id="a2926-130">變更的原因</span><span class="sxs-lookup"><span data-stu-id="a2926-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="a2926-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="a2926-131">MCAS</span></span> | <span data-ttu-id="a2926-132">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="a2926-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="a2926-133">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="a2926-134">WindowsDefenderAtp</span></span>| <span data-ttu-id="a2926-135">EDR</span><span class="sxs-lookup"><span data-stu-id="a2926-135">EDR</span></span>| <span data-ttu-id="a2926-136">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="a2926-137">WindowsDefenderAv</span></span> | <span data-ttu-id="a2926-138">防毒</span><span class="sxs-lookup"><span data-stu-id="a2926-138">Antivirus</span></span> | <span data-ttu-id="a2926-139">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="a2926-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="a2926-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="a2926-141">SmartScreen</span></span> | <span data-ttu-id="a2926-142">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="a2926-143">CustomerTI</span></span> | <span data-ttu-id="a2926-144">自訂 TI</span><span class="sxs-lookup"><span data-stu-id="a2926-144">Custom TI</span></span> | <span data-ttu-id="a2926-145">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="a2926-146">OfficeATP</span></span> | <span data-ttu-id="a2926-147">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="a2926-148">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-149">具有 MTP 之</span><span class="sxs-lookup"><span data-stu-id="a2926-149">MTP</span></span> | <span data-ttu-id="a2926-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="a2926-151">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="a2926-152">AzureATP</span></span> | <span data-ttu-id="a2926-153">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="a2926-154">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="a2926-155">CustomDetection</span></span> | <span data-ttu-id="a2926-156">自訂偵測</span><span class="sxs-lookup"><span data-stu-id="a2926-156">Custom detection</span></span> | <span data-ttu-id="a2926-157">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="a2926-158">AutomatedInvestigation</span></span> |<span data-ttu-id="a2926-159">自動調查</span><span class="sxs-lookup"><span data-stu-id="a2926-159">Automated investigation</span></span> | <span data-ttu-id="a2926-160">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="a2926-161">ThreatExperts</span></span> | <span data-ttu-id="a2926-162">Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="a2926-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="a2926-163">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="a2926-164">協力廠商的 TI</span><span class="sxs-lookup"><span data-stu-id="a2926-164">3rd party TI</span></span> | <span data-ttu-id="a2926-165">協力廠商感應器</span><span class="sxs-lookup"><span data-stu-id="a2926-165">3rd Party sensors</span></span> | <span data-ttu-id="a2926-166">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="a2926-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a2926-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="a2926-168">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="a2926-169">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="a2926-170">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="a2926-170">Microsoft Threat Protection</span></span> | <span data-ttu-id="a2926-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="a2926-172">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="a2926-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="a2926-173">Office 365 ATP</span></span> |<span data-ttu-id="a2926-174">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="a2926-175">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="a2926-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="a2926-176">Azure ATP</span></span> |<span data-ttu-id="a2926-177">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a2926-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="a2926-178">..Org</span><span class="sxs-lookup"><span data-stu-id="a2926-178">Rebranding</span></span> |

<span data-ttu-id="a2926-179">`DetectionSource` 可用於 [AlertInfo](advanced-hunting-alertinfo-table.md) 表格。</span><span class="sxs-lookup"><span data-stu-id="a2926-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="a2926-180">`ServiceSource` 可用於 [AlertEvidence](advanced-hunting-alertevidence-table.md) 和 [AlertInfo](advanced-hunting-alertinfo-table.md) 資料表。</span><span class="sxs-lookup"><span data-stu-id="a2926-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="a2926-181">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="a2926-181">February 2021</span></span>

1. <span data-ttu-id="a2926-182">在 [ [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) ] 和 [ [EmailEvents](advanced-hunting-emailevents-table.md) ] 表格中，[ `MalwareFilterVerdict` 和] 欄已 `PhishFilterVerdict` 由欄所取代 `ThreatTypes` 。</span><span class="sxs-lookup"><span data-stu-id="a2926-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="a2926-183">`MalwareDetectionMethod`和 `PhishDetectionMethod` 欄也會取代 `DetectionMethods` 欄。</span><span class="sxs-lookup"><span data-stu-id="a2926-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="a2926-184">這種精簡功能可讓我們在新欄下提供更多資訊。</span><span class="sxs-lookup"><span data-stu-id="a2926-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="a2926-185">下圖提供對應。</span><span class="sxs-lookup"><span data-stu-id="a2926-185">The mapping is provided below.</span></span>

    | <span data-ttu-id="a2926-186">表格名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-186">Table name</span></span> | <span data-ttu-id="a2926-187">原始欄名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-187">Original column name</span></span> | <span data-ttu-id="a2926-188">新欄名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-188">New column name</span></span> | <span data-ttu-id="a2926-189">變更的原因</span><span class="sxs-lookup"><span data-stu-id="a2926-189">Reason for change</span></span>
    |--|--|--|--|
    | `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="a2926-190">包含更多偵測方法</span><span class="sxs-lookup"><span data-stu-id="a2926-190">Include more detection methods</span></span> |
    | `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="a2926-191">包含更多威脅類型</span><span class="sxs-lookup"><span data-stu-id="a2926-191">Include more threat types</span></span> |
    | `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="a2926-192">包含更多偵測方法</span><span class="sxs-lookup"><span data-stu-id="a2926-192">Include more detection methods</span></span> |
    | `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="a2926-193">包含更多威脅類型</span><span class="sxs-lookup"><span data-stu-id="a2926-193">Include more threat types</span></span> |


2. <span data-ttu-id="a2926-194">在 [ `EmailAttachmentInfo` 和 `EmailEvents` 表格] 中， `ThreatNames` 新增欄以提供有關電子郵件威脅的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a2926-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="a2926-195">此欄包含垃圾郵件或網路釣魚詐騙等值。</span><span class="sxs-lookup"><span data-stu-id="a2926-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="a2926-196">在 [ [DeviceInfo](advanced-hunting-deviceinfo-table.md) ] 表格中，根據客戶的意見反應，欄會 `DeviceObjectId` 取代欄 `AadDeviceId` 。</span><span class="sxs-lookup"><span data-stu-id="a2926-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="a2926-197">在 [ [DeviceEvents](advanced-hunting-deviceevents-table.md) ] 表格中，已修改數個 ActionType 名稱，以更好地反映動作的描述。</span><span class="sxs-lookup"><span data-stu-id="a2926-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="a2926-198">您可以在下面找到變更的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a2926-198">Details of the changes can be found below.</span></span>

    | <span data-ttu-id="a2926-199">表格名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-199">Table name</span></span> | <span data-ttu-id="a2926-200">原始 ActionType 名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-200">Original ActionType name</span></span> | <span data-ttu-id="a2926-201">新 ActionType 名稱</span><span class="sxs-lookup"><span data-stu-id="a2926-201">New ActionType name</span></span> | <span data-ttu-id="a2926-202">變更的原因</span><span class="sxs-lookup"><span data-stu-id="a2926-202">Reason for change</span></span>
    |--|--|--|--|
    | `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="a2926-203">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="a2926-203">Customer feedback</span></span> |
    | `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="a2926-204">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="a2926-204">Customer feedback</span></span> |
    | `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="a2926-205">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="a2926-205">Customer feedback</span></span> |
    | `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="a2926-206">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="a2926-206">Customer feedback</span></span> |

## <a name="march-2021"></a><span data-ttu-id="a2926-207">2021 年 3 月</span><span class="sxs-lookup"><span data-stu-id="a2926-207">March 2021</span></span>

<span data-ttu-id="a2926-208">`DeviceTvmSoftwareInventoryVulnerabilities`資料表已被取代。</span><span class="sxs-lookup"><span data-stu-id="a2926-208">The `DeviceTvmSoftwareInventoryVulnerabilities` table has been deprecated.</span></span> <span data-ttu-id="a2926-209">請將其取代為 `DeviceTvmSoftwareInventory` 及 `DeviceTvmSoftwareVulnerabilities` 表格。</span><span class="sxs-lookup"><span data-stu-id="a2926-209">Replacing it are the `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables.</span></span>

## <a name="may-2021"></a><span data-ttu-id="a2926-210">2021 年 5 月</span><span class="sxs-lookup"><span data-stu-id="a2926-210">May 2021</span></span>

<span data-ttu-id="a2926-211">`AppFileEvents`資料表已被取代。</span><span class="sxs-lookup"><span data-stu-id="a2926-211">The `AppFileEvents` table has been deprecated.</span></span> <span data-ttu-id="a2926-212">此 `CloudAppEvents` 表格包含用於表格中的資訊 `AppFileEvents` ，以及雲端服務中的其他活動。</span><span class="sxs-lookup"><span data-stu-id="a2926-212">The `CloudAppEvents` table includes information that used to be in the `AppFileEvents` table, along with other activities in cloud services.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2926-213">相關主題</span><span class="sxs-lookup"><span data-stu-id="a2926-213">Related topics</span></span>
- [<span data-ttu-id="a2926-214">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="a2926-214">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a2926-215">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="a2926-215">Understand the schema</span></span>](advanced-hunting-schema-tables.md)