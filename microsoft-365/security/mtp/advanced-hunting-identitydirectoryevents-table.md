---
title: Advanced 搜尋架構中的 IdentityDirectoryEvents 表格
description: 深入瞭解高級搜尋架構的 IdentityDirectoryEvents 資料表中的網域控制站和 Active Directory 事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityDirectoryEvents，網域控制站，Active Directory，Azure ATP，身分識別
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1a65a8e78dfa09bc0a417669a1efd35320e261da
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798778"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="f056f-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="f056f-104">IdentityDirectoryEvents</span></span>

<span data-ttu-id="f056f-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f056f-105">**Applies to:**</span></span>
- <span data-ttu-id="f056f-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="f056f-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f056f-107">`IdentityDirectoryEvents` [Advanced 搜尋](advanced-hunting-overview.md)架構中的表格包含的事件包括內部部署網域控制站執行 ACTIVE Directory (AD) 。</span><span class="sxs-lookup"><span data-stu-id="f056f-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f056f-108">此表格會捕獲各種身分識別相關的事件，例如密碼變更、密碼到期和使用者主要名稱 (UPN) 變更。</span><span class="sxs-lookup"><span data-stu-id="f056f-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="f056f-109">它也會在網域控制站上捕獲系統事件，例如排程任務和 PowerShell 活動。</span><span class="sxs-lookup"><span data-stu-id="f056f-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="f056f-110">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="f056f-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="f056f-111">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="f056f-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="f056f-112">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="f056f-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f056f-113">欄名稱</span><span class="sxs-lookup"><span data-stu-id="f056f-113">Column name</span></span> | <span data-ttu-id="f056f-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="f056f-114">Data type</span></span> | <span data-ttu-id="f056f-115">描述</span><span class="sxs-lookup"><span data-stu-id="f056f-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f056f-116">datetime</span><span class="sxs-lookup"><span data-stu-id="f056f-116">datetime</span></span> | <span data-ttu-id="f056f-117">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="f056f-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f056f-118">string</span><span class="sxs-lookup"><span data-stu-id="f056f-118">string</span></span> | <span data-ttu-id="f056f-119">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="f056f-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="f056f-120">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="f056f-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="f056f-121">string</span><span class="sxs-lookup"><span data-stu-id="f056f-121">string</span></span> | <span data-ttu-id="f056f-122">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="f056f-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="f056f-123">string</span><span class="sxs-lookup"><span data-stu-id="f056f-123">string</span></span> | <span data-ttu-id="f056f-124">套用錄製動作之帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="f056f-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="f056f-125">string</span><span class="sxs-lookup"><span data-stu-id="f056f-125">string</span></span> | <span data-ttu-id="f056f-126">套用錄製的動作所套用之帳戶的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="f056f-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="f056f-127">string</span><span class="sxs-lookup"><span data-stu-id="f056f-127">string</span></span> | <span data-ttu-id="f056f-128">套用錄製動作之裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="f056f-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="f056f-129">string</span><span class="sxs-lookup"><span data-stu-id="f056f-129">string</span></span> | <span data-ttu-id="f056f-130">執行伺服器應用程式（處理錄製的動作）的裝置名稱</span><span class="sxs-lookup"><span data-stu-id="f056f-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f056f-131">string</span><span class="sxs-lookup"><span data-stu-id="f056f-131">string</span></span> | <span data-ttu-id="f056f-132">執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f056f-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="f056f-133">string</span><span class="sxs-lookup"><span data-stu-id="f056f-133">string</span></span> | <span data-ttu-id="f056f-134">活動的目的地埠</span><span class="sxs-lookup"><span data-stu-id="f056f-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="f056f-135">string</span><span class="sxs-lookup"><span data-stu-id="f056f-135">string</span></span> | <span data-ttu-id="f056f-136">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="f056f-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="f056f-137">string</span><span class="sxs-lookup"><span data-stu-id="f056f-137">string</span></span> | <span data-ttu-id="f056f-138">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="f056f-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f056f-139">string</span><span class="sxs-lookup"><span data-stu-id="f056f-139">string</span></span> | <span data-ttu-id="f056f-140">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="f056f-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f056f-141">string</span><span class="sxs-lookup"><span data-stu-id="f056f-141">string</span></span> | <span data-ttu-id="f056f-142">帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="f056f-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f056f-143">string</span><span class="sxs-lookup"><span data-stu-id="f056f-143">string</span></span> | <span data-ttu-id="f056f-144">帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="f056f-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f056f-145">string</span><span class="sxs-lookup"><span data-stu-id="f056f-145">string</span></span> | <span data-ttu-id="f056f-146">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f056f-146">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f056f-147">string</span><span class="sxs-lookup"><span data-stu-id="f056f-147">string</span></span> | <span data-ttu-id="f056f-148">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="f056f-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f056f-149">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="f056f-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f056f-150">string</span><span class="sxs-lookup"><span data-stu-id="f056f-150">string</span></span> | <span data-ttu-id="f056f-151">裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="f056f-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="f056f-152">string</span><span class="sxs-lookup"><span data-stu-id="f056f-152">string</span></span> | <span data-ttu-id="f056f-153">通訊期間指派給裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f056f-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="f056f-154">string</span><span class="sxs-lookup"><span data-stu-id="f056f-154">string</span></span> | <span data-ttu-id="f056f-155">通訊期間使用的 TCP 埠</span><span class="sxs-lookup"><span data-stu-id="f056f-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="f056f-156">string</span><span class="sxs-lookup"><span data-stu-id="f056f-156">string</span></span> | <span data-ttu-id="f056f-157">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="f056f-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="f056f-158">string</span><span class="sxs-lookup"><span data-stu-id="f056f-158">string</span></span> | <span data-ttu-id="f056f-159">與 IP 位址相關聯的網際網路服務提供者</span><span class="sxs-lookup"><span data-stu-id="f056f-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="f056f-160">long</span><span class="sxs-lookup"><span data-stu-id="f056f-160">long</span></span> | <span data-ttu-id="f056f-161">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="f056f-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f056f-162">string</span><span class="sxs-lookup"><span data-stu-id="f056f-162">string</span></span> | <span data-ttu-id="f056f-163">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="f056f-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f056f-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="f056f-164">Related topics</span></span>
- [<span data-ttu-id="f056f-165">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="f056f-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f056f-166">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="f056f-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f056f-167">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="f056f-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f056f-168">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="f056f-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f056f-169">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="f056f-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f056f-170">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="f056f-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
