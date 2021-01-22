---
title: 進位搜尋架構中的 IdentityQueryEvents 資料表
description: 瞭解進位搜尋架構之 IdentityQueryEvents 資料表中的 Active Directory 查詢事件
keywords: 進一步搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、IdentityQueryEvents、Azure AD、Active Directory、Azure ATP、identities、LDAP 查詢
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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929811"
---
# <a name="identityqueryevents"></a><span data-ttu-id="d4fa7-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="d4fa7-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4fa7-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="d4fa7-105">**Applies to:**</span></span>
- <span data-ttu-id="d4fa7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4fa7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d4fa7-107">進位搜尋架構中的表格包含對 Active Directory 物件執行查詢的資訊，例如使用者、群組、裝置 `IdentityQueryEvents` 和網域。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4fa7-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="d4fa7-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="d4fa7-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="d4fa7-109">有關事件種類及資料 (資料) 值的詳細資訊，請使用安全性中心內建的架構 `ActionType` 參考。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="d4fa7-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="d4fa7-110">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="d4fa7-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d4fa7-111">欄名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-111">Column name</span></span> | <span data-ttu-id="d4fa7-112">資料類型</span><span class="sxs-lookup"><span data-stu-id="d4fa7-112">Data type</span></span> | <span data-ttu-id="d4fa7-113">描述</span><span class="sxs-lookup"><span data-stu-id="d4fa7-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d4fa7-114">datetime</span><span class="sxs-lookup"><span data-stu-id="d4fa7-114">datetime</span></span> | <span data-ttu-id="d4fa7-115">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="d4fa7-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="d4fa7-116">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-116">string</span></span> | <span data-ttu-id="d4fa7-117">觸發事件的活動類型。</span><span class="sxs-lookup"><span data-stu-id="d4fa7-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="d4fa7-118">請參閱入口 [網站內架構參考以](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 進一步查看詳細資料</span><span class="sxs-lookup"><span data-stu-id="d4fa7-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="d4fa7-119">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-119">string</span></span> | <span data-ttu-id="d4fa7-120">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="d4fa7-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="d4fa7-121">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-121">string</span></span> | <span data-ttu-id="d4fa7-122">查詢類型，例如查詢組、查詢使用者或列舉使用者</span><span class="sxs-lookup"><span data-stu-id="d4fa7-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="d4fa7-123">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-123">string</span></span> | <span data-ttu-id="d4fa7-124">被查詢之使用者、群組、裝置、網域或其他實體類型的名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="d4fa7-125">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-125">string</span></span> | <span data-ttu-id="d4fa7-126">用來執行查詢的字串</span><span class="sxs-lookup"><span data-stu-id="d4fa7-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="d4fa7-127">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-127">string</span></span> | <span data-ttu-id="d4fa7-128">通訊期間使用的通訊協定</span><span class="sxs-lookup"><span data-stu-id="d4fa7-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="d4fa7-129">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-129">string</span></span> | <span data-ttu-id="d4fa7-130">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="d4fa7-131">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-131">string</span></span> | <span data-ttu-id="d4fa7-132">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="d4fa7-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="d4fa7-133">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-133">string</span></span> | <span data-ttu-id="d4fa7-134">帳戶 (UPN) 使用者主體名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="d4fa7-135">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-135">string</span></span> | <span data-ttu-id="d4fa7-136">帳戶 (安全性) SID 識別碼</span><span class="sxs-lookup"><span data-stu-id="d4fa7-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="d4fa7-137">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-137">string</span></span> | <span data-ttu-id="d4fa7-138">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="d4fa7-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="d4fa7-139">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-139">string</span></span> | <span data-ttu-id="d4fa7-140">顯示在通訊錄中的帳戶使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="d4fa7-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="d4fa7-141">通常是指定或名字、中間名、姓氏或名字的組合。</span><span class="sxs-lookup"><span data-stu-id="d4fa7-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="d4fa7-142">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-142">string</span></span> | <span data-ttu-id="d4fa7-143">端點之 FQDN () 完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="d4fa7-144">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-144">string</span></span> | <span data-ttu-id="d4fa7-145">指派給端點的 IP 位址，用於相關網路通訊期間</span><span class="sxs-lookup"><span data-stu-id="d4fa7-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="d4fa7-146">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-146">string</span></span> | <span data-ttu-id="d4fa7-147">執行處理錄製動作之伺服器應用程式之裝置的名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="d4fa7-148">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-148">string</span></span> | <span data-ttu-id="d4fa7-149">執行處理錄製動作之伺服器應用程式的裝置 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d4fa7-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="d4fa7-150">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-150">string</span></span> | <span data-ttu-id="d4fa7-151">所記錄動作 (裝置) FQDN 網域</span><span class="sxs-lookup"><span data-stu-id="d4fa7-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="d4fa7-152">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-152">string</span></span> | <span data-ttu-id="d4fa7-153">已記錄 (之) 之帳戶的使用者主體名稱或 UPN 名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="d4fa7-154">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-154">string</span></span> | <span data-ttu-id="d4fa7-155">顯示所記錄動作所適用于之帳戶的名稱</span><span class="sxs-lookup"><span data-stu-id="d4fa7-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="d4fa7-156">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-156">string</span></span> | <span data-ttu-id="d4fa7-157">與活動相關的城市、國家/地區或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="d4fa7-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="d4fa7-158">long</span><span class="sxs-lookup"><span data-stu-id="d4fa7-158">long</span></span> | <span data-ttu-id="d4fa7-159">事件的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="d4fa7-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="d4fa7-160">string</span><span class="sxs-lookup"><span data-stu-id="d4fa7-160">string</span></span> | <span data-ttu-id="d4fa7-161">實體或事件的其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="d4fa7-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d4fa7-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4fa7-162">Related topics</span></span>
- [<span data-ttu-id="d4fa7-163">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="d4fa7-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d4fa7-164">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="d4fa7-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d4fa7-165">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="d4fa7-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d4fa7-166">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="d4fa7-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d4fa7-167">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="d4fa7-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d4fa7-168">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="d4fa7-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
