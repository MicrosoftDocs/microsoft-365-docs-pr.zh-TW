---
title: 進位搜尋架構中的 IdentityDirectoryEvents 資料表
description: 瞭解進位搜尋架構之 IdentityDirectoryEvents 資料表中的網域控制站和 Active Directory 事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、欄、資料類型、描述、IdentityDirectoryEvents、網域控制站、Active Directory、Azure ATP、身分識別
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
ms.openlocfilehash: 95090b0f4abe0b0f0552c81495936f4f2261cf8e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929931"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="6b318-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="6b318-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6b318-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="6b318-105">**Applies to:**</span></span>
- <span data-ttu-id="6b318-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b318-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6b318-107">進 `IdentityDirectoryEvents` 位搜尋架構 [中的](advanced-hunting-overview.md) 資料表包含涉及涉及執行 Active Directory (AD 記錄之內部部署) 。</span><span class="sxs-lookup"><span data-stu-id="6b318-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="6b318-108">此表格會記錄各種身分識別相關事件，例如密碼變更、密碼到期，以及 UPN (使用者) 變更。</span><span class="sxs-lookup"><span data-stu-id="6b318-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="6b318-109">它也會記錄網域控制站上的系統事件，例如排程工作與 PowerShell 活動。</span><span class="sxs-lookup"><span data-stu-id="6b318-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="6b318-110">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="6b318-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6b318-111">有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參照。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="6b318-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="6b318-112">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="6b318-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6b318-113">欄名稱</span><span class="sxs-lookup"><span data-stu-id="6b318-113">Column name</span></span> | <span data-ttu-id="6b318-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="6b318-114">Data type</span></span> | <span data-ttu-id="6b318-115">描述</span><span class="sxs-lookup"><span data-stu-id="6b318-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6b318-116">datetime</span><span class="sxs-lookup"><span data-stu-id="6b318-116">datetime</span></span> | <span data-ttu-id="6b318-117">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="6b318-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6b318-118">string</span><span class="sxs-lookup"><span data-stu-id="6b318-118">string</span></span> | <span data-ttu-id="6b318-119">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="6b318-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="6b318-120">請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="6b318-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="6b318-121">string</span><span class="sxs-lookup"><span data-stu-id="6b318-121">string</span></span> | <span data-ttu-id="6b318-122">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="6b318-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="6b318-123">string</span><span class="sxs-lookup"><span data-stu-id="6b318-123">string</span></span> | <span data-ttu-id="6b318-124">已記錄 (之) 之帳戶的使用者主體名稱或 UPN 名稱</span><span class="sxs-lookup"><span data-stu-id="6b318-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="6b318-125">string</span><span class="sxs-lookup"><span data-stu-id="6b318-125">string</span></span> | <span data-ttu-id="6b318-126">顯示所記錄動作所適用于之帳戶的名稱</span><span class="sxs-lookup"><span data-stu-id="6b318-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="6b318-127">string</span><span class="sxs-lookup"><span data-stu-id="6b318-127">string</span></span> | <span data-ttu-id="6b318-128">所記錄動作 (裝置) FQDN 網域</span><span class="sxs-lookup"><span data-stu-id="6b318-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="6b318-129">string</span><span class="sxs-lookup"><span data-stu-id="6b318-129">string</span></span> | <span data-ttu-id="6b318-130">執行處理錄製動作之伺服器應用程式之裝置的名稱</span><span class="sxs-lookup"><span data-stu-id="6b318-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="6b318-131">string</span><span class="sxs-lookup"><span data-stu-id="6b318-131">string</span></span> | <span data-ttu-id="6b318-132">執行處理錄製動作之伺服器應用程式的裝置 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6b318-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="6b318-133">string</span><span class="sxs-lookup"><span data-stu-id="6b318-133">string</span></span> | <span data-ttu-id="6b318-134">活動的目的地埠</span><span class="sxs-lookup"><span data-stu-id="6b318-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="6b318-135">string</span><span class="sxs-lookup"><span data-stu-id="6b318-135">string</span></span> | <span data-ttu-id="6b318-136">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="6b318-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="6b318-137">string</span><span class="sxs-lookup"><span data-stu-id="6b318-137">string</span></span> | <span data-ttu-id="6b318-138">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="6b318-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6b318-139">string</span><span class="sxs-lookup"><span data-stu-id="6b318-139">string</span></span> | <span data-ttu-id="6b318-140">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="6b318-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6b318-141">string</span><span class="sxs-lookup"><span data-stu-id="6b318-141">string</span></span> | <span data-ttu-id="6b318-142">帳戶 (UPN) 使用者主體名稱</span><span class="sxs-lookup"><span data-stu-id="6b318-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="6b318-143">string</span><span class="sxs-lookup"><span data-stu-id="6b318-143">string</span></span> | <span data-ttu-id="6b318-144">帳戶 (安全性) SID 識別碼</span><span class="sxs-lookup"><span data-stu-id="6b318-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6b318-145">string</span><span class="sxs-lookup"><span data-stu-id="6b318-145">string</span></span> | <span data-ttu-id="6b318-146">Azure Active Directory 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6b318-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6b318-147">string</span><span class="sxs-lookup"><span data-stu-id="6b318-147">string</span></span> | <span data-ttu-id="6b318-148">顯示在通訊錄中的帳戶使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="6b318-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6b318-149">通常是指定或名字、中間名、姓氏或名字的組合。</span><span class="sxs-lookup"><span data-stu-id="6b318-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="6b318-150">string</span><span class="sxs-lookup"><span data-stu-id="6b318-150">string</span></span> | <span data-ttu-id="6b318-151">裝置 FQDN (完整) 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="6b318-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="6b318-152">string</span><span class="sxs-lookup"><span data-stu-id="6b318-152">string</span></span> | <span data-ttu-id="6b318-153">在通訊期間指派給裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6b318-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="6b318-154">string</span><span class="sxs-lookup"><span data-stu-id="6b318-154">string</span></span> | <span data-ttu-id="6b318-155">通訊期間使用的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="6b318-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="6b318-156">string</span><span class="sxs-lookup"><span data-stu-id="6b318-156">string</span></span> | <span data-ttu-id="6b318-157">與活動相關的城市、國家/地區或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="6b318-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="6b318-158">string</span><span class="sxs-lookup"><span data-stu-id="6b318-158">string</span></span> | <span data-ttu-id="6b318-159">與 IP 位址相關聯的網際網路服務提供者</span><span class="sxs-lookup"><span data-stu-id="6b318-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="6b318-160">long</span><span class="sxs-lookup"><span data-stu-id="6b318-160">long</span></span> | <span data-ttu-id="6b318-161">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6b318-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="6b318-162">string</span><span class="sxs-lookup"><span data-stu-id="6b318-162">string</span></span> | <span data-ttu-id="6b318-163">實體或事件的其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="6b318-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6b318-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="6b318-164">Related topics</span></span>
- [<span data-ttu-id="6b318-165">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="6b318-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6b318-166">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="6b318-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6b318-167">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="6b318-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6b318-168">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="6b318-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6b318-169">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="6b318-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6b318-170">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="6b318-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
