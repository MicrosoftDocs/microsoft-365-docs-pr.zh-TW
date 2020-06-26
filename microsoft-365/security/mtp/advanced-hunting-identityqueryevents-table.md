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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899110"
---
# <a name="identityqueryevents"></a><span data-ttu-id="56b27-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="56b27-104">IdentityQueryEvents</span></span>

<span data-ttu-id="56b27-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="56b27-105">**Applies to:**</span></span>
- <span data-ttu-id="56b27-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="56b27-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="56b27-107">[！附注] `IdentityQueryEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含針對 Active Directory 物件（如使用者、群組、裝置和網域）所執行之查詢的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="56b27-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="56b27-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="56b27-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="56b27-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="56b27-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="56b27-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="56b27-110">Column name</span></span> | <span data-ttu-id="56b27-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="56b27-111">Data type</span></span> | <span data-ttu-id="56b27-112">描述</span><span class="sxs-lookup"><span data-stu-id="56b27-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="56b27-113">datetime</span><span class="sxs-lookup"><span data-stu-id="56b27-113">datetime</span></span> | <span data-ttu-id="56b27-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="56b27-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="56b27-115">string</span><span class="sxs-lookup"><span data-stu-id="56b27-115">string</span></span> | <span data-ttu-id="56b27-116">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="56b27-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="56b27-117">string</span><span class="sxs-lookup"><span data-stu-id="56b27-117">string</span></span> | <span data-ttu-id="56b27-118">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="56b27-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="56b27-119">string</span><span class="sxs-lookup"><span data-stu-id="56b27-119">string</span></span> | <span data-ttu-id="56b27-120">查詢類型： QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="56b27-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="56b27-121">string</span><span class="sxs-lookup"><span data-stu-id="56b27-121">string</span></span> | <span data-ttu-id="56b27-122">所查詢的使用者、群組、裝置、網域或任何其他實體類型的名稱</span><span class="sxs-lookup"><span data-stu-id="56b27-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="56b27-123">string</span><span class="sxs-lookup"><span data-stu-id="56b27-123">string</span></span> | <span data-ttu-id="56b27-124">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="56b27-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="56b27-125">string</span><span class="sxs-lookup"><span data-stu-id="56b27-125">string</span></span> | <span data-ttu-id="56b27-126">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="56b27-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="56b27-127">string</span><span class="sxs-lookup"><span data-stu-id="56b27-127">string</span></span> | <span data-ttu-id="56b27-128">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="56b27-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="56b27-129">string</span><span class="sxs-lookup"><span data-stu-id="56b27-129">string</span></span> | <span data-ttu-id="56b27-130">帳戶的使用者主要名稱（UPN）</span><span class="sxs-lookup"><span data-stu-id="56b27-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="56b27-131">string</span><span class="sxs-lookup"><span data-stu-id="56b27-131">string</span></span> | <span data-ttu-id="56b27-132">帳戶的安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="56b27-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="56b27-133">string</span><span class="sxs-lookup"><span data-stu-id="56b27-133">string</span></span> | <span data-ttu-id="56b27-134">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="56b27-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="56b27-135">string</span><span class="sxs-lookup"><span data-stu-id="56b27-135">string</span></span> | <span data-ttu-id="56b27-136">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="56b27-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="56b27-137">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="56b27-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="56b27-138">string</span><span class="sxs-lookup"><span data-stu-id="56b27-138">string</span></span> | <span data-ttu-id="56b27-139">端點的完整功能變數名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="56b27-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="56b27-140">string</span><span class="sxs-lookup"><span data-stu-id="56b27-140">string</span></span> | <span data-ttu-id="56b27-141">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="56b27-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="56b27-142">string</span><span class="sxs-lookup"><span data-stu-id="56b27-142">string</span></span> | <span data-ttu-id="56b27-143">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="56b27-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="56b27-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="56b27-144">Related topics</span></span>
- [<span data-ttu-id="56b27-145">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="56b27-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="56b27-146">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="56b27-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="56b27-147">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="56b27-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="56b27-148">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="56b27-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="56b27-149">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="56b27-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="56b27-150">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="56b27-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
