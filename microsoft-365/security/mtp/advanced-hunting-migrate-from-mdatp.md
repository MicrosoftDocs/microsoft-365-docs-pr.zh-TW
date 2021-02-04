---
title: 從 Microsoft Defender for Endpoint 遷移高級搜尋查詢
description: 瞭解如何調整您的 Microsoft Defender 以進行端點查詢，讓您可以在 Microsoft 365 Defender 中使用它們
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，microsoft defender atp，mdatp，search，查詢，遙測，自訂偵測，schema，kusto，microsoft 365，對應
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094804"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="eddcc-104">從 Microsoft Defender for Endpoint 遷移高級搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="eddcc-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eddcc-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="eddcc-105">**Applies to:**</span></span>
- <span data-ttu-id="eddcc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eddcc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="eddcc-107">從 Microsoft Defender for Endpoint 移動您的高級搜尋工作流程，以使用更多資料集主動搜尋威脅。</span><span class="sxs-lookup"><span data-stu-id="eddcc-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="eddcc-108">在 Microsoft 365 Defender 中，您可以從其他 Microsoft 365 安全性解決方案中取得資料的存取權，包括：</span><span class="sxs-lookup"><span data-stu-id="eddcc-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="eddcc-109">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eddcc-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="eddcc-110">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eddcc-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="eddcc-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="eddcc-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="eddcc-112">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eddcc-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="eddcc-113">大多數 Microsoft Defender for Endpoint 客戶可以 [使用不含額外授權的 microsoft 365 Defender](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="eddcc-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="eddcc-114">若要開始從 Endpoint for Endpoint 轉換您的高級搜尋工作流程，請 [開啟 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="eddcc-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="eddcc-115">您可以轉換，而不會影響現有的端點工作流程。</span><span class="sxs-lookup"><span data-stu-id="eddcc-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="eddcc-116">儲存的查詢會保持不變，而且自訂偵測規則會繼續執行並產生警示。</span><span class="sxs-lookup"><span data-stu-id="eddcc-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="eddcc-117">不過，它們會顯示在 Microsoft 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="eddcc-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="eddcc-118">僅限 Microsoft 365 Defender 中的架構表格</span><span class="sxs-lookup"><span data-stu-id="eddcc-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="eddcc-119">[Microsoft 365 Defender advanced 搜尋架構](advanced-hunting-schema-tables.md)提供額外的資料表，其中包含各種 Microsoft 365 安全性解決方案中的資料。</span><span class="sxs-lookup"><span data-stu-id="eddcc-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="eddcc-120">下清單格僅適用于 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="eddcc-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="eddcc-121">表格名稱</span><span class="sxs-lookup"><span data-stu-id="eddcc-121">Table name</span></span> | <span data-ttu-id="eddcc-122">描述</span><span class="sxs-lookup"><span data-stu-id="eddcc-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="eddcc-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="eddcc-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="eddcc-124">與警示相關聯的檔案、IP 位址、URLs、使用者或裝置</span><span class="sxs-lookup"><span data-stu-id="eddcc-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="eddcc-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="eddcc-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="eddcc-126">Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 及 Microsoft Defender for Identity 的警示，包括嚴重性資訊和威脅類別</span><span class="sxs-lookup"><span data-stu-id="eddcc-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="eddcc-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="eddcc-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="eddcc-128">雲端應用程式和服務中的檔相關活動</span><span class="sxs-lookup"><span data-stu-id="eddcc-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="eddcc-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="eddcc-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="eddcc-130">附加至電子郵件之檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="eddcc-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="eddcc-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="eddcc-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="eddcc-132">Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件</span><span class="sxs-lookup"><span data-stu-id="eddcc-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="eddcc-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="eddcc-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="eddcc-134">Microsoft 365 將電子郵件傳遞至收件者信箱之後，進行傳遞後的安全性事件</span><span class="sxs-lookup"><span data-stu-id="eddcc-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="eddcc-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="eddcc-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="eddcc-136">有關電子郵件 URLs 的資訊</span><span class="sxs-lookup"><span data-stu-id="eddcc-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="eddcc-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="eddcc-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="eddcc-138">與執行 Active Directory (AD) 的內部部署網域控制站相關的事件。</span><span class="sxs-lookup"><span data-stu-id="eddcc-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="eddcc-139">此表格涵蓋網域控制站上的身分識別相關事件和系統事件範圍。</span><span class="sxs-lookup"><span data-stu-id="eddcc-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="eddcc-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="eddcc-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="eddcc-141">各來源的帳戶資訊，包括 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eddcc-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="eddcc-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="eddcc-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="eddcc-143">Active Directory 和 Microsoft online services 上的驗證事件</span><span class="sxs-lookup"><span data-stu-id="eddcc-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="eddcc-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="eddcc-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="eddcc-145">使用 Active Directory 物件的查詢，例如使用者、群組、裝置和網域</span><span class="sxs-lookup"><span data-stu-id="eddcc-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="eddcc-146">Map DeviceAlertEvents 表格</span><span class="sxs-lookup"><span data-stu-id="eddcc-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="eddcc-147">`AlertInfo`和 `AlertEvidence` 表格會取代 `DeviceAlertEvents` Microsoft Defender for Endpoint 架構中的表格。</span><span class="sxs-lookup"><span data-stu-id="eddcc-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="eddcc-148">除了裝置警示的資料之外，這兩個表格也包含有關身分識別、應用程式及電子郵件警示的資料。</span><span class="sxs-lookup"><span data-stu-id="eddcc-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="eddcc-149">請使用下表來檢查資料 `DeviceAlertEvents` 行對應至 [表格] 中欄的方式 `AlertInfo` `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="eddcc-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="eddcc-150">除了下表所列的資料行以外，此 `AlertEvidence` 表格還包含許多其他的欄，可提供來自各種來源之更整體的警示。</span><span class="sxs-lookup"><span data-stu-id="eddcc-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="eddcc-151">查看所有 AlertEvidence 欄</span><span class="sxs-lookup"><span data-stu-id="eddcc-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="eddcc-152">DeviceAlertEvents 欄</span><span class="sxs-lookup"><span data-stu-id="eddcc-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="eddcc-153">在 Microsoft 365 Defender 中尋找相同資料的位置</span><span class="sxs-lookup"><span data-stu-id="eddcc-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="eddcc-154">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="eddcc-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="eddcc-155">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="eddcc-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="eddcc-156">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="eddcc-157">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="eddcc-158">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="eddcc-159">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="eddcc-160">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="eddcc-161">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="eddcc-162">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="eddcc-163">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="eddcc-164">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="eddcc-165">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="eddcc-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="eddcc-166">此欄通常用在 Microsoft Defender for Endpoint 中，以尋找其他資料表中的相關記錄。</span><span class="sxs-lookup"><span data-stu-id="eddcc-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="eddcc-167">在 Microsoft 365 Defender 中，您可以直接從資料表取得相關資料 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="eddcc-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="eddcc-168">此欄通常用於 Microsoft Defender for Endpoint 中其他資料表中的其他事件資訊。</span><span class="sxs-lookup"><span data-stu-id="eddcc-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="eddcc-169">在 Microsoft 365 Defender 中，您可以直接從資料表取得相關資料 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="eddcc-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="eddcc-170">調整現有的 Microsoft Defender for Endpoint 查詢</span><span class="sxs-lookup"><span data-stu-id="eddcc-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="eddcc-171">Microsoft Defender for Endpoint 查詢會以-為單位運作，除非他們參考 `DeviceAlertEvents` 該表。</span><span class="sxs-lookup"><span data-stu-id="eddcc-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="eddcc-172">若要在 Microsoft 365 Defender 中使用這些查詢，請套用下列變更：</span><span class="sxs-lookup"><span data-stu-id="eddcc-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="eddcc-173">取代 `DeviceAlertEvents` `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="eddcc-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="eddcc-174">加入 `AlertInfo` 和上的 `AlertEvidence` 資料表， `AlertId` 以取得對等資料。</span><span class="sxs-lookup"><span data-stu-id="eddcc-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="eddcc-175">原始查詢</span><span class="sxs-lookup"><span data-stu-id="eddcc-175">Original query</span></span>
<span data-ttu-id="eddcc-176">下列查詢會 `DeviceAlertEvents` 在 Microsoft Defender For Endpoint 中使用，以取得涉及 _powershell.exe_ 的警示：</span><span class="sxs-lookup"><span data-stu-id="eddcc-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="eddcc-177">修改的查詢</span><span class="sxs-lookup"><span data-stu-id="eddcc-177">Modified query</span></span>
<span data-ttu-id="eddcc-178">下列查詢已調整為用於 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="eddcc-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="eddcc-179">`DeviceAlertEvents`它會加入 `AlertEvidence` 並檢查該表中的檔案名，而不是直接檢查檔案名。</span><span class="sxs-lookup"><span data-stu-id="eddcc-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="eddcc-180">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eddcc-180">See also</span></span>
- [<span data-ttu-id="eddcc-181">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eddcc-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="eddcc-182">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="eddcc-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="eddcc-183">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="eddcc-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="eddcc-184">Microsoft Defender for Endpoint 中的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="eddcc-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)