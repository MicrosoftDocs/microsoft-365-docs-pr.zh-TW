---
title: Advanced 搜尋架構中的 AccountInfo 表格
description: 深入瞭解高級搜尋架構的 AccountInfo 資料表中的使用者帳戶資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，資料表，欄，資料類型，描述，AlertInfo，警示，實體，證據，檔案，IP 位址裝置、電腦、使用者、帳戶
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929525"
---
# <a name="accountinfo"></a><span data-ttu-id="3b9ba-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="3b9ba-104">AccountInfo</span></span>

<span data-ttu-id="3b9ba-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3b9ba-105">**Applies to:**</span></span>
- <span data-ttu-id="3b9ba-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="3b9ba-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3b9ba-107">[ `AccountInfo` ！附注][高級搜尋](advanced-hunting-overview.md)架構中的表格包含從各種服務（包含 Azure Active Directory）取得之使用者帳戶的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3b9ba-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="3b9ba-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="3b9ba-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="3b9ba-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3b9ba-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3b9ba-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="3b9ba-110">Column name</span></span> | <span data-ttu-id="3b9ba-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="3b9ba-111">Data type</span></span> | <span data-ttu-id="3b9ba-112">描述</span><span class="sxs-lookup"><span data-stu-id="3b9ba-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="3b9ba-113">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-113">string</span></span> | <span data-ttu-id="3b9ba-114">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="3b9ba-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="3b9ba-115">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-115">string</span></span> | <span data-ttu-id="3b9ba-116">帳戶的使用者主要名稱（UPN）</span><span class="sxs-lookup"><span data-stu-id="3b9ba-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="3b9ba-117">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-117">string</span></span> | <span data-ttu-id="3b9ba-118">帳戶的內部部署安全性識別碼（SID）</span><span class="sxs-lookup"><span data-stu-id="3b9ba-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="3b9ba-119">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-119">string</span></span> | <span data-ttu-id="3b9ba-120">帳戶的雲端安全性識別碼</span><span class="sxs-lookup"><span data-stu-id="3b9ba-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="3b9ba-121">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-121">string</span></span> | <span data-ttu-id="3b9ba-122">帳戶使用者的指定名稱或名字</span><span class="sxs-lookup"><span data-stu-id="3b9ba-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="3b9ba-123">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-123">string</span></span> | <span data-ttu-id="3b9ba-124">帳戶使用者的姓氏、系列名稱或姓氏</span><span class="sxs-lookup"><span data-stu-id="3b9ba-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3b9ba-125">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-125">string</span></span> | <span data-ttu-id="3b9ba-126">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="3b9ba-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3b9ba-127">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="3b9ba-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="3b9ba-128">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-128">string</span></span> | <span data-ttu-id="3b9ba-129">帳戶使用者所屬的部門名稱</span><span class="sxs-lookup"><span data-stu-id="3b9ba-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="3b9ba-130">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-130">string</span></span> | <span data-ttu-id="3b9ba-131">帳戶使用者的職稱</span><span class="sxs-lookup"><span data-stu-id="3b9ba-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="3b9ba-132">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-132">string</span></span> | <span data-ttu-id="3b9ba-133">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="3b9ba-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="3b9ba-134">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-134">string</span></span> | <span data-ttu-id="3b9ba-135">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="3b9ba-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="3b9ba-136">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-136">string</span></span> | <span data-ttu-id="3b9ba-137">帳戶的 SMTP 位址</span><span class="sxs-lookup"><span data-stu-id="3b9ba-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="3b9ba-138">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-138">string</span></span> | <span data-ttu-id="3b9ba-139">客戶的 over IP （VOIP）會話初始通訊協定（SIP）位址的語音</span><span class="sxs-lookup"><span data-stu-id="3b9ba-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="3b9ba-140">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-140">string</span></span> | <span data-ttu-id="3b9ba-141">帳戶使用者所在的城市</span><span class="sxs-lookup"><span data-stu-id="3b9ba-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="3b9ba-142">string</span><span class="sxs-lookup"><span data-stu-id="3b9ba-142">string</span></span> | <span data-ttu-id="3b9ba-143">帳戶使用者所在的國家/地區</span><span class="sxs-lookup"><span data-stu-id="3b9ba-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="3b9ba-144">布林值</span><span class="sxs-lookup"><span data-stu-id="3b9ba-144">boolean</span></span> | <span data-ttu-id="3b9ba-145">指出帳戶是否已啟用</span><span class="sxs-lookup"><span data-stu-id="3b9ba-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3b9ba-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="3b9ba-146">Related topics</span></span>
- [<span data-ttu-id="3b9ba-147">主動威脅搜捕</span><span class="sxs-lookup"><span data-stu-id="3b9ba-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3b9ba-148">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="3b9ba-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3b9ba-149">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="3b9ba-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3b9ba-150">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="3b9ba-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3b9ba-151">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="3b9ba-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3b9ba-152">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="3b9ba-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
