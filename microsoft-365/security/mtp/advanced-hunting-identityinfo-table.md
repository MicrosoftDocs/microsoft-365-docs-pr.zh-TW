---
title: Advanced 搜尋架構中的 IdentityInfo 表格
description: 深入瞭解高級搜尋架構的 IdentityInfo 資料表中的使用者帳戶資訊
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，description，AccountInfo，IdentityInfo，account
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 94afa9e36ca75491511338297f02e8031333e53f
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412739"
---
# <a name="identityinfo"></a><span data-ttu-id="c9830-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="c9830-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c9830-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c9830-105">**Applies to:**</span></span>
- <span data-ttu-id="c9830-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="c9830-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c9830-107">[！附注] `IdentityInfo` [高級搜尋](advanced-hunting-overview.md) 架構中的表格包含從各種服務（包含 Azure Active Directory）取得之使用者帳戶的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c9830-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="c9830-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="c9830-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="c9830-109">此資料表已重新命名 `AccountInfo` 。</span><span class="sxs-lookup"><span data-stu-id="c9830-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="c9830-110">重新命名時，儲存在入口網站中的所有查詢都會自動更新。</span><span class="sxs-lookup"><span data-stu-id="c9830-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="c9830-111">檢查您已儲存在其他位置的查詢。</span><span class="sxs-lookup"><span data-stu-id="c9830-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="c9830-112">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="c9830-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c9830-113">欄名稱</span><span class="sxs-lookup"><span data-stu-id="c9830-113">Column name</span></span> | <span data-ttu-id="c9830-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="c9830-114">Data type</span></span> | <span data-ttu-id="c9830-115">描述</span><span class="sxs-lookup"><span data-stu-id="c9830-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="c9830-116">string</span><span class="sxs-lookup"><span data-stu-id="c9830-116">string</span></span> | <span data-ttu-id="c9830-117">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="c9830-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="c9830-118">string</span><span class="sxs-lookup"><span data-stu-id="c9830-118">string</span></span> | <span data-ttu-id="c9830-119">帳戶的使用者主要名稱 (UPN) </span><span class="sxs-lookup"><span data-stu-id="c9830-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="c9830-120">string</span><span class="sxs-lookup"><span data-stu-id="c9830-120">string</span></span> | <span data-ttu-id="c9830-121">內部部署安全性識別碼 (帳戶的 SID) </span><span class="sxs-lookup"><span data-stu-id="c9830-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="c9830-122">string</span><span class="sxs-lookup"><span data-stu-id="c9830-122">string</span></span> | <span data-ttu-id="c9830-123">帳戶的雲端安全性識別碼</span><span class="sxs-lookup"><span data-stu-id="c9830-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="c9830-124">string</span><span class="sxs-lookup"><span data-stu-id="c9830-124">string</span></span> | <span data-ttu-id="c9830-125">帳戶使用者的指定名稱或名字</span><span class="sxs-lookup"><span data-stu-id="c9830-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="c9830-126">string</span><span class="sxs-lookup"><span data-stu-id="c9830-126">string</span></span> | <span data-ttu-id="c9830-127">帳戶使用者的姓氏、系列名稱或姓氏</span><span class="sxs-lookup"><span data-stu-id="c9830-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c9830-128">string</span><span class="sxs-lookup"><span data-stu-id="c9830-128">string</span></span> | <span data-ttu-id="c9830-129">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="c9830-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c9830-130">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="c9830-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="c9830-131">string</span><span class="sxs-lookup"><span data-stu-id="c9830-131">string</span></span> | <span data-ttu-id="c9830-132">帳戶使用者所屬的部門名稱</span><span class="sxs-lookup"><span data-stu-id="c9830-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="c9830-133">string</span><span class="sxs-lookup"><span data-stu-id="c9830-133">string</span></span> | <span data-ttu-id="c9830-134">帳戶使用者的職稱</span><span class="sxs-lookup"><span data-stu-id="c9830-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="c9830-135">string</span><span class="sxs-lookup"><span data-stu-id="c9830-135">string</span></span> | <span data-ttu-id="c9830-136">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="c9830-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c9830-137">string</span><span class="sxs-lookup"><span data-stu-id="c9830-137">string</span></span> | <span data-ttu-id="c9830-138">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="c9830-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="c9830-139">string</span><span class="sxs-lookup"><span data-stu-id="c9830-139">string</span></span> | <span data-ttu-id="c9830-140">帳戶的 SMTP 位址</span><span class="sxs-lookup"><span data-stu-id="c9830-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="c9830-141">string</span><span class="sxs-lookup"><span data-stu-id="c9830-141">string</span></span> | <span data-ttu-id="c9830-142">Voice over IP (VOIP) 會話初始通訊協定 (SIP) 帳戶位址</span><span class="sxs-lookup"><span data-stu-id="c9830-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="c9830-143">string</span><span class="sxs-lookup"><span data-stu-id="c9830-143">string</span></span> | <span data-ttu-id="c9830-144">帳戶使用者所在的城市</span><span class="sxs-lookup"><span data-stu-id="c9830-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="c9830-145">string</span><span class="sxs-lookup"><span data-stu-id="c9830-145">string</span></span> | <span data-ttu-id="c9830-146">帳戶使用者所在的國家/地區</span><span class="sxs-lookup"><span data-stu-id="c9830-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="c9830-147">布林值</span><span class="sxs-lookup"><span data-stu-id="c9830-147">boolean</span></span> | <span data-ttu-id="c9830-148">指出帳戶是否已啟用</span><span class="sxs-lookup"><span data-stu-id="c9830-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c9830-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="c9830-149">Related topics</span></span>
- [<span data-ttu-id="c9830-150">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="c9830-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c9830-151">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="c9830-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c9830-152">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="c9830-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c9830-153">搜捕裝置、電子郵件、應用程式和身分識別</span><span class="sxs-lookup"><span data-stu-id="c9830-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c9830-154">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="c9830-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c9830-155">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="c9830-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
