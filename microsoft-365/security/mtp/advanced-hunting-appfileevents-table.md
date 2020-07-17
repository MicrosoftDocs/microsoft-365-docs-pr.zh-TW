---
title: Advanced 搜尋架構中的 AppFileEvents 表格
description: 深入瞭解在高級搜尋架構的 AppFileEvents 資料表中，與雲端 app 和服務相關聯的檔案相關事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，搜尋，查詢，遙測，架構參考，kusto，table，欄，資料類型，描述，AppFileEvents，Cloud App Security，MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899336"
---
# <a name="appfileevents"></a><span data-ttu-id="6b7c0-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="6b7c0-104">AppFileEvents</span></span>

<span data-ttu-id="6b7c0-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6b7c0-105">**Applies to:**</span></span>
- <span data-ttu-id="6b7c0-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="6b7c0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6b7c0-107">[！附注] `AppFileEvents` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含雲端 app 和服務中由 Microsoft cloud App Security 監控之檔案相關活動的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6b7c0-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="6b7c0-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="6b7c0-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6b7c0-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="6b7c0-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6b7c0-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="6b7c0-110">Column name</span></span> | <span data-ttu-id="6b7c0-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="6b7c0-111">Data type</span></span> | <span data-ttu-id="6b7c0-112">描述</span><span class="sxs-lookup"><span data-stu-id="6b7c0-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6b7c0-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6b7c0-113">datetime</span></span> | <span data-ttu-id="6b7c0-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="6b7c0-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6b7c0-115">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-115">string</span></span> | <span data-ttu-id="6b7c0-116">觸發事件的活動類型</span><span class="sxs-lookup"><span data-stu-id="6b7c0-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="6b7c0-117">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-117">string</span></span> | <span data-ttu-id="6b7c0-118">執行錄製動作的應用程式</span><span class="sxs-lookup"><span data-stu-id="6b7c0-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="6b7c0-119">字串</span><span class="sxs-lookup"><span data-stu-id="6b7c0-119">string</span></span> | <span data-ttu-id="6b7c0-120">記錄動作已套用的檔案名稱</span><span class="sxs-lookup"><span data-stu-id="6b7c0-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6b7c0-121">字串</span><span class="sxs-lookup"><span data-stu-id="6b7c0-121">string</span></span> | <span data-ttu-id="6b7c0-122">包含錄製的動作所套用之檔案的資料夾</span><span class="sxs-lookup"><span data-stu-id="6b7c0-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="6b7c0-123">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-123">string</span></span> | <span data-ttu-id="6b7c0-124">重新命名為動作結果之檔案的原始名稱</span><span class="sxs-lookup"><span data-stu-id="6b7c0-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="6b7c0-125">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-125">string</span></span> | <span data-ttu-id="6b7c0-126">帳戶的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="6b7c0-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6b7c0-127">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-127">string</span></span> | <span data-ttu-id="6b7c0-128">帳戶的網域</span><span class="sxs-lookup"><span data-stu-id="6b7c0-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6b7c0-129">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-129">string</span></span> | <span data-ttu-id="6b7c0-130">帳戶的使用者主要名稱（UPN）</span><span class="sxs-lookup"><span data-stu-id="6b7c0-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6b7c0-131">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-131">string</span></span> | <span data-ttu-id="6b7c0-132">Azure AD 中帳戶的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="6b7c0-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6b7c0-133">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-133">string</span></span> | <span data-ttu-id="6b7c0-134">顯示在通訊錄中之帳戶使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="6b7c0-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6b7c0-135">通常是指定的名稱或名字、中間初始名稱或姓氏的組合。</span><span class="sxs-lookup"><span data-stu-id="6b7c0-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="6b7c0-136">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-136">string</span></span> | <span data-ttu-id="6b7c0-137">指派給端點的 IP 位址，並在相關的網路通訊期間使用</span><span class="sxs-lookup"><span data-stu-id="6b7c0-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="6b7c0-138">string</span><span class="sxs-lookup"><span data-stu-id="6b7c0-138">string</span></span> | <span data-ttu-id="6b7c0-139">與事件關聯的城市、國家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="6b7c0-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6b7c0-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="6b7c0-140">Related topics</span></span>
- [<span data-ttu-id="6b7c0-141">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="6b7c0-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6b7c0-142">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="6b7c0-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6b7c0-143">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="6b7c0-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6b7c0-144">搜捕所有裝置和電子郵件的威脅</span><span class="sxs-lookup"><span data-stu-id="6b7c0-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6b7c0-145">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="6b7c0-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6b7c0-146">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="6b7c0-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
