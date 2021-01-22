---
title: 從 Microsoft Defender for Endpoint 進行進位搜尋查詢的遷移
description: 瞭解如何調整您的 Microsoft Defender 端點查詢，以便您可以在 Microsoft 365 Defender 中使用這些查詢
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、microsoft defender atp、mdatp、搜尋、查詢、遙測、自訂偵測、架構、kusto、microsoft 365、地圖
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
ms.openlocfilehash: 08bdd1e22040166bb3becac32580a185c74f34a0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932298"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="375a3-104">從 Microsoft Defender for Endpoint 進行進位搜尋查詢的遷移</span><span class="sxs-lookup"><span data-stu-id="375a3-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="375a3-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="375a3-105">**Applies to:**</span></span>
- <span data-ttu-id="375a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="375a3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="375a3-107">將進一步搜尋工作流程從 Microsoft Defender for Endpoint 移至使用一組更廣泛的資料主動搜尋威脅。</span><span class="sxs-lookup"><span data-stu-id="375a3-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="375a3-108">在 Microsoft 365 Defender 中，您可以存取其他 Microsoft 365 安全性解決方案的資料，包括：</span><span class="sxs-lookup"><span data-stu-id="375a3-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="375a3-109">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="375a3-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="375a3-110">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="375a3-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="375a3-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="375a3-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="375a3-112">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="375a3-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="375a3-113">大部分的 Microsoft Defender for Endpoint 客戶 [可以使用 Microsoft 365 Defender，不需要其他授權](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="375a3-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="375a3-114">若要從 Defender for Endpoint 開始轉換進位搜尋工作流程，[請開啟 Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="375a3-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="375a3-115">您可以轉換而不影響到現有的端點工作流程 Defender。</span><span class="sxs-lookup"><span data-stu-id="375a3-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="375a3-116">已儲存的查詢會保持不變，而自訂偵測規則會繼續執行並產生警示。</span><span class="sxs-lookup"><span data-stu-id="375a3-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="375a3-117">不過，他們會在 Microsoft 365 Defender 中顯示。</span><span class="sxs-lookup"><span data-stu-id="375a3-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="375a3-118">僅適用于 Microsoft 365 Defender 的架構資料表</span><span class="sxs-lookup"><span data-stu-id="375a3-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="375a3-119">[Microsoft 365 Defender 進位搜尋](advanced-hunting-schema-tables.md)架構提供包含來自各種 Microsoft 365 安全性解決方案之資料的其他資料表。</span><span class="sxs-lookup"><span data-stu-id="375a3-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="375a3-120">下表僅適用于 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="375a3-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="375a3-121">表格名稱</span><span class="sxs-lookup"><span data-stu-id="375a3-121">Table name</span></span> | <span data-ttu-id="375a3-122">描述</span><span class="sxs-lookup"><span data-stu-id="375a3-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="375a3-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="375a3-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="375a3-124">與警示相關聯的檔案、IP 位址、URL、使用者或裝置</span><span class="sxs-lookup"><span data-stu-id="375a3-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="375a3-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="375a3-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="375a3-126">來自 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App 安全性及 Microsoft Defender 的身分識別通知，包括嚴重性資訊和威脅類別</span><span class="sxs-lookup"><span data-stu-id="375a3-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="375a3-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="375a3-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="375a3-128">雲端應用程式和服務中的檔案相關活動</span><span class="sxs-lookup"><span data-stu-id="375a3-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="375a3-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="375a3-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="375a3-130">附加至電子郵件之檔案的資訊</span><span class="sxs-lookup"><span data-stu-id="375a3-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="375a3-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="375a3-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="375a3-132">Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件</span><span class="sxs-lookup"><span data-stu-id="375a3-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="375a3-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="375a3-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="375a3-134">Microsoft 365 將電子郵件送達收件者的信箱之後，在傳送後發生的安全性事件</span><span class="sxs-lookup"><span data-stu-id="375a3-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="375a3-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="375a3-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="375a3-136">電子郵件 URL 相關資訊</span><span class="sxs-lookup"><span data-stu-id="375a3-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="375a3-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="375a3-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="375a3-138">涉及內部部署網域控制站執行 Active Directory (AD) 。</span><span class="sxs-lookup"><span data-stu-id="375a3-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="375a3-139">下表涵蓋網域控制站上的一系列身分識別相關事件及系統事件。</span><span class="sxs-lookup"><span data-stu-id="375a3-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="375a3-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="375a3-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="375a3-141">各種來源的帳戶資訊，包括 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="375a3-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="375a3-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="375a3-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="375a3-143">Active Directory 和 Microsoft 線上服務上的驗證事件</span><span class="sxs-lookup"><span data-stu-id="375a3-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="375a3-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="375a3-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="375a3-145">Active Directory 物件的查詢，例如使用者、群組、裝置和網域</span><span class="sxs-lookup"><span data-stu-id="375a3-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="375a3-146">Map DeviceAlertEvents 資料表</span><span class="sxs-lookup"><span data-stu-id="375a3-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="375a3-147">And `AlertInfo` `AlertEvidence` table 會取代 `DeviceAlertEvents` Microsoft Defender for Endpoint 架構中的資料表。</span><span class="sxs-lookup"><span data-stu-id="375a3-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="375a3-148">除了裝置警示資料，這兩個數據表包含身分驗證、應用程式和電子郵件警示的資料。</span><span class="sxs-lookup"><span data-stu-id="375a3-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="375a3-149">使用下表檢查欄如何 `DeviceAlertEvents` 與資料表中的資料行 `AlertInfo` `AlertEvidence` 進行關聯。</span><span class="sxs-lookup"><span data-stu-id="375a3-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="375a3-150">除了下表的欄外，表格還包含許多其他欄，可提供更多來自各種來源 `AlertEvidence` 之通知的全貌。</span><span class="sxs-lookup"><span data-stu-id="375a3-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="375a3-151">查看所有 AlertEvidence 欄</span><span class="sxs-lookup"><span data-stu-id="375a3-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="375a3-152">DeviceAlertEvents 欄</span><span class="sxs-lookup"><span data-stu-id="375a3-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="375a3-153">Microsoft 365 Defender 的相同資料位置</span><span class="sxs-lookup"><span data-stu-id="375a3-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="375a3-154">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="375a3-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="375a3-155">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="375a3-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="375a3-156">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="375a3-157">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="375a3-158">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="375a3-159">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="375a3-160">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="375a3-161">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="375a3-162">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="375a3-163">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="375a3-164">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="375a3-165">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="375a3-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="375a3-166">此欄通常是在 Microsoft Defender for Endpoint 中用來尋找其他資料表中的相關記錄。</span><span class="sxs-lookup"><span data-stu-id="375a3-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="375a3-167">在 Microsoft 365 Defender 中，您可以直接從資料表取得 `AlertEvidence` 相關的資料。</span><span class="sxs-lookup"><span data-stu-id="375a3-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="375a3-168">此欄通常用於 Microsoft Defender for Endpoint，用於其他資料表中的其他事件資訊。</span><span class="sxs-lookup"><span data-stu-id="375a3-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="375a3-169">在 Microsoft 365 Defender 中，您可以直接從資料表取得 `AlertEvidence` 相關的資料。</span><span class="sxs-lookup"><span data-stu-id="375a3-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="375a3-170">調整現有的 Microsoft Defender 端點查詢</span><span class="sxs-lookup"><span data-stu-id="375a3-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="375a3-171">除非參照資料表，否則 Microsoft Defender 的端點查詢將能如新 `DeviceAlertEvents` 工作。</span><span class="sxs-lookup"><span data-stu-id="375a3-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="375a3-172">若要在 Microsoft 365 Defender 中使用這些查詢，請進行以下變更：</span><span class="sxs-lookup"><span data-stu-id="375a3-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="375a3-173">取代 `DeviceAlertEvents` 為 `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="375a3-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="375a3-174">聯 `AlertInfo` 聯資料 `AlertEvidence` 表和資料表 `AlertId` 以取得相等的資料。</span><span class="sxs-lookup"><span data-stu-id="375a3-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="375a3-175">原始查詢</span><span class="sxs-lookup"><span data-stu-id="375a3-175">Original query</span></span>
<span data-ttu-id="375a3-176">下列查詢會 `DeviceAlertEvents` 使用 Microsoft Defender for Endpoint 取得與下列powershell.exe：</span><span class="sxs-lookup"><span data-stu-id="375a3-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="375a3-177">已修改查詢</span><span class="sxs-lookup"><span data-stu-id="375a3-177">Modified query</span></span>
<span data-ttu-id="375a3-178">下列查詢已調整為在 Microsoft 365 Defender 中使用。</span><span class="sxs-lookup"><span data-stu-id="375a3-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="375a3-179">它無需直接檢查檔案名，而會聯入並檢查 `DeviceAlertEvents` `AlertEvidence` 資料表中的檔案名。</span><span class="sxs-lookup"><span data-stu-id="375a3-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="375a3-180">相關主題</span><span class="sxs-lookup"><span data-stu-id="375a3-180">Related topics</span></span>
- [<span data-ttu-id="375a3-181">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="375a3-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="375a3-182">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="375a3-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="375a3-183">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="375a3-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="375a3-184">Microsoft Defender for Endpoint 中的進位搜尋</span><span class="sxs-lookup"><span data-stu-id="375a3-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)