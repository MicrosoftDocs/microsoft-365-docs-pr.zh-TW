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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066866"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="4eea2-104">高級搜尋架構命名變更</span><span class="sxs-lookup"><span data-stu-id="4eea2-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4eea2-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="4eea2-105">**Applies to:**</span></span>
- <span data-ttu-id="4eea2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4eea2-107">「 [高級搜尋」架構](advanced-hunting-schema-tables.md) 會定期更新，以加入新的資料表和欄。</span><span class="sxs-lookup"><span data-stu-id="4eea2-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="4eea2-108">在某些情況下，會重新命名或取代現有的欄名，以提升使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="4eea2-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="4eea2-109">請參閱本文，以複查可能影響查詢的命名變更。</span><span class="sxs-lookup"><span data-stu-id="4eea2-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="4eea2-110">命名變更會自動套用至儲存在 [安全性中心] 中的查詢，包括自訂偵測規則所使用的查詢。</span><span class="sxs-lookup"><span data-stu-id="4eea2-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="4eea2-111">您不需要手動更新這些查詢。</span><span class="sxs-lookup"><span data-stu-id="4eea2-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="4eea2-112">不過，您將需要更新下列查詢：</span><span class="sxs-lookup"><span data-stu-id="4eea2-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="4eea2-113">使用 API 執行的查詢</span><span class="sxs-lookup"><span data-stu-id="4eea2-113">Queries that are run using the API</span></span>
- <span data-ttu-id="4eea2-114">儲存在安全性中心以外其他位置的查詢</span><span class="sxs-lookup"><span data-stu-id="4eea2-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="4eea2-115">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="4eea2-115">December 2020</span></span>

| <span data-ttu-id="4eea2-116">表格名稱</span><span class="sxs-lookup"><span data-stu-id="4eea2-116">Table name</span></span> | <span data-ttu-id="4eea2-117">原始欄名稱</span><span class="sxs-lookup"><span data-stu-id="4eea2-117">Original column name</span></span> | <span data-ttu-id="4eea2-118">新欄名稱</span><span class="sxs-lookup"><span data-stu-id="4eea2-118">New column name</span></span> | <span data-ttu-id="4eea2-119">變更的原因</span><span class="sxs-lookup"><span data-stu-id="4eea2-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="4eea2-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4eea2-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="4eea2-121">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="4eea2-121">Customer feedback</span></span> |
| [<span data-ttu-id="4eea2-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4eea2-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="4eea2-123">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="4eea2-123">Customer feedback</span></span> |
| [<span data-ttu-id="4eea2-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4eea2-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="4eea2-125">客戶意見反應</span><span class="sxs-lookup"><span data-stu-id="4eea2-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="4eea2-126">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="4eea2-126">January 2021</span></span>

| <span data-ttu-id="4eea2-127">資料行名稱</span><span class="sxs-lookup"><span data-stu-id="4eea2-127">Column name</span></span> | <span data-ttu-id="4eea2-128">原始值名稱</span><span class="sxs-lookup"><span data-stu-id="4eea2-128">Original value name</span></span> | <span data-ttu-id="4eea2-129">新值名稱</span><span class="sxs-lookup"><span data-stu-id="4eea2-129">New value name</span></span> | <span data-ttu-id="4eea2-130">變更的原因</span><span class="sxs-lookup"><span data-stu-id="4eea2-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="4eea2-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="4eea2-131">MCAS</span></span> |    <span data-ttu-id="4eea2-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4eea2-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="4eea2-133">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="4eea2-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="4eea2-135">EDR</span><span class="sxs-lookup"><span data-stu-id="4eea2-135">EDR</span></span>| <span data-ttu-id="4eea2-136">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="4eea2-137">WindowsDefenderAv</span></span> | <span data-ttu-id="4eea2-138">防毒</span><span class="sxs-lookup"><span data-stu-id="4eea2-138">Antivirus</span></span> | <span data-ttu-id="4eea2-139">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="4eea2-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="4eea2-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="4eea2-141">SmartScreen</span></span> | <span data-ttu-id="4eea2-142">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="4eea2-143">CustomerTI</span></span> |  <span data-ttu-id="4eea2-144">自訂 TI</span><span class="sxs-lookup"><span data-stu-id="4eea2-144">Custom TI</span></span> | <span data-ttu-id="4eea2-145">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="4eea2-146">OfficeATP</span></span> | <span data-ttu-id="4eea2-147">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="4eea2-148">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-149">具有 MTP 之</span><span class="sxs-lookup"><span data-stu-id="4eea2-149">MTP</span></span>   | <span data-ttu-id="4eea2-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="4eea2-151">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="4eea2-152">AzureATP</span></span> |    <span data-ttu-id="4eea2-153">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="4eea2-154">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="4eea2-155">CustomDetection</span></span>   | <span data-ttu-id="4eea2-156">自訂偵測</span><span class="sxs-lookup"><span data-stu-id="4eea2-156">Custom detection</span></span> | <span data-ttu-id="4eea2-157">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="4eea2-158">AutomatedInvestigation</span></span> |<span data-ttu-id="4eea2-159">自動調查</span><span class="sxs-lookup"><span data-stu-id="4eea2-159">Automated investigation</span></span> | <span data-ttu-id="4eea2-160">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="4eea2-161">ThreatExperts</span></span> | <span data-ttu-id="4eea2-162">Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="4eea2-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="4eea2-163">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="4eea2-164">協力廠商的 TI</span><span class="sxs-lookup"><span data-stu-id="4eea2-164">3rd party TI</span></span> | <span data-ttu-id="4eea2-165">協力廠商感應器</span><span class="sxs-lookup"><span data-stu-id="4eea2-165">3rd Party sensors</span></span> | <span data-ttu-id="4eea2-166">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="4eea2-167">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4eea2-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="4eea2-168">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="4eea2-169">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="4eea2-170">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="4eea2-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="4eea2-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="4eea2-172">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="4eea2-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4eea2-173">Office 365 ATP</span></span>  |<span data-ttu-id="4eea2-174">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="4eea2-175">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="4eea2-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="4eea2-176">Azure ATP</span></span>    |<span data-ttu-id="4eea2-177">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4eea2-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="4eea2-178">..Org</span><span class="sxs-lookup"><span data-stu-id="4eea2-178">Rebranding</span></span> |

<span data-ttu-id="4eea2-179">`DetectionSource` 可用於 [AlertInfo](advanced-hunting-alertinfo-table.md) 表格。</span><span class="sxs-lookup"><span data-stu-id="4eea2-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="4eea2-180">`ServiceSource` 可用於 [AlertEvidence](advanced-hunting-alertevidence-table.md) 和 [AlertInfo](advanced-hunting-alertinfo-table.md) 資料表。</span><span class="sxs-lookup"><span data-stu-id="4eea2-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="4eea2-181">相關主題</span><span class="sxs-lookup"><span data-stu-id="4eea2-181">Related topics</span></span>
- [<span data-ttu-id="4eea2-182">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="4eea2-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4eea2-183">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="4eea2-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)