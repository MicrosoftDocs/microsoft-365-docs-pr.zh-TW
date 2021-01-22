---
title: 進位搜尋架構中的 AlertInfo 表格
description: 瞭解進一代搜尋架構之 AlertInfo 資料表中的警示產生事件
keywords: 進層搜尋、威脅搜尋、網路威脅搜尋、Microsoft 威脅防護、microsoft 365、mtp、m365、搜尋、查詢、遙測、架構參照、kusto、表格、欄、資料類型、描述、警示、嚴重性、類別、MITRE、ATT&CK、Microsoft Defender ATP、MDATP、Office 365 ATP、Microsoft Cloud App Security、MCAS 和 Azure ATP
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
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929967"
---
# <a name="alertinfo"></a><span data-ttu-id="b2a2a-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="b2a2a-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2a2a-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="b2a2a-105">**Applies to:**</span></span>
- <span data-ttu-id="b2a2a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2a2a-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b2a2a-107">進位搜尋架構中的表格包含來自 `AlertInfo` Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 之警示的資訊。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b2a2a-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="b2a2a-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="b2a2a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b2a2a-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="b2a2a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b2a2a-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="b2a2a-110">Column name</span></span> | <span data-ttu-id="b2a2a-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="b2a2a-111">Data type</span></span> | <span data-ttu-id="b2a2a-112">描述</span><span class="sxs-lookup"><span data-stu-id="b2a2a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b2a2a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="b2a2a-113">datetime</span></span> | <span data-ttu-id="b2a2a-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="b2a2a-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="b2a2a-115">字串</span><span class="sxs-lookup"><span data-stu-id="b2a2a-115">string</span></span> | <span data-ttu-id="b2a2a-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="b2a2a-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="b2a2a-117">字串</span><span class="sxs-lookup"><span data-stu-id="b2a2a-117">string</span></span> | <span data-ttu-id="b2a2a-118">警示標題</span><span class="sxs-lookup"><span data-stu-id="b2a2a-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="b2a2a-119">字串</span><span class="sxs-lookup"><span data-stu-id="b2a2a-119">string</span></span> | <span data-ttu-id="b2a2a-120">輸入由警示所識別的威脅指示器或入侵活動類型</span><span class="sxs-lookup"><span data-stu-id="b2a2a-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="b2a2a-121">字串</span><span class="sxs-lookup"><span data-stu-id="b2a2a-121">string</span></span> | <span data-ttu-id="b2a2a-122">表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低)</span><span class="sxs-lookup"><span data-stu-id="b2a2a-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="b2a2a-123">字串</span><span class="sxs-lookup"><span data-stu-id="b2a2a-123">string</span></span> | <span data-ttu-id="b2a2a-124">提供警示資訊的產品或服務</span><span class="sxs-lookup"><span data-stu-id="b2a2a-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="b2a2a-125">string</span><span class="sxs-lookup"><span data-stu-id="b2a2a-125">string</span></span> | <span data-ttu-id="b2a2a-126">偵測技術或感應器會識別值得注意的元件或活動</span><span class="sxs-lookup"><span data-stu-id="b2a2a-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="b2a2a-127">string</span><span class="sxs-lookup"><span data-stu-id="b2a2a-127">string</span></span> | <span data-ttu-id="b2a2a-128">MITRE ATT&觸發警示之活動的 CK 技術</span><span class="sxs-lookup"><span data-stu-id="b2a2a-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b2a2a-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2a2a-129">Related topics</span></span>
- [<span data-ttu-id="b2a2a-130">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="b2a2a-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b2a2a-131">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="b2a2a-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b2a2a-132">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="b2a2a-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b2a2a-133">跨裝置、電子郵件、應用程式和身分識別搜捕</span><span class="sxs-lookup"><span data-stu-id="b2a2a-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b2a2a-134">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="b2a2a-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b2a2a-135">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="b2a2a-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
