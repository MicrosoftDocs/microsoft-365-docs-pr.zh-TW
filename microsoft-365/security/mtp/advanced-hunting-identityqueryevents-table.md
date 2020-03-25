---
title: Advanced 搜尋架構中的 IdentityQueryEvents 表格
description: 深入瞭解高級搜尋架構的 IdentityQueryEvents 資料表中的 Active Directory 查詢事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，表格，欄，資料類型，描述，IdentityQueryEvents，Azure AD，Active Directory，AzureATP、identity、LDAP 查詢
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929110"
---
# <a name="identityqueryevents"></a><span data-ttu-id="c788b-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c788b-104">IdentityQueryEvents</span></span>

<span data-ttu-id="c788b-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c788b-105">**Applies to:**</span></span>
- <span data-ttu-id="c788b-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="c788b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c788b-107">[ `IdentityQueryEvents` ！附注][高級搜尋](advanced-hunting-overview.md)架構中的表格包含針對 Active Directory 物件（如使用者、群組、裝置和網域）所執行之查詢的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c788b-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="c788b-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="c788b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c788b-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="c788b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c788b-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="c788b-110">Column name</span></span> | <span data-ttu-id="c788b-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="c788b-111">Data type</span></span> | <span data-ttu-id="c788b-112">描述</span><span class="sxs-lookup"><span data-stu-id="c788b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c788b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c788b-113">datetime</span></span> | <span data-ttu-id="c788b-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="c788b-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="c788b-115">string</span><span class="sxs-lookup"><span data-stu-id="c788b-115">string</span></span> | <span data-ttu-id="c788b-116">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="c788b-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="c788b-117">string</span><span class="sxs-lookup"><span data-stu-id="c788b-117">string</span></span> | <span data-ttu-id="c788b-118">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="c788b-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="c788b-119">string</span><span class="sxs-lookup"><span data-stu-id="c788b-119">string</span></span> | <span data-ttu-id="c788b-120">查詢類型： QueryGroup、QueryUser 或 EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="c788b-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="c788b-121">string</span><span class="sxs-lookup"><span data-stu-id="c788b-121">string</span></span> | <span data-ttu-id="c788b-122">所查詢的使用者、群組、裝置、網域或任何其他實體類型的名稱</span><span class="sxs-lookup"><span data-stu-id="c788b-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="c788b-123">string</span><span class="sxs-lookup"><span data-stu-id="c788b-123">string</span></span> | <span data-ttu-id="c788b-124">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="c788b-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="c788b-125">string</span><span class="sxs-lookup"><span data-stu-id="c788b-125">string</span></span> | <span data-ttu-id="c788b-126">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="c788b-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c788b-127">string</span><span class="sxs-lookup"><span data-stu-id="c788b-127">string</span></span> | <span data-ttu-id="c788b-128">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="c788b-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="c788b-129">string</span><span class="sxs-lookup"><span data-stu-id="c788b-129">string</span></span> | <span data-ttu-id="c788b-130">帳戶的使用者主要名稱（UPN）</span><span class="sxs-lookup"><span data-stu-id="c788b-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c788b-131">string</span><span class="sxs-lookup"><span data-stu-id="c788b-131">string</span></span> | <span data-ttu-id="c788b-132">帳戶的安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="c788b-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c788b-133">string</span><span class="sxs-lookup"><span data-stu-id="c788b-133">string</span></span> | <span data-ttu-id="c788b-134">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c788b-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c788b-135">string</span><span class="sxs-lookup"><span data-stu-id="c788b-135">string</span></span> | <span data-ttu-id="c788b-136">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="c788b-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c788b-137">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="c788b-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="c788b-138">string</span><span class="sxs-lookup"><span data-stu-id="c788b-138">string</span></span> | <span data-ttu-id="c788b-139">端點的完整功能變數名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="c788b-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="c788b-140">string</span><span class="sxs-lookup"><span data-stu-id="c788b-140">string</span></span> | <span data-ttu-id="c788b-141">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="c788b-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="c788b-142">string</span><span class="sxs-lookup"><span data-stu-id="c788b-142">string</span></span> | <span data-ttu-id="c788b-143">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="c788b-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c788b-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="c788b-144">Related topics</span></span>
- [<span data-ttu-id="c788b-145">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="c788b-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c788b-146">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="c788b-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c788b-147">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="c788b-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c788b-148">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="c788b-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c788b-149">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="c788b-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c788b-150">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="c788b-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
