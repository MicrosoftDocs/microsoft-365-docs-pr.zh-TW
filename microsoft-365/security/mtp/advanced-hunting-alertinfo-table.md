---
title: Advanced 搜尋架構中的 AlertInfo 表格
description: 深入瞭解高級搜尋架構的 AlertInfo 資料表中的警示產生事件
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，microsoft 威脅防護，microsoft 365，mtp，m365，search，query，遙測，schema reference，kusto，table，column，data type，MITRE，ATT&CK，Microsoft Defender ATP，MDATP，Office 365 ATP，Microsoft Cloud App Security，MCAS，and Azure ATP
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
ms.openlocfilehash: 36e76ae097dc31c6d7eb7eeff18dd2128ff0cc5c
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649484"
---
# <a name="alertinfo"></a><span data-ttu-id="5e9d3-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="5e9d3-104">AlertInfo</span></span>

<span data-ttu-id="5e9d3-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5e9d3-105">**Applies to:**</span></span>
- <span data-ttu-id="5e9d3-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="5e9d3-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5e9d3-107">[！附注] `AlertInfo` [高級搜尋](advanced-hunting-overview.md)架構中的表格包含來自 Microsoft Defender atp、Office 365 Atp、Microsoft Cloud App SECURITY 和 Azure atp 的提醒資訊。</span><span class="sxs-lookup"><span data-stu-id="5e9d3-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="5e9d3-108">使用這個參考來建立從此表格取回之資訊的查詢。</span><span class="sxs-lookup"><span data-stu-id="5e9d3-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5e9d3-109">如需進階搜捕結構描述中其他表格的資訊，[請參閱進階搜捕參考](advanced-hunting-schema-tables.md) (部分內容為機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="5e9d3-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5e9d3-110">欄名稱</span><span class="sxs-lookup"><span data-stu-id="5e9d3-110">Column name</span></span> | <span data-ttu-id="5e9d3-111">資料類型</span><span class="sxs-lookup"><span data-stu-id="5e9d3-111">Data type</span></span> | <span data-ttu-id="5e9d3-112">描述</span><span class="sxs-lookup"><span data-stu-id="5e9d3-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5e9d3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5e9d3-113">datetime</span></span> | <span data-ttu-id="5e9d3-114">事件記錄的日期和時間</span><span class="sxs-lookup"><span data-stu-id="5e9d3-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="5e9d3-115">字串</span><span class="sxs-lookup"><span data-stu-id="5e9d3-115">string</span></span> | <span data-ttu-id="5e9d3-116">警示的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="5e9d3-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="5e9d3-117">字串</span><span class="sxs-lookup"><span data-stu-id="5e9d3-117">string</span></span> | <span data-ttu-id="5e9d3-118">警示標題</span><span class="sxs-lookup"><span data-stu-id="5e9d3-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="5e9d3-119">字串</span><span class="sxs-lookup"><span data-stu-id="5e9d3-119">string</span></span> | <span data-ttu-id="5e9d3-120">輸入由警示所識別的威脅指示器或入侵活動類型</span><span class="sxs-lookup"><span data-stu-id="5e9d3-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="5e9d3-121">字串</span><span class="sxs-lookup"><span data-stu-id="5e9d3-121">string</span></span> | <span data-ttu-id="5e9d3-122">表示由警示所識別之威脅指示器或入侵活動的潛在影響 (高、中或低)</span><span class="sxs-lookup"><span data-stu-id="5e9d3-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="5e9d3-123">字串</span><span class="sxs-lookup"><span data-stu-id="5e9d3-123">string</span></span> | <span data-ttu-id="5e9d3-124">提供提醒資訊的產品或服務</span><span class="sxs-lookup"><span data-stu-id="5e9d3-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="5e9d3-125">string</span><span class="sxs-lookup"><span data-stu-id="5e9d3-125">string</span></span> | <span data-ttu-id="5e9d3-126">識別值得注意之元件或活動的偵測技術或感應器</span><span class="sxs-lookup"><span data-stu-id="5e9d3-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="5e9d3-127">string</span><span class="sxs-lookup"><span data-stu-id="5e9d3-127">string</span></span> | <span data-ttu-id="5e9d3-128">MITRE ATT&與觸發警示之活動相關聯的 CK 技術</span><span class="sxs-lookup"><span data-stu-id="5e9d3-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5e9d3-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="5e9d3-129">Related topics</span></span>
- [<span data-ttu-id="5e9d3-130">進階搜捕概觀</span><span class="sxs-lookup"><span data-stu-id="5e9d3-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5e9d3-131">了解查詢語言</span><span class="sxs-lookup"><span data-stu-id="5e9d3-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5e9d3-132">使用共用查詢</span><span class="sxs-lookup"><span data-stu-id="5e9d3-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5e9d3-133">跨裝置、電子郵件、應用程式及身分識別搜尋</span><span class="sxs-lookup"><span data-stu-id="5e9d3-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5e9d3-134">了解結構描述</span><span class="sxs-lookup"><span data-stu-id="5e9d3-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5e9d3-135">套用查詢最佳做法</span><span class="sxs-lookup"><span data-stu-id="5e9d3-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
