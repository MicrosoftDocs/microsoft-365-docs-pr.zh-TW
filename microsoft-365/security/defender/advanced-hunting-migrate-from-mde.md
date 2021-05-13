---
title: 從 Microsoft Defender for Endpoint 遷移高級搜尋查詢
description: 瞭解如何調整 Microsoft defender for Endpoint 查詢，以便在 Microsoft 365 defender 中使用。
keywords: 高級搜尋、威脅搜尋、網路威脅搜尋、Microsoft 365 defender、microsoft 365、m365、microsoft defender for 端點、搜尋、查詢、遙測、自訂偵測、架構、kusto、對應
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470685"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="8d030-104">從 Microsoft Defender for Endpoint 遷移高級搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="8d030-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8d030-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8d030-105">**Applies to:**</span></span>
- <span data-ttu-id="8d030-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d030-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8d030-107">從 Microsoft Defender for Endpoint 移動您的高級搜尋工作流程，以使用更多資料集主動搜尋威脅。</span><span class="sxs-lookup"><span data-stu-id="8d030-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="8d030-108">在 Microsoft 365 Defender 中，您可以存取其他 Microsoft 365 安全性解決方案中的資料，包括：</span><span class="sxs-lookup"><span data-stu-id="8d030-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="8d030-109">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8d030-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="8d030-110">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8d030-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="8d030-111">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="8d030-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="8d030-112">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8d030-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="8d030-113">大多數 Microsoft defender for Endpoint 客戶可以[使用 Microsoft 365 Defender，但不含其他授權](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="8d030-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="8d030-114">若要開始從 Endpoint for Endpoint 轉換您的高級搜尋工作流程，請[開啟 Microsoft 365 defender](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="8d030-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="8d030-115">您可以轉換，而不會影響現有的端點工作流程。</span><span class="sxs-lookup"><span data-stu-id="8d030-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="8d030-116">儲存的查詢會保持不變，而且自訂偵測規則會繼續執行並產生警示。</span><span class="sxs-lookup"><span data-stu-id="8d030-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="8d030-117">不過，Microsoft 365 Defender 會顯示這些功能。</span><span class="sxs-lookup"><span data-stu-id="8d030-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="8d030-118">僅限 Microsoft 365 Defender 中的架構表格</span><span class="sxs-lookup"><span data-stu-id="8d030-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="8d030-119">[Microsoft 365 的 Defender 高級搜尋架構](advanced-hunting-schema-tables.md)提供額外的資料表，其中包含各種 Microsoft 365 安全性解決方案的資料。</span><span class="sxs-lookup"><span data-stu-id="8d030-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="8d030-120">下表僅適用于 Microsoft 365 Defender：</span><span class="sxs-lookup"><span data-stu-id="8d030-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="8d030-121">表格名稱</span><span class="sxs-lookup"><span data-stu-id="8d030-121">Table name</span></span> | <span data-ttu-id="8d030-122">描述</span><span class="sxs-lookup"><span data-stu-id="8d030-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="8d030-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="8d030-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="8d030-124">與警示相關聯的檔案、IP 位址、URLs、使用者或裝置</span><span class="sxs-lookup"><span data-stu-id="8d030-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="8d030-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="8d030-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="8d030-126">microsoft defender for Endpoint、microsoft defender for Office 365、Microsoft Cloud App Security 和 microsoft defender for Identity 的警示，包括嚴重性資訊和威脅類別</span><span class="sxs-lookup"><span data-stu-id="8d030-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="8d030-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="8d030-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="8d030-128">附加至電子郵件之檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="8d030-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="8d030-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8d030-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="8d030-130">Microsoft 365 電子郵件事件，包括電子郵件傳遞和封鎖事件</span><span class="sxs-lookup"><span data-stu-id="8d030-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="8d030-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="8d030-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="8d030-132">Microsoft 365 將電子郵件傳遞至收件者信箱之後，進行傳遞後的安全性事件</span><span class="sxs-lookup"><span data-stu-id="8d030-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="8d030-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="8d030-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="8d030-134">有關電子郵件 URLs 的資訊</span><span class="sxs-lookup"><span data-stu-id="8d030-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="8d030-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="8d030-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="8d030-136">與執行 Active Directory (AD) 的內部部署網域控制站相關的事件。</span><span class="sxs-lookup"><span data-stu-id="8d030-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="8d030-137">此表格涵蓋網域控制站上的身分識別相關事件和系統事件範圍。</span><span class="sxs-lookup"><span data-stu-id="8d030-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="8d030-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="8d030-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="8d030-139">各來源的帳戶資訊，包括 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8d030-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="8d030-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="8d030-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="8d030-141">Active Directory 和 Microsoft online services 上的驗證事件</span><span class="sxs-lookup"><span data-stu-id="8d030-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="8d030-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="8d030-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="8d030-143">使用 Active Directory 物件的查詢，例如使用者、群組、裝置和網域</span><span class="sxs-lookup"><span data-stu-id="8d030-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="8d030-144">使用只能在 Microsoft 365 Defender 中使用之架構表的查詢和自訂偵測只可在 Microsoft 365 Defender 中查看。</span><span class="sxs-lookup"><span data-stu-id="8d030-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="8d030-145">Map DeviceAlertEvents 表格</span><span class="sxs-lookup"><span data-stu-id="8d030-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="8d030-146">`AlertInfo`和 `AlertEvidence` 表格會取代 `DeviceAlertEvents` Microsoft Defender for Endpoint 架構中的表格。</span><span class="sxs-lookup"><span data-stu-id="8d030-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="8d030-147">除了裝置警示的資料之外，這兩個表格也包含有關身分識別、應用程式及電子郵件警示的資料。</span><span class="sxs-lookup"><span data-stu-id="8d030-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="8d030-148">請使用下表來檢查資料 `DeviceAlertEvents` 行對應至 [表格] 中欄的方式 `AlertInfo` `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="8d030-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="8d030-149">除了下表中的欄以外，此表格還 `AlertEvidence` 包含許多其他的欄，可提供來自各種來源的更整體警示。</span><span class="sxs-lookup"><span data-stu-id="8d030-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="8d030-150">查看所有 AlertEvidence 欄</span><span class="sxs-lookup"><span data-stu-id="8d030-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="8d030-151">DeviceAlertEvents 欄</span><span class="sxs-lookup"><span data-stu-id="8d030-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="8d030-152">在 Microsoft 365 Defender 中尋找相同資料的位置</span><span class="sxs-lookup"><span data-stu-id="8d030-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="8d030-153">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="8d030-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="8d030-154">`AlertInfo` 和  `AlertEvidence` 表格</span><span class="sxs-lookup"><span data-stu-id="8d030-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="8d030-155">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="8d030-156">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="8d030-157">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="8d030-158">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="8d030-159">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="8d030-160">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="8d030-161">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="8d030-162">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="8d030-163">`AlertEvidence` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="8d030-164">`AlertInfo` 表</span><span class="sxs-lookup"><span data-stu-id="8d030-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="8d030-165">此欄通常用在 Microsoft Defender for Endpoint 中，以尋找其他資料表中的相關記錄。</span><span class="sxs-lookup"><span data-stu-id="8d030-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="8d030-166">在 Microsoft 365 Defender 中，您可以直接從資料表取得相關資料 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="8d030-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="8d030-167">此欄通常用於 Microsoft Defender for Endpoint 中其他資料表中的其他事件資訊。</span><span class="sxs-lookup"><span data-stu-id="8d030-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="8d030-168">在 Microsoft 365 Defender 中，您可以直接從資料表取得相關資料 `AlertEvidence` 。</span><span class="sxs-lookup"><span data-stu-id="8d030-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="8d030-169">調整現有的 Microsoft Defender for Endpoint 查詢</span><span class="sxs-lookup"><span data-stu-id="8d030-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="8d030-170">Microsoft Defender for Endpoint 查詢會以-為單位運作，除非他們參考 `DeviceAlertEvents` 該表。</span><span class="sxs-lookup"><span data-stu-id="8d030-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="8d030-171">若要在 Microsoft 365 Defender 中使用這些查詢，請套用下列變更：</span><span class="sxs-lookup"><span data-stu-id="8d030-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="8d030-172">取代 `DeviceAlertEvents` `AlertInfo` 。</span><span class="sxs-lookup"><span data-stu-id="8d030-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="8d030-173">加入 `AlertInfo` 和上的 `AlertEvidence` 資料表， `AlertId` 以取得對等資料。</span><span class="sxs-lookup"><span data-stu-id="8d030-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="8d030-174">原始查詢</span><span class="sxs-lookup"><span data-stu-id="8d030-174">Original query</span></span>
<span data-ttu-id="8d030-175">下列查詢會 `DeviceAlertEvents` 在 Microsoft Defender For Endpoint 中使用，以取得涉及 _powershell.exe_ 的警示：</span><span class="sxs-lookup"><span data-stu-id="8d030-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="8d030-176">修改的查詢</span><span class="sxs-lookup"><span data-stu-id="8d030-176">Modified query</span></span>
<span data-ttu-id="8d030-177">下列查詢已調整為用於 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="8d030-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="8d030-178">`DeviceAlertEvents`它會加入 `AlertEvidence` 並檢查該表中的檔案名，而不是直接檢查檔案名。</span><span class="sxs-lookup"><span data-stu-id="8d030-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="8d030-179">遷移自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="8d030-179">Migrate custom detection rules</span></span>

<span data-ttu-id="8d030-180">當 Microsoft defender for Endpoint rules 在 Microsoft 365 defender 上編輯時，如果結果查詢只會查看裝置資料表，便會繼續像之前一樣運作。</span><span class="sxs-lookup"><span data-stu-id="8d030-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="8d030-181">例如，自訂偵測規則所產生的警示，只要查詢裝置資料表，就會繼續傳遞到您的 SIEM 並產生電子郵件通知，視您在 Microsoft Defender for Endpoint 中的設定方式而定。</span><span class="sxs-lookup"><span data-stu-id="8d030-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8d030-182">在 Defender for Endpoint 中的任何現有抑制規則也會繼續套用。</span><span class="sxs-lookup"><span data-stu-id="8d030-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="8d030-183">一旦您編輯了某一 defender for Endpoint 規則，讓它查詢身分識別和電子郵件表格（僅 Microsoft 365 defender 中提供），該規則就會自動移至 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="8d030-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="8d030-184">由遷移的規則所產生的警示：</span><span class="sxs-lookup"><span data-stu-id="8d030-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="8d030-185">在端點入口網站 (Microsoft Defender 資訊安全中心中不再顯示) </span><span class="sxs-lookup"><span data-stu-id="8d030-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="8d030-186">停止傳遞到您的 SIEM 或產生電子郵件通知。</span><span class="sxs-lookup"><span data-stu-id="8d030-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="8d030-187">若要解決此變更，請透過 Microsoft 365 Defender 設定通知，以取得提醒。</span><span class="sxs-lookup"><span data-stu-id="8d030-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="8d030-188">您可以使用[Microsoft 365 Defender API](api-incident.md)接收客戶偵測警示或相關事件的通知。</span><span class="sxs-lookup"><span data-stu-id="8d030-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="8d030-189">不會由 Microsoft Defender for Endpoint 抑制規則抑制。</span><span class="sxs-lookup"><span data-stu-id="8d030-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="8d030-190">若要防止針對某些使用者、裝置或信箱產生警示，請修改對應的查詢以明確排除那些實體。</span><span class="sxs-lookup"><span data-stu-id="8d030-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="8d030-191">如果您以這種方式編輯規則，則在套用此類變更之前，系統會提示您進行確認。</span><span class="sxs-lookup"><span data-stu-id="8d030-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="8d030-192">由 Microsoft 365 Defender 入口網站中的自訂偵測規則所產生的新警示會顯示在警示頁面中，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="8d030-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="8d030-193">提醒標題和描述</span><span class="sxs-lookup"><span data-stu-id="8d030-193">Alert title and description</span></span> 
- <span data-ttu-id="8d030-194">受影響資產</span><span class="sxs-lookup"><span data-stu-id="8d030-194">Impacted assets</span></span>
- <span data-ttu-id="8d030-195">回應提醒所採取的動作</span><span class="sxs-lookup"><span data-stu-id="8d030-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="8d030-196">觸發警示的查詢結果</span><span class="sxs-lookup"><span data-stu-id="8d030-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="8d030-197">自訂偵測規則的資訊</span><span class="sxs-lookup"><span data-stu-id="8d030-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d030-198">![新警示頁面的圖像](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="8d030-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="8d030-199">寫入不含 DeviceAlertEvents 的查詢</span><span class="sxs-lookup"><span data-stu-id="8d030-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="8d030-200">在 Microsoft 365 的 Defender 架構中， `AlertInfo` `AlertEvidence` 會提供和資料表，以容納不同來源的警示附帶的資訊集。</span><span class="sxs-lookup"><span data-stu-id="8d030-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="8d030-201">若要取得您用來從 `DeviceAlertEvents` Microsoft Defender For Endpoint 架構中的表格取得的相同警示資訊，請篩選 `AlertInfo` 該表， `ServiceSource` 然後使用資料表加入每個唯一的 ID `AlertEvidence` ，以提供詳細的事件及實體資訊。</span><span class="sxs-lookup"><span data-stu-id="8d030-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="8d030-202">請參閱下列範例查詢：</span><span class="sxs-lookup"><span data-stu-id="8d030-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="8d030-203">此查詢所產生的資料行數多於 `DeviceAlertEvents` Microsoft Defender For Endpoint 架構中的資料行數。</span><span class="sxs-lookup"><span data-stu-id="8d030-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="8d030-204">若要保持可管理的結果，請使用 `project` 僅取得您感興趣的欄。</span><span class="sxs-lookup"><span data-stu-id="8d030-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="8d030-205">在調查偵測到 PowerShell 活動時，可能會對下列專案欄感興趣的範例：</span><span class="sxs-lookup"><span data-stu-id="8d030-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="8d030-206">如果您想要針對警示中的特定實體進行篩選，您可以在中指定實體類型 `EntityType` 和要篩選的值來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="8d030-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="8d030-207">下列範例會尋找特定的 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="8d030-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="8d030-208">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8d030-208">See also</span></span>
- [<span data-ttu-id="8d030-209">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d030-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8d030-210">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="8d030-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8d030-211">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="8d030-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8d030-212">Microsoft Defender for Endpoint 中的高級搜尋</span><span class="sxs-lookup"><span data-stu-id="8d030-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)