---
title: Advanced 搜尋架構中的 IdentityQueryEvents 表格
description: 深入瞭解高級搜尋架構的 IdentityQueryEvents 資料表中的 Active Directory 查詢事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityQueryEvents，Azure AD，Active Directory，Azure ATP，identity，LDAP 查詢
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
ms.openlocfilehash: bf1c57ee93c6f0e007c1b58e73fb9371799e75c6
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431120"
---
# <a name="identityqueryevents"></a><span data-ttu-id="c5782-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c5782-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c5782-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c5782-105">**Applies to:**</span></span>
- <span data-ttu-id="c5782-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="c5782-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c5782-107">[！附注] `IdentityQueryEvents` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含針對 Active Directory 物件（如使用者、群組、裝置和網域）所執行之查詢的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c5782-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="c5782-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="c5782-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="c5782-109">如需有關資料表所支援之事件種類 () 值的詳細資訊 `ActionType` ，請使用安全性中心內的 [內建架構參照](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="c5782-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="c5782-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="c5782-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c5782-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="c5782-111">Column name</span></span> | <span data-ttu-id="c5782-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="c5782-112">Data type</span></span> | <span data-ttu-id="c5782-113">描述</span><span class="sxs-lookup"><span data-stu-id="c5782-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c5782-114">datetime</span><span class="sxs-lookup"><span data-stu-id="c5782-114">datetime</span></span> | <span data-ttu-id="c5782-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="c5782-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="c5782-116">string</span><span class="sxs-lookup"><span data-stu-id="c5782-116">string</span></span> | <span data-ttu-id="c5782-117">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="c5782-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="c5782-118">如需詳細資訊，請參閱[入口網站內架構參考](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="c5782-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="c5782-119">string</span><span class="sxs-lookup"><span data-stu-id="c5782-119">string</span></span> | <span data-ttu-id="c5782-120">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="c5782-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="c5782-121">string</span><span class="sxs-lookup"><span data-stu-id="c5782-121">string</span></span> | <span data-ttu-id="c5782-122">查詢類型，例如 QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="c5782-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="c5782-123">string</span><span class="sxs-lookup"><span data-stu-id="c5782-123">string</span></span> | <span data-ttu-id="c5782-124">所查詢的使用者、群組、裝置、網域或任何其他實體類型的名稱</span><span class="sxs-lookup"><span data-stu-id="c5782-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="c5782-125">string</span><span class="sxs-lookup"><span data-stu-id="c5782-125">string</span></span> | <span data-ttu-id="c5782-126">用來執行查詢的字串</span><span class="sxs-lookup"><span data-stu-id="c5782-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="c5782-127">string</span><span class="sxs-lookup"><span data-stu-id="c5782-127">string</span></span> | <span data-ttu-id="c5782-128">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="c5782-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="c5782-129">string</span><span class="sxs-lookup"><span data-stu-id="c5782-129">string</span></span> | <span data-ttu-id="c5782-130">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="c5782-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c5782-131">string</span><span class="sxs-lookup"><span data-stu-id="c5782-131">string</span></span> | <span data-ttu-id="c5782-132">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="c5782-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="c5782-133">string</span><span class="sxs-lookup"><span data-stu-id="c5782-133">string</span></span> | <span data-ttu-id="c5782-134">帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="c5782-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c5782-135">string</span><span class="sxs-lookup"><span data-stu-id="c5782-135">string</span></span> | <span data-ttu-id="c5782-136">帳戶的安全性識別碼 (SID) </span><span class="sxs-lookup"><span data-stu-id="c5782-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c5782-137">string</span><span class="sxs-lookup"><span data-stu-id="c5782-137">string</span></span> | <span data-ttu-id="c5782-138">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c5782-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c5782-139">string</span><span class="sxs-lookup"><span data-stu-id="c5782-139">string</span></span> | <span data-ttu-id="c5782-140">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="c5782-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c5782-141">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="c5782-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="c5782-142">string</span><span class="sxs-lookup"><span data-stu-id="c5782-142">string</span></span> | <span data-ttu-id="c5782-143">端點 (FQDN) 的完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="c5782-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="c5782-144">string</span><span class="sxs-lookup"><span data-stu-id="c5782-144">string</span></span> | <span data-ttu-id="c5782-145">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="c5782-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="c5782-146">string</span><span class="sxs-lookup"><span data-stu-id="c5782-146">string</span></span> | <span data-ttu-id="c5782-147">執行伺服器應用程式（處理錄製的動作）的裝置名稱</span><span class="sxs-lookup"><span data-stu-id="c5782-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="c5782-148">string</span><span class="sxs-lookup"><span data-stu-id="c5782-148">string</span></span> | <span data-ttu-id="c5782-149">執行伺服器應用程式（處理錄製的動作）的裝置的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="c5782-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="c5782-150">string</span><span class="sxs-lookup"><span data-stu-id="c5782-150">string</span></span> | <span data-ttu-id="c5782-151">套用錄製動作之裝置的完整功能變數名稱 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="c5782-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="c5782-152">string</span><span class="sxs-lookup"><span data-stu-id="c5782-152">string</span></span> | <span data-ttu-id="c5782-153">套用錄製動作之帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="c5782-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="c5782-154">string</span><span class="sxs-lookup"><span data-stu-id="c5782-154">string</span></span> | <span data-ttu-id="c5782-155">套用錄製的動作所套用之帳戶的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="c5782-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="c5782-156">string</span><span class="sxs-lookup"><span data-stu-id="c5782-156">string</span></span> | <span data-ttu-id="c5782-157">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="c5782-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="c5782-158">long</span><span class="sxs-lookup"><span data-stu-id="c5782-158">long</span></span> | <span data-ttu-id="c5782-159">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c5782-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="c5782-160">string</span><span class="sxs-lookup"><span data-stu-id="c5782-160">string</span></span> | <span data-ttu-id="c5782-161">實體或事件的其他資訊</span><span class="sxs-lookup"><span data-stu-id="c5782-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c5782-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="c5782-162">Related topics</span></span>
- [<span data-ttu-id="c5782-163">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="c5782-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c5782-164">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="c5782-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c5782-165">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="c5782-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c5782-166">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="c5782-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c5782-167">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="c5782-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c5782-168">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="c5782-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
