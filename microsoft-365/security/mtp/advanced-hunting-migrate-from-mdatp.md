---
title: 從 Microsoft Defender ATP 遷移高級搜尋查詢
description: 瞭解如何調整您的 Microsoft Defender ATP 查詢，讓您可以在 Microsoft 威脅防護中使用它們
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，microsoft defender atp，mdatp，search，查詢，遙測，自訂偵測，schema，kusto，microsoft 365，對應
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429692"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="4b1c8-104">從 Microsoft Defender ATP 遷移高級搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="4b1c8-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4b1c8-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4b1c8-105">**Applies to:**</span></span>
- <span data-ttu-id="4b1c8-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="4b1c8-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4b1c8-107">從 Microsoft Defender ATP 移動您的高級搜尋工作流程，以主動使用更多資料集來尋找威脅。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="4b1c8-108">在 Microsoft 威脅防護中，您可以存取其他 Microsoft 365 安全性解決方案中的資料，包括：</span><span class="sxs-lookup"><span data-stu-id="4b1c8-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="4b1c8-109">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4b1c8-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="4b1c8-110">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4b1c8-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="4b1c8-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4b1c8-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="4b1c8-112">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4b1c8-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="4b1c8-113">大部分的 Microsoft Defender ATP 客戶可以 [使用不含其他授權的 Microsoft 威脅防護](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="4b1c8-114">若要從 Microsoft Defender ATP 開始轉換您的高級搜尋工作流程，請 [開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="4b1c8-115">您可以轉換，而不會影響現有的 Microsoft Defender ATP 工作流程。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="4b1c8-116">儲存的查詢會保持不變，而且自訂偵測規則會繼續執行並產生警示。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="4b1c8-117">不過，他們會在 Microsoft 威脅防護中看到。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="4b1c8-118">僅限 Microsoft 威脅防護中的架構表格</span><span class="sxs-lookup"><span data-stu-id="4b1c8-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="4b1c8-119">[Microsoft 威脅防護高級搜尋架構](advanced-hunting-schema-tables.md)提供額外的資料表，其中包含各種 Microsoft 365 安全性解決方案中的資料。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="4b1c8-120">下清單格僅適用于 Microsoft 威脅防護：</span><span class="sxs-lookup"><span data-stu-id="4b1c8-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="4b1c8-121">表格名稱</span><span class="sxs-lookup"><span data-stu-id="4b1c8-121">Table name</span></span> | <span data-ttu-id="4b1c8-122">描述</span><span class="sxs-lookup"><span data-stu-id="4b1c8-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="4b1c8-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="4b1c8-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="4b1c8-124">與警示相關聯的檔案、IP 位址、URLs、使用者或裝置</span><span class="sxs-lookup"><span data-stu-id="4b1c8-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="4b1c8-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="4b1c8-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="4b1c8-126">來自 Microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的警示，包括嚴重性資訊和威脅類別</span><span class="sxs-lookup"><span data-stu-id="4b1c8-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="4b1c8-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="4b1c8-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="4b1c8-128">雲端應用程式和服務中的檔相關活動</span><span class="sxs-lookup"><span data-stu-id="4b1c8-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="4b1c8-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="4b1c8-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="4b1c8-130">附加至電子郵件之檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="4b1c8-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="4b1c8-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4b1c8-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="4b1c8-132">Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件</span><span class="sxs-lookup"><span data-stu-id="4b1c8-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="4b1c8-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="4b1c8-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="4b1c8-134">Microsoft 365 將電子郵件傳遞至收件者信箱之後，進行傳遞後的安全性事件</span><span class="sxs-lookup"><span data-stu-id="4b1c8-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="4b1c8-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="4b1c8-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="4b1c8-136">有關電子郵件 URLs 的資訊</span><span class="sxs-lookup"><span data-stu-id="4b1c8-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="4b1c8-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="4b1c8-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="4b1c8-138">與執行 Active Directory (AD) 的內部部署網域控制站相關的事件。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="4b1c8-139">此表格涵蓋網域控制站上的身分識別相關事件和系統事件範圍。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="4b1c8-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="4b1c8-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="4b1c8-141">各來源的帳戶資訊，包括 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4b1c8-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="4b1c8-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="4b1c8-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="4b1c8-143">Active Directory 和 Microsoft online services 上的驗證事件</span><span class="sxs-lookup"><span data-stu-id="4b1c8-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="4b1c8-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="4b1c8-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="4b1c8-145">使用 Active Directory 物件的查詢，例如使用者、群組、裝置和網域</span><span class="sxs-lookup"><span data-stu-id="4b1c8-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="4b1c8-146">Map DeviceAlertEvents 表格</span><span class="sxs-lookup"><span data-stu-id="4b1c8-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="4b1c8-147">`AlertInfo`和 `AlertEvidence` tables 會取代 `DeviceAlertEvents` Microsoft Defender ATP 架構中的表格。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="4b1c8-148">除了裝置警示的資料之外，這兩個表格也包含有關身分識別、應用程式及電子郵件警示的資料。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="4b1c8-149">請使用下表來檢查資料 `DeviceAlertEvents` 行對應至 [表格] 中欄的方式 `AlertInfo` `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="4b1c8-150">除了下表所列的資料行以外，此 `AlertEvidence` 表格還包含許多其他的欄，可提供來自各種來源之更整體的警示。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="4b1c8-151">查看所有 AlertEvidence 欄</span><span class="sxs-lookup"><span data-stu-id="4b1c8-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="4b1c8-152">DeviceAlertEvents 欄</span><span class="sxs-lookup"><span data-stu-id="4b1c8-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="4b1c8-153">在 Microsoft 威脅防護中尋找相同資料的位置</span><span class="sxs-lookup"><span data-stu-id="4b1c8-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="4b1c8-154">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="4b1c8-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="4b1c8-155">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="4b1c8-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="4b1c8-156">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="4b1c8-157">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="4b1c8-158">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="4b1c8-159">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="4b1c8-160">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="4b1c8-161">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="4b1c8-162">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="4b1c8-163">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="4b1c8-164">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="4b1c8-165">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="4b1c8-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="4b1c8-166">此欄通常用在 Microsoft Defender ATP 中，以尋找其他資料表中的相關記錄。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="4b1c8-167">在 Microsoft 威脅防護中，您可以直接從資料表取得相關資料 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="4b1c8-168">此欄通常用於 Microsoft Defender ATP 中其他資料表中的其他事件資訊。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="4b1c8-169">在 Microsoft 威脅防護中，您可以直接從資料表取得相關資料 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="4b1c8-170">調整現有的 Microsoft Defender ATP 查詢</span><span class="sxs-lookup"><span data-stu-id="4b1c8-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="4b1c8-171">除非參考該表，否則 Microsoft Defender ATP 查詢將會以原樣運作 `DeviceAlertEvents` 。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="4b1c8-172">若要在 Microsoft 威脅防護中使用這些查詢，請套用下列變更：</span><span class="sxs-lookup"><span data-stu-id="4b1c8-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="4b1c8-173">取代 `DeviceAlertEvents` `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="4b1c8-174">加入 `AlertInfo` 和上的 `AlertEvidence` 資料表， `AlertId` 以取得對等資料。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="4b1c8-175">原始查詢</span><span class="sxs-lookup"><span data-stu-id="4b1c8-175">Original query</span></span>
<span data-ttu-id="4b1c8-176">下列查詢會 `DeviceAlertEvents` 在 Microsoft DEFENDER ATP 中使用，以取得涉及 _powershell.exe_的警示：</span><span class="sxs-lookup"><span data-stu-id="4b1c8-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="4b1c8-177">修改的查詢</span><span class="sxs-lookup"><span data-stu-id="4b1c8-177">Modified query</span></span>
<span data-ttu-id="4b1c8-178">下列查詢已調整為用於 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="4b1c8-179">`DeviceAlertEvents`它會加入 `AlertEvidence` 並檢查該表中的檔案名，而不是直接檢查檔案名。</span><span class="sxs-lookup"><span data-stu-id="4b1c8-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="4b1c8-180">相關主題</span><span class="sxs-lookup"><span data-stu-id="4b1c8-180">Related topics</span></span>
- [<span data-ttu-id="4b1c8-181">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="4b1c8-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4b1c8-182">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="4b1c8-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4b1c8-183">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="4b1c8-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4b1c8-184">Microsoft Defender ATP 中的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="4b1c8-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)