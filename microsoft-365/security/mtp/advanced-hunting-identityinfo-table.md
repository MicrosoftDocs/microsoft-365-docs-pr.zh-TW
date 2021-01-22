---
title: 進位搜尋架構中的 IdentityInfo 資料表
description: 瞭解進位搜尋架構之 IdentityInfo 資料表中的使用者帳戶資訊
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參考、kusto、表格、資料行、資料類型、描述、AccountInfo、IdentityInfo、account
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929907"
---
# <a name="identityinfo"></a><span data-ttu-id="18ed3-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="18ed3-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="18ed3-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="18ed3-105">**Applies to:**</span></span>
- <span data-ttu-id="18ed3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18ed3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="18ed3-107">進 `IdentityInfo` 位搜尋架構 [中的](advanced-hunting-overview.md) 表格包含從各種服務取得之使用者帳戶的資訊，包括 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="18ed3-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="18ed3-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="18ed3-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="18ed3-109">此資料表已 `AccountInfo` 重新命名。</span><span class="sxs-lookup"><span data-stu-id="18ed3-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="18ed3-110">重新命名期間，所有儲存于入口網站中的查詢都會自動更新。</span><span class="sxs-lookup"><span data-stu-id="18ed3-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="18ed3-111">檢查您儲存于其他位置的查詢。</span><span class="sxs-lookup"><span data-stu-id="18ed3-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="18ed3-112">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="18ed3-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="18ed3-113">欄名稱</span><span class="sxs-lookup"><span data-stu-id="18ed3-113">Column name</span></span> | <span data-ttu-id="18ed3-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="18ed3-114">Data type</span></span> | <span data-ttu-id="18ed3-115">描述</span><span class="sxs-lookup"><span data-stu-id="18ed3-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="18ed3-116">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-116">string</span></span> | <span data-ttu-id="18ed3-117">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="18ed3-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="18ed3-118">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-118">string</span></span> | <span data-ttu-id="18ed3-119">帳戶 (UPN) 使用者主體名稱</span><span class="sxs-lookup"><span data-stu-id="18ed3-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="18ed3-120">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-120">string</span></span> | <span data-ttu-id="18ed3-121">帳戶的 SID () 內部部署安全性識別碼</span><span class="sxs-lookup"><span data-stu-id="18ed3-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="18ed3-122">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-122">string</span></span> | <span data-ttu-id="18ed3-123">帳戶的雲端安全性識別碼</span><span class="sxs-lookup"><span data-stu-id="18ed3-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="18ed3-124">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-124">string</span></span> | <span data-ttu-id="18ed3-125">帳戶使用者的指定名稱或名字</span><span class="sxs-lookup"><span data-stu-id="18ed3-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="18ed3-126">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-126">string</span></span> | <span data-ttu-id="18ed3-127">帳戶使用者的姓氏、家人姓名或名字</span><span class="sxs-lookup"><span data-stu-id="18ed3-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="18ed3-128">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-128">string</span></span> | <span data-ttu-id="18ed3-129">顯示在通訊錄中的帳戶使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="18ed3-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="18ed3-130">通常是指定或名字、中間名、姓氏或名字的組合。</span><span class="sxs-lookup"><span data-stu-id="18ed3-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="18ed3-131">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-131">string</span></span> | <span data-ttu-id="18ed3-132">帳戶使用者所屬的部門名稱</span><span class="sxs-lookup"><span data-stu-id="18ed3-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="18ed3-133">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-133">string</span></span> | <span data-ttu-id="18ed3-134">帳戶使用者職稱</span><span class="sxs-lookup"><span data-stu-id="18ed3-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="18ed3-135">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-135">string</span></span> | <span data-ttu-id="18ed3-136">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="18ed3-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="18ed3-137">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-137">string</span></span> | <span data-ttu-id="18ed3-138">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="18ed3-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="18ed3-139">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-139">string</span></span> | <span data-ttu-id="18ed3-140">帳戶的 SMTP 位址</span><span class="sxs-lookup"><span data-stu-id="18ed3-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="18ed3-141">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-141">string</span></span> | <span data-ttu-id="18ed3-142">VOIP (VOIP) 會話初始通訊協定 (SIP) 位址</span><span class="sxs-lookup"><span data-stu-id="18ed3-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="18ed3-143">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-143">string</span></span> | <span data-ttu-id="18ed3-144">帳戶使用者所在的城市</span><span class="sxs-lookup"><span data-stu-id="18ed3-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="18ed3-145">string</span><span class="sxs-lookup"><span data-stu-id="18ed3-145">string</span></span> | <span data-ttu-id="18ed3-146">帳戶使用者所在的國家/地區</span><span class="sxs-lookup"><span data-stu-id="18ed3-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="18ed3-147">布林值</span><span class="sxs-lookup"><span data-stu-id="18ed3-147">boolean</span></span> | <span data-ttu-id="18ed3-148">指出帳戶是否已啟用</span><span class="sxs-lookup"><span data-stu-id="18ed3-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="18ed3-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="18ed3-149">Related topics</span></span>
- [<span data-ttu-id="18ed3-150">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="18ed3-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="18ed3-151">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="18ed3-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="18ed3-152">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="18ed3-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="18ed3-153">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="18ed3-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="18ed3-154">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="18ed3-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="18ed3-155">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="18ed3-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
